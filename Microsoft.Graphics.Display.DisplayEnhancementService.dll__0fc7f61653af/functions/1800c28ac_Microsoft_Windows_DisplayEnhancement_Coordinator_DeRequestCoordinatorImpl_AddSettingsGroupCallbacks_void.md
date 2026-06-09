# Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl::AddSettingsGroupCallbacks(void)

- ea: `0x1800c28ac`
- end: `0x1800c2be5`
- name: `?AddSettingsGroupCallbacks@DeRequestCoordinatorImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ`
- size: `825`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c40fc`

## callees

- `0x180005860`
- `0x180007c0c`
- `0x180009904`
- `0x180009b3c`
- `0x180009f68`
- `0x18000f778`
- `0x18000f9f0`
- `0x18000ffe0`
- `0x18001c404`
- `0x1800c28ac`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2928`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2938`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2a24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2a34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2b20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2b30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2928`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2938`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2a24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2a34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2b20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c2b30`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800c2961`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800c2a5d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800c2b59`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800c2961`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800c2a5d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800c2b59`

## string_xrefs

- `0x1800c296b`: `onecoreuap\drivers\mobilepc\displayenhancement\service\derequestcoordinator\lib\derequestcoordinator.cpp`
- `0x1800c2a67`: `onecoreuap\drivers\mobilepc\displayenhancement\service\derequestcoordinator\lib\derequestcoordinator.cpp`
- `0x1800c2b63`: `onecoreuap\drivers\mobilepc\displayenhancement\service\derequestcoordinator\lib\derequestcoordinator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl::AddSettingsGroupCallbacks(
        Microsoft::Windows::DisplayEnhancement::Coordinator::DeRequestCoordinatorImpl *this)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  HANDLE CurrentProcess; // rdi
  void *v5; // rbx
  HANDLE v6; // rax
  const char *v7; // r9
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 *v10; // rax
  HANDLE v11; // rdi
  void *v12; // rbx
  HANDLE v13; // rax
  const char *v14; // r9
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 *v17; // rax
  HANDLE v18; // rdi
  void *v19; // rbx
  HANDLE v20; // rax
  const char *v21; // r9
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int64 *v24; // rax
  HANDLE TargetHandle; // [rsp+40h] [rbp-79h] BYREF
  HANDLE v26; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v27[8]; // [rsp+50h] [rbp-69h] BYREF
  std::_Ref_count_base *v28; // [rsp+58h] [rbp-61h]
  _BYTE v29[8]; // [rsp+60h] [rbp-59h] BYREF
  __int64 (__fastcall **v30)(); // [rsp+68h] [rbp-51h] BYREF
  HANDLE v31; // [rsp+70h] [rbp-49h]
  __int64 (__fastcall ***v32)(); // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v26, (__int64)this);
  v30 = off_1800F5D08;
  v31 = v26;
  v32 = &v30;
  v3 = v2 + 200;
  wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
    v2 + 200,
    v29);
  wistd::function<void (unsigned char const &)>::~function<void (unsigned char const &)>(v29);
  TargetHandle = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &TargetHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  v5 = *(void **)(*(_QWORD *)v3 + 120LL);
  v6 = GetCurrentProcess();
  if ( !DuplicateHandle(v6, v5, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\derequestcoordinator\\lib\\derequestcoordinator.cpp",
      v7);
  v8 = (__int64 *)*((_QWORD *)this + 88);
  v9 = *v8;
  v26 = TargetHandle;
  TargetHandle = 0;
  v10 = (__int64 *)(*(__int64 (__fastcall **)(__int64 *, _BYTE *, HANDLE *))(v9 + 512))(v8, v27, &v26);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (_QWORD *)this + 28,
    v10);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&TargetHandle);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v26, (__int64)this);
  v30 = off_1800F5CE0;
  v31 = v26;
  v32 = &v30;
  wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
    (char *)this + 208,
    v29);
  wistd::function<void (unsigned char const &)>::~function<void (unsigned char const &)>(v29);
  TargetHandle = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &TargetHandle,
    0);
  v11 = GetCurrentProcess();
  v12 = *(void **)(*((_QWORD *)this + 26) + 120LL);
  v13 = GetCurrentProcess();
  if ( !DuplicateHandle(v13, v12, v11, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\derequestcoordinator\\lib\\derequestcoordinator.cpp",
      v14);
  v15 = (__int64 *)*((_QWORD *)this + 88);
  v16 = *v15;
  v26 = TargetHandle;
  TargetHandle = 0;
  v17 = (__int64 *)(*(__int64 (__fastcall **)(__int64 *, _BYTE *, HANDLE *))(v16 + 416))(v15, v27, &v26);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (_QWORD *)this + 30,
    v17);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&TargetHandle);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v26, (__int64)this);
  v30 = off_1800F5CE0;
  v31 = v26;
  v32 = &v30;
  wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
    (char *)this + 216,
    v29);
  wistd::function<void (unsigned char const &)>::~function<void (unsigned char const &)>(v29);
  TargetHandle = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &TargetHandle,
    0);
  v18 = GetCurrentProcess();
  v19 = *(void **)(*((_QWORD *)this + 27) + 120LL);
  v20 = GetCurrentProcess();
  if ( !DuplicateHandle(v20, v19, v18, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\derequestcoordinator\\lib\\derequestcoordinator.cpp",
      v21);
  v22 = (__int64 *)*((_QWORD *)this + 88);
  v23 = *v22;
  v26 = TargetHandle;
  TargetHandle = 0;
  v24 = (__int64 *)(*(__int64 (__fastcall **)(__int64 *, _BYTE *, HANDLE *))(v23 + 488))(v22, v27, &v26);
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
    (_QWORD *)this + 32,
    v24);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&TargetHandle);
}

```

