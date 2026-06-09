# __crtCompareStringA

- ea: `0x1400399d0`
- end: `0x140039d5c`
- name: `__crtCompareStringA`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400213ec`

## callees

- `0x1400399d0`
- `0x14003a5c0`
- `0x14003aab0`
- `0x14004f9a0`
- `0x14005a260`
- `0x140065340`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x140039b1f`
- `KERNEL32!MultiByteToWideChar` at `0x140039bc8`
- `KERNEL32!MultiByteToWideChar` at `0x140039bf8`
- `KERNEL32!MultiByteToWideChar` at `0x140039ca6`
- `KERNEL32!MultiByteToWideChar` at `0x140039b1f`
- `KERNEL32!MultiByteToWideChar` at `0x140039bc8`
- `KERNEL32!MultiByteToWideChar` at `0x140039bf8`
- `KERNEL32!MultiByteToWideChar` at `0x140039ca6`
- `KERNEL32!GetCPInfo` at `0x140039a83`
- `KERNEL32!GetCPInfo` at `0x140039a83`
- `KERNEL32!CompareStringEx` at `0x140039cfc`
- `KERNEL32!CompareStringEx` at `0x140039cfc`

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
  WCHAR *lpWideCharStr; // rbx
  WCHAR *v19; // rax
  int v20; // eax
  int v21; // r15d
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  __int64 v24; // rax
  void *v25; // rsp
  WCHAR *p_dwCmpFlags; // rdi
  WCHAR *v27; // rax
  WCHAR *v28; // r14
  WCHAR *v29; // rcx
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
    v19 = (WCHAR *)malloc(v15);
    lpWideCharStr = v19;
    if ( !v19 )
      goto LABEL_39;
    *(_DWORD *)v19 = 56797;
  }
  else
  {
    v16 = v15 + 15;
    if ( v15 + 15 < v15 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
    lpWideCharStr = (WCHAR *)&dwCmpFlags;
    if ( v32 == (_BYTE *)-80LL )
      return 0;
    dwCmpFlags = 52428;
  }
  lpWideCharStr += 8;
LABEL_39:
  if ( !lpWideCharStr )
    return 0;
  if ( !MultiByteToWideChar(CodePage, 1u, a3, v7, lpWideCharStr, cchWideChar) )
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
    v27 = (WCHAR *)malloc(v22 & -(__int64)(2LL * v20 < v22));
    p_dwCmpFlags = v27;
    if ( !v27 )
      goto LABEL_51;
    *(_DWORD *)v27 = 56797;
  }
  else
  {
    v24 = v23 + 15;
    if ( v23 + 15 < v23 )
      v24 = 0xFFFFFFFFFFFFFF0LL;
    v25 = alloca(v24 & 0xFFFFFFFFFFFFFFF0uLL);
    p_dwCmpFlags = (WCHAR *)&dwCmpFlags;
    if ( v32 == (_BYTE *)-80LL )
      goto LABEL_61;
    dwCmpFlags = 52428;
  }
  p_dwCmpFlags += 8;
LABEL_51:
  if ( !p_dwCmpFlags )
  {
LABEL_61:
    v29 = lpWideCharStr - 8;
    v30 = *((_DWORD *)lpWideCharStr - 4) == 56797;
LABEL_62:
    if ( v30 )
      free(v29);
    return 0;
  }
  v28 = p_dwCmpFlags - 8;
  if ( !MultiByteToWideChar(CodePage, 1u, lpMultiByteStr, v9, p_dwCmpFlags, v21) )
  {
    if ( *(_DWORD *)v28 == 56797 )
      free(v28);
    v29 = lpWideCharStr - 8;
    v30 = *((_DWORD *)lpWideCharStr - 4) == 56797;
    goto LABEL_62;
  }
  v31 = CompareStringEx(lpLocaleName, dwCmpFlags, lpWideCharStr, cchWideChar, p_dwCmpFlags, v21, 0, 0, 0);
  if ( *(_DWORD *)v28 == 56797 )
    free(v28);
  if ( *((_DWORD *)lpWideCharStr - 4) == 56797 )
    free(lpWideCharStr - 8);
  return v31;
}

