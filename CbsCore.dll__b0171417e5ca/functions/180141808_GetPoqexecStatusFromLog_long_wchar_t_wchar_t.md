# GetPoqexecStatusFromLog(long *,wchar_t * *,wchar_t * *)

- ea: `0x180141808`
- end: `0x1801421af`
- name: `?GetPoqexecStatusFromLog@@YAJPEAJPEAPEA_W1@Z`
- size: `2471`
- prototype: `__int64 __fastcall(int *, wchar_t **, wchar_t **)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801424e4`

## callees

- `0x180013250`
- `0x180015420`
- `0x18001a160`
- `0x1800261e0`
- `0x180033d50`
- `0x180058e08`
- `0x180059a00`
- `0x18005aa38`
- `0x180095924`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a02ec`
- `0x1800ad504`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800f19ec`
- `0x1800fe364`
- `0x180108ad4`
- `0x180141808`
- `0x180142e00`
- `0x1801f0840`
- `0x1802cf7c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141f5f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141f7d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141f9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141fb9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141fd3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141fed`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180142007`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180142021`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141f5f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141f7d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141f9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141fb9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141fd3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180141fed`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180142007`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180142021`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18014204f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18014204f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180142072`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180142072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180141a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180141bb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180141c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180141a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180141bb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180141c44`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1801419ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1801419ed`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180141c34`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180141c34`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180141b8a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180141b8a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180141b41`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180141b41`

## string_xrefs

- `0x180141cd4`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing`
- `0x180141dd2`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing`
- `0x180141a23`: `Failed to get Windows directory.`
- `0x180141c5e`: `Failed to get last write time of poqexec.log.`
- `0x180141bcc`: `Failed to open poqexec.log for reading.`
- `0x180141ac0`: `Windows directory path is {} in length and cannot be used`
- `0x180141f91`: `DeleteFile`
- `0x180141f73`: `MoveFile`
- `0x180141f55`: `CopyFile`
- `0x180141dfa`: `Failed to set last poqexec.log time in the registry.`
- `0x180141d75`: `Failed to get last poqexec.log time from the registry.`
- `0x180142017`: `SetFileInformation`
- `0x180141ffd`: `WriteFile`
- `0x180141fe3`: `CreateDirectory`
- `0x180141fc9`: `CreateFile`
- `0x180141faf`: `HardLinkFile`

## pseudocode

