# GetFinalPath(wil::basic_zstring_view<wchar_t> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,ulong,bool)

- ea: `0x1801e0ac4`
- end: `0x1801e0ff9`
- name: `?GetFinalPath@@YAJAEBV?$basic_zstring_view@_W@wil@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1K_N@Z`
- size: `1333`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800918a8`
- `0x1800c02fc`
- `0x1801e275c`

## callees

- `0x1800059d0`
- `0x18000c4c4`
- `0x18000d2fc`
- `0x180012b84`
- `0x180023b20`
- `0x180024dc8`
- `0x180027f3c`
- `0x1800604cc`
- `0x18008b360`
- `0x18008b38c`
- `0x18008b3bc`
- `0x18008b3ec`
- `0x1801ddfb4`
- `0x1801de1c0`
- `0x1801e0318`
- `0x1801e0ac4`
- `0x1801e3c10`
- `0x1801e3c88`
- `0x1801e3e74`
- `0x1801f05d4`
- `0x1801f250c`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1801e0ed1`
- `ntdll!NtQueryInformationFile` at `0x1801e0f0e`
- `ntdll!NtQueryInformationFile` at `0x1801e0ed1`
- `ntdll!NtQueryInformationFile` at `0x1801e0f0e`
- `ntdll!NtClose` at `0x1801e0c18`
- `ntdll!NtClose` at `0x1801e0fc1`
- `ntdll!NtClose` at `0x1801e0c18`
- `ntdll!NtClose` at `0x1801e0fc1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801e0c89`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801e0cc6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801e0c89`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801e0cc6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801e0b96`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801e0b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0bcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0bcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0cde`

## string_xrefs

- `0x1801e0b2e`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e0c44`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e0d5b`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e0e00`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e0f25`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e0f61`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801e0d01`: `Failed to get final path for {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetFinalPath(__int64 a1, _QWORD *a2, __int64 a3, DWORD a4, char a5)
{
  unsigned __int64 v9; // rdx
  unsigned int v10; // ebx
  const WCHAR *v12; // rcx
  char *FileW; // rbx
  const char *v14; // r9
  wil::details *v15; // rcx
  unsigned int LastErrorFailHr; // edi
  bool v17; // cc
  DWORD FinalPathNameByHandleW; // eax
  LPWSTR v19; // rdx
  signed int LastError; // edi
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // r8
  void *v24; // r8
  ULONG_PTR v25; // rax
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // r8
  _DWORD *v29; // r14
  NTSTATUS v30; // eax
  ULONG v31; // edi
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // r8
  int dwCreationDisposition; // [rsp+20h] [rbp-A1h]
  struct _IO_STATUS_BLOCK *dwCreationDispositiona; // [rsp+20h] [rbp-A1h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-A1h]
  unsigned int v38; // [rsp+40h] [rbp-81h] BYREF
  char *v39; // [rsp+48h] [rbp-79h]
  __int64 v40; // [rsp+50h] [rbp-71h]
  LPWSTR lpszFilePath[2]; // [rsp+58h] [rbp-69h] BYREF
  __int64 v42; // [rsp+68h] [rbp-59h]
  PVOID FileInformation[2]; // [rsp+70h] [rbp-51h] BYREF
  __int64 v44; // [rsp+80h] [rbp-41h]
  LPCWSTR lpFileName[4]; // [rsp+88h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-19h] BYREF
  LPWSTR v47; // [rsp+B8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v40 = -2;
  v39 = 0;
  GetCanonicalUNCPath(lpFileName, a1);
  UnicodeStringBuffer::UnicodeStringBuffer((UnicodeStringBuffer *)lpszFilePath, v9);
  if ( !a2 )
  {
    v10 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
      (const char *)0x80004003LL,
      dwCreationDisposition);
LABEL_5:
    std::vector<wchar_t>::~vector<wchar_t>(lpszFilePath);
    std::wstring::~wstring(lpFileName);
    return v10;
  }
  if ( !*(_QWORD *)(a1 + 8) )
  {
    v10 = -2147024809;
    goto LABEL_5;
  }
  v12 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v12 = lpFileName[0];
  FileW = (char *)CreateFileW(v12, 0, 7u, 0, 3u, 0xA000000u, 0);
  v39 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( a5 && (GetLastError() == 2 || GetLastError() == 3) )
    {
      if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v15);
        std::vector<wchar_t>::~vector<wchar_t>(lpszFilePath);
        std::wstring::~wstring(lpFileName);
        v17 = (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
        goto LABEL_14;
      }
    }
    else if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x5D,
                          (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                          v14);
