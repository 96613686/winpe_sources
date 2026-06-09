# PriHelper::FormulateResourceFilePath(ushort const *,ushort const *,ushort * *)

- ea: `0x18008b938`
- end: `0x18008bc66`
- name: `?FormulateResourceFilePath@PriHelper@@AEAAJPEBG0PEAPEAG@Z`
- size: `814`
- prototype: `__int64 __fastcall(PriHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18008bddc`

## callees

- `0x1800049a0`
- `0x180004ec0`
- `0x180005858`
- `0x180009634`
- `0x18000a0f8`
- `0x18000c964`
- `0x18000d3b4`
- `0x18000d478`
- `0x18000d4ec`
- `0x18000e4e4`
- `0x18008b938`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008ba41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008ba41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008bb24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008bb24`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18008ba67`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18008ba67`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18008ba1a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18008bae8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18008ba1a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18008bae8`

## string_xrefs

- `0x18008b9fa`: `onecoreuap\base\mrt\runtime\com\prihelper\lib\prihelper.cpp`
- `0x18008bbf8`: `onecoreuap\base\mrt\runtime\com\prihelper\lib\prihelper.cpp`
- `0x18008bc0d`: `onecoreuap\base\mrt\runtime\com\prihelper\lib\prihelper.cpp`
- `0x18008bc26`: `onecoreuap\base\mrt\runtime\com\prihelper\lib\prihelper.cpp`
- `0x18008bc3f`: `onecoreuap\base\mrt\runtime\com\prihelper\lib\prihelper.cpp`
- `0x18008bc54`: `onecoreuap\base\mrt\runtime\com\prihelper\lib\prihelper.cpp`

## pseudocode

```c
__int64 __fastcall PriHelper::FormulateResourceFilePath(
        PriHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  __int64 result; // rax
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  wil::details *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  WCHAR *v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // rbx
  unsigned __int16 *v19; // rax
  const char *v20; // r9
  int v21; // [rsp+20h] [rbp-E0h]
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[528]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+460h] [rbp+360h] BYREF
  WCHAR Filename[520]; // [rsp+670h] [rbp+570h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+AB8h] [rbp+9B8h]

  memset_0(Filename, 0, sizeof(Filename));
  memset_0(pszPath, 0, 0x41Au);
  FilePart = 0;
  if ( !a4 )
    return 2147942487LL;
  if ( a2 && *a2 )
  {
    v7 = StringCchPrintfW(pszPath, 0x20Du, L"%s\\%s%s", a2);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\prihelper\\lib\\prihelper.cpp",
        (const char *)(unsigned int)v7,
        (int)L"Windows-NFC-SEManagement");
      return v8;
    }
LABEL_7:
    if ( !PathFileExistsW(pszPath) )
      return 2147942402LL;
    goto LABEL_21;
  }
  if ( !GetModuleFileNameW(0, Filename, 0x208u) || !GetFullPathNameW(Filename, 0x20Du, pszPath, &FilePart) )
    return wil::details::GetLastErrorFailHr(v10);
  v11 = -1;
  do
    ++v11;
  while ( FilePart[v11] );
  v12 = -1;
  do
    ++v12;
  while ( pszPath[v12] );
  v13 = StringCchCopyW(FilePart, v11 - v12 + 525, L"Windows-NFC-SEManagement");
  if ( v13 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\prihelper\\lib\\prihelper.cpp",
      (const char *)(unsigned int)v13,
      v21);
  v14 = StringCchCatW(pszPath, 0x20Du, L".pri");
  if ( v14 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\prihelper\\lib\\prihelper.cpp",
      (const char *)(unsigned int)v14,
      v21);
  if ( !PathFileExistsW(pszPath) )
  {
    memset_0(pszPath, 0, 0x41Au);
    memset_0(Buffer, 0, 0x208u);
    if ( GetSystemDirectoryW(Buffer, 0x104u) )
    {
      v15 = StringCchPrintfW(pszPath, 0x20Du, L"%s\\%s%s", Buffer);
      if ( v15 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x12F,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\prihelper\\lib\\prihelper.cpp",
          (const char *)(unsigned int)v15,
          (int)L"Windows-NFC-SEManagement");
      goto LABEL_7;
    }
    return wil::details::GetLastErrorFailHr(v10);
  }
LABEL_21:
  v16 = pszPath;
  v17 = 0x7FFFFFFF;
  while ( *v16 )
  {
    ++v16;
    if ( !--v17 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x13D,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\prihelper\\lib\\prihelper.cpp",
        v9);
  }
  result = 0;
  if ( 0x7FFFFFFF != v17 )
  {
    v18 = 0x7FFFFFFF - v17 + 1;
    v19 = (unsigned __int16 *)operator new(saturated_mul(v18, 2u));
    *a4 = v19;
    result = StringCchCopyW(v19, v18, pszPath);
    if ( (int)result < 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\prihelper\\lib\\prihelper.cpp",
        v20);
  }
  return result;
}

```

## disassembly

