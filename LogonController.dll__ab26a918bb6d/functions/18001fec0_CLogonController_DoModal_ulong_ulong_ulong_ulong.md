# CLogonController::DoModal(ulong,ulong,ulong,ulong)

- ea: `0x18001fec0`
- end: `0x18002078a`
- name: `?DoModal@CLogonController@@UEAAJKKKK@Z`
- size: `2250`
- prototype: `int(CLogonController *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `33`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008094`
- `0x18000df10`
- `0x18001da0c`
- `0x18001f3a0`
- `0x18001fec0`
- `0x180020790`
- `0x1800207e8`
- `0x1800208b4`
- `0x180020948`
- `0x180020d3c`
- `0x180021054`
- `0x180021100`
- `0x1800211d0`
- `0x180021634`
- `0x180027010`
- `0x18002f760`
- `0x18002ff58`
- `0x1800342ac`
- `0x180040e6c`
- `0x180040e98`
- `0x180040f00`
- `0x180040f90`
- `0x180041674`
- `0x180041964`
- `0x18005d488`
- `0x18005d4e8`
- `0x180061ebc`
- `0x180063a40`
- `0x18006503c`
- `0x18006c000`
- `0x18006cad0`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18002007d`
- `KERNEL32!CreateEventW` at `0x18002007d`
- `KERNEL32!SetEvent` at `0x18002061b`
- `KERNEL32!SetEvent` at `0x18002065c`
- `KERNEL32!SetEvent` at `0x18002071e`
- `KERNEL32!SetEvent` at `0x180020753`
- `KERNEL32!SetEvent` at `0x18002061b`
- `KERNEL32!SetEvent` at `0x18002065c`
- `KERNEL32!SetEvent` at `0x18002071e`
- `KERNEL32!SetEvent` at `0x180020753`
- `KERNEL32!OpenEventW` at `0x18002010f`
- `KERNEL32!OpenEventW` at `0x180020379`
- `KERNEL32!OpenEventW` at `0x180020467`
- `KERNEL32!OpenEventW` at `0x1800205c1`
- `KERNEL32!OpenEventW` at `0x18002010f`
- `KERNEL32!OpenEventW` at `0x180020379`
- `KERNEL32!OpenEventW` at `0x180020467`
- `KERNEL32!OpenEventW` at `0x1800205c1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180020562`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800205a5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180020562`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800205a5`
- `KERNEL32!WaitForSingleObject` at `0x18002024b`
- `KERNEL32!WaitForSingleObject` at `0x18002025d`
- `KERNEL32!WaitForSingleObject` at `0x1800202b6`
- `KERNEL32!WaitForSingleObject` at `0x18002024b`
- `KERNEL32!WaitForSingleObject` at `0x18002025d`
- `KERNEL32!WaitForSingleObject` at `0x1800202b6`
- `KERNEL32!CloseHandle` at `0x180020267`
- `KERNEL32!CloseHandle` at `0x1800202c3`
- `KERNEL32!CloseHandle` at `0x180020624`
- `KERNEL32!CloseHandle` at `0x18002062f`
- `KERNEL32!CloseHandle` at `0x180020665`
- `KERNEL32!CloseHandle` at `0x18002075c`
- `KERNEL32!CloseHandle` at `0x180020267`
- `KERNEL32!CloseHandle` at `0x1800202c3`
- `KERNEL32!CloseHandle` at `0x180020624`
- `KERNEL32!CloseHandle` at `0x18002062f`
- `KERNEL32!CloseHandle` at `0x180020665`
- `KERNEL32!CloseHandle` at `0x18002075c`
- `ntdll!RtlPublishWnfStateData` at `0x1800202a6`
- `ntdll!RtlPublishWnfStateData` at `0x1800202a6`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x18002002b`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180020037`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x18002002b`
- `SHCORE!SHTaskPoolGetUniqueContext` at `0x180020037`
- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x180020002`
- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x180020002`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180020326`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180020335`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180020326`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180020335`
- `USER32!ShowCursor` at `0x180020342`
- `USER32!ShowCursor` at `0x180020342`
- `RPCRT4!RpcServerUnregisterIf` at `0x180020736`
- `RPCRT4!RpcServerUnregisterIf` at `0x180020736`
- `RPCRT4!RpcBindingVectorFree` at `0x1800204f4`
- `RPCRT4!RpcBindingVectorFree` at `0x1800204f4`
- `RPCRT4!RpcEpUnregister` at `0x180020425`
- `RPCRT4!RpcEpUnregister` at `0x180020425`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CLogonController::DoModal(
        CLogonController *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  HRESULT v9; // eax
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  unsigned int LastError; // edi
  HANDLE EventW; // rdi
  const char *v15; // r9
  char *v16; // rcx
  int v17; // eax
  CServer *v18; // rcx
  char *v19; // rax
  void *v20; // rbx
  int v22; // eax
  CServer *v23; // rdi
  CServer *v24; // rcx
  char *v25; // rax
  void *v26; // rbx
  char *v27; // rax
  void *v28; // rbx
  char v29; // bl
  char v30; // bl
  char *v31; // rbx
  CLogonController *v32; // rcx
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  char *v36; // [rsp+30h] [rbp-D0h] BYREF
  CServer *v37; // [rsp+38h] [rbp-C8h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-C0h] BYREF
  char v39; // [rsp+51h] [rbp-AFh]
  void **v40; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v41[8]; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v42; // [rsp+68h] [rbp-98h] BYREF
  void **v43; // [rsp+80h] [rbp-80h] BYREF
  int v44; // [rsp+88h] [rbp-78h] BYREF
  char v45; // [rsp+8Ch] [rbp-74h]
  int v46; // [rsp+B0h] [rbp-50h] BYREF
  const char *v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  char v49; // [rsp+C8h] [rbp-38h]
  int v50; // [rsp+D0h] [rbp-30h]
  _BYTE v51[152]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v52; // [rsp+170h] [rbp+70h]
  int v53; // [rsp+180h] [rbp+80h]
  __int64 v54; // [rsp+188h] [rbp+88h]
  int *v55; // [rsp+190h] [rbp+90h]
  _DWORD *v56; // [rsp+198h] [rbp+98h] BYREF
  _QWORD v57[3]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v58; // [rsp+1B8h] [rbp+B8h]
  int *v59; // [rsp+1C0h] [rbp+C0h]
  char v60; // [rsp+1C8h] [rbp+C8h]
  void **v61; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v62[264]; // [rsp+1D8h] [rbp+D8h] BYREF
  _DWORD *v63; // [rsp+2E0h] [rbp+1E0h]
  _DWORD *v64; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v65[24]; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v66; // [rsp+308h] [rbp+208h]
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v44 = 0;
  v45 = 0;
  v49 = 0;
  v46 = 0;
  v47 = "CLogonController_DoModal_Activity";
  v48 = 0;
  v50 = 0;
  v52 = 0;
  memset_0(v51, 0, sizeof(v51));
  v53 = 1;
  v54 = 0;
  v55 = &v44;
  v56 = 0;
  v57[0] = 0;
  v57[1] = &v43;
  v57[2] = 0;
  v58 = 0;
  v59 = &v46;
  v60 = 0;
  v43 = &LogonControllerTelemetry::CLogonController_DoModal_Activity::`vftable';
  Buf1 = (__int128)*GetFirstRunTelemetryCorrelationId(&v42);
  if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v43,
      &Buf1);
  LogonControllerTelemetry::CLogonController_DoModal_Activity::StartActivity((LogonControllerTelemetry::CLogonController_DoModal_Activity *)&v43);
  LogonControllerTelemetry::ProcessStartup::Start<>((LogonControllerTelemetry::ProcessStartup *)&v61);
  DwmWnfDiagnosticEvent::CDwmWnfDumpRequestListener::CDwmWnfDumpRequestListener((DwmWnfDiagnosticEvent::CDwmWnfDumpRequestListener *)&v40);
  v40 = &CLogonDwmWnfDumpRequestListener::`vftable';
  v9 = DXGIDeclareAdapterRemovalSupport();
  v10 = retaddr;
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v9,
      v33);
  *((_DWORD *)this + 50) = SHTaskPoolGetUniqueContext(v10);
  *((_DWORD *)this + 51) = SHTaskPoolGetUniqueContext(v11);
  Windows::Shell::CImmersiveCursor::DisableCursorSuppression();
  v39 = 1;
  v12 = CLogonController::_Initialize((CLogonController *)((char *)this - 8), a2, a3, a4, a5);
  LastError = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x172,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v12,
      v34);
    v27 = (char *)OpenEventW(2u, 0, L"Global\\LogonUIExitEvent");
    v28 = v27;
    if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      SetEvent(v27);
      CloseHandle(v28);
    }
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(v41);
    v61 = &LogonControllerTelemetry::ProcessStartup::`vftable';
    wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v61);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v65);
    wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(&v64);
    wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>(v62);
    v43 = &LogonControllerTelemetry::CLogonController_DoModal_Activity::`vftable';
    wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v43);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v57);
    goto LABEL_24;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v16 = (char *)*((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = 0;
  if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v16);
  *((_QWORD *)this + 41) = EventW;
  if ( EventW )
  {
    v37 = 0;
    v17 = Microsoft::WRL::Details::MakeAndInitialize<CServer,CServer,>(&v37);
    LastError = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x179,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v17,
        v34);
      v18 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(CServer *))(*(_QWORD *)v18 + 16LL))(v18);
      }
      v19 = (char *)OpenEventW(2u, 0, L"Global\\LogonUIExitEvent");
      v20 = v19;
      if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        SetEvent(v19);
        CloseHandle(v20);
      }
      wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(v41);
      v61 = &LogonControllerTelemetry::ProcessStartup::`vftable';
      if ( !v64 )
        goto LABEL_15;
      wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        &v61,
        &Buf1);
      if ( v64 && *v64 == 1 )
      {
        v29 = 1;
      }
      else
      {
        v29 = 0;
        wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(&v64);
      }
      if ( (_QWORD)Buf1 )
        ReleaseSRWLockExclusive((PSRWLOCK)Buf1);
      if ( v29 )
      {
LABEL_15:
        if ( *v63 == 1 )
        {
          wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException();
          wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v61);
        }
      }
      if ( v66 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v65);
      wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(&v64);
      wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>(v62);
      v43 = &LogonControllerTelemetry::CLogonController_DoModal_Activity::`vftable';
      if ( !v56 )
        goto LABEL_20;
      wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        &v43,
        &Buf1);
      if ( v56 && *v56 == 1 )
      {
        v30 = 1;
      }
      else
      {
        v30 = 0;
        wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(&v56);
      }
      if ( (_QWORD)Buf1 )
        ReleaseSRWLockExclusive((PSRWLOCK)Buf1);
      if ( v30 )
      {
LABEL_20:
        if ( *v55 == 1 )
        {
          wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException();
          wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v43);
        }
      }
      if ( v58 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v57);
