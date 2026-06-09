# ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(void *,ushort const *,ulong,ProofOfPossessionCookieInfo *)

- ea: `0x180003c28`
- end: `0x180003e06`
- name: `??$SetCookiesAndFreeTokens@UProofOfPossessionCookieInfo@@@ProofOfPossessionTokenProvider@@YAXPEAXPEBGKPEAUProofOfPossessionCookieInfo@@@Z`
- size: `478`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002b34`
- `0x180003520`

## callees

- `0x180003440`
- `0x180003c28`
- `0x18001054c`
- `0x1800a5a88`
- `0x1800a5a94`
- `0x18011627c`
- `0x1801164ac`

## import_xrefs

- `msvcrt!wcschr` at `0x180003d65`
- `msvcrt!wcschr` at `0x180003d65`
- `msvcrt!wcscpy_s` at `0x180003d7e`
- `msvcrt!wcscpy_s` at `0x180003d7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d1c`
- `WININET!HttpAddRequestHeadersW` at `0x180003d9a`
- `WININET!HttpAddRequestHeadersW` at `0x180003d9a`
- `WININET!InternetSetCookieExW` at `0x180003dfb`
- `WININET!InternetSetCookieExW` at `0x180003dfb`

## pseudocode

```c
void __fastcall ProofOfPossessionTokenProvider::SetCookiesAndFreeTokens<ProofOfPossessionCookieInfo>(
        void *a1,
        const WCHAR *a2,
        unsigned int a3,
        unsigned int *a4)
{
  void *v7; // rbx
  unsigned int v8; // r14d
  __int64 v9; // rbp
  __int64 v10; // rsi
  ProofOfPossessionTokenProvider *v11; // rcx
  unsigned int *v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int64 v16; // r15
  unsigned __int16 *v17; // rax
  wchar_t *v18; // rbx
  wchar_t *v19; // rax
  DWORD v20; // ebx
  bool IsEdgeCookiesFeatureEnabled; // al
  DWORD v22; // r9d
  DWORD dwSize; // [rsp+80h] [rbp+18h] BYREF

  dwSize = 0;
  v7 = a1;
  v8 = 0;
  if ( a3 )
  {
    v9 = 0;
    while ( 1 )
    {
      v10 = 8 * v9;
      if ( !ProofOfPossessionTokenProvider::ShouldSetCookie(a2, *(wchar_t **)&a4[8 * v9], &dwSize, a4)
        && !ProofOfPossessionTokenProvider::ShouldSetDeviceCookie(a2, *(wchar_t **)&a4[v10], &dwSize, v12) )
      {
        goto LABEL_12;
      }
      if ( !v7 )
        break;
      v13 = *(_QWORD *)&a4[v10 + 2];
      if ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(*(_QWORD *)&a4[v10] + 2 * v14) );
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)(v13 + 2 * v15) );
        v16 = (unsigned int)(v15 + v14 + 5);
        v17 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v16, 2u));
        v18 = v17;
        if ( v17 )
        {
          if ( (int)StringCchPrintfW(v17, v16, L"%s: %s\r\n", *(_QWORD *)&a4[v10], *(_QWORD *)&a4[v10 + 2]) >= 0 )
          {
            v19 = wcschr(v18, 0x3Bu);
            if ( !v19 || !wcscpy_s(v19, 3u, L"\r\n") )
              HttpAddRequestHeadersW(a1, v18, 0xFFFFFFFF, 0x10000000u);
          }
          operator delete[](v18);
        }
LABEL_11:
        v7 = a1;
      }
