# Identificação de Bloqueio por Hidrato em Linhas de Serviço de Poços Produtores de Óleo

#### Aluno: [Fabiano Garcia Drumond](https://github.com/fgdrumond).
#### Orientadora: [Manoela Kohler](https://github.com/manoelakohler).

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

---

### Resumo

Até um passado recente, o processo de gerenciamento de eventos de anormalidade, também conhecido como AEM (*Abnormal Event Management*) dentro do sistema Petrobras se deu exclusivamente através da análise individualizada de variáveis de processo; isto é, avaliando-se o comportamento medido de uma variável específica (pressão, temperatura, vazão...) e do eventual atingimento de valores definidos como limites superior e inferior para cada uma dessas variáveis.

Contudo, é notório que os eventos geradores de perdas (de produção ou injeção) geram intercorrências não em uma única, mas em um conjunto de variáveis, cuja conhecimento de um especialista é capaz de interpretar e inferir o que acontece com determinado poço.

Ocorre que na grande maioria dos eventos que conduzem às perdas (de produção ou injeção), o processo de interpretação, análise e diagnóstico é moroso e se dá após o ocorrido, ou seja, a perda não pôde ser evitada e se manterá até que se possua um diagnóstico adequado. O fato decorre do acompanhamento individualizado das variáveis de processo ser incapaz de  diagnosticar (classificar) o(s) evento(s). Ao mesmo tempo, faz-se impossível manter conjuntos de especialistas acompanhando as variáveis de processo e seu comportamento em tempo integral.

Nesse contexto surge o projeto MAE (Monitoramento de Alarmes Especialistas), cujo objetivo é identificar padrões automáticos do conjunto de variáveis medidas, de modo a classificar a ocorrências em poços e indicar diagnósticos de anormalidade. A implementação dos alarmes especialistas permite que as melhores práticas da classificação de anormalidades estejam incorporadas em um sistema que roda 24 horas por dia.

A obtenção dos padrões de comportamento das variáveis de processo e sua respectiva classificação com os possíveis modos de falha se dá através de técnicas de *machine learning*; fazendo-se uso do histórico das ocorrências e/ou através de simulações computacionais que emulem o modo de falha que se deseje identificar.

Dentre os possíveis modos de falha, a formação de hidrato na linha de serviço/*gas lift* foi o objeto deste estudo.

Isto posto, propõem-se o presente trabalho a levantar um adequado *data set* dos eventos de formação de hidratos nas linhas de serviço de poços, assim como de outros eventos não desejados, e através de técnicas de *machine learning*, criar um classificador que consiga identificar a formação de hidratos nas linhas de serviço em meio a um conjunto de eventos outros.

A abordagem adotada é do tipo OVA (*One Versus All*) onde se confronta o evento que se deseja classificar (hidrato na linha de serviço) contra uma série de não eventos.

Os não eventos que compõe a base de dados são:
  - Condição normal de produção;
  - Hidrato na linha de produção;
  - Fechamento espúrio da DHSV;
  - Restrição abrupta do choke de produção.

Os atributos que compõem a base de dados para cada registro em cada passo de tempo são:
  - Pressão à jusante do choke de gas lift;
  - Vazão de *gas lift*;
  - Pressão no TPT (Transdutor de Pressão e Temperatura) localizado na ANM;
  - Pressão a montante do choke de produção.

Por tratar de eventos que possuem relação direta com o tempo, utilizando-se do método *rolling*, foram criados atributos adicionais para os registros de forma a preservar o comportamento das variáveis em passos de tempo anteriores.

---

Matrícula: 192.190.084

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
