# vxi1Discovery
step to compile RPC source code:
1. rpcgen test.x
   this step will generate three files: test_clnt.c test.h test_svc.c
2. generate a cilent C file:
   rpcgen -Sc -o test_client.c test.x
3. generate a server function c file:
   rpcgen -Ss -o test_svc_func.c -o test.x // tips: test_svc_func.c is functions list file that will be call by rpc server
4. add some code in test_svc_func.c 
5. generate really cilent and server:
   gcc -Wall -o server test_svc.c test_clnt.c test_svc_func.c
   gcc -Wall -o client test_client.c test_clnt.c 
6. rpcgen --help to get help 
