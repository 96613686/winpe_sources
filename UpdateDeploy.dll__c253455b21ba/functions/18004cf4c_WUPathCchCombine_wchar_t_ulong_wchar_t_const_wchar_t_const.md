# WUPathCchCombine(wchar_t *,ulong,wchar_t const *,wchar_t const *)

- ea: `0x18004cf4c`
- end: `0x18004d1fd`
- name: `?WUPathCchCombine@@YAJPEA_WKPEB_W1@Z`
- size: `689`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int, const wchar_t *, const wchar_t *)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180049ff8`
- `0x18004d204`
- `0x18005936c`

## callees

- `0x180003180`
- `0x18000945c`
- `0x18000970c`
- `0x18004cb74`
- `0x18004ceb0`
- `0x18004cf4c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004d104`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004d104`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18004d060`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18004d060`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18004d13f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18004d13f`

## string_xrefs

- `0x18004cf86`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`
- `0x18004d018`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`
- `0x18004d09c`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`

## pseudocode

```c
__int64 __fastcall WUPathCchCombine(wchar_t *a1, unsigned int a2, const wchar_t *a3, const wchar_t *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v8; // rdx
  int v9; // ebx
  int v11; // edi
  __int64 v12; // rdx
  int v13; // ebp
  __int64 v14; // rdx
  wchar_t **v15; // r9
  wchar_t **v16; // r9
  int v17; // [rsp+20h] [rbp-28h]
  unsigned __int64 *v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a2;
  if ( !a1 )
  {
    v8 = 274;
LABEL_3:
    v9 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
      (const char *)(unsigned int)v9,
      v17);
    return (unsigned int)v9;
  }
  if ( !a2 )
  {
    v8 = 275;
    goto LABEL_3;
  }
  if ( a3 )
  {
    if ( *a3 )
      goto LABEL_22;
    if ( !a4 )
    {
LABEL_19:
      if ( a2 <= 1 )
      {
        v9 = -2147024774;
        v8 = 288;
        goto LABEL_4;
      }
      *(_DWORD *)a1 = 92;
      return 0;
    }
  }
  else if ( !a4 )
  {
    *a1 = 0;
    return 0;
  }
  if ( !*a4 )
    goto LABEL_19;
  if ( !a3 || !*a3 )
  {
    v11 = StringCchCopyExW(a1, a2, a4, 0, 0, 0x1100u);
    if ( v11 < 0 )
    {
      v12 = 302;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
        (const char *)(unsigned int)v11,
        v17);
      return (unsigned int)v11;
    }
    goto LABEL_44;
  }
LABEL_22:
  if ( !a4 || !*a4 )
  {
    v11 = StringCchCopyExW(a1, a2, a3, 0, 0, 0x1100u);
    if ( v11 < 0 )
    {
      v12 = 309;
      goto LABEL_18;
    }
    goto LABEL_44;
  }
  if ( PathIsRelativeW(a4) )
  {
    v13 = StringCchCopyExW(a1, v4, a3, 0, 0, 0x1100u);
    if ( v13 >= 0 )
    {
      v13 = WUPathCchAddBackslash(a1, v4);
      if ( v13 >= 0 )
      {
        v11 = StringCchCatExW(a1, v4, a4, v15, v18, 0x1100u);
        if ( v11 < 0 )
        {
          v12 = 318;
          goto LABEL_18;
        }
LABEL_44:
        v9 = WUPathCchCanonicalize(a1, v4, a1);
        if ( v9 < 0 )
        {
          v8 = 346;
          goto LABEL_4;
        }
        return 0;
      }
      v14 = 317;
    }
    else
    {
      v14 = 316;
    }
  }
  else
  {
    if ( *a4 != 92 || PathIsUNCW(a4) )
    {
      v11 = StringCchCopyExW(a1, v4, a4, 0, 0, 0x1100u);
      if ( v11 < 0 )
      {
        v12 = 342;
        goto LABEL_18;
      }
      goto LABEL_44;
    }
    v13 = StringCchCopyExW(a1, v4, a3, 0, 0, 0x1100u);
    if ( v13 >= 0 )
    {
      PathStripToRootW(a1);
      v13 = WUPathCchAddBackslash(a1, v4);
      if ( v13 >= 0 )
      {
        v11 = StringCchCatExW(a1, v4, a4 + 1, v16, v18, 0x1100u);
        if ( v11 < 0 )
        {
          v12 = 335;
          goto LABEL_18;
        }
        goto LABEL_44;
      }
      v14 = 332;
    }
    else
    {
      v14 = 326;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
    (const char *)(unsigned int)v13,
    (int)v18);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18004cf4c  mov     [rsp+arg_0], rbx
0x18004cf51  mov     [rsp+arg_8], rbp
0x18004cf56  mov     [rsp+arg_10], rsi
0x18004cf5b  push    rdi
0x18004cf5c  push    r14
0x18004cf5e  push    r15
0x18004cf60  sub     rsp, 30h
0x18004cf64  xor     r15d, r15d
0x18004cf67  mov     esi, edx
0x18004cf69  mov     rdi, r9
0x18004cf6c  mov     rbp, r8
0x18004cf6f  mov     rbx, rcx
0x18004cf72  test    rcx, rcx
0x18004cf75  jnz     short loc_18004CF99
0x18004cf77  mov     edx, 112h; void *
0x18004cf7c  mov     ebx, 80070057h
0x18004cf81  mov     rcx, [rsp+48h]; this
0x18004cf86  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18004cf8d  mov     r9d, ebx; char *
0x18004cf90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cf95  mov     eax, ebx
0x18004cf97  jmp     short loc_18004CFB4
0x18004cf99  test    edx, edx
0x18004cf9b  jnz     short loc_18004CFA4
0x18004cf9d  mov     edx, 113h
0x18004cfa2  jmp     short loc_18004CF7C
0x18004cfa4  test    rbp, rbp
0x18004cfa7  jnz     short loc_18004CFCD
0x18004cfa9  test    rdi, rdi
0x18004cfac  jnz     short loc_18004CFD8
0x18004cfae  mov     [rcx], r15w
0x18004cfb2  xor     eax, eax
0x18004cfb4  mov     rbx, [rsp+48h+arg_0]
0x18004cfb9  mov     rbp, [rsp+48h+arg_8]
0x18004cfbe  mov     rsi, [rsp+48h+arg_10]
0x18004cfc3  add     rsp, 30h
0x18004cfc7  pop     r15
0x18004cfc9  pop     r14
0x18004cfcb  pop     rdi
0x18004cfcc  retn
0x18004cfcd  cmp     [r8], r15w
0x18004cfd1  jnz     short loc_18004D04A
0x18004cfd3  test    rdi, rdi
0x18004cfd6  jz      short loc_18004D02B
0x18004cfd8  cmp     [r9], r15w
0x18004cfdc  jz      short loc_18004D02B
0x18004cfde  test    rbp, rbp
0x18004cfe1  jz      short loc_18004CFE9
0x18004cfe3  cmp     [r8], r15w
0x18004cfe7  jnz     short loc_18004D04A
0x18004cfe9  mov     rdx, rsi; unsigned __int64
0x18004cfec  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18004cff4  xor     r9d, r9d; wchar_t **
0x18004cff7  mov     [rsp+48h+var_28], r15; int
0x18004cffc  mov     r8, rdi; wchar_t *
0x18004cfff  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004d004  mov     edi, eax
0x18004d006  test    eax, eax
0x18004d008  jns     loc_18004D1DC
0x18004d00e  mov     edx, 12Eh; void *
0x18004d013  mov     rcx, [rsp+48h]; this
0x18004d018  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18004d01f  mov     r9d, edi; char *
0x18004d022  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d027  mov     eax, edi
0x18004d029  jmp     short loc_18004CFB4
0x18004d02b  cmp     esi, 1
0x18004d02e  ja      short loc_18004D03F
0x18004d030  mov     ebx, 8007007Ah
0x18004d035  mov     edx, 120h
0x18004d03a  jmp     loc_18004CF81
0x18004d03f  mov     dword ptr [rcx], 5Ch ; '\'
0x18004d045  jmp     loc_18004CFB2
0x18004d04a  test    rdi, rdi
0x18004d04d  jz      loc_18004D1B4
0x18004d053  cmp     [r9], r15w
0x18004d057  jz      loc_18004D1B4
0x18004d05d  mov     rcx, rdi; pszPath
0x18004d060  call    cs:__imp_PathIsRelativeW
0x18004d066  test    eax, eax
0x18004d068  jz      loc_18004D0F3
0x18004d06e  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18004d076  xor     r9d, r9d; wchar_t **
0x18004d079  mov     r8, rbp; wchar_t *
0x18004d07c  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x18004d081  mov     rdx, rsi; unsigned __int64
0x18004d084  mov     rcx, rbx; pszDest
0x18004d087  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004d08c  mov     ebp, eax
0x18004d08e  test    eax, eax
0x18004d090  jns     short loc_18004D0B2
0x18004d092  mov     edx, 13Ch; void *
0x18004d097  mov     rcx, [rsp+48h]; this
0x18004d09c  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18004d0a3  mov     r9d, ebp; char *
0x18004d0a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d0ab  mov     eax, ebp
0x18004d0ad  jmp     loc_18004CFB4
0x18004d0b2  mov     edx, esi; unsigned int
0x18004d0b4  mov     rcx, rbx; wchar_t *
0x18004d0b7  call    ?WUPathCchAddBackslash@@YAJPEA_WK@Z; WUPathCchAddBackslash(wchar_t *,ulong)
0x18004d0bc  mov     ebp, eax
0x18004d0be  test    eax, eax
0x18004d0c0  jns     short loc_18004D0C9
0x18004d0c2  mov     edx, 13Dh
0x18004d0c7  jmp     short loc_18004D097
0x18004d0c9  mov     r8, rdi; wchar_t *
0x18004d0cc  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18004d0d4  mov     rdx, rsi; unsigned __int64
0x18004d0d7  mov     rcx, rbx; pszDest
0x18004d0da  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004d0df  mov     edi, eax
0x18004d0e1  test    eax, eax
0x18004d0e3  jns     loc_18004D1DC
0x18004d0e9  mov     edx, 13Eh
0x18004d0ee  jmp     loc_18004D013
0x18004d0f3  mov     eax, 5Ch ; '\'
0x18004d0f8  cmp     [rdi], ax
0x18004d0fb  jnz     loc_18004D186
0x18004d101  mov     rcx, rdi; pszPath
0x18004d104  call    cs:__imp_PathIsUNCW
0x18004d10a  test    eax, eax
0x18004d10c  jnz     short loc_18004D186
0x18004d10e  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18004d116  xor     r9d, r9d; wchar_t **
0x18004d119  mov     r8, rbp; wchar_t *
0x18004d11c  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x18004d121  mov     rdx, rsi; unsigned __int64
0x18004d124  mov     rcx, rbx; pszDest
0x18004d127  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004d12c  mov     ebp, eax
0x18004d12e  test    eax, eax
0x18004d130  jns     short loc_18004D13C
0x18004d132  mov     edx, 146h
0x18004d137  jmp     loc_18004D097
0x18004d13c  mov     rcx, rbx; pszPath
0x18004d13f  call    cs:__imp_PathStripToRootW
0x18004d145  mov     edx, esi; unsigned int
0x18004d147  mov     rcx, rbx; wchar_t *
0x18004d14a  call    ?WUPathCchAddBackslash@@YAJPEA_WK@Z; WUPathCchAddBackslash(wchar_t *,ulong)
0x18004d14f  mov     ebp, eax
0x18004d151  test    eax, eax
0x18004d153  jns     short loc_18004D15F
0x18004d155  mov     edx, 14Ch
0x18004d15a  jmp     loc_18004D097
0x18004d15f  lea     r8, [rdi+2]; wchar_t *
0x18004d163  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18004d16b  mov     rdx, rsi; unsigned __int64
0x18004d16e  mov     rcx, rbx; pszDest
0x18004d171  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004d176  mov     edi, eax
0x18004d178  test    eax, eax
0x18004d17a  jns     short loc_18004D1DC
0x18004d17c  mov     edx, 14Fh
0x18004d181  jmp     loc_18004D013
0x18004d186  mov     rdx, rsi; unsigned __int64
0x18004d189  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18004d191  xor     r9d, r9d; wchar_t **
0x18004d194  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x18004d199  mov     r8, rdi; wchar_t *
0x18004d19c  mov     rcx, rbx; pszDest
0x18004d19f  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004d1a4  mov     edi, eax
0x18004d1a6  test    eax, eax
0x18004d1a8  jns     short loc_18004D1DC
0x18004d1aa  mov     edx, 156h
0x18004d1af  jmp     loc_18004D013
0x18004d1b4  mov     rdx, rsi; unsigned __int64
0x18004d1b7  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18004d1bf  xor     r9d, r9d; wchar_t **
0x18004d1c2  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x18004d1c7  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18004d1cc  mov     edi, eax
0x18004d1ce  test    eax, eax
0x18004d1d0  jns     short loc_18004D1DC
0x18004d1d2  mov     edx, 135h
0x18004d1d7  jmp     loc_18004D013
0x18004d1dc  mov     r8, rbx; wchar_t *
0x18004d1df  mov     edx, esi; unsigned int
0x18004d1e1  mov     rcx, rbx; wchar_t *
0x18004d1e4  call    ?WUPathCchCanonicalize@@YAJPEA_WKPEB_W@Z; WUPathCchCanonicalize(wchar_t *,ulong,wchar_t const *)
0x18004d1e9  mov     ebx, eax
0x18004d1eb  test    eax, eax
0x18004d1ed  jns     loc_18004CFB2
0x18004d1f3  mov     edx, 15Ah
0x18004d1f8  jmp     loc_18004CF81
```
