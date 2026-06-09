# Print::Driver::CPrinterExtensionServer::StartExtensionApp(_GUID const &,_GUID const &,ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92> &)

- ea: `0x18008045c`
- end: `0x180081227`
- name: `?StartExtensionApp@CPrinterExtensionServer@Driver@Print@@AEAAXAEBU_GUID@@0AEAV?$CComQIPtr@UIPrinterExtensionServerPrivate@Driver@Print@@$1?_GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92@@3U__s_GUID@@B@ATL@@@Z`
- size: `3531`
- prototype: `int __fastcall(Print::Driver::CPrinterExtensionServer *, const GUID *, const GUID *, __int64 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007f9a4`

## callees

- `0x180003400`
- `0x180003c20`
- `0x180004558`
- `0x180004564`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x1800197b4`
- `0x180036b80`
- `0x1800388f4`
- `0x180038a44`
- `0x18007df00`
- `0x18007df7c`
- `0x18007e580`
- `0x18007ee20`
- `0x18008045c`
- `0x180081230`
- `0x180081520`
- `0x18008862c`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180080914`
- `KERNEL32!IsDebuggerPresent` at `0x180080914`
- `KERNEL32!CloseHandle` at `0x180080e88`
- `KERNEL32!CloseHandle` at `0x180080ea3`
- `KERNEL32!CloseHandle` at `0x180080ec2`
- `KERNEL32!CloseHandle` at `0x180080edc`
- `KERNEL32!CloseHandle` at `0x180080f55`
- `KERNEL32!CloseHandle` at `0x180080e88`
- `KERNEL32!CloseHandle` at `0x180080ea3`
- `KERNEL32!CloseHandle` at `0x180080ec2`
- `KERNEL32!CloseHandle` at `0x180080edc`
- `KERNEL32!CloseHandle` at `0x180080f55`
- `KERNEL32!LeaveCriticalSection` at `0x180080ef0`
- `KERNEL32!LeaveCriticalSection` at `0x180080ef0`
- `KERNEL32!EnterCriticalSection` at `0x180080621`
- `KERNEL32!EnterCriticalSection` at `0x180080621`
- `KERNEL32!GetLastError` at `0x1800807d5`
- `KERNEL32!GetLastError` at `0x1800807fe`
- `KERNEL32!GetLastError` at `0x180080840`
- `KERNEL32!GetLastError` at `0x180080b26`
- `KERNEL32!GetLastError` at `0x180080cd2`
- `KERNEL32!GetLastError` at `0x1800810ef`
- `KERNEL32!GetLastError` at `0x180081157`
- `KERNEL32!GetLastError` at `0x1800811bf`
- `KERNEL32!GetLastError` at `0x1800807d5`
- `KERNEL32!GetLastError` at `0x1800807fe`
- `KERNEL32!GetLastError` at `0x180080840`
- `KERNEL32!GetLastError` at `0x180080b26`
- `KERNEL32!GetLastError` at `0x180080cd2`
- `KERNEL32!GetLastError` at `0x1800810ef`
- `KERNEL32!GetLastError` at `0x180081157`
- `KERNEL32!GetLastError` at `0x1800811bf`
- `KERNEL32!TerminateJobObject` at `0x180080c8a`
- `KERNEL32!TerminateJobObject` at `0x180080c8a`
- `KERNEL32!CreateWaitableTimerW` at `0x180080898`
- `KERNEL32!CreateWaitableTimerW` at `0x180080898`
- `KERNEL32!WaitForMultipleObjects` at `0x1800809f7`
- `KERNEL32!WaitForMultipleObjects` at `0x1800809f7`
- `KERNEL32!CreateJobObjectW` at `0x180080664`
- `KERNEL32!CreateJobObjectW` at `0x180080664`
- `KERNEL32!AssignProcessToJobObject` at `0x1800807be`
- `KERNEL32!AssignProcessToJobObject` at `0x1800807be`
- `KERNEL32!ResumeThread` at `0x1800807ed`
- `KERNEL32!ResumeThread` at `0x1800807ed`
- `KERNEL32!TerminateProcess` at `0x180080830`
- `KERNEL32!TerminateProcess` at `0x180080830`
- `KERNEL32!IsProcessInJob` at `0x180080b16`
- `KERNEL32!IsProcessInJob` at `0x180080b16`
- `OLEAUT32!__imp_SysFreeString` at `0x180080f3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180080f3a`
- `ADVAPI32!CreateProcessAsUserW` at `0x180080780`
- `ADVAPI32!CreateProcessAsUserW` at `0x180080780`
- `ole32!CoRevertToSelf` at `0x180080647`
- `ole32!CoRevertToSelf` at `0x180080647`
- `ole32!CoImpersonateClient` at `0x18008087c`
- `ole32!CoImpersonateClient` at `0x18008087c`
- `USERENV!CreateEnvironmentBlock` at `0x180080696`
- `USERENV!CreateEnvironmentBlock` at `0x180080696`

## string_xrefs

