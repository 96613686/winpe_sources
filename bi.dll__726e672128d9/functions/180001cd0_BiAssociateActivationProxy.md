# BiAssociateActivationProxy

- ea: `0x180001cd0`
- end: `0x180001dc8`
- name: `BiAssociateActivationProxy`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001cd0`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180001d86`
- `RPCRT4!NdrClientCall3` at `0x180001d86`
- `RPCRT4!RpcBindingFree` at `0x180001db0`
- `RPCRT4!RpcBindingFree` at `0x180001db0`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001d9f`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001d9f`

## pseudocode

```c
__int64 __fastcall BiAssociateActivationProxy(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        unsigned __int16 *a7)
{
  int RpcBinding; // ebx
  __int64 v12; // rsi
  int v13; // edi
  RPC_BINDING_HANDLE Binding[8]; // [rsp+68h] [rbp-40h] BYREF

  Binding[0] = 0;
  if ( a7 )
  {
    if ( (*(_BYTE *)a7 & 1) != 0 )
      return (unsigned int)-1073741811;
    v12 = *((_QWORD *)a7 + 1);
    v13 = *a7 >> 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
  }
  RpcBinding = BipCreateRpcBinding(Binding);
  if ( RpcBinding >= 0 )
  {
    RpcBinding = (unsigned int)NdrClientCall3(
                                 (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                 3u,
                                 0,
                                 Binding[0],
                                 a1,
                                 a2,
                                 a3,
                                 a4,
                                 a5,
                                 a6,
                                 v12,
                                 v13).Pointer;
    RpcBindingFree(Binding);
  }
  return (unsigned int)RpcBinding;
}

```

## disassembly

```asm
0x180001cd0  push    rbx
0x180001cd2  push    rsi
0x180001cd3  push    rdi
0x180001cd4  push    r12
0x180001cd6  push    r13
0x180001cd8  push    r14
0x180001cda  push    r15
0x180001cdc  sub     rsp, 70h
0x180001ce0  mov     r14, r9
0x180001ce3  mov     r15, r8
0x180001ce6  mov     r12, rdx
0x180001ce9  mov     r13, rcx
0x180001cec  mov     [rsp+0A8h+Binding], 0
0x180001cf5  mov     rax, [rsp+0A8h+arg_30]
0x180001cfd  test    rax, rax
0x180001d00  jz      short loc_180001D1C
0x180001d02  test    byte ptr [rax], 1
0x180001d05  jz      short loc_180001D11
0x180001d07  mov     ebx, 0C000000Dh
0x180001d0c  jmp     loc_180001DB6
0x180001d11  mov     rsi, [rax+8]
0x180001d15  movzx   edi, word ptr [rax]
0x180001d18  shr     edi, 1
0x180001d1a  jmp     short loc_180001D20
0x180001d1c  xor     esi, esi
0x180001d1e  xor     edi, edi
0x180001d20  lea     rcx, [rsp+0A8h+Binding]
0x180001d25  call    BipCreateRpcBinding
0x180001d2a  mov     ebx, eax
0x180001d2c  test    eax, eax
0x180001d2e  js      loc_180001DB6
0x180001d34  mov     [rsp+0A8h+arg_30], 0
0x180001d40  mov     [rsp+0A8h+var_50], edi
0x180001d44  mov     [rsp+0A8h+var_58], rsi
0x180001d49  mov     eax, [rsp+0A8h+arg_28]
0x180001d50  mov     [rsp+0A8h+var_60], eax
0x180001d54  mov     eax, [rsp+0A8h+arg_20]
0x180001d5b  mov     [rsp+0A8h+var_68], eax
0x180001d5f  mov     [rsp+0A8h+var_70], r14
0x180001d64  mov     [rsp+0A8h+var_78], r15
0x180001d69  mov     [rsp+0A8h+var_80], r12
0x180001d6e  mov     [rsp+0A8h+var_88], r13
0x180001d73  mov     r9, [rsp+0A8h+Binding]
0x180001d78  xor     r8d, r8d; pReturnValue
0x180001d7b  lea     edx, [r8+3]; nProcNum
0x180001d7f  lea     rcx, pProxyInfo; pProxyInfo
0x180001d86  call    cs:__imp_NdrClientCall3
0x180001d8c  mov     rbx, rax
0x180001d8f  mov     [rsp+0A8h+arg_30], rax
0x180001d97  mov     [rsp+0A8h+var_48], eax
0x180001d9b  jmp     short loc_180001DAB
0x180001d9d  mov     ecx, eax; Status
0x180001d9f  call    cs:__imp_I_RpcMapWin32Status
0x180001da5  mov     ebx, eax
0x180001da7  mov     [rsp+0A8h+var_48], eax
0x180001dab  lea     rcx, [rsp+0A8h+Binding]; Binding
0x180001db0  call    cs:__imp_RpcBindingFree
0x180001db6  mov     eax, ebx
0x180001db8  add     rsp, 70h
0x180001dbc  pop     r15
0x180001dbe  pop     r14
0x180001dc0  pop     r13
0x180001dc2  pop     r12
0x180001dc4  pop     rdi
0x180001dc5  pop     rsi
0x180001dc6  pop     rbx
0x180001dc7  retn
0x180003860  push    rbp
0x180003862  sub     rsp, 60h
0x180003866  mov     rbp, rdx
0x180003869  mov     rcx, [rcx]
0x18000386c  mov     ecx, [rcx]; ExceptionCode
0x18000386e  call    cs:__imp_RpcExceptionFilter
0x180003874  nop
0x180003875  add     rsp, 60h
0x180003879  pop     rbp
0x18000387a  retn
```
