# Thread
//Create a thread and print the process id. 
//Thread id and process id
#include <stdio.h>
#include <pthread.h>
#include <stdlib.h>
#define THREAD_TOTAL 5

void *thread(void *vargp){
	int p_id;
	p_id=getpid();
    	printf("thread id= %u \n", pthread_self());
	printf("Process id : %d\n", p_id);
}

int main() {
    int j,m;
    pthread_t t_id [THREAD_TOTAL];
   for(j=0; j< THREAD_TOTAL; j++){
        pthread_create(&t_id,NULL,thread,(void*)&t_id);
    }
    pthread_exit(NULL); // terminate the thread
    return 0;
}
