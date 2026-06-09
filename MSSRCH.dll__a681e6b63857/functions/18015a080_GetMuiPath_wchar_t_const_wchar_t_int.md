# GetMuiPath(wchar_t const *,wchar_t *,int)

- ea: `0x18015a080`
- end: `0x18015a262`
- name: `?GetMuiPath@@YAJPEB_WPEA_WH@Z`
- size: `482`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18015a268`

## callees

- `0x180082390`
- `0x18009491c`
- `0x1801244c0`
- `0x18012540e`
- `0x18015a080`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18015a1b1`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18015a1b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18015a151`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18015a151`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18015a199`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18015a199`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18015a101`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18015a101`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18015a1de`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18015a1f3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18015a1de`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18015a1f3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18015a17f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18015a17f`

## pseudocode

```c
__int64 __fastcall GetMuiPath(const wchar_t *a1, wchar_t *a2)
{
  int v4; // ebx
  const wchar_t *FileNameW; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  LANGID UserDefaultUILanguage; // ax
  WCHAR LCData[88]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszPath[264]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t pszMore[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  memset_0(pszPath, 0, 0x208u);
  if ( a2 && a1 )
  {
    v4 = StringCchCopyW(pszPath, 0x104u, a1);
    if ( v4 >= 0 )
    {
      FileNameW = PathFindFileNameW(pszPath);
      v4 = StringCchCopyW(pszMore, 0x104u, FileNameW);
      if ( v4 >= 0 )
      {
        v6 = -1;
        v7 = -1;
        do
          ++v7;
        while ( pszMore[v7] );
        if ( (int)v7 < 4
          || lstrcmpiW(&pszPath[(int)v7 + 260], L".dll")
          || (v4 = StringCchCatW(pszMore, 0x104u, L".mui"), v4 >= 0) )
        {
          if ( !PathRemoveFileSpecW(pszPath) )
            v4 = -2147467259;
          if ( v4 >= 0 )
          {
            UserDefaultUILanguage = GetUserDefaultUILanguage();
            if ( GetLocaleInfoW(UserDefaultUILanguage, 0x5Cu, LCData, 85)
              || (v4 = StringCchCopyW(LCData, 0x55u, L"en-us"), v4 >= 0) )
            {
              if ( PathAppendW(pszPath, LCData) && PathAppendW(pszPath, pszMore) )
              {
                do
                  ++v6;
                while ( pszPath[v6] );
                if ( (int)v6 + 1 <= 260 )
                  StringCchCopyW(a2, 0x104u, pszPath);
                else
                  return (unsigned int)-2147024662;
              }
              else
              {
                return (unsigned int)-2147467259;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18015a080  mov     [rsp-8+arg_10], rbx
0x18015a085  mov     [rsp-8+arg_18], rsi
0x18015a08a  push    rbp
0x18015a08b  push    rdi
0x18015a08c  push    r12
0x18015a08e  push    r14
0x18015a090  push    r15
0x18015a092  lea     rbp, [rsp-400h]
0x18015a09a  sub     rsp, 500h
0x18015a0a1  mov     rax, cs:__security_cookie
0x18015a0a8  xor     rax, rsp
0x18015a0ab  mov     [rbp+420h+var_30], rax
0x18015a0b2  mov     rsi, rdx
0x18015a0b5  mov     rbx, rcx
0x18015a0b8  xor     edx, edx; Val
0x18015a0ba  lea     rcx, [rbp+420h+pszPath]; void *
0x18015a0be  mov     r8d, 208h; Size
0x18015a0c4  call    memset_0
0x18015a0c9  xor     r14d, r14d
0x18015a0cc  test    rsi, rsi
0x18015a0cf  jz      loc_18015A230
0x18015a0d5  test    rbx, rbx
0x18015a0d8  jz      loc_18015A230
0x18015a0de  mov     r12d, 104h
0x18015a0e4  lea     rcx, [rbp+420h+pszPath]; wchar_t *
0x18015a0e8  mov     edx, r12d; unsigned __int64
0x18015a0eb  mov     r8, rbx; wchar_t *
0x18015a0ee  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18015a0f3  mov     ebx, eax
0x18015a0f5  test    eax, eax
0x18015a0f7  js      loc_18015A235
0x18015a0fd  lea     rcx, [rbp+420h+pszPath]; pszPath
0x18015a101  call    cs:__imp_PathFindFileNameW
0x18015a107  mov     edx, r12d; unsigned __int64
0x18015a10a  lea     rcx, [rbp+420h+pszMore]; wchar_t *
0x18015a111  mov     r8, rax; wchar_t *
0x18015a114  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18015a119  mov     ebx, eax
0x18015a11b  test    eax, eax
0x18015a11d  js      loc_18015A235
0x18015a123  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18015a127  lea     rcx, [rbp+420h+pszMore]
0x18015a12e  mov     rax, rdi
0x18015a131  inc     rax
0x18015a134  cmp     [rcx+rax*2], r14w
0x18015a139  jnz     short loc_18015A131
0x18015a13b  cmp     eax, 4
0x18015a13e  jl      short loc_18015A17B
0x18015a140  cdqe
0x18015a142  lea     rdx, aDll_0; ".dll"
0x18015a149  lea     rcx, [rbp+rax*2+420h+String1]; lpString1
0x18015a151  call    cs:__imp_lstrcmpiW
0x18015a157  test    eax, eax
0x18015a159  jnz     short loc_18015A17B
0x18015a15b  lea     r8, aMui; ".mui"
0x18015a162  mov     rdx, r12; unsigned __int64
0x18015a165  lea     rcx, [rbp+420h+pszMore]; wchar_t *
0x18015a16c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18015a171  mov     ebx, eax
0x18015a173  test    eax, eax
0x18015a175  js      loc_18015A235
0x18015a17b  lea     rcx, [rbp+420h+pszPath]; pszPath
0x18015a17f  call    cs:__imp_PathRemoveFileSpecW
0x18015a185  test    eax, eax
0x18015a187  mov     r15d, 80004005h
0x18015a18d  cmovz   ebx, r15d
0x18015a191  test    ebx, ebx
0x18015a193  js      loc_18015A235
0x18015a199  call    cs:__imp_GetUserDefaultUILanguage
0x18015a19f  mov     r9d, 55h ; 'U'; cchData
0x18015a1a5  movzx   ecx, ax; Locale
0x18015a1a8  lea     r8, [rsp+520h+LCData]; lpLCData
0x18015a1ad  lea     edx, [r9+7]; LCType
0x18015a1b1  call    cs:__imp_GetLocaleInfoW
0x18015a1b7  test    eax, eax
0x18015a1b9  jnz     short loc_18015A1D5
0x18015a1bb  lea     r8, aEnUs; "en-us"
0x18015a1c2  lea     edx, [rax+55h]; unsigned __int64
0x18015a1c5  lea     rcx, [rsp+520h+LCData]; wchar_t *
0x18015a1ca  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18015a1cf  mov     ebx, eax
0x18015a1d1  test    eax, eax
0x18015a1d3  js      short loc_18015A235
0x18015a1d5  lea     rdx, [rsp+520h+LCData]; pszMore
0x18015a1da  lea     rcx, [rbp+420h+pszPath]; pszPath
0x18015a1de  call    cs:__imp_PathAppendW
0x18015a1e4  test    eax, eax
0x18015a1e6  jz      short loc_18015A1FD
0x18015a1e8  lea     rdx, [rbp+420h+pszMore]; pszMore
0x18015a1ef  lea     rcx, [rbp+420h+pszPath]; pszPath
0x18015a1f3  call    cs:__imp_PathAppendW
0x18015a1f9  test    eax, eax
0x18015a1fb  jnz     short loc_18015A202
0x18015a1fd  mov     ebx, r15d
0x18015a200  jmp     short loc_18015A235
0x18015a202  lea     rax, [rbp+420h+pszPath]
0x18015a206  inc     rdi
0x18015a209  cmp     [rax+rdi*2], r14w
0x18015a20e  jnz     short loc_18015A206
0x18015a210  lea     eax, [rdi+1]
0x18015a213  cmp     eax, r12d
0x18015a216  jle     short loc_18015A21F
0x18015a218  mov     ebx, 800700EAh
0x18015a21d  jmp     short loc_18015A235
0x18015a21f  lea     r8, [rbp+420h+pszPath]; wchar_t *
0x18015a223  mov     rdx, r12; unsigned __int64
0x18015a226  mov     rcx, rsi; wchar_t *
0x18015a229  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18015a22e  jmp     short loc_18015A235
0x18015a230  mov     ebx, 80004003h
0x18015a235  mov     eax, ebx
0x18015a237  mov     rcx, [rbp+420h+var_30]
0x18015a23e  xor     rcx, rsp; StackCookie
0x18015a241  call    __security_check_cookie
0x18015a246  lea     r11, [rsp+520h+var_20]
0x18015a24e  mov     rbx, [r11+40h]
0x18015a252  mov     rsi, [r11+48h]
0x18015a256  mov     rsp, r11
0x18015a259  pop     r15
0x18015a25b  pop     r14
0x18015a25d  pop     r12
0x18015a25f  pop     rdi
0x18015a260  pop     rbp
0x18015a261  retn
```
