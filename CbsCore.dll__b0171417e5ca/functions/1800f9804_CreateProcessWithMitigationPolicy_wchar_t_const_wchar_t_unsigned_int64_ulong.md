# CreateProcessWithMitigationPolicy(wchar_t const *,wchar_t *,unsigned __int64,ulong)

- ea: `0x1800f9804`
- end: `0x1800f9e7f`
- name: `?CreateProcessWithMitigationPolicy@@YAJPEB_WPEA_W_KK@Z`
- size: `1659`
- prototype: `int(const wchar_t *, wchar_t *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f8cd0`

## callees

- `0x1800150c0`
- `0x18004a680`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb500`
- `0x1800eb50c`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800f9804`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f9bf0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f9bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f989f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f99b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9b4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f989f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f99b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9b4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f9c9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800f9af0`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800f9af0`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800f988b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800f99a1`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800f988b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800f99a1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800f9c8a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800f9c8a`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800f9a59`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800f9a59`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800f9b3c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800f9b3c`

## string_xrefs

- `0x1800f98dd`: `Unexpected result from InitializeProcThreadAttributeList`
- `0x1800f9df0`: `Unexpected result from InitializeProcThreadAttributeList`
- `0x1800f99d0`: `Failed to initialize ProcThreadAttributeList.`
- `0x1800f9951`: `Failed to allocate ProcThreadAttributeList.`
- `0x1800f9b6b`: `Failed to create process.`

## pseudocode

```c
__int64 __fastcall CreateProcessWithMitigationPolicy(const wchar_t *a1, wchar_t *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v6; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v7; // rsi
  const struct std::nothrow_t *v8; // rdx
  signed int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  const struct std::nothrow_t *v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // eax
  const struct std::nothrow_t *v18; // rdx
  unsigned int cbSize; // [rsp+20h] [rbp-E0h]
  unsigned int v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hHandle; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  ULONG_PTR Size; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v27; // [rsp+F8h] [rbp-8h]
  int v28; // [rsp+100h] [rbp+0h] BYREF
  DWORD ExitCode[3]; // [rsp+104h] [rbp+4h] BYREF
  __int64 Value; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v23 = 0;
  Value = 0x100000000000LL;
  hHandle = 0;
  *(_QWORD *)&StartupInfo.cb = 112;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  Size = 0;
  if ( InitializeProcThreadAttributeList(0, 1u, 0, &Size) )
  {
    v4 = -2147418113;
    v28 = -2147418113;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unexpected result from InitializeProcThreadAttributeList");
      *(_QWORD *)v21 = &v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v5 = 268;
    goto LABEL_66;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 != -2147024774 && (v4 & 0x80000000) != 0 )
  {
    v28 = v4;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unexpected result from InitializeProcThreadAttributeList");
      *(_QWORD *)v21 = &v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v5 = 263;
LABEL_66:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscoreshutdown.cpp",
      (const char *)v4,
      cbSize);
    goto LABEL_67;
  }
  v6 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)operator new[](Size);
  v7 = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    v28 = -2147024882;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate ProcThreadAttributeList.");
      *(_QWORD *)v21 = &v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v5 = 272;
    goto LABEL_66;
  }
  if ( InitializeProcThreadAttributeList(v6, 1u, 0, &Size) )
  {
    if ( UpdateProcThreadAttribute(v7, 0, 0x20007u, &Value, 8u, 0, 0) )
    {
      v27 = v7;
      SetErrorMode(1u);
      if ( CreateProcessW(0, a2, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&v23, ProcessInformation.hThread);
        Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hHandle, ProcessInformation.hProcess);
        ExitCode[0] = WaitForSingleObject(hHandle, 0xFFFFFFFF);
        if ( ExitCode[0] )
        {
          v9 = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed wait on process.");
            if ( v9 > 0 )
              v14 = (unsigned __int16)v9 | 0x80070000;
            else
              v14 = v9;
            v28 = v14;
            *(_QWORD *)v21 = &v28;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {0}",
              (__int64)v21);
          }
          if ( v9 )
          {
            v11 = 313;
            goto LABEL_61;
          }
        }
        else
        {
          if ( GetExitCodeProcess(hHandle, ExitCode) )
          {
            v9 = ExitCode[0];
            if ( !ExitCode[0] )
            {
              operator delete(v7, v15);
              Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hHandle);
              Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v23);
              return 0;
            }
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Process failed");
              if ( v9 > 0 )
                v17 = (unsigned __int16)v9 | 0x80070000;
              else
                v17 = v9;
              v28 = v17;
              *(_QWORD *)v21 = &v28;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {0}",
                (__int64)v21);
            }
            v11 = 316;
            goto LABEL_61;
          }
          v9 = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get exit code for process.");
            if ( v9 > 0 )
              v16 = (unsigned __int16)v9 | 0x80070000;
            else
              v16 = v9;
            v28 = v16;
            *(_QWORD *)v21 = &v28;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {0}",
              (__int64)v21);
          }
          if ( v9 )
          {
            v11 = 315;
            goto LABEL_61;
          }
        }
      }
      else
      {
        v9 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create process.");
          if ( v9 > 0 )
            v13 = (unsigned __int16)v9 | 0x80070000;
          else
            v13 = v9;
          v28 = v13;
          *(_QWORD *)v21 = &v28;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v21);
        }
        if ( v9 )
        {
          v11 = 305;
          goto LABEL_61;
        }
      }
    }
    else
    {
      v9 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set mitigation policy attribute.");
        if ( v9 > 0 )
          v12 = (unsigned __int16)v9 | 0x80070000;
        else
          v12 = v9;
        v28 = v12;
        *(_QWORD *)v21 = &v28;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v21);
      }
      if ( v9 )
      {
        v11 = 286;
        goto LABEL_61;
      }
    }
  }
  else
  {
    v9 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initialize ProcThreadAttributeList.");
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      else
        v10 = v9;
      v28 = v10;
      *(_QWORD *)v21 = &v28;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v21);
    }
    if ( v9 )
    {
      v11 = 275;
LABEL_61:
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"onecore\\base\\cbs\\core\\cbscoreshutdown.cpp",
             (const char *)(unsigned int)v9,
             cbSize);
      operator delete(v7, v18);
      goto LABEL_67;
    }
  }
  operator delete(v7, v8);
  v4 = 0;
