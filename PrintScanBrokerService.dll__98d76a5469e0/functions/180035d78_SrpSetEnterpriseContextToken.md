# SrpSetEnterpriseContextToken

- ea: `0x180035d78`
- end: `0x180035e25`
- name: `SrpSetEnterpriseContextToken`
- size: `173`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035e2c`

## callees

- `0x180035a68`
- `0x180035ce4`
- `0x180035d78`

## import_xrefs

- `ntdll!NtSetInformationToken` at `0x180035dd7`
- `ntdll!NtSetInformationToken` at `0x180035dd7`

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
0x180035d78  mov     rax, rsp
0x180035d7b  push    rbx
0x180035d7c  push    rbp
0x180035d7d  push    rsi
0x180035d7e  push    rdi
0x180035d7f  sub     rsp, 48h
0x180035d83  xorps   xmm0, xmm0
0x180035d86  mov     qword ptr [rax+18h], 0
0x180035d8e  movups  xmmword ptr [rax-38h], xmm0
0x180035d92  lea     rax, [rax+18h]
0x180035d96  mov     rdi, rcx
0x180035d99  mov     rcx, rdx
0x180035d9c  mov     [rsp+68h+var_48], rax
0x180035da1  call    CreateAttributesFromContext
0x180035da6  mov     rbx, [rsp+68h+arg_10]
0x180035dae  mov     ebp, eax
0x180035db0  test    eax, eax
0x180035db2  js      short loc_180035DDF
0x180035db4  mov     r9d, 10h; TokenInformationLength
0x180035dba  mov     [rsp+68h+TokenInformation], rbx
0x180035dbf  lea     rax, SrpReplaceOperations
0x180035dc6  mov     rcx, rdi; TokenHandle
0x180035dc9  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x180035dce  mov     [rsp+68h+var_30], rax
0x180035dd3  lea     edx, [r9+17h]; TokenInformationClass
0x180035dd7  call    cs:__imp_NtSetInformationToken
0x180035ddd  mov     ebp, eax
0x180035ddf  test    rbx, rbx
0x180035de2  jz      short loc_180035E1A
0x180035de4  xor     esi, esi
0x180035de6  cmp     [rbx+4], esi
0x180035de9  jbe     short loc_180035E09
0x180035deb  mov     rax, [rbx+8]
0x180035def  lea     rcx, [rsi+rsi*4]
0x180035df3  mov     rcx, [rax+rcx*8+20h]
0x180035df8  test    rcx, rcx
0x180035dfb  jz      short loc_180035E02
0x180035dfd  call    EnterpriseContextLibMemFree
0x180035e02  inc     esi
0x180035e04  cmp     esi, [rbx+4]
0x180035e07  jb      short loc_180035DEB
0x180035e09  mov     rcx, [rbx+8]
0x180035e0d  call    EnterpriseContextLibMemFree
0x180035e12  mov     rcx, rbx
0x180035e15  call    EnterpriseContextLibMemFree
0x180035e1a  mov     eax, ebp
0x180035e1c  add     rsp, 48h
0x180035e20  pop     rdi
0x180035e21  pop     rsi
0x180035e22  pop     rbp
0x180035e23  pop     rbx
0x180035e24  retn
```