```c
__int64 __fastcall GetPoqexecStatusFromLog(int *a1, wchar_t **a2, wchar_t **a3)
{
  wchar_t *v5; // r14
  wchar_t *v6; // r15
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  WCHAR *v11; // rcx
  UINT SystemWindowsDirectoryW; // eax
  signed int LastError; // ebx
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  HANDLE FileW; // rax
  unsigned int v18; // eax
  unsigned int v19; // r8d
  unsigned int v20; // eax
  int QWORDValue; // eax
  int v22; // eax
  const struct _LUNICODE_STRING *v23; // rcx
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // edx
  int v27; // esi
  int v28; // eax
  __int64 v29; // rdx
  unsigned __int64 v30; // r9
  __int64 v31; // rbx
  wchar_t *v32; // rbx
  wchar_t *v33; // rax
  wchar_t *v34; // rax
  wchar_t *v35; // rax
  int v36; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-99h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-99h]
  int *Buf2; // [rsp+40h] [rbp-79h] BYREF
  LPWSTR lpBuffer; // [rsp+48h] [rbp-71h] BYREF
  wchar_t *Str; // [rsp+50h] [rbp-69h] BYREF
  wchar_t *v43; // [rsp+58h] [rbp-61h] BYREF
  wchar_t *v44; // [rsp+60h] [rbp-59h] BYREF
  __int64 v45; // [rsp+68h] [rbp-51h] BYREF
  HANDLE hFile; // [rsp+70h] [rbp-49h] BYREF
  int *v47; // [rsp+78h] [rbp-41h]
  __int128 v48; // [rsp+80h] [rbp-39h] BYREF
  __int64 v49; // [rsp+90h] [rbp-29h]
  __int128 v50; // [rsp+98h] [rbp-21h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-11h]
  int v52; // [rsp+B0h] [rbp-9h] BYREF
  UINT v53; // [rsp+B4h] [rbp-5h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+B8h] [rbp-1h] BYREF
  int v55[4]; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v56; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v47 = a1;
  lpBuffer = 0;
  v53 = 0;
  hFile = (HANDLE)-1LL;
  LastWriteTime = 0;
  Buf2 = 0;
  v52 = 0;
  v51 = 0;
  v5 = 0;
  v49 = 0;
  v6 = 0;
  v56 = 0;
  v45 = 0;
  Str = 0;
  v44 = 0;
  v43 = 0;
  v50 = 0;
  v48 = 0;
  *(_OWORD *)v55 = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      v7 = -2147467261;
      v52 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No failed file name result specified");
        Buf2 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&Buf2);
      }
      v8 = 639;
      goto LABEL_13;
    }
    if ( !a3 )
    {
      v7 = -2147467261;
      v52 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No interfering process name result specified");
        Buf2 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&Buf2);
      }
      v8 = 640;
      goto LABEL_13;
    }
    v10 = SczAlloc(&lpBuffer, 260);
    v7 = v10;
    if ( v10 < 0 )
    {
      v8 = 646;
LABEL_16:
      v9 = (unsigned int)v10;
      goto LABEL_17;
    }
    v11 = lpBuffer;
    *lpBuffer = 0;
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(v11, 0x104u);
    v53 = SystemWindowsDirectoryW;
    if ( !SystemWindowsDirectoryW )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get Windows directory.");
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        else
          v14 = LastError;
        v52 = v14;
        Buf2 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&Buf2);
      }
      if ( LastError )
      {
        v15 = 651;
LABEL_26:
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v15,
                (unsigned int)"onecore\\base\\cbs\\core\\poqexechelper.cpp",
                (const char *)(unsigned int)LastError,
                dwCreationDisposition);
LABEL_27:
        v7 = v16;
        goto LABEL_103;
      }
      goto LABEL_102;
    }
    if ( SystemWindowsDirectoryW >= 0x104 )
    {
      v7 = -2147024774;
      v52 = -2147024774;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<unsigned long>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Windows directory path is {} in length and cannot be used",
          (__int64)&v53);
        Buf2 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&Buf2);
      }
      v9 = 2147942522LL;
      v8 = 653;
      goto LABEL_17;
    }
    v10 = SczEnsureBackslashTerminated(&lpBuffer);
    v7 = v10;
    if ( v10 < 0 )
    {
      v8 = 655;
      goto LABEL_16;
    }
    v10 = SczAllocConcatSz(&lpBuffer, L"WinSxS\\poqexec.log");
    v7 = v10;
    if ( v10 < 0 )
    {
      v8 = 657;
      goto LABEL_16;
    }
    if ( GetFileAttributesW(lpBuffer) == -1 )
    {
      LogAdapter::TraceAtLevel<>(1, "Poqexec.log doesn't exist; nothing to parse.");
      goto LABEL_102;
    }
    FileW = CreateFileW(lpBuffer, 0x80000000, 1u, 0, 3u, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
    if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open poqexec.log for reading.");
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
        else
          v18 = LastError;
        v52 = v18;
        Buf2 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&Buf2);
      }
      if ( LastError )
      {
        v15 = 666;
        goto LABEL_26;
      }
LABEL_102:
      v7 = 0;
      goto LABEL_103;
    }
    if ( !GetFileTime(hFile, 0, 0, &LastWriteTime) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get last write time of poqexec.log.");
        if ( LastError > 0 )
          v20 = (unsigned __int16)LastError | 0x80070000;
        else
          v20 = LastError;
        v52 = v20;
        Buf2 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&Buf2);
      }
      if ( LastError )
      {
        v15 = 669;
        goto LABEL_26;
      }
      goto LABEL_102;
    }
    QWORDValue = CbsRegQueryQWORDValue(
                   HKEY_LOCAL_MACHINE,
                   L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing",
                   v19,
                   L"LastPoqexecLogTime",
                   (unsigned __int64 *)&Buf2);
    v7 = QWORDValue;
    if ( QWORDValue < 0 )
    {
      if ( (unsigned int)(QWORDValue + 2147024894) > 1 )
      {
        v52 = QWORDValue;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get last poqexec.log time from the registry.");
          Buf2 = &v52;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&Buf2);
        }
        v9 = v7;
        v8 = 686;
        goto LABEL_17;
      }
    }
    else if ( !memcmp_0(&LastWriteTime, &Buf2, 8u) )
    {
      v7 = -2147467260;
      v52 = -2147467260;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Poqexec.log time same as last time reported; not reporting again.");
        Buf2 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&Buf2);
      }
      v9 = 2147500036LL;
      v8 = 681;
      goto LABEL_17;
    }
    v22 = CbsRegSetQWORDValue(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing",
            2u,
            L"LastPoqexecLogTime",
            (const unsigned __int64 *const)&LastWriteTime);
    v7 = v22;
    if ( v22 < 0 )
    {
      v52 = v22;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set last poqexec.log time in the registry.");
        Buf2 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&Buf2);
      }
      v9 = v7;
      v8 = 696;
      goto LABEL_17;
    }
    v24 = PoqParsePoqexecLog(
            v23,
            &v52,
            (struct _LUNICODE_STRING *)&v50,
            (struct _LUNICODE_STRING *)&v48,
            (struct _LUNICODE_STRING *)v55);
    v25 = v24;
    if ( v24 < 0 )
    {
      v52 = v24;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to parse poqexec.log.");
        Buf2 = &v52;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v26,
          3,
          (unsigned int)": {}",
          (__int64)&Buf2);
      }
      v16 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x2C0,
              (unsigned int)"onecore\\base\\cbs\\core\\poqexechelper.cpp",
              (const char *)v25,
              dwCreationDispositiona);
      goto LABEL_27;
    }
    v27 = v52;
    if ( v52 >= 0 )
      goto LABEL_101;
    v28 = SczAllocFormatted(&v45, L"%.*ls", (unsigned __int64)v50 >> 1, v51);
    v7 = v28;
    if ( v28 < 0 )
    {
      v29 = 717;
LABEL_74:
      v30 = (unsigned int)v28;
LABEL_75:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\base\\cbs\\core\\poqexechelper.cpp",
        (const char *)v30,
        dwCreationDispositiona);
      RtlFreeLBlob(&v48);
      RtlFreeLBlob(&v50);
      RtlFreeLBlob(v55);
      goto LABEL_103;
    }
    v28 = SczAllocFormatted(&Str, L"%.*ls", (unsigned __int64)v48 >> 1, v49);
    v7 = v28;
    if ( v28 < 0 )
    {
      v29 = 724;
      goto LABEL_74;
    }
    v31 = v45;
    if ( (unsigned int)_o__wcsicmp(v45, L"CopyFile")
      && (unsigned int)_o__wcsicmp(v31, L"MoveFile")
      && (unsigned int)_o__wcsicmp(v31, L"DeleteFile")
      && (unsigned int)_o__wcsicmp(v31, L"HardLinkFile")
      && (unsigned int)_o__wcsicmp(v31, L"CreateFile")
      && (unsigned int)_o__wcsicmp(v31, L"CreateDirectory") )
    {
      if ( !(unsigned int)_o__wcsicmp(v31, L"WriteFile") || !(unsigned int)_o__wcsicmp(v31, L"SetFileInformation") )
      {
        v32 = Str;
        v35 = wcschr(Str, 0x2Cu);
        if ( v35 )
          *v35 = 0;
LABEL_88:
        if ( v32 )
        {
          v33 = wcsrchr(v32, 0x5Cu);
          if ( v33 )
            v34 = v33 + 1;
          else
            v34 = v32;
          v28 = SczAllocFromSz(&v44, v34);
          v7 = v28;
          if ( v28 < 0 )
          {
            v29 = 766;
            goto LABEL_74;
          }
          v36 = TransformInterferingProcessesString(v55, &v43);
          v7 = v36;
          if ( v36 < 0 )
          {
            v52 = v36;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to transform string of interfering processes.");
              Buf2 = &v52;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&Buf2);
            }
            v30 = v7;
            v29 = 769;
            goto LABEL_75;
          }
          v5 = v44;
          v6 = v43;
        }
LABEL_101:
        *v47 = v27;
        *a2 = v5;
        v44 = 0;
        v43 = 0;
        *a3 = v6;
        RtlFreeLBlob(&v48);
        RtlFreeLBlob(&v50);
        RtlFreeLBlob(v55);
        goto LABEL_102;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
    }
    v32 = Str;
    goto LABEL_88;
  }
  v7 = -2147467261;
  v52 = -2147467261;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No status result specified");
    Buf2 = &v52;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)&Buf2);
  }
  v8 = 638;
LABEL_13:
  v9 = 2147500035LL;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\cbs\\core\\poqexechelper.cpp",
    (const char *)v9,
    dwCreationDisposition);
LABEL_103:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v43);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v44);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v45);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  return v7;
}

```

