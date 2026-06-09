# Windows::Internal::AssignedAccess::MdmTaskWorker::Start(void)

- ea: `0x18004d2a4`
- end: `0x18004d5cb`
- name: `?Start@MdmTaskWorker@AssignedAccess@Internal@Windows@@AEAAJXZ`
- size: `807`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::MdmTaskWorker *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004d204`

## callees

- `0x180006640`
- `0x1800090b4`
- `0x180009cb8`
- `0x18000b6b4`
- `0x18000c398`
- `0x18000cfe4`
- `0x18000d008`
- `0x18000d028`
- `0x18000d120`
- `0x180013fac`
- `0x18001f2b0`
- `0x18004c340`
- `0x18004c560`
- `0x18004c778`
- `0x18004cad8`
- `0x18004cb30`
- `0x18004d2a4`
- `0x18004d5d4`
- `0x18004dd04`
- `0x18004dd5c`
- `0x18004dfe4`
- `0x18004e010`
- `0x18004e11c`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004d34d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004d34d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d35f`

## string_xrefs

- `0x18004d321`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\mdmtaskworker.cpp`
- `0x18004d404`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\mdmtaskworker.cpp`
- `0x18004d46f`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\mdmtaskworker.cpp`
- `0x18004d2cc`: `MdmTaskWorker_Start`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::MdmTaskWorker::Start(
        Windows::Internal::AssignedAccess::MdmTaskWorker *this)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // edi
  HANDLE Event; // rdi
  unsigned int v6; // r8d
  const char *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // eax
  void *v12; // rdi
  int v13; // eax
  int v14; // esi
  __int64 v16; // rsi
  int v17; // [rsp+20h] [rbp-E0h]
  void *v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  void *v21; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v22; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v24[15]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v25[42]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v25,
    "MdmTaskWorker_Start");
  v25[0] = &AssignedAccessTelemetry::MdmTaskWorker_Start::`vftable';
  AssignedAccessTelemetry::MdmTaskWorker_Start::StartActivity((AssignedAccessTelemetry::MdmTaskWorker_Start *)v25);
  wil::wnf_publish<unsigned long>(v2, &qword_1800AAF20);
  v21 = 0;
  v3 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::MdmAlertTaskHandler,ITaskHandler,>(&v21);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\mdmtaskworker.cpp",
      (const char *)(unsigned int)v3,
      v17);
LABEL_10:
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v21);
    AssignedAccessTelemetry::MdmTaskWorker_Start::~MdmTaskWorker_Start((AssignedAccessTelemetry::MdmTaskWorker_Start *)v25);
    return v4;
  }
  v22 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x1CC8, v6, v7);
  GetLastError();
  _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
    &v22,
    Event);
  v19 = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v19,
    1);
  v8 = *(_QWORD *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                    &v18,
                    this);
  v24[0] = off_18009AEE0;
  v24[1] = v8;
  v24[13] = v24;
  v10 = v22;
  if ( (_QWORD)v22 )
    v10 = *(_QWORD *)v22;
  wil::make_event_watcher(&v20, v10, v9, v23);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v23);
  v18 = 0;
  v11 = ___MakeAndInitialize_VMdmTaskHandlerStatus_AssignedAccess_Internal_Windows__UITaskHandlerStatus__AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YAJPEAPEAUITaskHandlerStatus__AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z(&v18);
  v4 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\mdmtaskworker.cpp",
      (const char *)(unsigned int)v11,
      v17);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v18);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(&v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>::~shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>(&v22);
    goto LABEL_10;
  }
  v12 = v21;
  v13 = (*(__int64 (__fastcall **)(void *, void *, _QWORD))(*(_QWORD *)v21 + 24LL))(v21, v18, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\mdmtaskworker.cpp",
      (const char *)(unsigned int)v13,
      v17);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v18);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(&v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>::~shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>(&v22);
    v4 = v14;
    goto LABEL_10;
  }
  v16 = *(_QWORD *)this;
  *(_QWORD *)this = v12;
  if ( v12 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 8LL))(v12);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( (__int64 *)((char *)this + 8) != &v19 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 8,
      v19);
    v19 = 0;
  }
  if ( (__int128 *)((char *)this + 16) != &v22 )
    __4__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__QEAAAEAV01___QEAV01__Z(
      (char *)this + 16,
      &v22);
  if ( (__int64 *)((char *)this + 32) != &v20 )
  {
    wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(
      (char *)this + 32,
      v20);
    v20 = 0;
  }
  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v25);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(&v20);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
  std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>::~shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>(&v22);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v21);
  AssignedAccessTelemetry::MdmTaskWorker_Start::~MdmTaskWorker_Start((AssignedAccessTelemetry::MdmTaskWorker_Start *)v25);
  return 0;
}

