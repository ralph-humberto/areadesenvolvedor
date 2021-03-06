## Estrutura da URI

A estrutura da URI para os endpoints deve ser implementada conforme abaixo:  
`<host> / open-banking / <api> / <versão> / <recurso>`

Os componentes desta estrutura de URI estão descritos abaixo:

* **Host**: O host de API da entidade financeira implementadora é um endereço base definido pela entidade transmissora de dados.
* **“open-banking”**: Esta é uma string constante que representa a finalidade desta API.
* **API**: A API que será consumida (P.ex. channels).
* **Versão**: O número da versão da API. Na URI a versão deve ser precedida pela letra "v" seguida pelo número da versão a ser consumida (P.ex. v1, v2, v25).
* **Recurso**: O recurso a ser consumido dentro de uma API. Utilizando como exemplo a API `channels`, a mesma possui 4 recursos:
	- banking-agents
    - branches
    - eletronic-channels
	- phone-channels
	
A versão minor será repassada apenas no header do payload de resposta, orientando a instituição receptora sobre quais serão os dados no retorno.
	
Como exemplo, para realizar o consumo do método `eletronic-channels` da API `channels` na versão `1`, a URI ficaria com a seguinte estrutura:  

`<host>/open-banking/channels/v1/eletronic-channels`



	- O elemento `[versão]` sofrerá ajustes e se limitará a informar a versão major, sem mencionar a versão minor. Esse ajuste reduz complexidade de gestão, ao prover maior flexibilidade de atualização para o receptor e transmissor.
	- A versão minor será repassada apenas no header do payload de resposta, orientando a instituição receptora sobre quais serão os dados no retorno. Não haverá prazos para implementação de versões minor pelas instituições transmissoras. Alterações que resultem em quebra de contrato serão categorizadas como major.