## disassembly

```asm
0x1800c28ac  push    rbp
0x1800c28ae  push    rbx
0x1800c28af  push    rsi
0x1800c28b0  push    rdi
0x1800c28b1  push    r14
0x1800c28b3  push    r15
0x1800c28b5  lea     rbp, [rsp-2Fh]
0x1800c28ba  sub     rsp, 0E8h
0x1800c28c1  mov     rax, cs:__security_cookie
0x1800c28c8  xor     rax, rsp
0x1800c28cb  mov     [rbp+57h+var_38], rax
0x1800c28cf  mov     rsi, rcx
0x1800c28d2  mov     rdx, rcx
0x1800c28d5  lea     rcx, [rbp+57h+var_C8]
0x1800c28d9  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800c28de  mov     rax, [rbp+57h+var_C8]
0x1800c28e2  lea     rcx, off_1800F5D08
0x1800c28e9  mov     [rbp+57h+var_A8], rcx
0x1800c28ed  mov     [rbp+57h+var_A0], rax
0x1800c28f1  lea     rax, [rbp+57h+var_A8]
0x1800c28f5  mov     [rbp+57h+var_40], rax
0x1800c28f9  lea     rbx, [rdx+0C8h]
0x1800c2900  lea     rdx, [rbp+57h+var_B0]
0x1800c2904  mov     rcx, rbx
0x1800c2907  call    ?create@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(wistd::function<void (void)> &&)
0x1800c290c  nop
0x1800c290d  lea     rcx, [rbp+57h+var_B0]
0x1800c2911  call    ??1?$function@$$A6AXAEBE@Z@wistd@@QEAA@XZ; wistd::function<void (uchar const &)>::~function<void (uchar const &)>(void)
0x1800c2916  xor     r15d, r15d
0x1800c2919  mov     [rbp+57h+TargetHandle], r15
0x1800c291d  xor     edx, edx
0x1800c291f  lea     rcx, [rbp+57h+TargetHandle]
0x1800c2923  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800c2928  call    cs:__imp_GetCurrentProcess
0x1800c292e  mov     rdi, rax
0x1800c2931  mov     rcx, [rbx]
0x1800c2934  mov     rbx, [rcx+78h]
0x1800c2938  call    cs:__imp_GetCurrentProcess
0x1800c293e  mov     r14, [rbp+5Fh]
0x1800c2942  mov     [rsp+110h+dwOptions], 2; dwOptions
0x1800c294a  mov     [rsp+110h+bInheritHandle], r15d; bInheritHandle
0x1800c294f  mov     [rsp+110h+dwDesiredAccess], r15d; dwDesiredAccess
0x1800c2954  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x1800c2958  mov     r8, rdi; hTargetProcessHandle
0x1800c295b  mov     rdx, rbx; hSourceHandle
0x1800c295e  mov     rcx, rax; hSourceProcessHandle
0x1800c2961  call    cs:__imp_DuplicateHandle
0x1800c2967  test    eax, eax
0x1800c2969  jnz     short loc_1800C2980
0x1800c296b  lea     r8, aOnecoreuapDriv_5; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800c2972  mov     edx, 0AFh; void *
0x1800c2977  mov     rcx, r14; this
0x1800c297a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800c2980  mov     rcx, [rsi+2C0h]
0x1800c2987  mov     rax, [rcx]
0x1800c298a  mov     rdx, [rbp+57h+TargetHandle]
0x1800c298e  mov     [rbp+57h+var_C8], rdx
0x1800c2992  mov     [rbp+57h+TargetHandle], r15
0x1800c2996  lea     r8, [rbp+57h+var_C8]
0x1800c299a  lea     rdx, [rbp+57h+var_C0]
0x1800c299e  mov     rax, [rax+200h]
0x1800c29a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c29aa  lea     rcx, [rsi+0E0h]
0x1800c29b1  mov     rdx, rax
0x1800c29b4  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x1800c29b9  mov     rcx, [rbp+57h+var_B8]; this
0x1800c29bd  test    rcx, rcx
0x1800c29c0  jz      short loc_1800C29C8
0x1800c29c2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c29c7  nop
0x1800c29c8  lea     rcx, [rbp+57h+TargetHandle]
0x1800c29cc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c29d1  mov     rdx, rsi
0x1800c29d4  lea     rcx, [rbp+57h+var_C8]
0x1800c29d8  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800c29dd  mov     rax, [rbp+57h+var_C8]
0x1800c29e1  lea     rcx, off_1800F5CE0
0x1800c29e8  mov     [rbp+57h+var_A8], rcx
0x1800c29ec  mov     [rbp+57h+var_A0], rax
0x1800c29f0  lea     rax, [rbp+57h+var_A8]
0x1800c29f4  mov     [rbp+57h+var_40], rax
0x1800c29f8  lea     rbx, [rsi+0D0h]
0x1800c29ff  lea     rdx, [rbp+57h+var_B0]
0x1800c2a03  mov     rcx, rbx
0x1800c2a06  call    ?create@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(wistd::function<void (void)> &&)
0x1800c2a0b  nop
0x1800c2a0c  lea     rcx, [rbp+57h+var_B0]
0x1800c2a10  call    ??1?$function@$$A6AXAEBE@Z@wistd@@QEAA@XZ; wistd::function<void (uchar const &)>::~function<void (uchar const &)>(void)
0x1800c2a15  mov     [rbp+57h+TargetHandle], r15
0x1800c2a19  xor     edx, edx
0x1800c2a1b  lea     rcx, [rbp+57h+TargetHandle]
0x1800c2a1f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800c2a24  call    cs:__imp_GetCurrentProcess
0x1800c2a2a  mov     rdi, rax
0x1800c2a2d  mov     rcx, [rbx]
0x1800c2a30  mov     rbx, [rcx+78h]
0x1800c2a34  call    cs:__imp_GetCurrentProcess
0x1800c2a3a  mov     r14, [rbp+5Fh]
0x1800c2a3e  mov     [rsp+110h+dwOptions], 2; dwOptions
0x1800c2a46  mov     [rsp+110h+bInheritHandle], r15d; bInheritHandle
0x1800c2a4b  mov     [rsp+110h+dwDesiredAccess], r15d; dwDesiredAccess
0x1800c2a50  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x1800c2a54  mov     r8, rdi; hTargetProcessHandle
0x1800c2a57  mov     rdx, rbx; hSourceHandle
0x1800c2a5a  mov     rcx, rax; hSourceProcessHandle
0x1800c2a5d  call    cs:__imp_DuplicateHandle
0x1800c2a63  test    eax, eax
0x1800c2a65  jnz     short loc_1800C2A7C
0x1800c2a67  lea     r8, aOnecoreuapDriv_5; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800c2a6e  mov     edx, 0C6h; void *
0x1800c2a73  mov     rcx, r14; this
0x1800c2a76  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800c2a7c  mov     rcx, [rsi+2C0h]
0x1800c2a83  mov     rax, [rcx]
0x1800c2a86  mov     rdx, [rbp+57h+TargetHandle]
0x1800c2a8a  mov     [rbp+57h+var_C8], rdx
0x1800c2a8e  mov     [rbp+57h+TargetHandle], r15
0x1800c2a92  lea     r8, [rbp+57h+var_C8]
0x1800c2a96  lea     rdx, [rbp+57h+var_C0]
0x1800c2a9a  mov     rax, [rax+1A0h]
0x1800c2aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2aa6  lea     rcx, [rsi+0F0h]
0x1800c2aad  mov     rdx, rax
0x1800c2ab0  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x1800c2ab5  mov     rcx, [rbp+57h+var_B8]; this
0x1800c2ab9  test    rcx, rcx
0x1800c2abc  jz      short loc_1800C2AC4
0x1800c2abe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c2ac3  nop
0x1800c2ac4  lea     rcx, [rbp+57h+TargetHandle]
0x1800c2ac8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c2acd  mov     rdx, rsi
0x1800c2ad0  lea     rcx, [rbp+57h+var_C8]
0x1800c2ad4  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800c2ad9  mov     rax, [rbp+57h+var_C8]
0x1800c2add  lea     rcx, off_1800F5CE0
0x1800c2ae4  mov     [rbp+57h+var_A8], rcx
0x1800c2ae8  mov     [rbp+57h+var_A0], rax
0x1800c2aec  lea     rax, [rbp+57h+var_A8]
0x1800c2af0  mov     [rbp+57h+var_40], rax
0x1800c2af4  lea     rbx, [rsi+0D8h]
0x1800c2afb  lea     rdx, [rbp+57h+var_B0]
0x1800c2aff  mov     rcx, rbx
0x1800c2b02  call    ?create@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(wistd::function<void (void)> &&)
0x1800c2b07  nop
0x1800c2b08  lea     rcx, [rbp+57h+var_B0]
0x1800c2b0c  call    ??1?$function@$$A6AXAEBE@Z@wistd@@QEAA@XZ; wistd::function<void (uchar const &)>::~function<void (uchar const &)>(void)
0x1800c2b11  mov     [rbp+57h+TargetHandle], r15
0x1800c2b15  xor     edx, edx
0x1800c2b17  lea     rcx, [rbp+57h+TargetHandle]
0x1800c2b1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800c2b20  call    cs:__imp_GetCurrentProcess
0x1800c2b26  mov     rdi, rax
0x1800c2b29  mov     rcx, [rbx]
0x1800c2b2c  mov     rbx, [rcx+78h]
0x1800c2b30  call    cs:__imp_GetCurrentProcess
0x1800c2b36  mov     r14, [rbp+5Fh]
0x1800c2b3a  mov     [rsp+110h+dwOptions], 2; dwOptions
0x1800c2b42  mov     [rsp+110h+bInheritHandle], r15d; bInheritHandle
0x1800c2b47  mov     [rsp+110h+dwDesiredAccess], r15d; dwDesiredAccess
0x1800c2b4c  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x1800c2b50  mov     r8, rdi; hTargetProcessHandle
0x1800c2b53  mov     rdx, rbx; hSourceHandle
0x1800c2b56  mov     rcx, rax; hSourceProcessHandle
0x1800c2b59  call    cs:__imp_DuplicateHandle
0x1800c2b5f  test    eax, eax
0x1800c2b61  jnz     short loc_1800C2B78
0x1800c2b63  lea     r8, aOnecoreuapDriv_5; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800c2b6a  mov     edx, 0DDh; void *
0x1800c2b6f  mov     rcx, r14; this
0x1800c2b72  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800c2b78  mov     rcx, [rsi+2C0h]
0x1800c2b7f  mov     rax, [rcx]
0x1800c2b82  mov     rdx, [rbp+57h+TargetHandle]
0x1800c2b86  mov     [rbp+57h+var_C8], rdx
0x1800c2b8a  mov     [rbp+57h+TargetHandle], r15
0x1800c2b8e  lea     r8, [rbp+57h+var_C8]
0x1800c2b92  lea     rdx, [rbp+57h+var_C0]
0x1800c2b96  mov     rax, [rax+1E8h]
0x1800c2b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2ba2  lea     rcx, [rsi+100h]
0x1800c2ba9  mov     rdx, rax
0x1800c2bac  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x1800c2bb1  mov     rcx, [rbp+57h+var_B8]; this
0x1800c2bb5  test    rcx, rcx
0x1800c2bb8  jz      short loc_1800C2BC0
0x1800c2bba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c2bbf  nop
0x1800c2bc0  lea     rcx, [rbp+57h+TargetHandle]
0x1800c2bc4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c2bc9  mov     rcx, [rbp+57h+var_38]
0x1800c2bcd  xor     rcx, rsp; StackCookie
0x1800c2bd0  call    __security_check_cookie
0x1800c2bd5  add     rsp, 0E8h
0x1800c2bdc  pop     r15
0x1800c2bde  pop     r14
0x1800c2be0  pop     rdi
0x1800c2be1  pop     rsi
0x1800c2be2  pop     rbx
0x1800c2be3  pop     rbp
0x1800c2be4  retn
```
