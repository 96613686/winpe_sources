# FileExecutableArchitecture

- ea: `0x18004b5d4`
- end: `0x18004bba7`
- name: `FileExecutableArchitecture`
- size: `1491`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180043520`

## callees

- `0x18000ea3c`
- `0x18001e51c`
- `0x1800293a0`
- `0x18003d7d4`
- `0x180041a74`
- `0x180041de8`
- `0x180043c00`
- `0x180044bcc`
- `0x18004ab48`
- `0x18004b5d4`
- `0x180099cb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004b769`
- `KERNEL32!GetLastError` at `0x18004b819`
- `KERNEL32!GetLastError` at `0x18004b953`
- `KERNEL32!GetLastError` at `0x18004ba02`
- `KERNEL32!GetLastError` at `0x18004b769`
- `KERNEL32!GetLastError` at `0x18004b819`
- `KERNEL32!GetLastError` at `0x18004b953`
- `KERNEL32!GetLastError` at `0x18004ba02`
- `KERNEL32!CreateFileW` at `0x18004b73b`
- `KERNEL32!CreateFileW` at `0x18004b73b`
- `KERNEL32!ReadFile` at `0x18004b805`
- `KERNEL32!ReadFile` at `0x18004b9ee`
- `KERNEL32!ReadFile` at `0x18004b805`
- `KERNEL32!ReadFile` at `0x18004b9ee`
- `KERNEL32!SetFilePointer` at `0x18004b93e`
- `KERNEL32!SetFilePointer` at `0x18004b93e`

## string_xrefs

- `0x18004b788`: `Failed to open file: {}`
- `0x18004b838`: `Failed to read DOS header from file: {}`
- `0x18004b8d7`: `Read invalid DOS header from file: {}`
- `0x18004ba21`: `Failed to read NT header from file: {}`
- `0x18004baa5`: `Read invalid NT header from file: {}`

## pseudocode

```c
__int64 __fastcall FileExecutableArchitecture(LPCWSTR lpFileName, _WORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  HANDLE FileW; // rax
  HANDLE v9; // rbx
  int v10; // edx
  signed int LastError; // ebx
  int v12; // r8d
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // edx
  int v17; // r8d
  int v18; // edx
  int v19; // r8d
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  int v24; // edx
  int v25; // r8d
  __int64 v26; // rdx
  unsigned int v27; // eax
  int v28; // edx
  int v29; // r8d
  int v30; // edx
  int v31; // r8d
  __int64 v32; // rdx
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  unsigned int v39[2]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v41; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+58h] [rbp-A8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+5Ch] [rbp-A4h] BYREF
  LONG Buffer[16]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v45[68]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v41 = lpFileName;
  NumberOfBytesRead = 0;
  memset(Buffer, 0, sizeof(Buffer));
  memset(v45, 0, 0x108u);
  if ( lpFileName )
  {
    if ( !a2 )
    {
      v4 = -2147467261;
      v42 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No architecture result specified");
        hFile = &v42;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v7,
          3,
          (__int64)": {}",
          (__int64)&hFile);
      }
      v6 = 180;
      goto LABEL_5;
    }
    hFile = 0;
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      &hFile,
      FileW);
    v9 = hFile;
    if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      if ( ReadFile(hFile, Buffer, 0x40u, &NumberOfBytesRead, 0) )
      {
        if ( LOWORD(Buffer[0]) == 23117 )
        {
          if ( SetFilePointer(v9, Buffer[15], 0, 0) == -1 )
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                v24,
                v25,
                (unsigned int)"Failed to seek the NT header in file: {}",
                (__int64)&v41);
              if ( LastError > 0 )
                v27 = (unsigned __int16)LastError | 0x80070000;
              else
                v27 = LastError;
              v42 = v27;
              *(_QWORD *)v39 = &v42;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v26,
                3,
                (__int64)": {0}",
                (__int64)v39);
            }
            if ( LastError )
            {
              v15 = 196;
              goto LABEL_26;
            }
            goto LABEL_61;
          }
          if ( !ReadFile(v9, v45, 0x108u, &NumberOfBytesRead, 0) )
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                v30,
                v31,
                (unsigned int)"Failed to read NT header from file: {}",
                (__int64)&v41);
              if ( LastError > 0 )
                v33 = (unsigned __int16)LastError | 0x80070000;
              else
                v33 = LastError;
              v42 = v33;
              *(_QWORD *)v39 = &v42;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v32,
                3,
                (__int64)": {0}",
                (__int64)v39);
            }
            if ( LastError )
            {
              v15 = 199;
              goto LABEL_26;
            }
            goto LABEL_61;
          }
          if ( v45[0] == 17744 )
          {
            if ( LOWORD(v45[23]) == 1
              || LOWORD(v45[23]) == 2
              || LOWORD(v45[23]) == 3
              || LOWORD(v45[23]) != 5 && LOWORD(v45[23]) != 7 )
            {
              *a2 = v45[1];
              goto LABEL_61;
            }
            v4 = -2147024885;
            v42 = -2147024885;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<unsigned short,wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                v28,
                v29,
                (unsigned int)"Unexpected subsystem: {} specified in NT header from file: {}",
                (__int64)&v45[23],
                (__int64)&v41);
              *(_QWORD *)v39 = &v42;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v35,
                3,
                (__int64)": {}",
                (__int64)v39);
            }
            v23 = 221;
          }
          else
          {
            v4 = -2147024885;
            v42 = -2147024885;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                v28,
                v29,
                (unsigned int)"Read invalid NT header from file: {}",
                (__int64)&v41);
              *(_QWORD *)v39 = &v42;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                v34,
                3,
                (__int64)": {}",
                (__int64)v39);
            }
            v23 = 202;
          }
        }
        else
        {
          v4 = -2147024885;
          v42 = -2147024885;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              v16,
              v17,
              (unsigned int)"Read invalid DOS header from file: {}",
              (__int64)&v41);
            *(_QWORD *)v39 = &v42;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v22,
              3,
              (__int64)": {}",
              (__int64)v39);
          }
          v23 = 193;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)0x8007000BLL,
          dwCreationDispositiona);
        goto LABEL_62;
      }
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          v18,
          v19,
          (unsigned int)"Failed to read DOS header from file: {}",
          (__int64)&v41);
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
        else
          v21 = LastError;
        v42 = v21;
        *(_QWORD *)v39 = &v42;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v20,
          3,
          (__int64)": {0}",
          (__int64)v39);
      }
      if ( LastError )
      {
        v15 = 190;
        goto LABEL_26;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          v10,
          v12,
          (unsigned int)"Failed to open file: {}",
          (__int64)&v41);
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        else
          v14 = LastError;
        v42 = v14;
        *(_QWORD *)v39 = &v42;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v13,
          3,
          (__int64)": {0}",
          (__int64)v39);
      }
      if ( LastError )
      {
        v15 = 186;
LABEL_26:
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v15,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)(unsigned int)LastError,
               dwCreationDispositiona);
