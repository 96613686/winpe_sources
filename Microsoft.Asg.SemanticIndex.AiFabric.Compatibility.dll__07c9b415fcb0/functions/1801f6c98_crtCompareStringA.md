# __crtCompareStringA

- ea: `0x1801f6c98`
- end: `0x1801f7024`
- name: `__crtCompareStringA`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1801f6880`

## callees

- `0x1801f6c98`
- `0x1801f7110`
- `0x1801f7d30`
- `0x1802115b0`
- `0x1802115c0`
- `0x180213a40`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1801f6de7`
- `KERNEL32!MultiByteToWideChar` at `0x1801f6e90`
- `KERNEL32!MultiByteToWideChar` at `0x1801f6ec0`
- `KERNEL32!MultiByteToWideChar` at `0x1801f6f6e`
- `KERNEL32!MultiByteToWideChar` at `0x1801f6de7`
- `KERNEL32!MultiByteToWideChar` at `0x1801f6e90`
- `KERNEL32!MultiByteToWideChar` at `0x1801f6ec0`
- `KERNEL32!MultiByteToWideChar` at `0x1801f6f6e`
- `KERNEL32!CompareStringEx` at `0x1801f6fc4`
- `KERNEL32!CompareStringEx` at `0x1801f6fc4`
- `KERNEL32!GetCPInfo` at `0x1801f6d4b`
- `KERNEL32!GetCPInfo` at `0x1801f6d4b`

## pseudocode

