# Corretor Ortografico em Python Utilizando tecnicas de NLP

![Badge em Desenvolvimento](http://img.shields.io/static/v1?label=STATUS&message=FINALIZADO&color=GREEN&style=for-the-badge)

| :placard: Vitrine.Dev |     |
| -------------         | --- |
| :sparkles: Nome       | Corretor Ortografico
| :label: Tecnologias   | Python
| :rocket: URL          | https://github.com/wesleyfuchs/Corretor-ortografico
| :fire: Desafio        | https://cursos.alura.com.br/course/nlp-corretor-ortografico

<!-- Capa da Vitrine.dev-->
![1-1024x576](https://user-images.githubusercontent.com/55562529/227060027-83e4092f-e943-452c-8aed-b88be98d5635.jpg#vitrinedev)


## Sobre o projeto 📚

Esse corretor ortografico foi o projeto criado durante o curso [Corretor Ortográfico em Python: aplicando técnicas de NLP](https://cursos.alura.com.br/course/nlp-corretor-ortografico) da Alura.</br>
A ideia do projeto foi criar um corretor que como parametro uma palavra digitada de maneira equivocada, gerar as possíveis palavras corretas, e então inferir quais daquelas possíveis candidatas era possivelmente a correta.</br> 
Durante o desenvolvimento foram adicionados algoritimos onde nós inseríamos letras na palavra digitada equivocadamente, deletamos letras, trocamos letras e invertemos letras da palavra. Para realizar a inferência da palavra correta foi usada uma base de dados, e neste caso foram os artigos do Blog da Alura compilados em artigos.txt.


## Desenvolvimento

Começei pela importação da base de dados

![import](https://user-images.githubusercontent.com/55562529/227054947-5ffa3eef-dbfe-4aae-b608-272ba329d4f6.png)
#
Separei a string em pequenos tokens. Para isso, utilizei a biblioteca Python específica para processamento de linguagem natural chamada nltk.</br>
Depois, separei dos tokens apenas os que eram palavras, e aí foi feita uma contagem  do número de palavras que havia no nosso dataset e tambem do numero de palavras unicas.

![bibliteca-nltk](https://user-images.githubusercontent.com/55562529/227054945-58820018-b7a0-4bab-833d-896771c19f9a.png)
![tokenize](https://user-images.githubusercontent.com/55562529/227054961-e0d7a7c6-2ada-469e-990a-136e6441190d.png)
![palavras_unicas](https://user-images.githubusercontent.com/55562529/227054949-6408c61d-6ea3-45ac-aea2-2c3bdfbf9333.png)
#
Após isso, foi iniciada a construção do algoritimo 

![Inserir_letras](https://user-images.githubusercontent.com/55562529/227054967-3fbb8ece-66bb-4344-9119-65ddbd5c4fab.png)
![palavras_geradas](https://user-images.githubusercontent.com/55562529/227054969-6ceb1018-33b7-4ac6-b9e0-4fb224d64f9a.png)
#
A função corretor() faz uma comparação das palavras geradas e procura pela palavra com mais aparições dentro do dataset

![corretor](https://user-images.githubusercontent.com/55562529/227054974-4a86a287-3c95-468c-b94f-9518b071d515.png)
#
Para testar o corretor foi criado uma função que mostra a taxa de acerto do corretor após aplicar testes em um arquivo .txt com diversas palavras.


![dados_teste](https://user-images.githubusercontent.com/55562529/227059326-8e96f198-41e6-41c8-b993-84ddbf05efa1.png)
![avaliador_1](https://user-images.githubusercontent.com/55562529/227054965-7e9c9854-8c1b-4858-a73a-88659c9236e1.png)

Alem da inserir_letra(), foram adicionadas as funções deletando_caracteres(), troca_letra() e inverte_letra().</br>
Chegando então a quase 77% de taxa de acerto.

![avaliador_2](https://user-images.githubusercontent.com/55562529/227054977-b0f80b36-459b-48a1-96ae-0e35f5f82761.png)
#
Foi criado tambem um corretor_turbinado() que tem como ideia corrigir palavras com 2 erros, que consegue corrigir palavras que o nosso antigo corretor não conseguia, porem, depois de testa-lo foi constatado uma taxa de 55.38% de acerto fazendo com que o antigo continue tendo uma taxa de acerto maior e continue sendo a melhor opção 

![corretor_turbinado](https://user-images.githubusercontent.com/55562529/227054982-2bc3408c-6387-4660-94ae-61d82690a313.png)

