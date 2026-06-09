# CLockHost::_EnsureLockAppHost(LockAppType,ILockAppHost * *)

- ea: `0x180028f70`
- end: `0x180029e02`
- name: `?_EnsureLockAppHost@CLockHost@@AEAAJW4LockAppType@@PEAPEAUILockAppHost@@@Z`
- size: `3730`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005b5a0`
- `0x18006ab90`

## callees

- `0x180004c00`
- `0x18000df10`
- `0x180017dec`
- `0x18001c56c`
- `0x18001c860`
- `0x18001d850`
- `0x18001db70`
- `0x18001f3a0`
- `0x180028f70`
- `0x18002a060`
- `0x18002a228`
- `0x18002a254`
- `0x18002a2e8`
- `0x18002a8e8`
- `0x18002ab80`
- `0x18002ac4c`
- `0x18002fe2c`
- `0x1800440b4`
- `0x18005b3e4`
- `0x18005d488`
- `0x18005d4e8`
- `0x1800665c0`
- `0x1800690d0`
- `0x18006c000`
- `0x1800887ec`
- `0x180088844`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x180029222`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180029821`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180029b1a`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180029222`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180029821`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180029b1a`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800297d6`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800297d6`
- `KERNEL32!RegisterWaitForSingleObject` at `0x1800294b2`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180029998`
- `KERNEL32!RegisterWaitForSingleObject` at `0x1800294b2`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180029998`
- `KERNEL32!DuplicateHandle` at `0x1800296da`
- `KERNEL32!DuplicateHandle` at `0x1800296da`
- `KERNEL32!OpenProcess` at `0x180029656`
- `KERNEL32!OpenProcess` at `0x18002995a`
- `KERNEL32!OpenProcess` at `0x180029656`
- `KERNEL32!OpenProcess` at `0x18002995a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800291a8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029310`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800293ec`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800294e8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029730`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029a30`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029b7e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029c6b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029db3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800291a8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029310`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800293ec`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800294e8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029730`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029a30`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029b7e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029c6b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029db3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800290ff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800290ff`
- `KERNEL32!CloseHandle` at `0x180029697`
- `KERNEL32!CloseHandle` at `0x180029867`
- `KERNEL32!CloseHandle` at `0x18002987b`
- `KERNEL32!CloseHandle` at `0x1800299cf`
- `KERNEL32!CloseHandle` at `0x1800299e3`
- `KERNEL32!CloseHandle` at `0x180029a69`
- `KERNEL32!CloseHandle` at `0x180029a7d`
- `KERNEL32!CloseHandle` at `0x180029cc0`
- `KERNEL32!CloseHandle` at `0x180029cd4`
- `KERNEL32!CloseHandle` at `0x180029697`
- `KERNEL32!CloseHandle` at `0x180029867`
- `KERNEL32!CloseHandle` at `0x18002987b`
- `KERNEL32!CloseHandle` at `0x1800299cf`
- `KERNEL32!CloseHandle` at `0x1800299e3`
- `KERNEL32!CloseHandle` at `0x180029a69`
- `KERNEL32!CloseHandle` at `0x180029a7d`
- `KERNEL32!CloseHandle` at `0x180029cc0`
- `KERNEL32!CloseHandle` at `0x180029cd4`
- `KERNEL32!SetLastError` at `0x18002969f`
- `KERNEL32!SetLastError` at `0x18002969f`
- `KERNEL32!GetLastError` at `0x18002968c`
- `KERNEL32!GetLastError` at `0x18002968c`
- `KERNEL32!GetCurrentThreadId` at `0x180029784`
- `KERNEL32!GetCurrentThreadId` at `0x180029784`
- `KERNEL32!GetCurrentProcess` at `0x1800296ab`
- `KERNEL32!GetCurrentProcess` at `0x1800296b4`
- `KERNEL32!GetCurrentProcess` at `0x1800296ab`
- `KERNEL32!GetCurrentProcess` at `0x1800296b4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029150`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800293b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029559`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029150`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800293b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029559`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800297a1`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x1800297a1`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002920a`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180029809`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180029b02`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002920a`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180029809`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180029b02`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18002929c`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180029bd8`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18002929c`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180029bd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CLockHost::_EnsureLockAppHost(__int64 a1, int a2, struct IUnknown **a3)
{
  struct IUnknown **v3; // r13
  int AgileReference; // r14d
  RTL_SRWLOCK *v8; // r12
  HRESULT Instance; // edi
  HANDLE v10; // rcx
  unsigned int v11; // edx
  Microsoft::WRL::AgileRef *v12; // rdi
  struct IUnknown *v13; // rsi
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rdx
  char v15; // si
  struct IUnknown *v16; // rcx
  HANDLE v17; // rcx
  HRESULT v18; // eax
  unsigned int v19; // esi
  int v20; // eax
  int ServerProcessHandle; // eax
  const char *v22; // r9
  int LastError; // ebx
  Microsoft::WRL::AgileRef *v24; // r15
  LPVOID *v25; // rax
  __int64 v26; // rdx
  HANDLE *v27; // r14
  struct IUnknown *v28; // rsi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  __int64 (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rcx
  char *v31; // r13
  HANDLE CurrentProcess; // rdi
  HANDLE v33; // rax
  const char *v34; // r9
  struct IUnknown *v35; // rcx
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v37)(_QWORD, GUID *, _QWORD); // rsi
  __int64 (__fastcall *v38)(_QWORD, GUID *, _QWORD); // rdi
  __int64 (__fastcall ***v39)(_QWORD, _QWORD, _QWORD); // rcx
  HANDLE v40; // rax
  const char *v41; // r9
  struct IUnknown *v42; // rcx
  __int64 (__fastcall ***v43)(_QWORD, _QWORD, _QWORD); // rcx
  struct IUnknown *v44; // rcx
  unsigned int v45; // edx
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall ***v48)(_QWORD, _QWORD, _QWORD); // rdx
  __int64 (__fastcall ***v49)(_QWORD, _QWORD, _QWORD); // rcx
  struct IUnknown *v50; // rcx
  __int64 (__fastcall ***v51)(_QWORD, _QWORD, _QWORD); // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v56)(_QWORD, _QWORD, _QWORD); // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v57; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v58)(_QWORD, _QWORD, _QWORD); // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwProcessId[4]; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID Buf1; // [rsp+70h] [rbp-90h] BYREF
  void *phNewTimer; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown **v62; // [rsp+90h] [rbp-70h] BYREF
  struct IUnknown **Parameter; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE *p_hObject; // [rsp+A8h] [rbp-58h]
  HANDLE Timer; // [rsp+B0h] [rbp-50h]
  void **v66; // [rsp+C0h] [rbp-40h] BYREF
  int v67; // [rsp+C8h] [rbp-38h] BYREF
  char v68; // [rsp+CCh] [rbp-34h]
  int v69; // [rsp+F0h] [rbp-10h] BYREF
  const char *v70; // [rsp+F8h] [rbp-8h]
  __int64 v71; // [rsp+100h] [rbp+0h]
  char v72; // [rsp+108h] [rbp+8h]
  int v73; // [rsp+110h] [rbp+10h]
  __int128 v74; // [rsp+118h] [rbp+18h]
  __int128 v75; // [rsp+128h] [rbp+28h]
  __int128 v76; // [rsp+138h] [rbp+38h]
  __int128 v77; // [rsp+148h] [rbp+48h]
  __int128 v78; // [rsp+158h] [rbp+58h]
  __int128 v79; // [rsp+168h] [rbp+68h]
  __int128 v80; // [rsp+178h] [rbp+78h]
  __int128 v81; // [rsp+188h] [rbp+88h]
  __int128 v82; // [rsp+198h] [rbp+98h]
  __int64 v83; // [rsp+1A8h] [rbp+A8h]
  __int128 v84; // [rsp+1B0h] [rbp+B0h]
  int v85; // [rsp+1C0h] [rbp+C0h]
  __int64 v86; // [rsp+1C8h] [rbp+C8h]
  int *v87; // [rsp+1D0h] [rbp+D0h]
  __int64 v88; // [rsp+1D8h] [rbp+D8h]
  char v89[48]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v3 = a3;
  v62 = a3;
  v66 = &wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  AgileReference = 0;
  v67 = 0;
  v68 = 0;
  v72 = 0;
  v69 = 0;
  v70 = "CLockHost__EnsureLockAppHost_Activity";
  v71 = 0;
  v73 = 0;
  v84 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v85 = 1;
  v86 = 0;
  v87 = &v67;
  v88 = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v89,
    (struct wil::details::IFailureCallback *)&v66,
    (struct wil::CallContextInfo *)&v69,
    0);
  v66 = &LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::`vftable';
  Buf1 = *GetFirstRunTelemetryCorrelationId(&Buf1);
  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v66,
      &Buf1);
  LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::StartActivity((LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity *)&v66);
  *v3 = 0;
  if ( *(_DWORD *)(a1 + 176) >= 5u )
  {
    LogonControllerTelemetry::DesktopLockHostActivationBackedOff();
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A5,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
      (const char *)0x80004004LL,
      ppv);
    v66 = &LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::`vftable';
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v66);
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v66);
    return 2147500036LL;
  }
  v8 = (RTL_SRWLOCK *)(a1 + 72);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  if ( ((a2 - 1) & 0xFFFFFFFC) == 0 && a2 != 3 )
  {
    hObject = 0;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hObject);
    Instance = CoCreateInstance(
                 &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
                 0,
                 4u,
                 &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
                 &hObject);
    if ( Instance == -2147221164 )
    {
      LogonControllerTelemetry::FailedToLaunchLockAppBecauseExplorerIsNotRunning();
      goto LABEL_10;
    }
    if ( Instance < 0 )
    {
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2DE,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      v10 = hObject;
      if ( hObject )
      {
        hObject = 0;
        (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v10 + 16LL))(v10);
      }
      goto LABEL_12;
    }
    v57 = 0;
    *(_QWORD *)&Buf1.Data1 = &hObject;
    *(_QWORD *)Buf1.Data4 = &v57;
    if ( (unsigned int)IsDebuggerPresent(0) )
    {
      Instance = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_4707c60feee3eac480d59b58485360bd___(&Buf1);
    }
    else
    {
      CRPCTimeout::CRPCTimeout(&Parameter, v11);
      Instance = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_4707c60feee3eac480d59b58485360bd___(&Buf1);
      if ( Instance < 0 && BYTE4(Parameter) )
        Instance = -2147417825;
      if ( (int)p_hObject >= 0 )
      {
        LODWORD(p_hObject) = -2147467259;
        CoDisableCallCancellation(0);
        if ( Timer )
          DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      }
    }
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E0,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v57);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hObject);
LABEL_12:
      if ( a1 != -72 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 72));
      v66 = &LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::`vftable';
      goto LABEL_161;
    }
    v12 = (Microsoft::WRL::AgileRef *)(a1 + 96);
    v13 = v57;
    v56 = 0;
    if ( v57 )
    {
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v56);
      AgileReference = RoGetAgileReference(0, &GUID_a2aa05aa_47af_4b4a_8e77_6cd6efe35cda, v13, &v56);
    }
    v14 = v56;
    v56 = 0;
    *(_QWORD *)&Buf1.Data1 = *(_QWORD *)v12;
    *(_QWORD *)v12 = v14;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&Buf1);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v56);
    if ( AgileReference < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E1,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
        (const char *)(unsigned int)AgileReference,
        ppv);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v57);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hObject);
      if ( a1 != -72 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 72));
      v66 = &LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::`vftable';
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v66);
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v66);
      return (unsigned int)AgileReference;
    }
    v15 = 0;
    v16 = v57;
    if ( v57 )
    {
      v57 = 0;
      ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
    }
    v17 = hObject;
    if ( hObject )
    {
      hObject = 0;
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v17 + 16LL))(v17);
    }
LABEL_50:
    v24 = (Microsoft::WRL::AgileRef *)(a1 + 80);
    if ( *(_QWORD *)(a1 + 80) )
      goto LABEL_142;
    v56 = 0;
    if ( v15 )
    {
      v25 = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ILockScreenDirectorPrivate>>(&v56);
      Instance = CoCreateInstance(
                   &GUID_94291a92_7486_487b_bc9a_206a12880f02,
                   0,
                   4u,
                   &GUID_d72586df_0aac_4c94_9370_9863360cdb6b,
                   v25);
      if ( Instance < 0 )
      {
        v26 = 746;
LABEL_54:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
          (const char *)(unsigned int)Instance,
          ppv);
LABEL_55:
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v56);
        goto LABEL_56;
      }
      v27 = (HANDLE *)(a1 + 104);
      goto LABEL_119;
    }
    v57 = 0;
    if ( *(_QWORD *)v12 )
    {
      Instance = Microsoft::WRL::AgileRef::CopyTo(v12, &GUID_a2aa05aa_47af_4b4a_8e77_6cd6efe35cda, &v57);
      if ( Instance >= 0 )
      {
        v28 = v57;
        *(_QWORD *)&Buf1.Data1 = 0;
        dwProcessId[0] = 0;
        v58 = 0;
        QueryInterface = v57->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v58);
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD))QueryInterface)(
                     v28,
                     &GUID_5524fe34_8da7_40a8_8165_e8b37a8b4a4b,
                     &v58);
        if ( Instance >= 0 )
          Instance = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), DWORD *))(*v58)[3])(
                       v58,
                       dwProcessId);
        v30 = v58;
        if ( v58 )
        {
          v58 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v30)[2])(v30);
        }
        if ( Instance < 0
          || (v31 = (char *)OpenProcess(0x40u, 0, dwProcessId[0]), (*(_QWORD *)&Buf1.Data1 = v31) == 0)
          && (Instance = ResultFromKnownLastError(), Instance < 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F4,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
            (const char *)(unsigned int)Instance,
            ppv);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Buf1);
          Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v57);
          goto LABEL_55;
        }
        hObject = 0;
        CurrentProcess = GetCurrentProcess();
        v33 = GetCurrentProcess();
        if ( !DuplicateHandle(v33, CurrentProcess, v31, &hObject, 0x100000u, 0, 0) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x2F7,
                        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
                        v34);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Buf1);
          Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v57);
          Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v56);
          if ( v8 )
            ReleaseSRWLockExclusive(v8);
          goto LABEL_134;
        }
        Parameter = &v57;
        p_hObject = &hObject;
        Timer = &v56;
        if ( (unsigned int)IsDebuggerPresent(0) )
        {
          Instance = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_4a4f2905eb325c70f4402426812ab290___(&Parameter);
        }
        else
        {
          Buf1.Data1 = GetCurrentThreadId();
          LOBYTE(Buf1.Data2) = 0;
          *(_DWORD *)Buf1.Data4 = -2147467259;
          phNewTimer = 0;
          *(_DWORD *)Buf1.Data4 = CoEnableCallCancellation(0);
          if ( *(int *)Buf1.Data4 >= 0 )
            CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Buf1, 0x1388u, 0x3E8u, 0);
          Instance = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_4a4f2905eb325c70f4402426812ab290___(&Parameter);
          if ( Instance < 0 && LOBYTE(Buf1.Data2) )
            Instance = -2147417825;
          if ( *(int *)Buf1.Data4 >= 0 )
          {
            *(_DWORD *)Buf1.Data4 = -2147467259;
            CoDisableCallCancellation(0);
            if ( phNewTimer )
              DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          }
        }
        if ( Instance < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F9,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
            (const char *)(unsigned int)Instance,
            ppvb);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          if ( (unsigned __int64)(v31 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v31);
          v35 = v57;
          if ( v57 )
          {
            v57 = 0;
            ((void (__fastcall *)(struct IUnknown *))v35->lpVtbl->Release)(v35);
          }
          v36 = v56;
          if ( v56 )
          {
            v56 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v36)[2])(v36);
          }
          if ( a1 == -72 )
            goto LABEL_160;
          goto LABEL_159;
        }
        hObject = 0;
        v27 = (HANDLE *)(a1 + 104);
        v37 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD))v56;
        *(_QWORD *)(a1 + 104) = 0;
        dwProcessId[0] = 0;
        v58 = 0;
        v38 = **v37;
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v58);
        Instance = v38(v37, &GUID_5524fe34_8da7_40a8_8165_e8b37a8b4a4b, &v58);
        if ( Instance >= 0 )
          Instance = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), DWORD *))(*v58)[3])(
                       v58,
                       dwProcessId);
        v39 = v58;
        if ( v58 )
        {
          v58 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v39)[2])(v39);
        }
        if ( Instance < 0
          || (v40 = OpenProcess(0x100651u, 0, dwProcessId[0]), (*v27 = v40) == 0)
          && (Instance = ResultFromKnownLastError(), Instance < 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x301,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
            (const char *)(unsigned int)Instance,
            ppvb);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          if ( (unsigned __int64)(v31 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v31);
          v50 = v57;
          if ( v57 )
          {
            v57 = 0;
            ((void (__fastcall *)(struct IUnknown *))v50->lpVtbl->Release)(v50);
          }
          v51 = v56;
          if ( v56 )
          {
            v56 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v51)[2])(v51);
          }
LABEL_56:
          if ( !v8 )
            goto LABEL_160;
          goto LABEL_159;
        }
        if ( !RegisterWaitForSingleObject(
                (PHANDLE)(a1 + 112),
                *v27,
                CLockHost::_s_OnProcessClose,
                (PVOID)a1,
                0xFFFFFFFF,
                8u) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x302,
                        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
                        v41);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          if ( (unsigned __int64)(v31 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v31);
          v42 = v57;
          if ( v57 )
          {
            v57 = 0;
            ((void (__fastcall *)(struct IUnknown *))v42->lpVtbl->Release)(v42);
          }
          v43 = v56;
          if ( v56 )
          {
            v56 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v43)[2])(v43);
          }
          if ( v8 )
            ReleaseSRWLockExclusive(v8);
          goto LABEL_134;
        }
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        if ( (unsigned __int64)(v31 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v31);
        v44 = v57;
        if ( v57 )
        {
          v57 = 0;
          ((void (__fastcall *)(struct IUnknown *))v44->lpVtbl->Release)(v44);
        }
        v3 = v62;
LABEL_119:
        v58 = v56;
        if ( v56 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v56)[1])(v56);
        if ( (unsigned int)IsDebuggerPresent(*v27) )
        {
          LastError = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_e95e31c3d918f43de1ab0c6f6c8c5524___(&v58);
        }
        else
        {
          CRPCTimeout::CRPCTimeout(&Parameter, v45);
          LastError = CCLambdaAdapter_long____cdecl___void____1_::Adapt__lambda_e95e31c3d918f43de1ab0c6f6c8c5524___(&v58);
          if ( LastError < 0 && BYTE4(Parameter) )
            LastError = -2147417825;
          if ( (int)p_hObject >= 0 )
          {
            LODWORD(p_hObject) = -2147467259;
            CoDisableCallCancellation(0);
            if ( Timer )
              DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          }
        }
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v58);
        if ( LastError < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x306,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
            (const char *)(unsigned int)LastError,
            ppv);
          v46 = v56;
          if ( v56 )
          {
            v56 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v46)[2])(v46);
          }
          if ( v8 )
            ReleaseSRWLockExclusive(v8);
LABEL_134:
          v66 = &LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::`vftable';
          wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v66);
          wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v66);
          return (unsigned int)LastError;
        }
        v47 = v56;
        v58 = 0;
        Instance = 0;
        if ( v56 )
        {
          Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v58);
          Instance = RoGetAgileReference(0, &GUID_d72586df_0aac_4c94_9370_9863360cdb6b, v47, &v58);
        }
        v48 = v58;
        v58 = 0;
        v62 = *(struct IUnknown ***)v24;
        *(_QWORD *)v24 = v48;
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v62);
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v58);
        if ( Instance < 0 )
        {
          v26 = 776;
          goto LABEL_54;
        }
        v49 = v56;
        if ( v56 )
        {
          v56 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v49)[2])(v49);
        }
        if ( !*(_QWORD *)v24 )
        {
          *v3 = 0;
          Instance = -2147024809;
LABEL_158:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30B,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
            (const char *)(unsigned int)Instance,
            ppv);
          if ( !v8 )
          {
LABEL_160:
            v66 = &LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::`vftable';
LABEL_161:
            wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v66);
            wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v66);
            return (unsigned int)Instance;
          }
LABEL_159:
          ReleaseSRWLockExclusive(v8);
          goto LABEL_160;
        }
LABEL_142:
        Instance = Microsoft::WRL::AgileRef::CopyTo(v24, &GUID_d72586df_0aac_4c94_9370_9863360cdb6b, v3);
        if ( Instance >= 0 )
        {
          wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v66, 0);
          if ( v8 )
            ReleaseSRWLockExclusive(v8);
          v66 = &LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::`vftable';
          wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v66);
          wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v66);
          return 0;
        }
        goto LABEL_158;
      }
    }
    else
    {
      Instance = -2147024809;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v57);
    goto LABEL_55;
  }
  if ( *(_QWORD *)(a1 + 88) )
  {
LABEL_49:
    v15 = 1;
    v12 = (Microsoft::WRL::AgileRef *)(a1 + 96);
    goto LABEL_50;
  }
  hObject = 0;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hObject);
  v18 = CoCreateInstance(
          &GUID_4edd6725_7003_4120_a0bb_bbdeba704fb7,
          0,
          4u,
          &GUID_50977f92_07ea_498c_ae9f_28628a9a69f1,
          &hObject);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v20 = AgileGitPtr::Initialize<ILockAppHostServer>(a1 + 88, &hObject);
    Instance = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CC,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
        (const char *)(unsigned int)v20,
        ppva);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hObject);
      goto LABEL_12;
    }
    ServerProcessHandle = IUnknown_GetServerProcessHandle((struct IUnknown *)hObject, 0x100651u, (void **)(a1 + 104));
    Instance = ServerProcessHandle;
    if ( ServerProcessHandle < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D2,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
        (const char *)(unsigned int)ServerProcessHandle,
        ppva);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hObject);
      goto LABEL_12;
    }
    if ( !RegisterWaitForSingleObject(
            (PHANDLE)(a1 + 112),
            *(HANDLE *)(a1 + 104),
            CLockHost::_s_OnProcessClose,
            (PVOID)a1,
            0xFFFFFFFF,
            8u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2D3,
                    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
                    v22);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hObject);
      if ( v8 )
        ReleaseSRWLockExclusive(v8);
      goto LABEL_134;
    }
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hObject);
    goto LABEL_49;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C9,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lockhost\\lockhost.cpp",
    (const char *)(unsigned int)v18,
    ppva);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&hObject);
  if ( a1 != -72 )
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 72));
  v66 = &LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::`vftable';
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v66);
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v66);
  return v19;
}

```