- `0x1800807ca`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x180080965`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x1800809d9`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x180080af9`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x180080b5f`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x180080bb0`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x180080c1d`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x180080c55`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x180080cc4`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x180080d1b`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x180080d85`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x180080df2`: `Print::Driver::CPrinterExtensionServer::StartExtensionApp`
- `0x18008080a`: `ResumeThread client=%u(0x%p) error=%u; Process will be terminated.`
- `0x180080af2`: `client=%u(0x%p) driverId=%ws; Matched on processId.`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
int __fastcall Print::Driver::CPrinterExtensionServer::StartExtensionApp(
        Print::Driver::CPrinterExtensionServer *a1,
        const GUID *a2,
        const GUID *a3,
        __int64 *a4)
{
  __int64 *v4; // r13
  int Instance; // edi
  HANDLE v8; // rbx
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  __int64 v12; // r8
  int v13; // ebx
  char v14; // r15
  HANDLE v15; // rdi
  HRESULT v16; // eax
  HANDLE JobObjectW; // rsi
  __int64 v18; // r14
  void *lpEnvironment; // rbx
  _QWORD *v20; // rdx
  const WCHAR *lpCurrentDirectory; // rax
  __int64 v22; // rdx
  HANDLE hProcess; // r12
  HANDLE hThread; // rbx
  DWORD v25; // eax
  unsigned __int16 *v26; // rdx
  signed int v27; // ebx
  bool v28; // sf
  __int64 v29; // rbx
  char *WaitableTimerW; // rsi
  const GUID *v31; // rdi
  __int128 *v32; // rax
  _QWORD *v33; // rax
  __int128 *v34; // rax
  Print::Driver::CPrinterExtensionServer *v35; // rcx
  _QWORD *v36; // rax
  _QWORD *v37; // rdi
  HANDLE v38; // rsi
  __int64 v39; // r13
  __int64 v40; // r12
  unsigned int v41; // eax
  unsigned int v42; // r13d
  __int128 *v43; // rcx
  DWORD v44; // eax
  __int128 *v45; // rcx
  __int128 *v46; // rcx
  __int128 *v47; // rax
  __int128 *v48; // rax
  __int128 *v49; // rax
  signed int v50; // eax
  unsigned int v51; // ecx
  __int128 *v52; // rax
  __int128 *v53; // rax
  __int128 *v54; // rax
  __int64 v55; // rdi
  __int128 *v56; // r15
  __int128 *v57; // r14
  unsigned int v58; // eax
  __int64 v59; // rcx
  int result; // eax
  signed int LastError; // eax
  unsigned int v62; // ebx
  signed int v63; // eax
  unsigned int v64; // ebx
  signed int v65; // eax
  unsigned int v66; // ebx
  LPSECURITY_ATTRIBUTES lpThreadAttributes; // [rsp+28h] [rbp-E0h]
  LPSECURITY_ATTRIBUTES lpThreadAttributesa; // [rsp+28h] [rbp-E0h]
  BOOL bInheritHandles[2]; // [rsp+30h] [rbp-D8h]
  HANDLE JobHandle; // [rsp+70h] [rbp-98h] BYREF
  BOOL Result[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 *v72; // [rsp+80h] [rbp-88h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+88h] [rbp-80h] BYREF
  LPVOID Environment; // [rsp+A0h] [rbp-68h] BYREF
  LPWSTR lpCommandLine; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v76; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v77; // [rsp+B8h] [rbp-50h] BYREF
  HANDLE hToken; // [rsp+C0h] [rbp-48h] BYREF
  HANDLE pExceptionObject[4]; // [rsp+C8h] [rbp-40h] BYREF
  void *v80[2]; // [rsp+E8h] [rbp-20h] BYREF
  const GUID *v81; // [rsp+F8h] [rbp-10h]
  const GUID *v82; // [rsp+100h] [rbp-8h]
  __int64 v83; // [rsp+108h] [rbp+0h]
  HANDLE v84; // [rsp+110h] [rbp+8h]
  _OWORD v85[2]; // [rsp+118h] [rbp+10h] BYREF
  HANDLE v86; // [rsp+138h] [rbp+30h]
  HANDLE v87; // [rsp+140h] [rbp+38h]
  __int64 v88; // [rsp+148h] [rbp+40h]
  HANDLE ProcessHandle; // [rsp+150h] [rbp+48h]
  HANDLE hObject; // [rsp+158h] [rbp+50h]
  _QWORD v91[7]; // [rsp+160h] [rbp+58h] BYREF
  _QWORD *v92; // [rsp+198h] [rbp+90h]
  __int64 v93; // [rsp+1A0h] [rbp+98h]
  struct _STARTUPINFOW StartupInfo; // [rsp+1A8h] [rbp+A0h] BYREF
  __int128 v95; // [rsp+218h] [rbp+110h] BYREF
  __int64 v96; // [rsp+228h] [rbp+120h]
  unsigned __int64 v97; // [rsp+230h] [rbp+128h]
  __int128 v98; // [rsp+238h] [rbp+130h] BYREF
  __int64 v99; // [rsp+248h] [rbp+140h]
  unsigned __int64 v100; // [rsp+250h] [rbp+148h]
  LPCWSTR v101[2]; // [rsp+258h] [rbp+150h] BYREF
  __int64 v102; // [rsp+268h] [rbp+160h]
  unsigned __int64 v103; // [rsp+270h] [rbp+168h]
  __int128 v104; // [rsp+278h] [rbp+170h] BYREF
  _QWORD v105[7]; // [rsp+288h] [rbp+180h] BYREF
  _QWORD *v106; // [rsp+2C0h] [rbp+1B8h]
  void *v107; // [rsp+2C8h] [rbp+1C0h]
  HANDLE Handles[3]; // [rsp+2D8h] [rbp+1D0h] BYREF

  v93 = -2;
  v4 = a4;
  v72 = a4;
  v82 = a3;
  v81 = a2;
  hToken = 0;
  Print::Driver::CPrinterExtensionServer::CreateRestrictedToken(a1, &hToken);
  v104 = 0;
  lpCommandLine = 0;
  v76 = 0;
  v77 = 0;
  JobHandle = 0;
  Instance = ATL::CComObject<PrintConfig::CPrinterExtensionManager>::CreateInstance((__int64 *)&JobHandle);
  if ( Instance < 0 )
  {
    v76 = 0;
    goto LABEL_120;
  }
  v8 = JobHandle;
  (*(void (__fastcall **)(HANDLE))(*(_QWORD *)JobHandle + 8LL))(JobHandle);
  Instance = (**(__int64 (__fastcall ***)(HANDLE, GUID *, __int64 *))v8)(
               v8,
               &GUID_93c6eb8c_b001_4355_9629_8e8a1b3f8e77,
               &v76);
  (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v8 + 16LL))(v8);
  if ( Instance < 0 )
  {
LABEL_120:
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x1Cu,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        Instance);
    }
    hr_error::hr_error((hr_error *)v85, Instance);
    throw (hr_error *)v85;
  }
  v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v76)(
         v76,
         &GUID_4f27786b_13a2_4df5_857c_3eea48d4839b,
         &v77);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x1Du,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v9);
    }
    hr_error::hr_error((hr_error *)v85, v10);
    throw (hr_error *)v85;
  }
  v85[0] = *a3;
  *(GUID *)pExceptionObject = *a2;
  v11 = (*(__int64 (__fastcall **)(__int64, HANDLE *, _OWORD *, __int128 *, LPWSTR *))(*(_QWORD *)v77 + 24LL))(
          v77,
          pExceptionObject,
          v85,
          &v104,
          &lpCommandLine);
  v13 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x1Eu,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v11);
    }
    hr_error::hr_error((hr_error *)v85, v13);
    throw (hr_error *)v85;
  }
  *(_OWORD *)v101 = 0;
  v102 = 0;
  v103 = 7;
  LOWORD(v101[0]) = 0;
  Win32Adapters::FileSystem::GetFolderFromFullPath((const void **)&lpCommandLine, (__int64)v101, v12);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = L"winsta0\\default";
  StartupInfo.dwFlags = 65;
  v14 = 1;
  StartupInfo.wShowWindow = 1;
  v15 = hToken;
  *(_QWORD *)&v85[0] = &Print::Driver::CPrinterExtensionServer::s_startLock;
  EnterCriticalSection(&Print::Driver::CPrinterExtensionServer::s_startLock);
  v83 = 0;
  v86 = 0;
  v87 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v16 = CoRevertToSelf();
  if ( v16 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v16);
    throw (hr_error *)pExceptionObject;
  }
  JobObjectW = CreateJobObjectW(0, 0);
  JobHandle = JobObjectW;
  v18 = (__int64)JobObjectW;
  v83 = (__int64)JobObjectW;
  if ( !JobObjectW )
  {
    LastError = GetLastError();
    v62 = LastError;
    if ( LastError > 0 )
      v62 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x1Fu,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v62);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v62);
    throw (hr_error *)pExceptionObject;
  }
  Environment = 0;
  if ( !CreateEnvironmentBlock(&Environment, v15, 0) )
  {
    v63 = GetLastError();
    v64 = v63;
    if ( v63 > 0 )
      v64 = (unsigned __int16)v63 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x20u,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v64);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v64);
    throw (hr_error *)pExceptionObject;
  }
  lpEnvironment = Environment;
  v91[0] = &std::_Func_impl_no_alloc<_lambda_14c74629e3f443f77d94d33812d945c0_,void,void *>::`vftable';
  v92 = v91;
  pExceptionObject[0] = v91;
  v84 = v105;
  v106 = 0;
  v106 = std::_Func_impl_no_alloc__lambda_14c74629e3f443f77d94d33812d945c0__void_void___::_Move((__int64)v91, v105);
  v107 = lpEnvironment;
  if ( v92 )
  {
    v20 = v91;
    LOBYTE(v20) = v92 != v91;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v92 + 32LL))(v92, v20);
    v92 = 0;
    lpEnvironment = v107;
  }
  lpCurrentDirectory = (const WCHAR *)v101;
  if ( v103 > 7 )
    lpCurrentDirectory = v101[0];
  if ( !CreateProcessAsUserW(
          v15,
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
    v65 = GetLastError();
    v66 = v65;
    if ( v65 > 0 )
      v66 = (unsigned __int16)v65 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x21u,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v66);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v66);
    throw (hr_error *)pExceptionObject;
  }
  Print::Driver::GenericRAII<void *>::~GenericRAII<void *>((__int64)v105, v22);
  hProcess = ProcessInformation.hProcess;
  pExceptionObject[0] = ProcessInformation.hProcess;
  v86 = ProcessInformation.hProcess;
  hThread = ProcessInformation.hThread;
  v84 = ProcessInformation.hThread;
  v87 = ProcessInformation.hThread;
  if ( AssignProcessToJobObject(JobObjectW, ProcessInformation.hProcess) )
  {
    if ( ResumeThread(hThread) != -1 )
      goto LABEL_23;
    v25 = GetLastError();
    v26 = L"ResumeThread client=%u(0x%p) error=%u; Process will be terminated.";
  }
  else
  {
    v25 = GetLastError();
    v26 = L"AssignProcessToJobObject client=%u(0x%p) error=%u; Process will be terminated.";
  }
  v27 = v25;
  LODWORD(lpThreadAttributes) = v25;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
    "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
    v26,
    ProcessInformation.dwProcessId,
    *v4,
    lpThreadAttributes);
  if ( v27 )
  {
    if ( !TerminateProcess(hProcess, v27) )
    {
      LODWORD(lpThreadAttributesa) = GetLastError();
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
        L"TerminateProcess client=%u(0x%p) error=%u; Process could not be terminated and is suspended resource leak.",
        ProcessInformation.dwProcessId,
        *v4,
        lpThreadAttributesa);
    }
    v28 = v27 < 0;
    if ( v27 > 0 )
    {
      v27 = (unsigned __int16)v27 | 0x80070000;
      v28 = v27 < 0;
    }
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x22u,
          (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
          v27);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v27);
      throw (hr_error *)pExceptionObject;
    }
  }