LABEL_62:
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
        return v4;
      }
    }
LABEL_61:
    v4 = 0;
    goto LABEL_62;
  }
  v4 = -2147024809;
  v42 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file specified");
    hFile = &v42;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v5,
      3,
      (__int64)": {}",
      (__int64)&hFile);
  }
  v6 = 179;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)v4,
    dwCreationDisposition);
  return v4;
}

```

## disassembly

```asm
0x18004b5d4  mov     [rsp-8+arg_10], rbx
0x18004b5d9  push    rbp
0x18004b5da  push    rsi
0x18004b5db  push    rdi
0x18004b5dc  lea     rbp, [rsp-0C0h]
0x18004b5e4  sub     rsp, 1C0h
0x18004b5eb  mov     rax, cs:__security_cookie
0x18004b5f2  xor     rax, rsp
0x18004b5f5  mov     [rbp+0D0h+var_20], rax
0x18004b5fc  mov     rsi, rdx
0x18004b5ff  mov     [rsp+1D0h+var_180], rcx
0x18004b604  xor     edx, edx; Val
0x18004b606  mov     [rsp+1D0h+NumberOfBytesRead], 0
0x18004b60e  mov     rbx, rcx
0x18004b611  lea     rcx, [rsp+1D0h+Buffer]; void *
0x18004b616  lea     r8d, [rdx+40h]; Size
0x18004b61a  call    memset
0x18004b61f  xor     edx, edx; Val
0x18004b621  lea     rcx, [rbp+0D0h+var_130]; void *
0x18004b625  mov     r8d, 108h; Size
0x18004b62b  call    memset
0x18004b630  test    rbx, rbx
0x18004b633  jnz     short loc_18004B6AA
0x18004b635  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b63c  mov     ebx, 80070057h
0x18004b641  mov     [rsp+1D0h+var_178], ebx
0x18004b645  test    rcx, rcx
0x18004b648  jz      short loc_18004B68A
0x18004b64a  mov     edi, 3
0x18004b64f  lea     r9, aNoFileSpecifie; "No file specified"
0x18004b656  mov     r8d, edi
0x18004b659  xor     edx, edx
0x18004b65b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004b660  lea     rcx, [rsp+1D0h+hFile]
0x18004b665  mov     r8d, edi
0x18004b668  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rcx; int
0x18004b66d  lea     rax, [rsp+1D0h+var_178]
0x18004b672  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b679  lea     r9, asc_1800AFB70; ": {}"
0x18004b680  mov     [rsp+1D0h+hFile], rax
0x18004b685  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004b68a  mov     edx, 0B3h; void *
0x18004b68f  mov     rcx, [rbp+0D8h]; this
0x18004b696  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004b69d  mov     r9d, ebx; char *
0x18004b6a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b6a5  jmp     loc_18004BB82
0x18004b6aa  test    rsi, rsi
0x18004b6ad  jnz     short loc_18004B709
0x18004b6af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b6b6  mov     ebx, 80004003h
0x18004b6bb  mov     [rsp+1D0h+var_178], ebx
0x18004b6bf  test    rcx, rcx
0x18004b6c2  jz      short loc_18004B702
0x18004b6c4  lea     edi, [rsi+3]
0x18004b6c7  xor     edx, edx
0x18004b6c9  mov     r8d, edi
0x18004b6cc  lea     r9, aNoArchitecture; "No architecture result specified"
0x18004b6d3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004b6d8  lea     rcx, [rsp+1D0h+hFile]
0x18004b6dd  mov     r8d, edi
0x18004b6e0  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rcx
0x18004b6e5  lea     rax, [rsp+1D0h+var_178]
0x18004b6ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b6f1  lea     r9, asc_1800AFB70; ": {}"
0x18004b6f8  mov     [rsp+1D0h+hFile], rax
0x18004b6fd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004b702  mov     edx, 0B4h
0x18004b707  jmp     short loc_18004B68F
0x18004b709  mov     edi, 3
0x18004b70e  mov     [rsp+1D0h+hTemplateFile], 0; hTemplateFile
0x18004b717  mov     [rsp+1D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004b71f  xor     r9d, r9d; lpSecurityAttributes
0x18004b722  mov     edx, 80000000h; dwDesiredAccess
0x18004b727  mov     [rsp+1D0h+hFile], 0
0x18004b730  mov     rcx, rbx; lpFileName
0x18004b733  mov     [rsp+1D0h+dwCreationDisposition], edi; dwCreationDisposition
0x18004b737  lea     r8d, [rdi-2]; dwShareMode
0x18004b73b  call    cs:__imp_CreateFileW
0x18004b742  nop     dword ptr [rax+rax+00h]
0x18004b747  mov     rdx, rax
0x18004b74a  lea     rcx, [rsp+1D0h+hFile]
0x18004b74f  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18004b754  mov     rbx, [rsp+1D0h+hFile]
0x18004b759  lea     rax, [rbx+1]
0x18004b75d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004b763  jnz     loc_18004B7E9
0x18004b769  call    cs:__imp_GetLastError
0x18004b770  nop     dword ptr [rax+rax+00h]
0x18004b775  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b77c  mov     ebx, eax
0x18004b77e  test    rcx, rcx
0x18004b781  jz      short loc_18004B7D7
0x18004b783  lea     rax, [rsp+1D0h+var_180]
0x18004b788  lea     r9, aFailedToOpenFi; "Failed to open file: {}"
0x18004b78f  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004b794  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004b799  test    ebx, ebx
0x18004b79b  jg      short loc_18004B7A1
0x18004b79d  mov     eax, ebx
0x18004b79f  jmp     short loc_18004B7A9
0x18004b7a1  movzx   eax, bx
0x18004b7a4  or      eax, 80070000h
0x18004b7a9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b7b0  lea     r9, a0; ": {0}"
0x18004b7b7  mov     [rsp+1D0h+var_178], eax
0x18004b7bb  mov     r8d, edi
0x18004b7be  lea     rax, [rsp+1D0h+var_178]
0x18004b7c3  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004b7c8  lea     rax, [rsp+1D0h+var_190]
0x18004b7cd  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004b7d2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004b7d7  test    ebx, ebx
0x18004b7d9  jz      loc_18004BB76
0x18004b7df  mov     edx, 0BAh
0x18004b7e4  jmp     loc_18004B894
0x18004b7e9  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004b7ee  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x18004b7f7  mov     r8d, 40h ; '@'; nNumberOfBytesToRead
0x18004b7fd  lea     rdx, [rsp+1D0h+Buffer]; lpBuffer
0x18004b802  mov     rcx, rbx; hFile
0x18004b805  call    cs:__imp_ReadFile
0x18004b80c  nop     dword ptr [rax+rax+00h]
0x18004b811  test    eax, eax
0x18004b813  jnz     loc_18004B8B1
0x18004b819  call    cs:__imp_GetLastError
0x18004b820  nop     dword ptr [rax+rax+00h]
0x18004b825  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b82c  mov     ebx, eax
0x18004b82e  test    rcx, rcx
0x18004b831  jz      short loc_18004B887
0x18004b833  lea     rax, [rsp+1D0h+var_180]
0x18004b838  lea     r9, aFailedToReadDo; "Failed to read DOS header from file: {}"
0x18004b83f  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004b844  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004b849  test    ebx, ebx
0x18004b84b  jg      short loc_18004B851
0x18004b84d  mov     eax, ebx
0x18004b84f  jmp     short loc_18004B859
0x18004b851  movzx   eax, bx
0x18004b854  or      eax, 80070000h
0x18004b859  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b860  lea     r9, a0; ": {0}"
0x18004b867  mov     [rsp+1D0h+var_178], eax
0x18004b86b  mov     r8d, edi
0x18004b86e  lea     rax, [rsp+1D0h+var_178]
0x18004b873  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004b878  lea     rax, [rsp+1D0h+var_190]
0x18004b87d  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax; unsigned int
0x18004b882  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004b887  test    ebx, ebx
0x18004b889  jz      loc_18004BB76
0x18004b88f  mov     edx, 0BEh; void *
0x18004b894  mov     rcx, [rbp+0D8h]; this
0x18004b89b  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004b8a2  mov     r9d, ebx; char *
0x18004b8a5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b8aa  mov     ebx, eax
0x18004b8ac  jmp     loc_18004BB78
0x18004b8b1  mov     eax, 5A4Dh
0x18004b8b6  cmp     [rsp+1D0h+Buffer], ax
0x18004b8bb  jz      short loc_18004B932
0x18004b8bd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b8c4  mov     ebx, 8007000Bh
0x18004b8c9  mov     [rsp+1D0h+var_178], ebx
0x18004b8cd  test    rcx, rcx
0x18004b8d0  jz      short loc_18004B912
0x18004b8d2  lea     rax, [rsp+1D0h+var_180]
0x18004b8d7  lea     r9, aReadInvalidDos; "Read invalid DOS header from file: {}"
0x18004b8de  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004b8e3  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004b8e8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b8ef  lea     rax, [rsp+1D0h+var_178]
0x18004b8f4  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004b8f9  lea     r9, asc_1800AFB70; ": {}"
0x18004b900  lea     rax, [rsp+1D0h+var_190]
0x18004b905  mov     r8d, edi
0x18004b908  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax; int
0x18004b90d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004b912  mov     edx, 0C1h; void *
0x18004b917  mov     rcx, [rbp+0D8h]; this
0x18004b91e  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004b925  mov     r9d, ebx; char *
0x18004b928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b92d  jmp     loc_18004BB78
0x18004b932  mov     edx, [rbp+0D0h+lDistanceToMove]; lDistanceToMove
0x18004b935  xor     r9d, r9d; dwMoveMethod
0x18004b938  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004b93b  mov     rcx, rbx; hFile
0x18004b93e  call    cs:__imp_SetFilePointer
0x18004b945  nop     dword ptr [rax+rax+00h]
0x18004b94a  cmp     eax, 0FFFFFFFFh
0x18004b94d  jnz     loc_18004B9D3
0x18004b953  call    cs:__imp_GetLastError
0x18004b95a  nop     dword ptr [rax+rax+00h]
0x18004b95f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b966  mov     ebx, eax
0x18004b968  test    rcx, rcx
0x18004b96b  jz      short loc_18004B9C1
0x18004b96d  lea     rax, [rsp+1D0h+var_180]
0x18004b972  lea     r9, aFailedToSeekTh; "Failed to seek the NT header in file: {"...
0x18004b979  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004b97e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004b983  test    ebx, ebx
0x18004b985  jg      short loc_18004B98B
0x18004b987  mov     eax, ebx
0x18004b989  jmp     short loc_18004B993
0x18004b98b  movzx   eax, bx
0x18004b98e  or      eax, 80070000h
0x18004b993  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004b99a  lea     r9, a0; ": {0}"
0x18004b9a1  mov     [rsp+1D0h+var_178], eax
0x18004b9a5  mov     r8d, edi
0x18004b9a8  lea     rax, [rsp+1D0h+var_178]
0x18004b9ad  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004b9b2  lea     rax, [rsp+1D0h+var_190]
0x18004b9b7  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004b9bc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004b9c1  test    ebx, ebx
0x18004b9c3  jz      loc_18004BB76
0x18004b9c9  mov     edx, 0C4h
0x18004b9ce  jmp     loc_18004B894
0x18004b9d3  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004b9d8  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x18004b9e1  mov     r8d, 108h; nNumberOfBytesToRead
0x18004b9e7  lea     rdx, [rbp+0D0h+var_130]; lpBuffer
0x18004b9eb  mov     rcx, rbx; hFile
0x18004b9ee  call    cs:__imp_ReadFile
0x18004b9f5  nop     dword ptr [rax+rax+00h]
0x18004b9fa  test    eax, eax
0x18004b9fc  jnz     loc_18004BA82
0x18004ba02  call    cs:__imp_GetLastError
0x18004ba09  nop     dword ptr [rax+rax+00h]
0x18004ba0e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004ba15  mov     ebx, eax
0x18004ba17  test    rcx, rcx
0x18004ba1a  jz      short loc_18004BA70
0x18004ba1c  lea     rax, [rsp+1D0h+var_180]
0x18004ba21  lea     r9, aFailedToReadNt; "Failed to read NT header from file: {}"
0x18004ba28  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004ba2d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004ba32  test    ebx, ebx
0x18004ba34  jg      short loc_18004BA3A
0x18004ba36  mov     eax, ebx
0x18004ba38  jmp     short loc_18004BA42
0x18004ba3a  movzx   eax, bx
0x18004ba3d  or      eax, 80070000h
0x18004ba42  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004ba49  lea     r9, a0; ": {0}"
0x18004ba50  mov     [rsp+1D0h+var_178], eax
0x18004ba54  mov     r8d, edi
0x18004ba57  lea     rax, [rsp+1D0h+var_178]
0x18004ba5c  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004ba61  lea     rax, [rsp+1D0h+var_190]
0x18004ba66  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004ba6b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004ba70  test    ebx, ebx
0x18004ba72  jz      loc_18004BB76
0x18004ba78  mov     edx, 0C7h
0x18004ba7d  jmp     loc_18004B894
0x18004ba82  cmp     [rbp+0D0h+var_130], 4550h
0x18004ba89  jz      short loc_18004BAEA
0x18004ba8b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004ba92  mov     ebx, 8007000Bh
0x18004ba97  mov     [rsp+1D0h+var_178], ebx
0x18004ba9b  test    rcx, rcx
0x18004ba9e  jz      short loc_18004BAE0
0x18004baa0  lea     rax, [rsp+1D0h+var_180]
0x18004baa5  lea     r9, aReadInvalidNtH; "Read invalid NT header from file: {}"
0x18004baac  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004bab1  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004bab6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004babd  lea     rax, [rsp+1D0h+var_178]
0x18004bac2  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004bac7  lea     r9, asc_1800AFB70; ": {}"
0x18004bace  lea     rax, [rsp+1D0h+var_190]
0x18004bad3  mov     r8d, edi
0x18004bad6  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004badb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004bae0  mov     edx, 0CAh
0x18004bae5  jmp     loc_18004B917
0x18004baea  movzx   ecx, [rbp+0D0h+var_D4]
0x18004baee  sub     ecx, 1
0x18004baf1  jz      short loc_18004BB6F
0x18004baf3  sub     ecx, 1
0x18004baf6  jz      short loc_18004BB6F
0x18004baf8  sub     ecx, 1
0x18004bafb  jz      short loc_18004BB6F
0x18004bafd  sub     ecx, 2
0x18004bb00  jz      short loc_18004BB07
0x18004bb02  cmp     ecx, 2
0x18004bb05  jnz     short loc_18004BB6F
0x18004bb07  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004bb0e  mov     ebx, 8007000Bh
0x18004bb13  mov     [rsp+1D0h+var_178], ebx
0x18004bb17  test    rcx, rcx
0x18004bb1a  jz      short loc_18004BB65
0x18004bb1c  lea     rax, [rsp+1D0h+var_180]
0x18004bb21  mov     qword ptr [rsp+1D0h+dwFlagsAndAttributes], rax
0x18004bb26  lea     r9, aUnexpectedSubs; "Unexpected subsystem: {} specified in N"...
  ... truncated ...
```
