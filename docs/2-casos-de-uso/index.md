# Casos de uso

## 1. Diagrama de casos de uso

![Diagrama Caso de Uso Lembrou](https://github.com/sampaiolucas/oic_iot_mackenzie-projeto-XXX/blob/master/docs/2-casos-de-uso/imagens/Caso%20de%20Uso.PNG)

## 2. Especificação dos casos de uso

### 2.1. Caso de uso **CADASTRAR Medicamento**

| Campo          | Informação        |
|---|---|
| Identificador: | UC01              |
| Nome:          | Cadastrar Medicamento |
| Atores:        | Usuário Final |
| Sumário:       | Interação entre usuário e Blynk para inserir um medicamento para o dispositivo |

| Fluxo Principal |
|---|
| 1) O Usuário Final Seleciona a opção **Adicionar Medicamento** inserindo inicialmente o nome do Remédio |
| 2) O Sistema então pergunta a partir de quando ele irá cronometrar o tempo: A partir da hora atual ou horário Fixo |
| 3) O Usuário seleciona alguma das duas opções |
| 4) Caso Selecionado Hora Atual, pular passo 6 |
| 5) Caso Selecionado Horario Fixo, o sistema perguntará quando será a primeira dose |
| 6) Após qualquer das duas opções, o sistema pergunta qual a periodicidade do remédio |
| 7) O Sistema perguntará se este remédio tem rigidez ou não (Caso sim, será emitido um alerta sonoro ao extrapolar o tempo) |
| 8) Finalizado, o dispositivo irá emitir uma luz verde caso o cadastro tenha sido efetuado com sucesso |
| 9) A partir de então, os LEDs assumirão três estados: Amarelo, quando ainda não foi tomado, Azul, quando foi tomado e vermelho quando passou do período |


| Fluxo Alternativo (2a): O sistema não encontra algum erro de digitação |
|---|
| 1) O sistema informa que houve um erro de digitação na etapa 1, 5 ou 6 do processo.|
| 2) O Sistema reinicia o processo |

### 2.2. Caso de uso **Excluir Medicamento**

| Campo          | Informação        |
|---|---|
| Identificador: | UC01              |
| Nome:          | Excluir Medicamento |
| Atores:        | Usuário Final |
| Sumário:       | Interação entre usuário e Blynk para excluir o medicamento para o dispositivo |

| Fluxo Principal |
|---|
| 1) O Usuário Final Seleciona a opção **Excluir Medicamento**  |
| 2) O Sistema pede a confirmação para exclusão |
| 3) O Usuário Confirma exclusão |
| 4) O Sistema reseta as suas configurações e fica em estado default (com duas luzes azuis ligadas) |

### 2.3. Caso de uso **Uso de Medicamento**

| Campo          | Informação        |
|---|---|
| Identificador: | UC01              |
| Nome:          | Registrar Uso de Medicamento |
| Atores:        | Usuário Final |
| Sumário:       | Interação entre usuário e Dispositivo para registrar o uso do medicamento |

| Fluxo Principal |
|---|
| 1) O Dispositivo está emitindo a luz amarela ou vermelha - Não foi tomado o remédio ainda |
| 2) O Usuário aperta o botão no dispositivo para registrar o uso.|
| 3) O Dispositivo passa a emitir a luz azul e o cronometro zera. |
| 4) Quando restar uma hora para o próximo medicamento, a luz azul será desligada automaticamente e a amarela será ligada. |

| Fluxo Alternativo (2a): O Tempo para o medicamento passa |
|---|
| 1) Caso o tempo extrapole, a luz amarela será desligada e a vermelha será acessa |
| 2) Caso seja um remédio importante, será emitido um alerta sonoro |
| 3) O Alerta sonoro e a luz vermelha serão desligadas apenas após usuário realizar a etapa 2 do fluxo principal |
| 4) Retonar para o passo 3 do fluxo principal |
