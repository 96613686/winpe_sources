# I_BuildFileCacheQueryString(ushort *,ulong,char *,char *)

- ea: `0x18001cba0`
- end: `0x18001cd3c`
- name: `?I_BuildFileCacheQueryString@@YAKPEAGKPEAD1@Z`
- size: `412`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, char *, char *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001dd04`
- `0x18001e66c`
- `0x18001ebf4`

## callees

- `0x18000de80`
- `0x180019430`
- `0x18001c71c`
- `0x18001cba0`
- `0x18001d3c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccf5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cbfa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cc3d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cca8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cceb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cbfa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cc3d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cca8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001cceb`

## string_xrefs

- `0x18001cbbd`: `Cached_GeneralFile`

## pseudocode

```c
__int64 __fastcall I_BuildFileCacheQueryString(unsigned __int16 *a1, __int64 a2, char *a3, char *a4)
{
  unsigned int v7; // eax
  int cchWideChar; // ebx
  WCHAR *v9; // rdi
  DWORD LastError; // ebx
  WCHAR *lpWideCharStr; // rax
  __int64 v12; // rax
  unsigned int v13; // eax
  int v14; // ebx
  unsigned __int64 v15; // rdx
  WCHAR *v16; // rax
  const unsigned __int16 *v17; // rdi

  StringCbPrintfW(a1, 0x104u, L"%s/", L"Cached_GeneralFile");
  if ( a3 )
  {
    v7 = MultiByteToWideChar(0, 0, a3, -1, 0, 0);
    cchWideChar = v7;
    if ( v7 )
    {
      lpWideCharStr = (WCHAR *)MIDL_user_allocate(2LL * v7);
      v9 = lpWideCharStr;
      if ( !lpWideCharStr )
        return 8;
      if ( MultiByteToWideChar(0, 0, a3, -1, lpWideCharStr, cchWideChar) )
        goto LABEL_8;
      LastError = GetLastError();
      CspFreeH(v9);
      v9 = 0;
    }
    else
    {
      v9 = 0;
      LastError = GetLastError();
    }
    if ( LastError )
      return LastError;
LABEL_8:
    v12 = -1;
    do
      ++v12;
    while ( a1[v12] );
    StringCbPrintfW(&a1[v12], 260 - 2 * v12, L"%s/", v9);
    CspFreeH(v9);
  }
  v13 = MultiByteToWideChar(0, 0, a4, -1, 0, 0);
  v14 = v13;
  if ( !v13 )
  {
    LastError = GetLastError();
    goto LABEL_17;
  }
  v16 = (WCHAR *)MIDL_user_allocate(2LL * v13);
  v17 = v16;
  if ( !v16 )
    return 8;
  if ( !MultiByteToWideChar(0, 0, a4, -1, v16, v14) )
  {
    LastError = GetLastError();
    CspFreeH(v17);
LABEL_17:
    v17 = 0;
    if ( LastError )
      return LastError;
    goto LABEL_20;
  }
  LastError = 0;
LABEL_20:
  StringCbCatW(a1, v15, v17);
  if ( v17 )
    CspFreeH(v17);
  return LastError;
}

