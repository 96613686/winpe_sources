# PackageStoreMergePendingSessions(bool,wchar_t const *,CCbsInterfaceArray<CCbsSession *> const *)

- ea: `0x1800b21e4`
- end: `0x1800b2876`
- name: `?PackageStoreMergePendingSessions@@YAJ_NPEB_WPEBV?$CCbsInterfaceArray@PEAVCCbsSession@@@@@Z`
- size: `1682`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800b2990`

## callees

- `0x180010f54`
- `0x180011094`
- `0x180013250`
- `0x1800261e0`
- `0x180095924`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a02ec`
- `0x1800b21e4`
- `0x1800b287c`
- `0x1800b2fbc`
- `0x1800b980c`
- `0x1800c6f6c`
- `0x1800c731c`
- `0x1800eb500`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800ece48`
- `0x1800f68d8`
- `0x1800f8580`
- `0x18010c13c`
- `0x1801c1578`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800b256b`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800b256b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2699`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b25b7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b2685`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b25b7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b2685`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b2521`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b2521`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b243c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b243c`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800b2731`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800b2731`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800b24a4`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800b24a4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b246d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b246d`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x1800b2791`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x1800b2791`

## string_xrefs

- `0x1800b262e`: `Could not open file to read: {}`
- `0x1800b229e`: `Failed to get session store directory`
- `0x1800b25c7`: `Unable to write: {}`
- `0x1800b2531`: `Unable to read: {}`
- `0x1800b27af`: `Unable to copy {} to {}`
- `0x1800b22e1`: `%ws%ws.xml`
- `0x1800b23e8`: `%ws%ws.xml`
- `0x1800b231b`: `%ws%ws.back.xml`
- `0x1800b27d6`: `Unable to WOF compress {}`
- `0x1800b2802`: `Unable to WOF compress {}`

## pseudocode