## disassembly

```asm
0x180028f70  mov     [rsp-8+arg_8], rbx
0x180028f75  push    rbp
0x180028f76  push    rsi
0x180028f77  push    rdi
0x180028f78  push    r12
0x180028f7a  push    r13
0x180028f7c  push    r14
0x180028f7e  push    r15
0x180028f80  lea     rbp, [rsp-120h]
0x180028f88  sub     rsp, 220h
0x180028f8f  mov     rax, cs:__security_cookie
0x180028f96  xor     rax, rsp
0x180028f99  mov     [rbp+150h+var_40], rax
0x180028fa0  mov     r13, r8
0x180028fa3  mov     [rbp+150h+var_1C0], r8
0x180028fa7  mov     edi, edx
0x180028fa9  mov     rbx, rcx
0x180028fac  lea     rax, ??_7?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x180028fb3  mov     [rbp+150h+var_190], rax
0x180028fb7  xor     r14d, r14d
0x180028fba  mov     [rbp+150h+var_188], r14d
0x180028fbe  mov     [rbp+150h+var_184], r14b
0x180028fc2  mov     [rbp+150h+var_148], r14b
0x180028fc6  mov     [rbp+150h+var_160], r14d
0x180028fca  lea     rax, aClockhostEnsur; "CLockHost__EnsureLockAppHost_Activity"
0x180028fd1  mov     [rbp+150h+var_158], rax
0x180028fd5  mov     [rbp+150h+var_150], r14
0x180028fd9  mov     [rbp+150h+var_140], r14d
0x180028fdd  xorps   xmm0, xmm0
0x180028fe0  movdqa  [rbp+150h+var_A0], xmm0
0x180028fe8  xorps   xmm1, xmm1
0x180028feb  xor     eax, eax
0x180028fed  movups  [rbp+150h+var_138], xmm1
0x180028ff1  movups  [rbp+150h+var_128], xmm1
0x180028ff5  movups  [rbp+150h+var_118], xmm1
0x180028ff9  movups  [rbp+150h+var_108], xmm1
0x180028ffd  movups  [rbp+150h+var_F8], xmm1
0x180029001  movups  [rbp+150h+var_E8], xmm1
0x180029005  movups  [rbp+150h+var_D8], xmm1
0x180029009  movups  [rbp+150h+var_C8], xmm1
0x180029010  movups  [rbp+150h+var_B8], xmm1
0x180029017  mov     [rbp+150h+var_A8], rax
0x18002901e  mov     [rbp+150h+var_90], 1
0x180029028  mov     [rbp+150h+var_88], rax
0x18002902f  lea     rax, [rbp+150h+var_188]
0x180029033  mov     [rbp+150h+var_80], rax
0x18002903a  mov     [rbp+150h+var_78], r14
0x180029041  xor     r9d, r9d; bool
0x180029044  lea     r8, [rbp+150h+var_160]; struct wil::CallContextInfo *
0x180029048  lea     rdx, [rbp+150h+var_190]; struct wil::details::IFailureCallback *
0x18002904c  lea     rcx, [rbp+150h+var_70]; this
0x180029053  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180029058  nop
0x180029059  lea     r15, ??_7CLockHost__EnsureLockAppHost_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::`vftable'
0x180029060  mov     [rbp+150h+var_190], r15
0x180029064  lea     rcx, [rsp+250h+Buf1]; retstr
0x180029069  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18002906e  movups  xmm0, xmmword ptr [rax]
0x180029071  movups  [rsp+250h+Buf1], xmm0
0x180029076  mov     r8d, 10h; Size
0x18002907c  lea     rdx, GUID_NULL; Buf2
0x180029083  lea     rcx, [rsp+250h+Buf1]; Buf1
0x180029088  call    memcmp_0
0x18002908d  test    eax, eax
0x18002908f  jz      short loc_18002909F
0x180029091  lea     rdx, [rsp+250h+Buf1]
0x180029096  lea     rcx, [rbp+150h+var_190]
0x18002909a  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18002909f  lea     rcx, [rbp+150h+var_190]; this
0x1800290a3  call    ?StartActivity@CLockHost__EnsureLockAppHost_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLockHost__EnsureLockAppHost_Activity::StartActivity(void)
0x1800290a8  mov     [r13+0], r14
0x1800290ac  cmp     dword ptr [rbx+0B0h], 5
0x1800290b3  jb      short loc_1800290F8
0x1800290b5  call    ?DesktopLockHostActivationBackedOff@LogonControllerTelemetry@@SAXXZ; LogonControllerTelemetry::DesktopLockHostActivationBackedOff(void)
0x1800290ba  mov     rcx, [rbp+158h]; this
0x1800290c1  mov     r9d, 80004004h; char *
0x1800290c7  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800290ce  mov     edx, 2A5h; void *
0x1800290d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800290d8  mov     [rbp+150h+var_190], r15
0x1800290dc  lea     rcx, [rbp+150h+var_190]
0x1800290e0  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800290e5  lea     rcx, [rbp+150h+var_190]
0x1800290e9  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800290ee  mov     eax, 80004004h
0x1800290f3  jmp     loc_180029DD8
0x1800290f8  lea     r12, [rbx+48h]
0x1800290fc  mov     rcx, r12; SRWLock
0x1800290ff  call    cs:__imp_AcquireSRWLockExclusive
0x180029105  lea     eax, [rdi-1]
0x180029108  mov     esi, 8001011Fh
0x18002910d  test    eax, 0FFFFFFFCh
0x180029112  jnz     loc_180029379
0x180029118  cmp     edi, 3
0x18002911b  jz      loc_180029379
0x180029121  mov     [rsp+250h+hObject], r14
0x180029126  lea     rcx, [rsp+250h+hObject]
0x18002912b  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180029130  lea     rax, [rsp+250h+hObject]
0x180029135  mov     [rsp+250h+ppv], rax; int
0x18002913a  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180029141  xor     edx, edx; pUnkOuter
0x180029143  mov     r8d, 4; dwClsContext
0x180029149  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x180029150  call    cs:__imp_CoCreateInstance
0x180029156  mov     edi, eax
0x180029158  cmp     eax, 80040154h
0x18002915d  jnz     short loc_180029166
0x18002915f  call    ?FailedToLaunchLockAppBecauseExplorerIsNotRunning@LogonControllerTelemetry@@SAXXZ; LogonControllerTelemetry::FailedToLaunchLockAppBecauseExplorerIsNotRunning(void)
0x180029164  jmp     short loc_18002916A
0x180029166  test    edi, edi
0x180029168  jns     short loc_1800291B7
0x18002916a  mov     rcx, [rbp+158h]; this
0x180029171  mov     r9d, edi; char *
0x180029174  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002917b  mov     edx, 2DEh; void *
0x180029180  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029185  mov     rcx, [rsp+250h+hObject]
0x18002918a  test    rcx, rcx
0x18002918d  jz      short loc_1800291A0
0x18002918f  mov     [rsp+250h+hObject], r14
0x180029194  mov     rax, [rcx]
0x180029197  mov     rax, [rax+10h]
0x18002919b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291a0  test    r12, r12
0x1800291a3  jz      short loc_1800291AE
0x1800291a5  mov     rcx, r12; SRWLock
0x1800291a8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800291ae  mov     [rbp+150h+var_190], r15
0x1800291b2  jmp     loc_180029DC4
0x1800291b7  mov     [rsp+250h+var_200], r14
0x1800291bc  lea     rax, [rsp+250h+hObject]
0x1800291c1  mov     qword ptr [rsp+250h+Buf1], rax
0x1800291c6  lea     rax, [rsp+250h+var_200]
0x1800291cb  mov     qword ptr [rsp+250h+Buf1+8], rax
0x1800291d0  xor     ecx, ecx; hProcess
0x1800291d2  call    ?IsDebuggerPresent@@YAHPEAX@Z; IsDebuggerPresent(void *)
0x1800291d7  test    eax, eax
0x1800291d9  jnz     short loc_18002922A
0x1800291db  lea     rcx, [rbp+150h+Parameter]; Parameter
0x1800291df  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x1800291e4  lea     rcx, [rsp+250h+Buf1]
0x1800291e9  call    CCLambdaAdapter_long____cdecl___void____1___Adapt__lambda_4707c60feee3eac480d59b58485360bd___
0x1800291ee  mov     edi, eax
0x1800291f0  test    eax, eax
0x1800291f2  jns     short loc_1800291FB
0x1800291f4  cmp     byte ptr [rbp+150h+Parameter+4], 0
0x1800291f8  cmovnz  edi, esi
0x1800291fb  cmp     dword ptr [rbp+150h+var_1A8], 0
0x1800291ff  jl      short loc_180029236
0x180029201  mov     dword ptr [rbp+150h+var_1A8], 80004005h
0x180029208  xor     ecx, ecx; pReserved
0x18002920a  call    cs:__imp_CoDisableCallCancellation
0x180029210  mov     rdx, [rbp+150h+Timer]; Timer
0x180029214  test    rdx, rdx
0x180029217  jz      short loc_180029236
0x180029219  xor     ecx, ecx; TimerQueue
0x18002921b  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180029222  call    cs:__imp_DeleteTimerQueueTimer
0x180029228  jmp     short loc_180029236
0x18002922a  lea     rcx, [rsp+250h+Buf1]
0x18002922f  call    CCLambdaAdapter_long____cdecl___void____1___Adapt__lambda_4707c60feee3eac480d59b58485360bd___
0x180029234  mov     edi, eax
0x180029236  test    edi, edi
0x180029238  jns     short loc_18002926E
0x18002923a  mov     rcx, [rbp+158h]; this
0x180029241  mov     r9d, edi; char *
0x180029244  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002924b  mov     edx, 2E0h; void *
0x180029250  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029255  lea     rcx, [rsp+250h+var_200]
0x18002925a  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18002925f  lea     rcx, [rsp+250h+hObject]
0x180029264  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180029269  jmp     loc_1800291A0
0x18002926e  lea     rdi, [rbx+60h]
0x180029272  mov     rsi, [rsp+250h+var_200]
0x180029277  mov     [rsp+250h+var_208], r14
0x18002927c  test    rsi, rsi
0x18002927f  jz      short loc_1800292A5
0x180029281  lea     rcx, [rsp+250h+var_208]
0x180029286  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002928b  lea     r9, [rsp+250h+var_208]
0x180029290  mov     r8, rsi
0x180029293  lea     rdx, _GUID_a2aa05aa_47af_4b4a_8e77_6cd6efe35cda
0x18002929a  xor     ecx, ecx
0x18002929c  call    cs:__imp_RoGetAgileReference
0x1800292a2  mov     r14d, eax
0x1800292a5  mov     rdx, [rsp+250h+var_208]
0x1800292aa  mov     [rsp+250h+var_208], 0
0x1800292b3  mov     rcx, [rdi]
0x1800292b6  mov     qword ptr [rsp+250h+Buf1], rcx
0x1800292bb  mov     [rdi], rdx
0x1800292be  lea     rcx, [rsp+250h+Buf1]
0x1800292c3  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800292c8  nop
0x1800292c9  lea     rcx, [rsp+250h+var_208]
0x1800292ce  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800292d3  nop
0x1800292d4  test    r14d, r14d
0x1800292d7  jns     short loc_180029334
0x1800292d9  mov     rcx, [rbp+158h]; this
0x1800292e0  mov     r9d, r14d; char *
0x1800292e3  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800292ea  mov     edx, 2E1h; void *
0x1800292ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800292f4  lea     rcx, [rsp+250h+var_200]
0x1800292f9  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1800292fe  lea     rcx, [rsp+250h+hObject]
0x180029303  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180029308  test    r12, r12
0x18002930b  jz      short loc_180029316
0x18002930d  mov     rcx, r12; SRWLock
0x180029310  call    cs:__imp_ReleaseSRWLockExclusive
0x180029316  mov     [rbp+150h+var_190], r15
0x18002931a  lea     rcx, [rbp+150h+var_190]
0x18002931e  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180029323  lea     rcx, [rbp+150h+var_190]
0x180029327  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002932c  mov     eax, r14d
0x18002932f  jmp     loc_180029DD8
0x180029334  xor     sil, sil
0x180029337  mov     rcx, [rsp+250h+var_200]
0x18002933c  xor     r14d, r14d
0x18002933f  test    rcx, rcx
0x180029342  jz      short loc_180029355
0x180029344  mov     [rsp+250h+var_200], r14
0x180029349  mov     rax, [rcx]
0x18002934c  mov     rax, [rax+10h]
0x180029350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029355  mov     rcx, [rsp+250h+hObject]
0x18002935a  test    rcx, rcx
0x18002935d  jz      loc_18002951C
0x180029363  mov     [rsp+250h+hObject], r14
0x180029368  mov     rax, [rcx]
0x18002936b  mov     rax, [rax+10h]
0x18002936f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029374  jmp     loc_18002951C
0x180029379  cmp     qword ptr [rbx+58h], 0
0x18002937e  jnz     loc_180029515
0x180029384  mov     [rsp+250h+hObject], r14
0x180029389  lea     rcx, [rsp+250h+hObject]
0x18002938e  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180029393  lea     rax, [rsp+250h+hObject]
0x180029398  mov     [rsp+250h+ppv], rax; int
0x18002939d  lea     r9, _GUID_50977f92_07ea_498c_ae9f_28628a9a69f1; riid
0x1800293a4  xor     edx, edx; pUnkOuter
0x1800293a6  mov     r8d, 4; dwClsContext
0x1800293ac  lea     rcx, _GUID_4edd6725_7003_4120_a0bb_bbdeba704fb7; rclsid
0x1800293b3  call    cs:__imp_CoCreateInstance
0x1800293b9  mov     esi, eax
0x1800293bb  test    eax, eax
0x1800293bd  jns     short loc_18002940F
0x1800293bf  mov     rcx, [rbp+158h]; this
0x1800293c6  mov     r9d, eax; char *
0x1800293c9  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800293d0  mov     edx, 2C9h; void *
0x1800293d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800293da  lea     rcx, [rsp+250h+hObject]
0x1800293df  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1800293e4  test    r12, r12
0x1800293e7  jz      short loc_1800293F2
0x1800293e9  mov     rcx, r12; SRWLock
0x1800293ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800293f2  mov     [rbp+150h+var_190], r15
0x1800293f6  lea     rcx, [rbp+150h+var_190]
0x1800293fa  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800293ff  lea     rcx, [rbp+150h+var_190]
0x180029403  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180029408  mov     eax, esi
0x18002940a  jmp     loc_180029DD8
0x18002940f  lea     rdx, [rsp+250h+hObject]
0x180029414  lea     rcx, [rbx+58h]
0x180029418  call    ??$Initialize@UILockAppHostServer@@@AgileGitPtr@@QEAAJAEBV?$ComPtr@UILockAppHostServer@@@WRL@Microsoft@@@Z; AgileGitPtr::Initialize<ILockAppHostServer>(Microsoft::WRL::ComPtr<ILockAppHostServer> const &)
0x18002941d  mov     edi, eax
0x18002941f  test    eax, eax
0x180029421  jns     short loc_18002944D
0x180029423  mov     rcx, [rbp+158h]; this
0x18002942a  mov     r9d, eax; char *
0x18002942d  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x180029434  mov     edx, 2CCh; void *
0x180029439  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002943e  lea     rcx, [rsp+250h+hObject]
0x180029443  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180029448  jmp     loc_1800291A0
0x18002944d  lea     r8, [rbx+68h]; void **
0x180029451  mov     edx, 100651h; unsigned int
0x180029456  mov     rcx, [rsp+250h+hObject]; struct IUnknown *
0x18002945b  call    ?IUnknown_GetServerProcessHandle@@YAJPEAUIUnknown@@KPEAPEAX@Z; IUnknown_GetServerProcessHandle(IUnknown *,ulong,void * *)
0x180029460  mov     edi, eax
0x180029462  test    eax, eax
0x180029464  jns     short loc_180029490
0x180029466  mov     rcx, [rbp+158h]; this
0x18002946d  mov     r9d, eax; char *
0x180029470  lea     r8, aPcshellShellAu_7; "pcshell\\shell\\auth\\authux\\controlle"...
0x180029477  mov     edx, 2D2h; void *
0x18002947c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029481  lea     rcx, [rsp+250h+hObject]
0x180029486  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18002948b  jmp     loc_1800291A0
  ... truncated ...
```
