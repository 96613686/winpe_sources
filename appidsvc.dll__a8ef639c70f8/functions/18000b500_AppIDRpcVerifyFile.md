# AppIDRpcVerifyFile

- ea: `0x18000b500`
- end: `0x18000b5a0`
- name: `AppIDRpcVerifyFile`
- size: `160`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, unsigned int, _DWORD *, _DWORD *, _QWORD *, _DWORD *, PVOID *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800053c0`
- `0x18000b500`

## import_xrefs

- `RPCRT4!RpcAsyncAbortCall` at `0x18000b52d`
- `RPCRT4!RpcAsyncAbortCall` at `0x18000b52d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000b58a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000b58a`
- `RPCRT4!RpcServerTestCancel` at `0x18000b51b`
- `RPCRT4!RpcServerTestCancel` at `0x18000b51b`

## pseudocode

```c
RPC_STATUS __fastcall AppIDRpcVerifyFile(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        unsigned int a3,
        _DWORD *a4,
        _DWORD *a5,
        _QWORD *a6,
        _DWORD *a7,
        PVOID *a8,
        _QWORD *a9,
        _QWORD *a10,
        _QWORD *a11)
{
  unsigned __int64 v12; // rsi

  v12 = a3;
  if ( !RpcServerTestCancel(BindingHandle) )
    return RpcAsyncAbortCall(pAsync, 0x71Au);
  *a4 = AiSvcVerifyFile((void *)v12, a5, a6, a7, a8, a9, a10, a11);
  return RpcAsyncCompleteCall(pAsync, 0);
}

```

## disassembly

```asm
0x18000b500  mov     [rsp+arg_0], rbx
0x18000b505  mov     [rsp+arg_8], rsi
0x18000b50a  push    rdi
0x18000b50b  sub     rsp, 40h
0x18000b50f  mov     rbx, rcx
0x18000b512  mov     esi, r8d
0x18000b515  mov     rcx, rdx; BindingHandle
0x18000b518  mov     rdi, r9
0x18000b51b  call    cs:__imp_RpcServerTestCancel
0x18000b521  test    eax, eax
0x18000b523  jnz     short loc_18000B535
0x18000b525  mov     edx, 71Ah; ExceptionCode
0x18000b52a  mov     rcx, rbx; pAsync
0x18000b52d  call    cs:__imp_RpcAsyncAbortCall
0x18000b533  jmp     short loc_18000B590
0x18000b535  mov     rax, [rsp+48h+arg_50]
0x18000b53d  mov     rcx, rsi; int
0x18000b540  mov     r9, [rsp+48h+arg_30]
0x18000b548  mov     r8, [rsp+48h+arg_28]
0x18000b54d  mov     rdx, [rsp+48h+arg_20]
0x18000b552  mov     [rsp+48h+var_10], rax; __int64
0x18000b557  mov     rax, [rsp+48h+arg_48]
0x18000b55f  mov     [rsp+48h+var_18], rax; __int64
0x18000b564  mov     rax, [rsp+48h+arg_40]
0x18000b56c  mov     [rsp+48h+var_20], rax; __int64
0x18000b571  mov     rax, [rsp+48h+arg_38]
0x18000b579  mov     [rsp+48h+var_28], rax; __int64
0x18000b57e  call    AiSvcVerifyFile
0x18000b583  xor     edx, edx; Reply
0x18000b585  mov     [rdi], eax
0x18000b587  mov     rcx, rbx; pAsync
0x18000b58a  call    cs:__imp_RpcAsyncCompleteCall
0x18000b590  mov     rbx, [rsp+48h+arg_0]
0x18000b595  mov     rsi, [rsp+48h+arg_8]
0x18000b59a  add     rsp, 40h
0x18000b59e  pop     rdi
0x18000b59f  retn
```
