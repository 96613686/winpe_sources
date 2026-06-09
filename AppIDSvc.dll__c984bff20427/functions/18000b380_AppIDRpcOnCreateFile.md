# AppIDRpcOnCreateFile

- ea: `0x18000b380`
- end: `0x18000b3c3`
- name: `AppIDRpcOnCreateFile`
- size: `67`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, __int64, __int64, int, int, int, int, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000b380`

## import_xrefs

- `RPCRT4!RpcAsyncAbortCall` at `0x18000b3a3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000b3b7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000b3b7`
- `RPCRT4!RpcServerTestCancel` at `0x18000b38c`
- `RPCRT4!RpcServerTestCancel` at `0x18000b38c`

## pseudocode

```c
RPC_STATUS __fastcall AppIDRpcOnCreateFile(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        _DWORD *a9)
{
  if ( !RpcServerTestCancel(BindingHandle) )
    return RpcAsyncAbortCall(pAsync, 0x71Au);
  *a9 = 0;
  return RpcAsyncCompleteCall(pAsync, 0);
}

```

## disassembly

```asm
0x18000b380  push    rbx
0x18000b382  sub     rsp, 20h
0x18000b386  mov     rbx, rcx
0x18000b389  mov     rcx, rdx; BindingHandle
0x18000b38c  call    cs:__imp_RpcServerTestCancel
0x18000b392  mov     rcx, rbx; pAsync
0x18000b395  test    eax, eax
0x18000b397  jnz     short loc_18000B3AA
0x18000b399  mov     edx, 71Ah
0x18000b39e  add     rsp, 20h
0x18000b3a2  pop     rbx
0x18000b3a3  jmp     cs:__imp_RpcAsyncAbortCall
0x18000b3aa  mov     rax, [rsp+28h+arg_40]
0x18000b3af  xor     edx, edx; Reply
0x18000b3b1  mov     dword ptr [rax], 0
0x18000b3b7  call    cs:__imp_RpcAsyncCompleteCall
0x18000b3bd  add     rsp, 20h
0x18000b3c1  pop     rbx
0x18000b3c2  retn
```