```

## disassembly

```asm
0x18004d2a4  push    rbp
0x18004d2a6  push    rbx
0x18004d2a7  push    rsi
0x18004d2a8  push    rdi
0x18004d2a9  lea     rbp, [rsp-148h]
0x18004d2b1  sub     rsp, 248h
0x18004d2b8  mov     rax, cs:__security_cookie
0x18004d2bf  xor     rax, rsp
0x18004d2c2  mov     [rbp+160h+var_30], rax
0x18004d2c9  mov     rbx, rcx
0x18004d2cc  lea     rdx, aMdmtaskworkerS_0; "MdmTaskWorker_Start"
0x18004d2d3  lea     rcx, [rbp+160h+var_180]
0x18004d2d7  call    ??0?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004d2dc  lea     rax, ??_7MdmTaskWorker_Start@AssignedAccessTelemetry@@6B@; const AssignedAccessTelemetry::MdmTaskWorker_Start::`vftable'
0x18004d2e3  mov     [rbp+160h+var_180], rax
0x18004d2e7  lea     rcx, [rbp+160h+var_180]; this
0x18004d2eb  call    ?StartActivity@MdmTaskWorker_Start@AssignedAccessTelemetry@@QEAAXXZ; AssignedAccessTelemetry::MdmTaskWorker_Start::StartActivity(void)
0x18004d2f0  nop
0x18004d2f1  lea     rdx, qword_1800AAF20
0x18004d2f8  call    ??$wnf_publish@K@wil@@YAXAEBU_WNF_STATE_NAME@@AEBK@Z; wil::wnf_publish<ulong>(_WNF_STATE_NAME const &,ulong const &)
0x18004d2fd  nop
0x18004d2fe  mov     [rsp+260h+var_218], 0
0x18004d307  lea     rcx, [rsp+260h+var_218]; void **
0x18004d30c  call    ??$MakeAndInitialize@VMdmAlertTaskHandler@AssignedAccess@Internal@Windows@@UITaskHandler@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUITaskHandler@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::AssignedAccess::MdmAlertTaskHandler,ITaskHandler,>(ITaskHandler * *)
0x18004d311  mov     edi, eax
0x18004d313  test    eax, eax
0x18004d315  jns     short loc_18004D337
0x18004d317  mov     rcx, [rbp+168h]; this
0x18004d31e  mov     r9d, eax; char *
0x18004d321  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004d328  mov     edx, 43h ; 'C'; void *
0x18004d32d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d332  jmp     loc_18004D4AE
0x18004d337  xorps   xmm1, xmm1
0x18004d33a  movdqu  [rsp+260h+var_210], xmm1
0x18004d340  mov     r9d, 1F0003h; dwDesiredAccess
0x18004d346  xor     r8d, r8d; dwFlags
0x18004d349  xor     edx, edx; lpName
0x18004d34b  xor     ecx, ecx; lpEventAttributes
0x18004d34d  call    cs:__imp_CreateEventExW
0x18004d353  mov     rdi, rax
0x18004d356  test    rax, rax
0x18004d359  jz      loc_18004D5B9
0x18004d35f  call    cs:__imp_GetLastError
0x18004d365  mov     rdx, rdi
0x18004d368  lea     rcx, [rsp+260h+var_210]
0x18004d36d  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x18004d372  mov     [rsp+260h+var_228], 0
0x18004d37b  mov     edx, 1
0x18004d380  lea     rcx, [rsp+260h+var_228]
0x18004d385  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18004d38a  mov     rdx, rbx
0x18004d38d  lea     rcx, [rsp+260h+var_230]
0x18004d392  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18004d397  mov     rcx, [rax]
0x18004d39a  lea     rax, off_18009AEE0
0x18004d3a1  mov     [rsp+260h+var_1F8], rax
0x18004d3a6  mov     [rsp+260h+var_1F0], rcx
0x18004d3ab  lea     rax, [rsp+260h+var_1F8]
0x18004d3b0  mov     [rbp+160h+var_190], rax
0x18004d3b4  mov     rdx, qword ptr [rsp+260h+var_210]
0x18004d3b9  test    rdx, rdx
0x18004d3bc  jz      short loc_18004D3C1
0x18004d3be  mov     rdx, [rdx]
0x18004d3c1  lea     r9, [rsp+260h+var_200]
0x18004d3c6  lea     rcx, [rsp+260h+var_220]
0x18004d3cb  call    ?make_event_watcher@wil@@YA?AV?$unique_any_t@V?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@1@PEAXW4event_watcher_options@1@$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::make_event_watcher(void *,wil::event_watcher_options,wistd::function<void (void)> &&)
0x18004d3d0  nop
0x18004d3d1  lea     rcx, [rsp+260h+var_200]
0x18004d3d6  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x18004d3db  nop
0x18004d3dc  mov     [rsp+260h+var_230], 0
0x18004d3e5  lea     rdx, [rsp+260h+var_210]
0x18004d3ea  lea     rcx, [rsp+260h+var_230]; void **
0x18004d3ef  call    ??$MakeAndInitialize@VMdmTaskHandlerStatus@AssignedAccess@Internal@Windows@@UITaskHandlerStatus@@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Details@WRL@Microsoft@@YAJPEAPEAUITaskHandlerStatus@@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z
0x18004d3f4  mov     edi, eax
0x18004d3f6  test    eax, eax
0x18004d3f8  jns     short loc_18004D443
0x18004d3fa  mov     rcx, [rbp+168h]; this
0x18004d401  mov     r9d, eax; char *
0x18004d404  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004d40b  mov     edx, 4Eh ; 'N'; void *
0x18004d410  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d415  nop
0x18004d416  lea     rcx, [rsp+260h+var_230]
0x18004d41b  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004d420  nop
0x18004d421  lea     rcx, [rsp+260h+var_220]
0x18004d426  call    ??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)
0x18004d42b  nop
0x18004d42c  lea     rcx, [rsp+260h+var_228]
0x18004d431  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004d436  nop
0x18004d437  lea     rcx, [rsp+260h+var_210]
0x18004d43c  call    ??1?$shared_ptr@$$CBVEtwEventRecordWrapper@AssignedAccess@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>::~shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>(void)
0x18004d441  jmp     short loc_18004D4AE
0x18004d443  mov     rdi, [rsp+260h+var_218]
0x18004d448  mov     rax, [rdi]
0x18004d44b  xor     r8d, r8d
0x18004d44e  mov     rdx, [rsp+260h+var_230]
0x18004d453  mov     rcx, rdi
0x18004d456  mov     rax, [rax+18h]
0x18004d45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d45f  mov     esi, eax
0x18004d461  test    eax, eax
0x18004d463  jns     short loc_18004D4DF
0x18004d465  mov     rcx, [rbp+168h]; this
0x18004d46c  mov     r9d, eax; char *
0x18004d46f  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004d476  mov     edx, 4Fh ; 'O'; void *
0x18004d47b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d480  nop
0x18004d481  lea     rcx, [rsp+260h+var_230]
0x18004d486  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004d48b  nop
0x18004d48c  lea     rcx, [rsp+260h+var_220]
0x18004d491  call    ??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)
0x18004d496  nop
0x18004d497  lea     rcx, [rsp+260h+var_228]
0x18004d49c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004d4a1  nop
0x18004d4a2  lea     rcx, [rsp+260h+var_210]
0x18004d4a7  call    ??1?$shared_ptr@$$CBVEtwEventRecordWrapper@AssignedAccess@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>::~shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>(void)
0x18004d4ac  mov     edi, esi
0x18004d4ae  lea     rcx, [rsp+260h+var_218]
0x18004d4b3  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004d4b8  nop
0x18004d4b9  lea     rcx, [rbp+160h+var_180]; this
0x18004d4bd  call    ??1MdmTaskWorker_Start@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::MdmTaskWorker_Start::~MdmTaskWorker_Start(void)
0x18004d4c2  mov     eax, edi
0x18004d4c4  mov     rcx, [rbp+160h+var_30]
0x18004d4cb  xor     rcx, rsp; StackCookie
0x18004d4ce  call    __security_check_cookie
0x18004d4d3  add     rsp, 248h
0x18004d4da  pop     rdi
0x18004d4db  pop     rsi
0x18004d4dc  pop     rbx
0x18004d4dd  pop     rbp
0x18004d4de  retn
0x18004d4df  mov     rsi, [rbx]
0x18004d4e2  mov     [rbx], rdi
0x18004d4e5  test    rdi, rdi
0x18004d4e8  jz      short loc_18004D4F9
0x18004d4ea  mov     rax, [rdi]
0x18004d4ed  mov     rcx, rdi
0x18004d4f0  mov     rax, [rax+8]
0x18004d4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4f9  test    rsi, rsi
0x18004d4fc  jz      short loc_18004D50E
0x18004d4fe  mov     rax, [rsi]
0x18004d501  mov     rcx, rsi
0x18004d504  mov     rax, [rax+10h]
0x18004d508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d50d  nop
0x18004d50e  lea     rcx, [rbx+8]
0x18004d512  lea     rax, [rsp+260h+var_228]
0x18004d517  cmp     rcx, rax
0x18004d51a  jz      short loc_18004D52F
0x18004d51c  mov     rdx, [rsp+260h+var_228]
0x18004d521  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004d526  mov     [rsp+260h+var_228], 0
0x18004d52f  lea     rcx, [rbx+10h]
0x18004d533  lea     rax, [rsp+260h+var_210]
0x18004d538  cmp     rcx, rax
0x18004d53b  jz      short loc_18004D547
0x18004d53d  lea     rdx, [rsp+260h+var_210]
0x18004d542  call    ??4?$shared_ptr@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z
0x18004d547  lea     rcx, [rbx+20h]
0x18004d54b  lea     rax, [rsp+260h+var_220]
0x18004d550  cmp     rcx, rax
0x18004d553  jz      short loc_18004D568
0x18004d555  mov     rdx, [rsp+260h+var_220]
0x18004d55a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUevent_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(wil::details::event_watcher_state *)
0x18004d55f  mov     [rsp+260h+var_220], 0
0x18004d568  lea     rcx, [rbp+160h+var_180]
0x18004d56c  call    ?Stop@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004d571  nop
0x18004d572  lea     rcx, [rsp+260h+var_230]
0x18004d577  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004d57c  nop
0x18004d57d  lea     rcx, [rsp+260h+var_220]
0x18004d582  call    ??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)
0x18004d587  nop
0x18004d588  lea     rcx, [rsp+260h+var_228]
0x18004d58d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004d592  nop
0x18004d593  lea     rcx, [rsp+260h+var_210]
0x18004d598  call    ??1?$shared_ptr@$$CBVEtwEventRecordWrapper@AssignedAccess@Internal@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>::~shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>(void)
0x18004d59d  nop
0x18004d59e  lea     rcx, [rsp+260h+var_218]
0x18004d5a3  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18004d5a8  nop
0x18004d5a9  lea     rcx, [rbp+160h+var_180]; this
0x18004d5ad  call    ??1MdmTaskWorker_Start@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::MdmTaskWorker_Start::~MdmTaskWorker_Start(void)
0x18004d5b2  xor     eax, eax
0x18004d5b4  jmp     loc_18004D4C4
0x18004d5b9  mov     rcx, [rbp+168h]; this
0x18004d5c0  mov     edx, 1CC8h; void *
0x18004d5c5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