LABEL_23:
  v29 = 0;
  if ( CoImpersonateClient() < 0 )
    __int2c();
  WaitableTimerW = (char *)CreateWaitableTimerW(0, 1, 0);
  hObject = WaitableTimerW;
  v95 = 0;
  v96 = 0;
  v97 = 7;
  LOWORD(v95) = 0;
  v31 = v81;
  Win32Adapters::Guid::StringFromGuid(v81, (__int64)&v95);
  v98 = 0;
  v99 = 0;
  v100 = 7;
  LOWORD(v98) = 0;
  Win32Adapters::Guid::StringFromGuid(v82, (__int64)&v98);
  if ( !IsDebuggerPresent() )
  {
    Win32Adapters::Synchronization::SetWaitableTimerEx(
      (Win32Adapters::Synchronization *)WaitableTimerW,
      (void *const)0x1388,
      1000,
      0);
    v32 = &v95;
    if ( v97 > 7 )
      v32 = (__int128 *)v95;
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
      L"client=%u(0x%p) driverId=%ws; Timer set.",
      ProcessInformation.dwProcessId,
      *v4,
      v32);
  }
  Handles[0] = hProcess;
  Handles[1] = Print::Driver::CPrinterExtensionServer::s_activeClientAdded;
  Handles[2] = WaitableTimerW;
  v80[0] = 0;
  v80[1] = 0;
  v33 = operator new(0x18u);
  *v33 = v33;
  v33[1] = v33;
  v80[0] = v33;
  v88 = 0;
  while ( 2 )
  {
    v34 = &v95;
    if ( v97 > 7 )
      v34 = (__int128 *)v95;
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
      L"client=%u(0x%p) driverId=%ws; Waiting for EnableEvents().",
      ProcessInformation.dwProcessId,
      *v4,
      v34);
    LODWORD(Environment) = WaitForMultipleObjects(3u, Handles, 0, 0xFFFFFFFF);
    if ( !(_DWORD)Environment )
    {
      v54 = &v95;
      if ( v97 > 7 )
        v54 = (__int128 *)v95;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
        L"client=%u(0x%p) driverId=%ws; Process exited without invoking EnableEvents().",
        ProcessInformation.dwProcessId,
        v29,
        v54);
      break;
    }
    v35 = (Print::Driver::CPrinterExtensionServer *)(unsigned int)((_DWORD)Environment - 1);
    if ( (unsigned int)v35 > 1 )
    {
      v53 = &v95;
      if ( v97 > 7 )
        v53 = (__int128 *)v95;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
        L"client=%u(0x%p) driverId=%ws; Not found wait aborted.",
        ProcessInformation.dwProcessId,
        0,
        v53);
      break;
    }
    Print::Driver::CPrinterExtensionServer::FindTargetExtensionServers(
      v35,
      (__int64)v31,
      (__int64)&GUID_NULL,
      (__int64 *)v80);
    v36 = v80[0];
    v37 = *(_QWORD **)v80[0];
    v38 = JobHandle;
    while ( v37 != v36 && v14 )
    {
      v39 = v37[2];
      if ( v29 == v39 )
      {
        v39 = v29;
        v40 = v29;
      }
      else
      {
        if ( v39 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v39 + 8LL))(v37[2]);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        v29 = v39;
        v88 = v39;
        v40 = v39;
      }
      if ( !v39 )
      {
        v48 = &v95;
        if ( v97 > 7 )
          v48 = (__int128 *)v95;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
          L"client=%u(0x%p) driverId=%ws; Unexpected p is nullptr.",
          ProcessInformation.dwProcessId,
          v29,
          v48);
        goto LABEL_70;
      }
      ProcessHandle = (HANDLE)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 40LL))(v40);
      v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 48LL))(v40);
      v42 = v41;
      Result[0] = 0;
      if ( ProcessInformation.dwProcessId == v41 )
      {
        v43 = &v95;
        if ( v97 > 7 )
          v43 = (__int128 *)v95;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
          L"client=%u(0x%p) driverId=%ws; Matched on processId.",
          v41,
          v29,
          v43);
      }
      else
      {
        if ( !IsProcessInJob(ProcessHandle, v38, Result) )
        {
          v44 = GetLastError();
          v45 = &v95;
          if ( v97 > 7 )
            v45 = (__int128 *)v95;
          bInheritHandles[0] = v44;
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
            "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
            L"IsProcessInJob client=%u(0x%p) driverId=%ws lastError=%u; Not mached due to failure.",
            v42,
            v29,
            v45,
            *(_QWORD *)bInheritHandles);
LABEL_70:
          v4 = v72;
          goto LABEL_71;
        }
        if ( !Result[0] )
        {
          v47 = &v95;
          if ( v97 > 7 )
            v47 = (__int128 *)v95;
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
            "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
            L"client=%u(0x%p) driverId=%ws; Not matched.",
            v42,
            v29,
            v47);
          goto LABEL_70;
        }
        v46 = &v95;
        if ( v97 > 7 )
          v46 = (__int128 *)v95;
        bInheritHandles[0] = ProcessInformation.dwProcessId;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
          L"client=%u(0x%p) driverId=%ws; Matched on job changed from client=%u(0x%p).",
          v42,
          v29,
          v46,
          *(_QWORD *)bInheritHandles,
          0);
      }
      v4 = v72;
      if ( *v72 != v40 )
      {
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
        if ( *v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)*v4 + 16LL))(*v4);
        *v4 = v40;
      }
      v14 = 0;