```

## disassembly

```asm
0x1400399d0  push    rbp
0x1400399d2  push    rbx
0x1400399d3  push    rsi
0x1400399d4  push    rdi
0x1400399d5  push    r13
0x1400399d7  push    r14
0x1400399d9  push    r15
0x1400399db  sub     rsp, 90h
0x1400399e2  lea     rbp, [rsp+50h]
0x1400399e7  mov     rax, cs:__security_cookie
0x1400399ee  xor     rax, rbp
0x1400399f1  mov     [rbp+70h+var_40], rax
0x1400399f5  mov     r15, [rbp+70h+String]
0x1400399fc  xor     ebx, ebx
0x1400399fe  movsxd  rdi, r9d
0x140039a01  mov     r14, r8
0x140039a04  mov     [rbp+70h+dwCmpFlags], edx
0x140039a07  mov     [rbp+70h+lpLocaleName], rcx
0x140039a0b  mov     [rbp+70h+lpMultiByteStr], r15
0x140039a0f  test    r9d, r9d
0x140039a12  jle     short loc_140039A27
0x140039a14  lfence
0x140039a17  mov     rdx, rdi; Count
0x140039a1a  mov     rcx, r8; String
0x140039a1d  call    __strncnt
0x140039a22  mov     rdi, rax
0x140039a25  jmp     short loc_140039A30
0x140039a27  cmp     edi, 0FFFFFFFFh
0x140039a2a  jl      loc_140039D38
0x140039a30  movsxd  rsi, [rbp+70h+arg_28]
0x140039a37  test    esi, esi
0x140039a39  jle     short loc_140039A4E
0x140039a3b  lfence
0x140039a3e  mov     rdx, rsi; Count
0x140039a41  mov     rcx, r15; String
0x140039a44  call    __strncnt
0x140039a49  mov     rsi, rax
0x140039a4c  jmp     short loc_140039A57
0x140039a4e  cmp     esi, 0FFFFFFFFh
0x140039a51  jl      loc_140039D38
0x140039a57  test    edi, edi
0x140039a59  jz      short loc_140039A63
0x140039a5b  test    esi, esi
0x140039a5d  jnz     loc_140039B05
0x140039a63  cmp     edi, esi
0x140039a65  jz      loc_140039D55
0x140039a6b  cmp     esi, 1
0x140039a6e  jg      loc_140039AFB
0x140039a74  cmp     edi, 1
0x140039a77  jg      short loc_140039AC1
0x140039a79  mov     ecx, [rbp+70h+CodePage]; CodePage
0x140039a7f  lea     rdx, [rbp+70h+CPInfo]; lpCPInfo
0x140039a83  call    cs:__imp_GetCPInfo
0x140039a89  test    eax, eax
0x140039a8b  jz      loc_140039D38
0x140039a91  test    edi, edi
0x140039a93  jle     short loc_140039ACB
0x140039a95  cmp     [rbp+70h+CPInfo.MaxCharSize], 2
0x140039a99  jb      short loc_140039AC1
0x140039a9b  lea     rax, [rbp+70h+CPInfo.LeadByte]
0x140039a9f  cmp     [rbp+70h+CPInfo.LeadByte], bl
0x140039aa2  jz      short loc_140039AC1
0x140039aa4  cmp     [rax+1], bl
0x140039aa7  jz      short loc_140039AC1
0x140039aa9  mov     cl, [r14]
0x140039aac  cmp     cl, [rax]
0x140039aae  jb      short loc_140039AB9
0x140039ab0  cmp     cl, [rax+1]
0x140039ab3  jbe     loc_140039D55
0x140039ab9  add     rax, 2
0x140039abd  cmp     [rax], bl
0x140039abf  jnz     short loc_140039AA4
0x140039ac1  mov     eax, 3
0x140039ac6  jmp     loc_140039D3A
0x140039acb  test    esi, esi
0x140039acd  jle     short loc_140039B05
0x140039acf  cmp     [rbp+70h+CPInfo.MaxCharSize], 2
0x140039ad3  jb      short loc_140039AFB
0x140039ad5  lea     rax, [rbp+70h+CPInfo.LeadByte]
0x140039ad9  cmp     [rbp+70h+CPInfo.LeadByte], bl
0x140039adc  jz      short loc_140039AFB
0x140039ade  cmp     [rax+1], bl
0x140039ae1  jz      short loc_140039AFB
0x140039ae3  mov     cl, [r15]
0x140039ae6  cmp     cl, [rax]
0x140039ae8  jb      short loc_140039AF3
0x140039aea  cmp     cl, [rax+1]
0x140039aed  jbe     loc_140039D55
0x140039af3  add     rax, 2
0x140039af7  cmp     [rax], bl
0x140039af9  jnz     short loc_140039ADE
0x140039afb  mov     eax, 1
0x140039b00  jmp     loc_140039D3A
0x140039b05  mov     ecx, [rbp+70h+CodePage]; CodePage
0x140039b0b  mov     r9d, edi; cbMultiByte
0x140039b0e  mov     [rsp+0C0h+cchWideChar], ebx; cchWideChar
0x140039b12  mov     r8, r14; lpMultiByteStr
0x140039b15  mov     edx, 9; dwFlags
0x140039b1a  mov     [rsp+0C0h+lpWideCharStr], rbx; lpWideCharStr
0x140039b1f  call    cs:__imp_MultiByteToWideChar
0x140039b25  movsxd  r13, eax
0x140039b28  test    eax, eax
0x140039b2a  jz      loc_140039D38
0x140039b30  mov     rcx, r13
0x140039b33  add     rcx, rcx
0x140039b36  lea     rdx, [rcx+10h]
0x140039b3a  cmp     rcx, rdx
0x140039b3d  sbb     rcx, rcx
0x140039b40  and     rcx, rdx; Size
0x140039b43  jz      loc_140039D38
0x140039b49  mov     rdx, 0FFFFFFFFFFFFFF0h
0x140039b53  cmp     rcx, 400h
0x140039b5a  ja      short loc_140039B8A
0x140039b5c  lea     rax, [rcx+0Fh]
0x140039b60  cmp     rax, rcx
0x140039b63  ja      short loc_140039B68
0x140039b65  mov     rax, rdx
0x140039b68  and     rax, 0FFFFFFFFFFFFFFF0h
0x140039b6c  call    _alloca_probe
0x140039b71  sub     rsp, rax
0x140039b74  lea     rbx, [rsp+0C0h+dwCmpFlags]
0x140039b79  test    rbx, rbx
0x140039b7c  jz      loc_140039D38
0x140039b82  mov     dword ptr [rbx], 0CCCCh
0x140039b88  jmp     short loc_140039BA0
0x140039b8a  lfence
0x140039b8d  call    malloc
0x140039b92  mov     rbx, rax
0x140039b95  test    rax, rax
0x140039b98  jz      short loc_140039BA4
0x140039b9a  mov     dword ptr [rax], 0DDDDh
0x140039ba0  add     rbx, 10h
0x140039ba4  test    rbx, rbx
0x140039ba7  jz      loc_140039D38
0x140039bad  mov     ecx, [rbp+70h+CodePage]; CodePage
0x140039bb3  mov     r9d, edi; cbMultiByte
0x140039bb6  mov     [rsp+0C0h+cchWideChar], r13d; cchWideChar
0x140039bbb  mov     r8, r14; lpMultiByteStr
0x140039bbe  mov     edx, 1; dwFlags
0x140039bc3  mov     [rsp+0C0h+lpWideCharStr], rbx; lpWideCharStr
0x140039bc8  call    cs:__imp_MultiByteToWideChar
0x140039bce  test    eax, eax
0x140039bd0  jz      loc_140039D27
0x140039bd6  mov     ecx, [rbp+70h+CodePage]; CodePage
0x140039bdc  mov     r9d, esi; cbMultiByte
0x140039bdf  mov     [rsp+0C0h+cchWideChar], 0; cchWideChar
0x140039be7  mov     r8, r15; lpMultiByteStr
0x140039bea  mov     edx, 9; dwFlags
0x140039bef  mov     [rsp+0C0h+lpWideCharStr], 0; lpWideCharStr
0x140039bf8  call    cs:__imp_MultiByteToWideChar
0x140039bfe  movsxd  r15, eax
0x140039c01  test    eax, eax
0x140039c03  jz      loc_140039D27
0x140039c09  mov     rax, r15
0x140039c0c  add     rax, rax
0x140039c0f  lea     rcx, [rax+10h]
0x140039c13  cmp     rax, rcx
0x140039c16  sbb     rdx, rdx
0x140039c19  and     rdx, rcx
0x140039c1c  jz      loc_140039D27
0x140039c22  cmp     rdx, 400h
0x140039c29  ja      short loc_140039C60
0x140039c2b  lea     rax, [rdx+0Fh]
0x140039c2f  cmp     rax, rdx
0x140039c32  ja      short loc_140039C3E
0x140039c34  mov     rax, 0FFFFFFFFFFFFFF0h
0x140039c3e  and     rax, 0FFFFFFFFFFFFFFF0h
0x140039c42  call    _alloca_probe
0x140039c47  sub     rsp, rax
0x140039c4a  lea     rdi, [rsp+0C0h+dwCmpFlags]
0x140039c4f  test    rdi, rdi
0x140039c52  jz      loc_140039D27
0x140039c58  mov     dword ptr [rdi], 0CCCCh
0x140039c5e  jmp     short loc_140039C79
0x140039c60  lfence
0x140039c63  mov     rcx, rdx; Size
0x140039c66  call    malloc
0x140039c6b  mov     rdi, rax
0x140039c6e  test    rax, rax
0x140039c71  jz      short loc_140039C7D
0x140039c73  mov     dword ptr [rax], 0DDDDh
0x140039c79  add     rdi, 10h
0x140039c7d  test    rdi, rdi
0x140039c80  jz      loc_140039D27
0x140039c86  mov     r8, [rbp+70h+lpMultiByteStr]; lpMultiByteStr
0x140039c8a  lea     r14, [rdi-10h]
0x140039c8e  mov     ecx, [rbp+70h+CodePage]; CodePage
0x140039c94  mov     r9d, esi; cbMultiByte
0x140039c97  mov     [rsp+0C0h+cchWideChar], r15d; cchWideChar
0x140039c9c  mov     edx, 1; dwFlags
0x140039ca1  mov     [rsp+0C0h+lpWideCharStr], rdi; lpWideCharStr
0x140039ca6  call    cs:__imp_MultiByteToWideChar
0x140039cac  test    eax, eax
0x140039cae  jnz     short loc_140039CCA
0x140039cb0  mov     edi, 0DDDDh
0x140039cb5  cmp     [r14], edi
0x140039cb8  jnz     short loc_140039CC2
0x140039cba  mov     rcx, r14; Block
0x140039cbd  call    free
0x140039cc2  lea     rcx, [rbx-10h]
0x140039cc6  cmp     [rcx], edi
0x140039cc8  jmp     short loc_140039D31
0x140039cca  mov     edx, [rbp+70h+dwCmpFlags]; dwCmpFlags
0x140039ccd  mov     r9d, r13d; cchCount1
0x140039cd0  mov     rcx, [rbp+70h+lpLocaleName]; lpLocaleName
0x140039cd4  mov     r8, rbx; lpString1
0x140039cd7  mov     [rsp+0C0h+lParam], 0; lParam
0x140039ce0  mov     [rsp+0C0h+lpReserved], 0; lpReserved
0x140039ce9  mov     [rsp+0C0h+lpVersionInformation], 0; lpVersionInformation
0x140039cf2  mov     [rsp+0C0h+cchWideChar], r15d; cchCount2
0x140039cf7  mov     [rsp+0C0h+lpWideCharStr], rdi; lpString2
0x140039cfc  call    cs:__imp_CompareStringEx
0x140039d02  mov     esi, 0DDDDh
0x140039d07  mov     edi, eax
0x140039d09  cmp     [r14], esi
0x140039d0c  jnz     short loc_140039D16
0x140039d0e  mov     rcx, r14; Block
0x140039d11  call    free
0x140039d16  lea     rcx, [rbx-10h]; Block
0x140039d1a  cmp     [rcx], esi
0x140039d1c  jnz     short loc_140039D23
0x140039d1e  call    free
0x140039d23  mov     eax, edi
0x140039d25  jmp     short loc_140039D3A
0x140039d27  lea     rcx, [rbx-10h]; Block
0x140039d2b  cmp     dword ptr [rcx], 0DDDDh
0x140039d31  jnz     short loc_140039D38
0x140039d33  call    free
0x140039d38  xor     eax, eax
0x140039d3a  mov     rcx, [rbp+70h+var_40]
0x140039d3e  xor     rcx, rbp; StackCookie
0x140039d41  call    __security_check_cookie
0x140039d46  lea     rsp, [rbp+40h]
0x140039d4a  pop     r15
0x140039d4c  pop     r14
0x140039d4e  pop     r13
0x140039d50  pop     rdi
0x140039d51  pop     rsi
0x140039d52  pop     rbx
0x140039d53  pop     rbp
0x140039d54  retn
0x140039d55  mov     eax, 2
0x140039d5a  jmp     short loc_140039D3A
```
