# __crtCompareStringA

- ea: `0x1800da4b8`
- end: `0x1800da855`
- name: `__crtCompareStringA`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800d8b38`

## callees

- `0x1800049e0`
- `0x180005c6e`
- `0x180005cc2`
- `0x1800da4b8`
- `0x1800efc00`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da60e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da6b4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da6e4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da78f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da60e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da6b4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da6e4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800da78f`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800da7e7`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800da7e7`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x1800da574`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x1800da574`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x1800da4ff`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x1800da524`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x1800da4ff`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x1800da524`

## pseudocode

```c
__int64 __fastcall _crtCompareStringA(
        const WCHAR *a1,
        __int64 a2,
        const char *a3,
        int a4,
        char *String,
        int a6,
        UINT CodePage)
{
  int v7; // edi
  int v9; // esi
  BYTE *i; // rax
  BYTE *j; // rax
  int v12; // eax
  int cchWideChar; // r13d
  size_t v14; // rcx
  __int64 v15; // rax
  void *v16; // rsp
  WCHAR *lpWideCharStr; // rbx
  WCHAR *v18; // rax
  int v19; // eax
  int v20; // r15d
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  __int64 v23; // rax
  void *v24; // rsp
  WCHAR *p_lpMultiByteStr; // rdi
  WCHAR *v26; // rax
  WCHAR *v27; // r14
  WCHAR *v28; // rcx
  bool v29; // zf
  unsigned int v30; // edi
  _BYTE v32[32]; // [rsp+0h] [rbp-50h] BYREF
  LPCCH lpMultiByteStr; // [rsp+50h] [rbp+0h] BYREF
  LPCWSTR lpLocaleName; // [rsp+58h] [rbp+8h]
  _cpinfo CPInfo; // [rsp+60h] [rbp+10h] BYREF

  v7 = a4;
  lpLocaleName = a1;
  lpMultiByteStr = String;
  if ( a4 <= 0 )
  {
    if ( a4 < -1 )
      return 0;
  }
  else
  {
    v7 = __strncnt(a3, a4);
  }
  v9 = a6;
  if ( a6 <= 0 )
  {
    if ( a6 < -1 )
      return 0;
  }
  else
  {
    v9 = __strncnt(String, a6);
  }
  if ( v7 && v9 )
    goto LABEL_29;
  if ( v7 == v9 )
    return 2;
  if ( v9 > 1 )
    return 1;
  if ( v7 > 1 )
    return 3;
  memset(&CPInfo, 0, sizeof(CPInfo));
  if ( !GetCPInfo(CodePage, &CPInfo) )
    return 0;
  if ( v7 > 0 )
  {
    if ( CPInfo.MaxCharSize >= 2 )
    {
      for ( i = CPInfo.LeadByte; *i && i[1]; i += 2 )
      {
        if ( (unsigned int)*a3 >= *i && (unsigned int)*a3 <= i[1] )
          return 2;
      }
    }
    return 3;
  }
  if ( v9 > 0 )
  {
    if ( CPInfo.MaxCharSize >= 2 )
    {
      for ( j = CPInfo.LeadByte; *j && j[1]; j += 2 )
      {
        if ( (unsigned __int8)*String >= *j && (unsigned __int8)*String <= j[1] )
          return 2;
      }
    }
    return 1;
  }
LABEL_29:
  v12 = MultiByteToWideChar(CodePage, 9u, a3, v7, 0, 0);
  cchWideChar = v12;
  if ( !v12 )
    return 0;
  v14 = (2LL * v12 + 16) & -(__int64)(2LL * v12 < (unsigned __int64)(2LL * v12 + 16));
  if ( !v14 )
    return 0;
  if ( v14 > 0x400 )
  {
    v18 = (WCHAR *)malloc_base(v14);
    lpWideCharStr = v18;
    if ( !v18 )
      goto LABEL_39;
    *(_DWORD *)v18 = 56797;
  }
  else
  {
    v15 = v14 + 15;
    if ( v14 + 15 < v14 )
      v15 = 0xFFFFFFFFFFFFFF0LL;
    v16 = alloca(v15 & 0xFFFFFFFFFFFFFFF0uLL);
    lpWideCharStr = (WCHAR *)&lpMultiByteStr;
    if ( v32 == (_BYTE *)-80LL )
      return 0;
    LODWORD(lpMultiByteStr) = 52428;
  }
  lpWideCharStr += 8;
LABEL_39:
  if ( !lpWideCharStr )
    return 0;
  if ( !MultiByteToWideChar(CodePage, 1u, a3, v7, lpWideCharStr, cchWideChar) )
    goto LABEL_61;
  v19 = MultiByteToWideChar(CodePage, 9u, String, v9, 0, 0);
  v20 = v19;
  if ( !v19 )
    goto LABEL_61;
  v21 = 2LL * v19 + 16;
  v22 = v21 & -(__int64)(2LL * v19 < v21);
  if ( !v22 )
    goto LABEL_61;
  if ( v22 > 0x400 )
  {
    v26 = (WCHAR *)malloc_base(v21 & -(__int64)(2LL * v19 < v21));
    p_lpMultiByteStr = v26;
    if ( !v26 )
      goto LABEL_51;
    *(_DWORD *)v26 = 56797;
  }
  else
  {
    v23 = v22 + 15;
    if ( v22 + 15 < v22 )
      v23 = 0xFFFFFFFFFFFFFF0LL;
    v24 = alloca(v23 & 0xFFFFFFFFFFFFFFF0uLL);
    p_lpMultiByteStr = (WCHAR *)&lpMultiByteStr;
    if ( v32 == (_BYTE *)-80LL )
      goto LABEL_61;
    LODWORD(lpMultiByteStr) = 52428;
  }
  p_lpMultiByteStr += 8;
LABEL_51:
  if ( !p_lpMultiByteStr )
  {
LABEL_61:
    v28 = lpWideCharStr - 8;
    v29 = *((_DWORD *)lpWideCharStr - 4) == 56797;
LABEL_62:
    if ( v29 )
      free_base(v28);
    return 0;
  }
  v27 = p_lpMultiByteStr - 8;
  if ( !MultiByteToWideChar(CodePage, 1u, lpMultiByteStr, v9, p_lpMultiByteStr, v20) )
  {
    if ( *(_DWORD *)v27 == 56797 )
      free_base(v27);
    v28 = lpWideCharStr - 8;
    v29 = *((_DWORD *)lpWideCharStr - 4) == 56797;
    goto LABEL_62;
  }
  v30 = CompareStringEx(lpLocaleName, 0x1000u, lpWideCharStr, cchWideChar, p_lpMultiByteStr, v20, 0, 0, 0);
  if ( *(_DWORD *)v27 == 56797 )
    free_base(v27);
  if ( *((_DWORD *)lpWideCharStr - 4) == 56797 )
    free_base(lpWideCharStr - 8);
  return v30;
}

```

