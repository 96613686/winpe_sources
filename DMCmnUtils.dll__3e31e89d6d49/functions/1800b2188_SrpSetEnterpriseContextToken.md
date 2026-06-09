# SrpSetEnterpriseContextToken

- ea: `0x1800b2188`
- end: `0x1800b223c`
- name: `SrpSetEnterpriseContextToken`
- size: `180`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b2244`

## callees

- `0x1800b1aa8`
- `0x1800b1d40`
- `0x1800b2188`

## import_xrefs

- `ntdll!NtSetInformationToken` at `0x1800b21e7`
- `ntdll!NtSetInformationToken` at `0x1800b21e7`

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
0x1800b2188  mov     rax, rsp
0x1800b218b  push    rbx
0x1800b218c  push    rbp
0x1800b218d  push    rsi
0x1800b218e  push    rdi
0x1800b218f  sub     rsp, 48h
0x1800b2193  xorps   xmm0, xmm0
0x1800b2196  mov     qword ptr [rax+18h], 0
0x1800b219e  movups  xmmword ptr [rax-38h], xmm0
0x1800b21a2  lea     rax, [rax+18h]
0x1800b21a6  mov     rdi, rcx
0x1800b21a9  mov     rcx, rdx
0x1800b21ac  mov     [rsp+68h+var_48], rax
0x1800b21b1  call    CreateAttributesFromContext
0x1800b21b6  mov     rbx, [rsp+68h+arg_10]
0x1800b21be  mov     ebp, eax
0x1800b21c0  test    eax, eax
0x1800b21c2  js      short loc_1800B21F5
0x1800b21c4  mov     r9d, 10h; TokenInformationLength
0x1800b21ca  mov     [rsp+68h+TokenInformation], rbx
0x1800b21cf  lea     rax, SrpReplaceOperations
0x1800b21d6  mov     rcx, rdi; TokenHandle
0x1800b21d9  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x1800b21de  mov     [rsp+68h+var_30], rax
0x1800b21e3  lea     edx, [r9+17h]; TokenInformationClass
0x1800b21e7  call    cs:__imp_NtSetInformationToken
0x1800b21ee  nop     dword ptr [rax+rax+00h]
0x1800b21f3  mov     ebp, eax
0x1800b21f5  test    rbx, rbx
0x1800b21f8  jz      short loc_1800B2230
0x1800b21fa  xor     esi, esi
0x1800b21fc  cmp     [rbx+4], esi
0x1800b21ff  jbe     short loc_1800B221F
0x1800b2201  mov     rax, [rbx+8]
0x1800b2205  lea     rcx, [rsi+rsi*4]
0x1800b2209  mov     rcx, [rax+rcx*8+20h]
0x1800b220e  test    rcx, rcx
0x1800b2211  jz      short loc_1800B2218
0x1800b2213  call    EnterpriseContextLibMemFree
0x1800b2218  inc     esi
0x1800b221a  cmp     esi, [rbx+4]
0x1800b221d  jb      short loc_1800B2201
0x1800b221f  mov     rcx, [rbx+8]
0x1800b2223  call    EnterpriseContextLibMemFree
0x1800b2228  mov     rcx, rbx
0x1800b222b  call    EnterpriseContextLibMemFree
0x1800b2230  mov     eax, ebp
0x1800b2232  add     rsp, 48h
0x1800b2236  pop     rdi
0x1800b2237  pop     rsi
0x1800b2238  pop     rbp
0x1800b2239  pop     rbx
0x1800b223a  retn
```
