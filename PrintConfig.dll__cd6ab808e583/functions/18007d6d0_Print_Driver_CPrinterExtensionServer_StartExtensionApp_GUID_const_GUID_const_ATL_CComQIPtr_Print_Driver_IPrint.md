# Print::Driver::CPrinterExtensionServer::StartExtensionApp(_GUID const &,_GUID const &,ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92> &)

- ea: `0x18007d6d0`
- end: `0x18007e3ec`
- name: `?StartExtensionApp@CPrinterExtensionServer@Driver@Print@@AEAAXAEBU_GUID@@0AEAV?$CComQIPtr@UIPrinterExtensionServerPrivate@Driver@Print@@$1?_GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92@@3U__s_GUID@@B@ATL@@@Z`
- size: `3356`
- prototype: `int __fastcall(Print::Driver::CPrinterExtensionServer *, _OWORD *, _OWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007cc68`

## callees

- `0x1800032e0`
- `0x180003b00`
- `0x180004418`
- `0x180004424`
- `0x18000f380`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018bbc`
- `0x180035948`
- `0x18003744c`
- `0x180037580`
- `0x18007b2ec`
- `0x18007b364`
- `0x18007b8f4`
- `0x18007c128`
- `0x18007d6d0`
- `0x18007e3f4`
- `0x18007e6b0`
- `0x180085374`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18007db3a`
- `KERNEL32!IsDebuggerPresent` at `0x18007db3a`
- `KERNEL32!CloseHandle` at `0x18007e08a`
- `KERNEL32!CloseHandle` at `0x18007e09f`
- `KERNEL32!CloseHandle` at `0x18007e0b8`
- `KERNEL32!CloseHandle` at `0x18007e0cc`
- `KERNEL32!CloseHandle` at `0x18007e133`
- `KERNEL32!CloseHandle` at `0x18007e08a`
- `KERNEL32!CloseHandle` at `0x18007e09f`
- `KERNEL32!CloseHandle` at `0x18007e0b8`
- `KERNEL32!CloseHandle` at `0x18007e0cc`
- `KERNEL32!CloseHandle` at `0x18007e133`
- `KERNEL32!LeaveCriticalSection` at `0x18007e0da`
- `KERNEL32!LeaveCriticalSection` at `0x18007e0da`
- `KERNEL32!EnterCriticalSection` at `0x18007d895`
- `KERNEL32!EnterCriticalSection` at `0x18007d895`
- `KERNEL32!GetLastError` at `0x18007da25`
- `KERNEL32!GetLastError` at `0x18007da42`
- `KERNEL32!GetLastError` at `0x18007da78`
- `KERNEL32!GetLastError` at `0x18007dd3a`
- `KERNEL32!GetLastError` at `0x18007deda`
- `KERNEL32!GetLastError` at `0x18007e2c6`
- `KERNEL32!GetLastError` at `0x18007e328`
- `KERNEL32!GetLastError` at `0x18007e38a`
- `KERNEL32!GetLastError` at `0x18007da25`
- `KERNEL32!GetLastError` at `0x18007da42`
- `KERNEL32!GetLastError` at `0x18007da78`
- `KERNEL32!GetLastError` at `0x18007dd3a`
- `KERNEL32!GetLastError` at `0x18007deda`
- `KERNEL32!GetLastError` at `0x18007e2c6`
- `KERNEL32!GetLastError` at `0x18007e328`
- `KERNEL32!GetLastError` at `0x18007e38a`
- `KERNEL32!TerminateJobObject` at `0x18007de98`
- `KERNEL32!TerminateJobObject` at `0x18007de98`
- `KERNEL32!CreateWaitableTimerW` at `0x18007dac4`
- `KERNEL32!CreateWaitableTimerW` at `0x18007dac4`
- `KERNEL32!WaitForMultipleObjects` at `0x18007dc17`
- `KERNEL32!WaitForMultipleObjects` at `0x18007dc17`
- `KERNEL32!CreateJobObjectW` at `0x18007d8cc`
- `KERNEL32!CreateJobObjectW` at `0x18007d8cc`
- `KERNEL32!AssignProcessToJobObject` at `0x18007da14`
- `KERNEL32!AssignProcessToJobObject` at `0x18007da14`
- `KERNEL32!ResumeThread` at `0x18007da37`
- `KERNEL32!ResumeThread` at `0x18007da37`
- `KERNEL32!TerminateProcess` at `0x18007da6e`
- `KERNEL32!TerminateProcess` at `0x18007da6e`
- `KERNEL32!IsProcessInJob` at `0x18007dd30`
- `KERNEL32!IsProcessInJob` at `0x18007dd30`
- `OLEAUT32!__imp_SysFreeString` at `0x18007e11e`
- `OLEAUT32!__imp_SysFreeString` at `0x18007e11e`
- `ADVAPI32!CreateProcessAsUserW` at `0x18007d9dc`
- `ADVAPI32!CreateProcessAsUserW` at `0x18007d9dc`
- `ole32!CoRevertToSelf` at `0x18007d8b5`
- `ole32!CoRevertToSelf` at `0x18007d8b5`
- `ole32!CoImpersonateClient` at `0x18007daae`
- `ole32!CoImpersonateClient` at `0x18007daae`
- `USERENV!CreateEnvironmentBlock` at `0x18007d8f8`
- `USERENV!CreateEnvironmentBlock` at `0x18007d8f8`

## string_xrefs

