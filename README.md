# Ola meu nome é tayron yuri dos reis da silva, sou da turma cc1ma de ciencia da computação e vim apresentar solo o trabalho. 
# O trabalho consiste em fazer 3 jogos em cmd no falcon ou no Flowgorithm. Esses 3 jogos são: Pergunta e resposta, Cobra na caixa! e Gousmas War
# O jogo foi feito no programa Falcon C++, na Linguagem C, com o uso de IA em parte do desenvolvimento.
# Aqui abaixo esta o codigo fonte usado para rodar os jogos com todas as competencias mencionadas na atividade.
---- jogo ----

#include <stdio.h>
#include <stdlib.h>

// função pra mostra o menu
int exibir_menu() {
    int opcao;
    while (1) {
        printf("\n----- TITULO DO JOGO -----\n");
        printf("1. Pergunta e Resposta\n");
        printf("2. Cobra na Caixa!\n");
        printf("3. Gousmas War\n");
        printf("4. Sair\n");
        printf("Escolha uma opcao: ");
        scanf("%d", &opcao);

        // verifica se a opção é válida
        if (opcao >= 1 && opcao <= 4) {
            return opcao;
        } else {
            printf("Opção inválida. Tente novamente.\n");
        }
    }
}

// coisa pra mostra o jogo pergunta e resposta
int jogo_pergunta_resposta() {
    int resposta, pergunta = 1;

    printf("\n----- Jogo: Pergunta e Resposta -----\n");
    printf("Responda as seguintes perguntas:\n");

    while (pergunta <= 5) {
        if (pergunta == 1) {
            printf("1. Qual e a materia do giroto?\n");
            printf("1) pensamento computacional\n2) algebra linear\n3) algoritmo e codificacao de sistemas\n4) programacao de sofware\n");
            while (1) {
                printf("Escolha a alternativa (1-4): ");
                scanf("%d", &resposta);
                if (resposta >= 1 && resposta <= 4) break;
                else printf("Resposta inválida. Escolha entre 1 e 4.\n");
            }
            if (resposta == 3) printf("Resposta correta!\n");
            else printf("Resposta incorreta! A resposta correta e: 3) algoritmo e codificacao de sistemas\n");
        } else if (pergunta == 2) {
            printf("2. Quanto e 50-12*2\n");
            printf("1) 74\n2) 76\n3) 81\n4) 90\n");
            while (1) {
                printf("Escolha a alternativa (1-4): ");
                scanf("%d", &resposta);
                if (resposta >= 1 && resposta <= 4) break;
                else printf("Resposta inválida. Escolha entre 1 e 4.\n");
            }
            if (resposta == 2) printf("Resposta correta!\n");
            else printf("Resposta incorreta! A resposta correta e: 2) 76\n");
        } else if (pergunta == 3) {
            printf("3. qual nome da capital do Brasil?\n");
            printf("1) Brasilia\n2) Sao paulo\n3) Rio de janeiro\n4) Belem\n");
            while (1) {
                printf("Escolha a alternativa (1-4): ");
                scanf("%d", &resposta);
                if (resposta >= 1 && resposta <= 4) break;
                else printf("Resposta inválida. Escolha entre 1 e 4.\n");
            }
            if (resposta == 1) printf("Resposta correta!\n");
            else printf("Resposta incorreta! A resposta correta e: 1) Brasilia\n");
        } else if (pergunta == 4) {
            printf("4. em que ano o homem pisou na lua?\n");
            printf("1) 1945\n2) 1969\n3) 1901\n4) 1922\n");
            while (1) {
                printf("Escolha a alternativa (1-4): ");
                scanf("%d", &resposta);
                if (resposta >= 1 && resposta <= 4) break;
                else printf("Resposta inválida. Escolha entre 1 e 4.\n");
            }
            if (resposta == 2) printf("Resposta correta!\n");
            else printf("Resposta incorreta! A resposta correta e: 2) 1969\n");
        } else if (pergunta == 5) {
            printf("5. qual o pais com o maior indice de felicidade no mundo\n");
            printf("1) Brasil\n2) India\n3) Finlandia\n4) Estados Unidos\n");
            while (1) {
                printf("Escolha a alternativa (1-4): ");
                scanf("%d", &resposta);
                if (resposta >= 1 && resposta <= 4) break;
                else printf("Resposta inválida. Escolha entre 1 e 4.\n");
            }
            if (resposta == 3) printf("Resposta correta!\n");
            else printf("Resposta incorreta! A resposta correta e: 3) Finlandia\n");
        }
        pergunta++;
    }

    return 1; // retorna 1 pra mostrar q o jogo foi completado
}