LABEL_67:
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hHandle);
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v23);
  return v4;
}

```

## disassembly

```asm
0x1800f9804  mov     [rsp-8+arg_0], rbx
0x1800f9809  mov     [rsp-8+arg_10], rsi
0x1800f980e  push    rbp
0x1800f980f  push    rdi
0x1800f9810  push    r15
0x1800f9812  lea     rbp, [rsp-30h]
0x1800f9817  sub     rsp, 130h
0x1800f981e  mov     rax, cs:__security_cookie
0x1800f9825  xor     rax, rsp
0x1800f9828  mov     [rbp+40h+var_20], rax
0x1800f982c  mov     rax, 100000000000h
0x1800f9836  mov     [rsp+140h+var_E0], 0
0x1800f983f  mov     [rbp+40h+Value], rax
0x1800f9843  lea     rcx, [rbp+40h+StartupInfo.lpReserved]; void *
0x1800f9847  xor     eax, eax
0x1800f9849  mov     [rsp+140h+hHandle], 0
0x1800f9852  mov     rdi, rdx
0x1800f9855  mov     qword ptr [rbp+40h+ProcessInformation.dwProcessId], rax
0x1800f9859  xorps   xmm0, xmm0
0x1800f985c  mov     qword ptr [rbp+40h+StartupInfo.cb], 70h ; 'p'
0x1800f9864  xor     edx, edx; Val
0x1800f9866  lea     r8d, [rax+68h]; Size
0x1800f986a  movups  xmmword ptr [rsp+140h+ProcessInformation.hProcess], xmm0
0x1800f986f  call    memset_0
0x1800f9874  xor     r8d, r8d; dwFlags
0x1800f9877  mov     [rsp+140h+Size], 0
0x1800f9880  lea     r9, [rsp+140h+Size]; lpSize
0x1800f9885  xor     ecx, ecx; lpAttributeList
0x1800f9887  lea     edx, [r8+1]; dwAttributeCount
0x1800f988b  call    cs:__imp_InitializeProcThreadAttributeList
0x1800f9892  nop     dword ptr [rax+rax+00h]
0x1800f9897  test    eax, eax
0x1800f9899  jnz     loc_1800F9DD7
0x1800f989f  call    cs:__imp_GetLastError
0x1800f98a6  nop     dword ptr [rax+rax+00h]
0x1800f98ab  mov     ebx, eax
0x1800f98ad  mov     r15d, 80070000h
0x1800f98b3  test    eax, eax
0x1800f98b5  jle     short loc_1800F98BD
0x1800f98b7  movzx   ebx, ax
0x1800f98ba  or      ebx, r15d
0x1800f98bd  cmp     ebx, 8007007Ah
0x1800f98c3  jz      short loc_1800F9923
0x1800f98c5  test    ebx, ebx
0x1800f98c7  jns     short loc_1800F9923
0x1800f98c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f98d0  mov     [rbp+40h+var_40], ebx
0x1800f98d3  test    rcx, rcx
0x1800f98d6  jz      short loc_1800F9919
0x1800f98d8  mov     edi, 3
0x1800f98dd  lea     r9, aUnexpectedResu; "Unexpected result from InitializeProcTh"...
0x1800f98e4  mov     r8d, edi
0x1800f98e7  xor     edx, edx
0x1800f98e9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f98ee  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f98f5  lea     rax, [rbp+40h+var_40]
0x1800f98f9  mov     qword ptr [rsp+140h+var_F0], rax
0x1800f98fe  lea     r9, asc_1802EE7AC; ": {}"
0x1800f9905  lea     rax, [rsp+140h+var_F0]
0x1800f990a  mov     r8d, edi
0x1800f990d  mov     dl, 1
0x1800f990f  mov     [rsp+140h+cbSize], rax
0x1800f9914  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f9919  mov     edx, 107h
0x1800f991e  jmp     loc_1800F9E31
0x1800f9923  mov     rcx, [rsp+140h+Size]; unsigned __int64
0x1800f9928  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800f992d  mov     rsi, rax
0x1800f9930  test    rax, rax
0x1800f9933  jnz     short loc_1800F9992
0x1800f9935  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f993c  mov     ebx, 8007000Eh
0x1800f9941  mov     [rbp+40h+var_40], ebx
0x1800f9944  test    rcx, rcx
0x1800f9947  jz      short loc_1800F9988
0x1800f9949  lea     edi, [rax+3]
0x1800f994c  xor     edx, edx
0x1800f994e  mov     r8d, edi
0x1800f9951  lea     r9, aFailedToAlloca_25; "Failed to allocate ProcThreadAttributeL"...
0x1800f9958  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f995d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9964  lea     rax, [rbp+40h+var_40]
0x1800f9968  mov     qword ptr [rsp+140h+var_F0], rax
0x1800f996d  lea     r9, asc_1802EE7AC; ": {}"
0x1800f9974  lea     rax, [rsp+140h+var_F0]
0x1800f9979  mov     r8d, edi
0x1800f997c  mov     dl, 1
0x1800f997e  mov     [rsp+140h+cbSize], rax
0x1800f9983  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f9988  mov     edx, 110h
0x1800f998d  jmp     loc_1800F9E31
0x1800f9992  xor     r8d, r8d; dwFlags
0x1800f9995  lea     r9, [rsp+140h+Size]; lpSize
0x1800f999a  mov     rcx, rsi; lpAttributeList
0x1800f999d  lea     edx, [r8+1]; dwAttributeCount
0x1800f99a1  call    cs:__imp_InitializeProcThreadAttributeList
0x1800f99a8  nop     dword ptr [rax+rax+00h]
0x1800f99ad  test    eax, eax
0x1800f99af  jnz     short loc_1800F9A2F
0x1800f99b1  call    cs:__imp_GetLastError
0x1800f99b8  nop     dword ptr [rax+rax+00h]
0x1800f99bd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f99c4  mov     ebx, eax
0x1800f99c6  test    rcx, rcx
0x1800f99c9  jz      short loc_1800F9A1D
0x1800f99cb  mov     edi, 3
0x1800f99d0  lea     r9, aFailedToInitia_5; "Failed to initialize ProcThreadAttribut"...
0x1800f99d7  mov     r8d, edi
0x1800f99da  xor     edx, edx
0x1800f99dc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f99e1  test    ebx, ebx
0x1800f99e3  jg      short loc_1800F99E9
0x1800f99e5  mov     eax, ebx
0x1800f99e7  jmp     short loc_1800F99EF
0x1800f99e9  movzx   eax, bx
0x1800f99ec  or      eax, r15d
0x1800f99ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f99f6  lea     r9, a0; ": {0}"
0x1800f99fd  mov     [rbp+40h+var_40], eax
0x1800f9a00  mov     r8d, edi
0x1800f9a03  lea     rax, [rbp+40h+var_40]
0x1800f9a07  mov     dl, 1
0x1800f9a09  mov     qword ptr [rsp+140h+var_F0], rax
0x1800f9a0e  lea     rax, [rsp+140h+var_F0]
0x1800f9a13  mov     [rsp+140h+cbSize], rax
0x1800f9a18  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f9a1d  test    ebx, ebx
0x1800f9a1f  jz      loc_1800F9D15
0x1800f9a25  mov     edx, 113h
0x1800f9a2a  jmp     loc_1800F9D92
0x1800f9a2f  mov     [rsp+140h+lpReturnSize], 0; lpReturnSize
0x1800f9a38  lea     r9, [rbp+40h+Value]; lpValue
0x1800f9a3c  mov     [rsp+140h+lpPreviousValue], 0; lpPreviousValue
0x1800f9a45  xor     edx, edx; dwFlags
0x1800f9a47  mov     r8d, 20007h; Attribute
0x1800f9a4d  mov     [rsp+140h+cbSize], 8; cbSize
0x1800f9a56  mov     rcx, rsi; lpAttributeList
0x1800f9a59  call    cs:__imp_UpdateProcThreadAttribute
0x1800f9a60  nop     dword ptr [rax+rax+00h]
0x1800f9a65  test    eax, eax
0x1800f9a67  jnz     short loc_1800F9AE7
0x1800f9a69  call    cs:__imp_GetLastError
0x1800f9a70  nop     dword ptr [rax+rax+00h]
0x1800f9a75  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9a7c  mov     ebx, eax
0x1800f9a7e  test    rcx, rcx
0x1800f9a81  jz      short loc_1800F9AD5
0x1800f9a83  mov     edi, 3
0x1800f9a88  lea     r9, aFailedToSetMit; "Failed to set mitigation policy attribu"...
0x1800f9a8f  mov     r8d, edi
0x1800f9a92  xor     edx, edx
0x1800f9a94  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f9a99  test    ebx, ebx
0x1800f9a9b  jg      short loc_1800F9AA1
0x1800f9a9d  mov     eax, ebx
0x1800f9a9f  jmp     short loc_1800F9AA7
0x1800f9aa1  movzx   eax, bx
0x1800f9aa4  or      eax, r15d
0x1800f9aa7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9aae  lea     r9, a0; ": {0}"
0x1800f9ab5  mov     [rbp+40h+var_40], eax
0x1800f9ab8  mov     r8d, edi
0x1800f9abb  lea     rax, [rbp+40h+var_40]
0x1800f9abf  mov     dl, 1
0x1800f9ac1  mov     qword ptr [rsp+140h+var_F0], rax
0x1800f9ac6  lea     rax, [rsp+140h+var_F0]
0x1800f9acb  mov     [rsp+140h+cbSize], rax
0x1800f9ad0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f9ad5  test    ebx, ebx
0x1800f9ad7  jz      loc_1800F9D15
0x1800f9add  mov     edx, 11Eh
0x1800f9ae2  jmp     loc_1800F9D92
0x1800f9ae7  mov     ecx, 1; uMode
0x1800f9aec  mov     [rbp+40h+var_48], rsi
0x1800f9af0  call    cs:__imp_SetErrorMode
0x1800f9af7  nop     dword ptr [rax+rax+00h]
0x1800f9afc  lea     rax, [rsp+140h+ProcessInformation]
0x1800f9b01  xor     r9d, r9d; lpThreadAttributes
0x1800f9b04  mov     [rsp+140h+lpProcessInformation], rax; lpProcessInformation
0x1800f9b09  xor     r8d, r8d; lpProcessAttributes
0x1800f9b0c  lea     rax, [rbp+40h+StartupInfo]
0x1800f9b10  mov     rdx, rdi; lpCommandLine
0x1800f9b13  mov     [rsp+140h+lpStartupInfo], rax; lpStartupInfo
0x1800f9b18  xor     ecx, ecx; lpApplicationName
0x1800f9b1a  mov     [rsp+140h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800f9b23  mov     [rsp+140h+lpReturnSize], 0; lpEnvironment
0x1800f9b2c  mov     dword ptr [rsp+140h+lpPreviousValue], 8000000h; dwCreationFlags
0x1800f9b34  mov     dword ptr [rsp+140h+cbSize], 0; bInheritHandles
0x1800f9b3c  call    cs:__imp_CreateProcessW
0x1800f9b43  nop     dword ptr [rax+rax+00h]
0x1800f9b48  test    eax, eax
0x1800f9b4a  jnz     short loc_1800F9BCA
0x1800f9b4c  call    cs:__imp_GetLastError
0x1800f9b53  nop     dword ptr [rax+rax+00h]
0x1800f9b58  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9b5f  mov     ebx, eax
0x1800f9b61  test    rcx, rcx
0x1800f9b64  jz      short loc_1800F9BB8
0x1800f9b66  mov     edi, 3
0x1800f9b6b  lea     r9, aFailedToCreate_59; "Failed to create process."
0x1800f9b72  mov     r8d, edi
0x1800f9b75  xor     edx, edx
0x1800f9b77  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f9b7c  test    ebx, ebx
0x1800f9b7e  jg      short loc_1800F9B84
0x1800f9b80  mov     eax, ebx
0x1800f9b82  jmp     short loc_1800F9B8A
0x1800f9b84  movzx   eax, bx
0x1800f9b87  or      eax, r15d
0x1800f9b8a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9b91  lea     r9, a0; ": {0}"
0x1800f9b98  mov     [rbp+40h+var_40], eax
0x1800f9b9b  mov     r8d, edi
0x1800f9b9e  lea     rax, [rbp+40h+var_40]
0x1800f9ba2  mov     dl, 1
0x1800f9ba4  mov     qword ptr [rsp+140h+var_F0], rax
0x1800f9ba9  lea     rax, [rsp+140h+var_F0]
0x1800f9bae  mov     [rsp+140h+cbSize], rax
0x1800f9bb3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f9bb8  test    ebx, ebx
0x1800f9bba  jz      loc_1800F9D15
0x1800f9bc0  mov     edx, 131h
0x1800f9bc5  jmp     loc_1800F9D92
0x1800f9bca  mov     rdx, [rsp+140h+ProcessInformation.hThread]
0x1800f9bcf  lea     rcx, [rsp+140h+var_E0]
0x1800f9bd4  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800f9bd9  mov     rdx, [rsp+140h+ProcessInformation.hProcess]
0x1800f9bde  lea     rcx, [rsp+140h+hHandle]
0x1800f9be3  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800f9be8  mov     rcx, [rsp+140h+hHandle]; hHandle
0x1800f9bed  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800f9bf0  call    cs:__imp_WaitForSingleObject
0x1800f9bf7  nop     dword ptr [rax+rax+00h]
0x1800f9bfc  mov     [rbp+40h+ExitCode], eax
0x1800f9bff  test    eax, eax
0x1800f9c01  jz      short loc_1800F9C81
0x1800f9c03  call    cs:__imp_GetLastError
0x1800f9c0a  nop     dword ptr [rax+rax+00h]
0x1800f9c0f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9c16  mov     ebx, eax
0x1800f9c18  test    rcx, rcx
0x1800f9c1b  jz      short loc_1800F9C6F
0x1800f9c1d  mov     edi, 3
0x1800f9c22  lea     r9, aFailedWaitOnPr; "Failed wait on process."
0x1800f9c29  mov     r8d, edi
0x1800f9c2c  xor     edx, edx
0x1800f9c2e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f9c33  test    ebx, ebx
0x1800f9c35  jg      short loc_1800F9C3B
0x1800f9c37  mov     eax, ebx
0x1800f9c39  jmp     short loc_1800F9C41
0x1800f9c3b  movzx   eax, bx
0x1800f9c3e  or      eax, r15d
0x1800f9c41  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9c48  lea     r9, a0; ": {0}"
0x1800f9c4f  mov     [rbp+40h+var_40], eax
0x1800f9c52  mov     r8d, edi
0x1800f9c55  lea     rax, [rbp+40h+var_40]
0x1800f9c59  mov     dl, 1
0x1800f9c5b  mov     qword ptr [rsp+140h+var_F0], rax
0x1800f9c60  lea     rax, [rsp+140h+var_F0]
0x1800f9c65  mov     [rsp+140h+cbSize], rax
0x1800f9c6a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f9c6f  test    ebx, ebx
0x1800f9c71  jz      loc_1800F9D15
0x1800f9c77  mov     edx, 139h
0x1800f9c7c  jmp     loc_1800F9D92
0x1800f9c81  mov     rcx, [rsp+140h+hHandle]; hProcess
0x1800f9c86  lea     rdx, [rbp+40h+ExitCode]; lpExitCode
0x1800f9c8a  call    cs:__imp_GetExitCodeProcess
0x1800f9c91  nop     dword ptr [rax+rax+00h]
0x1800f9c96  test    eax, eax
0x1800f9c98  jnz     loc_1800F9D24
0x1800f9c9e  call    cs:__imp_GetLastError
0x1800f9ca5  nop     dword ptr [rax+rax+00h]
0x1800f9caa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9cb1  mov     ebx, eax
0x1800f9cb3  test    rcx, rcx
0x1800f9cb6  jz      short loc_1800F9D0A
0x1800f9cb8  mov     edi, 3
0x1800f9cbd  lea     r9, aFailedToGetExi; "Failed to get exit code for process."
0x1800f9cc4  mov     r8d, edi
0x1800f9cc7  xor     edx, edx
0x1800f9cc9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f9cce  test    ebx, ebx
0x1800f9cd0  jg      short loc_1800F9CD6
0x1800f9cd2  mov     eax, ebx
0x1800f9cd4  jmp     short loc_1800F9CDC
0x1800f9cd6  movzx   eax, bx
0x1800f9cd9  or      eax, r15d
0x1800f9cdc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f9ce3  lea     r9, a0; ": {0}"
0x1800f9cea  mov     [rbp+40h+var_40], eax
0x1800f9ced  mov     r8d, edi
0x1800f9cf0  lea     rax, [rbp+40h+var_40]
0x1800f9cf4  mov     dl, 1
0x1800f9cf6  mov     qword ptr [rsp+140h+var_F0], rax
0x1800f9cfb  lea     rax, [rsp+140h+var_F0]
0x1800f9d00  mov     [rsp+140h+cbSize], rax
0x1800f9d05  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
  ... truncated ...
```