- `0x18007da1a`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007db85`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007dbf9`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007dd13`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007dd6d`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007ddbe`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007de2b`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007de63`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007decc`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007df1d`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007df87`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007dff4`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18007da48`: `ResumeThread client=%u(0x%p) error=%u; Process will be terminated.`
- `0x18007dd0c`: `client=%u(0x%p) driverId=%ws; Matched on processId.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
int __fastcall Print::Driver::CPrinterExtensionServer::StartExtensionApp(
        Print::Driver::CPrinterExtensionServer *a1,
        _OWORD *a2,
        _OWORD *a3,
        __int64 *a4)
{
  __int64 *v4; // r13
  int v7; // edi
  HANDLE v8; // rbx
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  char v13; // r15
  HANDLE v14; // rdi
  HRESULT v15; // eax
  HANDLE JobObjectW; // rsi
  __int64 v17; // r14
  void *lpEnvironment; // rbx
  _QWORD *v19; // rdx
  const WCHAR *lpCurrentDirectory; // rax
  HANDLE hProcess; // r12
  HANDLE hThread; // rbx
  DWORD v23; // eax
  unsigned __int16 *v24; // rdx
  signed int v25; // ebx
  bool v26; // sf
  __int64 v27; // rbx
  char *WaitableTimerW; // rsi
  _OWORD *v29; // rdi
  __int128 *v30; // rax
  _QWORD *v31; // rax
  __int128 *v32; // rax
  __int64 v33; // rcx
  _QWORD *v34; // rax
  _QWORD *v35; // rdi
  HANDLE v36; // rsi
  __int64 v37; // r13
  __int64 v38; // r12
  unsigned int v39; // eax
  unsigned int v40; // r13d
  __int128 *v41; // rcx
  DWORD v42; // eax
  __int128 *v43; // rcx
  __int128 *v44; // rcx
  __int128 *v45; // rax
  __int128 *v46; // rax
  __int128 *v47; // rax
  signed int v48; // eax
  unsigned int v49; // ecx
  __int128 *v50; // rax
  __int128 *v51; // rax
  __int128 *v52; // rax
  __int64 v53; // rdi
  __int128 *v54; // r15
  __int128 *v55; // r14
  unsigned int v56; // eax
  __int64 v57; // rcx
  int result; // eax
  signed int LastError; // eax
  unsigned int v60; // ebx
  signed int v61; // eax
  unsigned int v62; // ebx
  signed int v63; // eax
  unsigned int v64; // ebx
  DWORD lpThreadAttributes; // [rsp+28h] [rbp-E0h]
  BOOL bInheritHandles[2]; // [rsp+30h] [rbp-D8h]
  HANDLE JobHandle; // [rsp+70h] [rbp-98h] BYREF
  BOOL Result[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 *v69; // [rsp+80h] [rbp-88h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+88h] [rbp-80h] BYREF
  LPVOID Environment; // [rsp+A0h] [rbp-68h] BYREF
  LPWSTR lpCommandLine; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v73; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v74; // [rsp+B8h] [rbp-50h] BYREF
  HANDLE hToken; // [rsp+C0h] [rbp-48h] BYREF
  HANDLE pExceptionObject[4]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v77[2]; // [rsp+E8h] [rbp-20h] BYREF
  _OWORD *v78; // [rsp+F8h] [rbp-10h]
  _OWORD *v79; // [rsp+100h] [rbp-8h]
  __int64 v80; // [rsp+108h] [rbp+0h]
  HANDLE v81; // [rsp+110h] [rbp+8h]
  _OWORD v82[2]; // [rsp+118h] [rbp+10h] BYREF
  HANDLE v83; // [rsp+138h] [rbp+30h]
  HANDLE v84; // [rsp+140h] [rbp+38h]
  __int64 v85; // [rsp+148h] [rbp+40h]
  HANDLE ProcessHandle; // [rsp+150h] [rbp+48h]
  HANDLE hObject; // [rsp+158h] [rbp+50h]
  _QWORD v88[7]; // [rsp+160h] [rbp+58h] BYREF
  _QWORD *v89; // [rsp+198h] [rbp+90h]
  __int64 v90; // [rsp+1A0h] [rbp+98h]
  struct _STARTUPINFOW StartupInfo; // [rsp+1A8h] [rbp+A0h] BYREF
  __int128 v92; // [rsp+218h] [rbp+110h] BYREF
  __int64 v93; // [rsp+228h] [rbp+120h]
  unsigned __int64 v94; // [rsp+230h] [rbp+128h]
  __int128 v95; // [rsp+238h] [rbp+130h] BYREF
  __int64 v96; // [rsp+248h] [rbp+140h]
  unsigned __int64 v97; // [rsp+250h] [rbp+148h]
  LPCWSTR v98[2]; // [rsp+258h] [rbp+150h] BYREF
  __int64 v99; // [rsp+268h] [rbp+160h]
  unsigned __int64 v100; // [rsp+270h] [rbp+168h]
  __int128 v101; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v102[56]; // [rsp+288h] [rbp+180h] BYREF
  __int64 v103; // [rsp+2C0h] [rbp+1B8h]
  void *v104; // [rsp+2C8h] [rbp+1C0h]
  HANDLE Handles[3]; // [rsp+2D8h] [rbp+1D0h] BYREF

  v90 = -2;
  v4 = a4;
  v69 = a4;
  v79 = a3;
  v78 = a2;
  hToken = 0;
  Print::Driver::CPrinterExtensionServer::CreateRestrictedToken(a1, (struct Win32HandleRAII *)&hToken);
  v101 = 0;
  lpCommandLine = 0;
  v73 = 0;
  v74 = 0;
  JobHandle = 0;
  v7 = ATL::CComObject<PrintConfig::CPrinterExtensionManager>::CreateInstance(&JobHandle);
  if ( v7 < 0 )
  {
    v73 = 0;
    goto LABEL_120;
  }
  v8 = JobHandle;
  (*(void (__fastcall **)(HANDLE))(*(_QWORD *)JobHandle + 8LL))(JobHandle);
  v7 = (**(__int64 (__fastcall ***)(HANDLE, GUID *, __int64 *))v8)(v8, &GUID_93c6eb8c_b001_4355_9629_8e8a1b3f8e77, &v73);
  (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v7 < 0 )
  {
LABEL_120:
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        28,
        WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        (unsigned int)v7);
    }
    hr_error::hr_error((hr_error *)v82, v7);
    throw (hr_error *)v82;
  }
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v73)(
         v73,
         &GUID_4f27786b_13a2_4df5_857c_3eea48d4839b,
         &v74);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        29,
        WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        (unsigned int)v9);
    }
    hr_error::hr_error((hr_error *)v82, v10);
    throw (hr_error *)v82;
  }
  v82[0] = *a3;
  *(_OWORD *)pExceptionObject = *a2;
  v11 = (*(__int64 (__fastcall **)(__int64, HANDLE *, _OWORD *, __int128 *, LPWSTR *))(*(_QWORD *)v74 + 24LL))(
          v74,
          pExceptionObject,
          v82,
          &v101,
          &lpCommandLine);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        30,
        WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        (unsigned int)v11);
    }
    hr_error::hr_error((hr_error *)v82, v12);
    throw (hr_error *)v82;
  }
  *(_OWORD *)v98 = 0;
  v99 = 0;
  v100 = 7;
  LOWORD(v98[0]) = 0;
  Win32Adapters::FileSystem::GetFolderFromFullPath(&lpCommandLine, v98);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = L"winsta0\\default";
  StartupInfo.dwFlags = 65;
  v13 = 1;
  StartupInfo.wShowWindow = 1;
  v14 = hToken;
  *(_QWORD *)&v82[0] = &Print::Driver::CPrinterExtensionServer::s_startLock;
  EnterCriticalSection(&Print::Driver::CPrinterExtensionServer::s_startLock);
  v80 = 0;
  v83 = 0;
  v84 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v15 = CoRevertToSelf();
  if ( v15 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v15);
    throw (hr_error *)pExceptionObject;
  }
  JobObjectW = CreateJobObjectW(0, 0);
  JobHandle = JobObjectW;
  v17 = (__int64)JobObjectW;
  v80 = (__int64)JobObjectW;
  if ( !JobObjectW )
  {
    LastError = GetLastError();
    v60 = LastError;
    if ( LastError > 0 )
      v60 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids, v60);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v60);
    throw (hr_error *)pExceptionObject;
  }
  Environment = 0;
  if ( !CreateEnvironmentBlock(&Environment, v14, 0) )
  {
    v61 = GetLastError();
    v62 = v61;
    if ( v61 > 0 )
      v62 = (unsigned __int16)v61 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids, v62);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v62);
    throw (hr_error *)pExceptionObject;
  }
  lpEnvironment = Environment;
  v88[0] = &std::_Func_impl_no_alloc<_lambda_14c74629e3f443f77d94d33812d945c0_,void,void *>::`vftable';
  v89 = v88;
  pExceptionObject[0] = v88;
  v81 = v102;
  v103 = 0;
  v103 = std::_Func_impl_no_alloc__lambda_14c74629e3f443f77d94d33812d945c0__void_void___::_Move(v88, v102);
  v104 = lpEnvironment;
  if ( v89 )
  {
    v19 = v88;
    LOBYTE(v19) = v89 != v88;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v89 + 32LL))(v89, v19);
    v89 = 0;
    lpEnvironment = v104;
  }
  lpCurrentDirectory = (const WCHAR *)v98;
  if ( v100 > 7 )
    lpCurrentDirectory = v98[0];
  if ( !CreateProcessAsUserW(
          v14,
          0,
          lpCommandLine,
          0,
          0,
          0,
          0x434u,
          lpEnvironment,
          lpCurrentDirectory,
          &StartupInfo,
          &ProcessInformation) )
  {
    v63 = GetLastError();
    v64 = v63;
    if ( v63 > 0 )
      v64 = (unsigned __int16)v63 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids, v64);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v64);
    throw (hr_error *)pExceptionObject;
  }
  Print::Driver::GenericRAII<void *>::~GenericRAII<void *>(v102);
  hProcess = ProcessInformation.hProcess;
  pExceptionObject[0] = ProcessInformation.hProcess;
  v83 = ProcessInformation.hProcess;
  hThread = ProcessInformation.hThread;
  v81 = ProcessInformation.hThread;
  v84 = ProcessInformation.hThread;
  if ( AssignProcessToJobObject(JobObjectW, ProcessInformation.hProcess) )
  {
    if ( ResumeThread(hThread) != -1 )
      goto LABEL_23;
    v23 = GetLastError();
    v24 = L"ResumeThread client=%u(0x%p) error=%u; Process will be terminated.";
  }
  else
  {
    v23 = GetLastError();
    v24 = L"AssignProcessToJobObject client=%u(0x%p) error=%u; Process will be terminated.";
  }
  v25 = v23;
  lpThreadAttributes = v23;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
    "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
    v24,
    ProcessInformation.dwProcessId,
    *v4);
  if ( v25 )
  {
    if ( !TerminateProcess(hProcess, v25) )
    {
      lpThreadAttributes = GetLastError();
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
        L"TerminateProcess client=%u(0x%p) error=%u; Process could not be terminated and is suspended resource leak.",
        ProcessInformation.dwProcessId,
        *v4);
    }
    v26 = v25 < 0;
    if ( v25 > 0 )
    {
      v25 = (unsigned __int16)v25 | 0x80070000;
      v26 = v25 < 0;
    }
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          34,
          WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
          (unsigned int)v25);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v25);
      throw (hr_error *)pExceptionObject;
    }
  }