LABEL_24:
      wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(&v56);
      wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>(&v44);
      return LastError;
    }
    *(_QWORD *)&v42.Data1 = (char *)this - 8;
    v42.Data4[0] = 1;
    v22 = CServer::Start(
            v37,
            (struct IWinLogonRPC *)(((unsigned __int64)this + 24)
                                  & ((unsigned __int128)-(__int128)((unsigned __int64)this - 8) >> 64)),
            a3,
            a4,
            a5);
    LastError = v22;
    if ( v22 >= 0 )
    {
      wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v61);
      WaitForSingleObject(*((HANDLE *)this + 41), 0xFFFFFFFF);
      v23 = v37;
      WaitForSingleObject(*((HANDLE *)v37 + 11), 0xFFFFFFFF);
      CloseHandle(*((HANDLE *)v23 + 11));
      if ( hEvent )
      {
        LODWORD(v36) = 0;
        *(_QWORD *)&Buf1 = __PAIR64__(CServer::s_dwWnfState1, CServer::s_dwWnfState0);
        RtlPublishWnfStateData(__PAIR64__(CServer::s_dwWnfState1, CServer::s_dwWnfState0), 0, &v36, 4, 0);
        WaitForSingleObject(hEvent, 0xFFFFFFFF);
        CloseHandle(hEvent);
        hEvent = 0;
      }
      if ( dword_1800D4124 && !RpcEpUnregister(qword_1800A0830, BindingVector, &UuidVector) )
        dword_1800D4124 = 0;
      if ( BindingVector && !RpcBindingVectorFree(&BindingVector) )
        BindingVector = 0;
      if ( dword_1800D4120 && !RpcServerUnregisterIf(qword_1800A0830, 0, 1u) )
        dword_1800D4120 = 0;
      memset_0(&xmmword_1800D4130, 0, 0xE8u);
      Windows::Shell::CImmersiveCursor::DisableCursorSuppression();
      if ( byte_1800D3540 != 1 )
      {
        byte_1800D3540 = 1;
        if ( GetSystemMetrics(19) )
        {
          if ( !GetSystemMetrics(4096) )
            ShowCursor(1);
        }
      }
      CLogonController::_Teardown((CLogonController *)((char *)this - 8));
      v24 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(CServer *))(*(_QWORD *)v24 + 16LL))(v24);
      }
      v25 = (char *)OpenEventW(2u, 0, L"Global\\LogonUIExitEvent");
      v26 = v25;
      if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        SetEvent(v25);
        CloseHandle(v26);
      }
      wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v43);
      wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(v41);
      v61 = &LogonControllerTelemetry::ProcessStartup::`vftable';
      wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v61);
      if ( v66 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v65);
      wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(&v64);
      wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>(v62);
      v43 = &LogonControllerTelemetry::CLogonController_DoModal_Activity::`vftable';
      wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v43);
      if ( v58 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v57);
      LastError = 0;
      goto LABEL_24;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v22,
      v35);
    Windows::Shell::CImmersiveCursor::DisableCursorSuppression();
    CLogonController::_ShowCursor(v32, 1);
    CLogonController::_Teardown((CLogonController *)((char *)this - 8));
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v37);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x176,
                  (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
                  v15);
  }
  v36 = 0;
  v31 = (char *)OpenEventW(2u, 0, L"Global\\LogonUIExitEvent");
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v36);
  v36 = v31;
  if ( (unsigned __int64)(v31 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    SetEvent(v31);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v36);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(v41);
  LogonControllerTelemetry::ProcessStartup::~ProcessStartup((LogonControllerTelemetry::ProcessStartup *)&v61);
  LogonControllerTelemetry::CLogonController_DoModal_Activity::~CLogonController_DoModal_Activity((LogonControllerTelemetry::CLogonController_DoModal_Activity *)&v43);
  return LastError;
}