// codigo pro jogo cobra na caixa
int jogo_cobra_na_caixa() {
    int escolha, sorteio, continuar;
    
    // sortear posicao do botao e da cobra
    sorteio = rand() % 5 + 1; // uns numero aleatorio de 1 a 5

    printf("\n----- Jogo: Cobra na Caixa! -----\n");

    while (1) {
        printf("Escolha um numero de 1 a 5 para tentar encontrar o botao ou a cobra:\n");
        while (1) {
            printf("Escolha: ");
            scanf("%d", &escolha);
            if (escolha >= 1 && escolha <= 5) break;
            else printf("Escolha inválida. Digite um número entre 1 e 5.\n");
        }

        if (escolha == sorteio) {
            printf("Voce encontrou o botao! Parabens, voce venceu!\n");
            break;
        } else if (escolha == rand() % 5 + 1) {
            printf("Voce encontrou a cobra! Game Over!\n");
            break;
        } else {
            printf("A caixa esta vazia. Tente novamente.\n");
        }
    }

    // pergunta se o jogador quer jogar denovo ou ir pro menu
    while (1) {
        printf("\nDeseja jogar novamente? (1 para sim, 2 para voltar ao menu): ");
        scanf("%d", &continuar);

        if (continuar == 1) {
            return jogo_cobra_na_caixa();  // Reinicia o jogo
        } else if (continuar == 2) {
            return 2;  // Retorna para o menu
        } else {
            printf("Opção inválida. Digite 1 ou 2.\n");
        }
    }
}

// codigo do joguinho da gosma :c (fiz com IA).
int jogo_gousmas_war() {
    int jogador1_furia_gousma1 = 1, jogador1_furia_gousma2 = 1;
    int jogador2_furia_gousma1 = 1, jogador2_furia_gousma2 = 1;
    int comando, jogador_atual = 1; // 1 = Jogador 1, 2 = Jogador 2

    printf("\n----- Jogo: Gousmas War -----\n");
    printf("Dois jogadores comecam com 2 Gousmas cada, com furia = 1.\n");
    printf("Quando uma Gousma ataca a outra, ela transfere todo seu nivel de furia para a Gousma atacada.\n");

    while (jogador1_furia_gousma1 <= 5 && jogador1_furia_gousma2 <= 5 && jogador2_furia_gousma1 <= 5 && jogador2_furia_gousma2 <= 5) {
        if (jogador_atual == 1) {
            printf("\n--- Jogador 1 (Furia Gousma1: %d, Furia Gousma2: %d) ---\n", jogador1_furia_gousma1, jogador1_furia_gousma2);
            printf("Escolha uma acao:\n");
            printf("1. Atacar com Gousma 1\n");
            printf("2. Atacar com Gousma 2\n");
            printf("3. Dividir Gousma\n");
            while (1) {
                scanf("%d", &comando);
                if (comando >= 1 && comando <= 3) break;
                else printf("Opção inválida. Escolha entre 1 e 3.\n");
            }

            if (comando == 1) {
                jogador2_furia_gousma1 += jogador1_furia_gousma1;  // Gousma1 de Jogador 1 ataca Gousma1 de Jogador 2
                jogador1_furia_gousma1 = 0;  // Gousma 1 de Jogador 1 foi usada
            } else if (comando == 2) {
                jogador2_furia_gousma2 += jogador1_furia_gousma2;  // Gousma2 de Jogador 1 ataca Gousma2 de Jogador 2
                jogador1_furia_gousma2 = 0;  // Gousma 2 de Jogador 1 foi usada
            } else if (comando == 3) {
                // Jogador 1 decide dividir suas Gousmas
                printf("Dividindo as Gousmas de Jogador 1!\n");
                if (jogador1_furia_gousma1 > 1) {
                    jogador1_furia_gousma1 /= 2; // Divide a furia entre as Gousmas
                    jogador1_furia_gousma2 = jogador1_furia_gousma1; // Aumenta a furia da Gousma2
                }
            }
            jogador_atual = 2;  // Passa a vez para Jogador 2
        } else {
            printf("\n--- Jogador 2 (Furia Gousma1: %d, Furia Gousma2: %d) ---\n", jogador2_furia_gousma1, jogador2_furia_gousma2);
            printf("Escolha uma acao:\n");
            printf("1. Atacar com Gousma 1\n");
            printf("2. Atacar com Gousma 2\n");
            printf("3. Dividir Gousma\n");
            while (1) {
                scanf("%d", &comando);
                if (comando >= 1 && comando <= 3) break;
                else printf("Opção inválida. Escolha entre 1 e 3.\n");
            }

            if (comando == 1) {
                jogador1_furia_gousma1 += jogador2_furia_gousma1;  // Gousma1 de Jogador 2 ataca Gousma1 de Jogador 1
                jogador2_furia_gousma1 = 0;  // Gousma 1 de Jogador 2 foi usada
            } else if (comando == 2) {
                jogador1_furia_gousma2 += jogador2_furia_gousma2;  // Gousma2 de Jogador 2 ataca Gousma2 de Jogador 1
                jogador2_furia_gousma2 = 0;  // Gousma 2 de Jogador 2 foi usada
            } else if (comando == 3) {
                // Jogador 2 decide dividir suas Gousmas
                printf("Dividindo as Gousmas de Jogador 2!\n");
                if (jogador2_furia_gousma1 > 1) {
                    jogador2_furia_gousma1 /= 2; // Divide a furia entre as Gousmas
                    jogador2_furia_gousma2 = jogador2_furia_gousma1; // Aumenta a furia da Gousma2
                }
            }
            jogador_atual = 1;  // Passa a vez para Jogador 1
        }

        // Verifica se alguma Gousma foi desintegrada
        if (jogador1_furia_gousma1 > 5 || jogador1_furia_gousma2 > 5) {
            printf("Jogador 1 perdeu, suas Gousmas se desintegraram!\n");
            break;
        }
        if (jogador2_furia_gousma1 > 5 || jogador2_furia_gousma2 > 5) {
            printf("Jogador 2 perdeu, suas Gousmas se desintegraram!\n");
            break;
        }
    }

    return 1; // Retorna 1 para indicar que o jogo foi completado
}