LABEL_23:
  v27 = 0;
  if ( CoImpersonateClient() < 0 )
    __int2c();
  WaitableTimerW = (char *)CreateWaitableTimerW(0, 1, 0);
  hObject = WaitableTimerW;
  v92 = 0;
  v93 = 0;
  v94 = 7;
  LOWORD(v92) = 0;
  v29 = v78;
  Win32Adapters::Guid::StringFromGuid(v78, &v92);
  v95 = 0;
  v96 = 0;
  v97 = 7;
  LOWORD(v95) = 0;
  Win32Adapters::Guid::StringFromGuid(v79, &v95);
  if ( !IsDebuggerPresent() )
  {
    Win32Adapters::Synchronization::SetWaitableTimerEx(
      (Win32Adapters::Synchronization *)WaitableTimerW,
      (void *const)0x1388,
      0x3E8u,
      0,
      lpThreadAttributes);
    v30 = &v92;
    if ( v94 > 7 )
      v30 = (__int128 *)v92;
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
      L"client=%u(0x%p) driverId=%ws; Timer set.",
      ProcessInformation.dwProcessId,
      *v4,
      v30);
  }
  Handles[0] = hProcess;
  Handles[1] = Print::Driver::CPrinterExtensionServer::s_activeClientAdded;
  Handles[2] = WaitableTimerW;
  v77[0] = 0;
  v77[1] = 0;
  v31 = operator new(0x18u);
  *v31 = v31;
  v31[1] = v31;
  v77[0] = v31;
  v85 = 0;
  while ( 2 )
  {
    v32 = &v92;
    if ( v94 > 7 )
      v32 = (__int128 *)v92;
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
      L"client=%u(0x%p) driverId=%ws; Waiting for EnableEvents().",
      ProcessInformation.dwProcessId,
      *v4,
      v32);
    LODWORD(Environment) = WaitForMultipleObjects(3u, Handles, 0, 0xFFFFFFFF);
    if ( !(_DWORD)Environment )
    {
      v52 = &v92;
      if ( v94 > 7 )
        v52 = (__int128 *)v92;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
        L"client=%u(0x%p) driverId=%ws; Process exited without invoking EnableEvents().",
        ProcessInformation.dwProcessId,
        v27,
        v52);
      break;
    }
    v33 = (unsigned int)((_DWORD)Environment - 1);
    if ( (unsigned int)v33 > 1 )
    {
      v51 = &v92;
      if ( v94 > 7 )
        v51 = (__int128 *)v92;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
        L"client=%u(0x%p) driverId=%ws; Not found wait aborted.",
        ProcessInformation.dwProcessId,
        0,
        v51);
      break;
    }
    Print::Driver::CPrinterExtensionServer::FindTargetExtensionServers(v33, v29, &GUID_NULL, v77);
    v34 = (_QWORD *)v77[0];
    v35 = *(_QWORD **)v77[0];
    v36 = JobHandle;
    while ( v35 != v34 && v13 )
    {
      v37 = v35[2];
      if ( v27 == v37 )
      {
        v37 = v27;
        v38 = v27;
      }
      else
      {
        if ( v37 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37 + 8LL))(v35[2]);
        if ( v27 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        v27 = v37;
        v85 = v37;
        v38 = v37;
      }
      if ( !v37 )
      {
        v46 = &v92;
        if ( v94 > 7 )
          v46 = (__int128 *)v92;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
          L"client=%u(0x%p) driverId=%ws; Unexpected p is nullptr.",
          ProcessInformation.dwProcessId,
          v27,
          v46);
        goto LABEL_70;
      }
      ProcessHandle = (HANDLE)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 40LL))(v38);
      v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 48LL))(v38);
      v40 = v39;
      Result[0] = 0;
      if ( ProcessInformation.dwProcessId == v39 )
      {
        v41 = &v92;
        if ( v94 > 7 )
          v41 = (__int128 *)v92;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
          L"client=%u(0x%p) driverId=%ws; Matched on processId.",
          v39,
          v27,
          v41);
      }
      else
      {
        if ( !IsProcessInJob(ProcessHandle, v36, Result) )
        {
          v42 = GetLastError();
          v43 = &v92;
          if ( v94 > 7 )
            v43 = (__int128 *)v92;
          bInheritHandles[0] = v42;
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
            "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
            L"IsProcessInJob client=%u(0x%p) driverId=%ws lastError=%u; Not mached due to failure.",
            v40,
            v27,
            v43,
            *(_QWORD *)bInheritHandles);
LABEL_70:
          v4 = v69;
          goto LABEL_71;
        }
        if ( !Result[0] )
        {
          v45 = &v92;
          if ( v94 > 7 )
            v45 = (__int128 *)v92;
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
            "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
            L"client=%u(0x%p) driverId=%ws; Not matched.",
            v40,
            v27,
            v45);
          goto LABEL_70;
        }
        v44 = &v92;
        if ( v94 > 7 )
          v44 = (__int128 *)v92;
        bInheritHandles[0] = ProcessInformation.dwProcessId;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
          L"client=%u(0x%p) driverId=%ws; Matched on job changed from client=%u(0x%p).",
          v40,
          v27,
          v44,
          *(_QWORD *)bInheritHandles,
          0);
      }
      v4 = v69;
      if ( *v69 != v38 )
      {
        if ( v38 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
        if ( *v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)*v4 + 16LL))(*v4);
        *v4 = v38;
      }
      v13 = 0;
