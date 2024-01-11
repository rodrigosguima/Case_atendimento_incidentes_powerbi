# Case_atendimento_incidentes_powerbi
Dashboard feito PowerBI com técnicas de big query e dax.

1 - Inconsistências encontradas nas planilhas:

* Aplicar a primeira linha como cabeçalho na tabela “Aplicações 2023” (Botão: Usar primeira linha como cabeçalho);
* Linhas em branco nas tabelas “Atendimentos geral”:
  
Resolução:

1. No Power BI Desktop, ir para guia “Página Inicial” e selecione “Transformar Dados” para abrir o editor do power query;
2. Localize as tabelas que contém as linhas em branco que deseja remover;
3. Filtre as linhas em branco selecionando a coluna que possui valores em branco, no cabeçalho da coluna, clique na seta para baixo para abrir o menu suspenso e desmarque a opção "Em branco" para filtrar as linhas em branco/nulo;
4. Remova as linhas em branco selecionando as linhas filtradas (linhas em branco/nulo) e clique com o botão direito na seleção e escolha a opção "Remover";
5. Fechar e aplicar as mudanças em cada tabela.
6. Nome e sobrenome nas tabelas “Atendimentos geral” estavam todas maiúsculas e minúsculas consecutivamente e para ajustar na nova coluna de “Nome responsável”, além de concatenar as colunas Responsável e Sobrenome, foi usada a função a seguir para ajustar o nome do responsável em uma só fonte `Text.Proper([Responsável]) & " " & Text.Proper([Sobrenome])`
9. No campo “Categoria do status” existe dois registros diferentes para tratar casos pendentes: “Itens Pendentes” e “Pendente”.

2 - Insights & Propostas:

1. Média geral de dias aberto muito maior que a média geral concluída;
   
     Indica uma necessidade de otimização nos processos de resolução de problemas ou uma possível sobrecarga na equipe responsável.

3. Média de atendimento por responsável para casos em andamento chega em média de 7 atendimentos;
   
    Sugere que os membros da equipe estão lidando com uma carga de trabalho significativa. Seria útil avaliar a distribuição de tarefas e considerar a possibilidade de reorganizar responsabilidades.

5. Qual o motivo de tanta demora no atendimento e de uma quantidade expressiva de horas de esforço?
   
     Pode ser resultado de processos ineficientes, falta de recursos ou treinamento inadequado. Investigar e melhorar esses aspectos pode reduzir o tempo de resposta.

7. Maior motivo de abertura de chamados gira em torno de falha sistêmica, tanto em minutos quanto em número de id chamados;
   
     Pode ser resultado de processos ineficientes, falta de recursos ou treinamento inadequado, investir em tecnologia. Investigar e melhorar esses aspectos pode reduzir o tempo de resposta.
     
9. Número expressivo de incidentes abertos nos primeiros 20 dias e com mais de 30 dias;
    
      Pode indicar a importância de uma resposta rápida nos estágios iniciais do incidente e a necessidade de acelerar a resolução para evitar atrasos prolongados.

11. Novembro foi o mês onde a média de incidentes abertos foi o mais expressivo (274 incidentes) e a média de incidentes que foram de fato resolvidos está bastante baixa (12 incidentes);
    
    Pode haver uma sobrecarga sazonal ou desafios específicos durante esse período. Avaliar se recursos adicionais são necessários ou se mudanças nos processos podem melhorar a eficiência.

13. Maiores índices de incidentes acontecem no fim do ano (11 de novembro a 17 de novembro e 16 de dezembro a 22 de dezembro, consecutivamente);
    
     Existe aqui um padrão específico no final do ano que contribuem para o aumento de incidentes e preparar recursos extras para esses períodos.

15. Para todos os tipos de aplicações no ano de 2022 foi notório uma tendência positiva entre ago e novembro, podendo observar como padrão entre os meses de set, out e nov por apresentarem os maiores índices em todas as aplicações, diferentemente do ano de 2023, onde os níveis se manteram predominantemente constantes e em todas as aplicações obtiveram maiores registros em dezembro.
    
     Essa análise sazonal é eficiente para alocação de recursos ao longo do ano e para avaliar as razões por trás das mudanças nas tendências pode orientar estratégias para manter o desempenho consistente.

3 - Visão KPI: Identifique através de uma condicional os incidentes abertos na seguinte faixa temporal: 1 a 10 dias, 20 a 25 dias, 26 a 30 dias e mais de 30 dias. Expresse em uma tabela sinalizando-os e monte um KPI.

Resposta:

KPI – De 2022 para 2023 teve um aumento de 3 para 20 casos de incidentes abertos que foram fechados (aumento de 666%) 

Sugestões de KPI: Diminuir média de conclusão de 10 dias para 5 dias;

- O que fazer?
  
Aumentar o número de responsáveis visto que cada um cuidam em média de 7 casos em andamento para diminuir o dia e esforço em cada incidente.

[CLIQUE AQUI PARA VER O DASHBOARD](https://app.powerbi.com/view?r=eyJrIjoiNzFmMGE3YzMtZjMxNy00ZDdhLTgzZTgtNGY4NDI1NDEzNTg0IiwidCI6ImQ1YjYyNzdjLTk1MjctNDI4MS1iMzkxLTJlNjc3YWY4MGM1OCJ9)
