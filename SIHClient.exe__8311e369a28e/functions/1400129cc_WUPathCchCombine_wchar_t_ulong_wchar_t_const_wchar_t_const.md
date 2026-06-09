# WUPathCchCombine(wchar_t *,ulong,wchar_t const *,wchar_t const *)

- ea: `0x1400129cc`
- end: `0x140012c72`
- name: `?WUPathCchCombine@@YAJPEA_WKPEB_W1@Z`
- size: `678`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int, const wchar_t *, const wchar_t *)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400166c8`
- `0x140016c54`
- `0x14002f1bc`

## callees

- `0x140008de4`
- `0x14000d814`
- `0x14000db18`
- `0x14001259c`
- `0x140012930`
- `0x1400129cc`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x140012bac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x140012bac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x140012ac1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x140012ac1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x140012b6d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x140012b6d`

## string_xrefs

- `0x140012a06`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`
- `0x140012a8d`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`
- `0x140012afd`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WUPathCchCombine(wchar_t *a1, unsigned int a2, const wchar_t *a3, const wchar_t *a4)
{
  unsigned __int64 v4; // rbp
  int v8; // ebx
  __int64 v9; // rdx
  int v11; // edi
  __int64 v12; // rdx
  int v13; // esi
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-28h]
  int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a2;
  if ( !a1 )
  {
    v8 = -2147024809;
    v9 = 274;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
      (const char *)(unsigned int)v8,
      v15);
    return (unsigned int)v8;
  }
  if ( a3 )
  {
    if ( *a3 )
      goto LABEL_17;
    if ( !a4 )
    {
LABEL_16:
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
    goto LABEL_16;
  if ( !a3 || !*a3 )
  {
    v11 = StringCchCopyExW(a1, a2, a4, 0, 0, 0x1100u);
    if ( v11 < 0 )
    {
      v12 = 302;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
        (const char *)(unsigned int)v11,
        v15);
      return (unsigned int)v11;
    }
    goto LABEL_39;
  }
LABEL_17:
  if ( !a4 || !*a4 )
  {
    v11 = StringCchCopyExW(a1, a2, a3, 0, 0, 0x1100u);
    if ( v11 < 0 )
    {
      v12 = 309;
      goto LABEL_15;
    }
    goto LABEL_39;
  }
  if ( PathIsRelativeW(a4) )
  {
    v13 = StringCchCopyExW(a1, v4, a3, 0, 0, 0x1100u);
    if ( v13 >= 0 )
    {
      v13 = WUPathCchAddBackslash(a1, v4);
      if ( v13 >= 0 )
      {
        v11 = StringCchCatExW(a1, v4, a4, 0, 0, 0x1100u);
        if ( v11 < 0 )
        {
          v12 = 318;
          goto LABEL_15;
        }
LABEL_39:
        v8 = WUPathCchCanonicalize(a1, v4, a1);
        if ( v8 < 0 )
        {
          v9 = 346;
          goto LABEL_3;
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
        goto LABEL_15;
      }
      goto LABEL_39;
    }
    v13 = StringCchCopyExW(a1, v4, a3, 0, 0, 0x1100u);
    if ( v13 >= 0 )
    {
      PathStripToRootW(a1);
      v13 = WUPathCchAddBackslash(a1, v4);
      if ( v13 >= 0 )
      {
        v11 = StringCchCatExW(a1, v4, a4 + 1, 0, 0, 0x1100u);
        if ( v11 < 0 )
        {
          v12 = 335;
          goto LABEL_15;
        }
        goto LABEL_39;
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
    v16);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400129cc  mov     [rsp+arg_0], rbx
0x1400129d1  mov     [rsp+arg_8], rbp
0x1400129d6  mov     [rsp+arg_10], rsi
0x1400129db  push    rdi
0x1400129dc  push    r14
0x1400129de  push    r15
0x1400129e0  sub     rsp, 30h
0x1400129e4  xor     r15d, r15d
0x1400129e7  mov     ebp, edx
0x1400129e9  mov     rdi, r9
0x1400129ec  mov     rsi, r8
0x1400129ef  mov     rbx, rcx
0x1400129f2  test    rcx, rcx
0x1400129f5  jnz     short loc_140012A19
0x1400129f7  mov     ebx, 80070057h
0x1400129fc  mov     edx, 112h; void *
0x140012a01  mov     rcx, [rsp+48h]; this
0x140012a06  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x140012a0d  mov     r9d, ebx; char *
0x140012a10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012a15  mov     eax, ebx
0x140012a17  jmp     short loc_140012A29
0x140012a19  test    rsi, rsi
0x140012a1c  jnz     short loc_140012A42
0x140012a1e  test    rdi, rdi
0x140012a21  jnz     short loc_140012A4D
0x140012a23  mov     [rcx], r15w
0x140012a27  xor     eax, eax
0x140012a29  mov     rbx, [rsp+48h+arg_0]
0x140012a2e  mov     rbp, [rsp+48h+arg_8]
0x140012a33  mov     rsi, [rsp+48h+arg_10]
0x140012a38  add     rsp, 30h
0x140012a3c  pop     r15
0x140012a3e  pop     r14
0x140012a40  pop     rdi
0x140012a41  retn
0x140012a42  cmp     [r8], r15w
0x140012a46  jnz     short loc_140012AAB
0x140012a48  test    rdi, rdi
0x140012a4b  jz      short loc_140012AA0
0x140012a4d  cmp     [r9], r15w
0x140012a51  jz      short loc_140012AA0
0x140012a53  test    rsi, rsi
0x140012a56  jz      short loc_140012A5E
0x140012a58  cmp     [r8], r15w
0x140012a5c  jnz     short loc_140012AAB
0x140012a5e  mov     rdx, rbp; unsigned __int64
0x140012a61  mov     [rsp+48h+var_20], 1100h; unsigned int
0x140012a69  xor     r9d, r9d; wchar_t **
0x140012a6c  mov     [rsp+48h+var_28], r15; int
0x140012a71  mov     r8, rdi; wchar_t *
0x140012a74  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140012a79  mov     edi, eax
0x140012a7b  test    eax, eax
0x140012a7d  jns     loc_140012C51
0x140012a83  mov     edx, 12Eh; void *
0x140012a88  mov     rcx, [rsp+48h]; this
0x140012a8d  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x140012a94  mov     r9d, edi; char *
0x140012a97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012a9c  mov     eax, edi
0x140012a9e  jmp     short loc_140012A29
0x140012aa0  mov     dword ptr [rcx], 5Ch ; '\'
0x140012aa6  jmp     loc_140012A27
0x140012aab  test    rdi, rdi
0x140012aae  jz      loc_140012C29
0x140012ab4  cmp     [r9], r15w
0x140012ab8  jz      loc_140012C29
0x140012abe  mov     rcx, rdi; pszPath
0x140012ac1  call    cs:__imp_PathIsRelativeW
0x140012ac7  test    eax, eax
0x140012ac9  jz      loc_140012B5C
0x140012acf  mov     [rsp+48h+var_20], 1100h; unsigned int
0x140012ad7  xor     r9d, r9d; wchar_t **
0x140012ada  mov     r8, rsi; wchar_t *
0x140012add  mov     [rsp+48h+var_28], r15; int
0x140012ae2  mov     rdx, rbp; unsigned __int64
0x140012ae5  mov     rcx, rbx; pszDest
0x140012ae8  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140012aed  mov     esi, eax
0x140012aef  test    eax, eax
0x140012af1  jns     short loc_140012B13
0x140012af3  mov     edx, 13Ch; void *
0x140012af8  mov     rcx, [rsp+48h]; this
0x140012afd  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x140012b04  mov     r9d, esi; char *
0x140012b07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012b0c  mov     eax, esi
0x140012b0e  jmp     loc_140012A29
0x140012b13  mov     edx, ebp; unsigned int
0x140012b15  mov     rcx, rbx; wchar_t *
0x140012b18  call    ?WUPathCchAddBackslash@@YAJPEA_WK@Z; WUPathCchAddBackslash(wchar_t *,ulong)
0x140012b1d  mov     esi, eax
0x140012b1f  test    eax, eax
0x140012b21  jns     short loc_140012B2A
0x140012b23  mov     edx, 13Dh
0x140012b28  jmp     short loc_140012AF8
0x140012b2a  mov     [rsp+48h+var_20], 1100h; unsigned int
0x140012b32  xor     r9d, r9d; wchar_t **
0x140012b35  mov     r8, rdi; wchar_t *
0x140012b38  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x140012b3d  mov     rdx, rbp; unsigned __int64
0x140012b40  mov     rcx, rbx; pszDest
0x140012b43  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140012b48  mov     edi, eax
0x140012b4a  test    eax, eax
0x140012b4c  jns     loc_140012C51
0x140012b52  mov     edx, 13Eh
0x140012b57  jmp     loc_140012A88
0x140012b5c  mov     eax, 5Ch ; '\'
0x140012b61  cmp     [rdi], ax
0x140012b64  jnz     loc_140012BFB
0x140012b6a  mov     rcx, rdi; pszPath
0x140012b6d  call    cs:__imp_PathIsUNCW
0x140012b73  test    eax, eax
0x140012b75  jnz     loc_140012BFB
0x140012b7b  mov     [rsp+48h+var_20], 1100h; unsigned int
0x140012b83  xor     r9d, r9d; wchar_t **
0x140012b86  mov     r8, rsi; wchar_t *
0x140012b89  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x140012b8e  mov     rdx, rbp; unsigned __int64
0x140012b91  mov     rcx, rbx; pszDest
0x140012b94  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140012b99  mov     esi, eax
0x140012b9b  test    eax, eax
0x140012b9d  jns     short loc_140012BA9
0x140012b9f  mov     edx, 146h
0x140012ba4  jmp     loc_140012AF8
0x140012ba9  mov     rcx, rbx; pszPath
0x140012bac  call    cs:__imp_PathStripToRootW
0x140012bb2  mov     edx, ebp; unsigned int
0x140012bb4  mov     rcx, rbx; wchar_t *
0x140012bb7  call    ?WUPathCchAddBackslash@@YAJPEA_WK@Z; WUPathCchAddBackslash(wchar_t *,ulong)
0x140012bbc  mov     esi, eax
0x140012bbe  test    eax, eax
0x140012bc0  jns     short loc_140012BCC
0x140012bc2  mov     edx, 14Ch
0x140012bc7  jmp     loc_140012AF8
0x140012bcc  lea     r8, [rdi+2]; wchar_t *
0x140012bd0  mov     [rsp+48h+var_20], 1100h; unsigned int
0x140012bd8  xor     r9d, r9d; wchar_t **
0x140012bdb  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x140012be0  mov     rdx, rbp; unsigned __int64
0x140012be3  mov     rcx, rbx; pszDest
0x140012be6  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140012beb  mov     edi, eax
0x140012bed  test    eax, eax
0x140012bef  jns     short loc_140012C51
0x140012bf1  mov     edx, 14Fh
0x140012bf6  jmp     loc_140012A88
0x140012bfb  mov     rdx, rbp; unsigned __int64
0x140012bfe  mov     [rsp+48h+var_20], 1100h; unsigned int
0x140012c06  xor     r9d, r9d; wchar_t **
0x140012c09  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x140012c0e  mov     r8, rdi; wchar_t *
0x140012c11  mov     rcx, rbx; pszDest
0x140012c14  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140012c19  mov     edi, eax
0x140012c1b  test    eax, eax
0x140012c1d  jns     short loc_140012C51
0x140012c1f  mov     edx, 156h
0x140012c24  jmp     loc_140012A88
0x140012c29  mov     rdx, rbp; unsigned __int64
0x140012c2c  mov     [rsp+48h+var_20], 1100h; unsigned int
0x140012c34  xor     r9d, r9d; wchar_t **
0x140012c37  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x140012c3c  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140012c41  mov     edi, eax
0x140012c43  test    eax, eax
0x140012c45  jns     short loc_140012C51
0x140012c47  mov     edx, 135h
0x140012c4c  jmp     loc_140012A88
0x140012c51  mov     r8, rbx; wchar_t *
0x140012c54  mov     edx, ebp; unsigned int
0x140012c56  mov     rcx, rbx; wchar_t *
0x140012c59  call    ?WUPathCchCanonicalize@@YAJPEA_WKPEB_W@Z; WUPathCchCanonicalize(wchar_t *,ulong,wchar_t const *)
0x140012c5e  mov     ebx, eax
0x140012c60  test    eax, eax
0x140012c62  jns     loc_140012A27
0x140012c68  mov     edx, 15Ah
0x140012c6d  jmp     loc_140012A01
```
