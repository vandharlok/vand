# vand
#include <stdlib.h>
#include <string.h>
#include <stdio.h>
typedef struct lista{
    int valor;
struct lista* prox;
}Lista;

Lista* deslocaMaior(Lista* L){
   Lista* aux = L; //Percorre lista
   Lista* maior = L;// Guarda o maior encontrado
   Lista* antMaior = NULL; // Sala o antereior ao maior
  Lista* antAux = NULL;

   //Laço para encontrar o maior
   while(aux != NULL){
     if(maior->valor < aux->valor){
       antMaior = antAux;//Salvo a posicao anterior
       maior = aux;
     }
     antAux = aux;
     aux =aux->prox;    
   }
  //30->60->NULL
   antMaior->prox = maior->prox;
   maior->prox = L;
  return maior;  
}