LABEL_20:
      std::vector<wchar_t>::~vector<wchar_t>(lpszFilePath);
      std::wstring::~wstring(lpFileName);
      v17 = (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_14:
      if ( !v17 )
        return LastErrorFailHr;
LABEL_15:
      if ( NtClose(FileW) < 0 )
        __fastfail(7u);
      return LastErrorFailHr;
    }
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(
                             FileW,
                             lpszFilePath[0],
                             (signed __int64)(v42 - (unsigned __int64)lpszFilePath[0]) >> 1,
                             a4);
  v19 = lpszFilePath[0];
  if ( FinalPathNameByHandleW >= (unsigned int)((signed __int64)(v42 - (unsigned __int64)lpszFilePath[0]) >> 1) )
  {
    UnicodeStringBuffer::resize((UnicodeStringBuffer *)lpszFilePath, FinalPathNameByHandleW);
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(
                               FileW,
                               lpszFilePath[0],
                               (signed __int64)(v42 - (unsigned __int64)lpszFilePath[0]) >> 1,
                               a4);
    v19 = lpszFilePath[0];
  }
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<std::wstring>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get final path for {}",
        lpFileName);
      if ( LastError > 0 )
        v22 = (unsigned __int16)LastError | 0x80070000;
      else
        v22 = LastError;
      v38 = v22;
      IoStatusBlock.Pointer = &v38;
      dwCreationDispositiona = &IoStatusBlock;
      LOBYTE(v21) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v21,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      LastErrorFailHr = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0x70,
                          (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                          (const char *)(unsigned int)LastError,
                          (unsigned int)dwCreationDispositiona);
      std::vector<wchar_t>::~vector<wchar_t>(lpszFilePath);
      std::wstring::~wstring(lpFileName);
      goto LABEL_15;
    }
    std::vector<wchar_t>::~vector<wchar_t>(lpszFilePath);
    std::wstring::~wstring(lpFileName);
    goto LABEL_62;
  }
  if ( (a4 & 2) != 0 )
  {
    *(_OWORD *)FileInformation = 0;
    v44 = 0;
    if ( v19 )
    {
      v23 = -1;
      do
        ++v23;
      while ( v19[v23] );
      v24 = (void *)(2 * v23);
      v25 = (ULONG_PTR)v24 + 2;
    }
    else
    {
      v19 = 0;
      v24 = 0;
      v25 = 0;
    }
    IoStatusBlock.Pointer = v24;
    IoStatusBlock.Information = v25;
    v47 = v19;
    v26 = RtlConvertNtFilePathToWin32FilePath(&IoStatusBlock, FileInformation);
    if ( v26 < 0 )
    {
      LastErrorFailHr = wil::details::in1diag3::Return_NtStatus(
                          retaddr,
                          (void *)0x78,
                          (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                          (const char *)(unsigned int)v26,
                          (int)dwCreationDispositiona);
      if ( v44 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v44);
      goto LABEL_20;
    }
    v27 = to_wstring(&IoStatusBlock, FileInformation);
    std::wstring::operator=(a2, v27);
    std::wstring::~wstring(&IoStatusBlock);
    if ( v44 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v44);
  }
  else
  {
    v28 = -1;
    do
      ++v28;
    while ( v19[v28] );
    std::wstring::_Assign<wchar_t>(a2, v19, v28);
  }
  if ( a3 )
  {
    IoStatusBlock = 0;
    *(_OWORD *)FileInformation = 0;
    v44 = 0;
    std::vector<unsigned char>::resize(FileInformation, 528);
    v29 = FileInformation[0];
    v30 = NtQueryInformationFile(FileW, &IoStatusBlock, FileInformation[0], 0x210u, FileNameInformation);
    if ( v30 == -2147483643 )
    {
      v31 = *v29 + 8;
      std::vector<unsigned char>::resize(FileInformation, v31);
      v29 = FileInformation[0];
      v30 = NtQueryInformationFile(FileW, &IoStatusBlock, FileInformation[0], v31, FileNameInformation);
    }
    if ( v30 < 0 )
    {
      LastErrorFailHr = wil::details::in1diag3::Return_NtStatus(
                          retaddr,
                          (void *)0xA1,
                          (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                          (const char *)(unsigned int)v30,
                          dwCreationDispositionb);
LABEL_53:
      std::vector<unsigned char>::~vector<unsigned char>(FileInformation);
      goto LABEL_20;
    }
    v32 = (unsigned __int64)(unsigned int)*v29 >> 1;
    v33 = a2[2];
    if ( v32 >= v33 )
    {
      LastErrorFailHr = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
        (const char *)0x8000FFFFLL,
        dwCreationDispositionb);
      goto LABEL_53;
    }
    v34 = v33 - v32;
    if ( v33 < v32 )
      v34 = a2[2];
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    std::wstring::_Assign<wchar_t>(a3, a2, v34);
    std::vector<unsigned char>::~vector<unsigned char>(FileInformation);
  }
  std::vector<wchar_t>::~vector<wchar_t>(lpszFilePath);
  std::wstring::~wstring(lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_62:
    if ( NtClose(FileW) < 0 )
      __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x1801e0ac4  push    rbp
0x1801e0ac6  push    rbx
0x1801e0ac7  push    rsi
0x1801e0ac8  push    rdi
0x1801e0ac9  push    r12
0x1801e0acb  push    r13
0x1801e0acd  push    r14
0x1801e0acf  push    r15
0x1801e0ad1  lea     rbp, [rsp-17h]
0x1801e0ad6  sub     rsp, 0D8h
0x1801e0add  mov     [rbp+4Fh+var_C0], 0FFFFFFFFFFFFFFFEh
0x1801e0ae5  mov     rax, cs:__security_cookie
0x1801e0aec  xor     rax, rsp
0x1801e0aef  mov     [rbp+4Fh+var_48], rax
0x1801e0af3  mov     edi, r9d
0x1801e0af6  mov     r15, r8
0x1801e0af9  mov     rsi, rdx
0x1801e0afc  mov     rbx, rcx
0x1801e0aff  xor     r12d, r12d
0x1801e0b02  mov     [rbp+4Fh+var_C8], r12
0x1801e0b06  mov     rdx, rcx
0x1801e0b09  lea     rcx, [rbp+4Fh+lpFileName]
0x1801e0b0d  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x1801e0b12  nop
0x1801e0b13  lea     rcx, [rbp+4Fh+lpszFilePath]; this
0x1801e0b17  call    ??0UnicodeStringBuffer@@QEAA@_K@Z; UnicodeStringBuffer::UnicodeStringBuffer(unsigned __int64)
0x1801e0b1c  nop
0x1801e0b1d  test    rsi, rsi
0x1801e0b20  jnz     short loc_1801E0B3F
0x1801e0b22  mov     rcx, [rbp+57h]; this
0x1801e0b26  mov     ebx, 80004003h
0x1801e0b2b  mov     r9d, ebx; char *
0x1801e0b2e  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e0b35  lea     edx, [rsi+4Bh]; void *
0x1801e0b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e0b3d  jmp     short loc_1801E0B4A
0x1801e0b3f  cmp     [rbx+8], r12
0x1801e0b43  jnz     short loc_1801E0B65
0x1801e0b45  mov     ebx, 80070057h
0x1801e0b4a  lea     rcx, [rbp+4Fh+lpszFilePath]
0x1801e0b4e  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x1801e0b53  nop
0x1801e0b54  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x1801e0b58  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e0b5d  nop
0x1801e0b5e  mov     eax, ebx
0x1801e0b60  jmp     loc_1801E0FD8
0x1801e0b65  lea     rcx, [rbp+4Fh+lpFileName]
0x1801e0b69  mov     r13d, 7
0x1801e0b6f  cmp     [rbp+4Fh+var_70], r13
0x1801e0b73  cmova   rcx, [rbp+4Fh+lpFileName]; lpFileName
0x1801e0b78  mov     [rsp+110h+hTemplateFile], r12; hTemplateFile
0x1801e0b7d  mov     [rsp+110h+dwFlagsAndAttributes], 0A000000h; dwFlagsAndAttributes
0x1801e0b85  lea     r14d, [r13-4]
0x1801e0b89  mov     [rsp+110h+dwCreationDisposition], r14d; int
0x1801e0b8e  xor     r9d, r9d; lpSecurityAttributes
0x1801e0b91  mov     r8d, r13d; dwShareMode
0x1801e0b94  xor     edx, edx; dwDesiredAccess
0x1801e0b96  call    cs:__imp_CreateFileW
0x1801e0b9d  nop     dword ptr [rax+rax+00h]
0x1801e0ba2  mov     rbx, rax
0x1801e0ba5  mov     [rbp+4Fh+var_C8], rax
0x1801e0ba9  inc     rax
0x1801e0bac  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801e0bb2  jnz     loc_1801E0C75
0x1801e0bb8  cmp     [rbp+4Fh+arg_20], r12b
0x1801e0bbc  jz      short loc_1801E0C34
0x1801e0bbe  call    cs:__imp_GetLastError
0x1801e0bc5  nop     dword ptr [rax+rax+00h]
0x1801e0bca  cmp     eax, 2
0x1801e0bcd  jz      short loc_1801E0BE0
0x1801e0bcf  call    cs:__imp_GetLastError
0x1801e0bd6  nop     dword ptr [rax+rax+00h]
0x1801e0bdb  cmp     eax, r14d
0x1801e0bde  jnz     short loc_1801E0C34
0x1801e0be0  lea     rax, [rbx+1]
0x1801e0be4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801e0bea  jnz     loc_1801E0C75
0x1801e0bf0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1801e0bf5  mov     edi, eax
0x1801e0bf7  lea     rcx, [rbp+4Fh+lpszFilePath]
0x1801e0bfb  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x1801e0c00  nop
0x1801e0c01  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x1801e0c05  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e0c0a  nop
0x1801e0c0b  lea     rdx, [rbx-1]
0x1801e0c0f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801e0c13  ja      short loc_1801E0C2D
0x1801e0c15  mov     rcx, rbx; Handle
0x1801e0c18  call    cs:__imp_NtClose
0x1801e0c1f  nop     dword ptr [rax+rax+00h]
0x1801e0c24  test    eax, eax
0x1801e0c26  jns     short loc_1801E0C2D
0x1801e0c28  mov     rcx, r13
0x1801e0c2b  int     29h; Win8: RtlFailFast(ecx)
0x1801e0c2d  mov     eax, edi
0x1801e0c2f  jmp     loc_1801E0FD8
0x1801e0c34  lea     rax, [rbx+1]
0x1801e0c38  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801e0c3e  jnz     short loc_1801E0C75
0x1801e0c40  mov     rcx, [rbp+57h]; this
0x1801e0c44  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e0c4b  mov     edx, 5Dh ; ']'; void *
0x1801e0c50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e0c55  mov     edi, eax
0x1801e0c57  lea     rcx, [rbp+4Fh+lpszFilePath]
0x1801e0c5b  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x1801e0c60  nop
0x1801e0c61  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x1801e0c65  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e0c6a  nop
0x1801e0c6b  lea     rcx, [rbx-1]
0x1801e0c6f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801e0c73  jmp     short loc_1801E0C13
0x1801e0c75  mov     rdx, [rbp+4Fh+lpszFilePath]; lpszFilePath
0x1801e0c79  mov     r8, [rbp+4Fh+var_A8]
0x1801e0c7d  sub     r8, rdx
0x1801e0c80  sar     r8, 1; cchFilePath
0x1801e0c83  mov     r9d, edi; dwFlags
0x1801e0c86  mov     rcx, rbx; hFile
0x1801e0c89  call    cs:__imp_GetFinalPathNameByHandleW
0x1801e0c90  nop     dword ptr [rax+rax+00h]
0x1801e0c95  mov     rcx, [rbp+4Fh+var_A8]
0x1801e0c99  mov     rdx, [rbp+4Fh+lpszFilePath]
0x1801e0c9d  sub     rcx, rdx
0x1801e0ca0  sar     rcx, 1
0x1801e0ca3  cmp     eax, ecx
0x1801e0ca5  jb      short loc_1801E0CD6
0x1801e0ca7  mov     edx, eax; unsigned __int64
0x1801e0ca9  lea     rcx, [rbp+4Fh+lpszFilePath]; this
0x1801e0cad  call    ?resize@UnicodeStringBuffer@@QEAAX_K@Z; UnicodeStringBuffer::resize(unsigned __int64)
0x1801e0cb2  mov     rdx, [rbp+4Fh+lpszFilePath]; lpszFilePath
0x1801e0cb6  mov     r8, [rbp+4Fh+var_A8]
0x1801e0cba  sub     r8, rdx
0x1801e0cbd  sar     r8, 1; cchFilePath
0x1801e0cc0  mov     r9d, edi; dwFlags
0x1801e0cc3  mov     rcx, rbx; hFile
0x1801e0cc6  call    cs:__imp_GetFinalPathNameByHandleW
0x1801e0ccd  nop     dword ptr [rax+rax+00h]
0x1801e0cd2  mov     rdx, [rbp+4Fh+lpszFilePath]
0x1801e0cd6  test    eax, eax
0x1801e0cd8  jnz     loc_1801E0DA0
0x1801e0cde  call    cs:__imp_GetLastError
0x1801e0ce5  nop     dword ptr [rax+rax+00h]
0x1801e0cea  mov     edi, eax
0x1801e0cec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801e0cf3  test    rcx, rcx
0x1801e0cf6  jz      short loc_1801E0D50
0x1801e0cf8  lea     rax, [rbp+4Fh+lpFileName]
0x1801e0cfc  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1801e0d01  lea     r9, aFailedToGetFin; "Failed to get final path for {}"
0x1801e0d08  mov     r8d, r14d
0x1801e0d0b  xor     edx, edx
0x1801e0d0d  call    ??$LogNumObjects@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::Logger::LogNumObjects<std::wstring>(bool,LogAdapter::LogLevel,char const * const,std::wstring const &)
0x1801e0d12  test    edi, edi
0x1801e0d14  jg      short loc_1801E0D1A
0x1801e0d16  mov     eax, edi
0x1801e0d18  jmp     short loc_1801E0D22
0x1801e0d1a  movzx   eax, di
0x1801e0d1d  or      eax, 80070000h
0x1801e0d22  mov     [rsp+110h+var_D0], eax
0x1801e0d26  lea     rax, [rsp+110h+var_D0]
0x1801e0d2b  mov     qword ptr [rbp+4Fh+IoStatusBlock], rax
0x1801e0d2f  lea     rax, [rbp+4Fh+IoStatusBlock]
0x1801e0d33  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; unsigned int
0x1801e0d38  lea     r9, a0; ": {0}"
0x1801e0d3f  mov     r8d, r14d
0x1801e0d42  mov     dl, 1
0x1801e0d44  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801e0d4b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801e0d50  test    edi, edi
0x1801e0d52  jz      short loc_1801E0D87
0x1801e0d54  mov     rcx, [rbp+57h]; this
0x1801e0d58  mov     r9d, edi; char *
0x1801e0d5b  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e0d62  mov     edx, 70h ; 'p'; void *
0x1801e0d67  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801e0d6c  mov     edi, eax
0x1801e0d6e  lea     rcx, [rbp+4Fh+lpszFilePath]
0x1801e0d72  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x1801e0d77  nop
0x1801e0d78  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x1801e0d7c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e0d81  nop
0x1801e0d82  jmp     loc_1801E0C15
0x1801e0d87  lea     rcx, [rbp+4Fh+lpszFilePath]
0x1801e0d8b  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x1801e0d90  nop
0x1801e0d91  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x1801e0d95  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e0d9a  nop
0x1801e0d9b  jmp     loc_1801E0FBE
0x1801e0da0  test    dil, 2
0x1801e0da4  jz      loc_1801E0E76
0x1801e0daa  xorps   xmm0, xmm0
0x1801e0dad  xor     eax, eax
0x1801e0daf  movups  xmmword ptr [rbp+4Fh+FileInformation], xmm0
0x1801e0db3  mov     [rbp+4Fh+var_90], rax
0x1801e0db7  test    rdx, rdx
0x1801e0dba  jz      short loc_1801E0DD3
0x1801e0dbc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801e0dc0  inc     r8
0x1801e0dc3  cmp     [rdx+r8*2], r12w
0x1801e0dc8  jnz     short loc_1801E0DC0
0x1801e0dca  add     r8, r8
0x1801e0dcd  lea     rax, [r8+2]
0x1801e0dd1  jmp     short loc_1801E0DDC
0x1801e0dd3  mov     rdx, r12
0x1801e0dd6  mov     r8, r12
0x1801e0dd9  mov     rax, r12
0x1801e0ddc  mov     qword ptr [rbp+4Fh+IoStatusBlock], r8
0x1801e0de0  mov     [rbp+4Fh+IoStatusBlock.Information], rax
0x1801e0de4  mov     [rbp+4Fh+var_58], rdx
0x1801e0de8  lea     rdx, [rbp+4Fh+FileInformation]
0x1801e0dec  lea     rcx, [rbp+4Fh+IoStatusBlock]
0x1801e0df0  call    RtlConvertNtFilePathToWin32FilePath
0x1801e0df5  test    eax, eax
0x1801e0df7  jns     short loc_1801E0E43
0x1801e0df9  mov     rcx, [rbp+57h]; this
0x1801e0dfd  mov     r9d, eax; char *
0x1801e0e00  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e0e07  mov     edx, 78h ; 'x'; void *
0x1801e0e0c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801e0e11  mov     edi, eax
0x1801e0e13  mov     rcx, [rbp+4Fh+var_90]
0x1801e0e17  test    rcx, rcx
0x1801e0e1a  jz      short loc_1801E0E22
0x1801e0e1c  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801e0e21  nop
0x1801e0e22  lea     rcx, [rbp+4Fh+lpszFilePath]
0x1801e0e26  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x1801e0e2b  nop
0x1801e0e2c  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x1801e0e30  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e0e35  nop
0x1801e0e36  lea     rax, [rbx-1]
0x1801e0e3a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e0e3e  jmp     loc_1801E0C13
0x1801e0e43  lea     rdx, [rbp+4Fh+FileInformation]
0x1801e0e47  lea     rcx, [rbp+4Fh+IoStatusBlock]
0x1801e0e4b  call    ?to_wstring@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_LUNICODE_STRING@@@Z; to_wstring(_LUNICODE_STRING const &)
0x1801e0e50  mov     rdx, rax
0x1801e0e53  mov     rcx, rsi
0x1801e0e56  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801e0e5b  lea     rcx, [rbp+4Fh+IoStatusBlock]; void *
0x1801e0e5f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801e0e64  nop
0x1801e0e65  mov     rcx, [rbp+4Fh+var_90]
0x1801e0e69  test    rcx, rcx
0x1801e0e6c  jz      short loc_1801E0E74
0x1801e0e6e  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801e0e73  nop
0x1801e0e74  jmp     short loc_1801E0E8C
0x1801e0e76  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801e0e7a  inc     r8
0x1801e0e7d  cmp     [rdx+r8*2], r12w
0x1801e0e82  jnz     short loc_1801E0E7A
0x1801e0e84  mov     rcx, rsi
0x1801e0e87  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801e0e8c  test    r15, r15
0x1801e0e8f  jz      loc_1801E0FA0
0x1801e0e95  xorps   xmm0, xmm0
0x1801e0e98  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x1801e0e9c  xorps   xmm1, xmm1
0x1801e0e9f  movdqu  xmmword ptr [rbp+4Fh+FileInformation], xmm1
0x1801e0ea4  mov     [rbp+4Fh+var_90], r12
0x1801e0ea8  mov     edi, 210h
0x1801e0ead  mov     edx, edi
0x1801e0eaf  lea     rcx, [rbp+4Fh+FileInformation]
0x1801e0eb3  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1801e0eb8  mov     r14, [rbp+4Fh+FileInformation]
0x1801e0ebc  mov     [rsp+110h+dwCreationDisposition], 9; FileInformationClass
0x1801e0ec4  mov     r9d, edi; Length
0x1801e0ec7  mov     r8, r14; FileInformation
0x1801e0eca  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1801e0ece  mov     rcx, rbx; FileHandle
0x1801e0ed1  call    cs:__imp_NtQueryInformationFile
0x1801e0ed8  nop     dword ptr [rax+rax+00h]
0x1801e0edd  cmp     eax, 80000005h
0x1801e0ee2  jnz     short loc_1801E0F1A
0x1801e0ee4  mov     edi, [r14]
0x1801e0ee7  add     edi, 8
0x1801e0eea  mov     edx, edi
0x1801e0eec  lea     rcx, [rbp+4Fh+FileInformation]
0x1801e0ef0  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1801e0ef5  mov     r14, [rbp+4Fh+FileInformation]
0x1801e0ef9  mov     [rsp+110h+dwCreationDisposition], 9; int
0x1801e0f01  mov     r9d, edi; Length
0x1801e0f04  mov     r8, r14; FileInformation
0x1801e0f07  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1801e0f0b  mov     rcx, rbx; FileHandle
0x1801e0f0e  call    cs:__imp_NtQueryInformationFile
0x1801e0f15  nop     dword ptr [rax+rax+00h]
0x1801e0f1a  test    eax, eax
0x1801e0f1c  jns     short loc_1801E0F46
0x1801e0f1e  mov     rcx, [rbp+57h]; this
0x1801e0f22  mov     r9d, eax; char *
0x1801e0f25  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801e0f2c  mov     edx, 0A1h; void *
  ... truncated ...
```
