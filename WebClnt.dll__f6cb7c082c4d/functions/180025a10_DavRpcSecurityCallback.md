# DavRpcSecurityCallback

- ea: `0x180025a10`
- end: `0x180025b04`
- name: `DavRpcSecurityCallback`
- size: `244`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025a10`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x180025a8f`
- `RPCRT4!RpcStringBindingParseW` at `0x180025a8f`
- `RPCRT4!RpcBindingServerFromClient` at `0x180025a43`
- `RPCRT4!RpcBindingServerFromClient` at `0x180025a43`
- `RPCRT4!RpcStringFreeW` at `0x180025ae0`
- `RPCRT4!RpcStringFreeW` at `0x180025af1`
- `RPCRT4!RpcStringFreeW` at `0x180025ae0`
- `RPCRT4!RpcStringFreeW` at `0x180025af1`
- `RPCRT4!RpcBindingFree` at `0x180025acf`
- `RPCRT4!RpcBindingFree` at `0x180025acf`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180025a5f`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180025a5f`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180025ab4`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180025ab4`
- `KERNEL32!lstrcmpW` at `0x180025aa4`
- `KERNEL32!lstrcmpW` at `0x180025aa4`

## pseudocode

```c
__int64 __fastcall DavRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v3; // ebx
  RPC_STATUS IsClientLocal; // eax
  RPC_WSTR Protseq; // [rsp+30h] [rbp-10h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+38h] [rbp-8h] BYREF
  unsigned int ClientLocalFlag; // [rsp+60h] [rbp+20h] BYREF
  RPC_WSTR StringBinding; // [rsp+68h] [rbp+28h] BYREF

  ServerBinding = 0;
  StringBinding = 0;
  Protseq = 0;
  ClientLocalFlag = 0;
  if ( RpcBindingServerFromClient(Context, &ServerBinding) )
    return 5;
  if ( RpcBindingToStringBindingW(ServerBinding, &StringBinding)
    || RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0)
    || lstrcmpW(Protseq, L"ncacn_np") )
  {
    v3 = 5;
  }
  else
  {
    IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
    v3 = 5;
    if ( !IsClientLocal )
    {
      if ( !ClientLocalFlag )
        IsClientLocal = 5;
      v3 = IsClientLocal;
    }
  }
  RpcBindingFree(&ServerBinding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  return v3;
}

```

## disassembly

```asm
0x180025a10  mov     [rsp-8+arg_0], rbx
0x180025a15  push    rbp
0x180025a16  mov     rbp, rsp
0x180025a19  sub     rsp, 40h
0x180025a1d  mov     rcx, rdx; ClientBinding
0x180025a20  mov     [rbp+ServerBinding], 0
0x180025a28  lea     rdx, [rbp+ServerBinding]; ServerBinding
0x180025a2c  mov     [rbp+StringBinding], 0
0x180025a34  mov     [rbp+Protseq], 0
0x180025a3c  mov     [rbp+ClientLocalFlag], 0
0x180025a43  call    cs:__imp_RpcBindingServerFromClient
0x180025a49  test    eax, eax
0x180025a4b  jz      short loc_180025A57
0x180025a4d  mov     eax, 5
0x180025a52  jmp     loc_180025AF9
0x180025a57  mov     rcx, [rbp+ServerBinding]; Binding
0x180025a5b  lea     rdx, [rbp+StringBinding]; StringBinding
0x180025a5f  call    cs:__imp_RpcBindingToStringBindingW
0x180025a65  test    eax, eax
0x180025a67  jz      short loc_180025A70
0x180025a69  mov     ebx, 5
0x180025a6e  jmp     short loc_180025ACB
0x180025a70  mov     rcx, [rbp+StringBinding]; StringBinding
0x180025a74  lea     r8, [rbp+Protseq]; Protseq
0x180025a78  mov     [rsp+40h+NetworkOptions], 0; NetworkOptions
0x180025a81  xor     r9d, r9d; NetworkAddr
0x180025a84  xor     edx, edx; ObjUuid
0x180025a86  mov     [rsp+40h+Endpoint], 0; Endpoint
0x180025a8f  call    cs:__imp_RpcStringBindingParseW
0x180025a95  test    eax, eax
0x180025a97  jnz     short loc_180025A69
0x180025a99  mov     rcx, [rbp+Protseq]; lpString1
0x180025a9d  lea     rdx, Protseq; "ncacn_np"
0x180025aa4  call    cs:__imp_lstrcmpW
0x180025aaa  test    eax, eax
0x180025aac  jnz     short loc_180025A69
0x180025aae  lea     rdx, [rbp+ClientLocalFlag]; ClientLocalFlag
0x180025ab2  xor     ecx, ecx; BindingHandle
0x180025ab4  call    cs:__imp_I_RpcBindingIsClientLocal
0x180025aba  mov     ebx, 5
0x180025abf  test    eax, eax
0x180025ac1  jnz     short loc_180025ACB
0x180025ac3  cmp     [rbp+ClientLocalFlag], eax
0x180025ac6  cmovz   eax, ebx
0x180025ac9  mov     ebx, eax
0x180025acb  lea     rcx, [rbp+ServerBinding]; Binding
0x180025acf  call    cs:__imp_RpcBindingFree
0x180025ad5  cmp     [rbp+StringBinding], 0
0x180025ada  jz      short loc_180025AE6
0x180025adc  lea     rcx, [rbp+StringBinding]; String
0x180025ae0  call    cs:__imp_RpcStringFreeW
0x180025ae6  cmp     [rbp+Protseq], 0
0x180025aeb  jz      short loc_180025AF7
0x180025aed  lea     rcx, [rbp+Protseq]; String
0x180025af1  call    cs:__imp_RpcStringFreeW
0x180025af7  mov     eax, ebx
0x180025af9  mov     rbx, [rsp+40h+arg_0]
0x180025afe  add     rsp, 40h
0x180025b02  pop     rbp
0x180025b03  retn
```