```

## disassembly

```asm
0x18001fec0  mov     [rsp-8+arg_8], rbx
0x18001fec5  push    rbp
0x18001fec6  push    rsi
0x18001fec7  push    rdi
0x18001fec8  push    r12
0x18001feca  push    r13
0x18001fecc  push    r14
0x18001fece  push    r15
0x18001fed0  lea     rbp, [rsp-230h]
0x18001fed8  sub     rsp, 330h
0x18001fedf  mov     rax, cs:__security_cookie
0x18001fee6  xor     rax, rsp
0x18001fee9  mov     [rbp+260h+var_40], rax
0x18001fef0  mov     r12d, r9d
0x18001fef3  mov     r15d, r8d
0x18001fef6  mov     edi, edx
0x18001fef8  mov     rsi, rcx
0x18001fefb  xor     r13d, r13d
0x18001fefe  mov     [rbp+260h+var_2D8], r13d
0x18001ff02  mov     [rbp+260h+var_2D4], r13b
0x18001ff06  mov     [rbp+260h+var_298], r13b
0x18001ff0a  mov     [rbp+260h+var_2B0], r13d
0x18001ff0e  lea     rax, aClogoncontroll_25; "CLogonController_DoModal_Activity"
0x18001ff15  mov     [rbp+260h+var_2A8], rax
0x18001ff19  mov     [rbp+260h+var_2A0], r13
0x18001ff1d  mov     [rbp+260h+var_290], r13d
0x18001ff21  xorps   xmm0, xmm0
0x18001ff24  movdqa  [rbp+260h+var_1F0], xmm0
0x18001ff29  xor     edx, edx; Val
0x18001ff2b  mov     r8d, 98h; Size
0x18001ff31  lea     rcx, [rbp+260h+var_288]; void *
0x18001ff35  call    memset_0
0x18001ff3a  mov     [rbp+260h+var_1E0], 1
0x18001ff44  xor     eax, eax
0x18001ff46  mov     [rbp+260h+var_1D8], rax
0x18001ff4d  lea     rax, [rbp+260h+var_2D8]
0x18001ff51  mov     [rbp+260h+var_1D0], rax
0x18001ff58  mov     [rbp+260h+var_1C8], r13
0x18001ff5f  mov     [rbp+260h+var_1C0], r13
0x18001ff66  lea     rax, [rbp+260h+var_2E0]
0x18001ff6a  mov     [rbp+260h+var_1B8], rax
0x18001ff71  mov     [rbp+260h+var_1B0], r13
0x18001ff78  mov     [rbp+260h+var_1A8], r13d
0x18001ff7f  lea     rax, [rbp+260h+var_2B0]
0x18001ff83  mov     [rbp+260h+var_1A0], rax
0x18001ff8a  mov     [rbp+260h+var_198], r13b
0x18001ff91  lea     rax, ??_7CLogonController_DoModal_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLogonController_DoModal_Activity::`vftable'
0x18001ff98  mov     [rbp+260h+var_2E0], rax
0x18001ff9c  lea     rcx, [rsp+360h+var_2F8]; retstr
0x18001ffa1  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18001ffa6  movups  xmm0, xmmword ptr [rax]
0x18001ffa9  movdqu  [rsp+360h+Buf1], xmm0
0x18001ffaf  lea     r8d, [r13+10h]; Size
0x18001ffb3  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18001ffba  lea     rcx, [rsp+360h+Buf1]; Buf1
0x18001ffbf  call    memcmp_0
0x18001ffc4  test    eax, eax
0x18001ffc6  jz      short loc_18001FFD6
0x18001ffc8  lea     rdx, [rsp+360h+Buf1]
0x18001ffcd  lea     rcx, [rbp+260h+var_2E0]
0x18001ffd1  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18001ffd6  lea     rcx, [rbp+260h+var_2E0]; this
0x18001ffda  call    ?StartActivity@CLogonController_DoModal_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLogonController_DoModal_Activity::StartActivity(void)
0x18001ffdf  lea     rcx, [rbp+260h+var_190]; this
0x18001ffe6  call    ??$Start@$$V@ProcessStartup@LogonControllerTelemetry@@SA?AV01@XZ; LogonControllerTelemetry::ProcessStartup::Start<>(void)
0x18001ffeb  nop
0x18001ffec  lea     rcx, [rsp+360h+var_308]; this
0x18001fff1  call    ??0CDwmWnfDumpRequestListener@DwmWnfDiagnosticEvent@@QEAA@XZ; DwmWnfDiagnosticEvent::CDwmWnfDumpRequestListener::CDwmWnfDumpRequestListener(void)
0x18001fff6  lea     rax, ??_7CLogonDwmWnfDumpRequestListener@@6B@; const CLogonDwmWnfDumpRequestListener::`vftable'
0x18001fffd  mov     [rsp+360h+var_308], rax
0x180020002  call    cs:__imp_DXGIDeclareAdapterRemovalSupport
0x180020008  mov     rcx, [rbp+268h]; this
0x18002000f  test    eax, eax
0x180020011  jns     short loc_180020027
0x180020013  mov     r9d, eax; char *
0x180020016  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002001d  mov     edx, 15Fh; void *
0x180020022  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020027  lea     rbx, [rsi-8]
0x18002002b  call    cs:__imp_SHTaskPoolGetUniqueContext
0x180020031  mov     [rbx+0D0h], eax
0x180020037  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18002003d  mov     [rsi+0CCh], eax
0x180020043  call    ?DisableCursorSuppression@CImmersiveCursor@Shell@Windows@@SAXXZ; Windows::Shell::CImmersiveCursor::DisableCursorSuppression(void)
0x180020048  mov     [rsp+360h+var_30F], 1
0x18002004d  mov     r14d, [rbp+260h+arg_20]
0x180020054  mov     [rsp+360h+var_340], r14d; int
0x180020059  mov     r9d, r12d; unsigned int
0x18002005c  mov     r8d, r15d; unsigned int
0x18002005f  mov     edx, edi; unsigned int
0x180020061  mov     rcx, rbx; this
0x180020064  call    ?_Initialize@CLogonController@@AEAAJKKKK@Z; CLogonController::_Initialize(ulong,ulong,ulong,ulong)
0x180020069  mov     edi, eax
0x18002006b  test    eax, eax
0x18002006d  js      loc_18002043F
0x180020073  xor     r9d, r9d; lpName
0x180020076  xor     r8d, r8d; bInitialState
0x180020079  xor     edx, edx; bManualReset
0x18002007b  xor     ecx, ecx; lpEventAttributes
0x18002007d  call    cs:__imp_CreateEventW
0x180020083  mov     rdi, rax
0x180020086  mov     rcx, [rsi+148h]; hObject
0x18002008d  mov     [rsi+148h], r13
0x180020094  lea     rdx, [rcx-1]
0x180020098  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002009c  jbe     loc_18002062F
0x1800200a2  mov     [rsi+148h], rdi
0x1800200a9  test    rdi, rdi
0x1800200ac  jz      loc_18002063A
0x1800200b2  mov     [rsp+360h+var_328], r13
0x1800200b7  lea     rcx, [rsp+360h+var_328]
0x1800200bc  call    ??$MakeAndInitialize@VCServer@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCServer@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CServer,CServer,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CServer>>)
0x1800200c1  mov     edi, eax
0x1800200c3  test    eax, eax
0x1800200c5  jns     loc_1800201F8
0x1800200cb  mov     rcx, [rbp+268h]; this
0x1800200d2  mov     r9d, eax; char *
0x1800200d5  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800200dc  mov     edx, 179h; void *
0x1800200e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800200e6  nop
0x1800200e7  mov     rcx, [rsp+360h+var_328]
0x1800200ec  test    rcx, rcx
0x1800200ef  jz      short loc_180020103
0x1800200f1  mov     [rsp+360h+var_328], r13
0x1800200f6  mov     rax, [rcx]
0x1800200f9  mov     rax, [rax+10h]
0x1800200fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020102  nop
0x180020103  lea     r8, Name; "Global\\LogonUIExitEvent"
0x18002010a  xor     edx, edx; bInheritHandle
0x18002010c  lea     ecx, [rdx+2]; dwDesiredAccess
0x18002010f  call    cs:__imp_OpenEventW
0x180020115  mov     rbx, rax
0x180020118  lea     rcx, [rax-1]
0x18002011c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180020120  jbe     loc_180020659
0x180020126  lea     rcx, [rsp+360h+var_300]
0x18002012b  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180020130  nop
0x180020131  lea     rax, ??_7ProcessStartup@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::ProcessStartup::`vftable'
0x180020138  mov     [rbp+260h+var_190], rax
0x18002013f  cmp     [rbp+260h+var_78], r13
0x180020146  jnz     loc_180020528
0x18002014c  mov     rcx, [rbp+260h+var_80]
0x180020153  cmp     dword ptr [rcx], 1
0x180020156  jz      loc_180020680
0x18002015c  cmp     [rbp+260h+var_58], r13d
0x180020163  jnz     loc_180020696
0x180020169  lea     rcx, [rbp+260h+var_78]
0x180020170  call    ?reset@?$shared_object@V?$ActivityData@VLogonControllerLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180020175  lea     rcx, [rbp+260h+var_188]
0x18002017c  call    ??1?$ActivityData@VLogonControllerLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>(void)
0x180020181  nop
0x180020182  lea     rax, ??_7CLogonController_DoModal_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLogonController_DoModal_Activity::`vftable'
0x180020189  mov     [rbp+260h+var_2E0], rax
0x18002018d  cmp     [rbp+260h+var_1C8], r13
0x180020194  jnz     loc_18002056A
0x18002019a  mov     rcx, [rbp+260h+var_1D0]
0x1800201a1  cmp     dword ptr [rcx], 1
0x1800201a4  jz      loc_1800206B7
0x1800201aa  cmp     [rbp+260h+var_1A8], r13d
0x1800201b1  jnz     loc_1800206CA
0x1800201b7  lea     rcx, [rbp+260h+var_1C8]
0x1800201be  call    ?reset@?$shared_object@V?$ActivityData@VLogonControllerLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800201c3  lea     rcx, [rbp+260h+var_2D8]
0x1800201c7  call    ??1?$ActivityData@VLogonControllerLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800201cc  mov     eax, edi
0x1800201ce  mov     rcx, [rbp+260h+var_40]
0x1800201d5  xor     rcx, rsp; StackCookie
0x1800201d8  call    __security_check_cookie
0x1800201dd  mov     rbx, [rsp+360h+arg_8]
0x1800201e5  add     rsp, 330h
0x1800201ec  pop     r15
0x1800201ee  pop     r14
0x1800201f0  pop     r13
0x1800201f2  pop     r12
0x1800201f4  pop     rdi
0x1800201f5  pop     rsi
0x1800201f6  pop     rbp
0x1800201f7  retn
0x1800201f8  mov     qword ptr [rsp+360h+var_2F8.Data1], rbx
0x1800201fd  mov     [rsp+360h+var_2F8.Data4], 1
0x180020202  mov     rax, rbx
0x180020205  lea     r8, [rsi+18h]
0x180020209  neg     rax
0x18002020c  sbb     rdx, rdx
0x18002020f  and     rdx, r8; struct IWinLogonRPC *
0x180020212  mov     [rsp+360h+var_340], r14d; int
0x180020217  mov     r9d, r12d; unsigned int
0x18002021a  mov     r8d, r15d; unsigned int
0x18002021d  mov     rcx, [rsp+360h+var_328]; this
0x180020222  call    ?Start@CServer@@QEAAJPEAUIWinLogonRPC@@KKK@Z; CServer::Start(IWinLogonRPC *,ulong,ulong,ulong)
0x180020227  mov     edi, eax
0x180020229  test    eax, eax
0x18002022b  js      loc_1800206DB
0x180020231  lea     rcx, [rbp+260h+var_190]
0x180020238  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002023d  or      r14d, 0FFFFFFFFh
0x180020241  mov     edx, r14d; dwMilliseconds
0x180020244  mov     rcx, [rsi+148h]; hHandle
0x18002024b  call    cs:__imp_WaitForSingleObject
0x180020251  mov     rdi, [rsp+360h+var_328]
0x180020256  mov     edx, r14d; dwMilliseconds
0x180020259  mov     rcx, [rdi+58h]; hHandle
0x18002025d  call    cs:__imp_WaitForSingleObject
0x180020263  mov     rcx, [rdi+58h]; hObject
0x180020267  call    cs:__imp_CloseHandle
0x18002026d  cmp     cs:hEvent, r13
0x180020274  jz      short loc_1800202D0
0x180020276  mov     dword ptr [rsp+360h+var_330], r13d
0x18002027b  mov     eax, cs:?s_dwWnfState0@CServer@@0KA; ulong CServer::s_dwWnfState0
0x180020281  mov     dword ptr [rsp+360h+Buf1], eax
0x180020285  mov     eax, cs:?s_dwWnfState1@CServer@@0KA; ulong CServer::s_dwWnfState1
0x18002028b  mov     dword ptr [rsp+360h+Buf1+4], eax
0x18002028f  mov     qword ptr [rsp+360h+var_340], r13
0x180020294  mov     r9d, 4
0x18002029a  lea     r8, [rsp+360h+var_330]
0x18002029f  xor     edx, edx
0x1800202a1  mov     rcx, qword ptr [rsp+360h+Buf1]
0x1800202a6  call    cs:__imp_RtlPublishWnfStateData
0x1800202ac  mov     edx, r14d; dwMilliseconds
0x1800202af  mov     rcx, cs:hEvent; hHandle
0x1800202b6  call    cs:__imp_WaitForSingleObject
0x1800202bc  mov     rcx, cs:hEvent; hObject
0x1800202c3  call    cs:__imp_CloseHandle
0x1800202c9  mov     cs:hEvent, r13
0x1800202d0  cmp     cs:dword_1800D4124, r13d
0x1800202d7  jnz     loc_180020410
0x1800202dd  cmp     cs:BindingVector, r13
0x1800202e4  jnz     loc_1800204ED
0x1800202ea  cmp     cs:dword_1800D4120, r13d
0x1800202f1  jnz     loc_180020729
0x1800202f7  xor     edx, edx; Val
0x1800202f9  mov     r8d, 0E8h; Size
0x1800202ff  lea     rcx, xmmword_1800D4130; void *
0x180020306  call    memset_0
0x18002030b  nop
0x18002030c  call    ?DisableCursorSuppression@CImmersiveCursor@Shell@Windows@@SAXXZ; Windows::Shell::CImmersiveCursor::DisableCursorSuppression(void)
0x180020311  cmp     cs:byte_1800D3540, 1
0x180020318  jz      short loc_180020348
0x18002031a  mov     cs:byte_1800D3540, 1
0x180020321  mov     ecx, 13h; nIndex
0x180020326  call    cs:__imp_GetSystemMetrics
0x18002032c  test    eax, eax
0x18002032e  jz      short loc_180020348
0x180020330  mov     ecx, 1000h; nIndex
0x180020335  call    cs:__imp_GetSystemMetrics
0x18002033b  test    eax, eax
0x18002033d  jnz     short loc_180020348
0x18002033f  lea     ecx, [rax+1]; bShow
0x180020342  call    cs:__imp_ShowCursor
0x180020348  mov     rcx, rbx; this
0x18002034b  call    ?_Teardown@CLogonController@@AEAAJXZ; CLogonController::_Teardown(void)
0x180020350  nop
0x180020351  mov     rcx, [rsp+360h+var_328]
0x180020356  test    rcx, rcx
0x180020359  jz      short loc_18002036D
0x18002035b  mov     [rsp+360h+var_328], r13
0x180020360  mov     rax, [rcx]
0x180020363  mov     rax, [rax+10h]
0x180020367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002036c  nop
0x18002036d  lea     r8, Name; "Global\\LogonUIExitEvent"
0x180020374  xor     edx, edx; bInheritHandle
0x180020376  lea     ecx, [rdx+2]; dwDesiredAccess
0x180020379  call    cs:__imp_OpenEventW
0x18002037f  mov     rbx, rax
0x180020382  lea     rcx, [rax-1]
0x180020386  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002038a  jbe     loc_180020750
0x180020390  lea     rcx, [rbp+260h+var_2E0]
0x180020394  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180020399  nop
0x18002039a  lea     rcx, [rsp+360h+var_300]
0x18002039f  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800203a4  nop
0x1800203a5  lea     rax, ??_7ProcessStartup@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::ProcessStartup::`vftable'
0x1800203ac  mov     [rbp+260h+var_190], rax
0x1800203b3  lea     rcx, [rbp+260h+var_190]
0x1800203ba  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800203bf  nop
0x1800203c0  cmp     [rbp+260h+var_58], r13d
0x1800203c7  jnz     loc_180020767
0x1800203cd  lea     rcx, [rbp+260h+var_78]
0x1800203d4  call    ?reset@?$shared_object@V?$ActivityData@VLogonControllerLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800203d9  lea     rcx, [rbp+260h+var_188]
0x1800203e0  call    ??1?$ActivityData@VLogonControllerLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800203e5  nop
0x1800203e6  lea     rax, ??_7CLogonController_DoModal_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLogonController_DoModal_Activity::`vftable'
0x1800203ed  mov     [rbp+260h+var_2E0], rax
0x1800203f1  lea     rcx, [rbp+260h+var_2E0]
0x1800203f5  call    ?Destroy@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800203fa  nop
0x1800203fb  cmp     [rbp+260h+var_1A8], r13d
0x180020402  jnz     loc_180020778
0x180020408  mov     edi, r13d
0x18002040b  jmp     loc_1800201B7
0x180020410  lea     r8, UuidVector; UuidVector
0x180020417  mov     rdx, cs:BindingVector; BindingVector
  ... truncated ...
```