```c
__int64 __fastcall PackageStoreMergePendingSessions(char a1, __int64 a2, __int64 a3)
{
  int SessionStoreDirectory; // eax
  unsigned int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  void **v10; // rax
  wchar_t *v11; // rsi
  wchar_t *v12; // rdi
  struct CCbsSession *v13; // rcx
  int v14; // eax
  int *v15; // rcx
  int *v16; // rax
  const WCHAR *v17; // rbx
  unsigned int v18; // r12d
  HANDLE FileW; // rax
  HANDLE v20; // r13
  DWORD FileSize; // eax
  char *v22; // rax
  char *v23; // r12
  const char *v24; // rdx
  const struct std::nothrow_t *v25; // rdx
  DWORD v26; // r13d
  char *v27; // rax
  int v28; // edx
  int v29; // r9d
  signed int LastError; // ebx
  unsigned int v31; // eax
  unsigned int v32; // eax
  wchar_t *v33; // rdx
  wchar_t *v34; // rcx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-79h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-79h]
  unsigned int v42[2]; // [rsp+48h] [rbp-51h] BYREF
  size_t Size; // [rsp+50h] [rbp-49h] BYREF
  DWORD *v44; // [rsp+58h] [rbp-41h] BYREF
  DWORD nNumberOfBytesToRead[2]; // [rsp+60h] [rbp-39h] BYREF
  HANDLE v46; // [rsp+68h] [rbp-31h] BYREF
  int *v47; // [rsp+70h] [rbp-29h] BYREF
  wchar_t *v48; // [rsp+78h] [rbp-21h] BYREF
  HANDLE hFile; // [rsp+80h] [rbp-19h] BYREF
  wchar_t *v50; // [rsp+88h] [rbp-11h] BYREF
  LPCWSTR lpFileName; // [rsp+90h] [rbp-9h] BYREF
  wchar_t *v52; // [rsp+98h] [rbp-1h] BYREF
  _BYTE v53[24]; // [rsp+A0h] [rbp+7h] BYREF
  int v54; // [rsp+B8h] [rbp+1Fh] BYREF
  DWORD NumberOfBytesRead; // [rsp+BCh] [rbp+23h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v52 = 0;
  lpFileName = 0;
  v46 = (HANDLE)-1LL;
  v48 = 0;
  v50 = 0;
  v54 = 0;
  NumberOfBytesRead = 0;
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v53,
    (struct AutoMonitoredCritSec *)&vPackageStoreLock,
    1);
  if ( !*(_QWORD *)(a3 + 24) )
    goto LABEL_58;
  SessionStoreDirectory = CCbsSession::GetSessionStoreDirectory(**(CCbsSession ***)(a3 + 40), &v48);
  v6 = SessionStoreDirectory;
  if ( SessionStoreDirectory < 0 )
  {
    v54 = SessionStoreDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get session store directory");
      v47 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v47);
    }
    v7 = v6;
    v8 = 7157;
    goto LABEL_9;
  }
  v9 = SczAllocFormatted(&v52, L"%ws%ws.xml", v48, a2);
  v6 = v9;
  if ( v9 >= 0 )
  {
    v9 = SczAllocFormatted(&v50, L"%ws%ws.back.xml", v48, a2);
    v6 = v9;
    if ( v9 < 0 )
    {
      v8 = 7159;
      goto LABEL_8;
    }
    v10 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v46);
    v11 = v50;
    v12 = v52;
    v14 = ValidateAndOpenSessionFileToWrite(v13, v52, v50, &v54, v10);
    v6 = v14;
    if ( v14 < 0 )
    {
      v54 = v14;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get session file");
        v47 = &v54;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v47);
      }
      v7 = v6;
      v8 = 7166;
      goto LABEL_9;
    }
    v15 = *(int **)(a3 + 40);
    v16 = &v15[2 * *(_QWORD *)(a3 + 24)];
    *(_QWORD *)v42 = v16;
    while ( 1 )
    {
      v47 = v15;
      if ( v15 == v16 )
      {
        if ( WriteFile(v46, "</Sessions>", 0xBu, &NumberOfBytesRead, 0) )
        {
          if ( a1 )
          {
            v32 = FlushFileBuffers(v46);
            LogAdapter::TraceAtLevelIfWin32BoolFalse<>(3, v32, "Failed to flush session file");
          }
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &v46,
            -1);
          if ( v54 )
          {
            *(_QWORD *)v42 = v12;
            v33 = v12;
            v44 = (DWORD *)v11;
            v34 = v11;
          }
          else
          {
            *(_QWORD *)v42 = v11;
            v33 = v11;
            v44 = (DWORD *)v12;
            v34 = v12;
          }
          v35 = PrivCopyFileExW(v34, v33, 0, 0);
          LogAdapter::TraceAtLevelIfWin32BoolFalse<wchar_t *,wchar_t *>(
            3,
            v35,
            (unsigned int)"Unable to copy {} to {}",
            (unsigned int)&v44,
            (__int64)v42);
          *(_QWORD *)v42 = v12;
          v36 = NativeCompressFile(v12, 0, 0);
          if ( v36 < 0 )
            LogAdapter::TraceAtLevelHr<long,wchar_t const *>(2, (unsigned int)v36, "Unable to WOF compress {}", v42);
          *(_QWORD *)v42 = v11;
          v37 = NativeCompressFile(v11, 0, 0);
          if ( v37 < 0 )
            LogAdapter::TraceAtLevelHr<long,wchar_t const *>(2, (unsigned int)v37, "Unable to WOF compress {}", v42);
        }
        else
        {
          LastError = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed on merging session files");
            if ( LastError > 0 )
              v31 = (unsigned __int16)LastError | 0x80070000;
            else
              v31 = LastError;
            v54 = v31;
            *(_QWORD *)v42 = &v54;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {0}",
              (__int64)v42);
          }
          if ( LastError )
          {
            v6 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x1C5A,
                   (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
                   (const char *)(unsigned int)LastError,
                   dwCreationDispositiona);
            goto LABEL_59;
          }
        }
LABEL_58:
        v6 = 0;
        goto LABEL_59;
      }
      v9 = SczAllocFormatted(&lpFileName, L"%ws%ws.xml", v48, *(_QWORD *)(*(_QWORD *)v15 + 640LL));
      v6 = v9;
      if ( v9 < 0 )
      {
        v8 = 7179;
        goto LABEL_8;
      }
      v17 = lpFileName;
      hFile = (HANDLE)-1LL;
      v18 = 0;
      while ( 1 )
      {
        FileW = CreateFileW(v17, 0x80000000, 0, 0, 3u, 0x80u, 0);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hFile,
          FileW);
        v20 = hFile;
        if ( hFile != (HANDLE)-1LL )
        {
          if ( hFile )
            break;
        }
        Sleep(0x3E8u);
        ++v18;
        if ( v20 != (HANDLE)-1LL )
        {
          if ( v20 )
            break;
        }
        if ( v18 >= 3 )
        {
          v44 = (DWORD *)v17;
          LogAdapter::TraceAtLevelLastError<wchar_t const *>(2, "Could not open file to read: {}", &v44);
          goto LABEL_39;
        }
      }
      FileSize = GetFileSize(v20, 0);
      nNumberOfBytesToRead[0] = FileSize;
      if ( FileSize == -1 )
      {
        *(_QWORD *)nNumberOfBytesToRead = v17;
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
          2,
          2147500037LL,
          "Unexpected file size: {}",
          nNumberOfBytesToRead);
        goto LABEL_39;
      }
      Size = FileSize + 2;
      v22 = (char *)operator new[]((unsigned int)Size, (const struct std::nothrow_t *)&std::nothrow);
      v23 = v22;
      if ( v22 )
        break;
      Size = (size_t)v17;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Out of memory: {}",
          (__int64)&Size);
        v44 = nNumberOfBytesToRead;
        nNumberOfBytesToRead[0] = 14;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>(
          (_DWORD)LogAdapter::g_Logger,
          v28,
          3,
          v29,
          (__int64)&v44);
      }
LABEL_39:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      v16 = *(int **)v42;
      v15 = v47 + 2;
    }
    memset_0(v22, 0, Size);
    if ( ReadFile(v20, v23, nNumberOfBytesToRead[0], &NumberOfBytesRead, 0) )
    {
      v26 = nNumberOfBytesToRead[0];
      v23[nNumberOfBytesToRead[0]] = 0;
      v27 = strstr(v23, "<Session");
      if ( !v27 )
      {
        Size = (size_t)v17;
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(2, 2147500037LL, "Invalid individual session file: {}", &Size);
        goto LABEL_32;
      }
      if ( WriteFile(v46, v27, v26 + (_DWORD)v23 - (_DWORD)v27, &NumberOfBytesRead, 0) )
        goto LABEL_32;
      v24 = "Unable to write: {}";
    }
    else
    {
      v24 = "Unable to read: {}";
    }
    Size = (size_t)v17;
    LogAdapter::TraceAtLevelLastError<wchar_t const *>(2, v24, &Size);
LABEL_32:
    operator delete(v23, v25);
    goto LABEL_39;
  }
  v8 = 7158;
LABEL_8:
  v7 = (unsigned int)v9;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\cbs\\core\\packagestore.cpp",
    (const char *)v7,
    dwCreationDisposition);
LABEL_59:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v53);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v46);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v50);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v48);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v52);
  return v6;
}

```