## disassembly

```asm
0x180141808  mov     [rsp-8+arg_18], rbx
0x18014180d  push    rbp
0x18014180e  push    rsi
0x18014180f  push    rdi
0x180141810  push    r12
0x180141812  push    r13
0x180141814  push    r14
0x180141816  push    r15
0x180141818  lea     rbp, [rsp-27h]
0x18014181d  sub     rsp, 0E0h
0x180141824  mov     rax, cs:__security_cookie
0x18014182b  xor     rax, rsp
0x18014182e  mov     [rbp+57h+var_38], rax
0x180141832  xor     esi, esi
0x180141834  mov     [rbp+57h+var_98], rcx
0x180141838  mov     rax, rcx
0x18014183b  mov     [rbp+57h+lpBuffer], rsi
0x18014183f  xor     ecx, ecx
0x180141841  mov     [rbp+57h+var_5C], esi
0x180141844  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x18014184c  xorps   xmm0, xmm0
0x18014184f  mov     qword ptr [rbp+57h+LastWriteTime.dwLowDateTime], rsi
0x180141853  xorps   xmm1, xmm1
0x180141856  mov     [rbp+57h+Buf2], rsi
0x18014185a  mov     r13, r8
0x18014185d  mov     [rbp+57h+var_60], esi
0x180141860  mov     r12, rdx
0x180141863  mov     [rbp+57h+var_68], rcx
0x180141867  mov     r14d, esi
0x18014186a  mov     [rbp+57h+var_80], rcx
0x18014186e  mov     r15d, esi
0x180141871  mov     [rbp+57h+var_40], rcx
0x180141875  mov     [rbp+57h+var_A8], rsi
0x180141879  mov     [rbp+57h+Str], rsi
0x18014187d  mov     [rbp+57h+var_B0], rsi
0x180141881  mov     [rbp+57h+var_B8], rsi
0x180141885  movups  [rbp+57h+var_78], xmm0
0x180141889  movups  [rbp+57h+var_90], xmm1
0x18014188d  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180141891  test    rax, rax
0x180141894  jnz     short loc_1801418F1
0x180141896  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18014189d  mov     ebx, 80004003h
0x1801418a2  mov     [rbp+57h+var_60], ebx
0x1801418a5  test    rcx, rcx
0x1801418a8  jz      short loc_1801418E7
0x1801418aa  lea     edi, [rax+3]
0x1801418ad  xor     edx, edx
0x1801418af  mov     r8d, edi
0x1801418b2  lea     r9, aNoStatusResult; "No status result specified"
0x1801418b9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801418be  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801418c5  lea     rax, [rbp+57h+var_60]
0x1801418c9  mov     [rbp+57h+Buf2], rax
0x1801418cd  lea     r9, asc_1802EE7AC; ": {}"
0x1801418d4  lea     rax, [rbp+57h+Buf2]
0x1801418d8  mov     r8d, edi
0x1801418db  mov     dl, 1
0x1801418dd  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1801418e2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801418e7  mov     edx, 27Eh
0x1801418ec  jmp     loc_1801419AC
0x1801418f1  test    r12, r12
0x1801418f4  jnz     short loc_180141950
0x1801418f6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801418fd  mov     ebx, 80004003h
0x180141902  mov     [rbp+57h+var_60], ebx
0x180141905  test    rcx, rcx
0x180141908  jz      short loc_180141949
0x18014190a  lea     edi, [r12+3]
0x18014190f  xor     edx, edx
0x180141911  mov     r8d, edi
0x180141914  lea     r9, aNoFailedFileNa; "No failed file name result specified"
0x18014191b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180141920  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180141927  lea     rax, [rbp+57h+var_60]
0x18014192b  mov     [rbp+57h+Buf2], rax
0x18014192f  lea     r9, asc_1802EE7AC; ": {}"
0x180141936  lea     rax, [rbp+57h+Buf2]
0x18014193a  mov     r8d, edi
0x18014193d  mov     dl, 1
0x18014193f  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180141944  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180141949  mov     edx, 27Fh
0x18014194e  jmp     short loc_1801419AC
0x180141950  test    r13, r13
0x180141953  jnz     short loc_1801419B1
0x180141955  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18014195c  mov     ebx, 80004003h
0x180141961  mov     [rbp+57h+var_60], ebx
0x180141964  test    rcx, rcx
0x180141967  jz      short loc_1801419A7
0x180141969  lea     edi, [r13+3]
0x18014196d  xor     edx, edx
0x18014196f  mov     r8d, edi
0x180141972  lea     r9, aNoInterferingP; "No interfering process name result spec"...
0x180141979  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18014197e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180141985  lea     rax, [rbp+57h+var_60]
0x180141989  mov     [rbp+57h+Buf2], rax
0x18014198d  lea     r9, asc_1802EE7AC; ": {}"
0x180141994  lea     rax, [rbp+57h+Buf2]
0x180141998  mov     r8d, edi
0x18014199b  mov     dl, 1
0x18014199d  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1801419a2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801419a7  mov     edx, 280h
0x1801419ac  mov     r9d, ebx
0x1801419af  jmp     short loc_1801419CF
0x1801419b1  mov     edi, 104h
0x1801419b6  lea     rcx, [rbp+57h+lpBuffer]
0x1801419ba  mov     edx, edi
0x1801419bc  call    SczAlloc
0x1801419c1  mov     ebx, eax
0x1801419c3  test    eax, eax
0x1801419c5  jns     short loc_1801419E4
0x1801419c7  mov     edx, 286h; void *
0x1801419cc  mov     r9d, eax; char *
0x1801419cf  mov     rcx, [rbp+5Fh]; this
0x1801419d3  lea     r8, aOnecoreBaseCbs_100; "onecore\\base\\cbs\\core\\poqexechelper"...
0x1801419da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801419df  jmp     loc_18014214F
0x1801419e4  mov     rcx, [rbp+57h+lpBuffer]; lpBuffer
0x1801419e8  mov     edx, edi; uSize
0x1801419ea  mov     [rcx], si
0x1801419ed  call    cs:__imp_GetSystemWindowsDirectoryW
0x1801419f4  nop     dword ptr [rax+rax+00h]
0x1801419f9  mov     [rbp+57h+var_5C], eax
0x1801419fc  test    eax, eax
0x1801419fe  jnz     loc_180141A97
0x180141a04  call    cs:__imp_GetLastError
0x180141a0b  nop     dword ptr [rax+rax+00h]
0x180141a10  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180141a17  mov     ebx, eax
0x180141a19  test    rcx, rcx
0x180141a1c  jz      short loc_180141A70
0x180141a1e  mov     edi, 3
0x180141a23  lea     r9, aFailedToGetWin; "Failed to get Windows directory."
0x180141a2a  mov     r8d, edi
0x180141a2d  xor     edx, edx
0x180141a2f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180141a34  test    ebx, ebx
0x180141a36  jg      short loc_180141A3C
0x180141a38  mov     eax, ebx
0x180141a3a  jmp     short loc_180141A44
0x180141a3c  movzx   eax, bx
0x180141a3f  or      eax, 80070000h
0x180141a44  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180141a4b  lea     r9, a0; ": {0}"
0x180141a52  mov     [rbp+57h+var_60], eax
0x180141a55  mov     r8d, edi
0x180141a58  lea     rax, [rbp+57h+var_60]
0x180141a5c  mov     dl, 1
0x180141a5e  mov     [rbp+57h+Buf2], rax
0x180141a62  lea     rax, [rbp+57h+Buf2]
0x180141a66  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; unsigned int
0x180141a6b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180141a70  test    ebx, ebx
0x180141a72  jz      loc_18014214D
0x180141a78  mov     edx, 28Bh; void *
0x180141a7d  mov     rcx, [rbp+5Fh]; this
0x180141a81  lea     r8, aOnecoreBaseCbs_100; "onecore\\base\\cbs\\core\\poqexechelper"...
0x180141a88  mov     r9d, ebx; char *
0x180141a8b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180141a90  mov     ebx, eax
0x180141a92  jmp     loc_18014214F
0x180141a97  cmp     eax, edi
0x180141a99  jb      short loc_180141B04
0x180141a9b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180141aa2  mov     ebx, 8007007Ah
0x180141aa7  mov     [rbp+57h+var_60], ebx
0x180141aaa  test    rcx, rcx
0x180141aad  jz      short loc_180141AF7
0x180141aaf  lea     rax, [rbp+57h+var_5C]
0x180141ab3  mov     edi, 3
0x180141ab8  mov     r8d, edi
0x180141abb  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180141ac0  lea     r9, aWindowsDirecto; "Windows directory path is {} in length "...
0x180141ac7  xor     edx, edx
0x180141ac9  call    ??$LogNumObjects@K@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBK@Z; LogAdapter::Logger::LogNumObjects<ulong>(bool,LogAdapter::LogLevel,char const * const,ulong const &)
0x180141ace  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180141ad5  lea     rax, [rbp+57h+var_60]
0x180141ad9  mov     [rbp+57h+Buf2], rax
0x180141add  lea     r9, asc_1802EE7AC; ": {}"
0x180141ae4  lea     rax, [rbp+57h+Buf2]
0x180141ae8  mov     r8d, edi
0x180141aeb  mov     dl, 1
0x180141aed  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180141af2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180141af7  mov     r9d, ebx
0x180141afa  mov     edx, 28Dh
0x180141aff  jmp     loc_1801419CF
0x180141b04  lea     rcx, [rbp+57h+lpBuffer]
0x180141b08  call    SczEnsureBackslashTerminated
0x180141b0d  mov     ebx, eax
0x180141b0f  test    eax, eax
0x180141b11  jns     short loc_180141B1D
0x180141b13  mov     edx, 28Fh
0x180141b18  jmp     loc_1801419CC
0x180141b1d  lea     rdx, aWinsxsPoqexecL; "WinSxS\\poqexec.log"
0x180141b24  lea     rcx, [rbp+57h+lpBuffer]
0x180141b28  call    SczAllocConcatSz
0x180141b2d  mov     ebx, eax
0x180141b2f  test    eax, eax
0x180141b31  jns     short loc_180141B3D
0x180141b33  mov     edx, 291h
0x180141b38  jmp     loc_1801419CC
0x180141b3d  mov     rcx, [rbp+57h+lpBuffer]; lpFileName
0x180141b41  call    cs:__imp_GetFileAttributesW
0x180141b48  nop     dword ptr [rax+rax+00h]
0x180141b4d  cmp     eax, 0FFFFFFFFh
0x180141b50  jnz     short loc_180141B68
0x180141b52  lea     rdx, aPoqexecLogDoes; "Poqexec.log doesn't exist; nothing to p"...
0x180141b59  mov     ecx, 1
0x180141b5e  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180141b63  jmp     loc_18014214D
0x180141b68  mov     rcx, [rbp+57h+lpBuffer]; lpFileName
0x180141b6c  mov     edi, 3
0x180141b71  mov     [rsp+110h+hTemplateFile], rsi; hTemplateFile
0x180141b76  xor     r9d, r9d; lpSecurityAttributes
0x180141b79  mov     [rsp+110h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180141b7d  mov     edx, 80000000h; dwDesiredAccess
0x180141b82  mov     [rsp+110h+dwCreationDisposition], edi; dwCreationDisposition
0x180141b86  lea     r8d, [rdi-2]; dwShareMode
0x180141b8a  call    cs:__imp_CreateFileW
0x180141b91  nop     dword ptr [rax+rax+00h]
0x180141b96  mov     rdx, rax
0x180141b99  lea     rcx, [rbp+57h+hFile]
0x180141b9d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180141ba2  mov     rcx, [rbp+57h+hFile]; hFile
0x180141ba6  lea     rax, [rcx+1]
0x180141baa  test    rax, 0FFFFFFFFFFFFFFFEh
0x180141bb0  jnz     short loc_180141C2B
0x180141bb2  call    cs:__imp_GetLastError
0x180141bb9  nop     dword ptr [rax+rax+00h]
0x180141bbe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180141bc5  mov     ebx, eax
0x180141bc7  test    rcx, rcx
0x180141bca  jz      short loc_180141C19
0x180141bcc  lea     r9, aFailedToOpenPo; "Failed to open poqexec.log for reading."
0x180141bd3  mov     r8d, edi
0x180141bd6  xor     edx, edx
0x180141bd8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180141bdd  test    ebx, ebx
0x180141bdf  jg      short loc_180141BE5
0x180141be1  mov     eax, ebx
0x180141be3  jmp     short loc_180141BED
0x180141be5  movzx   eax, bx
0x180141be8  or      eax, 80070000h
0x180141bed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180141bf4  lea     r9, a0; ": {0}"
0x180141bfb  mov     [rbp+57h+var_60], eax
0x180141bfe  mov     r8d, edi
0x180141c01  lea     rax, [rbp+57h+var_60]
0x180141c05  mov     dl, 1
0x180141c07  mov     [rbp+57h+Buf2], rax
0x180141c0b  lea     rax, [rbp+57h+Buf2]
0x180141c0f  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180141c14  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180141c19  test    ebx, ebx
0x180141c1b  jz      loc_18014214D
0x180141c21  mov     edx, 29Ah
0x180141c26  jmp     loc_180141A7D
0x180141c2b  lea     r9, [rbp+57h+LastWriteTime]; lpLastWriteTime
0x180141c2f  xor     r8d, r8d; lpLastAccessTime
0x180141c32  xor     edx, edx; lpCreationTime
0x180141c34  call    cs:__imp_GetFileTime
0x180141c3b  nop     dword ptr [rax+rax+00h]
0x180141c40  test    eax, eax
0x180141c42  jnz     short loc_180141CBD
0x180141c44  call    cs:__imp_GetLastError
0x180141c4b  nop     dword ptr [rax+rax+00h]
0x180141c50  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180141c57  mov     ebx, eax
0x180141c59  test    rcx, rcx
0x180141c5c  jz      short loc_180141CAB
0x180141c5e  lea     r9, aFailedToGetLas; "Failed to get last write time of poqexe"...
0x180141c65  mov     r8d, edi
0x180141c68  xor     edx, edx
0x180141c6a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180141c6f  test    ebx, ebx
0x180141c71  jg      short loc_180141C77
0x180141c73  mov     eax, ebx
0x180141c75  jmp     short loc_180141C7F
0x180141c77  movzx   eax, bx
0x180141c7a  or      eax, 80070000h
0x180141c7f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180141c86  lea     r9, a0; ": {0}"
0x180141c8d  mov     [rbp+57h+var_60], eax
0x180141c90  mov     r8d, edi
0x180141c93  lea     rax, [rbp+57h+var_60]
0x180141c97  mov     dl, 1
0x180141c99  mov     [rbp+57h+Buf2], rax
0x180141c9d  lea     rax, [rbp+57h+Buf2]
0x180141ca1  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180141ca6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180141cab  test    ebx, ebx
0x180141cad  jz      loc_18014214D
0x180141cb3  mov     edx, 29Dh
0x180141cb8  jmp     loc_180141A7D
  ... truncated ...
```
