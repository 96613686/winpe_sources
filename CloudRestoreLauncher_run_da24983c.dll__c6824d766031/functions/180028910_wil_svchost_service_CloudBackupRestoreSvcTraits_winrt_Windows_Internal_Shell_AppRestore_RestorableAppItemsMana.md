# wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>::start(void)

- ea: `0x180028910`
- end: `0x180028a4e`
- name: `?start@?$svchost_service@UCloudBackupRestoreSvcTraits@@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@34567@UAppRestoreOrchestrator@34567@@wil@@AEAAXXZ`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180028628`

## callees

- `0x18000cbbc`
- `0x18001d234`
- `0x180027cf8`
- `0x180028094`
- `0x180028210`
- `0x180028584`
- `0x1800288ac`
- `0x180028910`
- `0x180028b14`
- `0x18012d010`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x18002894d`
- `combase!__imp_CoGetSharedServiceId` at `0x18002894d`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180028991`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180028991`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>::start(
        void *a1)
{
  unsigned int SharedServiceId; // eax
  __int64 v2; // rdx
  unsigned int v3; // eax
  __int64 v4; // rax
  __int64 v5; // rdx
  void (__fastcall *v6)(char *, const WCHAR *, __int64, __int64 (__fastcall *)(void *, unsigned __int8), __int128 *, int); // rdi
  __int64 v7; // rbx
  int v9; // [rsp+40h] [rbp-20h] BYREF
  __int128 v10; // [rsp+48h] [rbp-18h]
  void *v11; // [rsp+80h] [rbp+20h] BYREF
  char v12; // [rsp+88h] [rbp+28h] BYREF

  v11 = a1;
  wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>::update_status(
    &g_service,
    2,
    0);
  LODWORD(v11) = 0;
  v9 = 0;
  v10 = 0;
  SharedServiceId = CoGetSharedServiceId(&v11);
  winrt::check_hresult(&v12, SharedServiceId, &v9);
  wil::details::g_service_id = (unsigned int)v11;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &xmmword_18017BFC8,
    v2,
    0);
  v9 = 0;
  v10 = 0;
  v3 = CoRegisterServerShutdownDelay(xmmword_18017BFC8, 5000);
  winrt::check_hresult(&v11, v3, &v9);
  v11 = operator new(0x18u);
  v4 = wil::details::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>(v11);
  v11 = 0;
  v5 = *((_QWORD *)&xmmword_18017BFC8 + 1);
  *((_QWORD *)&xmmword_18017BFC8 + 1) = v4;
  if ( v5 )
    std::default_delete<wil::details::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>>::operator()();
  std::unique_ptr<wil::details::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>>::~unique_ptr<wil::details::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>>(&v11);
  v6 = *(void (__fastcall **)(char *, const WCHAR *, __int64, __int64 (__fastcall *)(void *, unsigned __int8), __int128 *, int))(g_service + 192);
  v7 = xmmword_18017BFC8;
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (char *)&g_service + 8,
    0);
  v6(
    (char *)&g_service + 8,
    L"CloudBackupRestoreSvc",
    v7,
    _lambda_76faea2acde04a1933f73c23dfee4fe9_::_lambda_invoker_cdecl_,
    &g_service,
    8);
  return wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>::update_status(
           &g_service,
           4,
           0);
}