## disassembly

```asm
0x1800b21e4  mov     [rsp-8+arg_0], rbx
0x1800b21e9  mov     [rsp-8+arg_18], rsi
0x1800b21ee  push    rbp
0x1800b21ef  push    rdi
0x1800b21f0  push    r12
0x1800b21f2  push    r13
0x1800b21f4  push    r15
0x1800b21f6  lea     rbp, [rsp-37h]
0x1800b21fb  sub     rsp, 0D0h
0x1800b2202  mov     rax, cs:__security_cookie
0x1800b2209  xor     rax, rsp
0x1800b220c  mov     [rbp+57h+var_30], rax
0x1800b2210  mov     r15, r8
0x1800b2213  mov     [rbp+57h+var_B0], cl
0x1800b2216  mov     rdi, rdx
0x1800b2219  mov     [rbp+57h+var_58], 0
0x1800b2221  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800b2225  mov     [rbp+57h+lpFileName], 0
0x1800b222d  mov     r8b, 1; bool
0x1800b2230  mov     [rbp+57h+var_88], r12
0x1800b2234  lea     rdx, ?vPackageStoreLock@@3UMonitoredCritSec@@A; struct AutoMonitoredCritSec *
0x1800b223b  mov     [rbp+57h+var_78], 0
0x1800b2243  lea     rcx, [rbp+57h+var_50]; this
0x1800b2247  mov     [rbp+57h+var_68], 0
0x1800b224f  mov     [rbp+57h+var_38], 0
0x1800b2256  mov     [rbp+57h+NumberOfBytesRead], 0
0x1800b225d  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x1800b2262  mov     rax, [r15+18h]
0x1800b2266  test    rax, rax
0x1800b2269  jz      loc_1800B2813
0x1800b226f  mov     rcx, [r15+28h]
0x1800b2273  lea     rdx, [rbp+57h+var_78]; wchar_t **
0x1800b2277  mov     rcx, [rcx]; this
0x1800b227a  call    ?GetSessionStoreDirectory@CCbsSession@@QEAAJPEAPEA_W@Z; CCbsSession::GetSessionStoreDirectory(wchar_t * *)
0x1800b227f  mov     ebx, eax
0x1800b2281  test    eax, eax
0x1800b2283  jns     short loc_1800B22DD
0x1800b2285  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b228c  mov     [rbp+57h+var_38], eax
0x1800b228f  test    rcx, rcx
0x1800b2292  jz      short loc_1800B22D3
0x1800b2294  lea     r15d, [r12+4]
0x1800b2299  xor     edx, edx
0x1800b229b  mov     r8d, r15d
0x1800b229e  lea     r9, aFailedToGetSes_4; "Failed to get session store directory"
0x1800b22a5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b22aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b22b1  lea     rax, [rbp+57h+var_38]
0x1800b22b5  mov     [rbp+57h+var_80], rax
0x1800b22b9  lea     r9, asc_1802EE7AC; ": {}"
0x1800b22c0  lea     rax, [rbp+57h+var_80]
0x1800b22c4  mov     r8d, r15d
0x1800b22c7  mov     dl, 1
0x1800b22c9  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax
0x1800b22ce  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b22d3  mov     r9d, ebx
0x1800b22d6  mov     edx, 1BF5h
0x1800b22db  jmp     short loc_1800B2302
0x1800b22dd  mov     r8, [rbp+57h+var_78]
0x1800b22e1  lea     rdx, aWsWsXml; "%ws%ws.xml"
0x1800b22e8  mov     r9, rdi
0x1800b22eb  lea     rcx, [rbp+57h+var_58]
0x1800b22ef  call    SczAllocFormatted
0x1800b22f4  mov     ebx, eax
0x1800b22f6  test    eax, eax
0x1800b22f8  jns     short loc_1800B2317
0x1800b22fa  mov     edx, 1BF6h; void *
0x1800b22ff  mov     r9d, eax; char *
0x1800b2302  mov     rcx, [rbp+5Fh]; this
0x1800b2306  lea     r8, aOnecoreBaseCbs_18; "onecore\\base\\cbs\\core\\packagestore."...
0x1800b230d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2312  jmp     loc_1800B2815
0x1800b2317  mov     r8, [rbp+57h+var_78]
0x1800b231b  lea     rdx, aWsWsBackXml; "%ws%ws.back.xml"
0x1800b2322  mov     r9, rdi
0x1800b2325  lea     rcx, [rbp+57h+var_68]
0x1800b2329  call    SczAllocFormatted
0x1800b232e  mov     ebx, eax
0x1800b2330  test    eax, eax
0x1800b2332  jns     short loc_1800B233B
0x1800b2334  mov     edx, 1BF7h
0x1800b2339  jmp     short loc_1800B22FF
0x1800b233b  lea     rcx, [rbp+57h+var_88]
0x1800b233f  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1800b2344  mov     rsi, [rbp+57h+var_68]
0x1800b2348  lea     r9, [rbp+57h+var_38]; int *
0x1800b234c  mov     rdi, [rbp+57h+var_58]
0x1800b2350  mov     r8, rsi; wchar_t *
0x1800b2353  mov     rdx, rdi; wchar_t *
0x1800b2356  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax; void **
0x1800b235b  call    ?ValidateAndOpenSessionFileToWrite@@YAJPEAVCCbsSession@@PEB_W1PEAHPEAPEAX@Z; ValidateAndOpenSessionFileToWrite(CCbsSession *,wchar_t const *,wchar_t const *,int *,void * *)
0x1800b2360  mov     ebx, eax
0x1800b2362  test    eax, eax
0x1800b2364  jns     short loc_1800B23C2
0x1800b2366  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b236d  mov     [rbp+57h+var_38], eax
0x1800b2370  test    rcx, rcx
0x1800b2373  jz      short loc_1800B23B5
0x1800b2375  mov     r15d, 3
0x1800b237b  lea     r9, aFailedToGetSes_8; "Failed to get session file"
0x1800b2382  mov     r8d, r15d
0x1800b2385  xor     edx, edx
0x1800b2387  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b238c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b2393  lea     rax, [rbp+57h+var_38]
0x1800b2397  mov     [rbp+57h+var_80], rax
0x1800b239b  lea     r9, asc_1802EE7AC; ": {}"
0x1800b23a2  lea     rax, [rbp+57h+var_80]
0x1800b23a6  mov     r8d, r15d
0x1800b23a9  mov     dl, 1
0x1800b23ab  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax
0x1800b23b0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b23b5  mov     r9d, ebx
0x1800b23b8  mov     edx, 1BFEh
0x1800b23bd  jmp     loc_1800B2302
0x1800b23c2  mov     rcx, [r15+28h]
0x1800b23c6  mov     rax, [r15+18h]
0x1800b23ca  mov     r15d, 3
0x1800b23d0  lea     rax, [rcx+rax*8]
0x1800b23d4  mov     qword ptr [rbp+57h+var_A8], rax
0x1800b23d8  mov     [rbp+57h+var_80], rcx
0x1800b23dc  cmp     rcx, rax
0x1800b23df  jz      loc_1800B2667
0x1800b23e5  mov     r9, [rcx]
0x1800b23e8  lea     rdx, aWsWsXml; "%ws%ws.xml"
0x1800b23ef  mov     r8, [rbp+57h+var_78]
0x1800b23f3  lea     rcx, [rbp+57h+lpFileName]
0x1800b23f7  mov     r9, [r9+280h]
0x1800b23fe  call    SczAllocFormatted
0x1800b2403  mov     ebx, eax
0x1800b2405  test    eax, eax
0x1800b2407  js      loc_1800B265D
0x1800b240d  mov     rbx, [rbp+57h+lpFileName]
0x1800b2411  mov     [rbp+57h+hFile], r12
0x1800b2415  xor     r12d, r12d
0x1800b2418  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x1800b2421  xor     r9d, r9d; lpSecurityAttributes
0x1800b2424  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b242c  xor     r8d, r8d; dwShareMode
0x1800b242f  mov     edx, 80000000h; dwDesiredAccess
0x1800b2434  mov     [rsp+0F0h+dwCreationDisposition], r15d; dwCreationDisposition
0x1800b2439  mov     rcx, rbx; lpFileName
0x1800b243c  call    cs:__imp_CreateFileW
0x1800b2443  nop     dword ptr [rax+rax+00h]
0x1800b2448  mov     rdx, rax
0x1800b244b  lea     rcx, [rbp+57h+hFile]
0x1800b244f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b2454  mov     r13, [rbp+57h+hFile]
0x1800b2458  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800b245c  jz      short loc_1800B2468
0x1800b245e  test    r13, r13
0x1800b2461  jnz     short loc_1800B249F
0x1800b2463  cmp     r12d, r15d
0x1800b2466  jnb     short loc_1800B248C
0x1800b2468  mov     ecx, 3E8h; dwMilliseconds
0x1800b246d  call    cs:__imp_Sleep
0x1800b2474  nop     dword ptr [rax+rax+00h]
0x1800b2479  inc     r12d
0x1800b247c  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800b2480  jz      short loc_1800B2487
0x1800b2482  test    r13, r13
0x1800b2485  jnz     short loc_1800B249F
0x1800b2487  cmp     r12d, r15d
0x1800b248a  jb      short loc_1800B2418
0x1800b248c  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800b2490  jz      loc_1800B2626
0x1800b2496  test    r13, r13
0x1800b2499  jz      loc_1800B2626
0x1800b249f  xor     edx, edx; lpFileSizeHigh
0x1800b24a1  mov     rcx, r13; hFile
0x1800b24a4  call    cs:__imp_GetFileSize
0x1800b24ab  nop     dword ptr [rax+rax+00h]
0x1800b24b0  mov     [rbp+57h+nNumberOfBytesToRead], eax
0x1800b24b3  cmp     eax, 0FFFFFFFFh
0x1800b24b6  jnz     short loc_1800B24DB
0x1800b24b8  lea     r9, [rbp+57h+nNumberOfBytesToRead]
0x1800b24bc  mov     qword ptr [rbp+57h+nNumberOfBytesToRead], rbx
0x1800b24c0  lea     r8, aUnexpectedFile; "Unexpected file size: {}"
0x1800b24c7  mov     edx, 80004005h
0x1800b24cc  mov     ecx, 2
0x1800b24d1  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x1800b24d6  jmp     loc_1800B263F
0x1800b24db  add     eax, 2
0x1800b24de  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b24e5  mov     ecx, eax; unsigned __int64
0x1800b24e7  mov     [rbp+57h+Size], rax
0x1800b24eb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800b24f0  mov     r12, rax
0x1800b24f3  test    rax, rax
0x1800b24f6  jz      loc_1800B25D3
0x1800b24fc  mov     r8, [rbp+57h+Size]; Size
0x1800b2500  xor     edx, edx; Val
0x1800b2502  mov     rcx, rax; void *
0x1800b2505  call    memset_0
0x1800b250a  mov     r8d, [rbp+57h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x1800b250e  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800b2512  mov     rdx, r12; lpBuffer
0x1800b2515  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; lpOverlapped
0x1800b251e  mov     rcx, r13; hFile
0x1800b2521  call    cs:__imp_ReadFile
0x1800b2528  nop     dword ptr [rax+rax+00h]
0x1800b252d  test    eax, eax
0x1800b252f  jnz     short loc_1800B2557
0x1800b2531  lea     rdx, aUnableToRead; "Unable to read: {}"
0x1800b2538  lea     r8, [rbp+57h+Size]
0x1800b253c  mov     [rbp+57h+Size], rbx
0x1800b2540  mov     ecx, 2
0x1800b2545  call    ??$TraceAtLevelLastError@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelLastError<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b254a  mov     rcx, r12; void *
0x1800b254d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b2552  jmp     loc_1800B263F
0x1800b2557  mov     r13d, [rbp+57h+nNumberOfBytesToRead]
0x1800b255b  lea     rdx, SubStr; "<Session"
0x1800b2562  mov     rcx, r12; Str
0x1800b2565  mov     byte ptr [r13+r12+0], 0
0x1800b256b  call    cs:__imp_strstr
0x1800b2572  nop     dword ptr [rax+rax+00h]
0x1800b2577  test    rax, rax
0x1800b257a  jnz     short loc_1800B259A
0x1800b257c  lea     r9, [rbp+57h+Size]
0x1800b2580  mov     [rbp+57h+Size], rbx
0x1800b2584  lea     r8, aInvalidIndivid; "Invalid individual session file: {}"
0x1800b258b  mov     edx, 80004005h
0x1800b2590  lea     ecx, [rax+2]
0x1800b2593  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x1800b2598  jmp     short loc_1800B254A
0x1800b259a  mov     rcx, [rbp+57h+var_88]; hFile
0x1800b259e  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x1800b25a2  mov     r8d, r12d
0x1800b25a5  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; lpOverlapped
0x1800b25ae  sub     r8d, eax
0x1800b25b1  mov     rdx, rax; lpBuffer
0x1800b25b4  add     r8d, r13d; nNumberOfBytesToWrite
0x1800b25b7  call    cs:__imp_WriteFile
0x1800b25be  nop     dword ptr [rax+rax+00h]
0x1800b25c3  test    eax, eax
0x1800b25c5  jnz     short loc_1800B254A
0x1800b25c7  lea     rdx, aUnableToWrite; "Unable to write: {}"
0x1800b25ce  jmp     loc_1800B2538
0x1800b25d3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b25da  mov     [rbp+57h+Size], rbx
0x1800b25de  test    rcx, rcx
0x1800b25e1  jz      short loc_1800B263F
0x1800b25e3  lea     rax, [rbp+57h+Size]
0x1800b25e7  mov     r8d, r15d
0x1800b25ea  lea     r9, aOutOfMemory_0; "Out of memory: {}"
0x1800b25f1  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax
0x1800b25f6  xor     edx, edx
0x1800b25f8  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b25fd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b2604  lea     rax, [rbp+57h+nNumberOfBytesToRead]
0x1800b2608  mov     [rbp+57h+var_98], rax
0x1800b260c  mov     r8d, r15d
0x1800b260f  lea     rax, [rbp+57h+var_98]
0x1800b2613  mov     [rbp+57h+nNumberOfBytesToRead], 0Eh
0x1800b261a  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax
0x1800b261f  call    ??$LogNumObjects@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)
0x1800b2624  jmp     short loc_1800B263F
0x1800b2626  lea     r8, [rbp+57h+var_98]
0x1800b262a  mov     [rbp+57h+var_98], rbx
0x1800b262e  lea     rdx, aCouldNotOpenFi_0; "Could not open file to read: {}"
0x1800b2635  mov     ecx, 2
0x1800b263a  call    ??$TraceAtLevelLastError@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelLastError<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b263f  lea     rcx, [rbp+57h+hFile]
0x1800b2643  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b2648  mov     rcx, [rbp+57h+var_80]
0x1800b264c  mov     rax, qword ptr [rbp+57h+var_A8]
0x1800b2650  add     rcx, 8
0x1800b2654  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800b2658  jmp     loc_1800B23D8
0x1800b265d  mov     edx, 1C0Bh
0x1800b2662  jmp     loc_1800B22FF
0x1800b2667  mov     rcx, [rbp+57h+var_88]; hFile
0x1800b266b  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x1800b266f  mov     r8d, 0Bh; nNumberOfBytesToWrite
0x1800b2675  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; lpOverlapped
0x1800b267e  lea     rdx, aSessions_2; "</Sessions>"
0x1800b2685  call    cs:__imp_WriteFile
0x1800b268c  nop     dword ptr [rax+rax+00h]
0x1800b2691  test    eax, eax
0x1800b2693  jnz     loc_1800B2727
0x1800b2699  call    cs:__imp_GetLastError
0x1800b26a0  nop     dword ptr [rax+rax+00h]
0x1800b26a5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b26ac  mov     ebx, eax
0x1800b26ae  test    rcx, rcx
0x1800b26b1  jz      short loc_1800B2700
0x1800b26b3  lea     r9, aFailedOnMergin; "Failed on merging session files"
0x1800b26ba  mov     r8d, r15d
0x1800b26bd  xor     edx, edx
0x1800b26bf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b26c4  test    ebx, ebx
0x1800b26c6  jg      short loc_1800B26CC
0x1800b26c8  mov     eax, ebx
0x1800b26ca  jmp     short loc_1800B26D4
0x1800b26cc  movzx   eax, bx
0x1800b26cf  or      eax, 80070000h
0x1800b26d4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b26db  lea     r9, a0; ": {0}"
0x1800b26e2  mov     [rbp+57h+var_38], eax
  ... truncated ...
```
