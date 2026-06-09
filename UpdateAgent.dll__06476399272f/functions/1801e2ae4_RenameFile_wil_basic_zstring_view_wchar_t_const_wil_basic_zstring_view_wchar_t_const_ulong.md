# RenameFile(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong)

- ea: `0x1801e2ae4`
- end: `0x1801e30c7`
- name: `?RenameFile@@YAJAEBV?$basic_zstring_view@_W@wil@@0K@Z`
- size: `1507`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1801dec50`
- `0x1801e30d0`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x1800061e0`
- `0x1800068b2`
- `0x1800068ee`
- `0x180006a18`
- `0x180023b20`
- `0x18008b360`
- `0x18008b38c`
- `0x180145ab4`
- `0x1801df878`
- `0x1801e0318`
- `0x1801e1cc8`
- `0x1801e2ae4`
- `0x1801e32b0`
- `0x18029eaa4`

## import_xrefs

- `ntdll!NtClose` at `0x1801e2d68`
- `ntdll!NtClose` at `0x1801e2e22`
- `ntdll!NtClose` at `0x1801e2e81`
- `ntdll!NtClose` at `0x1801e2ed3`
- `ntdll!NtClose` at `0x1801e2f6c`
- `ntdll!NtClose` at `0x1801e2fb2`
- `ntdll!NtClose` at `0x1801e2d68`
- `ntdll!NtClose` at `0x1801e2e22`
- `ntdll!NtClose` at `0x1801e2e81`
- `ntdll!NtClose` at `0x1801e2ed3`
- `ntdll!NtClose` at `0x1801e2f6c`
- `ntdll!NtClose` at `0x1801e2fb2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801e2da2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801e2da2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801e2fff`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801e301a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801e307b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801e2fff`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801e301a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801e307b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801e2bd8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801e2bd8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801e2fd9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801e2fd9`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1801e3043`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1801e3043`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1801e2de1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1801e2f1b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1801e2de1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1801e2f1b`

## string_xrefs

- `0x1801e2b32`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e2ce3`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e2d3c`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e2df5`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e2ea1`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e2f8f`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e3057`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RenameFile(__int64 a1, __int64 a2, int a3)
{
  void **v6; // rax
  unsigned __int16 v7; // dx
  unsigned __int16 v8; // cx
  unsigned __int16 v9; // r8
  bool v10; // al
  const WCHAR *v11; // rcx
  char *FileW; // rax
  const char *v13; // r9
  char *v14; // rbx
  __int64 v15; // r14
  DWORD v16; // r13d
  _DWORD *v17; // rsi
  unsigned __int16 v18; // dx
  unsigned __int16 v19; // cx
  unsigned __int16 v20; // r8
  unsigned __int64 v21; // r12
  void **v22; // rdi
  void *v23; // rcx
  size_t v24; // r13
  LPCWSTR *v25; // rax
  int v26; // eax
  unsigned int LastError; // edi
  const struct std::nothrow_t *v28; // rdx
  bool v29; // cc
  const struct std::nothrow_t *v30; // rdx
  FILE_INFO_BY_HANDLE_CLASS v31; // edx
  const struct std::nothrow_t *v32; // rdx
  const char *v33; // r9
  void **v34; // rdx
  const WCHAR *v35; // rcx
  const char *v36; // r9
  const struct std::nothrow_t *v37; // rdx
  LPCWSTR *v38; // rax
  const struct std::nothrow_t *v39; // rdx
  void **v40; // rdx
  const WCHAR *v41; // rcx
  __int64 v42; // rdx
  LPCWSTR *v43; // rax
  DWORD FileAttributesW; // ebx
  DWORD v45; // r15d
  const WCHAR *v46; // rcx
  void **v47; // rcx
  void **v48; // rdx
  const WCHAR *v49; // rcx
  const char *v50; // r9
  void **v51; // rcx
  DWORD dwCreationDisposition; // [rsp+28h] [rbp-89h]
  DWORD dwCreationDispositiona; // [rsp+28h] [rbp-89h]
  char v54[8]; // [rsp+48h] [rbp-69h] BYREF
  LPCWSTR *v55; // [rsp+50h] [rbp-61h] BYREF
  LPCWSTR v56; // [rsp+58h] [rbp-59h]
  DWORD v57; // [rsp+60h] [rbp-51h]
  _DWORD *v58; // [rsp+68h] [rbp-49h]
  _QWORD v59[3]; // [rsp+70h] [rbp-41h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int64 v61; // [rsp+A0h] [rbp-11h]
  void *Src[2]; // [rsp+A8h] [rbp-9h] BYREF
  __int64 v63; // [rsp+B8h] [rbp+7h]
  unsigned __int64 v64; // [rsp+C0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]

  v59[2] = -2;
  if ( (a3 & 0xFFFFFFF5) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C0,
      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return 2147942487LL;
  }
  GetCanonicalUNCPath(lpFileName, a1);
  GetCanonicalUNCPath(Src, a2);
  v6 = Src;
  if ( v64 > 7 )
    v6 = (void **)Src[0];
  v59[0] = v6;
  v59[1] = v63;
  EnsurePathForFileExists(v59);
  v10 = IsWindowsVersionOrGreaterEx(v8, v7, v9, 0x383Au);
  v11 = (const WCHAR *)lpFileName;
  if ( !v10 )
  {
    if ( v61 > 7 )
      v11 = lpFileName[0];
    FileAttributesW = GetFileAttributesW(v11);
    v45 = a3 | 1;
    v46 = (const WCHAR *)lpFileName;
    if ( v61 > 7 )
      v46 = lpFileName[0];
    SetFileAttributesW(v46, 0x80u);
    v47 = Src;
    if ( v64 > 7 )
      v47 = (void **)Src[0];
    SetFileAttributesW((LPCWSTR)v47, 0x80u);
    v48 = Src;
    if ( v64 > 7 )
      v48 = (void **)Src[0];
    v49 = (const WCHAR *)lpFileName;
    if ( v61 > 7 )
      v49 = lpFileName[0];
    if ( !MoveFileExW(v49, (LPCWSTR)v48, v45) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x919,
                    (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                    v50);
      goto LABEL_90;
    }
    v51 = Src;
    if ( v64 > 7 )
      v51 = (void **)Src[0];
    SetFileAttributesW((LPCWSTR)v51, FileAttributesW);
    goto LABEL_89;
  }
  if ( v61 > 7 )
    v11 = lpFileName[0];
  FileW = (char *)CreateFileW(v11, 0x10180u, 7u, 0, 3u, ((a3 & 0xFFFFFFF8) << 28) | 0x2000000, 0);
  v14 = FileW;
  v59[0] = FileW;
  v15 = -1;
  if ( !FileW || FileW == (char *)-1LL )
  {
    if ( (a3 & 2) != 0 )
    {
      v40 = Src;
      if ( v64 > 7 )
        v40 = (void **)Src[0];
      v41 = (const WCHAR *)lpFileName;
      if ( v61 > 7 )
        v41 = lpFileName[0];
      if ( CopyFileW(v41, (LPCWSTR)v40, 0) )
      {
        v43 = lpFileName;
        if ( v61 > 7 )
          v43 = (LPCWSTR *)lpFileName[0];
        v55 = v43;
        do
          ++v15;
        while ( *((_WORD *)v43 + v15) );
        v56 = (LPCWSTR)v15;
        SetAttrAndDeleteFile(&v55);
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v14) < 0 )
          goto LABEL_69;
        goto LABEL_89;
      }
      v42 = 2272;
    }
    else
    {
      v42 = 2277;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v42,
                  (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                  v13);
    if ( (unsigned __int64)(v14 - 1) > 0xFFFFFFFFFFFFFFFDuLL || NtClose(v14) >= 0 )
      goto LABEL_90;
    goto LABEL_73;
  }
  v16 = 2 * v63 + 24;
  v57 = v16;
  v17 = operator new[](v16);
  v58 = v17;
  memset_0(v17, 0, v16);
  *v17 = 3;
  if ( IsWindowsVersionOrGreaterEx(v19, v18, v20, 0x4563u) )
    *v17 |= 0x40u;
  v17[4] = 2 * v63;
  v21 = 2 * v63;
  v22 = Src;
  if ( v64 > 7 )
    v22 = (void **)Src[0];
  if ( v21 )
  {
    v23 = v17 + 5;
    if ( v17 == (_DWORD *)-20LL )
      goto LABEL_16;
    v24 = v16 - 20;
    if ( !v22 || v24 < v21 )
    {
      memset_0(v23, 0, v24);
      if ( v22 )
      {
        if ( v24 >= v21 )
        {
LABEL_28:
          LastError = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8F6,
            (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
            (const char *)0x8000FFFFLL,
            dwCreationDispositiona);
LABEL_29:
          operator delete(v17, v30);
          v29 = (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
          goto LABEL_30;
        }
        *(_DWORD *)o__errno_0() = 34;
LABEL_27:
        invalid_parameter_noinfo();
        goto LABEL_28;
      }
LABEL_16:
      *(_DWORD *)o__errno_0() = 22;
      goto LABEL_27;
    }
    memcpy_0(v23, v22, 2 * v63);
    v16 = v57;
  }
  v54[0] = 0;
  v25 = lpFileName;
  if ( v61 > 7 )
    v25 = (LPCWSTR *)lpFileName[0];
  v55 = v25;
  v56 = lpFileName[2];
  v26 = IsPathFAT(v14, &v55, v54);
  LastError = v26;
  if ( v26 >= 0 )
  {
    v31 = MaximumFileInfoByHandleClass|FileDispositionInfo;
    if ( v54[0] )
    {
      v31 = FileRenameInfo;
      *(_BYTE *)v17 = 1;
    }
    if ( SetFileInformationByHandle(v14, v31, v17, v16) )
    {
      operator delete(v17, v32);
      if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v14) < 0 )
        goto LABEL_69;
    }
    else
    {
      if ( (a3 & 2) == 0 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x90D,
                      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                      v33);
        goto LABEL_29;
      }
      v34 = Src;
      if ( v64 > 7 )
        v34 = (void **)Src[0];
      v35 = (const WCHAR *)lpFileName;
      if ( v61 > 7 )
        v35 = lpFileName[0];
      if ( !CopyFileW(v35, (LPCWSTR)v34, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x908,
                      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                      v36);
        operator delete(v17, v37);
        if ( (unsigned __int64)(v14 - 1) > 0xFFFFFFFFFFFFFFFDuLL || NtClose(v14) >= 0 )
          goto LABEL_90;
LABEL_73:
        __fastfail(7u);
      }
      v38 = lpFileName;
      if ( v61 > 7 )
        v38 = (LPCWSTR *)lpFileName[0];
      v55 = v38;
      do
        ++v15;
      while ( *((_WORD *)v38 + v15) );
      v56 = (LPCWSTR)v15;
      SetAttrAndDeleteFile(&v55);
      operator delete(v17, v39);
      if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v14) < 0 )
LABEL_69:
        __fastfail(7u);
    }
LABEL_89:
    LastError = 0;
    goto LABEL_90;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8FC,
    (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
    (const char *)(unsigned int)v26,
    dwCreationDispositiona);
  operator delete(v17, v28);
  v29 = (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_30:
  if ( v29 && NtClose(v14) < 0 )
    goto LABEL_73;
LABEL_90:
  std::wstring::~wstring(Src);
  std::wstring::~wstring(lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x1801e2ae4  mov     rax, rsp
0x1801e2ae7  push    rbp
0x1801e2ae8  push    rsi
0x1801e2ae9  push    rdi
0x1801e2aea  push    r12
0x1801e2aec  push    r13
0x1801e2aee  push    r14
0x1801e2af0  push    r15
0x1801e2af2  lea     rbp, [rax-5Fh]
0x1801e2af6  sub     rsp, 0D0h
0x1801e2afd  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x1801e2b05  mov     [rax+20h], rbx
0x1801e2b09  mov     rax, cs:__security_cookie
0x1801e2b10  xor     rax, rsp
0x1801e2b13  mov     [rbp+57h+var_40], rax
0x1801e2b17  mov     r15d, r8d
0x1801e2b1a  mov     rbx, rdx
0x1801e2b1d  test    r8d, 0FFFFFFF5h
0x1801e2b24  jz      short loc_1801E2B4A
0x1801e2b26  mov     rcx, [rbp+5Fh]; this
0x1801e2b2a  mov     ebx, 80070057h
0x1801e2b2f  mov     r9d, ebx; char *
0x1801e2b32  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e2b39  mov     edx, 8C0h; void *
0x1801e2b3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2b43  mov     eax, ebx
0x1801e2b45  jmp     loc_1801E309F
0x1801e2b4a  mov     rdx, rcx
0x1801e2b4d  lea     rcx, [rbp+57h+lpFileName]
0x1801e2b51  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x1801e2b56  nop
0x1801e2b57  mov     rdx, rbx
0x1801e2b5a  lea     rcx, [rbp+57h+Src]
0x1801e2b5e  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x1801e2b63  nop
0x1801e2b64  mov     rcx, [rbp+57h+var_50]
0x1801e2b68  lea     rax, [rbp+57h+Src]
0x1801e2b6c  mov     r13d, 7
0x1801e2b72  cmp     [rbp+57h+var_48], r13
0x1801e2b76  cmova   rax, [rbp+57h+Src]
0x1801e2b7b  mov     [rbp+57h+var_98], rax
0x1801e2b7f  mov     [rbp+57h+var_90], rcx
0x1801e2b83  lea     rcx, [rbp+57h+var_98]
0x1801e2b87  call    ?EnsurePathForFileExists@@YAXAEBV?$basic_zstring_view@_W@wil@@@Z; EnsurePathForFileExists(wil::basic_zstring_view<wchar_t> const &)
0x1801e2b8c  mov     r9d, 383Ah; unsigned __int16
0x1801e2b92  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1801e2b97  xor     r12d, r12d
0x1801e2b9a  lea     rcx, [rbp+57h+lpFileName]
0x1801e2b9e  test    al, al
0x1801e2ba0  jz      loc_1801E2FD0
0x1801e2ba6  mov     eax, r15d
0x1801e2ba9  and     eax, 0FFFFFFF8h
0x1801e2bac  shl     eax, 1Ch
0x1801e2baf  bts     eax, 19h
0x1801e2bb3  cmp     [rbp+57h+var_68], r13
0x1801e2bb7  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1801e2bbc  mov     [rsp+30h], r12; hTemplateFile
0x1801e2bc1  mov     [rsp+100h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1801e2bc5  mov     [rsp+100h+dwCreationDisposition], 3; int
0x1801e2bcd  xor     r9d, r9d; lpSecurityAttributes
0x1801e2bd0  mov     r8d, r13d; dwShareMode
0x1801e2bd3  mov     edx, 10180h; dwDesiredAccess
0x1801e2bd8  call    cs:__imp_CreateFileW
0x1801e2bdf  nop     dword ptr [rax+rax+00h]
0x1801e2be4  mov     rbx, rax
0x1801e2be7  mov     [rbp+57h+var_98], rax
0x1801e2beb  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801e2bef  test    rax, rax
0x1801e2bf2  jz      loc_1801E2EF1
0x1801e2bf8  cmp     rax, r14
0x1801e2bfb  jz      loc_1801E2EF1
0x1801e2c01  mov     eax, dword ptr [rbp+57h+var_50]
0x1801e2c04  lea     r13d, ds:18h[rax*2]
0x1801e2c0c  mov     [rbp+57h+var_A8], r13d
0x1801e2c10  mov     [rbp+57h+var_A0], r12
0x1801e2c14  mov     ecx, r13d; unsigned __int64
0x1801e2c17  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801e2c1c  mov     rsi, rax
0x1801e2c1f  mov     [rbp+57h+var_A0], rax
0x1801e2c23  mov     r8d, r13d; Size
0x1801e2c26  xor     edx, edx; Val
0x1801e2c28  mov     rcx, rax; void *
0x1801e2c2b  call    memset_0
0x1801e2c30  mov     dword ptr [rsi], 3
0x1801e2c36  mov     r9d, 4563h; unsigned __int16
0x1801e2c3c  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1801e2c41  test    al, al
0x1801e2c43  jz      short loc_1801E2C48
0x1801e2c45  or      dword ptr [rsi], 40h
0x1801e2c48  mov     eax, dword ptr [rbp+57h+var_50]
0x1801e2c4b  add     eax, eax
0x1801e2c4d  mov     [rsi+10h], eax
0x1801e2c50  mov     rax, [rbp+57h+var_50]
0x1801e2c54  lea     r12, [rax+rax]
0x1801e2c58  lea     rdi, [rbp+57h+Src]
0x1801e2c5c  cmp     [rbp+57h+var_48], 7
0x1801e2c61  cmova   rdi, [rbp+57h+Src]
0x1801e2c66  test    r12, r12
0x1801e2c69  jz      short loc_1801E2CA1
0x1801e2c6b  lea     rcx, [rsi+14h]; void *
0x1801e2c6f  test    rcx, rcx
0x1801e2c72  jnz     short loc_1801E2C84
0x1801e2c74  call    _o__errno_0
0x1801e2c79  mov     dword ptr [rax], 16h
0x1801e2c7f  jmp     loc_1801E2D2B
0x1801e2c84  add     r13d, 0FFFFFFECh
0x1801e2c88  test    rdi, rdi
0x1801e2c8b  jz      short loc_1801E2D08
0x1801e2c8d  cmp     r13, r12
0x1801e2c90  jb      short loc_1801E2D08
0x1801e2c92  mov     r8, r12; Size
0x1801e2c95  mov     rdx, rdi; Src
0x1801e2c98  call    memcpy_0
0x1801e2c9d  mov     r13d, [rbp+57h+var_A8]
0x1801e2ca1  xor     r12d, r12d
0x1801e2ca4  mov     [rbp+57h+var_C0], r12b
0x1801e2ca8  mov     rcx, [rbp+57h+var_70]
0x1801e2cac  lea     rax, [rbp+57h+lpFileName]
0x1801e2cb0  cmp     [rbp+57h+var_68], 7
0x1801e2cb5  cmova   rax, [rbp+57h+lpFileName]
0x1801e2cba  mov     [rbp+57h+var_B8], rax
0x1801e2cbe  mov     [rbp+57h+var_B0], rcx
0x1801e2cc2  lea     r8, [rbp+57h+var_C0]
0x1801e2cc6  lea     rdx, [rbp+57h+var_B8]
0x1801e2cca  mov     rcx, rbx
0x1801e2ccd  call    ?IsPathFAT@@YAJPEAXAEBV?$basic_zstring_view@_W@wil@@PEA_N@Z; IsPathFAT(void *,wil::basic_zstring_view<wchar_t> const &,bool *)
0x1801e2cd2  mov     edi, eax
0x1801e2cd4  test    eax, eax
0x1801e2cd6  jns     loc_1801E2D86
0x1801e2cdc  mov     rcx, [rbp+5Fh]; this
0x1801e2ce0  mov     r9d, eax; char *
0x1801e2ce3  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e2cea  mov     edx, 8FCh; void *
0x1801e2cef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2cf4  nop
0x1801e2cf5  mov     rcx, rsi; void *
0x1801e2cf8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801e2cfd  nop
0x1801e2cfe  lea     rcx, [rbx-1]
0x1801e2d02  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801e2d06  jmp     short loc_1801E2D5F
0x1801e2d08  mov     r8, r13; Size
0x1801e2d0b  xor     edx, edx; Val
0x1801e2d0d  call    memset_0
0x1801e2d12  test    rdi, rdi
0x1801e2d15  jz      loc_1801E2C74
0x1801e2d1b  cmp     r13, r12
0x1801e2d1e  jnb     short loc_1801E2D30
0x1801e2d20  call    _o__errno_0
0x1801e2d25  mov     dword ptr [rax], 22h ; '"'
0x1801e2d2b  call    _invalid_parameter_noinfo
0x1801e2d30  mov     rcx, [rbp+5Fh]; this
0x1801e2d34  mov     edi, 8000FFFFh
0x1801e2d39  mov     r9d, edi; char *
0x1801e2d3c  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e2d43  mov     edx, 8F6h; void *
0x1801e2d48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2d4d  nop
0x1801e2d4e  mov     rcx, rsi; void *
0x1801e2d51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801e2d56  nop
0x1801e2d57  lea     rax, [rbx-1]
0x1801e2d5b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e2d5f  ja      loc_1801E308A
0x1801e2d65  mov     rcx, rbx; Handle
0x1801e2d68  call    cs:__imp_NtClose
0x1801e2d6f  nop     dword ptr [rax+rax+00h]
0x1801e2d74  test    eax, eax
0x1801e2d76  jns     loc_1801E308A
0x1801e2d7c  mov     ecx, 7
0x1801e2d81  jmp     loc_1801E2FC9
0x1801e2d86  mov     edx, 16h
0x1801e2d8b  cmp     [rbp+57h+var_C0], r12b
0x1801e2d8f  jz      short loc_1801E2D99
0x1801e2d91  mov     edx, 3; FileInformationClass
0x1801e2d96  mov     byte ptr [rsi], 1
0x1801e2d99  mov     r9d, r13d; dwBufferSize
0x1801e2d9c  mov     r8, rsi; lpFileInformation
0x1801e2d9f  mov     rcx, rbx; hFile
0x1801e2da2  call    cs:__imp_SetFileInformationByHandle
0x1801e2da9  nop     dword ptr [rax+rax+00h]
0x1801e2dae  test    eax, eax
0x1801e2db0  jnz     loc_1801E2EB9
0x1801e2db6  test    r15b, 2
0x1801e2dba  jz      loc_1801E2E9D
0x1801e2dc0  lea     rdx, [rbp+57h+Src]
0x1801e2dc4  lea     r15d, [rax+7]
0x1801e2dc8  cmp     [rbp+57h+var_48], r15
0x1801e2dcc  cmova   rdx, [rbp+57h+Src]; lpNewFileName
0x1801e2dd1  lea     rcx, [rbp+57h+lpFileName]
0x1801e2dd5  cmp     [rbp+57h+var_68], r15
0x1801e2dd9  cmova   rcx, [rbp+57h+lpFileName]; lpExistingFileName
0x1801e2dde  xor     r8d, r8d; bFailIfExists
0x1801e2de1  call    cs:__imp_CopyFileW
0x1801e2de8  nop     dword ptr [rax+rax+00h]
0x1801e2ded  test    eax, eax
0x1801e2def  jnz     short loc_1801E2E3E
0x1801e2df1  mov     rcx, [rbp+5Fh]; this
0x1801e2df5  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e2dfc  mov     edx, 908h; void *
0x1801e2e01  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e2e06  mov     edi, eax
0x1801e2e08  mov     rcx, rsi; void *
0x1801e2e0b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801e2e10  nop
0x1801e2e11  lea     rax, [rbx-1]
0x1801e2e15  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e2e19  ja      loc_1801E308A
0x1801e2e1f  mov     rcx, rbx; Handle
0x1801e2e22  call    cs:__imp_NtClose
0x1801e2e29  nop     dword ptr [rax+rax+00h]
0x1801e2e2e  test    eax, eax
0x1801e2e30  jns     loc_1801E308A
0x1801e2e36  mov     ecx, r15d
0x1801e2e39  jmp     loc_1801E2FC9
0x1801e2e3e  lea     rax, [rbp+57h+lpFileName]
0x1801e2e42  cmp     [rbp+57h+var_68], r15
0x1801e2e46  cmova   rax, [rbp+57h+lpFileName]
0x1801e2e4b  mov     [rbp+57h+var_B8], rax
0x1801e2e4f  inc     r14
0x1801e2e52  cmp     [rax+r14*2], r12w
0x1801e2e57  jnz     short loc_1801E2E4F
0x1801e2e59  mov     [rbp+57h+var_B0], r14
0x1801e2e5d  lea     rcx, [rbp+57h+var_B8]
0x1801e2e61  call    ?SetAttrAndDeleteFile@@YAHAEBV?$basic_zstring_view@_W@wil@@@Z; SetAttrAndDeleteFile(wil::basic_zstring_view<wchar_t> const &)
0x1801e2e66  nop
0x1801e2e67  mov     rcx, rsi; void *
0x1801e2e6a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801e2e6f  nop
0x1801e2e70  lea     rax, [rbx-1]
0x1801e2e74  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e2e78  ja      loc_1801E3087
0x1801e2e7e  mov     rcx, rbx; Handle
0x1801e2e81  call    cs:__imp_NtClose
0x1801e2e88  nop     dword ptr [rax+rax+00h]
0x1801e2e8d  test    eax, eax
0x1801e2e8f  jns     loc_1801E3087
0x1801e2e95  mov     rcx, r15
0x1801e2e98  jmp     loc_1801E2F83
0x1801e2e9d  mov     rcx, [rbp+5Fh]; this
0x1801e2ea1  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e2ea8  mov     edx, 90Dh; void *
0x1801e2ead  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e2eb2  mov     edi, eax
0x1801e2eb4  jmp     loc_1801E2D4E
0x1801e2eb9  mov     rcx, rsi; void *
0x1801e2ebc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801e2ec1  nop
0x1801e2ec2  lea     rax, [rbx-1]
0x1801e2ec6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e2eca  ja      loc_1801E3087
0x1801e2ed0  mov     rcx, rbx; Handle
0x1801e2ed3  call    cs:__imp_NtClose
0x1801e2eda  nop     dword ptr [rax+rax+00h]
0x1801e2edf  test    eax, eax
0x1801e2ee1  jns     loc_1801E3087
0x1801e2ee7  mov     ecx, 7
0x1801e2eec  jmp     loc_1801E2F83
0x1801e2ef1  mov     rsi, rbx
0x1801e2ef4  test    r15b, 2
0x1801e2ef8  jz      loc_1801E2F8A
0x1801e2efe  lea     rdx, [rbp+57h+Src]
0x1801e2f02  cmp     [rbp+57h+var_48], r13
0x1801e2f06  cmova   rdx, [rbp+57h+Src]; lpNewFileName
0x1801e2f0b  lea     rcx, [rbp+57h+lpFileName]
0x1801e2f0f  cmp     [rbp+57h+var_68], r13
0x1801e2f13  cmova   rcx, [rbp+57h+lpFileName]; lpExistingFileName
0x1801e2f18  xor     r8d, r8d; bFailIfExists
0x1801e2f1b  call    cs:__imp_CopyFileW
0x1801e2f22  nop     dword ptr [rax+rax+00h]
0x1801e2f27  test    eax, eax
0x1801e2f29  jnz     short loc_1801E2F32
0x1801e2f2b  mov     edx, 8E0h
0x1801e2f30  jmp     short loc_1801E2F8F
0x1801e2f32  lea     rax, [rbp+57h+lpFileName]
0x1801e2f36  cmp     [rbp+57h+var_68], r13
0x1801e2f3a  cmova   rax, [rbp+57h+lpFileName]
0x1801e2f3f  mov     [rbp+57h+var_B8], rax
0x1801e2f43  inc     r14
0x1801e2f46  cmp     [rax+r14*2], r12w
0x1801e2f4b  jnz     short loc_1801E2F43
0x1801e2f4d  mov     [rbp+57h+var_B0], r14
0x1801e2f51  lea     rcx, [rbp+57h+var_B8]
0x1801e2f55  call    ?SetAttrAndDeleteFile@@YAHAEBV?$basic_zstring_view@_W@wil@@@Z; SetAttrAndDeleteFile(wil::basic_zstring_view<wchar_t> const &)
0x1801e2f5a  nop
0x1801e2f5b  lea     rax, [rsi-1]
0x1801e2f5f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e2f63  ja      loc_1801E3087
0x1801e2f69  mov     rcx, rbx; Handle
0x1801e2f6c  call    cs:__imp_NtClose
0x1801e2f73  nop     dword ptr [rax+rax+00h]
0x1801e2f78  test    eax, eax
0x1801e2f7a  jns     loc_1801E3087
0x1801e2f80  mov     rcx, r13
0x1801e2f83  int     29h; Win8: RtlFailFast(ecx)
0x1801e2f85  jmp     loc_1801E3087
0x1801e2f8a  mov     edx, 8E5h; void *
0x1801e2f8f  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e2f96  mov     rcx, [rbp+5Fh]; this
0x1801e2f9a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
  ... truncated ...
```
