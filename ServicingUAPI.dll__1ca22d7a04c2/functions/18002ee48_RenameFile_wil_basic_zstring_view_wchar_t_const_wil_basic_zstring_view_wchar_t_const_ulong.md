# RenameFile(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong)

- ea: `0x18002ee48`
- end: `0x18002f253`
- name: `?RenameFile@@YAJAEBV?$basic_zstring_view@_W@wil@@0K@Z`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002f25c`

## callees

- `0x1800031d0`
- `0x180003b2a`
- `0x180003b66`
- `0x180003c64`
- `0x1800062b8`
- `0x18000636c`
- `0x18000693e`
- `0x180009750`
- `0x18000ba14`
- `0x18000ba40`
- `0x18002c4ec`
- `0x18002cdf8`
- `0x18002e6ac`
- `0x18002e70c`
- `0x18002ee48`

## import_xrefs

- `ntdll!NtClose` at `0x18002f0a1`
- `ntdll!NtClose` at `0x18002f11e`
- `ntdll!NtClose` at `0x18002f0a1`
- `ntdll!NtClose` at `0x18002f11e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002f1cf`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002f1cf`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002f0db`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002f0db`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002f18a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002f1a5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002f207`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002f18a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002f1a5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002f207`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002f168`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002f168`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ef06`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ef06`

## string_xrefs

