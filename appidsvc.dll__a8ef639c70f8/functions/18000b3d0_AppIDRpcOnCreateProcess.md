# AppIDRpcOnCreateProcess

- ea: `0x18000b3d0`
- end: `0x18000b4ed`
- name: `AppIDRpcOnCreateProcess`
- size: `285`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, int, __int64, __int64, __int16, int, int, __int64, __int64, int, __int64, int, __int64, int, void *, int, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008578`
- `0x18000b3d0`

## import_xrefs

- `RPCRT4!RpcAsyncAbortCall` at `0x18000b3fe`
- `RPCRT4!RpcAsyncAbortCall` at `0x18000b3fe`
- `RPCRT4!RpcRevertToSelf` at `0x18000b4db`
- `RPCRT4!RpcRevertToSelf` at `0x18000b4db`
- `RPCRT4!RpcImpersonateClient` at `0x18000b40c`
- `RPCRT4!RpcImpersonateClient` at `0x18000b40c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000b4d5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000b4d5`
- `RPCRT4!RpcServerTestCancel` at `0x18000b3ec`
- `RPCRT4!RpcServerTestCancel` at `0x18000b3ec`

## pseudocode

```c
RPC_STATUS __fastcall AppIDRpcOnCreateProcess(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        int a3,
        __int64 a4,
        __int64 a5,
        __int16 a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        int a11,
        __int64 a12,
        int a13,
        __int64 a14,
        int a15,
        void *a16,
        int a17,
        __int64 a18,
        _DWORD *a19)
{
  unsigned int v22; // edx
  RPC_STATUS v24; // eax

  if ( !RpcServerTestCancel(BindingHandle) )
  {
    v22 = 1818;
    return RpcAsyncAbortCall(pAsync, v22);
  }
  v24 = RpcImpersonateClient(BindingHandle);
  if ( v24 )
  {
    v22 = v24;
    return RpcAsyncAbortCall(pAsync, v22);
  }
  *a19 = AiSvcOnCreateProcess(a3, a7, a8, a9, a10, a11, a12, a13, a14, a15, a16, a17, a18);
  RpcAsyncCompleteCall(pAsync, 0);
  return RpcRevertToSelf();
}

```

## disassembly

```asm
0x18000b3d0  push    rbx
0x18000b3d2  push    rbp
0x18000b3d3  push    rsi
0x18000b3d4  push    rdi
0x18000b3d5  sub     rsp, 88h
0x18000b3dc  mov     rbx, rcx
0x18000b3df  movzx   esi, r9w
0x18000b3e3  mov     rcx, rdx; BindingHandle
0x18000b3e6  mov     rbp, r8
0x18000b3e9  mov     rdi, rdx
0x18000b3ec  call    cs:__imp_RpcServerTestCancel
0x18000b3f2  test    eax, eax
0x18000b3f4  jnz     short loc_18000B409
0x18000b3f6  mov     edx, 71Ah; ExceptionCode
0x18000b3fb  mov     rcx, rbx; pAsync
0x18000b3fe  call    cs:__imp_RpcAsyncAbortCall
0x18000b404  jmp     loc_18000B4E1
0x18000b409  mov     rcx, rdi; BindingHandle
0x18000b40c  call    cs:__imp_RpcImpersonateClient
0x18000b412  test    eax, eax
0x18000b414  jz      short loc_18000B41A
0x18000b416  mov     edx, eax
0x18000b418  jmp     short loc_18000B3FB
0x18000b41a  mov     rax, [rsp+0A8h+arg_88]
0x18000b422  movzx   edx, si
0x18000b425  movzx   r9d, [rsp+0A8h+arg_28]
0x18000b42e  mov     rcx, rbp; int
0x18000b431  mov     r8, [rsp+0A8h+arg_20]
0x18000b439  mov     [rsp+0A8h+var_30], rax; __int64
0x18000b43e  mov     eax, [rsp+0A8h+arg_80]
0x18000b445  mov     [rsp+0A8h+var_38], eax; int
0x18000b449  mov     rax, [rsp+0A8h+arg_78]
0x18000b451  mov     [rsp+0A8h+var_40], rax; void *
0x18000b456  mov     eax, [rsp+0A8h+arg_70]
0x18000b45d  mov     [rsp+0A8h+var_48], eax; int
0x18000b461  mov     rax, [rsp+0A8h+arg_68]
0x18000b469  mov     [rsp+0A8h+var_50], rax; __int64
0x18000b46e  mov     eax, [rsp+0A8h+arg_60]
0x18000b475  mov     [rsp+0A8h+var_58], eax; int
0x18000b479  mov     rax, [rsp+0A8h+arg_58]
0x18000b481  mov     [rsp+0A8h+var_60], rax; __int64
0x18000b486  mov     eax, [rsp+0A8h+arg_50]
0x18000b48d  mov     [rsp+0A8h+var_68], eax; int
0x18000b491  mov     rax, [rsp+0A8h+arg_48]
0x18000b499  mov     [rsp+0A8h+var_70], rax; __int64
0x18000b49e  mov     rax, [rsp+0A8h+arg_40]
0x18000b4a6  mov     [rsp+0A8h+var_78], rax; __int64
0x18000b4ab  mov     eax, [rsp+0A8h+arg_38]
0x18000b4b2  mov     [rsp+0A8h+var_80], eax; int
0x18000b4b6  mov     eax, [rsp+0A8h+arg_30]
0x18000b4bd  mov     [rsp+0A8h+var_88], eax; int
0x18000b4c1  call    AiSvcOnCreateProcess
0x18000b4c6  mov     rcx, [rsp+0A8h+arg_90]
0x18000b4ce  xor     edx, edx; Reply
0x18000b4d0  mov     [rcx], eax
0x18000b4d2  mov     rcx, rbx; pAsync
0x18000b4d5  call    cs:__imp_RpcAsyncCompleteCall
0x18000b4db  call    cs:__imp_RpcRevertToSelf
0x18000b4e1  add     rsp, 88h
0x18000b4e8  pop     rdi
0x18000b4e9  pop     rsi
0x18000b4ea  pop     rbp
0x18000b4eb  pop     rbx
0x18000b4ec  retn
```