## disassembly

```asm
0x1800da4b8  push    rbp
0x1800da4ba  push    rbx
0x1800da4bb  push    rsi
0x1800da4bc  push    rdi
0x1800da4bd  push    r13
0x1800da4bf  push    r14
0x1800da4c1  push    r15
0x1800da4c3  sub     rsp, 80h
0x1800da4ca  lea     rbp, [rsp+50h]
0x1800da4cf  mov     rax, cs:__security_cookie
0x1800da4d6  xor     rax, rbp
0x1800da4d9  mov     [rbp+60h+var_38], rax
0x1800da4dd  mov     r15, [rbp+60h+String]
0x1800da4e4  xor     ebx, ebx
0x1800da4e6  movsxd  rdi, r9d
0x1800da4e9  mov     r14, r8
0x1800da4ec  mov     [rbp+60h+lpLocaleName], rcx
0x1800da4f0  mov     [rbp+60h+lpMultiByteStr], r15
0x1800da4f4  test    r9d, r9d
0x1800da4f7  jle     short loc_1800DA50A
0x1800da4f9  mov     rdx, rdi; Count
0x1800da4fc  mov     rcx, r8; String
0x1800da4ff  call    cs:__imp___strncnt
0x1800da505  mov     rdi, rax
0x1800da508  jmp     short loc_1800DA513
0x1800da50a  cmp     edi, 0FFFFFFFFh
0x1800da50d  jl      loc_1800DA823
0x1800da513  movsxd  rsi, [rbp+60h+arg_28]
0x1800da51a  test    esi, esi
0x1800da51c  jle     short loc_1800DA52F
0x1800da51e  mov     rdx, rsi; Count
0x1800da521  mov     rcx, r15; String
0x1800da524  call    cs:__imp___strncnt
0x1800da52a  mov     rsi, rax
0x1800da52d  jmp     short loc_1800DA538
0x1800da52f  cmp     esi, 0FFFFFFFFh
0x1800da532  jl      loc_1800DA823
0x1800da538  test    edi, edi
0x1800da53a  jz      short loc_1800DA544
0x1800da53c  test    esi, esi
0x1800da53e  jnz     loc_1800DA5F4
0x1800da544  cmp     edi, esi
0x1800da546  jz      loc_1800DA84E
0x1800da54c  cmp     esi, 1
0x1800da54f  jg      loc_1800DA847
0x1800da555  cmp     edi, 1
0x1800da558  jg      loc_1800DA840
0x1800da55e  mov     ecx, [rbp+60h+CodePage]; CodePage
0x1800da564  lea     rdx, [rbp+60h+CPInfo]; lpCPInfo
0x1800da568  xorps   xmm0, xmm0
0x1800da56b  xor     eax, eax
0x1800da56d  movups  xmmword ptr [rbp+60h+CPInfo.MaxCharSize], xmm0
0x1800da571  mov     dword ptr [rbp+60h+CPInfo.LeadByte+0Ah], eax
0x1800da574  call    cs:__imp_GetCPInfo
0x1800da57a  test    eax, eax
0x1800da57c  jz      loc_1800DA823
0x1800da582  test    edi, edi
0x1800da584  jle     short loc_1800DA5BB
0x1800da586  cmp     [rbp+60h+CPInfo.MaxCharSize], 2
0x1800da58a  jb      loc_1800DA840
0x1800da590  lea     rax, [rbp+60h+CPInfo.LeadByte]
0x1800da594  cmp     [rax], bl
0x1800da596  jz      loc_1800DA840
0x1800da59c  cmp     [rax+1], bl
0x1800da59f  jz      loc_1800DA840
0x1800da5a5  mov     cl, [r14]
0x1800da5a8  cmp     cl, [rax]
0x1800da5aa  jb      short loc_1800DA5B5
0x1800da5ac  cmp     cl, [rax+1]
0x1800da5af  jbe     loc_1800DA84E
0x1800da5b5  add     rax, 2
0x1800da5b9  jmp     short loc_1800DA594
0x1800da5bb  test    esi, esi
0x1800da5bd  jle     short loc_1800DA5F4
0x1800da5bf  cmp     [rbp+60h+CPInfo.MaxCharSize], 2
0x1800da5c3  jb      loc_1800DA847
0x1800da5c9  lea     rax, [rbp+60h+CPInfo.LeadByte]
0x1800da5cd  cmp     [rax], bl
0x1800da5cf  jz      loc_1800DA847
0x1800da5d5  cmp     [rax+1], bl
0x1800da5d8  jz      loc_1800DA847
0x1800da5de  mov     cl, [r15]
0x1800da5e1  cmp     cl, [rax]
0x1800da5e3  jb      short loc_1800DA5EE
0x1800da5e5  cmp     cl, [rax+1]
0x1800da5e8  jbe     loc_1800DA84E
0x1800da5ee  add     rax, 2
0x1800da5f2  jmp     short loc_1800DA5CD
0x1800da5f4  mov     ecx, [rbp+60h+CodePage]; CodePage
0x1800da5fa  mov     r9d, edi; cbMultiByte
0x1800da5fd  mov     [rsp+0B0h+cchWideChar], ebx; cchWideChar
0x1800da601  mov     r8, r14; lpMultiByteStr
0x1800da604  mov     edx, 9; dwFlags
0x1800da609  mov     [rsp+0B0h+lpWideCharStr], rbx; lpWideCharStr
0x1800da60e  call    cs:__imp_MultiByteToWideChar
0x1800da614  movsxd  r13, eax
0x1800da617  test    eax, eax
0x1800da619  jz      loc_1800DA823
0x1800da61f  mov     rcx, r13
0x1800da622  add     rcx, rcx
0x1800da625  lea     rdx, [rcx+10h]
0x1800da629  cmp     rcx, rdx
0x1800da62c  sbb     rcx, rcx
0x1800da62f  and     rcx, rdx; Size
0x1800da632  jz      loc_1800DA823
0x1800da638  mov     rdx, 0FFFFFFFFFFFFFF0h
0x1800da642  cmp     rcx, 400h
0x1800da649  ja      short loc_1800DA679
0x1800da64b  lea     rax, [rcx+0Fh]
0x1800da64f  cmp     rax, rcx
0x1800da652  ja      short loc_1800DA657
0x1800da654  mov     rax, rdx
0x1800da657  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800da65b  call    _alloca_probe
0x1800da660  sub     rsp, rax
0x1800da663  lea     rbx, [rsp+0B0h+lpMultiByteStr]
0x1800da668  test    rbx, rbx
0x1800da66b  jz      loc_1800DA823
0x1800da671  mov     dword ptr [rbx], 0CCCCh
0x1800da677  jmp     short loc_1800DA68C
0x1800da679  call    _malloc_base
0x1800da67e  mov     rbx, rax
0x1800da681  test    rax, rax
0x1800da684  jz      short loc_1800DA690
0x1800da686  mov     dword ptr [rax], 0DDDDh
0x1800da68c  add     rbx, 10h
0x1800da690  test    rbx, rbx
0x1800da693  jz      loc_1800DA823
0x1800da699  mov     ecx, [rbp+60h+CodePage]; CodePage
0x1800da69f  mov     r9d, edi; cbMultiByte
0x1800da6a2  mov     [rsp+0B0h+cchWideChar], r13d; cchWideChar
0x1800da6a7  mov     r8, r14; lpMultiByteStr
0x1800da6aa  mov     edx, 1; dwFlags
0x1800da6af  mov     [rsp+0B0h+lpWideCharStr], rbx; lpWideCharStr
0x1800da6b4  call    cs:__imp_MultiByteToWideChar
0x1800da6ba  test    eax, eax
0x1800da6bc  jz      loc_1800DA812
0x1800da6c2  mov     ecx, [rbp+60h+CodePage]; CodePage
0x1800da6c8  mov     r9d, esi; cbMultiByte
0x1800da6cb  mov     [rsp+0B0h+cchWideChar], 0; cchWideChar
0x1800da6d3  mov     r8, r15; lpMultiByteStr
0x1800da6d6  mov     edx, 9; dwFlags
0x1800da6db  mov     [rsp+0B0h+lpWideCharStr], 0; lpWideCharStr
0x1800da6e4  call    cs:__imp_MultiByteToWideChar
0x1800da6ea  movsxd  r15, eax
0x1800da6ed  test    eax, eax
0x1800da6ef  jz      loc_1800DA812
0x1800da6f5  mov     rax, r15
0x1800da6f8  add     rax, rax
0x1800da6fb  lea     rcx, [rax+10h]
0x1800da6ff  cmp     rax, rcx
0x1800da702  sbb     rdx, rdx
0x1800da705  and     rdx, rcx
0x1800da708  jz      loc_1800DA812
0x1800da70e  cmp     rdx, 400h
0x1800da715  ja      short loc_1800DA74C
0x1800da717  lea     rax, [rdx+0Fh]
0x1800da71b  cmp     rax, rdx
0x1800da71e  ja      short loc_1800DA72A
0x1800da720  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800da72a  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800da72e  call    _alloca_probe
0x1800da733  sub     rsp, rax
0x1800da736  lea     rdi, [rsp+0B0h+lpMultiByteStr]
0x1800da73b  test    rdi, rdi
0x1800da73e  jz      loc_1800DA812
0x1800da744  mov     dword ptr [rdi], 0CCCCh
0x1800da74a  jmp     short loc_1800DA762
0x1800da74c  mov     rcx, rdx; Size
0x1800da74f  call    _malloc_base
0x1800da754  mov     rdi, rax
0x1800da757  test    rax, rax
0x1800da75a  jz      short loc_1800DA766
0x1800da75c  mov     dword ptr [rax], 0DDDDh
0x1800da762  add     rdi, 10h
0x1800da766  test    rdi, rdi
0x1800da769  jz      loc_1800DA812
0x1800da76f  mov     r8, [rbp+60h+lpMultiByteStr]; lpMultiByteStr
0x1800da773  lea     r14, [rdi-10h]
0x1800da777  mov     ecx, [rbp+60h+CodePage]; CodePage
0x1800da77d  mov     r9d, esi; cbMultiByte
0x1800da780  mov     [rsp+0B0h+cchWideChar], r15d; cchWideChar
0x1800da785  mov     edx, 1; dwFlags
0x1800da78a  mov     [rsp+0B0h+lpWideCharStr], rdi; lpWideCharStr
0x1800da78f  call    cs:__imp_MultiByteToWideChar
0x1800da795  test    eax, eax
0x1800da797  jnz     short loc_1800DA7B3
0x1800da799  mov     edi, 0DDDDh
0x1800da79e  cmp     [r14], edi
0x1800da7a1  jnz     short loc_1800DA7AB
0x1800da7a3  mov     rcx, r14; Block
0x1800da7a6  call    _free_base
0x1800da7ab  lea     rcx, [rbx-10h]
0x1800da7af  cmp     [rcx], edi
0x1800da7b1  jmp     short loc_1800DA81C
0x1800da7b3  mov     rcx, [rbp+60h+lpLocaleName]; lpLocaleName
0x1800da7b7  mov     r9d, r13d; cchCount1
0x1800da7ba  mov     [rsp+0B0h+lParam], 0; lParam
0x1800da7c3  mov     r8, rbx; lpString1
0x1800da7c6  mov     [rsp+0B0h+lpReserved], 0; lpReserved
0x1800da7cf  mov     edx, 1000h; dwCmpFlags
0x1800da7d4  mov     [rsp+0B0h+lpVersionInformation], 0; lpVersionInformation
0x1800da7dd  mov     [rsp+0B0h+cchWideChar], r15d; cchCount2
0x1800da7e2  mov     [rsp+0B0h+lpWideCharStr], rdi; lpString2
0x1800da7e7  call    cs:__imp_CompareStringEx
0x1800da7ed  mov     esi, 0DDDDh
0x1800da7f2  mov     edi, eax
0x1800da7f4  cmp     [r14], esi
0x1800da7f7  jnz     short loc_1800DA801
0x1800da7f9  mov     rcx, r14; Block
0x1800da7fc  call    _free_base
0x1800da801  lea     rcx, [rbx-10h]; Block
0x1800da805  cmp     [rcx], esi
0x1800da807  jnz     short loc_1800DA80E
0x1800da809  call    _free_base
0x1800da80e  mov     eax, edi
0x1800da810  jmp     short loc_1800DA825
0x1800da812  lea     rcx, [rbx-10h]; Block
0x1800da816  cmp     dword ptr [rcx], 0DDDDh
0x1800da81c  jnz     short loc_1800DA823
0x1800da81e  call    _free_base
0x1800da823  xor     eax, eax
0x1800da825  mov     rcx, [rbp+60h+var_38]
0x1800da829  xor     rcx, rbp; StackCookie
0x1800da82c  call    __security_check_cookie
0x1800da831  lea     rsp, [rbp+30h]
0x1800da835  pop     r15
0x1800da837  pop     r14
0x1800da839  pop     r13
0x1800da83b  pop     rdi
0x1800da83c  pop     rsi
0x1800da83d  pop     rbx
0x1800da83e  pop     rbp
0x1800da83f  retn
0x1800da840  mov     eax, 3
0x1800da845  jmp     short loc_1800DA825
0x1800da847  mov     eax, 1
0x1800da84c  jmp     short loc_1800DA825
0x1800da84e  mov     eax, 2
0x1800da853  jmp     short loc_1800DA825
```