// codgio pra pergunta se o jogador quer voltar pro menu ou quer jogar dnv
int jogar_novamente() {
    int opcao;
    while (1) {
        printf("\nDeseja jogar novamente? (1 para sim, 2 para voltar ao menu): ");
        scanf("%d", &opcao);

        if (opcao == 1) {
            return 1;  // Joga novamente
        } else if (opcao == 2) {
            return 2;  // Voltar para o menu
        } else {
            printf("Opção inválida. Digite 1 ou 2.\n");
        }
    }
}

// codigo principal
int main() {
    int opcao, resultado;

    while (1) {
        opcao = exibir_menu();  // mostra menu principal e pega a escolha do usuário

        if (opcao == 1) {
            resultado = jogo_pergunta_resposta();  // escolhe o jogo Pergunta e Resposta
            if (resultado == 1) {
                if (jogar_novamente() == 2) continue;  // voltar ao menu se o usuario escolher
            }
        } else if (opcao == 2) {
            resultado = jogo_cobra_na_caixa();  // escolhe o jogo Cobra na Caixa!
            if (resultado == 2) continue;  // volta pro menu se o usuario escolher
        } else if (opcao == 3) {
            resultado = jogo_gousmas_war();  // pega o jogo Gousmas War
            if (resultado == 1) {
                if (jogar_novamente() == 2) continue;  // volta no menu se o jogador escolher
            }
        } else if (opcao == 4) {
            printf("Saindo do programa. Obrigado por jogar!\n");
            break;  // sai do programa(acho q ta funcionando)
        } else {
            printf("Opção inválida. Tente novamente.\n");  // pra quando o usuario digitar alguma opção invalida
        }
    }

    return 0;
}
#Aqui abaixo esta o registro da conversa que tive com o ChatGPT
![ia conversa1](https://github.com/user-attachments/assets/e5eba229-f1e3-4154-a747-acd793e179ec)

![ia conversa1 1](https://github.com/user-attachments/assets/21785de5-dd8a-41f8-afd5-fe9fe881c302)

![conversa ia1 2](https://github.com/user-attachments/assets/e5d4403a-1ba4-4e7a-b2b6-9c4c0869e15e)

![conversa ia1 3](https://github.com/user-attachments/assets/c58101f4-673f-48f7-92ce-333097a03910)

![conversa ia 1 4](https://github.com/user-attachments/assets/be7b5bb4-5907-4f18-8fcc-2e9dd7d3e856)

![conversa ia1 5](https://github.com/user-attachments/assets/21959d52-1b9a-462e-acb1-48a3a95fc204)

![conversa ia1 6](https://github.com/user-attachments/assets/9afcf2fa-d80a-464a-a703-7bc2c3a56e28)

![conversa ia1 7](https://github.com/user-attachments/assets/8336efb4-6e2b-431c-b9f0-c5d919887bbc)

![conversa ia 1 8](https://github.com/user-attachments/assets/028f4acc-a379-4bec-97e7-5552caba490a)

![conversa ia 1 9](https://github.com/user-attachments/assets/c0785ac4-10b1-43aa-9161-4d0b04917250)

![conversa ia2 0](https://github.com/user-attachments/assets/f8eb30ee-185f-4655-8bd4-694e593cc497)

![conversa ia 2 1](https://github.com/user-attachments/assets/263600ff-2e53-4330-b5a9-97a833d9a626)

![Captura de tela 2025-03-26 193844](https://github.com/user-attachments/assets/13b5ce6a-5cc2-431d-8953-fab4cdcf7e2b)