LABEL_12:
      CoTaskMemFree(*(LPVOID *)&a4[v10]);
      CoTaskMemFree(*(LPVOID *)&a4[v10 + 2]);
      CoTaskMemFree(*(LPVOID *)&a4[v10 + 6]);
      ++v8;
      ++v9;
      if ( v8 >= a3 )
        goto LABEL_13;
    }
    v20 = a4[v10 + 4];
    IsEdgeCookiesFeatureEnabled = ProofOfPossessionTokenProvider::IsEdgeCookiesFeatureEnabled(v11);
    v22 = v20 | 0x8000;
    if ( !IsEdgeCookiesFeatureEnabled )
      v22 = v20;
    InternetSetCookieExW(a2, *(LPCWSTR *)&a4[v10], *(LPCWSTR *)&a4[v10 + 2], v22, *(_QWORD *)&a4[v10 + 6]);
    goto LABEL_11;
  }
LABEL_13:
  CoTaskMemFree(a4);
}

```

## disassembly

```asm
0x180003c28  mov     rax, rsp
0x180003c2b  mov     [rax+10h], rbx
0x180003c2f  mov     [rax+8], rcx
0x180003c33  push    rbp
0x180003c34  push    rsi
0x180003c35  push    rdi
0x180003c36  push    r12
0x180003c38  push    r13
0x180003c3a  push    r14
0x180003c3c  push    r15
0x180003c3e  sub     rsp, 30h
0x180003c42  xor     r15d, r15d
0x180003c45  mov     rdi, r9
0x180003c48  mov     [rax+18h], r15d
0x180003c4c  mov     r13d, r8d
0x180003c4f  mov     r12, rdx
0x180003c52  mov     rbx, rcx
0x180003c55  mov     r14d, r15d
0x180003c58  test    r8d, r8d
0x180003c5b  jz      loc_180003D19
0x180003c61  mov     ebp, r15d
0x180003c64  mov     rsi, rbp
0x180003c67  lea     r8, [rsp+68h+dwSize]; lpdwSize
0x180003c6f  shl     rsi, 5
0x180003c73  mov     rcx, r12; lpszUrl
0x180003c76  mov     rdx, [rsi+rdi]; String1
0x180003c7a  call    ?ShouldSetCookie@ProofOfPossessionTokenProvider@@YA_NPEBG0PEAK@Z; ProofOfPossessionTokenProvider::ShouldSetCookie(ushort const *,ushort const *,ulong *)
0x180003c7f  test    al, al
0x180003c81  jz      loc_180003DAD
0x180003c87  test    rbx, rbx
0x180003c8a  jz      loc_180003DCE
0x180003c90  mov     rdx, [rsi+rdi+8]
0x180003c95  test    rdx, rdx
0x180003c98  jz      short loc_180003CEA
0x180003c9a  mov     rax, [rsi+rdi]
0x180003c9e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003ca2  mov     rcx, r8
0x180003ca5  inc     rcx
0x180003ca8  cmp     [rax+rcx*2], r15w
0x180003cad  jnz     short loc_180003CA5
0x180003caf  mov     rax, r8
0x180003cb2  inc     rax
0x180003cb5  cmp     [rdx+rax*2], r15w
0x180003cba  jnz     short loc_180003CB2
0x180003cbc  lea     r15, [rcx+5]
0x180003cc0  add     r15, rax
0x180003cc3  mov     eax, 2
0x180003cc8  mov     r15d, r15d
0x180003ccb  mul     r15
0x180003cce  cmovb   rax, r8
0x180003cd2  mov     rcx, rax; unsigned __int64
0x180003cd5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003cda  mov     rbx, rax
0x180003cdd  test    rax, rax
0x180003ce0  jnz     short loc_180003D37
0x180003ce2  xor     r15d, r15d
0x180003ce5  mov     rbx, [rsp+68h+hRequest]
0x180003cea  mov     rcx, [rsi+rdi]; pv
0x180003cee  call    cs:__imp_CoTaskMemFree
0x180003cf4  mov     rcx, [rsi+rdi+8]; pv
0x180003cf9  call    cs:__imp_CoTaskMemFree
0x180003cff  mov     rcx, [rsi+rdi+18h]; pv
0x180003d04  call    cs:__imp_CoTaskMemFree
0x180003d0a  inc     r14d
0x180003d0d  inc     rbp
0x180003d10  cmp     r14d, r13d
0x180003d13  jb      loc_180003C64
0x180003d19  mov     rcx, rdi; pv
0x180003d1c  call    cs:__imp_CoTaskMemFree
0x180003d22  mov     rbx, [rsp+68h+arg_8]
0x180003d27  add     rsp, 30h
0x180003d2b  pop     r15
0x180003d2d  pop     r14
0x180003d2f  pop     r13
0x180003d31  pop     r12
0x180003d33  pop     rdi
0x180003d34  pop     rsi
0x180003d35  pop     rbp
0x180003d36  retn
0x180003d37  mov     rcx, [rsi+rdi+8]
0x180003d3c  lea     r8, aSS_4; "%s: %s\r\n"
0x180003d43  mov     r9, [rsi+rdi]
0x180003d47  mov     rdx, r15; unsigned __int64
0x180003d4a  mov     [rsp+68h+dwReserved], rcx
0x180003d4f  mov     rcx, rbx; unsigned __int16 *
0x180003d52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003d57  xor     r15d, r15d
0x180003d5a  test    eax, eax
0x180003d5c  js      short loc_180003DA0
0x180003d5e  lea     edx, [r15+3Bh]; Ch
0x180003d62  mov     rcx, rbx; Str
0x180003d65  call    cs:__imp_wcschr
0x180003d6b  test    rax, rax
0x180003d6e  jz      short loc_180003D88
0x180003d70  lea     r8, Source; "\r\n"
0x180003d77  mov     rcx, rax; Destination
0x180003d7a  lea     edx, [r15+3]; SizeInWords
0x180003d7e  call    cs:__imp_wcscpy_s
0x180003d84  test    eax, eax
0x180003d86  jnz     short loc_180003DA0
0x180003d88  mov     rcx, [rsp+68h+hRequest]; hRequest
0x180003d8d  mov     r9d, 10000000h; dwModifiers
0x180003d93  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x180003d97  mov     rdx, rbx; lpszHeaders
0x180003d9a  call    cs:__imp_HttpAddRequestHeadersW
0x180003da0  mov     rcx, rbx; void *
0x180003da3  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003da8  jmp     loc_180003CE5
0x180003dad  mov     rdx, [rsi+rdi]; String1
0x180003db1  lea     r8, [rsp+68h+dwSize]; lpdwSize
0x180003db9  mov     rcx, r12; lpszUrl
0x180003dbc  call    ?ShouldSetDeviceCookie@ProofOfPossessionTokenProvider@@YA_NPEBG0PEAK@Z; ProofOfPossessionTokenProvider::ShouldSetDeviceCookie(ushort const *,ushort const *,ulong *)
0x180003dc1  test    al, al
0x180003dc3  jz      loc_180003CEA
0x180003dc9  jmp     loc_180003C87
0x180003dce  mov     ebx, [rsi+rdi+10h]
0x180003dd2  call    ?IsEdgeCookiesFeatureEnabled@ProofOfPossessionTokenProvider@@YA_NXZ; ProofOfPossessionTokenProvider::IsEdgeCookiesFeatureEnabled(void)
0x180003dd7  mov     r8, [rsi+rdi+8]; lpszCookieData
0x180003ddc  mov     r9d, ebx
0x180003ddf  mov     rdx, [rsi+rdi]; lpszCookieName
0x180003de3  bts     r9d, 0Fh
0x180003de8  test    al, al
0x180003dea  mov     rcx, r12; lpszUrl
0x180003ded  mov     rax, [rsi+rdi+18h]
0x180003df2  cmovz   r9d, ebx; dwFlags
0x180003df6  mov     [rsp+68h+dwReserved], rax; dwReserved
0x180003dfb  call    cs:__imp_InternetSetCookieExW
0x180003e01  jmp     loc_180003CE5
```