```c
__int64 __fastcall _crtCompareStringA(
        const WCHAR *a1,
        DWORD a2,
        const char *a3,
        int a4,
        char *String,
        int a6,
        UINT CodePage)
{
  int v7; // edi
  int v9; // esi
  BYTE *LeadByte; // rax
  BYTE *v12; // rax
  int v13; // eax
  int cchWideChar; // r13d
  size_t v15; // rcx
  __int64 v16; // rax
  void *v17; // rsp
  DWORD *lpWideCharStr; // rbx
  DWORD *v19; // rax
  int v20; // eax
  int v21; // r15d
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  __int64 v24; // rax
  void *v25; // rsp
  DWORD *p_dwCmpFlags; // rdi
  DWORD *v27; // rax
  DWORD *v28; // r14
  DWORD *v29; // rcx
  bool v30; // zf
  unsigned int v31; // edi
  _BYTE v32[32]; // [rsp+0h] [rbp-50h] BYREF
  DWORD dwCmpFlags; // [rsp+50h] [rbp+0h] BYREF
  LPCCH lpMultiByteStr; // [rsp+58h] [rbp+8h]
  LPCWSTR lpLocaleName; // [rsp+60h] [rbp+10h]
  _cpinfo CPInfo; // [rsp+68h] [rbp+18h] BYREF

  v7 = a4;
  dwCmpFlags = a2;
  lpLocaleName = a1;
  lpMultiByteStr = String;
  if ( a4 <= 0 )
  {
    if ( a4 < -1 )
      return 0;
  }
  else
  {
    _mm_lfence();
    v7 = _strncnt(a3, a4);
  }
  v9 = a6;
  if ( a6 <= 0 )
  {
    if ( a6 < -1 )
      return 0;
  }
  else
  {
    _mm_lfence();
    v9 = _strncnt(String, a6);
  }
  if ( !v7 || !v9 )
  {
    if ( v7 == v9 )
      return 2;
    if ( v9 > 1 )
      return 1;
    if ( v7 > 1 )
      return 3;
    if ( !GetCPInfo(CodePage, &CPInfo) )
      return 0;
    if ( v7 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        LeadByte = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( LeadByte[1] )
          {
            if ( (unsigned int)*a3 >= *LeadByte && (unsigned int)*a3 <= LeadByte[1] )
              return 2;
            LeadByte += 2;
            if ( !*LeadByte )
              return 3;
          }
        }
      }
      return 3;
    }
    if ( v9 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        v12 = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( v12[1] )
          {
            if ( (unsigned __int8)*String >= *v12 && (unsigned __int8)*String <= v12[1] )
              return 2;
            v12 += 2;
            if ( !*v12 )
              return 1;
          }
        }
      }
      return 1;
    }
  }
  v13 = MultiByteToWideChar(CodePage, 9u, a3, v7, 0, 0);
  cchWideChar = v13;
  if ( !v13 )
    return 0;
  v15 = (2LL * v13 + 16) & -(__int64)(2LL * v13 < (unsigned __int64)(2LL * v13 + 16));
  if ( !v15 )
    return 0;
  if ( v15 > 0x400 )
  {
    _mm_lfence();
    v19 = (DWORD *)malloc(v15);
    lpWideCharStr = v19;
    if ( !v19 )
      goto LABEL_39;
    *v19 = 56797;
  }
  else
  {
    v16 = v15 + 15;
    if ( v15 + 15 < v15 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
    lpWideCharStr = &dwCmpFlags;
    if ( v32 == (_BYTE *)-80LL )
      return 0;
    dwCmpFlags = 52428;
  }
  lpWideCharStr += 4;
LABEL_39:
  if ( !lpWideCharStr )
    return 0;
  if ( !MultiByteToWideChar(CodePage, 1u, a3, v7, (LPWSTR)lpWideCharStr, cchWideChar) )
    goto LABEL_61;
  v20 = MultiByteToWideChar(CodePage, 9u, String, v9, 0, 0);
  v21 = v20;
  if ( !v20 )
    goto LABEL_61;
  v22 = 2LL * v20 + 16;
  v23 = v22 & -(__int64)(2LL * v20 < v22);
  if ( !v23 )
    goto LABEL_61;
  if ( v23 > 0x400 )
  {
    _mm_lfence();
    v27 = (DWORD *)malloc(v22 & -(__int64)(2LL * v20 < v22));
    p_dwCmpFlags = v27;
    if ( !v27 )
      goto LABEL_51;
    *v27 = 56797;
  }
  else
  {
    v24 = v23 + 15;
    if ( v23 + 15 < v23 )
      v24 = 0xFFFFFFFFFFFFFF0LL;
    v25 = alloca(v24 & 0xFFFFFFFFFFFFFFF0uLL);
    p_dwCmpFlags = &dwCmpFlags;
    if ( v32 == (_BYTE *)-80LL )
      goto LABEL_61;
    dwCmpFlags = 52428;
  }
  p_dwCmpFlags += 4;
LABEL_51:
  if ( !p_dwCmpFlags )
  {
LABEL_61:
    v29 = lpWideCharStr - 4;
    v30 = *(lpWideCharStr - 4) == 56797;
LABEL_62:
    if ( v30 )
      free(v29);
    return 0;
  }
  v28 = p_dwCmpFlags - 4;
  if ( !MultiByteToWideChar(CodePage, 1u, lpMultiByteStr, v9, (LPWSTR)p_dwCmpFlags, v21) )
  {
    if ( *v28 == 56797 )
      free(v28);
    v29 = lpWideCharStr - 4;
    v30 = *(lpWideCharStr - 4) == 56797;
    goto LABEL_62;
  }
  v31 = CompareStringEx(
          lpLocaleName,
          dwCmpFlags,
          (LPCWCH)lpWideCharStr,
          cchWideChar,
          (LPCWCH)p_dwCmpFlags,
          v21,
          0,
          0,
          0);
  if ( *v28 == 56797 )
    free(v28);
  if ( *(lpWideCharStr - 4) == 56797 )
    free(lpWideCharStr - 4);
  return v31;
}

```

## disassembly