LABEL_71:
      v35 = (_QWORD *)*v35;
      v34 = (_QWORD *)v77[0];
    }
    WaitableTimerW = (char *)hObject;
    if ( (_DWORD)Environment == 2 )
    {
      if ( TerminateJobObject(JobHandle, 0x42Bu) )
      {
        v47 = &v92;
        if ( v94 > 7 )
          v47 = (__int128 *)v92;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
          L"client=%u(0x%p) driverId=%ws; Not found after timeout. Process and child processes were terminated.",
          ProcessInformation.dwProcessId,
          0,
          v47);
      }
      else
      {
        v48 = GetLastError();
        v49 = v48;
        if ( v48 > 0 )
          v49 = (unsigned __int16)v48 | 0x80070000;
        v50 = &v92;
        if ( v94 > 7 )
          v50 = (__int128 *)v92;
        bInheritHandles[0] = v49;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
          L"client=%u(0x%p) driverId=%ws; Not found after timeout. Process and child processes couldn't be terminated: 0x%x",
          ProcessInformation.dwProcessId,
          0,
          v50,
          *(_QWORD *)bInheritHandles);
      }
      v13 = 0;
    }
    if ( v13 )
    {
      v29 = v78;
      continue;
    }
    break;
  }
  v53 = *v4;
  if ( *v4 )
  {
    v54 = &v95;
    if ( v97 > 7 )
      v54 = (__int128 *)v95;
    v55 = &v92;
    if ( v94 > 7 )
      v55 = (__int128 *)v92;
    v56 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 48LL))(*v4);
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
      L"client=%u(0x%p) driverId=%ws reasonId=%ws; Matched setting reason.",
      v56,
      v53,
      v55,
      v54);
    (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)*v4 + 56LL))(*v4, v79);
    v57 = *v4;
    v17 = -1;
    v80 = -1;
    (*(void (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v57 + 64LL))(v57, JobHandle);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
      Print::Driver::CPrinterExtensionServer::TraceRegistrationList();
  }
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  std::list<ATL::CAdapt<ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92>>>::~list<ATL::CAdapt<ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92>>>(v77);
  std::wstring::~wstring(&v95);
  std::wstring::~wstring(&v92);
  if ( (unsigned __int64)(WaitableTimerW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(WaitableTimerW);
  if ( (char *)v81 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v81);
  if ( (unsigned __int64)pExceptionObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(pExceptionObject[0]);
  if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v17);
  LeaveCriticalSection(&Print::Driver::CPrinterExtensionServer::s_startLock);
  std::wstring::~wstring(v98);
  if ( v74 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
  if ( v73 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
  SysFreeString(lpCommandLine);
  result = (_DWORD)hToken - 1;
  if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return CloseHandle(hToken);
  return result;
}

```

## disassembly

```asm
0x18007d6d0  mov     rax, rsp
0x18007d6d3  push    rbp
0x18007d6d4  push    rsi
0x18007d6d5  push    rdi
0x18007d6d6  push    r12
0x18007d6d8  push    r13
0x18007d6da  push    r14
0x18007d6dc  push    r15
0x18007d6de  lea     rbp, [rax-228h]
0x18007d6e5  sub     rsp, 2F0h
0x18007d6ec  mov     [rbp+220h+var_188], 0FFFFFFFFFFFFFFFEh
0x18007d6f7  mov     [rax+8], rbx
0x18007d6fb  mov     rax, cs:__security_cookie
0x18007d702  xor     rax, rsp
0x18007d705  mov     [rbp+220h+var_38], rax
0x18007d70c  mov     r13, r9
0x18007d70f  mov     [rsp+320h+var_2A8], r9
0x18007d714  mov     r14, r8
0x18007d717  mov     [rbp+220h+var_228], r8
0x18007d71b  mov     rsi, rdx
0x18007d71e  mov     [rbp+220h+var_230], rdx
0x18007d722  xor     r12d, r12d
0x18007d725  mov     [rbp+220h+hToken], r12
0x18007d729  lea     rdx, [rbp+220h+hToken]; struct Win32HandleRAII *
0x18007d72d  call    ?CreateRestrictedToken@CPrinterExtensionServer@Driver@Print@@AEAAXAEAVWin32HandleRAII@@@Z; Print::Driver::CPrinterExtensionServer::CreateRestrictedToken(Win32HandleRAII &)
0x18007d732  xorps   xmm0, xmm0
0x18007d735  movups  [rbp+220h+var_B0], xmm0
0x18007d73c  mov     [rbp+220h+lpCommandLine], r12
0x18007d740  mov     [rbp+220h+var_278], r12
0x18007d744  mov     [rbp+220h+var_270], r12
0x18007d748  mov     [rsp+320h+JobHandle], r12
0x18007d74d  lea     rcx, [rsp+320h+JobHandle]
0x18007d752  call    ?CreateInstance@?$CComObject@VCPrinterExtensionManager@PrintConfig@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<PrintConfig::CPrinterExtensionManager>::CreateInstance(ATL::CComObject<PrintConfig::CPrinterExtensionManager> * *)
0x18007d757  mov     edi, eax
0x18007d759  test    eax, eax
0x18007d75b  js      loc_18007E1B0
0x18007d761  mov     rbx, [rsp+320h+JobHandle]
0x18007d766  mov     rax, [rbx]
0x18007d769  mov     rcx, rbx
0x18007d76c  mov     rax, [rax+8]
0x18007d770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d775  mov     rax, [rbx]
0x18007d778  lea     r8, [rbp+220h+var_278]
0x18007d77c  lea     rdx, _GUID_93c6eb8c_b001_4355_9629_8e8a1b3f8e77
0x18007d783  mov     rcx, rbx
0x18007d786  mov     rax, [rax]
0x18007d789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d78e  mov     edi, eax
0x18007d790  mov     rax, [rbx]
0x18007d793  mov     rcx, rbx
0x18007d796  mov     rax, [rax+10h]
0x18007d79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d79f  test    edi, edi
0x18007d7a1  js      loc_18007E1B4
0x18007d7a7  mov     rcx, [rbp+220h+var_278]
0x18007d7ab  mov     rax, [rcx]
0x18007d7ae  lea     r8, [rbp+220h+var_270]
0x18007d7b2  lea     rdx, _GUID_4f27786b_13a2_4df5_857c_3eea48d4839b
0x18007d7b9  mov     rax, [rax]
0x18007d7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7c1  mov     ebx, eax
0x18007d7c3  test    eax, eax
0x18007d7c5  js      loc_18007E206
0x18007d7cb  mov     rcx, [rbp+220h+var_270]
0x18007d7cf  movaps  xmm0, xmmword ptr [r14]
0x18007d7d3  movdqa  [rbp+220h+var_210], xmm0
0x18007d7d8  movups  xmm1, xmmword ptr [rsi]
0x18007d7db  movdqu  xmmword ptr [rbp+220h+pExceptionObject], xmm1
0x18007d7e0  mov     rax, [rcx]
0x18007d7e3  lea     rdx, [rbp+220h+lpCommandLine]
0x18007d7e7  mov     [rsp+320h+lpThreadAttributes], rdx
0x18007d7ec  lea     r9, [rbp+220h+var_B0]
0x18007d7f3  lea     r8, [rbp+220h+var_210]
0x18007d7f7  lea     rdx, [rbp+220h+pExceptionObject]
0x18007d7fb  mov     rax, [rax+18h]
0x18007d7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d804  mov     ebx, eax
0x18007d806  test    eax, eax
0x18007d808  js      loc_18007E258
0x18007d80e  xorps   xmm0, xmm0
0x18007d811  movups  xmmword ptr [rbp+220h+var_D0], xmm0
0x18007d818  mov     [rbp+220h+var_C0], r12
0x18007d81f  mov     [rbp+220h+var_B8], 7
0x18007d82a  mov     word ptr [rbp+220h+var_D0], r12w
0x18007d832  lea     rdx, [rbp+220h+var_D0]
0x18007d839  lea     rcx, [rbp+220h+lpCommandLine]
0x18007d83d  call    ?GetFolderFromFullPath@FileSystem@Win32Adapters@@YAXAEBVCComBSTR@ATL@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::FileSystem::GetFolderFromFullPath(ATL::CComBSTR const &,std::wstring &)
0x18007d842  lea     ebx, [r12+68h]
0x18007d847  mov     r8d, ebx; Size
0x18007d84a  xor     edx, edx; Val
0x18007d84c  lea     rcx, [rbp+220h+StartupInfo]; void *
0x18007d853  call    memset_0
0x18007d858  mov     [rbp+220h+StartupInfo.cb], ebx
0x18007d85e  lea     rax, aWinsta0Default; "winsta0\\default"
0x18007d865  mov     [rbp+220h+StartupInfo.lpDesktop], rax
0x18007d86c  mov     [rbp+220h+StartupInfo.dwFlags], 41h ; 'A'
0x18007d876  lea     r15d, [r12+1]
0x18007d87b  mov     [rbp+220h+StartupInfo.wShowWindow], r15w
0x18007d883  mov     rdi, [rbp+220h+hToken]
0x18007d887  lea     rax, ?s_startLock@CPrinterExtensionServer@Driver@Print@@0VCriticalSectionRAII@@A; CriticalSectionRAII Print::Driver::CPrinterExtensionServer::s_startLock
0x18007d88e  mov     qword ptr [rbp+220h+var_210], rax
0x18007d892  mov     rcx, rax; lpCriticalSection
0x18007d895  call    cs:__imp_EnterCriticalSection
0x18007d89b  nop
0x18007d89c  mov     [rbp+220h+var_220], r12
0x18007d8a0  mov     [rbp+220h+var_1F0], r12
0x18007d8a4  mov     [rbp+220h+var_1E8], r12
0x18007d8a8  xorps   xmm0, xmm0
0x18007d8ab  xor     eax, eax
0x18007d8ad  movups  xmmword ptr [rbp+220h+ProcessInformation.hProcess], xmm0
0x18007d8b1  mov     qword ptr [rbp+220h+ProcessInformation.dwProcessId], rax
0x18007d8b5  call    cs:__imp_CoRevertToSelf
0x18007d8bb  test    eax, eax
0x18007d8bd  js      loc_18007E2AA
0x18007d8c3  mov     byte ptr [rsp+320h+var_2C0], r15b
0x18007d8c8  xor     edx, edx; lpName
0x18007d8ca  xor     ecx, ecx; lpJobAttributes
0x18007d8cc  call    cs:__imp_CreateJobObjectW
0x18007d8d2  mov     rsi, rax
0x18007d8d5  mov     [rsp+320h+JobHandle], rax
0x18007d8da  mov     r14, rax
0x18007d8dd  mov     [rbp+220h+var_220], rax
0x18007d8e1  test    rax, rax
0x18007d8e4  jz      loc_18007E2C6
0x18007d8ea  mov     [rbp+220h+Environment], r12
0x18007d8ee  xor     r8d, r8d; bInherit
0x18007d8f1  mov     rdx, rdi; hToken
0x18007d8f4  lea     rcx, [rbp+220h+Environment]; lpEnvironment
0x18007d8f8  call    cs:__imp_CreateEnvironmentBlock
0x18007d8fe  test    eax, eax
0x18007d900  jz      loc_18007E328
0x18007d906  mov     rbx, [rbp+220h+Environment]
0x18007d90a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_14c74629e3f443f77d94d33812d945c0_@@XPEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_14c74629e3f443f77d94d33812d945c0_,void,void *>::`vftable'
0x18007d911  mov     [rbp+220h+var_1C8], rax
0x18007d915  lea     rax, [rbp+220h+var_1C8]
0x18007d919  mov     [rbp+220h+var_190], rax
0x18007d920  lea     rax, [rbp+220h+var_1C8]
0x18007d924  mov     [rbp+220h+pExceptionObject], rax
0x18007d928  lea     rax, [rbp+220h+var_A0]
0x18007d92f  mov     [rbp+220h+var_218], rax
0x18007d933  mov     [rbp+220h+var_68], r12
0x18007d93a  lea     rdx, [rbp+220h+var_A0]
0x18007d941  lea     rcx, [rbp+220h+var_1C8]
0x18007d945  call    std___Func_impl_no_alloc__lambda_14c74629e3f443f77d94d33812d945c0__void_void______Move
0x18007d94a  mov     [rbp+220h+var_68], rax
0x18007d951  mov     [rbp+220h+var_60], rbx
0x18007d958  mov     rcx, [rbp+220h+var_190]
0x18007d95f  test    rcx, rcx
0x18007d962  jz      short loc_18007D988
0x18007d964  mov     rax, [rcx]
0x18007d967  lea     rdx, [rbp+220h+var_1C8]
0x18007d96b  cmp     rcx, rdx
0x18007d96e  setnz   dl
0x18007d971  mov     rax, [rax+20h]
0x18007d975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d97a  mov     [rbp+220h+var_190], r12
0x18007d981  mov     rbx, [rbp+220h+var_60]
0x18007d988  lea     rax, [rbp+220h+var_D0]
0x18007d98f  cmp     [rbp+220h+var_B8], 7
0x18007d997  cmova   rax, [rbp+220h+var_D0]
0x18007d99f  lea     rcx, [rbp+220h+ProcessInformation]
0x18007d9a3  mov     [rsp+50h], rcx; lpProcessInformation
0x18007d9a8  lea     rcx, [rbp+220h+StartupInfo]
0x18007d9af  mov     [rsp+320h+lpStartupInfo], rcx; lpStartupInfo
0x18007d9b4  mov     [rsp+320h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18007d9b9  mov     [rsp+320h+lpEnvironment], rbx; lpEnvironment
0x18007d9be  mov     [rsp+320h+dwCreationFlags], 434h; dwCreationFlags
0x18007d9c6  mov     [rsp+320h+bInheritHandles], r12d; bInheritHandles
0x18007d9cb  mov     [rsp+320h+lpThreadAttributes], r12; lpThreadAttributes
0x18007d9d0  xor     r9d, r9d; lpProcessAttributes
0x18007d9d3  mov     r8, [rbp+220h+lpCommandLine]; lpCommandLine
0x18007d9d7  xor     edx, edx; lpApplicationName
0x18007d9d9  mov     rcx, rdi; hToken
0x18007d9dc  call    cs:__imp_CreateProcessAsUserW
0x18007d9e2  test    eax, eax
0x18007d9e4  jz      loc_18007E38A
0x18007d9ea  lea     rcx, [rbp+220h+var_A0]
0x18007d9f1  call    ??1?$GenericRAII@PEAX@Driver@Print@@QEAA@XZ; Print::Driver::GenericRAII<void *>::~GenericRAII<void *>(void)
0x18007d9f6  mov     r12, [rbp+220h+ProcessInformation.hProcess]
0x18007d9fa  mov     [rbp+220h+pExceptionObject], r12
0x18007d9fe  mov     [rbp+220h+var_1F0], r12
0x18007da02  mov     rbx, [rbp+220h+ProcessInformation.hThread]
0x18007da06  mov     [rbp+220h+var_218], rbx
0x18007da0a  mov     [rbp+220h+var_1E8], rbx
0x18007da0e  mov     rdx, r12; hProcess
0x18007da11  mov     rcx, rsi; hJob
0x18007da14  call    cs:__imp_AssignProcessToJobObject
0x18007da1a  lea     rdi, aPrintDriverCpr_4; "Print::Driver::CPrinterExtensionServer:"...
0x18007da21  test    eax, eax
0x18007da23  jnz     short loc_18007DA34
0x18007da25  call    cs:__imp_GetLastError
0x18007da2b  lea     rdx, aAssignprocesst; "AssignProcessToJobObject client=%u(0x%p"...
0x18007da32  jmp     short loc_18007DA4F
0x18007da34  mov     rcx, rbx; hThread
0x18007da37  call    cs:__imp_ResumeThread
0x18007da3d  cmp     eax, 0FFFFFFFFh
0x18007da40  jnz     short loc_18007DAAE
0x18007da42  call    cs:__imp_GetLastError
0x18007da48  lea     rdx, aResumethreadCl; "ResumeThread client=%u(0x%p) error=%u; "...
0x18007da4f  mov     ebx, eax
0x18007da51  mov     dword ptr [rsp+320h+lpThreadAttributes], eax
0x18007da55  mov     r9, [r13+0]
0x18007da59  mov     r8d, [rbp+220h+ProcessInformation.dwProcessId]
0x18007da5d  mov     rcx, rdi; char *
0x18007da60  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18007da65  test    ebx, ebx
0x18007da67  jz      short loc_18007DAAE
0x18007da69  mov     edx, ebx; uExitCode
0x18007da6b  mov     rcx, r12; hProcess
0x18007da6e  call    cs:__imp_TerminateProcess
0x18007da74  test    eax, eax
0x18007da76  jnz     short loc_18007DA99
0x18007da78  call    cs:__imp_GetLastError
0x18007da7e  mov     dword ptr [rsp+320h+lpThreadAttributes], eax; unsigned int
0x18007da82  mov     r9, [r13+0]
0x18007da86  mov     r8d, [rbp+220h+ProcessInformation.dwProcessId]
0x18007da8a  lea     rdx, aTerminateproce; "TerminateProcess client=%u(0x%p) error="...
0x18007da91  mov     rcx, rdi; char *
0x18007da94  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18007da99  test    ebx, ebx
0x18007da9b  jle     short loc_18007DAA8
0x18007da9d  movzx   ebx, bx
0x18007daa0  or      ebx, 80070000h
0x18007daa6  test    ebx, ebx
0x18007daa8  js      loc_18007E163
0x18007daae  call    cs:__imp_CoImpersonateClient
0x18007dab4  xor     ebx, ebx
0x18007dab6  test    eax, eax
0x18007dab8  jns     short loc_18007DABC
0x18007daba  int     2Ch; Windows NT - assertion failure
0x18007dabc  xor     r8d, r8d; lpTimerName
0x18007dabf  mov     edx, r15d; bManualReset
0x18007dac2  xor     ecx, ecx; lpTimerAttributes
0x18007dac4  call    cs:__imp_CreateWaitableTimerW
0x18007daca  mov     rsi, rax
0x18007dacd  mov     [rbp+220h+hObject], rax
0x18007dad1  xorps   xmm0, xmm0
0x18007dad4  movups  [rbp+220h+var_110], xmm0
0x18007dadb  mov     [rbp+220h+var_100], rbx
0x18007dae2  mov     [rbp+220h+var_F8], 7
0x18007daed  mov     word ptr [rbp+220h+var_110], bx
0x18007daf4  lea     rdx, [rbp+220h+var_110]
0x18007dafb  mov     rdi, [rbp+220h+var_230]
0x18007daff  mov     rcx, rdi
0x18007db02  call    ?StringFromGuid@Guid@Win32Adapters@@YAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::Guid::StringFromGuid(_GUID const &,std::wstring &)
0x18007db07  xorps   xmm0, xmm0
0x18007db0a  movups  [rbp+220h+var_F0], xmm0
0x18007db11  mov     [rbp+220h+var_E0], rbx
0x18007db18  mov     [rbp+220h+var_D8], 7
0x18007db23  mov     word ptr [rbp+220h+var_F0], bx
0x18007db2a  lea     rdx, [rbp+220h+var_F0]
0x18007db31  mov     rcx, [rbp+220h+var_228]
0x18007db35  call    ?StringFromGuid@Guid@Win32Adapters@@YAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::Guid::StringFromGuid(_GUID const &,std::wstring &)
0x18007db3a  call    cs:__imp_IsDebuggerPresent
0x18007db40  test    eax, eax
0x18007db42  jnz     short loc_18007DB91
0x18007db44  xor     r9d, r9d; unsigned int
0x18007db47  mov     edx, 1388h; void *
0x18007db4c  mov     r8d, 3E8h; unsigned int
0x18007db52  mov     rcx, rsi; this
0x18007db55  call    ?SetWaitableTimerEx@Synchronization@Win32Adapters@@YAXQEAXKKK@Z; Win32Adapters::Synchronization::SetWaitableTimerEx(void * const,ulong,ulong,ulong)
0x18007db5a  lea     rax, [rbp+220h+var_110]
0x18007db61  cmp     [rbp+220h+var_F8], 7
0x18007db69  cmova   rax, qword ptr [rbp+220h+var_110]
0x18007db71  mov     [rsp+320h+lpThreadAttributes], rax
0x18007db76  mov     r9, [r13+0]
0x18007db7a  mov     r8d, [rbp+220h+ProcessInformation.dwProcessId]
0x18007db7e  lea     rdx, aClientU0xPDriv_1; "client=%u(0x%p) driverId=%ws; Timer set"...
0x18007db85  lea     rcx, aPrintDriverCpr_4; "Print::Driver::CPrinterExtensionServer:"...
0x18007db8c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007db91  mov     [rbp+220h+Handles], r12
0x18007db98  mov     rax, cs:?s_activeClientAdded@CPrinterExtensionServer@Driver@Print@@0VWin32HandleRAII@@A; Win32HandleRAII Print::Driver::CPrinterExtensionServer::s_activeClientAdded
0x18007db9f  mov     [rbp+220h+var_48], rax
0x18007dba6  mov     [rbp+220h+var_40], rsi
0x18007dbad  mov     [rbp+220h+var_240], rbx
0x18007dbb1  mov     [rbp+220h+var_238], rbx
0x18007dbb5  mov     ecx, 18h; Size
0x18007dbba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007dbbf  mov     [rax], rax
0x18007dbc2  mov     [rax+8], rax
0x18007dbc6  mov     [rbp+220h+var_240], rax
0x18007dbca  mov     [rbp+220h+var_1E0], rbx
0x18007dbce  lea     rax, [rbp+220h+var_110]
0x18007dbd5  cmp     [rbp+220h+var_F8], 7
0x18007dbdd  cmova   rax, qword ptr [rbp+220h+var_110]
0x18007dbe5  mov     [rsp+320h+lpThreadAttributes], rax
0x18007dbea  mov     r9, [r13+0]
0x18007dbee  mov     r8d, [rbp+220h+ProcessInformation.dwProcessId]
0x18007dbf2  lea     rdx, aClientU0xPDriv_3; "client=%u(0x%p) driverId=%ws; Waiting f"...
0x18007dbf9  lea     rcx, aPrintDriverCpr_4; "Print::Driver::CPrinterExtensionServer:"...
0x18007dc00  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007dc05  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18007dc09  xor     r8d, r8d; bWaitAll
0x18007dc0c  lea     rdx, [rbp+220h+Handles]; lpHandles
0x18007dc13  lea     ecx, [r8+3]; nCount
0x18007dc17  call    cs:__imp_WaitForMultipleObjects
0x18007dc1d  mov     dword ptr [rbp+220h+Environment], eax
0x18007dc20  mov     ecx, eax
0x18007dc22  test    eax, eax
0x18007dc24  jz      loc_18007DF5D
  ... truncated ...
```