```

## disassembly

```asm
0x180028910  mov     [rsp-18h+arg_10], rbx
0x180028915  mov     [rsp-18h+arg_0], rcx
0x18002891a  push    rbp
0x18002891b  push    rsi
0x18002891c  push    rdi
0x18002891d  mov     rbp, rsp
0x180028920  sub     rsp, 60h
0x180028924  xor     ebx, ebx
0x180028926  xor     r8d, r8d
0x180028929  lea     edx, [rbx+2]
0x18002892c  lea     rsi, ?g_service@@3V?$svchost_service@UCloudBackupRestoreSvcTraits@@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@34567@UAppRestoreOrchestrator@34567@@wil@@A; wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator> g_service
0x180028933  mov     rcx, rsi
0x180028936  call    ?update_status@?$svchost_service@UCloudBackupRestoreSvcTraits@@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@34567@UAppRestoreOrchestrator@34567@@wil@@AEAAXKK@Z; wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>::update_status(ulong,ulong)
0x18002893b  mov     dword ptr [rbp+arg_0], ebx
0x18002893e  mov     [rbp+var_20], ebx
0x180028941  xorps   xmm0, xmm0
0x180028944  movdqu  [rbp+var_18], xmm0
0x180028949  lea     rcx, [rbp+arg_0]
0x18002894d  call    cs:__imp_CoGetSharedServiceId
0x180028953  lea     r8, [rbp+var_20]
0x180028957  mov     edx, eax
0x180028959  lea     rcx, [rbp+arg_8]
0x18002895d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180028962  mov     eax, dword ptr [rbp+arg_0]
0x180028965  mov     cs:?g_service_id@details@wil@@3KA, eax; ulong wil::details::g_service_id
0x18002896b  xor     r8d, r8d
0x18002896e  lea     rcx, xmmword_18017BFC8
0x180028975  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002897a  mov     [rbp+var_20], ebx
0x18002897d  xorps   xmm0, xmm0
0x180028980  movdqu  [rbp+var_18], xmm0
0x180028985  mov     edx, 1388h
0x18002898a  mov     rcx, qword ptr cs:xmmword_18017BFC8
0x180028991  call    cs:__imp_CoRegisterServerShutdownDelay
0x180028997  lea     r8, [rbp+var_20]
0x18002899b  mov     edx, eax
0x18002899d  lea     rcx, [rbp+arg_0]
0x1800289a1  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800289a6  lea     ecx, [rbx+18h]; Size
0x1800289a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800289ae  mov     [rbp+arg_0], rax
0x1800289b2  mov     rcx, rax
0x1800289b5  call    ??0?$svchost_module@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@23456@UAppRestoreOrchestrator@23456@@details@wil@@QEAA@XZ; wil::details::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>(void)
0x1800289ba  nop
0x1800289bb  mov     [rbp+arg_0], rbx
0x1800289bf  mov     rdx, qword ptr cs:xmmword_18017BFC8+8
0x1800289c6  mov     qword ptr cs:xmmword_18017BFC8+8, rax
0x1800289cd  test    rdx, rdx
0x1800289d0  jz      short loc_1800289D7
0x1800289d2  call    ??R?$default_delete@V?$svchost_module@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@23456@UAppRestoreOrchestrator@23456@@details@wil@@@std@@QEBAXPEAV?$svchost_module@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@23456@UAppRestoreOrchestrator@23456@@details@wil@@@Z; std::default_delete<wil::details::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>>::operator()(wil::details::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator> *)
0x1800289d7  lea     rcx, [rbp+arg_0]
0x1800289db  call    ??1?$unique_ptr@V?$svchost_module@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@23456@UAppRestoreOrchestrator@23456@@details@wil@@U?$default_delete@V?$svchost_module@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@23456@UAppRestoreOrchestrator@23456@@details@wil@@@std@@@std@@QEAA@XZ; std::unique_ptr<wil::details::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>>::~unique_ptr<wil::details::svchost_module<winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>>(void)
0x1800289e0  mov     rax, qword ptr cs:?g_service@@3V?$svchost_service@UCloudBackupRestoreSvcTraits@@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@34567@UAppRestoreOrchestrator@34567@@wil@@A; wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator> g_service
0x1800289e7  mov     rdi, [rax+0C0h]
0x1800289ee  mov     rbx, qword ptr cs:xmmword_18017BFC8
0x1800289f5  xor     edx, edx
0x1800289f7  lea     rcx, ?g_service@@3V?$svchost_service@UCloudBackupRestoreSvcTraits@@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@34567@UAppRestoreOrchestrator@34567@@wil@@A+8; wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator> g_service
0x1800289fe  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?UnregisterWait@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180028a03  mov     [rsp+60h+var_38], 8
0x180028a0b  mov     [rsp+60h+var_40], rsi
0x180028a10  lea     r9, ?_lambda_invoker_cdecl_@_lambda_76faea2acde04a1933f73c23dfee4fe9_@@CA@PEAXE@Z; _lambda_76faea2acde04a1933f73c23dfee4fe9_::_lambda_invoker_cdecl_(void *,uchar)
0x180028a17  mov     r8, rbx
0x180028a1a  lea     rdx, ServiceName; "CloudBackupRestoreSvc"
0x180028a21  lea     rcx, ?g_service@@3V?$svchost_service@UCloudBackupRestoreSvcTraits@@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@34567@UAppRestoreOrchestrator@34567@@wil@@A+8; wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator> g_service
0x180028a28  mov     rax, rdi
0x180028a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a30  xor     r8d, r8d
0x180028a33  lea     edx, [r8+4]
0x180028a37  mov     rcx, rsi
0x180028a3a  mov     rbx, [rsp+60h+arg_10]
0x180028a42  add     rsp, 60h
0x180028a46  pop     rdi
0x180028a47  pop     rsi
0x180028a48  pop     rbp
0x180028a49  jmp     ?update_status@?$svchost_service@UCloudBackupRestoreSvcTraits@@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@34567@UAppRestoreOrchestrator@34567@@wil@@AEAAXKK@Z; wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>::update_status(ulong,ulong)
```
