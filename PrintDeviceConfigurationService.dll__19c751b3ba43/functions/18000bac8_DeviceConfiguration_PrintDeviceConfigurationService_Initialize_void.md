# DeviceConfiguration::PrintDeviceConfigurationService::Initialize(void)

- ea: `0x18000bac8`
- end: `0x18000bf4c`
- name: `?Initialize@PrintDeviceConfigurationService@DeviceConfiguration@@QEAAXXZ`
- size: `1156`
- prototype: `void __fastcall(DeviceConfiguration::WNFListener **this)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000abc0`

## callees

- `0x180002490`
- `0x1800024cc`
- `0x180002b28`
- `0x180004af8`
- `0x180005240`
- `0x18000a028`
- `0x18000a07c`
- `0x18000aeac`
- `0x18000af54`
- `0x18000b130`
- `0x18000b7f8`
- `0x18000b838`
- `0x18000b86c`
- `0x18000b884`
- `0x18000b8c4`
- `0x18000b8e0`
- `0x18000bac8`
- `0x18000c06c`
- `0x18000c13c`
- `0x18000c158`
- `0x18000c2e0`
- `0x18000c34c`
- `0x18000c384`
- `0x18000d668`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000bcb2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000bcb2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000be06`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000be06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be18`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bb42`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000bb42`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000be54`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18000be54`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000bb08`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000bb08`

## string_xrefs

