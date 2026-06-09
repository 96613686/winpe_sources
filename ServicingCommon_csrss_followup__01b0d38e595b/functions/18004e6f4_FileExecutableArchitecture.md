# FileExecutableArchitecture

- ea: `0x18004e6f4`
- end: `0x18004ecc7`
- name: `FileExecutableArchitecture`
- size: `1491`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180046170`

## callees

- `0x180018df0`
- `0x180020440`
- `0x18002d2b0`
- `0x180046650`
- `0x180046bb4`
- `0x180046ca4`
- `0x180047c5c`
- `0x180047d5c`
- `0x18004dc68`
- `0x18004e6f4`
- `0x180097e20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004e889`
- `KERNEL32!GetLastError` at `0x18004e939`
- `KERNEL32!GetLastError` at `0x18004ea73`
- `KERNEL32!GetLastError` at `0x18004eb22`
- `KERNEL32!GetLastError` at `0x18004e889`
- `KERNEL32!GetLastError` at `0x18004e939`
- `KERNEL32!GetLastError` at `0x18004ea73`
- `KERNEL32!GetLastError` at `0x18004eb22`
- `KERNEL32!CreateFileW` at `0x18004e85b`
- `KERNEL32!CreateFileW` at `0x18004e85b`
- `KERNEL32!ReadFile` at `0x18004e925`
- `KERNEL32!ReadFile` at `0x18004eb0e`
- `KERNEL32!ReadFile` at `0x18004e925`
- `KERNEL32!ReadFile` at `0x18004eb0e`
- `KERNEL32!SetFilePointer` at `0x18004ea5e`
- `KERNEL32!SetFilePointer` at `0x18004ea5e`

## string_xrefs

- `0x18004e8a8`: `Failed to open file: {}`
- `0x18004e958`: `Failed to read DOS header from file: {}`
- `0x18004e9f7`: `Read invalid DOS header from file: {}`
- `0x18004eb41`: `Failed to read NT header from file: {}`
- `0x18004ebc5`: `Read invalid NT header from file: {}`

## pseudocode

```c
__int64 __fastcall FileExecutableArchitecture(LPCWSTR lpFileName, _WORD *a2)
{
  unsigned int v4; // ebx
  int v5; // edx
  __int64 v6; // rdx
  int v7; // edx
  HANDLE FileW; // rax
  HANDLE v9; // rbx
  int v10; // edx
  signed int LastError; // ebx
  int v12; // r8d
  int v13; // edx
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // edx
  int v17; // r8d
  int v18; // edx
  int v19; // r8d
  int v20; // edx
  unsigned int v21; // eax
  int v22; // edx
  __int64 v23; // rdx
  int v24; // edx
  int v25; // r8d
  int v26; // edx
  unsigned int v27; // eax
  int v28; // edx
  int v29; // r8d
  int v30; // edx
  int v31; // r8d
  int v32; // edx
  unsigned int v33; // eax
  int v34; // edx
  int v35; // edx
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
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No architecture result specified");
        hFile = &v42;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v7,
          3,
          (unsigned int)": {}",
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
                (_DWORD)LogAdapter::g_Logger,
                v26,
                3,
                (unsigned int)": {0}",
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
                (_DWORD)LogAdapter::g_Logger,
                v32,
                3,
                (unsigned int)": {0}",
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
                (_DWORD)LogAdapter::g_Logger,
                v35,
                3,
                (unsigned int)": {}",
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
                (_DWORD)LogAdapter::g_Logger,
                v34,
                3,
                (unsigned int)": {}",
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
              (_DWORD)LogAdapter::g_Logger,
              v22,
              3,
              (unsigned int)": {}",
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
          (_DWORD)LogAdapter::g_Logger,
          v20,
          3,
          (unsigned int)": {0}",
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
          (_DWORD)LogAdapter::g_Logger,
          v13,
          3,
          (unsigned int)": {0}",
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
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file specified");
    hFile = &v42;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v5,
      3,
      (unsigned int)": {}",
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
0x18004e6f4  mov     [rsp-8+arg_10], rbx
0x18004e6f9  push    rbp
0x18004e6fa  push    rsi
0x18004e6fb  push    rdi
0x18004e6fc  lea     rbp, [rsp-0C0h]
0x18004e704  sub     rsp, 1C0h
0x18004e70b  mov     rax, cs:__security_cookie
0x18004e712  xor     rax, rsp
0x18004e715  mov     [rbp+0D0h+var_20], rax
0x18004e71c  mov     rsi, rdx
0x18004e71f  mov     [rsp+1D0h+var_180], rcx
0x18004e724  xor     edx, edx; Val
0x18004e726  mov     [rsp+1D0h+NumberOfBytesRead], 0
0x18004e72e  mov     rbx, rcx
0x18004e731  lea     rcx, [rsp+1D0h+Buffer]; void *
0x18004e736  lea     r8d, [rdx+40h]; Size
0x18004e73a  call    memset
0x18004e73f  xor     edx, edx; Val
0x18004e741  lea     rcx, [rbp+0D0h+var_130]; void *
0x18004e745  mov     r8d, 108h; Size
0x18004e74b  call    memset
0x18004e750  test    rbx, rbx
0x18004e753  jnz     short loc_18004E7CA
0x18004e755  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e75c  mov     ebx, 80070057h
0x18004e761  mov     [rsp+1D0h+var_178], ebx
0x18004e765  test    rcx, rcx
0x18004e768  jz      short loc_18004E7AA
0x18004e76a  mov     edi, 3
0x18004e76f  lea     r9, aNoFileSpecifie; "No file specified"
0x18004e776  mov     r8d, edi
0x18004e779  xor     edx, edx
0x18004e77b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004e780  lea     rcx, [rsp+1D0h+hFile]
0x18004e785  mov     r8d, edi
0x18004e788  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rcx; int
0x18004e78d  lea     rax, [rsp+1D0h+var_178]
0x18004e792  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e799  lea     r9, asc_1800AFAD8; ": {}"
0x18004e7a0  mov     [rsp+1D0h+hFile], rax
0x18004e7a5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e7aa  mov     edx, 0B3h; void *
0x18004e7af  mov     rcx, [rbp+0D8h]; this
0x18004e7b6  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004e7bd  mov     r9d, ebx; char *
0x18004e7c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e7c5  jmp     loc_18004ECA2
0x18004e7ca  test    rsi, rsi
0x18004e7cd  jnz     short loc_18004E829
0x18004e7cf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e7d6  mov     ebx, 80004003h
0x18004e7db  mov     [rsp+1D0h+var_178], ebx
0x18004e7df  test    rcx, rcx
0x18004e7e2  jz      short loc_18004E822
0x18004e7e4  lea     edi, [rsi+3]
0x18004e7e7  xor     edx, edx
0x18004e7e9  mov     r8d, edi
0x18004e7ec  lea     r9, aNoArchitecture; "No architecture result specified"
0x18004e7f3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004e7f8  lea     rcx, [rsp+1D0h+hFile]
0x18004e7fd  mov     r8d, edi
0x18004e800  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rcx
0x18004e805  lea     rax, [rsp+1D0h+var_178]
0x18004e80a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e811  lea     r9, asc_1800AFAD8; ": {}"
0x18004e818  mov     [rsp+1D0h+hFile], rax
0x18004e81d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e822  mov     edx, 0B4h
0x18004e827  jmp     short loc_18004E7AF
0x18004e829  mov     edi, 3
0x18004e82e  mov     [rsp+1D0h+hTemplateFile], 0; hTemplateFile
0x18004e837  mov     [rsp+1D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004e83f  xor     r9d, r9d; lpSecurityAttributes
0x18004e842  mov     edx, 80000000h; dwDesiredAccess
0x18004e847  mov     [rsp+1D0h+hFile], 0
0x18004e850  mov     rcx, rbx; lpFileName
0x18004e853  mov     [rsp+1D0h+dwCreationDisposition], edi; dwCreationDisposition
0x18004e857  lea     r8d, [rdi-2]; dwShareMode
0x18004e85b  call    cs:__imp_CreateFileW
0x18004e862  nop     dword ptr [rax+rax+00h]
0x18004e867  mov     rdx, rax
0x18004e86a  lea     rcx, [rsp+1D0h+hFile]
0x18004e86f  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18004e874  mov     rbx, [rsp+1D0h+hFile]
0x18004e879  lea     rax, [rbx+1]
0x18004e87d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004e883  jnz     loc_18004E909
0x18004e889  call    cs:__imp_GetLastError
0x18004e890  nop     dword ptr [rax+rax+00h]
0x18004e895  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e89c  mov     ebx, eax
0x18004e89e  test    rcx, rcx
0x18004e8a1  jz      short loc_18004E8F7
0x18004e8a3  lea     rax, [rsp+1D0h+var_180]
0x18004e8a8  lea     r9, aFailedToOpenFi; "Failed to open file: {}"
0x18004e8af  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004e8b4  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004e8b9  test    ebx, ebx
0x18004e8bb  jg      short loc_18004E8C1
0x18004e8bd  mov     eax, ebx
0x18004e8bf  jmp     short loc_18004E8C9
0x18004e8c1  movzx   eax, bx
0x18004e8c4  or      eax, 80070000h
0x18004e8c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e8d0  lea     r9, a0; ": {0}"
0x18004e8d7  mov     [rsp+1D0h+var_178], eax
0x18004e8db  mov     r8d, edi
0x18004e8de  lea     rax, [rsp+1D0h+var_178]
0x18004e8e3  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004e8e8  lea     rax, [rsp+1D0h+var_190]
0x18004e8ed  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004e8f2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e8f7  test    ebx, ebx
0x18004e8f9  jz      loc_18004EC96
0x18004e8ff  mov     edx, 0BAh
0x18004e904  jmp     loc_18004E9B4
0x18004e909  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004e90e  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x18004e917  mov     r8d, 40h ; '@'; nNumberOfBytesToRead
0x18004e91d  lea     rdx, [rsp+1D0h+Buffer]; lpBuffer
0x18004e922  mov     rcx, rbx; hFile
0x18004e925  call    cs:__imp_ReadFile
0x18004e92c  nop     dword ptr [rax+rax+00h]
0x18004e931  test    eax, eax
0x18004e933  jnz     loc_18004E9D1
0x18004e939  call    cs:__imp_GetLastError
0x18004e940  nop     dword ptr [rax+rax+00h]
0x18004e945  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e94c  mov     ebx, eax
0x18004e94e  test    rcx, rcx
0x18004e951  jz      short loc_18004E9A7
0x18004e953  lea     rax, [rsp+1D0h+var_180]
0x18004e958  lea     r9, aFailedToReadDo; "Failed to read DOS header from file: {}"
0x18004e95f  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004e964  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004e969  test    ebx, ebx
0x18004e96b  jg      short loc_18004E971
0x18004e96d  mov     eax, ebx
0x18004e96f  jmp     short loc_18004E979
0x18004e971  movzx   eax, bx
0x18004e974  or      eax, 80070000h
0x18004e979  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e980  lea     r9, a0; ": {0}"
0x18004e987  mov     [rsp+1D0h+var_178], eax
0x18004e98b  mov     r8d, edi
0x18004e98e  lea     rax, [rsp+1D0h+var_178]
0x18004e993  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004e998  lea     rax, [rsp+1D0h+var_190]
0x18004e99d  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax; unsigned int
0x18004e9a2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004e9a7  test    ebx, ebx
0x18004e9a9  jz      loc_18004EC96
0x18004e9af  mov     edx, 0BEh; void *
0x18004e9b4  mov     rcx, [rbp+0D8h]; this
0x18004e9bb  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004e9c2  mov     r9d, ebx; char *
0x18004e9c5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004e9ca  mov     ebx, eax
0x18004e9cc  jmp     loc_18004EC98
0x18004e9d1  mov     eax, 5A4Dh
0x18004e9d6  cmp     [rsp+1D0h+Buffer], ax
0x18004e9db  jz      short loc_18004EA52
0x18004e9dd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004e9e4  mov     ebx, 8007000Bh
0x18004e9e9  mov     [rsp+1D0h+var_178], ebx
0x18004e9ed  test    rcx, rcx
0x18004e9f0  jz      short loc_18004EA32
0x18004e9f2  lea     rax, [rsp+1D0h+var_180]
0x18004e9f7  lea     r9, aReadInvalidDos; "Read invalid DOS header from file: {}"
0x18004e9fe  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004ea03  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004ea08  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004ea0f  lea     rax, [rsp+1D0h+var_178]
0x18004ea14  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004ea19  lea     r9, asc_1800AFAD8; ": {}"
0x18004ea20  lea     rax, [rsp+1D0h+var_190]
0x18004ea25  mov     r8d, edi
0x18004ea28  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax; int
0x18004ea2d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004ea32  mov     edx, 0C1h; void *
0x18004ea37  mov     rcx, [rbp+0D8h]; this
0x18004ea3e  lea     r8, aOnecoreBaseCbs_5; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004ea45  mov     r9d, ebx; char *
0x18004ea48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ea4d  jmp     loc_18004EC98
0x18004ea52  mov     edx, [rbp+0D0h+lDistanceToMove]; lDistanceToMove
0x18004ea55  xor     r9d, r9d; dwMoveMethod
0x18004ea58  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004ea5b  mov     rcx, rbx; hFile
0x18004ea5e  call    cs:__imp_SetFilePointer
0x18004ea65  nop     dword ptr [rax+rax+00h]
0x18004ea6a  cmp     eax, 0FFFFFFFFh
0x18004ea6d  jnz     loc_18004EAF3
0x18004ea73  call    cs:__imp_GetLastError
0x18004ea7a  nop     dword ptr [rax+rax+00h]
0x18004ea7f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004ea86  mov     ebx, eax
0x18004ea88  test    rcx, rcx
0x18004ea8b  jz      short loc_18004EAE1
0x18004ea8d  lea     rax, [rsp+1D0h+var_180]
0x18004ea92  lea     r9, aFailedToSeekTh; "Failed to seek the NT header in file: {"...
0x18004ea99  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004ea9e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004eaa3  test    ebx, ebx
0x18004eaa5  jg      short loc_18004EAAB
0x18004eaa7  mov     eax, ebx
0x18004eaa9  jmp     short loc_18004EAB3
0x18004eaab  movzx   eax, bx
0x18004eaae  or      eax, 80070000h
0x18004eab3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004eaba  lea     r9, a0; ": {0}"
0x18004eac1  mov     [rsp+1D0h+var_178], eax
0x18004eac5  mov     r8d, edi
0x18004eac8  lea     rax, [rsp+1D0h+var_178]
0x18004eacd  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004ead2  lea     rax, [rsp+1D0h+var_190]
0x18004ead7  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004eadc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004eae1  test    ebx, ebx
0x18004eae3  jz      loc_18004EC96
0x18004eae9  mov     edx, 0C4h
0x18004eaee  jmp     loc_18004E9B4
0x18004eaf3  lea     r9, [rsp+1D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004eaf8  mov     qword ptr [rsp+1D0h+dwCreationDisposition], 0; lpOverlapped
0x18004eb01  mov     r8d, 108h; nNumberOfBytesToRead
0x18004eb07  lea     rdx, [rbp+0D0h+var_130]; lpBuffer
0x18004eb0b  mov     rcx, rbx; hFile
0x18004eb0e  call    cs:__imp_ReadFile
0x18004eb15  nop     dword ptr [rax+rax+00h]
0x18004eb1a  test    eax, eax
0x18004eb1c  jnz     loc_18004EBA2
0x18004eb22  call    cs:__imp_GetLastError
0x18004eb29  nop     dword ptr [rax+rax+00h]
0x18004eb2e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004eb35  mov     ebx, eax
0x18004eb37  test    rcx, rcx
0x18004eb3a  jz      short loc_18004EB90
0x18004eb3c  lea     rax, [rsp+1D0h+var_180]
0x18004eb41  lea     r9, aFailedToReadNt; "Failed to read NT header from file: {}"
0x18004eb48  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004eb4d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004eb52  test    ebx, ebx
0x18004eb54  jg      short loc_18004EB5A
0x18004eb56  mov     eax, ebx
0x18004eb58  jmp     short loc_18004EB62
0x18004eb5a  movzx   eax, bx
0x18004eb5d  or      eax, 80070000h
0x18004eb62  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004eb69  lea     r9, a0; ": {0}"
0x18004eb70  mov     [rsp+1D0h+var_178], eax
0x18004eb74  mov     r8d, edi
0x18004eb77  lea     rax, [rsp+1D0h+var_178]
0x18004eb7c  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004eb81  lea     rax, [rsp+1D0h+var_190]
0x18004eb86  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004eb8b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004eb90  test    ebx, ebx
0x18004eb92  jz      loc_18004EC96
0x18004eb98  mov     edx, 0C7h
0x18004eb9d  jmp     loc_18004E9B4
0x18004eba2  cmp     [rbp+0D0h+var_130], 4550h
0x18004eba9  jz      short loc_18004EC0A
0x18004ebab  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004ebb2  mov     ebx, 8007000Bh
0x18004ebb7  mov     [rsp+1D0h+var_178], ebx
0x18004ebbb  test    rcx, rcx
0x18004ebbe  jz      short loc_18004EC00
0x18004ebc0  lea     rax, [rsp+1D0h+var_180]
0x18004ebc5  lea     r9, aReadInvalidNtH; "Read invalid NT header from file: {}"
0x18004ebcc  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004ebd1  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18004ebd6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004ebdd  lea     rax, [rsp+1D0h+var_178]
0x18004ebe2  mov     qword ptr [rsp+1D0h+var_190], rax
0x18004ebe7  lea     r9, asc_1800AFAD8; ": {}"
0x18004ebee  lea     rax, [rsp+1D0h+var_190]
0x18004ebf3  mov     r8d, edi
0x18004ebf6  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rax
0x18004ebfb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18004ec00  mov     edx, 0CAh
0x18004ec05  jmp     loc_18004EA37
0x18004ec0a  movzx   ecx, [rbp+0D0h+var_D4]
0x18004ec0e  sub     ecx, 1
0x18004ec11  jz      short loc_18004EC8F
0x18004ec13  sub     ecx, 1
0x18004ec16  jz      short loc_18004EC8F
0x18004ec18  sub     ecx, 1
0x18004ec1b  jz      short loc_18004EC8F
0x18004ec1d  sub     ecx, 2
0x18004ec20  jz      short loc_18004EC27
0x18004ec22  cmp     ecx, 2
0x18004ec25  jnz     short loc_18004EC8F
0x18004ec27  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004ec2e  mov     ebx, 8007000Bh
0x18004ec33  mov     [rsp+1D0h+var_178], ebx
0x18004ec37  test    rcx, rcx
0x18004ec3a  jz      short loc_18004EC85
0x18004ec3c  lea     rax, [rsp+1D0h+var_180]
0x18004ec41  mov     qword ptr [rsp+1D0h+dwFlagsAndAttributes], rax
0x18004ec46  lea     r9, aUnexpectedSubs; "Unexpected subsystem: {} specified in N"...
  ... truncated ...
```
