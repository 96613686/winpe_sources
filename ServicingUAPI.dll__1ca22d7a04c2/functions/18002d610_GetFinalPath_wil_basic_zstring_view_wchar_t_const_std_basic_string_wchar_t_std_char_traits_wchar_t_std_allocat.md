# GetFinalPath(wil::basic_zstring_view<wchar_t> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,ulong,bool)

- ea: `0x18002d610`
- end: `0x18002db45`
- name: `?GetFinalPath@@YAJAEBV?$basic_zstring_view@_W@wil@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1K_N@Z`
- size: `1333`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18002eb38`
- `0x180069378`

## callees

- `0x1800031d0`
- `0x180009750`
- `0x18000a774`
- `0x18000ba14`
- `0x18000ba40`
- `0x18000f874`
- `0x18000fb10`
- `0x18001ba80`
- `0x18001d650`
- `0x180022a18`
- `0x1800286d4`
- `0x1800296a4`
- `0x18002b4f8`
- `0x18002b834`
- `0x18002cdf8`
- `0x18002d610`
- `0x18002fcac`
- `0x18002fd24`
- `0x18002fda0`
- `0x18004a05c`
- `0x18004d970`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x18002da1d`
- `ntdll!NtQueryInformationFile` at `0x18002da5a`
- `ntdll!NtQueryInformationFile` at `0x18002da1d`
- `ntdll!NtQueryInformationFile` at `0x18002da5a`
- `ntdll!NtClose` at `0x18002d764`
- `ntdll!NtClose` at `0x18002db0d`
- `ntdll!NtClose` at `0x18002d764`
- `ntdll!NtClose` at `0x18002db0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d70a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d71b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d82a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d70a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d71b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d82a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d6e2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d6e2`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002d7d5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002d812`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002d7d5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002d812`

## string_xrefs