```asm
0x1801f6c98  push    rbp
0x1801f6c9a  push    rbx
0x1801f6c9b  push    rsi
0x1801f6c9c  push    rdi
0x1801f6c9d  push    r13
0x1801f6c9f  push    r14
0x1801f6ca1  push    r15
0x1801f6ca3  sub     rsp, 90h
0x1801f6caa  lea     rbp, [rsp+50h]
0x1801f6caf  mov     rax, cs:__security_cookie
0x1801f6cb6  xor     rax, rbp
0x1801f6cb9  mov     [rbp+70h+var_40], rax
0x1801f6cbd  mov     r15, [rbp+70h+String]
0x1801f6cc4  xor     ebx, ebx
0x1801f6cc6  movsxd  rdi, r9d
0x1801f6cc9  mov     r14, r8
0x1801f6ccc  mov     [rbp+70h+dwCmpFlags], edx
0x1801f6ccf  mov     [rbp+70h+lpLocaleName], rcx
0x1801f6cd3  mov     [rbp+70h+lpMultiByteStr], r15
0x1801f6cd7  test    r9d, r9d
0x1801f6cda  jle     short loc_1801F6CEF
0x1801f6cdc  lfence
0x1801f6cdf  mov     rdx, rdi; Count
0x1801f6ce2  mov     rcx, r8; String
0x1801f6ce5  call    __strncnt
0x1801f6cea  mov     rdi, rax
0x1801f6ced  jmp     short loc_1801F6CF8
0x1801f6cef  cmp     edi, 0FFFFFFFFh
0x1801f6cf2  jl      loc_1801F7000
0x1801f6cf8  movsxd  rsi, [rbp+70h+arg_28]
0x1801f6cff  test    esi, esi
0x1801f6d01  jle     short loc_1801F6D16
0x1801f6d03  lfence
0x1801f6d06  mov     rdx, rsi; Count
0x1801f6d09  mov     rcx, r15; String
0x1801f6d0c  call    __strncnt
0x1801f6d11  mov     rsi, rax
0x1801f6d14  jmp     short loc_1801F6D1F
0x1801f6d16  cmp     esi, 0FFFFFFFFh
0x1801f6d19  jl      loc_1801F7000
0x1801f6d1f  test    edi, edi
0x1801f6d21  jz      short loc_1801F6D2B
0x1801f6d23  test    esi, esi
0x1801f6d25  jnz     loc_1801F6DCD
0x1801f6d2b  cmp     edi, esi
0x1801f6d2d  jz      loc_1801F701D
0x1801f6d33  cmp     esi, 1
0x1801f6d36  jg      loc_1801F6DC3
0x1801f6d3c  cmp     edi, 1
0x1801f6d3f  jg      short loc_1801F6D89
0x1801f6d41  mov     ecx, [rbp+70h+CodePage]; CodePage
0x1801f6d47  lea     rdx, [rbp+70h+CPInfo]; lpCPInfo
0x1801f6d4b  call    cs:__imp_GetCPInfo
0x1801f6d51  test    eax, eax
0x1801f6d53  jz      loc_1801F7000
0x1801f6d59  test    edi, edi
0x1801f6d5b  jle     short loc_1801F6D93
0x1801f6d5d  cmp     [rbp+70h+CPInfo.MaxCharSize], 2
0x1801f6d61  jb      short loc_1801F6D89
0x1801f6d63  lea     rax, [rbp+70h+CPInfo.LeadByte]
0x1801f6d67  cmp     [rbp+70h+CPInfo.LeadByte], bl
0x1801f6d6a  jz      short loc_1801F6D89
0x1801f6d6c  cmp     [rax+1], bl
0x1801f6d6f  jz      short loc_1801F6D89
0x1801f6d71  mov     cl, [r14]
0x1801f6d74  cmp     cl, [rax]
0x1801f6d76  jb      short loc_1801F6D81
0x1801f6d78  cmp     cl, [rax+1]
0x1801f6d7b  jbe     loc_1801F701D
0x1801f6d81  add     rax, 2
0x1801f6d85  cmp     [rax], bl
0x1801f6d87  jnz     short loc_1801F6D6C
0x1801f6d89  mov     eax, 3
0x1801f6d8e  jmp     loc_1801F7002
0x1801f6d93  test    esi, esi
0x1801f6d95  jle     short loc_1801F6DCD
0x1801f6d97  cmp     [rbp+70h+CPInfo.MaxCharSize], 2
0x1801f6d9b  jb      short loc_1801F6DC3
0x1801f6d9d  lea     rax, [rbp+70h+CPInfo.LeadByte]
0x1801f6da1  cmp     [rbp+70h+CPInfo.LeadByte], bl
0x1801f6da4  jz      short loc_1801F6DC3
0x1801f6da6  cmp     [rax+1], bl
0x1801f6da9  jz      short loc_1801F6DC3
0x1801f6dab  mov     cl, [r15]
0x1801f6dae  cmp     cl, [rax]
0x1801f6db0  jb      short loc_1801F6DBB
0x1801f6db2  cmp     cl, [rax+1]
0x1801f6db5  jbe     loc_1801F701D
0x1801f6dbb  add     rax, 2
0x1801f6dbf  cmp     [rax], bl
0x1801f6dc1  jnz     short loc_1801F6DA6
0x1801f6dc3  mov     eax, 1
0x1801f6dc8  jmp     loc_1801F7002
0x1801f6dcd  mov     ecx, [rbp+70h+CodePage]; CodePage
0x1801f6dd3  mov     r9d, edi; cbMultiByte
0x1801f6dd6  mov     [rsp+0C0h+cchWideChar], ebx; cchWideChar
0x1801f6dda  mov     r8, r14; lpMultiByteStr
0x1801f6ddd  mov     edx, 9; dwFlags
0x1801f6de2  mov     [rsp+0C0h+lpWideCharStr], rbx; lpWideCharStr
0x1801f6de7  call    cs:__imp_MultiByteToWideChar
0x1801f6ded  movsxd  r13, eax
0x1801f6df0  test    eax, eax
0x1801f6df2  jz      loc_1801F7000
0x1801f6df8  mov     rcx, r13
0x1801f6dfb  add     rcx, rcx
0x1801f6dfe  lea     rdx, [rcx+10h]
0x1801f6e02  cmp     rcx, rdx
0x1801f6e05  sbb     rcx, rcx
0x1801f6e08  and     rcx, rdx; Size
0x1801f6e0b  jz      loc_1801F7000
0x1801f6e11  mov     rdx, 0FFFFFFFFFFFFFF0h
0x1801f6e1b  cmp     rcx, 400h
0x1801f6e22  ja      short loc_1801F6E52
0x1801f6e24  lea     rax, [rcx+0Fh]
0x1801f6e28  cmp     rax, rcx
0x1801f6e2b  ja      short loc_1801F6E30
0x1801f6e2d  mov     rax, rdx
0x1801f6e30  and     rax, 0FFFFFFFFFFFFFFF0h
0x1801f6e34  call    _alloca_probe
0x1801f6e39  sub     rsp, rax
0x1801f6e3c  lea     rbx, [rsp+0C0h+dwCmpFlags]
0x1801f6e41  test    rbx, rbx
0x1801f6e44  jz      loc_1801F7000
0x1801f6e4a  mov     dword ptr [rbx], 0CCCCh
0x1801f6e50  jmp     short loc_1801F6E68
0x1801f6e52  lfence
0x1801f6e55  call    malloc
0x1801f6e5a  mov     rbx, rax
0x1801f6e5d  test    rax, rax
0x1801f6e60  jz      short loc_1801F6E6C
0x1801f6e62  mov     dword ptr [rax], 0DDDDh
0x1801f6e68  add     rbx, 10h
0x1801f6e6c  test    rbx, rbx
0x1801f6e6f  jz      loc_1801F7000
0x1801f6e75  mov     ecx, [rbp+70h+CodePage]; CodePage
0x1801f6e7b  mov     r9d, edi; cbMultiByte
0x1801f6e7e  mov     [rsp+0C0h+cchWideChar], r13d; cchWideChar
0x1801f6e83  mov     r8, r14; lpMultiByteStr
0x1801f6e86  mov     edx, 1; dwFlags
0x1801f6e8b  mov     [rsp+0C0h+lpWideCharStr], rbx; lpWideCharStr
0x1801f6e90  call    cs:__imp_MultiByteToWideChar
0x1801f6e96  test    eax, eax
0x1801f6e98  jz      loc_1801F6FEF
0x1801f6e9e  mov     ecx, [rbp+70h+CodePage]; CodePage
0x1801f6ea4  mov     r9d, esi; cbMultiByte
0x1801f6ea7  mov     [rsp+0C0h+cchWideChar], 0; cchWideChar
0x1801f6eaf  mov     r8, r15; lpMultiByteStr
0x1801f6eb2  mov     edx, 9; dwFlags
0x1801f6eb7  mov     [rsp+0C0h+lpWideCharStr], 0; lpWideCharStr
0x1801f6ec0  call    cs:__imp_MultiByteToWideChar
0x1801f6ec6  movsxd  r15, eax
0x1801f6ec9  test    eax, eax
0x1801f6ecb  jz      loc_1801F6FEF
0x1801f6ed1  mov     rax, r15
0x1801f6ed4  add     rax, rax
0x1801f6ed7  lea     rcx, [rax+10h]
0x1801f6edb  cmp     rax, rcx
0x1801f6ede  sbb     rdx, rdx
0x1801f6ee1  and     rdx, rcx
0x1801f6ee4  jz      loc_1801F6FEF
0x1801f6eea  cmp     rdx, 400h
0x1801f6ef1  ja      short loc_1801F6F28
0x1801f6ef3  lea     rax, [rdx+0Fh]
0x1801f6ef7  cmp     rax, rdx
0x1801f6efa  ja      short loc_1801F6F06
0x1801f6efc  mov     rax, 0FFFFFFFFFFFFFF0h
0x1801f6f06  and     rax, 0FFFFFFFFFFFFFFF0h
0x1801f6f0a  call    _alloca_probe
0x1801f6f0f  sub     rsp, rax
0x1801f6f12  lea     rdi, [rsp+0C0h+dwCmpFlags]
0x1801f6f17  test    rdi, rdi
0x1801f6f1a  jz      loc_1801F6FEF
0x1801f6f20  mov     dword ptr [rdi], 0CCCCh
0x1801f6f26  jmp     short loc_1801F6F41
0x1801f6f28  lfence
0x1801f6f2b  mov     rcx, rdx; Size
0x1801f6f2e  call    malloc
0x1801f6f33  mov     rdi, rax
0x1801f6f36  test    rax, rax
0x1801f6f39  jz      short loc_1801F6F45
0x1801f6f3b  mov     dword ptr [rax], 0DDDDh
0x1801f6f41  add     rdi, 10h
0x1801f6f45  test    rdi, rdi
0x1801f6f48  jz      loc_1801F6FEF
0x1801f6f4e  mov     r8, [rbp+70h+lpMultiByteStr]; lpMultiByteStr
0x1801f6f52  lea     r14, [rdi-10h]
0x1801f6f56  mov     ecx, [rbp+70h+CodePage]; CodePage
0x1801f6f5c  mov     r9d, esi; cbMultiByte
0x1801f6f5f  mov     [rsp+0C0h+cchWideChar], r15d; cchWideChar
0x1801f6f64  mov     edx, 1; dwFlags
0x1801f6f69  mov     [rsp+0C0h+lpWideCharStr], rdi; lpWideCharStr
0x1801f6f6e  call    cs:__imp_MultiByteToWideChar
0x1801f6f74  test    eax, eax
0x1801f6f76  jnz     short loc_1801F6F92
0x1801f6f78  mov     edi, 0DDDDh
0x1801f6f7d  cmp     [r14], edi
0x1801f6f80  jnz     short loc_1801F6F8A
0x1801f6f82  mov     rcx, r14; Block
0x1801f6f85  call    free
0x1801f6f8a  lea     rcx, [rbx-10h]
0x1801f6f8e  cmp     [rcx], edi
0x1801f6f90  jmp     short loc_1801F6FF9
0x1801f6f92  mov     edx, [rbp+70h+dwCmpFlags]; dwCmpFlags
0x1801f6f95  mov     r9d, r13d; cchCount1
0x1801f6f98  mov     rcx, [rbp+70h+lpLocaleName]; lpLocaleName
0x1801f6f9c  mov     r8, rbx; lpString1
0x1801f6f9f  mov     [rsp+0C0h+lParam], 0; lParam
0x1801f6fa8  mov     [rsp+0C0h+lpReserved], 0; lpReserved
0x1801f6fb1  mov     [rsp+0C0h+lpVersionInformation], 0; lpVersionInformation
0x1801f6fba  mov     [rsp+0C0h+cchWideChar], r15d; cchCount2
0x1801f6fbf  mov     [rsp+0C0h+lpWideCharStr], rdi; lpString2
0x1801f6fc4  call    cs:__imp_CompareStringEx
0x1801f6fca  mov     esi, 0DDDDh
0x1801f6fcf  mov     edi, eax
0x1801f6fd1  cmp     [r14], esi
0x1801f6fd4  jnz     short loc_1801F6FDE
0x1801f6fd6  mov     rcx, r14; Block
0x1801f6fd9  call    free
0x1801f6fde  lea     rcx, [rbx-10h]; Block
0x1801f6fe2  cmp     [rcx], esi
0x1801f6fe4  jnz     short loc_1801F6FEB
0x1801f6fe6  call    free
0x1801f6feb  mov     eax, edi
0x1801f6fed  jmp     short loc_1801F7002
0x1801f6fef  lea     rcx, [rbx-10h]; Block
0x1801f6ff3  cmp     dword ptr [rcx], 0DDDDh
0x1801f6ff9  jnz     short loc_1801F7000
0x1801f6ffb  call    free
0x1801f7000  xor     eax, eax
0x1801f7002  mov     rcx, [rbp+70h+var_40]
0x1801f7006  xor     rcx, rbp; StackCookie
0x1801f7009  call    __security_check_cookie
0x1801f700e  lea     rsp, [rbp+40h]
0x1801f7012  pop     r15
0x1801f7014  pop     r14
0x1801f7016  pop     r13
0x1801f7018  pop     rdi
0x1801f7019  pop     rsi
0x1801f701a  pop     rbx
0x1801f701b  pop     rbp
0x1801f701c  retn
0x1801f701d  mov     eax, 2
0x1801f7022  jmp     short loc_1801F7002
```