```

## disassembly

```asm
0x18001cba0  push    rbx
0x18001cba2  push    rbp
0x18001cba3  push    rsi
0x18001cba4  push    rdi
0x18001cba5  push    r12
0x18001cba7  push    r13
0x18001cba9  push    r14
0x18001cbab  push    r15
0x18001cbad  sub     rsp, 38h
0x18001cbb1  mov     r15, r9
0x18001cbb4  mov     rsi, r8
0x18001cbb7  mov     r14d, 104h
0x18001cbbd  lea     r9, aCachedGeneralf; "Cached_GeneralFile"
0x18001cbc4  mov     edx, r14d; cbDest
0x18001cbc7  lea     r8, aS_0; "%s/"
0x18001cbce  mov     rbp, rcx
0x18001cbd1  call    StringCbPrintfW
0x18001cbd6  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001cbda  xor     r12d, r12d
0x18001cbdd  test    rsi, rsi
0x18001cbe0  jz      loc_18001CC94
0x18001cbe6  mov     [rsp+78h+cchWideChar], r12d; cchWideChar
0x18001cbeb  mov     r9d, r13d; cbMultiByte
0x18001cbee  mov     r8, rsi; lpMultiByteStr
0x18001cbf1  mov     [rsp+78h+lpWideCharStr], r12; lpWideCharStr
0x18001cbf6  xor     edx, edx; dwFlags
0x18001cbf8  xor     ecx, ecx; CodePage
0x18001cbfa  call    cs:__imp_MultiByteToWideChar
0x18001cc00  mov     ebx, eax
0x18001cc02  test    eax, eax
0x18001cc04  jnz     short loc_18001CC13
0x18001cc06  mov     edi, r12d
0x18001cc09  call    cs:__imp_GetLastError
0x18001cc0f  mov     ebx, eax
0x18001cc11  jmp     short loc_18001CC5A
0x18001cc13  mov     rcx, rbx
0x18001cc16  add     rcx, rcx; size
0x18001cc19  call    MIDL_user_allocate
0x18001cc1e  mov     rdi, rax
0x18001cc21  test    rax, rax
0x18001cc24  jz      loc_18001CCD1
0x18001cc2a  mov     [rsp+78h+cchWideChar], ebx; cchWideChar
0x18001cc2e  mov     r9d, r13d; cbMultiByte
0x18001cc31  mov     r8, rsi; lpMultiByteStr
0x18001cc34  mov     [rsp+78h+lpWideCharStr], rax; lpWideCharStr
0x18001cc39  xor     edx, edx; dwFlags
0x18001cc3b  xor     ecx, ecx; CodePage
0x18001cc3d  call    cs:__imp_MultiByteToWideChar
0x18001cc43  test    eax, eax
0x18001cc45  jnz     short loc_18001CC62
0x18001cc47  call    cs:__imp_GetLastError
0x18001cc4d  mov     rcx, rdi
0x18001cc50  mov     ebx, eax
0x18001cc52  call    CspFreeH
0x18001cc57  mov     rdi, r12
0x18001cc5a  test    ebx, ebx
0x18001cc5c  jnz     loc_18001CD29
0x18001cc62  mov     rax, r13
0x18001cc65  inc     rax
0x18001cc68  cmp     [rbp+rax*2+0], r12w
0x18001cc6e  jnz     short loc_18001CC65
0x18001cc70  add     rax, rax
0x18001cc73  lea     r8, aS_0; "%s/"
0x18001cc7a  sub     r14, rax
0x18001cc7d  mov     r9, rdi
0x18001cc80  mov     rdx, r14; cbDest
0x18001cc83  lea     rcx, [rax+rbp]; pszDest
0x18001cc87  call    StringCbPrintfW
0x18001cc8c  mov     rcx, rdi
0x18001cc8f  call    CspFreeH
0x18001cc94  mov     [rsp+78h+cchWideChar], r12d; cchWideChar
0x18001cc99  mov     r9d, r13d; cbMultiByte
0x18001cc9c  mov     r8, r15; lpMultiByteStr
0x18001cc9f  mov     [rsp+78h+lpWideCharStr], r12; lpWideCharStr
0x18001cca4  xor     edx, edx; dwFlags
0x18001cca6  xor     ecx, ecx; CodePage
0x18001cca8  call    cs:__imp_MultiByteToWideChar
0x18001ccae  mov     ebx, eax
0x18001ccb0  test    eax, eax
0x18001ccb2  jnz     short loc_18001CCBE
0x18001ccb4  call    cs:__imp_GetLastError
0x18001ccba  mov     ebx, eax
0x18001ccbc  jmp     short loc_18001CD05
0x18001ccbe  mov     rcx, rbx
0x18001ccc1  add     rcx, rcx; size
0x18001ccc4  call    MIDL_user_allocate
0x18001ccc9  mov     rdi, rax
0x18001cccc  test    rax, rax
0x18001cccf  jnz     short loc_18001CCD8
0x18001ccd1  mov     ebx, 8
0x18001ccd6  jmp     short loc_18001CD29
0x18001ccd8  mov     [rsp+78h+cchWideChar], ebx; cchWideChar
0x18001ccdc  mov     r9d, r13d; cbMultiByte
0x18001ccdf  mov     r8, r15; lpMultiByteStr
0x18001cce2  mov     [rsp+78h+lpWideCharStr], rdi; lpWideCharStr
0x18001cce7  xor     edx, edx; dwFlags
0x18001cce9  xor     ecx, ecx; CodePage
0x18001cceb  call    cs:__imp_MultiByteToWideChar
0x18001ccf1  test    eax, eax
0x18001ccf3  jnz     short loc_18001CD0E
0x18001ccf5  call    cs:__imp_GetLastError
0x18001ccfb  mov     rcx, rdi
0x18001ccfe  mov     ebx, eax
0x18001cd00  call    CspFreeH
0x18001cd05  mov     rdi, r12
0x18001cd08  test    ebx, ebx
0x18001cd0a  jnz     short loc_18001CD29
0x18001cd0c  jmp     short loc_18001CD11
0x18001cd0e  mov     ebx, r12d
0x18001cd11  mov     r8, rdi; unsigned __int16 *
0x18001cd14  mov     rcx, rbp; unsigned __int16 *
0x18001cd17  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18001cd1c  test    rdi, rdi
0x18001cd1f  jz      short loc_18001CD29
0x18001cd21  mov     rcx, rdi
0x18001cd24  call    CspFreeH
0x18001cd29  mov     eax, ebx
0x18001cd2b  add     rsp, 38h
0x18001cd2f  pop     r15
0x18001cd31  pop     r14
0x18001cd33  pop     r13
0x18001cd35  pop     r12
0x18001cd37  pop     rdi
0x18001cd38  pop     rsi
0x18001cd39  pop     rbp
0x18001cd3a  pop     rbx
0x18001cd3b  retn
```
