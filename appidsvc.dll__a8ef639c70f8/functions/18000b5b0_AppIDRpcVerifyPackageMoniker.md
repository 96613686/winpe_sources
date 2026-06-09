# AppIDRpcVerifyPackageMoniker

- ea: `0x18000b5b0`
- end: `0x18000b682`
- name: `AppIDRpcVerifyPackageMoniker`
- size: `210`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, PCWSTR packageFullName, int *, unsigned __int64 *, unsigned int *, unsigned __int8 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004c28`
- `0x18000b5b0`
- `0x18000d010`

## import_xrefs

- `RPCRT4!RpcAsyncAbortCall` at `0x18000b619`
- `RPCRT4!RpcAsyncAbortCall` at `0x18000b619`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000b66b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000b66b`
- `RPCRT4!RpcServerTestCancel` at `0x18000b607`
- `RPCRT4!RpcServerTestCancel` at `0x18000b607`

## pseudocode

```c
RPC_STATUS __fastcall AppIDRpcVerifyPackageMoniker(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        PCWSTR packageFullName,
        int *a4,
        unsigned __int64 *a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9)
{
  int v13; // ebx

  *a8 = 0;
  *a9 = 0;
  *a7 = 0;
  *a6 = 0;
  *a5 = 0;
  if ( !RpcServerTestCancel(BindingHandle) )
    return RpcAsyncAbortCall(pAsync, 0x71Au);
  v13 = AipSvcPopulateCacheForPackage(packageFullName, a8, a9, a7, a6, a5);
  if ( v13 < 0 )
  {
    if ( g_AiLogFunctionCallErrorEvent )
      g_AiLogFunctionCallErrorEvent(L"24", L":<", (unsigned int)v13);
  }
  *a4 = v13;
  return RpcAsyncCompleteCall(pAsync, 0);
}

```

## disassembly

```asm
0x18000b5b0  push    rbx
0x18000b5b2  push    rbp
0x18000b5b3  push    rsi
0x18000b5b4  push    rdi
0x18000b5b5  push    r12
0x18000b5b7  push    r13
0x18000b5b9  push    r14
0x18000b5bb  push    r15
0x18000b5bd  sub     rsp, 38h
0x18000b5c1  mov     rbx, [rsp+78h+arg_38]
0x18000b5c9  xor     eax, eax
0x18000b5cb  mov     r14, [rsp+78h+arg_40]
0x18000b5d3  mov     rdi, rcx
0x18000b5d6  mov     r15, [rsp+78h+arg_30]
0x18000b5de  mov     rcx, rdx; BindingHandle
0x18000b5e1  mov     rbp, [rsp+78h+arg_28]
0x18000b5e9  mov     rsi, r9
0x18000b5ec  mov     r12, [rsp+78h+arg_20]
0x18000b5f4  mov     r13, r8
0x18000b5f7  mov     [rbx], rax
0x18000b5fa  mov     [r14], rax
0x18000b5fd  mov     [r15], rax
0x18000b600  mov     [rbp+0], eax
0x18000b603  mov     [r12], rax
0x18000b607  call    cs:__imp_RpcServerTestCancel
0x18000b60d  test    eax, eax
0x18000b60f  jnz     short loc_18000B621
0x18000b611  mov     edx, 71Ah; ExceptionCode
0x18000b616  mov     rcx, rdi; pAsync
0x18000b619  call    cs:__imp_RpcAsyncAbortCall
0x18000b61f  jmp     short loc_18000B671
0x18000b621  mov     [rsp+78h+var_50], r12; unsigned __int64 *
0x18000b626  mov     r9, r15; unsigned __int8 **
0x18000b629  mov     r8, r14; unsigned __int16 **
0x18000b62c  mov     [rsp+78h+var_58], rbp; unsigned int *
0x18000b631  mov     rdx, rbx; unsigned __int16 **
0x18000b634  mov     rcx, r13; packageFullName
0x18000b637  call    ?AipSvcPopulateCacheForPackage@@YAJPEAGPEAPEAG1PEAPEAEPEAKPEA_K@Z; AipSvcPopulateCacheForPackage(ushort *,ushort * *,ushort * *,uchar * *,ulong *,unsigned __int64 *)
0x18000b63c  mov     ebx, eax
0x18000b63e  test    eax, eax
0x18000b640  jns     short loc_18000B664
0x18000b642  mov     rax, cs:g_AiLogFunctionCallErrorEvent
0x18000b649  test    rax, rax
0x18000b64c  jz      short loc_18000B664
0x18000b64e  mov     r8d, ebx
0x18000b651  lea     rdx, asc_18000ED10; ":<"
0x18000b658  lea     rcx, a24_7; "24"
0x18000b65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b664  xor     edx, edx; Reply
0x18000b666  mov     [rsi], ebx
0x18000b668  mov     rcx, rdi; pAsync
0x18000b66b  call    cs:__imp_RpcAsyncCompleteCall
0x18000b671  add     rsp, 38h
0x18000b675  pop     r15
0x18000b677  pop     r14
0x18000b679  pop     r13
0x18000b67b  pop     r12
0x18000b67d  pop     rdi
0x18000b67e  pop     rsi
0x18000b67f  pop     rbp
0x18000b680  pop     rbx
0x18000b681  retn
```