```asm
0x18008b938  mov     [rsp-8+arg_0], rbx
0x18008b93d  mov     [rsp-8+arg_10], rsi
0x18008b942  push    rbp
0x18008b943  push    rdi
0x18008b944  push    r12
0x18008b946  push    r14
0x18008b948  push    r15
0x18008b94a  lea     rbp, [rsp-990h]
0x18008b952  sub     rsp, 0A90h
0x18008b959  mov     rax, cs:__security_cookie
0x18008b960  xor     rax, rsp
0x18008b963  mov     [rbp+9B0h+var_30], rax
0x18008b96a  mov     rbx, rdx
0x18008b96d  lea     rcx, [rbp+9B0h+Filename]; void *
0x18008b974  xor     edx, edx; Val
0x18008b976  mov     r8d, 410h; Size
0x18008b97c  mov     r14, r9
0x18008b97f  call    memset_0
0x18008b984  xor     edx, edx; Val
0x18008b986  lea     rcx, [rsp+0AB0h+pszPath]; void *
0x18008b98b  mov     r8d, 41Ah; Size
0x18008b991  call    memset_0
0x18008b996  xor     r15d, r15d
0x18008b999  mov     [rsp+0AB0h+FilePart], r15
0x18008b99e  test    r14, r14
0x18008b9a1  jnz     short loc_18008B9AD
0x18008b9a3  mov     eax, 80070057h
0x18008b9a8  jmp     loc_18008BBCA
0x18008b9ad  or      r12, 0FFFFFFFFFFFFFFFFh
0x18008b9b1  test    rbx, rbx
0x18008b9b4  jz      short loc_18008BA32
0x18008b9b6  cmp     [rbx], r15w
0x18008b9ba  jz      short loc_18008BA32
0x18008b9bc  lea     rdi, aPri; ".pri"
0x18008b9c3  mov     r9, rbx
0x18008b9c6  lea     rsi, aWindowsNfcSema; "Windows-NFC-SEManagement"
0x18008b9cd  mov     [rsp+0AB0h+var_A88], rdi
0x18008b9d2  lea     r8, aSSS; "%s\\%s%s"
0x18008b9d9  mov     qword ptr [rsp+0AB0h+var_A90], rsi; int
0x18008b9de  mov     edx, 20Dh; unsigned __int64
0x18008b9e3  lea     rcx, [rsp+0AB0h+pszPath]; unsigned __int16 *
0x18008b9e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008b9ed  mov     ebx, eax
0x18008b9ef  test    eax, eax
0x18008b9f1  jns     short loc_18008BA15
0x18008b9f3  mov     rcx, [rbp+9B8h]; this
0x18008b9fa  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\pr"...
0x18008ba01  mov     r9d, eax; char *
0x18008ba04  mov     edx, 10Fh; void *
0x18008ba09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ba0e  mov     eax, ebx
0x18008ba10  jmp     loc_18008BBCA
0x18008ba15  lea     rcx, [rsp+0AB0h+pszPath]; pszPath
0x18008ba1a  call    cs:__imp_PathFileExistsW
0x18008ba20  test    eax, eax
0x18008ba22  jnz     loc_18008BB6B
0x18008ba28  mov     eax, 80070002h
0x18008ba2d  jmp     loc_18008BBCA
0x18008ba32  mov     r8d, 208h; nSize
0x18008ba38  lea     rdx, [rbp+9B0h+Filename]; lpFilename
0x18008ba3f  xor     ecx, ecx; hModule
0x18008ba41  call    cs:__imp_GetModuleFileNameW
0x18008ba47  test    eax, eax
0x18008ba49  jz      loc_18008BBC5
0x18008ba4f  mov     ebx, 20Dh
0x18008ba54  lea     r9, [rsp+0AB0h+FilePart]; lpFilePart
0x18008ba59  mov     edx, ebx; nBufferLength
0x18008ba5b  lea     r8, [rsp+0AB0h+pszPath]; lpBuffer
0x18008ba60  lea     rcx, [rbp+9B0h+Filename]; lpFileName
0x18008ba67  call    cs:__imp_GetFullPathNameW
0x18008ba6d  test    eax, eax
0x18008ba6f  jz      loc_18008BBC5
0x18008ba75  mov     rcx, [rsp+0AB0h+FilePart]; unsigned __int16 *
0x18008ba7a  mov     rdx, r12
0x18008ba7d  inc     rdx
0x18008ba80  cmp     [rcx+rdx*2], r15w
0x18008ba85  jnz     short loc_18008BA7D
0x18008ba87  lea     r8, [rsp+0AB0h+pszPath]
0x18008ba8c  mov     rax, r12
0x18008ba8f  inc     rax
0x18008ba92  cmp     [r8+rax*2], r15w
0x18008ba97  jnz     short loc_18008BA8F
0x18008ba99  sub     rdx, rax
0x18008ba9c  lea     rsi, aWindowsNfcSema; "Windows-NFC-SEManagement"
0x18008baa3  add     rdx, rbx; unsigned __int64
0x18008baa6  mov     r8, rsi; unsigned __int16 *
0x18008baa9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008baae  mov     rcx, [rbp+9B8h]; this
0x18008bab5  test    eax, eax
0x18008bab7  js      loc_18008BC51
0x18008babd  lea     rdi, aPri; ".pri"
0x18008bac4  mov     rdx, rbx; unsigned __int64
0x18008bac7  mov     r8, rdi; unsigned __int16 *
0x18008baca  lea     rcx, [rsp+0AB0h+pszPath]; unsigned __int16 *
0x18008bacf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008bad4  mov     rcx, [rbp+9B8h]; this
0x18008badb  test    eax, eax
0x18008badd  js      loc_18008BBF5
0x18008bae3  lea     rcx, [rsp+0AB0h+pszPath]; pszPath
0x18008bae8  call    cs:__imp_PathFileExistsW
0x18008baee  test    eax, eax
0x18008baf0  jnz     short loc_18008BB6B
0x18008baf2  xor     edx, edx; Val
0x18008baf4  lea     rcx, [rsp+0AB0h+pszPath]; void *
0x18008baf9  mov     r8d, 41Ah; Size
0x18008baff  call    memset_0
0x18008bb04  xor     edx, edx; Val
0x18008bb06  lea     rcx, [rbp+9B0h+Buffer]; void *
0x18008bb0d  mov     r8d, 208h; Size
0x18008bb13  call    memset_0
0x18008bb18  mov     edx, 104h; uSize
0x18008bb1d  lea     rcx, [rbp+9B0h+Buffer]; lpBuffer
0x18008bb24  call    cs:__imp_GetSystemDirectoryW
0x18008bb2a  test    eax, eax
0x18008bb2c  jz      loc_18008BBC5
0x18008bb32  mov     [rsp+0AB0h+var_A88], rdi
0x18008bb37  lea     r9, [rbp+9B0h+Buffer]
0x18008bb3e  lea     r8, aSSS; "%s\\%s%s"
0x18008bb45  mov     qword ptr [rsp+0AB0h+var_A90], rsi; int
0x18008bb4a  mov     rdx, rbx; unsigned __int64
0x18008bb4d  lea     rcx, [rsp+0AB0h+pszPath]; unsigned __int16 *
0x18008bb52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008bb57  mov     rcx, [rbp+9B8h]; this
0x18008bb5e  test    eax, eax
0x18008bb60  js      loc_18008BC0A
0x18008bb66  jmp     loc_18008BA15
0x18008bb6b  mov     ebx, 7FFFFFFFh
0x18008bb70  lea     rax, [rsp+0AB0h+pszPath]
0x18008bb75  mov     ecx, ebx
0x18008bb77  cmp     [rax], r15w
0x18008bb7b  jz      short loc_18008BB8D
0x18008bb7d  add     rax, 2
0x18008bb81  sub     rcx, 1
0x18008bb85  jz      loc_18008BC1F
0x18008bb8b  jmp     short loc_18008BB77
0x18008bb8d  mov     eax, r15d
0x18008bb90  sub     rbx, rcx
0x18008bb93  jz      short loc_18008BBCA
0x18008bb95  inc     rbx
0x18008bb98  mov     eax, 2
0x18008bb9d  mul     rbx
0x18008bba0  cmovb   rax, r12
0x18008bba4  mov     rcx, rax; Size
0x18008bba7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008bbac  lea     r8, [rsp+0AB0h+pszPath]; unsigned __int16 *
0x18008bbb1  mov     [r14], rax
0x18008bbb4  mov     rdx, rbx; unsigned __int64
0x18008bbb7  mov     rcx, rax; unsigned __int16 *
0x18008bbba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008bbbf  test    eax, eax
0x18008bbc1  js      short loc_18008BC38
0x18008bbc3  jmp     short loc_18008BBCA
0x18008bbc5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18008bbca  mov     rcx, [rbp+9B0h+var_30]
0x18008bbd1  xor     rcx, rsp; StackCookie
0x18008bbd4  call    __security_check_cookie
0x18008bbd9  lea     r11, [rsp+0AB0h+var_20]
0x18008bbe1  mov     rbx, [r11+30h]
0x18008bbe5  mov     rsi, [r11+40h]
0x18008bbe9  mov     rsp, r11
0x18008bbec  pop     r15
0x18008bbee  pop     r14
0x18008bbf0  pop     r12
0x18008bbf2  pop     rdi
0x18008bbf3  pop     rbp
0x18008bbf4  retn
0x18008bbf5  mov     r9d, eax; char *
0x18008bbf8  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\pr"...
0x18008bbff  mov     edx, 127h; void *
0x18008bc04  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18008bc0a  mov     r9d, eax; char *
0x18008bc0d  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\pr"...
0x18008bc14  mov     edx, 12Fh; void *
0x18008bc19  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18008bc1f  mov     rcx, [rbp+9B8h]; this
0x18008bc26  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\pr"...
0x18008bc2d  mov     edx, 13Dh; void *
0x18008bc32  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18008bc38  mov     rcx, [rbp+9B8h]; this
0x18008bc3f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\pr"...
0x18008bc46  mov     edx, 146h; void *
0x18008bc4b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18008bc51  mov     r9d, eax; char *
0x18008bc54  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\pr"...
0x18008bc5b  mov     edx, 123h; void *
0x18008bc60  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