- `0x18002f00d`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002f075`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002f0ef`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002f143`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002f1e3`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RenameFile(__int64 a1, __int64 a2)
{
  void **v3; // rax
  unsigned __int16 v4; // dx
  unsigned __int16 v5; // cx
  unsigned __int16 v6; // r8
  bool v7; // al
  const WCHAR *v8; // rcx
  char *FileW; // rax
  const char *v10; // r9
  char *v11; // rbx
  DWORD v12; // r13d
  _DWORD *v13; // rsi
  unsigned __int16 v14; // dx
  unsigned __int16 v15; // cx
  unsigned __int16 v16; // r8
  unsigned __int64 v17; // r14
  void **v18; // rdi
  void *v19; // rcx
  unsigned __int64 v20; // r15
  LPCWSTR *v21; // rax
  int v22; // eax
  unsigned int LastError; // edi
  bool v24; // cc
  unsigned __int64 v25; // rax
  FILE_INFO_BY_HANDLE_CLASS v26; // edx
  const char *v27; // r9
  DWORD FileAttributesW; // ebx
  const WCHAR *v29; // rcx
  void **v30; // rcx
  void **v31; // rdx
  const WCHAR *v32; // rcx
  const char *v33; // r9
  void **v34; // rcx
  DWORD dwCreationDisposition; // [rsp+28h] [rbp-69h]
  char v37[8]; // [rsp+48h] [rbp-49h] BYREF
  _DWORD *v38; // [rsp+50h] [rbp-41h]
  _QWORD v39[2]; // [rsp+58h] [rbp-39h] BYREF
  _QWORD v40[3]; // [rsp+68h] [rbp-29h] BYREF
  void *Src[2]; // [rsp+80h] [rbp-11h] BYREF
  __int64 v42; // [rsp+90h] [rbp-1h]
  unsigned __int64 v43; // [rsp+98h] [rbp+7h]
  LPCWSTR lpFileName[3]; // [rsp+A0h] [rbp+Fh] BYREF
  unsigned __int64 v45; // [rsp+B8h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v40[2] = -2;
  GetCanonicalUNCPath(lpFileName, a1);
  GetCanonicalUNCPath(Src, a2);
  v3 = Src;
  if ( v43 > 7 )
    v3 = (void **)Src[0];
  v39[0] = v3;
  v39[1] = v42;
  EnsurePathForFileExists(v39);
  v7 = IsWindowsVersionOrGreaterEx(v5, v4, v6, 0x383Au);
  v8 = (const WCHAR *)lpFileName;
  if ( !v7 )
  {
    if ( v45 > 7 )
      v8 = lpFileName[0];
    FileAttributesW = GetFileAttributesW(v8);
    v29 = (const WCHAR *)lpFileName;
    if ( v45 > 7 )
      v29 = lpFileName[0];
    SetFileAttributesW(v29, 0x80u);
    v30 = Src;
    if ( v43 > 7 )
      v30 = (void **)Src[0];
    SetFileAttributesW((LPCWSTR)v30, 0x80u);
    v31 = Src;
    if ( v43 > 7 )
      v31 = (void **)Src[0];
    v32 = (const WCHAR *)lpFileName;
    if ( v45 > 7 )
      v32 = lpFileName[0];
    if ( !MoveFileExW(v32, (LPCWSTR)v31, 1u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x919,
                    (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                    v33);
      goto LABEL_57;
    }
    v34 = Src;
    if ( v43 > 7 )
      v34 = (void **)Src[0];
    SetFileAttributesW((LPCWSTR)v34, FileAttributesW);
    goto LABEL_56;
  }
  if ( v45 > 7 )
    v8 = lpFileName[0];
  FileW = (char *)CreateFileW(v8, 0x10180u, 7u, 0, 3u, 0x2000000u, 0);
  v11 = FileW;
  v39[0] = FileW;
  if ( !FileW || FileW == (char *)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x8E5,
                  (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                  v10);
    v25 = (unsigned __int64)(v11 - 1);
    goto LABEL_29;
  }
  v12 = 2 * v42 + 24;
  v13 = operator new[](v12);
  v38 = v13;
  memset_0(v13, 0, v12);
  *v13 = 3;
  if ( IsWindowsVersionOrGreaterEx(v15, v14, v16, 0x4563u) )
    *v13 |= 0x40u;
  v13[4] = 2 * v42;
  v17 = 2 * v42;
  v18 = Src;
  if ( v43 > 7 )
    v18 = (void **)Src[0];
  if ( v17 )
  {
    v19 = v13 + 5;
    if ( v13 == (_DWORD *)-20LL )
    {
      *(_DWORD *)o__errno_0() = 22;
      invalid_parameter_noinfo();
LABEL_27:
      LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F6,
        (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
        (const char *)0x8000FFFFLL,
        dwCreationDisposition);
LABEL_28:
      operator delete(v13);
      v25 = (unsigned __int64)(v11 - 1);
LABEL_29:
      v24 = v25 <= 0xFFFFFFFFFFFFFFFDuLL;
      goto LABEL_30;
    }
    v20 = v12 - 20;
    if ( !v18 || v20 < v17 )
    {
      memset_0(v19, 0, v12 - 20);
      if ( v18 )
      {
        if ( v20 >= v17 )
          goto LABEL_27;
        *(_DWORD *)o__errno_0() = 34;
      }
      else
      {
        *(_DWORD *)o__errno_0() = 22;
      }
      invalid_parameter_noinfo();
      goto LABEL_27;
    }
    memcpy_0(v19, v18, 2 * v42);
  }
  v37[0] = 0;
  v21 = lpFileName;
  if ( v45 > 7 )
    v21 = (LPCWSTR *)lpFileName[0];
  v40[0] = v21;
  v40[1] = lpFileName[2];
  v22 = IsPathFAT(v11, v40, v37);
  LastError = v22;
  if ( v22 >= 0 )
  {
    v26 = MaximumFileInfoByHandleClass|FileDispositionInfo;
    if ( v37[0] )
    {
      v26 = FileRenameInfo;
      *(_BYTE *)v13 = 1;
    }
    if ( !SetFileInformationByHandle(v11, v26, v13, v12) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x90D,
                    (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                    v27);
      goto LABEL_28;
    }
    operator delete(v13);
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v11) < 0 )
      __fastfail(7u);
LABEL_56:
    LastError = 0;
    goto LABEL_57;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8FC,
    (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
    (const char *)(unsigned int)v22,
    dwCreationDisposition);
  operator delete(v13);
  v24 = (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_30:
  if ( v24 && NtClose(v11) < 0 )
    __fastfail(7u);
LABEL_57:
  std::wstring::~wstring(Src);
  std::wstring::~wstring(lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x18002ee48  mov     rax, rsp
0x18002ee4b  push    rbp
0x18002ee4c  push    rdi
0x18002ee4d  push    r13
0x18002ee4f  push    r14
0x18002ee51  push    r15
0x18002ee53  lea     rbp, [rax-5Fh]
0x18002ee57  sub     rsp, 0C0h
0x18002ee5e  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x18002ee66  mov     [rax+18h], rbx
0x18002ee6a  mov     [rax+20h], rsi
0x18002ee6e  mov     rax, cs:__security_cookie
0x18002ee75  xor     rax, rsp
0x18002ee78  mov     [rbp+57h+var_28], rax
0x18002ee7c  mov     rbx, rdx
0x18002ee7f  mov     rdx, rcx
0x18002ee82  lea     rcx, [rbp+57h+lpFileName]
0x18002ee86  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x18002ee8b  nop
0x18002ee8c  mov     rdx, rbx
0x18002ee8f  lea     rcx, [rbp+57h+Src]
0x18002ee93  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x18002ee98  nop
0x18002ee99  mov     rcx, [rbp+57h+var_58]
0x18002ee9d  lea     rax, [rbp+57h+Src]
0x18002eea1  mov     r15d, 7
0x18002eea7  cmp     [rbp+57h+var_50], r15
0x18002eeab  cmova   rax, [rbp+57h+Src]
0x18002eeb0  mov     [rbp+57h+var_90], rax
0x18002eeb4  mov     [rbp+57h+var_88], rcx
0x18002eeb8  lea     rcx, [rbp+57h+var_90]
0x18002eebc  call    ?EnsurePathForFileExists@@YAXAEBV?$basic_zstring_view@_W@wil@@@Z; EnsurePathForFileExists(wil::basic_zstring_view<wchar_t> const &)
0x18002eec1  mov     r9d, 383Ah; unsigned __int16
0x18002eec7  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18002eecc  lea     rcx, [rbp+57h+lpFileName]
0x18002eed0  test    al, al
0x18002eed2  jz      loc_18002F15F
0x18002eed8  cmp     [rbp+57h+var_30], r15
0x18002eedc  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18002eee1  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18002eeea  mov     [rsp+0E0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002eef2  lea     r14d, [r15-4]
0x18002eef6  mov     [rsp+0E0h+dwCreationDisposition], r14d; int
0x18002eefb  xor     r9d, r9d; lpSecurityAttributes
0x18002eefe  mov     r8d, r15d; dwShareMode
0x18002ef01  mov     edx, 10180h; dwDesiredAccess
0x18002ef06  call    cs:__imp_CreateFileW
0x18002ef0d  nop     dword ptr [rax+rax+00h]
0x18002ef12  mov     rbx, rax
0x18002ef15  mov     [rbp+57h+var_90], rax
0x18002ef19  test    rax, rax
0x18002ef1c  jz      loc_18002F13C
0x18002ef22  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ef26  jz      loc_18002F13C
0x18002ef2c  mov     eax, dword ptr [rbp+57h+var_58]
0x18002ef2f  lea     r13d, ds:18h[rax*2]
0x18002ef37  mov     [rbp+57h+var_98], 0
0x18002ef3f  mov     ecx, r13d; unsigned __int64
0x18002ef42  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002ef47  mov     rsi, rax
0x18002ef4a  mov     [rbp+57h+var_98], rax
0x18002ef4e  mov     r8d, r13d; Size
0x18002ef51  xor     edx, edx; Val
0x18002ef53  mov     rcx, rax; void *
0x18002ef56  call    memset_0
0x18002ef5b  mov     [rsi], r14d
0x18002ef5e  mov     r9d, 4563h; unsigned __int16
0x18002ef64  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18002ef69  test    al, al
0x18002ef6b  jz      short loc_18002EF70
0x18002ef6d  or      dword ptr [rsi], 40h
0x18002ef70  mov     eax, dword ptr [rbp+57h+var_58]
0x18002ef73  add     eax, eax
0x18002ef75  mov     [rsi+10h], eax
0x18002ef78  mov     rax, [rbp+57h+var_58]
0x18002ef7c  lea     r14, [rax+rax]
0x18002ef80  lea     rdi, [rbp+57h+Src]
0x18002ef84  cmp     [rbp+57h+var_50], r15
0x18002ef88  cmova   rdi, [rbp+57h+Src]
0x18002ef8d  test    r14, r14
0x18002ef90  jz      short loc_18002EFCF
0x18002ef92  lea     rcx, [rsi+14h]; void *
0x18002ef96  test    rcx, rcx
0x18002ef99  jnz     short loc_18002EFB0
0x18002ef9b  call    _o__errno_0
0x18002efa0  mov     dword ptr [rax], 16h
0x18002efa6  call    _invalid_parameter_noinfo
0x18002efab  jmp     loc_18002F069
0x18002efb0  lea     r15d, [r13-14h]
0x18002efb4  test    rdi, rdi
0x18002efb7  jz      short loc_18002F032
0x18002efb9  cmp     r15, r14
0x18002efbc  jb      short loc_18002F032
0x18002efbe  mov     r8, r14; Size
0x18002efc1  mov     rdx, rdi; Src
0x18002efc4  call    memcpy_0
0x18002efc9  mov     r15d, 7
0x18002efcf  mov     [rbp+57h+var_A0], 0
0x18002efd3  mov     rcx, [rbp+57h+var_38]
0x18002efd7  lea     rax, [rbp+57h+lpFileName]
0x18002efdb  cmp     [rbp+57h+var_30], r15
0x18002efdf  cmova   rax, [rbp+57h+lpFileName]
0x18002efe4  mov     [rbp+57h+var_80], rax
0x18002efe8  mov     [rbp+57h+var_78], rcx
0x18002efec  lea     r8, [rbp+57h+var_A0]
0x18002eff0  lea     rdx, [rbp+57h+var_80]
0x18002eff4  mov     rcx, rbx
0x18002eff7  call    ?IsPathFAT@@YAJPEAXAEBV?$basic_zstring_view@_W@wil@@PEA_N@Z; IsPathFAT(void *,wil::basic_zstring_view<wchar_t> const &,bool *)
0x18002effc  mov     edi, eax
0x18002effe  test    eax, eax
0x18002f000  jns     loc_18002F0BF
0x18002f006  mov     rcx, [rbp+5Fh]; this
0x18002f00a  mov     r9d, eax; char *
0x18002f00d  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002f014  mov     edx, 8FCh; void *
0x18002f019  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f01e  nop
0x18002f01f  mov     rcx, rsi; Block
0x18002f022  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f027  nop
0x18002f028  lea     rcx, [rbx-1]
0x18002f02c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002f030  jmp     short loc_18002F098
0x18002f032  mov     r8, r15; Size
0x18002f035  xor     edx, edx; Val
0x18002f037  call    memset_0
0x18002f03c  test    rdi, rdi
0x18002f03f  jnz     short loc_18002F04E
0x18002f041  call    _o__errno_0
0x18002f046  mov     dword ptr [rax], 16h
0x18002f04c  jmp     short loc_18002F05E
0x18002f04e  cmp     r15, r14
0x18002f051  jnb     short loc_18002F063
0x18002f053  call    _o__errno_0
0x18002f058  mov     dword ptr [rax], 22h ; '"'
0x18002f05e  call    _invalid_parameter_noinfo
0x18002f063  mov     r15d, 7
0x18002f069  mov     rcx, [rbp+5Fh]; this
0x18002f06d  mov     edi, 8000FFFFh
0x18002f072  mov     r9d, edi; char *
0x18002f075  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002f07c  mov     edx, 8F6h; void *
0x18002f081  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f086  nop
0x18002f087  mov     rcx, rsi; Block
0x18002f08a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f08f  nop
0x18002f090  lea     rax, [rbx-1]
0x18002f094  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f098  ja      loc_18002F215
0x18002f09e  mov     rcx, rbx; Handle
0x18002f0a1  call    cs:__imp_NtClose
0x18002f0a8  nop     dword ptr [rax+rax+00h]
0x18002f0ad  test    eax, eax
0x18002f0af  jns     loc_18002F215
0x18002f0b5  mov     rcx, r15
0x18002f0b8  int     29h; Win8: RtlFailFast(ecx)
0x18002f0ba  jmp     loc_18002F215
0x18002f0bf  mov     edx, 16h
0x18002f0c4  cmp     [rbp+57h+var_A0], 0
0x18002f0c8  jz      short loc_18002F0D2
0x18002f0ca  mov     edx, 3; FileInformationClass
0x18002f0cf  mov     byte ptr [rsi], 1
0x18002f0d2  mov     r9d, r13d; dwBufferSize
0x18002f0d5  mov     r8, rsi; lpFileInformation
0x18002f0d8  mov     rcx, rbx; hFile
0x18002f0db  call    cs:__imp_SetFileInformationByHandle
0x18002f0e2  nop     dword ptr [rax+rax+00h]
0x18002f0e7  test    eax, eax
0x18002f0e9  jnz     short loc_18002F104
0x18002f0eb  mov     rcx, [rbp+5Fh]; this
0x18002f0ef  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002f0f6  mov     edx, 90Dh; void *
0x18002f0fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f100  mov     edi, eax
0x18002f102  jmp     short loc_18002F087
0x18002f104  mov     rcx, rsi; Block
0x18002f107  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f10c  nop
0x18002f10d  lea     rax, [rbx-1]
0x18002f111  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f115  ja      loc_18002F213
0x18002f11b  mov     rcx, rbx; Handle
0x18002f11e  call    cs:__imp_NtClose
0x18002f125  nop     dword ptr [rax+rax+00h]
0x18002f12a  test    eax, eax
0x18002f12c  jns     loc_18002F213
0x18002f132  mov     rcx, r15
0x18002f135  int     29h; Win8: RtlFailFast(ecx)
0x18002f137  jmp     loc_18002F213
0x18002f13c  mov     rsi, rbx
0x18002f13f  mov     rcx, [rbp+5Fh]; this
0x18002f143  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002f14a  mov     edx, 8E5h; void *
0x18002f14f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f154  mov     edi, eax
0x18002f156  lea     rax, [rbx-1]
0x18002f15a  jmp     loc_18002F094
0x18002f15f  cmp     [rbp+57h+var_30], r15
0x18002f163  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18002f168  call    cs:__imp_GetFileAttributesW
0x18002f16f  nop     dword ptr [rax+rax+00h]
0x18002f174  mov     ebx, eax
0x18002f176  lea     rcx, [rbp+57h+lpFileName]
0x18002f17a  cmp     [rbp+57h+var_30], r15
0x18002f17e  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18002f183  mov     edi, 80h
0x18002f188  mov     edx, edi; dwFileAttributes
0x18002f18a  call    cs:__imp_SetFileAttributesW
0x18002f191  nop     dword ptr [rax+rax+00h]
0x18002f196  lea     rcx, [rbp+57h+Src]
0x18002f19a  cmp     [rbp+57h+var_50], r15
0x18002f19e  cmova   rcx, [rbp+57h+Src]; lpFileName
0x18002f1a3  mov     edx, edi; dwFileAttributes
0x18002f1a5  call    cs:__imp_SetFileAttributesW
0x18002f1ac  nop     dword ptr [rax+rax+00h]
0x18002f1b1  lea     rdx, [rbp+57h+Src]
0x18002f1b5  cmp     [rbp+57h+var_50], r15
0x18002f1b9  cmova   rdx, [rbp+57h+Src]; lpNewFileName
0x18002f1be  lea     rcx, [rbp+57h+lpFileName]
0x18002f1c2  cmp     [rbp+57h+var_30], r15
0x18002f1c6  cmova   rcx, [rbp+57h+lpFileName]; lpExistingFileName
0x18002f1cb  lea     r8d, [rdi-7Fh]; dwFlags
0x18002f1cf  call    cs:__imp_MoveFileExW
0x18002f1d6  nop     dword ptr [rax+rax+00h]
0x18002f1db  test    eax, eax
0x18002f1dd  jnz     short loc_18002F1F8
0x18002f1df  mov     rcx, [rbp+5Fh]; this
0x18002f1e3  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002f1ea  mov     edx, 919h; void *
0x18002f1ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f1f4  mov     edi, eax
0x18002f1f6  jmp     short loc_18002F215
0x18002f1f8  lea     rcx, [rbp+57h+Src]
0x18002f1fc  cmp     [rbp+57h+var_50], r15
0x18002f200  cmova   rcx, [rbp+57h+Src]; lpFileName
0x18002f205  mov     edx, ebx; dwFileAttributes
0x18002f207  call    cs:__imp_SetFileAttributesW
0x18002f20e  nop     dword ptr [rax+rax+00h]
0x18002f213  xor     edi, edi
0x18002f215  lea     rcx, [rbp+57h+Src]; void *
0x18002f219  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f21e  nop
0x18002f21f  lea     rcx, [rbp+57h+lpFileName]; void *
0x18002f223  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f228  mov     eax, edi
0x18002f22a  mov     rcx, [rbp+57h+var_28]
0x18002f22e  xor     rcx, rsp; StackCookie
0x18002f231  call    __security_check_cookie
0x18002f236  lea     r11, [rsp+0E0h+var_20]
0x18002f23e  mov     rbx, [r11+40h]
0x18002f242  mov     rsi, [r11+48h]
0x18002f246  mov     rsp, r11
0x18002f249  pop     r15
0x18002f24b  pop     r14
0x18002f24d  pop     r13
0x18002f24f  pop     rdi
0x18002f250  pop     rbp
0x18002f251  retn
```
