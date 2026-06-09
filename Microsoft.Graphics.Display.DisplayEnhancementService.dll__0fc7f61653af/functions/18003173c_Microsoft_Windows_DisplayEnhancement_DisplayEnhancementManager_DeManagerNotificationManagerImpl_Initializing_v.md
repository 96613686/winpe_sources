# Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl::Initializing(void)

- ea: `0x18003173c`
- end: `0x180031c3e`
- name: `?Initializing@DeManagerNotificationManagerImpl@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@QEAAXXZ`
- size: `1282`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180031c44`

## callees

- `0x180005860`
- `0x180007c0c`
- `0x180009904`
- `0x180009b3c`
- `0x180009f68`
- `0x18000f778`
- `0x18000f9f0`
- `0x18000fb14`
- `0x18000ffe0`
- `0x180011704`
- `0x180013138`
- `0x18001c3ac`
- `0x18001c404`
- `0x18002ecb0`
- `0x18002ed10`
- `0x18002ed30`
- `0x18002ed80`
- `0x18003173c`
- `0x180063c54`
- `0x18009830c`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003184e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003185f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031942`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031952`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031a34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031a45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031b24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031b35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003184e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003185f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031942`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031952`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031a34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031a45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031b24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031b35`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031889`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003197c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031a6f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031b5f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031889`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003197c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031a6f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180031b5f`

## string_xrefs

- `0x180031781`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanager\lib\demanagernotificationmanager.cpp`
- `0x1800317f8`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanager\lib\demanagernotificationmanager.cpp`
- `0x180031893`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanager\lib\demanagernotificationmanager.cpp`
- `0x180031986`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanager\lib\demanagernotificationmanager.cpp`
- `0x180031a79`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanager\lib\demanagernotificationmanager.cpp`
- `0x180031b69`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanager\lib\demanagernotificationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl::Initializing(
        struct SmFx::StateMachineEngine::StateMachineEngineImpl **this,
        __int64 a2,
        __int64 a3)
{
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v5; // eax
  HANDLE CurrentProcess; // rdi
  void *v7; // rbx
  HANDLE v8; // rax
  const char *v9; // r9
  struct SmFx::StateMachineEngine::StateMachineEngineImpl *v10; // rcx
  __int64 v11; // rax
  __int64 *v12; // rax
  HANDLE v13; // rdi
  void *v14; // rbx
  HANDLE v15; // rax
  const char *v16; // r9
  struct SmFx::StateMachineEngine::StateMachineEngineImpl *v17; // rcx
  __int64 v18; // rax
  __int64 *v19; // rax
  HANDLE v20; // rdi
  void *v21; // rbx
  HANDLE v22; // rax
  const char *v23; // r9
  struct SmFx::StateMachineEngine::StateMachineEngineImpl *v24; // rcx
  __int64 v25; // rax
  __int64 *v26; // rax
  HANDLE v27; // rdi
  void *v28; // rbx
  HANDLE v29; // rax
  const char *v30; // r9
  struct SmFx::StateMachineEngine::StateMachineEngineImpl *v31; // rcx
  __int64 v32; // rax
  __int64 *v33; // rax
  __int64 v34; // rax
  __int64 *Shared; // rax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  HANDLE TargetHandle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v38; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v39[8]; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v40; // [rsp+58h] [rbp-A8h]
  _QWORD v41[6]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v42; // [rsp+90h] [rbp-70h]
  int v43; // [rsp+92h] [rbp-6Eh]
  __int16 v44; // [rsp+96h] [rbp-6Ah]
  _BYTE v45[120]; // [rsp+98h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 55, 1, a3);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanager\\lib\\demanagernotificationmanager.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      dwDesiredAccess);
  v43 = 0;
  v44 = 0;
  v41[0] = &Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::GeneratedStateMachines::DeManagerStateMachine<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::c_specification;
  v41[1] = this;
  v42 = 257;
  v41[2] = Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::GeneratedStateMachines::DeManagerStateMachine<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::EvtLogMachineExceptionThunk;
  v41[3] = Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::GeneratedStateMachines::DeManagerStateMachine<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::EvtLogEventEnqueueThunk;
  v41[4] = Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::GeneratedStateMachines::DeManagerStateMachine<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::EvtLogTransitionThunk;
  v41[5] = Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::GeneratedStateMachines::DeManagerStateMachine<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::EvtMachineDestroyedThunk;
  v5 = SmFx::StateMachineEngine::StateMachineEngineImpl::MakeAndInitialize(
         (const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *)v41,
         this);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanager\\lib\\demanagernotificationmanager.cpp",
      (const char *)(unsigned int)v5,
      dwDesiredAccess);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v38, (__int64)this);
  wistd::function_void___cdecl_void__::function_void___cdecl_void____lambda_bd4f2aaa049b215157f55c33c1358936__void_(
    v45,
    v38);
  wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
    this + 8,
    v45);
  wistd::function<void (unsigned char const &)>::~function<void (unsigned char const &)>(v45);
  TargetHandle = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &TargetHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  v7 = (void *)*((_QWORD *)this[8] + 15);
  v8 = GetCurrentProcess();
  if ( !DuplicateHandle(v8, v7, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanager\\lib\\demanagernotificationmanager.cpp",
      v9);
  v10 = this[4];
  v11 = *(_QWORD *)v10;
  v38 = TargetHandle;
  TargetHandle = 0;
  v12 = (__int64 *)(*(__int64 (__fastcall **)(struct SmFx::StateMachineEngine::StateMachineEngineImpl *, _BYTE *, HANDLE *))(v11 + 536))(
                     v10,
                     v39,
                     &v38);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 9,
    v12);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&TargetHandle);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v38, (__int64)this);
  wistd::function_void___cdecl_void__::function_void___cdecl_void____lambda_08916717245842905d91babd18e52812__void_(
    v45,
    v38);
  wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
    this + 18,
    v45);
  wistd::function<void (unsigned char const &)>::~function<void (unsigned char const &)>(v45);
  TargetHandle = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &TargetHandle,
    0);
  v13 = GetCurrentProcess();
  v14 = (void *)*((_QWORD *)this[18] + 15);
  v15 = GetCurrentProcess();
  if ( !DuplicateHandle(v15, v14, v13, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanager\\lib\\demanagernotificationmanager.cpp",
      v16);
  v17 = this[4];
  v18 = *(_QWORD *)v17;
  v38 = TargetHandle;
  TargetHandle = 0;
  v19 = (__int64 *)(*(__int64 (__fastcall **)(struct SmFx::StateMachineEngine::StateMachineEngineImpl *, _BYTE *, HANDLE *))(v18 + 416))(
                     v17,
                     v39,
                     &v38);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 19,
    v19);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&TargetHandle);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v38, (__int64)this);
  wistd::function_void___cdecl_void__::function_void___cdecl_void____lambda_5dc1d4f8ee6fda12c4970d1ae3e56e45__void_(
    v45,
    v38);
  wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
    this + 12,
    v45);
  wistd::function<void (unsigned char const &)>::~function<void (unsigned char const &)>(v45);
  TargetHandle = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &TargetHandle,
    0);
  v20 = GetCurrentProcess();
  v21 = (void *)*((_QWORD *)this[12] + 15);
  v22 = GetCurrentProcess();
  if ( !DuplicateHandle(v22, v21, v20, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanager\\lib\\demanagernotificationmanager.cpp",
      v23);
  v24 = this[4];
  v25 = *(_QWORD *)v24;
  v38 = TargetHandle;
  TargetHandle = 0;
  v26 = (__int64 *)(*(__int64 (__fastcall **)(struct SmFx::StateMachineEngine::StateMachineEngineImpl *, _BYTE *, HANDLE *))(v25 + 128))(
                     v24,
                     v39,
                     &v38);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 13,
    v26);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&TargetHandle);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v38, (__int64)this);
  wistd::function_void___cdecl_void__::function_void___cdecl_void____lambda_8694b62541581ff6870704328c8150a7__void_(
    v45,
    v38);
  wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
    this + 15,
    v45);
  wistd::function<void (unsigned char const &)>::~function<void (unsigned char const &)>(v45);
  TargetHandle = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &TargetHandle,
    0);
  v27 = GetCurrentProcess();
  v28 = (void *)*((_QWORD *)this[15] + 15);
  v29 = GetCurrentProcess();
  if ( !DuplicateHandle(v29, v28, v27, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanager\\lib\\demanagernotificationmanager.cpp",
      v30);
  v31 = this[4];
  v32 = *(_QWORD *)v31;
  v38 = TargetHandle;
  TargetHandle = 0;
  v33 = (__int64 *)(*(__int64 (__fastcall **)(struct SmFx::StateMachineEngine::StateMachineEngineImpl *, _BYTE *, HANDLE *))(v32 + 296))(
                     v31,
                     v39,
                     &v38);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 16,
    v33);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&TargetHandle);
  v34 = (*(__int64 (__fastcall **)(struct SmFx::StateMachineEngine::StateMachineEngineImpl *, _QWORD *))(*(_QWORD *)this[62] + 16LL))(
          this[62],
          v41);
  Shared = (__int64 *)Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(v39, v34);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    this + 60,
    Shared);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  std::wstring::_Tidy_deallocate(v41);
}