- `0x18000bb01`: `PrintDeviceConfigurationService`
- `0x18000be81`: `PrintDeviceConfigurationService`
- `0x18000bae4`: `Initializing the Print Device Configuration Service...`
- `0x18000baeb`: `DeviceConfiguration::PrintDeviceConfigurationService::Initialize`
- `0x18000bf1e`: `DeviceConfiguration::PrintDeviceConfigurationService::Initialize`
- `0x18000bb15`: `RegisterServiceCtrlHandlerEx failed!`
- `0x18000bb24`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`
- `0x18000bb68`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`
- `0x18000bea6`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`
- `0x18000bb58`: `Failed to create the service stop timer!`
- `0x18000bf17`: `Print Device Configuration Service successfully initialized!`

## pseudocode

```c
void __fastcall DeviceConfiguration::PrintDeviceConfigurationService::Initialize(
        DeviceConfiguration::WNFListener **this)
{
  SERVICE_STATUS_HANDLE v2; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  unsigned int v4; // r8d
  int v5; // eax
  unsigned int v6; // r8d
  DeviceConfiguration::DeviceManager *v7; // rax
  __int64 v8; // rdi
  _DWORD *v9; // rbx
  std::_Ref_count_base *v10; // rcx
  DeviceConfiguration::ConfigurationManager *v11; // rax
  __int64 v12; // rdi
  char *v13; // rbx
  std::_Ref_count_base *v14; // rcx
  char *v15; // rdi
  _DWORD *v16; // rbx
  std::_Ref_count_base *v17; // rcx
  __int64 v18; // rbx
  __int64 *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // r8
  __int64 v22; // rdx
  std::_Ref_count_base *v23; // rcx
  __int64 v24; // rbx
  __int64 *v25; // rax
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rdx
  std::_Ref_count_base *v29; // rcx
  int v30; // eax
  unsigned int v31; // r8d
  void *v32; // rdx
  HANDLE Event; // rdi
  unsigned int v34; // r8d
  const char *v35; // r9
  __int64 (__fastcall *v36)(DeviceConfiguration::WNFListener **, const WCHAR *, DeviceConfiguration::WNFListener *, void (__fastcall *)(void *, unsigned __int8), DeviceConfiguration::WNFListener **, int); // r15
  DeviceConfiguration::WNFListener *v37; // r14
  DeviceConfiguration::WNFListener *v38; // rbx
  unsigned int v39; // eax
  DeviceConfiguration::PrintDeviceConfigurationService *v40; // rcx
  unsigned int v41; // r8d
  int v42; // eax
  unsigned int v43; // r8d
  unsigned int v44; // r8d
  int v45; // eax
  unsigned int v46; // r8d
  int v47; // [rsp+20h] [rbp-40h]
  int v48; // [rsp+20h] [rbp-40h]
  char *v49; // [rsp+28h] [rbp-38h]
  _BYTE v50[8]; // [rsp+40h] [rbp-20h] BYREF
  std::_Ref_count_base *v51; // [rsp+48h] [rbp-18h]
  _BYTE v52[8]; // [rsp+50h] [rbp-10h] BYREF
  std::_Ref_count_base *v53; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  char *v55; // [rsp+90h] [rbp+30h] BYREF

  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::PrintDeviceConfigurationService::Initialize",
    L"Initializing the Print Device Configuration Service...");
  v2 = RegisterServiceCtrlHandlerExW(
         L"PrintDeviceConfigurationService",
         DeviceConfiguration::PrintDeviceConfigurationService::s_ServiceControlHandlerCallback,
         this);
  *this = (DeviceConfiguration::WNFListener *)v2;
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
    retaddr,
    28,
    "printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
    v2,
    "RegisterServiceCtrlHandlerEx failed!");
  ThreadpoolTimer = CreateThreadpoolTimer(
                      DeviceConfiguration::PrintDeviceConfigurationService::s_StopTimerCallback,
                      this,
                      0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this + 3,
    ThreadpoolTimer);
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
    retaddr,
    32,
    "printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
    this[3],
    "Failed to create the service stop timer!");
  v5 = DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(
         (DeviceConfiguration::PrintDeviceConfigurationService *)this,
         2u,
         v4);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x22, v6, (const char *)(unsigned int)v5, v47);
  v7 = (DeviceConfiguration::DeviceManager *)operator new(0x18u);
  *(_OWORD *)v7 = 0;
  *((_QWORD *)v7 + 2) = 0;
  v8 = DeviceConfiguration::DeviceManager::DeviceManager(v7);
  v55 = (char *)v8;
  v9 = operator new(0x18u);
  *(_OWORD *)v9 = 0;
  v9[2] = 1;
  v9[3] = 1;
  *(_QWORD *)v9 = &std::_Ref_count<DeviceConfiguration::DeviceManager>::`vftable';
  *((_QWORD *)v9 + 2) = v8;
  v55 = 0;
  std::_Temporary_owner<DeviceConfiguration::DeviceManager>::~_Temporary_owner<DeviceConfiguration::DeviceManager>(&v55);
  this[15] = (DeviceConfiguration::WNFListener *)v8;
  v10 = this[16];
  this[16] = (DeviceConfiguration::WNFListener *)v9;
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  v11 = (DeviceConfiguration::ConfigurationManager *)operator new(1u);
  *(_BYTE *)v11 = 0;
  v12 = DeviceConfiguration::ConfigurationManager::ConfigurationManager(v11);
  v55 = (char *)v12;
  v13 = (char *)operator new(0x18u);
  v55 = v13;
  *(_OWORD *)v13 = 0;
  *((_DWORD *)v13 + 2) = 1;
  *((_DWORD *)v13 + 3) = 1;
  *(_QWORD *)v13 = &std::_Ref_count<DeviceConfiguration::ConfigurationManager>::`vftable';
  *((_QWORD *)v13 + 2) = v12;
  operator delete(0, 1u);
  this[17] = (DeviceConfiguration::WNFListener *)v12;
  v14 = this[18];
  this[18] = (DeviceConfiguration::WNFListener *)v13;
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  v15 = (char *)operator new(0x60u);
  memset_0(v15, 0, 0x60u);
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v15 + 48), 0, 0);
  std::atomic<bool>::atomic<bool>(v15 + 88);
  v55 = v15;
  v16 = operator new(0x18u);
  *(_OWORD *)v16 = 0;
  v16[2] = 1;
  v16[3] = 1;
  *(_QWORD *)v16 = &std::_Ref_count<DeviceConfiguration::WNFListener>::`vftable';
  *((_QWORD *)v16 + 2) = v15;
  v55 = 0;
  std::_Temporary_owner<DeviceConfiguration::WNFListener>::~_Temporary_owner<DeviceConfiguration::WNFListener>(&v55);
  this[19] = (DeviceConfiguration::WNFListener *)v15;
  v17 = this[20];
  this[20] = (DeviceConfiguration::WNFListener *)v16;
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  v18 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(
          v50,
          this + 15);
  v19 = (__int64 *)std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(
                     v52,
                     v18);
  v20 = *v19;
  *v19 = *v21;
  *v21 = v20;
  v22 = v19[1];
  v19[1] = v21[1];
  v21[1] = v22;
  if ( v53 )
    std::_Ref_count_base::_Decref(v53);
  v23 = *(std::_Ref_count_base **)(v18 + 8);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v24 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(
          v52,
          this + 17);
  v25 = (__int64 *)std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(
                     v50,
                     v24);
  v27 = *v25;
  *v25 = *(_QWORD *)(v26 + 24);
  *(_QWORD *)(v26 + 24) = v27;
  v28 = v25[1];
  v25[1] = *(_QWORD *)(v26 + 32);
  *(_QWORD *)(v26 + 32) = v28;
  if ( v51 )
    std::_Ref_count_base::_Decref(v51);
  v29 = *(std::_Ref_count_base **)(v24 + 8);
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
  v30 = DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(
          (DeviceConfiguration::PrintDeviceConfigurationService *)this,
          2u,
          v26);
  if ( v30 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x2B, v31, (const char *)(unsigned int)v30, v47);
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v32, v34, v35);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    this + 1,
    Event);
  v36 = (__int64 (__fastcall *)(DeviceConfiguration::WNFListener **, const WCHAR *, DeviceConfiguration::WNFListener *, void (__fastcall *)(void *, unsigned __int8), DeviceConfiguration::WNFListener **, int))*((_QWORD *)g_svchostSharedGlobals + 24);
  v37 = this[1];
  v38 = this[2];
  if ( v38 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v55);
    UnregisterWait(v38);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v55);
  }
  this[2] = 0;
  v39 = v36(
          this + 2,
          L"PrintDeviceConfigurationService",
          v37,
          DeviceConfiguration::PrintDeviceConfigurationService::s_StopCallback,
          this,
          8);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x2F,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
    (const char *)v39,
    (unsigned int)"RegisterStopCallback failed!",
    v49);
  *((_DWORD *)this + 8) = DeviceConfiguration::PrintDeviceConfigurationService::_GetMinimumLifetimeInMs(v40);
  DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer((DeviceConfiguration::PrintDeviceConfigurationService *)this);
  v42 = DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(
          (DeviceConfiguration::PrintDeviceConfigurationService *)this,
          2u,
          v41);
  if ( v42 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x35, v43, (const char *)(unsigned int)v42, v48);
  DeviceConfiguration::WNFListener::SubscribeToWNFNotifications(this[19]);
  v45 = DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(
          (DeviceConfiguration::PrintDeviceConfigurationService *)this,
          4u,
          v44);
  if ( v45 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x3A, v46, (const char *)(unsigned int)v45, v48);
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::PrintDeviceConfigurationService::Initialize",
    L"Print Device Configuration Service successfully initialized!");
}

```

