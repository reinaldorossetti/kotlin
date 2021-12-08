# Luhn (Mod 10)

Fiz esse fork do Algoritmo de Luhnn em Kotlin, para deixar para os QAs de referência de como realizar os testes em Cartão de Crédito. Além do algoritmo é preciso validar outros pontos citados abaixo.

Wiki [luhn check algorithm](https://en.wikipedia.org/wiki/Luhn_algorithm). 
Implementations in other languages can be found at [github.com/luhn-algorithm](https://github.com/luhnmod10).

Validador online:
https://www.vccgenerator.org/br/credit-card-validator-result/

Gerador de Cartão de Crédito:
https://www.4devs.com.br/gerador_de_numero_cartao_credito

Passo a Passo                                                                                             Total
Número Original                          :  4   5   5   6   7   3   7   5   8   6   8   9   9   8   5   5   
Tirando o último dígito                  :  4   5   5   6   7   3   7   5   8   6   8   9   9   8   5       
Invertendo                               :  5   8   9   9   8   6   8   5   7   3   7   6   5   5   4       
Multiplicando casas ímpares por 2        :  10  8   18  9   16  6   16  5   14  3   14  6   10  5   8       
Subtraia 9 de todos os números acima de 9:  1   8   9   9   7   6   7   5   5   3   5   6   1   5   8       
Somando todos os números                 :  1   8   9   9   7   6   7   5   5   3   5   6   1   5   8       85
Mod 10: 85, módulo 10 = 5 (último dígito do cartão)


Validações:
1. Possuir somente números
2. Ter entre 12 e 19 dígitos (na verdade não há CC com 17 dígitos)
3. Os 6 primeiros dígitos devem indicar um IIN (Issuer identification number) válido. Ele é chamado de BIN no meio bancário.
4. Passar na validação do Algoritmo de Luhnn
5. Validar o soma igual a Zero, o zero ele passa no algoritmo de Luhnn, ou seja "0000" ou "00000000000000000" ele considera como valido.

Medium:
https://reiload-88128.medium.com/validando-cart%C3%B5es-de-cr%C3%A9dito-luhn-algorithm-a4c341ec0bd9

Sobre mais:
https://www.freeformatter.com/credit-card-number-generator-validator.html#howToValidate