LABEL_71:
      v37 = (_QWORD *)*v37;
      v36 = v80[0];
    }
    WaitableTimerW = (char *)hObject;
    if ( (_DWORD)Environment == 2 )
    {
      if ( TerminateJobObject(JobHandle, 0x42Bu) )
      {
        v49 = &v95;
        if ( v97 > 7 )
          v49 = (__int128 *)v95;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
          L"client=%u(0x%p) driverId=%ws; Not found after timeout. Process and child processes were terminated.",
          ProcessInformation.dwProcessId,
          0,
          v49);
      }
      else
      {
        v50 = GetLastError();
        v51 = v50;
        if ( v50 > 0 )
          v51 = (unsigned __int16)v50 | 0x80070000;
        v52 = &v95;
        if ( v97 > 7 )
          v52 = (__int128 *)v95;
        bInheritHandles[0] = v51;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
          L"client=%u(0x%p) driverId=%ws; Not found after timeout. Process and child processes couldn't be terminated: 0x%x",
          ProcessInformation.dwProcessId,
          0,
          v52,
          *(_QWORD *)bInheritHandles);
      }
      v14 = 0;
    }
    if ( v14 )
    {
      v31 = v81;
      continue;
    }
    break;
  }
  v55 = *v4;
  if ( *v4 )
  {
    v56 = &v98;
    if ( v100 > 7 )
      v56 = (__int128 *)v98;
    v57 = &v95;
    if ( v97 > 7 )
      v57 = (__int128 *)v95;
    v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 48LL))(*v4);
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::CPrinterExtensionServer::StartExtensionApp",
      L"client=%u(0x%p) driverId=%ws reasonId=%ws; Matched setting reason.",
      v58,
      v55,
      v57,
      v56);
    (*(void (__fastcall **)(__int64, const GUID *))(*(_QWORD *)*v4 + 56LL))(*v4, v82);
    v59 = *v4;
    v18 = -1;
    v83 = -1;
    (*(void (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v59 + 64LL))(v59, JobHandle);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
      Print::Driver::CPrinterExtensionServer::TraceRegistrationList();
  }
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  std::list<ATL::CAdapt<ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92>>>::~list<ATL::CAdapt<ATL::CComQIPtr<Print::Driver::IPrinterExtensionServerPrivate,&__s_GUID const _GUID_7dac59f6_5ef3_4b19_adf9_517ce4f22f92>>>(v80);
  std::wstring::~wstring((char **)&v98);
  std::wstring::~wstring((char **)&v95);
  if ( (unsigned __int64)(WaitableTimerW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(WaitableTimerW);
  if ( (char *)v84 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v84);
  if ( (unsigned __int64)pExceptionObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(pExceptionObject[0]);
  if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v18);
  LeaveCriticalSection(&Print::Driver::CPrinterExtensionServer::s_startLock);
  std::wstring::~wstring((char **)v101);
  if ( v77 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  if ( v76 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
  SysFreeString(lpCommandLine);
  result = (_DWORD)hToken - 1;
  if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return CloseHandle(hToken);
  return result;
}

```

## disassembly

```asm
0x18008045c  mov     rax, rsp
0x18008045f  push    rbp
0x180080460  push    rsi
0x180080461  push    rdi
0x180080462  push    r12
0x180080464  push    r13
0x180080466  push    r14
0x180080468  push    r15
0x18008046a  lea     rbp, [rax-228h]
0x180080471  sub     rsp, 2F0h
0x180080478  mov     [rbp+220h+var_188], 0FFFFFFFFFFFFFFFEh
0x180080483  mov     [rax+8], rbx
0x180080487  mov     rax, cs:__security_cookie
0x18008048e  xor     rax, rsp
0x180080491  mov     [rbp+220h+var_38], rax
0x180080498  mov     r13, r9
0x18008049b  mov     [rsp+320h+var_2A8], r9
0x1800804a0  mov     r14, r8
0x1800804a3  mov     [rbp+220h+var_228], r8
0x1800804a7  mov     rsi, rdx
0x1800804aa  mov     [rbp+220h+var_230], rdx
0x1800804ae  xor     r12d, r12d
0x1800804b1  mov     [rbp+220h+hToken], r12
0x1800804b5  lea     rdx, [rbp+220h+hToken]; struct Win32HandleRAII *
0x1800804b9  call    ?CreateRestrictedToken@CPrinterExtensionServer@Driver@Print@@AEAAXAEAVWin32HandleRAII@@@Z; Print::Driver::CPrinterExtensionServer::CreateRestrictedToken(Win32HandleRAII &)
0x1800804be  xorps   xmm0, xmm0
0x1800804c1  movups  [rbp+220h+var_B0], xmm0
0x1800804c8  mov     [rbp+220h+lpCommandLine], r12
0x1800804cc  mov     [rbp+220h+var_278], r12
0x1800804d0  mov     [rbp+220h+var_270], r12
0x1800804d4  mov     [rsp+320h+JobHandle], r12
0x1800804d9  lea     rcx, [rsp+320h+JobHandle]
0x1800804de  call    ?CreateInstance@?$CComObject@VCPrinterExtensionManager@PrintConfig@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<PrintConfig::CPrinterExtensionManager>::CreateInstance(ATL::CComObject<PrintConfig::CPrinterExtensionManager> * *)
0x1800804e3  mov     edi, eax
0x1800804e5  test    eax, eax
0x1800804e7  js      loc_180080FD9
0x1800804ed  mov     rbx, [rsp+320h+JobHandle]
0x1800804f2  mov     rax, [rbx]
0x1800804f5  mov     rcx, rbx
0x1800804f8  mov     rax, [rax+8]
0x1800804fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080501  mov     rax, [rbx]
0x180080504  lea     r8, [rbp+220h+var_278]
0x180080508  lea     rdx, _GUID_93c6eb8c_b001_4355_9629_8e8a1b3f8e77
0x18008050f  mov     rcx, rbx
0x180080512  mov     rax, [rax]
0x180080515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008051a  mov     edi, eax
0x18008051c  mov     rax, [rbx]
0x18008051f  mov     rcx, rbx
0x180080522  mov     rax, [rax+10h]
0x180080526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008052b  test    edi, edi
0x18008052d  js      loc_180080FDD
0x180080533  mov     rcx, [rbp+220h+var_278]
0x180080537  mov     rax, [rcx]
0x18008053a  lea     r8, [rbp+220h+var_270]
0x18008053e  lea     rdx, _GUID_4f27786b_13a2_4df5_857c_3eea48d4839b
0x180080545  mov     rax, [rax]
0x180080548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008054d  mov     ebx, eax
0x18008054f  test    eax, eax
0x180080551  js      loc_18008102F
0x180080557  mov     rcx, [rbp+220h+var_270]
0x18008055b  movaps  xmm0, xmmword ptr [r14]
0x18008055f  movdqa  [rbp+220h+var_210], xmm0
0x180080564  movups  xmm1, xmmword ptr [rsi]
0x180080567  movdqu  xmmword ptr [rbp+220h+pExceptionObject], xmm1
0x18008056c  mov     rax, [rcx]
0x18008056f  lea     rdx, [rbp+220h+lpCommandLine]
0x180080573  mov     [rsp+320h+lpThreadAttributes], rdx
0x180080578  lea     r9, [rbp+220h+var_B0]
0x18008057f  lea     r8, [rbp+220h+var_210]
0x180080583  lea     rdx, [rbp+220h+pExceptionObject]
0x180080587  mov     rax, [rax+18h]
0x18008058b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080590  mov     ebx, eax
0x180080592  test    eax, eax
0x180080594  js      loc_180081081
0x18008059a  xorps   xmm0, xmm0
0x18008059d  movups  xmmword ptr [rbp+220h+var_D0], xmm0
0x1800805a4  mov     [rbp+220h+var_C0], r12
0x1800805ab  mov     [rbp+220h+var_B8], 7
0x1800805b6  mov     word ptr [rbp+220h+var_D0], r12w
0x1800805be  lea     rdx, [rbp+220h+var_D0]
0x1800805c5  lea     rcx, [rbp+220h+lpCommandLine]
0x1800805c9  call    ?GetFolderFromFullPath@FileSystem@Win32Adapters@@YAXAEBVCComBSTR@ATL@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::FileSystem::GetFolderFromFullPath(ATL::CComBSTR const &,std::wstring &)
0x1800805ce  lea     ebx, [r12+68h]
0x1800805d3  mov     r8d, ebx; Size
0x1800805d6  xor     edx, edx; Val
0x1800805d8  lea     rcx, [rbp+220h+StartupInfo]; void *
0x1800805df  call    memset_0
0x1800805e4  mov     [rbp+220h+StartupInfo.cb], ebx
0x1800805ea  lea     rax, aWinsta0Default; "winsta0\\default"
0x1800805f1  mov     [rbp+220h+StartupInfo.lpDesktop], rax
0x1800805f8  mov     [rbp+220h+StartupInfo.dwFlags], 41h ; 'A'
0x180080602  lea     r15d, [r12+1]
0x180080607  mov     [rbp+220h+StartupInfo.wShowWindow], r15w
0x18008060f  mov     rdi, [rbp+220h+hToken]
0x180080613  lea     rax, ?s_startLock@CPrinterExtensionServer@Driver@Print@@0VCriticalSectionRAII@@A; CriticalSectionRAII Print::Driver::CPrinterExtensionServer::s_startLock
0x18008061a  mov     qword ptr [rbp+220h+var_210], rax
0x18008061e  mov     rcx, rax; lpCriticalSection
0x180080621  call    cs:__imp_EnterCriticalSection
0x180080628  nop     dword ptr [rax+rax+00h]
0x18008062d  nop
0x18008062e  mov     [rbp+220h+var_220], r12
0x180080632  mov     [rbp+220h+var_1F0], r12
0x180080636  mov     [rbp+220h+var_1E8], r12
0x18008063a  xorps   xmm0, xmm0
0x18008063d  xor     eax, eax
0x18008063f  movups  xmmword ptr [rbp+220h+ProcessInformation.hProcess], xmm0
0x180080643  mov     qword ptr [rbp+220h+ProcessInformation.dwProcessId], rax
0x180080647  call    cs:__imp_CoRevertToSelf
0x18008064e  nop     dword ptr [rax+rax+00h]
0x180080653  test    eax, eax
0x180080655  js      loc_1800810D3
0x18008065b  mov     byte ptr [rsp+320h+var_2C0], r15b
0x180080660  xor     edx, edx; lpName
0x180080662  xor     ecx, ecx; lpJobAttributes
0x180080664  call    cs:__imp_CreateJobObjectW
0x18008066b  nop     dword ptr [rax+rax+00h]
0x180080670  mov     rsi, rax
0x180080673  mov     [rsp+320h+JobHandle], rax
0x180080678  mov     r14, rax
0x18008067b  mov     [rbp+220h+var_220], rax
0x18008067f  test    rax, rax
0x180080682  jz      loc_1800810EF
0x180080688  mov     [rbp+220h+Environment], r12
0x18008068c  xor     r8d, r8d; bInherit
0x18008068f  mov     rdx, rdi; hToken
0x180080692  lea     rcx, [rbp+220h+Environment]; lpEnvironment
0x180080696  call    cs:__imp_CreateEnvironmentBlock
0x18008069d  nop     dword ptr [rax+rax+00h]
0x1800806a2  test    eax, eax
0x1800806a4  jz      loc_180081157
0x1800806aa  mov     rbx, [rbp+220h+Environment]
0x1800806ae  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_14c74629e3f443f77d94d33812d945c0_@@XPEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_14c74629e3f443f77d94d33812d945c0_,void,void *>::`vftable'
0x1800806b5  mov     [rbp+220h+var_1C8], rax
0x1800806b9  lea     rax, [rbp+220h+var_1C8]
0x1800806bd  mov     [rbp+220h+var_190], rax
0x1800806c4  lea     rax, [rbp+220h+var_1C8]
0x1800806c8  mov     [rbp+220h+pExceptionObject], rax
0x1800806cc  lea     rax, [rbp+220h+var_A0]
0x1800806d3  mov     [rbp+220h+var_218], rax
0x1800806d7  mov     [rbp+220h+var_68], r12
0x1800806de  lea     rdx, [rbp+220h+var_A0]
0x1800806e5  lea     rcx, [rbp+220h+var_1C8]
0x1800806e9  call    std___Func_impl_no_alloc__lambda_14c74629e3f443f77d94d33812d945c0__void_void______Move
0x1800806ee  mov     [rbp+220h+var_68], rax
0x1800806f5  mov     [rbp+220h+var_60], rbx
0x1800806fc  mov     rcx, [rbp+220h+var_190]
0x180080703  test    rcx, rcx
0x180080706  jz      short loc_18008072C
0x180080708  mov     rax, [rcx]
0x18008070b  lea     rdx, [rbp+220h+var_1C8]
0x18008070f  cmp     rcx, rdx
0x180080712  setnz   dl
0x180080715  mov     rax, [rax+20h]
0x180080719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008071e  mov     [rbp+220h+var_190], r12
0x180080725  mov     rbx, [rbp+220h+var_60]
0x18008072c  lea     rax, [rbp+220h+var_D0]
0x180080733  cmp     [rbp+220h+var_B8], 7
0x18008073b  cmova   rax, [rbp+220h+var_D0]
0x180080743  lea     rcx, [rbp+220h+ProcessInformation]
0x180080747  mov     [rsp+50h], rcx; lpProcessInformation
0x18008074c  lea     rcx, [rbp+220h+StartupInfo]
0x180080753  mov     [rsp+320h+lpStartupInfo], rcx; lpStartupInfo
0x180080758  mov     [rsp+320h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18008075d  mov     [rsp+320h+lpEnvironment], rbx; lpEnvironment
0x180080762  mov     [rsp+320h+dwCreationFlags], 434h; dwCreationFlags
0x18008076a  mov     [rsp+320h+bInheritHandles], r12d; bInheritHandles
0x18008076f  mov     [rsp+320h+lpThreadAttributes], r12; lpThreadAttributes
0x180080774  xor     r9d, r9d; lpProcessAttributes
0x180080777  mov     r8, [rbp+220h+lpCommandLine]; lpCommandLine
0x18008077b  xor     edx, edx; lpApplicationName
0x18008077d  mov     rcx, rdi; hToken
0x180080780  call    cs:__imp_CreateProcessAsUserW
0x180080787  nop     dword ptr [rax+rax+00h]
0x18008078c  test    eax, eax
0x18008078e  jz      loc_1800811BF
0x180080794  lea     rcx, [rbp+220h+var_A0]
0x18008079b  call    ??1?$GenericRAII@PEAX@Driver@Print@@QEAA@XZ; Print::Driver::GenericRAII<void *>::~GenericRAII<void *>(void)
0x1800807a0  mov     r12, [rbp+220h+ProcessInformation.hProcess]
0x1800807a4  mov     [rbp+220h+pExceptionObject], r12
0x1800807a8  mov     [rbp+220h+var_1F0], r12
0x1800807ac  mov     rbx, [rbp+220h+ProcessInformation.hThread]
0x1800807b0  mov     [rbp+220h+var_218], rbx
0x1800807b4  mov     [rbp+220h+var_1E8], rbx
0x1800807b8  mov     rdx, r12; hProcess
0x1800807bb  mov     rcx, rsi; hJob
0x1800807be  call    cs:__imp_AssignProcessToJobObject
0x1800807c5  nop     dword ptr [rax+rax+00h]
0x1800807ca  lea     rdi, aPrintDriverCpr_4; "Print::Driver::CPrinterExtensionServer:"...
0x1800807d1  test    eax, eax
0x1800807d3  jnz     short loc_1800807EA
0x1800807d5  call    cs:__imp_GetLastError
0x1800807dc  nop     dword ptr [rax+rax+00h]
0x1800807e1  lea     rdx, aAssignprocesst; "AssignProcessToJobObject client=%u(0x%p"...
0x1800807e8  jmp     short loc_180080811
0x1800807ea  mov     rcx, rbx; hThread
0x1800807ed  call    cs:__imp_ResumeThread
0x1800807f4  nop     dword ptr [rax+rax+00h]
0x1800807f9  cmp     eax, 0FFFFFFFFh
0x1800807fc  jnz     short loc_18008087C
0x1800807fe  call    cs:__imp_GetLastError
0x180080805  nop     dword ptr [rax+rax+00h]
0x18008080a  lea     rdx, aResumethreadCl; "ResumeThread client=%u(0x%p) error=%u; "...
0x180080811  mov     ebx, eax
0x180080813  mov     dword ptr [rsp+320h+lpThreadAttributes], eax
0x180080817  mov     r9, [r13+0]
0x18008081b  mov     r8d, [rbp+220h+ProcessInformation.dwProcessId]
0x18008081f  mov     rcx, rdi; char *
0x180080822  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180080827  test    ebx, ebx
0x180080829  jz      short loc_18008087C
0x18008082b  mov     edx, ebx; uExitCode
0x18008082d  mov     rcx, r12; hProcess
0x180080830  call    cs:__imp_TerminateProcess
0x180080837  nop     dword ptr [rax+rax+00h]
0x18008083c  test    eax, eax
0x18008083e  jnz     short loc_180080867
0x180080840  call    cs:__imp_GetLastError
0x180080847  nop     dword ptr [rax+rax+00h]
0x18008084c  mov     dword ptr [rsp+320h+lpThreadAttributes], eax; unsigned int
0x180080850  mov     r9, [r13+0]
0x180080854  mov     r8d, [rbp+220h+ProcessInformation.dwProcessId]
0x180080858  lea     rdx, aTerminateproce; "TerminateProcess client=%u(0x%p) error="...
0x18008085f  mov     rcx, rdi; char *
0x180080862  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180080867  test    ebx, ebx
0x180080869  jle     short loc_180080876
0x18008086b  movzx   ebx, bx
0x18008086e  or      ebx, 80070000h
0x180080874  test    ebx, ebx
0x180080876  js      loc_180080F8C
0x18008087c  call    cs:__imp_CoImpersonateClient
0x180080883  nop     dword ptr [rax+rax+00h]
0x180080888  xor     ebx, ebx
0x18008088a  test    eax, eax
0x18008088c  jns     short loc_180080890
0x18008088e  int     2Ch; Windows NT - assertion failure
0x180080890  xor     r8d, r8d; lpTimerName
0x180080893  mov     edx, r15d; bManualReset
0x180080896  xor     ecx, ecx; lpTimerAttributes
0x180080898  call    cs:__imp_CreateWaitableTimerW
0x18008089f  nop     dword ptr [rax+rax+00h]
0x1800808a4  mov     rsi, rax
0x1800808a7  mov     [rbp+220h+hObject], rax
0x1800808ab  xorps   xmm0, xmm0
0x1800808ae  movups  [rbp+220h+var_110], xmm0
0x1800808b5  mov     [rbp+220h+var_100], rbx
0x1800808bc  mov     [rbp+220h+var_F8], 7
0x1800808c7  mov     word ptr [rbp+220h+var_110], bx
0x1800808ce  lea     rdx, [rbp+220h+var_110]
0x1800808d5  mov     rdi, [rbp+220h+var_230]
0x1800808d9  mov     rcx, rdi
0x1800808dc  call    ?StringFromGuid@Guid@Win32Adapters@@YAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::Guid::StringFromGuid(_GUID const &,std::wstring &)
0x1800808e1  xorps   xmm0, xmm0
0x1800808e4  movups  [rbp+220h+var_F0], xmm0
0x1800808eb  mov     [rbp+220h+var_E0], rbx
0x1800808f2  mov     [rbp+220h+var_D8], 7
0x1800808fd  mov     word ptr [rbp+220h+var_F0], bx
0x180080904  lea     rdx, [rbp+220h+var_F0]
0x18008090b  mov     rcx, [rbp+220h+var_228]
0x18008090f  call    ?StringFromGuid@Guid@Win32Adapters@@YAXAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Win32Adapters::Guid::StringFromGuid(_GUID const &,std::wstring &)
0x180080914  call    cs:__imp_IsDebuggerPresent
0x18008091b  nop     dword ptr [rax+rax+00h]
0x180080920  test    eax, eax
0x180080922  jnz     short loc_180080971
0x180080924  xor     r9d, r9d; unsigned int
0x180080927  mov     edx, 1388h; void *
0x18008092c  mov     r8d, 3E8h; unsigned int
0x180080932  mov     rcx, rsi; this
0x180080935  call    ?SetWaitableTimerEx@Synchronization@Win32Adapters@@YAXQEAXKKK@Z; Win32Adapters::Synchronization::SetWaitableTimerEx(void * const,ulong,ulong,ulong)
0x18008093a  lea     rax, [rbp+220h+var_110]
0x180080941  cmp     [rbp+220h+var_F8], 7
0x180080949  cmova   rax, qword ptr [rbp+220h+var_110]
0x180080951  mov     [rsp+320h+lpThreadAttributes], rax
0x180080956  mov     r9, [r13+0]
0x18008095a  mov     r8d, [rbp+220h+ProcessInformation.dwProcessId]
0x18008095e  lea     rdx, aClientU0xPDriv_1; "client=%u(0x%p) driverId=%ws; Timer set"...
0x180080965  lea     rcx, aPrintDriverCpr_4; "Print::Driver::CPrinterExtensionServer:"...
0x18008096c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180080971  mov     [rbp+220h+Handles], r12
0x180080978  mov     rax, cs:?s_activeClientAdded@CPrinterExtensionServer@Driver@Print@@0VWin32HandleRAII@@A; Win32HandleRAII Print::Driver::CPrinterExtensionServer::s_activeClientAdded
0x18008097f  mov     [rbp+220h+var_48], rax
0x180080986  mov     [rbp+220h+var_40], rsi
0x18008098d  mov     [rbp+220h+var_240], rbx
0x180080991  mov     [rbp+220h+var_238], rbx
0x180080995  mov     ecx, 18h; Size
0x18008099a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008099f  mov     [rax], rax
0x1800809a2  mov     [rax+8], rax
0x1800809a6  mov     [rbp+220h+var_240], rax
0x1800809aa  mov     [rbp+220h+var_1E0], rbx
0x1800809ae  lea     rax, [rbp+220h+var_110]
0x1800809b5  cmp     [rbp+220h+var_F8], 7
0x1800809bd  cmova   rax, qword ptr [rbp+220h+var_110]
0x1800809c5  mov     [rsp+320h+lpThreadAttributes], rax
  ... truncated ...
```
