# SrpSetEnterpriseContextToken

- ea: `0x180017bcc`
- end: `0x180017c80`
- name: `SrpSetEnterpriseContextToken`
- size: `180`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017c88`

## callees

- `0x1800174ec`
- `0x180017784`
- `0x180017bcc`

## import_xrefs

- `ntdll!NtSetInformationToken` at `0x180017c2b`
- `ntdll!NtSetInformationToken` at `0x180017c2b`

## pseudocode

```c
__int64 __fastcall SrpSetEnterpriseContextToken(HANDLE TokenHandle, int a2, int a3, int a4)
{
  int AttributesFromContext; // eax
  __int64 v6; // rbx
  unsigned int v7; // ebp
  __int64 i; // rsi
  __int128 TokenInformation; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+80h] [rbp+18h] BYREF

  v11 = 0;
  TokenInformation = 0;
  AttributesFromContext = CreateAttributesFromContext(a2, a2, a3, a4, (__int64)&v11);
  v6 = v11;
  v7 = AttributesFromContext;
  if ( AttributesFromContext >= 0 )
  {
    *(_QWORD *)&TokenInformation = v11;
    *((_QWORD *)&TokenInformation + 1) = SrpReplaceOperations;
    v7 = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
  }
  if ( v6 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v6 + 4); i = (unsigned int)(i + 1) )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v6 + 8) + 40 * i + 32) )
        ((void (*)(void))EnterpriseContextLibMemFree)();
    }
    EnterpriseContextLibMemFree(*(_QWORD *)(v6 + 8));
    EnterpriseContextLibMemFree(v6);
  }
  return v7;
}

```

## disassembly

```asm
0x180017bcc  mov     rax, rsp
0x180017bcf  push    rbx
0x180017bd0  push    rbp
0x180017bd1  push    rsi
0x180017bd2  push    rdi
0x180017bd3  sub     rsp, 48h
0x180017bd7  xorps   xmm0, xmm0
0x180017bda  mov     qword ptr [rax+18h], 0
0x180017be2  movups  xmmword ptr [rax-38h], xmm0
0x180017be6  lea     rax, [rax+18h]
0x180017bea  mov     rdi, rcx
0x180017bed  mov     rcx, rdx
0x180017bf0  mov     [rsp+68h+var_48], rax
0x180017bf5  call    CreateAttributesFromContext
0x180017bfa  mov     rbx, [rsp+68h+arg_10]
0x180017c02  mov     ebp, eax
0x180017c04  test    eax, eax
0x180017c06  js      short loc_180017C39
0x180017c08  mov     r9d, 10h; TokenInformationLength
0x180017c0e  mov     [rsp+68h+TokenInformation], rbx
0x180017c13  lea     rax, SrpReplaceOperations
0x180017c1a  mov     rcx, rdi; TokenHandle
0x180017c1d  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x180017c22  mov     [rsp+68h+var_30], rax
0x180017c27  lea     edx, [r9+17h]; TokenInformationClass
0x180017c2b  call    cs:__imp_NtSetInformationToken
0x180017c32  nop     dword ptr [rax+rax+00h]
0x180017c37  mov     ebp, eax
0x180017c39  test    rbx, rbx
0x180017c3c  jz      short loc_180017C74
0x180017c3e  xor     esi, esi
0x180017c40  cmp     [rbx+4], esi
0x180017c43  jbe     short loc_180017C63
0x180017c45  mov     rax, [rbx+8]
0x180017c49  lea     rcx, [rsi+rsi*4]
0x180017c4d  mov     rcx, [rax+rcx*8+20h]
0x180017c52  test    rcx, rcx
0x180017c55  jz      short loc_180017C5C
0x180017c57  call    EnterpriseContextLibMemFree
0x180017c5c  inc     esi
0x180017c5e  cmp     esi, [rbx+4]
0x180017c61  jb      short loc_180017C45
0x180017c63  mov     rcx, [rbx+8]
0x180017c67  call    EnterpriseContextLibMemFree
0x180017c6c  mov     rcx, rbx
0x180017c6f  call    EnterpriseContextLibMemFree
0x180017c74  mov     eax, ebp
0x180017c76  add     rsp, 48h
0x180017c7a  pop     rdi
0x180017c7b  pop     rsi
0x180017c7c  pop     rbp
0x180017c7d  pop     rbx
0x180017c7e  retn
```