```

## disassembly

```asm
0x18003173c  push    rbp
0x18003173e  push    rbx
0x18003173f  push    rsi
0x180031740  push    rdi
0x180031741  push    r14
0x180031743  push    r15
0x180031745  lea     rbp, [rsp-28h]
0x18003174a  sub     rsp, 128h
0x180031751  mov     rax, cs:__security_cookie
0x180031758  xor     rax, rsp
0x18003175b  mov     [rbp+50h+var_40], rax
0x18003175f  mov     rsi, rcx
0x180031762  add     rcx, 1B8h
0x180031769  mov     edx, 1
0x18003176e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180031773  mov     rcx, [rbp+58h]; this
0x180031777  xor     r15d, r15d
0x18003177a  test    eax, eax
0x18003177c  jns     short loc_180031792
0x18003177e  mov     r9d, eax; char *
0x180031781  lea     r8, aOnecoreuapDriv_18; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180031788  lea     edx, [r15+4Eh]; void *
0x18003178c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031792  mov     [rbp+50h+var_BE], r15d
0x180031796  mov     [rbp+50h+var_BA], r15w
0x18003179b  lea     rax, ?c_specification@?$DeManagerStateMachine@VDeManagerNotificationManagerImpl@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@0USTATE_MACHINE_SPECIFICATION@SmFx@@B; SmFx::STATE_MACHINE_SPECIFICATION const Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::GeneratedStateMachines::DeManagerStateMachine<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::c_specification
0x1800317a2  mov     [rsp+150h+var_F0], rax
0x1800317a7  mov     [rsp+150h+var_E8], rsi
0x1800317ac  mov     [rbp+50h+var_C0], 101h
0x1800317b2  lea     rax, ?EvtLogMachineExceptionThunk@?$DeManagerStateMachine@VDeManagerNotificationManagerImpl@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@CAXPEAXW4MachineException@SmFx@@GG@Z; Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::GeneratedStateMachines::DeManagerStateMachine<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::EvtLogMachineExceptionThunk(void *,SmFx::MachineException,ushort,ushort)
0x1800317b9  mov     [rsp+150h+var_E0], rax
0x1800317be  lea     rax, ?EvtLogEventEnqueueThunk@?$DeManagerStateMachine@VDeManagerNotificationManagerImpl@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@CAXPEAXG@Z; Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::GeneratedStateMachines::DeManagerStateMachine<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::EvtLogEventEnqueueThunk(void *,ushort)
0x1800317c5  mov     [rsp+150h+var_D8], rax
0x1800317ca  lea     rax, ?EvtLogTransitionThunk@?$DeManagerStateMachine@VDeManagerNotificationManagerImpl@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@CAXPEAXW4TransitionType@SmFx@@GGG@Z; Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::GeneratedStateMachines::DeManagerStateMachine<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::EvtLogTransitionThunk(void *,SmFx::TransitionType,ushort,ushort,ushort)
0x1800317d1  mov     [rbp+50h+var_D0], rax
0x1800317d5  lea     rax, ?EvtMachineDestroyedThunk@?$DeManagerStateMachine@VDeManagerNotificationManagerImpl@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@DisplayEnhancementManager@DisplayEnhancement@Windows@Microsoft@@CAXPEAX@Z; Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::GeneratedStateMachines::DeManagerStateMachine<Microsoft::Windows::DisplayEnhancement::DisplayEnhancementManager::DeManagerNotificationManagerImpl>::EvtMachineDestroyedThunk(void *)
0x1800317dc  mov     [rbp+50h+var_C8], rax
0x1800317e0  mov     rdx, rsi; struct SmFx::StateMachineEngine::StateMachineEngineImpl **
0x1800317e3  lea     rcx, [rsp+150h+var_F0]; struct SmFx::STATE_MACHINE_ENGINE_CONFIG *
0x1800317e8  call    ?MakeAndInitialize@StateMachineEngineImpl@StateMachineEngine@SmFx@@SAJAEBUSTATE_MACHINE_ENGINE_CONFIG@3@PEAPEAV123@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::MakeAndInitialize(SmFx::STATE_MACHINE_ENGINE_CONFIG const &,SmFx::StateMachineEngine::StateMachineEngineImpl * *)
0x1800317ed  mov     rcx, [rbp+58h]; this
0x1800317f1  test    eax, eax
0x1800317f3  jns     short loc_18003180A
0x1800317f5  mov     r9d, eax; char *
0x1800317f8  lea     r8, aOnecoreuapDriv_18; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800317ff  mov     edx, 51h ; 'Q'; void *
0x180031804  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18003180a  mov     rdx, rsi
0x18003180d  lea     rcx, [rsp+150h+var_108]
0x180031812  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180031817  mov     rdx, [rsp+150h+var_108]
0x18003181c  lea     rcx, [rbp+50h+var_B8]
0x180031820  call    wistd__function_void___cdecl_void____function_void___cdecl_void____lambda_bd4f2aaa049b215157f55c33c1358936__void_
0x180031825  nop
0x180031826  lea     rdx, [rbp+50h+var_B8]
0x18003182a  lea     rcx, [rsi+40h]
0x18003182e  call    ?create@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(wistd::function<void (void)> &&)
0x180031833  nop
0x180031834  lea     rcx, [rbp+50h+var_B8]
0x180031838  call    ??1?$function@$$A6AXAEBE@Z@wistd@@QEAA@XZ; wistd::function<void (uchar const &)>::~function<void (uchar const &)>(void)
0x18003183d  mov     [rsp+150h+TargetHandle], r15
0x180031842  xor     edx, edx
0x180031844  lea     rcx, [rsp+150h+TargetHandle]
0x180031849  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003184e  call    cs:__imp_GetCurrentProcess
0x180031854  mov     rdi, rax
0x180031857  mov     rcx, [rsi+40h]
0x18003185b  mov     rbx, [rcx+78h]
0x18003185f  call    cs:__imp_GetCurrentProcess
0x180031865  mov     r14, [rbp+58h]
0x180031869  mov     [rsp+150h+dwOptions], 2; dwOptions
0x180031871  mov     [rsp+150h+bInheritHandle], r15d; bInheritHandle
0x180031876  mov     [rsp+150h+dwDesiredAccess], r15d; dwDesiredAccess
0x18003187b  lea     r9, [rsp+150h+TargetHandle]; lpTargetHandle
0x180031880  mov     r8, rdi; hTargetProcessHandle
0x180031883  mov     rdx, rbx; hSourceHandle
0x180031886  mov     rcx, rax; hSourceProcessHandle
0x180031889  call    cs:__imp_DuplicateHandle
0x18003188f  test    eax, eax
0x180031891  jnz     short loc_1800318A6
0x180031893  lea     r8, aOnecoreuapDriv_18; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18003189a  lea     edx, [rax+7Dh]; void *
0x18003189d  mov     rcx, r14; this
0x1800318a0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800318a6  mov     rcx, [rsi+20h]
0x1800318aa  mov     rax, [rcx]
0x1800318ad  mov     rdx, [rsp+150h+TargetHandle]
0x1800318b2  mov     [rsp+150h+var_108], rdx
0x1800318b7  mov     [rsp+150h+TargetHandle], r15
0x1800318bc  lea     r8, [rsp+150h+var_108]
0x1800318c1  lea     rdx, [rsp+150h+var_100]
0x1800318c6  mov     rax, [rax+218h]
0x1800318cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318d2  lea     rcx, [rsi+48h]
0x1800318d6  mov     rdx, rax
0x1800318d9  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x1800318de  mov     rcx, [rsp+150h+var_F8]; this
0x1800318e3  test    rcx, rcx
0x1800318e6  jz      short loc_1800318EE
0x1800318e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800318ed  nop
0x1800318ee  lea     rcx, [rsp+150h+TargetHandle]
0x1800318f3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800318f8  mov     rdx, rsi
0x1800318fb  lea     rcx, [rsp+150h+var_108]
0x180031900  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180031905  mov     rdx, [rsp+150h+var_108]
0x18003190a  lea     rcx, [rbp+50h+var_B8]
0x18003190e  call    wistd__function_void___cdecl_void____function_void___cdecl_void____lambda_08916717245842905d91babd18e52812__void_
0x180031913  nop
0x180031914  lea     rbx, [rsi+90h]
0x18003191b  lea     rdx, [rbp+50h+var_B8]
0x18003191f  mov     rcx, rbx
0x180031922  call    ?create@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(wistd::function<void (void)> &&)
0x180031927  nop
0x180031928  lea     rcx, [rbp+50h+var_B8]
0x18003192c  call    ??1?$function@$$A6AXAEBE@Z@wistd@@QEAA@XZ; wistd::function<void (uchar const &)>::~function<void (uchar const &)>(void)
0x180031931  mov     [rsp+150h+TargetHandle], r15
0x180031936  xor     edx, edx
0x180031938  lea     rcx, [rsp+150h+TargetHandle]
0x18003193d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180031942  call    cs:__imp_GetCurrentProcess
0x180031948  mov     rdi, rax
0x18003194b  mov     rcx, [rbx]
0x18003194e  mov     rbx, [rcx+78h]
0x180031952  call    cs:__imp_GetCurrentProcess
0x180031958  mov     r14, [rbp+58h]
0x18003195c  mov     [rsp+150h+dwOptions], 2; dwOptions
0x180031964  mov     [rsp+150h+bInheritHandle], r15d; bInheritHandle
0x180031969  mov     [rsp+150h+dwDesiredAccess], r15d; dwDesiredAccess
0x18003196e  lea     r9, [rsp+150h+TargetHandle]; lpTargetHandle
0x180031973  mov     r8, rdi; hTargetProcessHandle
0x180031976  mov     rdx, rbx; hSourceHandle
0x180031979  mov     rcx, rax; hSourceProcessHandle
0x18003197c  call    cs:__imp_DuplicateHandle
0x180031982  test    eax, eax
0x180031984  jnz     short loc_18003199B
0x180031986  lea     r8, aOnecoreuapDriv_18; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18003198d  mov     edx, 9Fh; void *
0x180031992  mov     rcx, r14; this
0x180031995  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003199b  mov     rcx, [rsi+20h]
0x18003199f  mov     rax, [rcx]
0x1800319a2  mov     rdx, [rsp+150h+TargetHandle]
0x1800319a7  mov     [rsp+150h+var_108], rdx
0x1800319ac  mov     [rsp+150h+TargetHandle], r15
0x1800319b1  lea     r8, [rsp+150h+var_108]
0x1800319b6  lea     rdx, [rsp+150h+var_100]
0x1800319bb  mov     rax, [rax+1A0h]
0x1800319c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319c7  lea     rcx, [rsi+98h]
0x1800319ce  mov     rdx, rax
0x1800319d1  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x1800319d6  mov     rcx, [rsp+150h+var_F8]; this
0x1800319db  test    rcx, rcx
0x1800319de  jz      short loc_1800319E6
0x1800319e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800319e5  nop
0x1800319e6  lea     rcx, [rsp+150h+TargetHandle]
0x1800319eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800319f0  mov     rdx, rsi
0x1800319f3  lea     rcx, [rsp+150h+var_108]
0x1800319f8  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800319fd  mov     rdx, [rsp+150h+var_108]
0x180031a02  lea     rcx, [rbp+50h+var_B8]
0x180031a06  call    wistd__function_void___cdecl_void____function_void___cdecl_void____lambda_5dc1d4f8ee6fda12c4970d1ae3e56e45__void_
0x180031a0b  nop
0x180031a0c  lea     rdx, [rbp+50h+var_B8]
0x180031a10  lea     rcx, [rsi+60h]
0x180031a14  call    ?create@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(wistd::function<void (void)> &&)
0x180031a19  nop
0x180031a1a  lea     rcx, [rbp+50h+var_B8]
0x180031a1e  call    ??1?$function@$$A6AXAEBE@Z@wistd@@QEAA@XZ; wistd::function<void (uchar const &)>::~function<void (uchar const &)>(void)
0x180031a23  mov     [rsp+150h+TargetHandle], r15
0x180031a28  xor     edx, edx
0x180031a2a  lea     rcx, [rsp+150h+TargetHandle]
0x180031a2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180031a34  call    cs:__imp_GetCurrentProcess
0x180031a3a  mov     rdi, rax
0x180031a3d  mov     rcx, [rsi+60h]
0x180031a41  mov     rbx, [rcx+78h]
0x180031a45  call    cs:__imp_GetCurrentProcess
0x180031a4b  mov     r14, [rbp+58h]
0x180031a4f  mov     [rsp+150h+dwOptions], 2; dwOptions
0x180031a57  mov     [rsp+150h+bInheritHandle], r15d; bInheritHandle
0x180031a5c  mov     [rsp+150h+dwDesiredAccess], r15d; dwDesiredAccess
0x180031a61  lea     r9, [rsp+150h+TargetHandle]; lpTargetHandle
0x180031a66  mov     r8, rdi; hTargetProcessHandle
0x180031a69  mov     rdx, rbx; hSourceHandle
0x180031a6c  mov     rcx, rax; hSourceProcessHandle
0x180031a6f  call    cs:__imp_DuplicateHandle
0x180031a75  test    eax, eax
0x180031a77  jnz     short loc_180031A8E
0x180031a79  lea     r8, aOnecoreuapDriv_18; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180031a80  mov     edx, 0CDh; void *
0x180031a85  mov     rcx, r14; this
0x180031a88  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180031a8e  mov     rcx, [rsi+20h]
0x180031a92  mov     rax, [rcx]
0x180031a95  mov     rdx, [rsp+150h+TargetHandle]
0x180031a9a  mov     [rsp+150h+var_108], rdx
0x180031a9f  mov     [rsp+150h+TargetHandle], r15
0x180031aa4  lea     r8, [rsp+150h+var_108]
0x180031aa9  lea     rdx, [rsp+150h+var_100]
0x180031aae  mov     rax, [rax+80h]
0x180031ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031aba  lea     rcx, [rsi+68h]
0x180031abe  mov     rdx, rax
0x180031ac1  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x180031ac6  mov     rcx, [rsp+150h+var_F8]; this
0x180031acb  test    rcx, rcx
0x180031ace  jz      short loc_180031AD6
0x180031ad0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031ad5  nop
0x180031ad6  lea     rcx, [rsp+150h+TargetHandle]
0x180031adb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180031ae0  mov     rdx, rsi
0x180031ae3  lea     rcx, [rsp+150h+var_108]
0x180031ae8  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180031aed  mov     rdx, [rsp+150h+var_108]
0x180031af2  lea     rcx, [rbp+50h+var_B8]
0x180031af6  call    wistd__function_void___cdecl_void____function_void___cdecl_void____lambda_8694b62541581ff6870704328c8150a7__void_
0x180031afb  nop
0x180031afc  lea     rdx, [rbp+50h+var_B8]
0x180031b00  lea     rcx, [rsi+78h]
0x180031b04  call    ?create@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(wistd::function<void (void)> &&)
0x180031b09  nop
0x180031b0a  lea     rcx, [rbp+50h+var_B8]
0x180031b0e  call    ??1?$function@$$A6AXAEBE@Z@wistd@@QEAA@XZ; wistd::function<void (uchar const &)>::~function<void (uchar const &)>(void)
0x180031b13  mov     [rsp+150h+TargetHandle], r15
0x180031b18  xor     edx, edx
0x180031b1a  lea     rcx, [rsp+150h+TargetHandle]
0x180031b1f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180031b24  call    cs:__imp_GetCurrentProcess
0x180031b2a  mov     rdi, rax
0x180031b2d  mov     rcx, [rsi+78h]
0x180031b31  mov     rbx, [rcx+78h]
0x180031b35  call    cs:__imp_GetCurrentProcess
0x180031b3b  mov     r14, [rbp+58h]
0x180031b3f  mov     [rsp+150h+dwOptions], 2; dwOptions
0x180031b47  mov     [rsp+150h+bInheritHandle], r15d; bInheritHandle
0x180031b4c  mov     [rsp+150h+dwDesiredAccess], r15d; dwDesiredAccess
0x180031b51  lea     r9, [rsp+150h+TargetHandle]; lpTargetHandle
0x180031b56  mov     r8, rdi; hTargetProcessHandle
0x180031b59  mov     rdx, rbx; hSourceHandle
0x180031b5c  mov     rcx, rax; hSourceProcessHandle
0x180031b5f  call    cs:__imp_DuplicateHandle
0x180031b65  test    eax, eax
0x180031b67  jnz     short loc_180031B7E
0x180031b69  lea     r8, aOnecoreuapDriv_18; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180031b70  mov     edx, 0EDh; void *
0x180031b75  mov     rcx, r14; this
0x180031b78  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180031b7e  mov     rcx, [rsi+20h]
0x180031b82  mov     rax, [rcx]
0x180031b85  mov     rdx, [rsp+150h+TargetHandle]
0x180031b8a  mov     [rsp+150h+var_108], rdx
0x180031b8f  mov     [rsp+150h+TargetHandle], r15
0x180031b94  lea     r8, [rsp+150h+var_108]
0x180031b99  lea     rdx, [rsp+150h+var_100]
0x180031b9e  mov     rax, [rax+128h]
0x180031ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031baa  lea     rcx, [rsi+80h]
0x180031bb1  mov     rdx, rax
0x180031bb4  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x180031bb9  mov     rcx, [rsp+150h+var_F8]; this
0x180031bbe  test    rcx, rcx
0x180031bc1  jz      short loc_180031BC9
0x180031bc3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031bc8  nop
0x180031bc9  lea     rcx, [rsp+150h+TargetHandle]
0x180031bce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180031bd3  mov     rcx, [rsi+1F0h]
0x180031bda  mov     rax, [rcx]
0x180031bdd  lea     rdx, [rsp+150h+var_F0]
0x180031be2  mov     rax, [rax+10h]
0x180031be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031beb  nop
0x180031bec  mov     rdx, rax
0x180031bef  lea     rcx, [rsp+150h+var_100]
0x180031bf4  call    ?GetOrMakeShared@DesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDesTelemetry@Telemetry@DisplayEnhancement@Windows@Microsoft@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Microsoft::Windows::DisplayEnhancement::Telemetry::DesTelemetry::GetOrMakeShared(std::wstring const &)
0x180031bf9  lea     rcx, [rsi+1E0h]
0x180031c00  mov     rdx, rax
0x180031c03  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x180031c08  mov     rcx, [rsp+150h+var_F8]; this
0x180031c0d  test    rcx, rcx
0x180031c10  jz      short loc_180031C18
0x180031c12  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031c17  nop
0x180031c18  lea     rcx, [rsp+150h+var_F0]
0x180031c1d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031c22  mov     rcx, [rbp+50h+var_40]
0x180031c26  xor     rcx, rsp; StackCookie
0x180031c29  call    __security_check_cookie
0x180031c2e  add     rsp, 128h
0x180031c35  pop     r15
0x180031c37  pop     r14
0x180031c39  pop     rdi
0x180031c3a  pop     rsi
0x180031c3b  pop     rbx
  ... truncated ...
```