## disassembly

```asm
0x18000bac8  mov     [rsp-28h+arg_8], rbx
0x18000bacd  mov     [rsp-28h+arg_10], rsi
0x18000bad2  push    rbp
0x18000bad3  push    rdi
0x18000bad4  push    r13
0x18000bad6  push    r14
0x18000bad8  push    r15
0x18000bada  mov     rbp, rsp
0x18000badd  sub     rsp, 60h
0x18000bae1  mov     rsi, rcx
0x18000bae4  lea     rdx, aInitializingTh; "Initializing the Print Device Configura"...
0x18000baeb  lea     rcx, aDeviceconfigur_13; "DeviceConfiguration::PrintDeviceConfigu"...
0x18000baf2  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000baf7  mov     r8, rsi; lpContext
0x18000bafa  lea     rdx, ?s_ServiceControlHandlerCallback@PrintDeviceConfigurationService@DeviceConfiguration@@CAKKKPEAX0@Z; lpHandlerProc
0x18000bb01  lea     rcx, ServiceName; "PrintDeviceConfigurationService"
0x18000bb08  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000bb0e  mov     [rsi], rax
0x18000bb11  mov     rcx, [rbp+28h]
0x18000bb15  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandlerEx failed!"
0x18000bb1c  mov     qword ptr [rsp+60h+var_40], rdx
0x18000bb21  mov     r9, rax
0x18000bb24  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x18000bb2b  mov     edx, 1Ch
0x18000bb30  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x18000bb35  xor     r8d, r8d; pcbe
0x18000bb38  mov     rdx, rsi; pv
0x18000bb3b  lea     rcx, ?s_StopTimerCallback@PrintDeviceConfigurationService@DeviceConfiguration@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000bb42  call    cs:__imp_CreateThreadpoolTimer
0x18000bb48  mov     rdx, rax
0x18000bb4b  lea     rcx, [rsi+18h]
0x18000bb4f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000bb54  mov     rcx, [rbp+28h]
0x18000bb58  lea     rax, aFailedToCreate_3; "Failed to create the service stop timer"...
0x18000bb5f  mov     qword ptr [rsp+60h+var_40], rax; int
0x18000bb64  mov     r9, [rsi+18h]
0x18000bb68  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x18000bb6f  mov     edx, 20h ; ' '
0x18000bb74  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x18000bb79  mov     edx, 2; unsigned int
0x18000bb7e  mov     rcx, rsi; this
0x18000bb81  call    ?_ReportServiceStatus@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAJKK@Z; DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(ulong,ulong)
0x18000bb86  mov     rcx, [rbp+28h]; this
0x18000bb8a  test    eax, eax
0x18000bb8c  jns     short loc_18000BB9B
0x18000bb8e  mov     r9d, eax; char *
0x18000bb91  mov     edx, 22h ; '"'; void *
0x18000bb96  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bb9b  mov     ebx, 18h
0x18000bba0  mov     ecx, ebx; Size
0x18000bba2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bba7  xorps   xmm0, xmm0
0x18000bbaa  xor     ecx, ecx
0x18000bbac  movups  xmmword ptr [rax], xmm0
0x18000bbaf  mov     [rax+10h], rcx
0x18000bbb3  mov     rcx, rax; this
0x18000bbb6  call    ??0DeviceManager@DeviceConfiguration@@QEAA@XZ; DeviceConfiguration::DeviceManager::DeviceManager(void)
0x18000bbbb  mov     rdi, rax
0x18000bbbe  mov     [rbp+arg_0], rax
0x18000bbc2  mov     ecx, ebx; Size
0x18000bbc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bbc9  mov     rbx, rax
0x18000bbcc  mov     [rbp+arg_0], rax
0x18000bbd0  xorps   xmm0, xmm0
0x18000bbd3  movups  xmmword ptr [rax], xmm0
0x18000bbd6  mov     r13d, 1
0x18000bbdc  mov     [rax+8], r13d
0x18000bbe0  mov     [rax+0Ch], r13d
0x18000bbe4  lea     rax, ??_7?$_Ref_count@VDeviceManager@DeviceConfiguration@@@std@@6B@; const std::_Ref_count<DeviceConfiguration::DeviceManager>::`vftable'
0x18000bbeb  mov     [rbx], rax
0x18000bbee  mov     [rbx+10h], rdi
0x18000bbf2  mov     [rbp+arg_0], 0
0x18000bbfa  lea     rcx, [rbp+arg_0]
0x18000bbfe  call    ??1?$_Temporary_owner@VDeviceManager@DeviceConfiguration@@@std@@QEAA@XZ; std::_Temporary_owner<DeviceConfiguration::DeviceManager>::~_Temporary_owner<DeviceConfiguration::DeviceManager>(void)
0x18000bc03  mov     [rsi+78h], rdi
0x18000bc07  mov     rcx, [rsi+80h]; this
0x18000bc0e  mov     [rsi+80h], rbx
0x18000bc15  test    rcx, rcx
0x18000bc18  jz      short loc_18000BC1F
0x18000bc1a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bc1f  lea     r15, [rsi+88h]
0x18000bc26  mov     rcx, r13; Size
0x18000bc29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc2e  xor     ecx, ecx
0x18000bc30  mov     [rax], cl
0x18000bc32  mov     rcx, rax; this
0x18000bc35  call    ??0ConfigurationManager@DeviceConfiguration@@QEAA@XZ; DeviceConfiguration::ConfigurationManager::ConfigurationManager(void)
0x18000bc3a  mov     rdi, rax
0x18000bc3d  mov     [rbp+arg_0], rax
0x18000bc41  mov     ecx, 18h; Size
0x18000bc46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc4b  mov     rbx, rax
0x18000bc4e  mov     [rbp+arg_0], rax
0x18000bc52  xorps   xmm0, xmm0
0x18000bc55  movups  xmmword ptr [rax], xmm0
0x18000bc58  mov     [rax+8], r13d
0x18000bc5c  mov     [rax+0Ch], r13d
0x18000bc60  lea     rax, ??_7?$_Ref_count@VConfigurationManager@DeviceConfiguration@@@std@@6B@; const std::_Ref_count<DeviceConfiguration::ConfigurationManager>::`vftable'
0x18000bc67  mov     [rbx], rax
0x18000bc6a  mov     [rbx+10h], rdi
0x18000bc6e  mov     rdx, r13; unsigned __int64
0x18000bc71  xor     ecx, ecx; void *
0x18000bc73  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bc78  mov     [r15], rdi
0x18000bc7b  mov     rcx, [r15+8]; this
0x18000bc7f  mov     [r15+8], rbx
0x18000bc83  test    rcx, rcx
0x18000bc86  jz      short loc_18000BC8D
0x18000bc88  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bc8d  mov     ebx, 60h ; '`'
0x18000bc92  mov     ecx, ebx; Size
0x18000bc94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc99  mov     rdi, rax
0x18000bc9c  mov     r8d, ebx; Size
0x18000bc9f  xor     edx, edx; Val
0x18000bca1  mov     rcx, rax; void *
0x18000bca4  call    memset_0
0x18000bca9  lea     rcx, [rdi+30h]; lpCriticalSection
0x18000bcad  xor     r8d, r8d; Flags
0x18000bcb0  xor     edx, edx; dwSpinCount
0x18000bcb2  call    cs:__imp_InitializeCriticalSectionEx
0x18000bcb8  lea     rcx, [rdi+58h]
0x18000bcbc  call    ??$?0_N$0A@@?$atomic@_N@std@@QEAA@XZ; std::atomic<bool>::atomic<bool>(void)
0x18000bcc1  mov     [rbp+arg_0], rdi
0x18000bcc5  lea     ecx, [rbx-48h]; Size
0x18000bcc8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bccd  mov     rbx, rax
0x18000bcd0  mov     [rbp+arg_0], rax
0x18000bcd4  xorps   xmm0, xmm0
0x18000bcd7  movups  xmmword ptr [rax], xmm0
0x18000bcda  mov     [rax+8], r13d
0x18000bcde  mov     [rax+0Ch], r13d
0x18000bce2  lea     rax, ??_7?$_Ref_count@VWNFListener@DeviceConfiguration@@@std@@6B@; const std::_Ref_count<DeviceConfiguration::WNFListener>::`vftable'
0x18000bce9  mov     [rbx], rax
0x18000bcec  mov     [rbx+10h], rdi
0x18000bcf0  mov     [rbp+arg_0], 0
0x18000bcf8  lea     rcx, [rbp+arg_0]
0x18000bcfc  call    ??1?$_Temporary_owner@VWNFListener@DeviceConfiguration@@@std@@QEAA@XZ; std::_Temporary_owner<DeviceConfiguration::WNFListener>::~_Temporary_owner<DeviceConfiguration::WNFListener>(void)
0x18000bd01  mov     [rsi+98h], rdi
0x18000bd08  mov     rcx, [rsi+0A0h]; this
0x18000bd0f  mov     [rsi+0A0h], rbx
0x18000bd16  test    rcx, rcx
0x18000bd19  jz      short loc_18000BD20
0x18000bd1b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bd20  mov     r8, [rsi+98h]
0x18000bd27  lea     rdx, [rsi+78h]
0x18000bd2b  lea     rcx, [rbp+var_20]
0x18000bd2f  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x18000bd34  mov     rbx, rax
0x18000bd37  mov     rdx, rax
0x18000bd3a  lea     rcx, [rbp+var_10]
0x18000bd3e  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x18000bd43  mov     rdx, [rax]
0x18000bd46  mov     rcx, [r8]
0x18000bd49  mov     [rax], rcx
0x18000bd4c  mov     [r8], rdx
0x18000bd4f  mov     rdx, [rax+8]
0x18000bd53  mov     rcx, [r8+8]
0x18000bd57  mov     [rax+8], rcx
0x18000bd5b  mov     [r8+8], rdx
0x18000bd5f  mov     rcx, [rbp+var_8]; this
0x18000bd63  test    rcx, rcx
0x18000bd66  jz      short loc_18000BD6D
0x18000bd68  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bd6d  mov     rcx, [rbx+8]; this
0x18000bd71  test    rcx, rcx
0x18000bd74  jz      short loc_18000BD7B
0x18000bd76  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bd7b  mov     r8, [rsi+98h]
0x18000bd82  mov     rdx, r15
0x18000bd85  lea     rcx, [rbp+var_10]
0x18000bd89  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x18000bd8e  mov     rbx, rax
0x18000bd91  mov     rdx, rax
0x18000bd94  lea     rcx, [rbp+var_20]
0x18000bd98  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x18000bd9d  mov     rdx, [rax]
0x18000bda0  mov     rcx, [r8+18h]
0x18000bda4  mov     [rax], rcx
0x18000bda7  mov     [r8+18h], rdx
0x18000bdab  mov     rdx, [rax+8]
0x18000bdaf  mov     rcx, [r8+20h]
0x18000bdb3  mov     [rax+8], rcx
0x18000bdb7  mov     [r8+20h], rdx
0x18000bdbb  mov     rcx, [rbp+var_18]; this
0x18000bdbf  test    rcx, rcx
0x18000bdc2  jz      short loc_18000BDC9
0x18000bdc4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bdc9  mov     rcx, [rbx+8]; this
0x18000bdcd  test    rcx, rcx
0x18000bdd0  jz      short loc_18000BDD7
0x18000bdd2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000bdd7  mov     edx, 2; unsigned int
0x18000bddc  mov     rcx, rsi; this
0x18000bddf  call    ?_ReportServiceStatus@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAJKK@Z; DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(ulong,ulong)
0x18000bde4  test    eax, eax
0x18000bde6  jns     short loc_18000BDF9
0x18000bde8  mov     rcx, [rbp+28h]; this
0x18000bdec  mov     r9d, eax; char *
0x18000bdef  mov     edx, 2Bh ; '+'; void *
0x18000bdf4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bdf9  mov     r9d, 1F0003h; dwDesiredAccess
0x18000bdff  mov     r8d, r13d; dwFlags
0x18000be02  xor     edx, edx; lpName
0x18000be04  xor     ecx, ecx; lpEventAttributes
0x18000be06  call    cs:__imp_CreateEventExW
0x18000be0c  mov     rdi, rax
0x18000be0f  test    rax, rax
0x18000be12  jz      loc_18000BF42
0x18000be18  call    cs:__imp_GetLastError
0x18000be1e  mov     rdx, rdi
0x18000be21  lea     rcx, [rsi+8]
0x18000be25  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000be2a  mov     rax, cs:?g_svchostSharedGlobals@@3PEBU_SVCHOST_GLOBAL_DATA@@EB; _SVCHOST_GLOBAL_DATA const * const g_svchostSharedGlobals
0x18000be31  mov     r15, [rax+0C0h]
0x18000be38  mov     r14, [rsi+8]
0x18000be3c  lea     rdi, [rsi+10h]
0x18000be40  mov     rbx, [rdi]
0x18000be43  test    rbx, rbx
0x18000be46  jz      short loc_18000BE63
0x18000be48  lea     rcx, [rbp+arg_0]; this
0x18000be4c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000be51  mov     rcx, rbx; WaitHandle
0x18000be54  call    cs:__imp_UnregisterWait
0x18000be5a  lea     rcx, [rbp+arg_0]; this
0x18000be5e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000be63  mov     qword ptr [rdi], 0
0x18000be6a  mov     dword ptr [rsp+60h+var_38], 8; char *
0x18000be72  mov     qword ptr [rsp+60h+var_40], rsi
0x18000be77  lea     r9, ?s_StopCallback@PrintDeviceConfigurationService@DeviceConfiguration@@CAXPEAXE@Z; DeviceConfiguration::PrintDeviceConfigurationService::s_StopCallback(void *,uchar)
0x18000be7e  mov     r8, r14
0x18000be81  lea     rdx, ServiceName; "PrintDeviceConfigurationService"
0x18000be88  mov     rcx, rdi
0x18000be8b  mov     rax, r15
0x18000be8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be93  mov     r9d, eax; char *
0x18000be96  mov     rcx, [rbp+28h]; this
0x18000be9a  lea     rax, aRegisterstopca; "RegisterStopCallback failed!"
0x18000bea1  mov     qword ptr [rsp+60h+var_40], rax; int
0x18000bea6  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x18000bead  mov     edx, 2Fh ; '/'; void *
0x18000beb2  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18000beb7  call    ?_GetMinimumLifetimeInMs@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAKXZ; DeviceConfiguration::PrintDeviceConfigurationService::_GetMinimumLifetimeInMs(void)
0x18000bebc  mov     [rsi+20h], eax
0x18000bebf  mov     rcx, rsi; this
0x18000bec2  call    ?ResetStopTimer@PrintDeviceConfigurationService@DeviceConfiguration@@QEAAXXZ; DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer(void)
0x18000bec7  mov     edx, 2; unsigned int
0x18000becc  mov     rcx, rsi; this
0x18000becf  call    ?_ReportServiceStatus@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAJKK@Z; DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(ulong,ulong)
0x18000bed4  test    eax, eax
0x18000bed6  jns     short loc_18000BEE9
0x18000bed8  mov     rcx, [rbp+28h]; this
0x18000bedc  mov     r9d, eax; char *
0x18000bedf  mov     edx, 35h ; '5'; void *
0x18000bee4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bee9  mov     rcx, [rsi+98h]; this
0x18000bef0  call    ?SubscribeToWNFNotifications@WNFListener@DeviceConfiguration@@QEAAXXZ; DeviceConfiguration::WNFListener::SubscribeToWNFNotifications(void)
0x18000bef5  mov     edx, 4; unsigned int
0x18000befa  mov     rcx, rsi; this
0x18000befd  call    ?_ReportServiceStatus@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAJKK@Z; DeviceConfiguration::PrintDeviceConfigurationService::_ReportServiceStatus(ulong,ulong)
0x18000bf02  test    eax, eax
0x18000bf04  jns     short loc_18000BF17
0x18000bf06  mov     rcx, [rbp+28h]; this
0x18000bf0a  mov     r9d, eax; char *
0x18000bf0d  mov     edx, 3Ah ; ':'; void *
0x18000bf12  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bf17  lea     rdx, aPrintDeviceCon; "Print Device Configuration Service succ"...
0x18000bf1e  lea     rcx, aDeviceconfigur_13; "DeviceConfiguration::PrintDeviceConfigu"...
0x18000bf25  lea     r11, [rsp+60h+var_s0]
0x18000bf2a  mov     rbx, [r11+38h]
0x18000bf2e  mov     rsi, [r11+40h]
0x18000bf32  mov     rsp, r11
0x18000bf35  pop     r15
0x18000bf37  pop     r14
0x18000bf39  pop     r13
0x18000bf3b  pop     rdi
0x18000bf3c  pop     rbp
0x18000bf3d  jmp     ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000bf42  mov     rcx, [rbp+28h]; this
0x18000bf46  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
