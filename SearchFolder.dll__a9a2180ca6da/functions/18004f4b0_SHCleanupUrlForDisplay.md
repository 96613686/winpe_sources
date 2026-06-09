# SHCleanupUrlForDisplay

- ea: `0x18004f4b0`
- end: `0x18004f64a`
- name: `SHCleanupUrlForDisplay`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004f1c8`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x18000ecc4`
- `0x18004f4b0`
- `0x18004faa0`

## import_xrefs

- `SHLWAPI!StrPBrkW` at `0x18004f5dd`
- `SHLWAPI!StrPBrkW` at `0x18004f5dd`
- `SHLWAPI!__imp_ParseURLW` at `0x18004f50a`
- `SHLWAPI!__imp_ParseURLW` at `0x18004f50a`
- `WININET!InternetCrackUrlW` at `0x18004f5ad`
- `WININET!InternetCrackUrlW` at `0x18004f5ad`
- `WININET!InternetCreateUrlW` at `0x18004f5ff`
- `WININET!InternetCreateUrlW` at `0x18004f5ff`

## pseudocode

```c
__int64 __fastcall SHCleanupUrlForDisplay(unsigned __int16 *a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned __int64 v3; // rsi
  PWSTR v5; // rax
  DWORD dwUrlLength[4]; // [rsp+20h] [rbp-E0h] BYREF
  $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+30h] [rbp-D0h] BYREF
  PARSEDURLW ppu; // [rsp+A0h] [rbp-60h] BYREF
  char v10; // [rsp+E0h] [rbp-20h] BYREF
  char v11; // [rsp+1E0h] [rbp+E0h] BYREF
  char v12; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v13; // [rsp+4E0h] [rbp+3E0h] BYREF
  WCHAR szUrl[2088]; // [rsp+14E0h] [rbp+13E0h] BYREF

  v2 = 0;
  v3 = a2;
  if ( a1 )
  {
    memset(&ppu, 0, sizeof(ppu));
    ppu.cbSize = 40;
    if ( ParseURLW(a1, &ppu) >= 0 && (ppu.nScheme == 1 || ppu.nScheme == 2 || ppu.nScheme == 11) )
    {
      memset_0(&UrlComponents, 0, sizeof(UrlComponents));
      UrlComponents.dwStructSize = 104;
      UrlComponents.lpszUserName = (LPWSTR)&v10;
      UrlComponents.dwSchemeLength = 32;
      UrlComponents.lpszPassword = (LPWSTR)&v11;
      UrlComponents.dwHostNameLength = 256;
      UrlComponents.lpszHostName = (LPWSTR)&v12;
      UrlComponents.dwUrlPathLength = 2048;
      UrlComponents.lpszScheme = (LPWSTR)&ppu;
      UrlComponents.lpszUrlPath = (LPWSTR)&v13;
      UrlComponents.dwUserNameLength = 128;
      UrlComponents.dwPasswordLength = 128;
      if ( InternetCrackUrlW(a1, 0, 0, &UrlComponents) )
      {
        UrlComponents.dwUserNameLength = 0;
        UrlComponents.dwPasswordLength = 0;
        UrlComponents.lpszPassword = 0;
        UrlComponents.lpszUserName = 0;
        dwUrlLength[0] = 2084;
        v5 = StrPBrkW(UrlComponents.lpszHostName, &word_18005E040);
        if ( InternetCreateUrlW(&UrlComponents, v5 != 0 ? 0x2000 : 0, szUrl, dwUrlLength) )
        {
          if ( (unsigned int)v3 > dwUrlLength[0] )
          {
            StringCchCopyW(a1, v3, szUrl);
            return 1;
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18004f4b0  mov     [rsp-8+arg_10], rbx
0x18004f4b5  push    rbp
0x18004f4b6  push    rsi
0x18004f4b7  push    rdi
0x18004f4b8  lea     rbp, [rsp-2440h]
0x18004f4c0  mov     eax, 2540h
0x18004f4c5  call    _alloca_probe
0x18004f4ca  sub     rsp, rax
0x18004f4cd  mov     rax, cs:__security_cookie
0x18004f4d4  xor     rax, rsp
0x18004f4d7  mov     [rbp+2450h+var_20], rax
0x18004f4de  xor     edi, edi
0x18004f4e0  mov     esi, edx
0x18004f4e2  mov     rbx, rcx
0x18004f4e5  test    rcx, rcx
0x18004f4e8  jz      loc_18004F626
0x18004f4ee  xorps   xmm0, xmm0
0x18004f4f1  lea     rdx, [rbp+2450h+ppu]; ppu
0x18004f4f5  xor     eax, eax
0x18004f4f7  movups  xmmword ptr [rbp+2450h+ppu.cbSize], xmm0
0x18004f4fb  mov     [rbp+2450h+ppu.cbSize], 28h ; '('
0x18004f502  movups  xmmword ptr [rbp+2450h+ppu.cchProtocol], xmm0
0x18004f506  mov     qword ptr [rbp+2450h+ppu.cchSuffix], rax
0x18004f50a  call    cs:__imp_ParseURLW
0x18004f510  test    eax, eax
0x18004f512  js      loc_18004F626
0x18004f518  mov     eax, [rbp+2450h+ppu.nScheme]
0x18004f51b  sub     eax, 1
0x18004f51e  jz      short loc_18004F52E
0x18004f520  sub     eax, 1
0x18004f523  jz      short loc_18004F52E
0x18004f525  cmp     eax, 9
0x18004f528  jnz     loc_18004F626
0x18004f52e  xor     edx, edx; Val
0x18004f530  lea     rcx, [rsp+2550h+UrlComponents]; void *
0x18004f535  lea     r8d, [rdx+68h]; Size
0x18004f539  call    memset_0
0x18004f53e  lea     rax, [rbp+2450h+var_2470]
0x18004f542  mov     [rsp+2550h+UrlComponents.dwStructSize], 68h ; 'h'
0x18004f54a  mov     [rsp+2550h+UrlComponents.lpszUserName], rax
0x18004f54f  lea     r9, [rsp+2550h+UrlComponents]; lpUrlComponents
0x18004f554  lea     rax, [rbp+2450h+var_2370]
0x18004f55b  mov     [rsp+2550h+UrlComponents.dwSchemeLength], 20h ; ' '
0x18004f563  mov     [rsp+2550h+UrlComponents.lpszPassword], rax
0x18004f568  xor     r8d, r8d; dwFlags
0x18004f56b  lea     rax, [rbp+2450h+var_2270]
0x18004f572  mov     [rsp+2550h+UrlComponents.dwHostNameLength], 100h
0x18004f57a  mov     [rsp+2550h+UrlComponents.lpszHostName], rax
0x18004f57f  xor     edx, edx; dwUrlLength
0x18004f581  lea     rax, [rbp+2450h+ppu]
0x18004f585  mov     [rbp+2450h+UrlComponents.dwUrlPathLength], 800h
0x18004f58c  mov     [rsp+2550h+UrlComponents.lpszScheme], rax
0x18004f591  mov     rcx, rbx; lpszUrl
0x18004f594  lea     rax, [rbp+2450h+var_2070]
0x18004f59b  mov     [rsp+2550h+UrlComponents.lpszUrlPath], rax
0x18004f5a0  mov     eax, 80h
0x18004f5a5  mov     [rsp+2550h+UrlComponents.dwUserNameLength], eax
0x18004f5a9  mov     [rsp+2550h+UrlComponents.dwPasswordLength], eax
0x18004f5ad  call    cs:__imp_InternetCrackUrlW
0x18004f5b3  test    eax, eax
0x18004f5b5  jz      short loc_18004F626
0x18004f5b7  mov     rcx, [rsp+2550h+UrlComponents.lpszHostName]; psz
0x18004f5bc  lea     rdx, word_18005E040; pszSet
0x18004f5c3  mov     [rsp+2550h+UrlComponents.dwUserNameLength], edi
0x18004f5c7  mov     [rsp+2550h+UrlComponents.dwPasswordLength], edi
0x18004f5cb  mov     [rsp+2550h+UrlComponents.lpszPassword], rdi
0x18004f5d0  mov     [rsp+2550h+UrlComponents.lpszUserName], rdi
0x18004f5d5  mov     [rsp+2550h+dwUrlLength], 824h
0x18004f5dd  call    cs:__imp_StrPBrkW
0x18004f5e3  neg     rax
0x18004f5e6  lea     r9, [rsp+2550h+dwUrlLength]; lpdwUrlLength
0x18004f5eb  lea     r8, [rbp+2450h+szUrl]; lpszUrl
0x18004f5f2  sbb     edx, edx
0x18004f5f4  lea     rcx, [rsp+2550h+UrlComponents]; lpUrlComponents
0x18004f5f9  and     edx, 2000h; dwFlags
0x18004f5ff  call    cs:__imp_InternetCreateUrlW
0x18004f605  test    eax, eax
0x18004f607  jz      short loc_18004F626
0x18004f609  cmp     esi, [rsp+2550h+dwUrlLength]
0x18004f60d  jbe     short loc_18004F626
0x18004f60f  mov     rdx, rsi; unsigned __int64
0x18004f612  lea     r8, [rbp+2450h+szUrl]; unsigned __int16 *
0x18004f619  mov     rcx, rbx; unsigned __int16 *
0x18004f61c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f621  mov     edi, 1
0x18004f626  mov     eax, edi
0x18004f628  mov     rcx, [rbp+2450h+var_20]
0x18004f62f  xor     rcx, rsp; StackCookie
0x18004f632  call    __security_check_cookie
0x18004f637  mov     rbx, [rsp+2550h+arg_10]
0x18004f63f  add     rsp, 2540h
0x18004f646  pop     rdi
0x18004f647  pop     rsi
0x18004f648  pop     rbp
0x18004f649  retn
```
