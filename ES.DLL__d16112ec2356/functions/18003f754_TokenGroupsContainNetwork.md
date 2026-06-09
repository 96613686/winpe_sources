# TokenGroupsContainNetwork

- ea: `0x18003f754`
- end: `0x18003f8f7`
- name: `TokenGroupsContainNetwork`
- size: `419`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bf40`

## callees

- `0x180008fbc`
- `0x18003f754`
- `0x180043510`
- `0x1800435a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f8b1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003f89a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003f89a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f798`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f877`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f798`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f877`

## pseudocode

```c
signed int __fastcall TokenGroupsContainNetwork(HANDLE TokenHandle, _DWORD *a2)
{
  signed int result; // eax
  unsigned __int64 v5; // rdi
  DWORD *p_TokenInformationLength; // rbx
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  DWORD *v11; // rax
  unsigned int v12; // edi
  DWORD i; // esi
  signed int LastError; // eax
  __int64 v15; // [rsp+0h] [rbp-30h] BYREF
  DWORD TokenInformationLength; // [rsp+30h] [rbp+0h] BYREF
  __int64 v17; // [rsp+38h] [rbp+8h] BYREF

  *a2 = 0;
  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength);
  result = GetLastError();
  if ( result == 122 )
  {
    v5 = TokenInformationLength;
    p_TokenInformationLength = 0;
    if ( !TokenInformationLength
      || TokenInformationLength > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)TokenInformationLength + g_ulAdditionalProbeSize + 8 < TokenInformationLength
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_30;
    }
    v7 = v5 + 23;
    if ( v5 + 23 <= v5 + 8 )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
    v9 = alloca(v8);
    v10 = alloca(v8);
    p_TokenInformationLength = &TokenInformationLength;
    if ( &v15 == (__int64 *)-48LL
      || (TokenInformationLength = 1801679955, (p_TokenInformationLength = (DWORD *)&v17) == 0) )
    {
LABEL_30:
      if ( v5 + 8 >= v5 )
      {
        v11 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_TokenInformationLength = v11;
        if ( v11 )
        {
          *v11 = 1885431112;
          p_TokenInformationLength = v11 + 2;
        }
      }
    }
    if ( p_TokenInformationLength )
    {
      if ( GetTokenInformation(
             TokenHandle,
             TokenGroups,
             p_TokenInformationLength,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        v12 = 0;
        for ( i = 0; i < *p_TokenInformationLength; ++i )
        {
          if ( EqualSid(*(PSID *)&p_TokenInformationLength[4 * i + 2], pSid2) )
          {
            *a2 = 1;
            break;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( *(p_TokenInformationLength - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      return v12;
    }
    else
    {
      return -2147024882;
    }
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18003f754  push    rbp
0x18003f756  push    rbx
0x18003f757  push    rsi
0x18003f758  push    rdi
0x18003f759  push    r14
0x18003f75b  sub     rsp, 50h
0x18003f75f  lea     rbp, [rsp+30h]
0x18003f764  mov     rax, cs:__security_cookie
0x18003f76b  xor     rax, rbp
0x18003f76e  mov     [rbp+40h+var_30], rax
0x18003f772  xor     r9d, r9d; TokenInformationLength
0x18003f775  mov     dword ptr [rdx], 0
0x18003f77b  mov     r14, rdx
0x18003f77e  mov     [rbp+40h+TokenInformationLength], 0
0x18003f785  lea     rax, [rbp+40h+TokenInformationLength]
0x18003f789  xor     r8d, r8d; TokenInformation
0x18003f78c  mov     rsi, rcx
0x18003f78f  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003f794  lea     edx, [r9+2]; TokenInformationClass
0x18003f798  call    cs:__imp_GetTokenInformation
0x18003f79e  call    cs:__imp_GetLastError
0x18003f7a4  cmp     eax, 7Ah ; 'z'
0x18003f7a7  jz      short loc_18003F7BE
0x18003f7a9  test    eax, eax
0x18003f7ab  jle     loc_18003F8E0
0x18003f7b1  movzx   eax, ax
0x18003f7b4  or      eax, 80070000h
0x18003f7b9  jmp     loc_18003F8E0
0x18003f7be  mov     edi, [rbp+40h+TokenInformationLength]
0x18003f7c1  xor     ebx, ebx
0x18003f7c3  test    rdi, rdi
0x18003f7c6  jz      short loc_18003F829
0x18003f7c8  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18003f7cf  ja      short loc_18003F829
0x18003f7d1  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003f7d8  add     rcx, 8
0x18003f7dc  add     rcx, rdi
0x18003f7df  cmp     rcx, rdi
0x18003f7e2  jb      short loc_18003F829
0x18003f7e4  call    VerifyStackAvailable
0x18003f7e9  test    eax, eax
0x18003f7eb  jz      short loc_18003F829
0x18003f7ed  lea     rax, [rdi+8]
0x18003f7f1  lea     rcx, [rax+0Fh]
0x18003f7f5  cmp     rcx, rax
0x18003f7f8  ja      short loc_18003F804
0x18003f7fa  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18003f804  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003f808  mov     rax, rcx
0x18003f80b  call    _alloca_probe
0x18003f810  sub     rsp, rcx
0x18003f813  lea     rbx, [rsp+70h+TokenInformationLength]
0x18003f818  test    rbx, rbx
0x18003f81b  jz      short loc_18003F829
0x18003f81d  mov     dword ptr [rbx], 6B637453h
0x18003f823  add     rbx, 8
0x18003f827  jnz     short loc_18003F850
0x18003f829  lea     rcx, [rdi+8]
0x18003f82d  cmp     rcx, rdi
0x18003f830  jb      short loc_18003F850
0x18003f832  mov     rax, cs:g_pfnAllocate
0x18003f839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f83e  mov     rbx, rax
0x18003f841  test    rax, rax
0x18003f844  jz      short loc_18003F850
0x18003f846  mov     dword ptr [rax], 70616548h
0x18003f84c  add     rbx, 8
0x18003f850  test    rbx, rbx
0x18003f853  jnz     short loc_18003F85F
0x18003f855  mov     eax, 8007000Eh
0x18003f85a  jmp     loc_18003F8E0
0x18003f85f  mov     r9d, [rbp+40h+TokenInformationLength]; TokenInformationLength
0x18003f863  lea     rax, [rbp+40h+TokenInformationLength]
0x18003f867  mov     r8, rbx; TokenInformation
0x18003f86a  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003f86f  mov     edx, 2; TokenInformationClass
0x18003f874  mov     rcx, rsi; TokenHandle
0x18003f877  call    cs:__imp_GetTokenInformation
0x18003f87d  test    eax, eax
0x18003f87f  jz      short loc_18003F8B1
0x18003f881  xor     edi, edi
0x18003f883  xor     esi, esi
0x18003f885  cmp     esi, [rbx]
0x18003f887  jnb     short loc_18003F8C6
0x18003f889  mov     rdx, cs:pSid2; pSid2
0x18003f890  mov     ecx, esi
0x18003f892  add     rcx, rcx
0x18003f895  mov     rcx, [rbx+rcx*8+8]; pSid1
0x18003f89a  call    cs:__imp_EqualSid
0x18003f8a0  test    eax, eax
0x18003f8a2  jnz     short loc_18003F8A8
0x18003f8a4  inc     esi
0x18003f8a6  jmp     short loc_18003F885
0x18003f8a8  mov     dword ptr [r14], 1
0x18003f8af  jmp     short loc_18003F8C6
0x18003f8b1  call    cs:__imp_GetLastError
0x18003f8b7  mov     edi, eax
0x18003f8b9  test    eax, eax
0x18003f8bb  jle     short loc_18003F8C6
0x18003f8bd  movzx   edi, ax
0x18003f8c0  or      edi, 80070000h
0x18003f8c6  lea     rcx, [rbx-8]
0x18003f8ca  cmp     dword ptr [rcx], 70616548h
0x18003f8d0  jnz     short loc_18003F8DE
0x18003f8d2  mov     rax, cs:g_pfnFree
0x18003f8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8de  mov     eax, edi
0x18003f8e0  mov     rcx, [rbp+40h+var_30]
0x18003f8e4  xor     rcx, rbp; StackCookie
0x18003f8e7  call    __security_check_cookie
0x18003f8ec  lea     rsp, [rbp+20h]
0x18003f8f0  pop     r14
0x18003f8f2  pop     rdi
0x18003f8f3  pop     rsi
0x18003f8f4  pop     rbx
0x18003f8f5  pop     rbp
0x18003f8f6  retn
```
