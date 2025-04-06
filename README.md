# Azure Cognitive Search: Indexação e Consulta de Dados

Este repositório contém uma prática desenvolvida durante o bootcamp Decola Tech 2025 na prática __"Azure Cognitive Search: Utilizando AI Search para indexação e consulta de Dados"__, utilizando recursos do Azure para importar, indexar e consultar dados de forma inteligente.

## :file_folder: Estrutura do Projeto
- `data/reviews.zip:` Arquivo com as avaliações usadas no projeto.
- `README.md:` Documento com o passo a passo da prática e os aprendizados.

## :gear: Passo a passo
1. Criação da Fonte de Dados
- Criei um container chamado storagemineracao dentro de uma Storage Account no Azure.
- Adicionei 9 arquivos com [reviews](https://github.com/wastecoder/ia-mineracao-dados/blob/main/reviews.zip), baixados da documentação oficial da Microsoft.

2. Configuração do Azure AI Search
- Criei um recurso chamado ia-pesquisa-mineracao-dados.
- A partir do portal do Azure, acessei o recurso e cliquei em "Importar dados".
- Selecionei o container criado anteriormente como fonte de dados.
- Configurei o pipeline para extrair informações com análise cognitiva (já vem pré-configuradas do Azure).

3. Consultas realizadas
- Após a indexação, executei diversas consultas no Azure Search Explorer, utilizando filtros e expressões de busca:

```bash
# Por idioma
search=language:'en'

# Por organização mencionada
search=organizations:'Fourth Coffee'

# Por palavras-chave detectadas
search=keyphrases:'wi-fi'
search=keyphrases:'local art'
search=keyphrases:'coffee drinks'
search=keyphrases:'fun'

# Por localização mencionada
search=locations:'Chicago'

# Por sentimento negativo
search=sentiment:'negative'

# Por dia da semana mencionado nos textos
search=Wednesday
```

## :brain: Insights e Possibilidades
- A ferramenta consegue identificar entidades como organizações, locais e palavras-chave automaticamente, permitindo buscas mais inteligentes.
- As keyphrases e sentimentos extraídos dos textos ajudam a entender a percepção dos usuários e temas mais citados.
- A integração com fontes como Azure Blob Storage torna o processo simples e escalável.
- É possível expandir o uso para análise de feedbacks de clientes, avaliações de produtos, dados de redes sociais e mais.

## 🔧 Ferramentas que podem se beneficiar com isso:
- Chatbots inteligentes que consultam conteúdos indexados.
- Dashboards de BI, como Power BI, integrando os dados via API do Search.
- Sistemas de recomendação, baseados nos termos e sentimentos mais citados.
- Buscas internas em sites, portais ou aplicativos com grandes volumes de texto.
