# LsaCreateConnectedUser

- ea: `0x180018ca0`
- end: `0x180018dc2`
- name: `LsaCreateConnectedUser`
- size: `290`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015d10`

## callees

- `0x180018ca0`
- `0x180018ecc`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180018d9d`
- `RPCRT4!RpcBindingFree` at `0x180018d9d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180018d89`
- `RPCRT4!I_RpcMapWin32Status` at `0x180018d89`
- `RPCRT4!NdrClientCall3` at `0x180018d73`
- `RPCRT4!NdrClientCall3` at `0x180018d73`

## pseudocode

```c
__int64 __fastcall LsaCreateConnectedUser(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5, int a6)
{
  int v10; // ebx
  __int64 result; // rax
  unsigned int Pointer; // ebx
  int v13; // [rsp+30h] [rbp-48h]
  int v14; // [rsp+40h] [rbp-38h]
  RPC_BINDING_HANDLE Binding; // [rsp+80h] [rbp+8h] BYREF

  Binding = 0;
  if ( !a1 || !a2 || !a4 )
    return 3221225485LL;
  v10 = a6;
  if ( !a6 )
  {
    if ( !a5 )
      goto LABEL_8;
    return 3221225485LL;
  }
  if ( !a5 )
    return 3221225485LL;
LABEL_8:
  result = LsapCreateBindingHandleForLocal(L"LSA_IDPEXT_ENDPOINT", qword_18001D5F0, &Binding);
  if ( (int)result >= 0 )
  {
    v14 = v10;
    v13 = a3;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              2u,
                              0,
                              Binding,
                              a1,
                              a2,
                              v13,
                              a4,
                              v14,
                              a5).Pointer;
    RpcBindingFree(&Binding);
    return Pointer;
  }
  return result;
}

```

## disassembly

```asm
0x180018ca0  mov     rax, rsp
0x180018ca3  mov     [rax+10h], rbx
0x180018ca7  mov     [rax+18h], rsi
0x180018cab  push    rdi
0x180018cac  push    r14
0x180018cae  push    r15
0x180018cb0  sub     rsp, 60h
0x180018cb4  mov     rdi, r9
0x180018cb7  mov     r15d, r8d
0x180018cba  mov     rsi, rdx
0x180018cbd  mov     r14, rcx
0x180018cc0  mov     qword ptr [rax+8], 0
0x180018cc8  test    rcx, rcx
0x180018ccb  jz      loc_180018DA7
0x180018cd1  test    rdx, rdx
0x180018cd4  jz      loc_180018DA7
0x180018cda  test    r9, r9
0x180018cdd  jz      loc_180018DA7
0x180018ce3  mov     ebx, [rsp+78h+arg_28]
0x180018cea  test    ebx, ebx
0x180018cec  jz      short loc_180018D01
0x180018cee  cmp     [rsp+78h+arg_20], 0
0x180018cf7  jz      loc_180018DA7
0x180018cfd  test    ebx, ebx
0x180018cff  jnz     short loc_180018D10
0x180018d01  cmp     [rsp+78h+arg_20], 0
0x180018d0a  jnz     loc_180018DA7
0x180018d10  lea     r8, [rsp+78h+Binding]
0x180018d18  lea     rdx, qword_18001D5F0
0x180018d1f  lea     rcx, aLsaIdpextEndpo; "LSA_IDPEXT_ENDPOINT"
0x180018d26  call    LsapCreateBindingHandleForLocal
0x180018d2b  test    eax, eax
0x180018d2d  js      short loc_180018DAC
0x180018d2f  mov     [rsp+78h+var_20], 0
0x180018d38  mov     rax, [rsp+78h+arg_20]
0x180018d40  mov     [rsp+78h+var_30], rax
0x180018d45  mov     [rsp+78h+var_38], ebx
0x180018d49  mov     [rsp+78h+var_40], rdi
0x180018d4e  mov     [rsp+78h+var_48], r15d
0x180018d53  mov     [rsp+78h+var_50], rsi
0x180018d58  mov     [rsp+78h+var_58], r14
0x180018d5d  mov     r9, [rsp+78h+Binding]
0x180018d65  xor     r8d, r8d; pReturnValue
0x180018d68  lea     edx, [r8+2]; nProcNum
0x180018d6c  lea     rcx, pProxyInfo; pProxyInfo
0x180018d73  call    cs:__imp_NdrClientCall3
0x180018d79  mov     rbx, rax
0x180018d7c  mov     [rsp+78h+var_20], rax
0x180018d81  mov     [rsp+78h+var_28], eax
0x180018d85  jmp     short loc_180018D95
0x180018d87  mov     ecx, eax; Status
0x180018d89  call    cs:__imp_I_RpcMapWin32Status
0x180018d8f  mov     ebx, eax
0x180018d91  mov     [rsp+78h+var_28], eax
0x180018d95  lea     rcx, [rsp+78h+Binding]; Binding
0x180018d9d  call    cs:__imp_RpcBindingFree
0x180018da3  mov     eax, ebx
0x180018da5  jmp     short loc_180018DAC
0x180018da7  mov     eax, 0C000000Dh
0x180018dac  lea     r11, [rsp+78h+var_18]
0x180018db1  mov     rbx, [r11+28h]
0x180018db5  mov     rsi, [r11+30h]
0x180018db9  mov     rsp, r11
0x180018dbc  pop     r15
0x180018dbe  pop     r14
0x180018dc0  pop     rdi
0x180018dc1  retn
0x18001a0a0  push    rbp
0x18001a0a2  sub     rsp, 50h
0x18001a0a6  mov     rbp, rdx
0x18001a0a9  mov     rcx, [rcx]
0x18001a0ac  mov     ecx, [rcx]; ExceptionCode
0x18001a0ae  call    cs:__imp_I_RpcExceptionFilter
0x18001a0b4  nop
0x18001a0b5  add     rsp, 50h
0x18001a0b9  pop     rbp
0x18001a0ba  retn
0x18001a0bc  push    rbp
0x18001a0be  sub     rsp, 50h
0x18001a0c2  mov     rbp, rdx
0x18001a0c5  lea     rcx, [rbp+80h]; Binding
0x18001a0cc  call    cs:__imp_RpcBindingFree
0x18001a0d2  nop
0x18001a0d3  add     rsp, 50h
0x18001a0d7  pop     rbp
0x18001a0d8  retn
```