- `0x18002d67a`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002d790`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002d8a7`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002d94c`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002da71`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002daad`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18002d84d`: `Failed to get final path for {}`

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
  _IO_STATUS_BLOCK *dwCreationDispositiona; // [rsp+20h] [rbp-A1h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-A1h]
  unsigned int v38; // [rsp+40h] [rbp-81h] BYREF
  char *v39; // [rsp+48h] [rbp-79h]
  __int64 v40; // [rsp+50h] [rbp-71h]
  LPWSTR lpszFilePath[2]; // [rsp+58h] [rbp-69h] BYREF
  __int64 v42; // [rsp+68h] [rbp-59h]
  PVOID FileInformation[2]; // [rsp+70h] [rbp-51h] BYREF
  __int64 v44; // [rsp+80h] [rbp-41h]
  LPCWSTR lpFileName[4]; // [rsp+88h] [rbp-39h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-19h] BYREF
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
      std::vector<char>::~vector<char>(FileInformation);
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
    std::vector<char>::~vector<char>(FileInformation);
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
0x18002d610  push    rbp
0x18002d612  push    rbx
0x18002d613  push    rsi
0x18002d614  push    rdi
0x18002d615  push    r12
0x18002d617  push    r13
0x18002d619  push    r14
0x18002d61b  push    r15
0x18002d61d  lea     rbp, [rsp-17h]
0x18002d622  sub     rsp, 0D8h
0x18002d629  mov     [rbp+4Fh+var_C0], 0FFFFFFFFFFFFFFFEh
0x18002d631  mov     rax, cs:__security_cookie
0x18002d638  xor     rax, rsp
0x18002d63b  mov     [rbp+4Fh+var_48], rax
0x18002d63f  mov     edi, r9d
0x18002d642  mov     r15, r8
0x18002d645  mov     rsi, rdx
0x18002d648  mov     rbx, rcx
0x18002d64b  xor     r12d, r12d
0x18002d64e  mov     [rbp+4Fh+var_C8], r12
0x18002d652  mov     rdx, rcx
0x18002d655  lea     rcx, [rbp+4Fh+lpFileName]
0x18002d659  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x18002d65e  nop
0x18002d65f  lea     rcx, [rbp+4Fh+lpszFilePath]; this
0x18002d663  call    ??0UnicodeStringBuffer@@QEAA@_K@Z; UnicodeStringBuffer::UnicodeStringBuffer(unsigned __int64)
0x18002d668  nop
0x18002d669  test    rsi, rsi
0x18002d66c  jnz     short loc_18002D68B
0x18002d66e  mov     rcx, [rbp+57h]; this
0x18002d672  mov     ebx, 80004003h
0x18002d677  mov     r9d, ebx; char *
0x18002d67a  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002d681  lea     edx, [rsi+4Bh]; void *
0x18002d684  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d689  jmp     short loc_18002D696
0x18002d68b  cmp     [rbx+8], r12
0x18002d68f  jnz     short loc_18002D6B1
0x18002d691  mov     ebx, 80070057h
0x18002d696  lea     rcx, [rbp+4Fh+lpszFilePath]
0x18002d69a  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x18002d69f  nop
0x18002d6a0  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x18002d6a4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d6a9  nop
0x18002d6aa  mov     eax, ebx
0x18002d6ac  jmp     loc_18002DB24
0x18002d6b1  lea     rcx, [rbp+4Fh+lpFileName]
0x18002d6b5  mov     r13d, 7
0x18002d6bb  cmp     [rbp+4Fh+var_70], r13
0x18002d6bf  cmova   rcx, [rbp+4Fh+lpFileName]; lpFileName
0x18002d6c4  mov     [rsp+110h+hTemplateFile], r12; hTemplateFile
0x18002d6c9  mov     [rsp+110h+dwFlagsAndAttributes], 0A000000h; dwFlagsAndAttributes
0x18002d6d1  lea     r14d, [r13-4]
0x18002d6d5  mov     [rsp+110h+dwCreationDisposition], r14d; int
0x18002d6da  xor     r9d, r9d; lpSecurityAttributes
0x18002d6dd  mov     r8d, r13d; dwShareMode
0x18002d6e0  xor     edx, edx; dwDesiredAccess
0x18002d6e2  call    cs:__imp_CreateFileW
0x18002d6e9  nop     dword ptr [rax+rax+00h]
0x18002d6ee  mov     rbx, rax
0x18002d6f1  mov     [rbp+4Fh+var_C8], rax
0x18002d6f5  inc     rax
0x18002d6f8  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002d6fe  jnz     loc_18002D7C1
0x18002d704  cmp     [rbp+4Fh+arg_20], r12b
0x18002d708  jz      short loc_18002D780
0x18002d70a  call    cs:__imp_GetLastError
0x18002d711  nop     dword ptr [rax+rax+00h]
0x18002d716  cmp     eax, 2
0x18002d719  jz      short loc_18002D72C
0x18002d71b  call    cs:__imp_GetLastError
0x18002d722  nop     dword ptr [rax+rax+00h]
0x18002d727  cmp     eax, r14d
0x18002d72a  jnz     short loc_18002D780
0x18002d72c  lea     rax, [rbx+1]
0x18002d730  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002d736  jnz     loc_18002D7C1
0x18002d73c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002d741  mov     edi, eax
0x18002d743  lea     rcx, [rbp+4Fh+lpszFilePath]
0x18002d747  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x18002d74c  nop
0x18002d74d  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x18002d751  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d756  nop
0x18002d757  lea     rdx, [rbx-1]
0x18002d75b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002d75f  ja      short loc_18002D779
0x18002d761  mov     rcx, rbx; Handle
0x18002d764  call    cs:__imp_NtClose
0x18002d76b  nop     dword ptr [rax+rax+00h]
0x18002d770  test    eax, eax
0x18002d772  jns     short loc_18002D779
0x18002d774  mov     rcx, r13
0x18002d777  int     29h; Win8: RtlFailFast(ecx)
0x18002d779  mov     eax, edi
0x18002d77b  jmp     loc_18002DB24
0x18002d780  lea     rax, [rbx+1]
0x18002d784  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002d78a  jnz     short loc_18002D7C1
0x18002d78c  mov     rcx, [rbp+57h]; this
0x18002d790  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002d797  mov     edx, 5Dh ; ']'; void *
0x18002d79c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d7a1  mov     edi, eax
0x18002d7a3  lea     rcx, [rbp+4Fh+lpszFilePath]
0x18002d7a7  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x18002d7ac  nop
0x18002d7ad  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x18002d7b1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d7b6  nop
0x18002d7b7  lea     rcx, [rbx-1]
0x18002d7bb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002d7bf  jmp     short loc_18002D75F
0x18002d7c1  mov     rdx, [rbp+4Fh+lpszFilePath]; lpszFilePath
0x18002d7c5  mov     r8, [rbp+4Fh+var_A8]
0x18002d7c9  sub     r8, rdx
0x18002d7cc  sar     r8, 1; cchFilePath
0x18002d7cf  mov     r9d, edi; dwFlags
0x18002d7d2  mov     rcx, rbx; hFile
0x18002d7d5  call    cs:__imp_GetFinalPathNameByHandleW
0x18002d7dc  nop     dword ptr [rax+rax+00h]
0x18002d7e1  mov     rcx, [rbp+4Fh+var_A8]
0x18002d7e5  mov     rdx, [rbp+4Fh+lpszFilePath]
0x18002d7e9  sub     rcx, rdx
0x18002d7ec  sar     rcx, 1
0x18002d7ef  cmp     eax, ecx
0x18002d7f1  jb      short loc_18002D822
0x18002d7f3  mov     edx, eax; unsigned __int64
0x18002d7f5  lea     rcx, [rbp+4Fh+lpszFilePath]; this
0x18002d7f9  call    ?resize@UnicodeStringBuffer@@QEAAX_K@Z; UnicodeStringBuffer::resize(unsigned __int64)
0x18002d7fe  mov     rdx, [rbp+4Fh+lpszFilePath]; lpszFilePath
0x18002d802  mov     r8, [rbp+4Fh+var_A8]
0x18002d806  sub     r8, rdx
0x18002d809  sar     r8, 1; cchFilePath
0x18002d80c  mov     r9d, edi; dwFlags
0x18002d80f  mov     rcx, rbx; hFile
0x18002d812  call    cs:__imp_GetFinalPathNameByHandleW
0x18002d819  nop     dword ptr [rax+rax+00h]
0x18002d81e  mov     rdx, [rbp+4Fh+lpszFilePath]
0x18002d822  test    eax, eax
0x18002d824  jnz     loc_18002D8EC
0x18002d82a  call    cs:__imp_GetLastError
0x18002d831  nop     dword ptr [rax+rax+00h]
0x18002d836  mov     edi, eax
0x18002d838  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18002d83f  test    rcx, rcx
0x18002d842  jz      short loc_18002D89C
0x18002d844  lea     rax, [rbp+4Fh+lpFileName]
0x18002d848  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x18002d84d  lea     r9, aFailedToGetFin; "Failed to get final path for {}"
0x18002d854  mov     r8d, r14d
0x18002d857  xor     edx, edx
0x18002d859  call    ??$LogNumObjects@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::Logger::LogNumObjects<std::wstring>(bool,LogAdapter::LogLevel,char const * const,std::wstring const &)
0x18002d85e  test    edi, edi
0x18002d860  jg      short loc_18002D866
0x18002d862  mov     eax, edi
0x18002d864  jmp     short loc_18002D86E
0x18002d866  movzx   eax, di
0x18002d869  or      eax, 80070000h
0x18002d86e  mov     [rsp+110h+var_D0], eax
0x18002d872  lea     rax, [rsp+110h+var_D0]
0x18002d877  mov     qword ptr [rbp+4Fh+IoStatusBlock], rax
0x18002d87b  lea     rax, [rbp+4Fh+IoStatusBlock]
0x18002d87f  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; unsigned int
0x18002d884  lea     r9, a0; ": {0}"
0x18002d88b  mov     r8d, r14d
0x18002d88e  mov     dl, 1
0x18002d890  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18002d897  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18002d89c  test    edi, edi
0x18002d89e  jz      short loc_18002D8D3
0x18002d8a0  mov     rcx, [rbp+57h]; this
0x18002d8a4  mov     r9d, edi; char *
0x18002d8a7  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002d8ae  mov     edx, 70h ; 'p'; void *
0x18002d8b3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d8b8  mov     edi, eax
0x18002d8ba  lea     rcx, [rbp+4Fh+lpszFilePath]
0x18002d8be  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x18002d8c3  nop
0x18002d8c4  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x18002d8c8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d8cd  nop
0x18002d8ce  jmp     loc_18002D761
0x18002d8d3  lea     rcx, [rbp+4Fh+lpszFilePath]
0x18002d8d7  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x18002d8dc  nop
0x18002d8dd  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x18002d8e1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d8e6  nop
0x18002d8e7  jmp     loc_18002DB0A
0x18002d8ec  test    dil, 2
0x18002d8f0  jz      loc_18002D9C2
0x18002d8f6  xorps   xmm0, xmm0
0x18002d8f9  xor     eax, eax
0x18002d8fb  movups  xmmword ptr [rbp+4Fh+FileInformation], xmm0
0x18002d8ff  mov     [rbp+4Fh+var_90], rax
0x18002d903  test    rdx, rdx
0x18002d906  jz      short loc_18002D91F
0x18002d908  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002d90c  inc     r8
0x18002d90f  cmp     [rdx+r8*2], r12w
0x18002d914  jnz     short loc_18002D90C
0x18002d916  add     r8, r8
0x18002d919  lea     rax, [r8+2]
0x18002d91d  jmp     short loc_18002D928
0x18002d91f  mov     rdx, r12
0x18002d922  mov     r8, r12
0x18002d925  mov     rax, r12
0x18002d928  mov     qword ptr [rbp+4Fh+IoStatusBlock], r8
0x18002d92c  mov     [rbp+4Fh+IoStatusBlock.Information], rax
0x18002d930  mov     [rbp+4Fh+var_58], rdx
0x18002d934  lea     rdx, [rbp+4Fh+FileInformation]
0x18002d938  lea     rcx, [rbp+4Fh+IoStatusBlock]
0x18002d93c  call    RtlConvertNtFilePathToWin32FilePath
0x18002d941  test    eax, eax
0x18002d943  jns     short loc_18002D98F
0x18002d945  mov     rcx, [rbp+57h]; this
0x18002d949  mov     r9d, eax; char *
0x18002d94c  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002d953  mov     edx, 78h ; 'x'; void *
0x18002d958  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002d95d  mov     edi, eax
0x18002d95f  mov     rcx, [rbp+4Fh+var_90]
0x18002d963  test    rcx, rcx
0x18002d966  jz      short loc_18002D96E
0x18002d968  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18002d96d  nop
0x18002d96e  lea     rcx, [rbp+4Fh+lpszFilePath]
0x18002d972  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x18002d977  nop
0x18002d978  lea     rcx, [rbp+4Fh+lpFileName]; void *
0x18002d97c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d981  nop
0x18002d982  lea     rax, [rbx-1]
0x18002d986  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d98a  jmp     loc_18002D75F
0x18002d98f  lea     rdx, [rbp+4Fh+FileInformation]
0x18002d993  lea     rcx, [rbp+4Fh+IoStatusBlock]
0x18002d997  call    ?to_wstring@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_LUNICODE_STRING@@@Z; to_wstring(_LUNICODE_STRING const &)
0x18002d99c  mov     rdx, rax
0x18002d99f  mov     rcx, rsi
0x18002d9a2  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002d9a7  lea     rcx, [rbp+4Fh+IoStatusBlock]; void *
0x18002d9ab  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d9b0  nop
0x18002d9b1  mov     rcx, [rbp+4Fh+var_90]
0x18002d9b5  test    rcx, rcx
0x18002d9b8  jz      short loc_18002D9C0
0x18002d9ba  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18002d9bf  nop
0x18002d9c0  jmp     short loc_18002D9D8
0x18002d9c2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002d9c6  inc     r8
0x18002d9c9  cmp     [rdx+r8*2], r12w
0x18002d9ce  jnz     short loc_18002D9C6
0x18002d9d0  mov     rcx, rsi
0x18002d9d3  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18002d9d8  test    r15, r15
0x18002d9db  jz      loc_18002DAEC
0x18002d9e1  xorps   xmm0, xmm0
0x18002d9e4  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x18002d9e8  xorps   xmm1, xmm1
0x18002d9eb  movdqu  xmmword ptr [rbp+4Fh+FileInformation], xmm1
0x18002d9f0  mov     [rbp+4Fh+var_90], r12
0x18002d9f4  mov     edi, 210h
0x18002d9f9  mov     edx, edi
0x18002d9fb  lea     rcx, [rbp+4Fh+FileInformation]
0x18002d9ff  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18002da04  mov     r14, [rbp+4Fh+FileInformation]
0x18002da08  mov     [rsp+110h+dwCreationDisposition], 9; FileInformationClass
0x18002da10  mov     r9d, edi; Length
0x18002da13  mov     r8, r14; FileInformation
0x18002da16  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18002da1a  mov     rcx, rbx; FileHandle
0x18002da1d  call    cs:__imp_NtQueryInformationFile
0x18002da24  nop     dword ptr [rax+rax+00h]
0x18002da29  cmp     eax, 80000005h
0x18002da2e  jnz     short loc_18002DA66
0x18002da30  mov     edi, [r14]
0x18002da33  add     edi, 8
0x18002da36  mov     edx, edi
0x18002da38  lea     rcx, [rbp+4Fh+FileInformation]
0x18002da3c  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18002da41  mov     r14, [rbp+4Fh+FileInformation]
0x18002da45  mov     [rsp+110h+dwCreationDisposition], 9; int
0x18002da4d  mov     r9d, edi; Length
0x18002da50  mov     r8, r14; FileInformation
0x18002da53  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18002da57  mov     rcx, rbx; FileHandle
0x18002da5a  call    cs:__imp_NtQueryInformationFile
0x18002da61  nop     dword ptr [rax+rax+00h]
0x18002da66  test    eax, eax
0x18002da68  jns     short loc_18002DA92
0x18002da6a  mov     rcx, [rbp+57h]; this
0x18002da6e  mov     r9d, eax; char *
0x18002da71  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002da78  mov     edx, 0A1h; void *
  ... truncated ...
```
