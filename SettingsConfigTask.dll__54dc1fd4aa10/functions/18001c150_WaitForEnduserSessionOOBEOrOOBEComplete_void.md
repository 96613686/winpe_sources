# WaitForEnduserSessionOOBEOrOOBEComplete(void)

- ea: `0x18001c150`
- end: `0x18001c36d`
- name: `?WaitForEnduserSessionOOBEOrOOBEComplete@@YAJXZ`
- size: `541`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c380`

## callees

- `0x1800021d0`
- `0x1800025d8`
- `0x18000458c`
- `0x1800046b0`
- `0x180005c3c`
- `0x1800120e4`
- `0x1800125cc`
- `0x1800125e8`
- `0x180012820`
- `0x1800129f4`
- `0x180012ea0`
- `0x1800197b0`
- `0x18001c150`
- `0x18001c8d0`
- `0x18001d718`
- `0x18001d7e8`
- `0x18001d840`
- `0x18001e1ac`
- `0x180020f74`
- `0x1800215e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c2cc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c2cc`

## string_xrefs

- `0x18001c2b1`: `pcshell\shell\settings\settingsconfigtask\lib\settingsconfigtaskhandler.cpp`
- `0x18001c2e1`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 WaitForEnduserSessionOOBEOrOOBEComplete(void)
{
  void **v0; // rax
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // ebx
  char *v3; // rax
  _QWORD *v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD v9; // eax
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-69h]
  _QWORD *v12; // [rsp+30h] [rbp-59h] BYREF
  char *v13; // [rsp+38h] [rbp-51h] BYREF
  HANDLE hHandle; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v15[16]; // [rsp+48h] [rbp-41h] BYREF
  int v16; // [rsp+58h] [rbp-31h] BYREF
  _QWORD v17[14]; // [rsp+60h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v13 = 0;
  v0 = tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data((void **)&v13);
  tip2::details::shared_data<0,0,0>::start((char *)*v0 + 8, v15);
  hHandle = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)&hHandle, 1);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    v3 = (char *)operator new(0x20u);
    winrt::impl::implements_delegate_base::implements_delegate_base((winrt::impl::implements_delegate_base *)(v3 + 8));
    v4[2] = &hHandle;
    v4[3] = &v13;
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *v4 = off_180025340;
    v12 = v4;
    winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceStateChanged(v15, v5, &v12);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
    v17[0] = off_180025360;
    v17[1] = &hHandle;
    v17[2] = &v13;
    v17[13] = v17;
    v12 = 0;
    wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(
      (__int64 *)&v12,
      v6,
      v7,
      v8,
      (__int64)&v16);
    wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(&v16);
    if ( !v12 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"pcshell\\shell\\settings\\settingsconfigtask\\lib\\settingsconfigtaskhandler.cpp",
        (const char *)0x8007000ELL,
        v11);
    v9 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
    if ( v9 != 258 && v9 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v10);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v12);
    __1__factory_event_revoker_UISystemSetupInfoStatics_Profile_System_Windows_winrt___MP8type___abi_UISystemSetupInfoStatics_Profile_System_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BEA_AA_impl_winrt__QEAA_XZ(v15);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::operator->(
                             &v13,
                             &v12)
              + 272LL) = 5;
    tip2::test_data_control<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>(&v12);
    if ( v13 )
      tip2::details::shared_data<0,0,0>::complete_without_lock(v13 + 8);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>(&v13);
    return 0;
  }
  else
  {
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::operator->(
                             &v13,
                             &v12)
              + 272LL) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>(&v12);
    if ( v13 )
      tip2::details::shared_data<0,0,0>::complete_without_lock(v13 + 8);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    wil::com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>(&v13);
    return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
}

```

## disassembly

```asm
0x18001c150  mov     [rsp-8+arg_0], rbx
0x18001c155  push    rbp
0x18001c156  lea     rbp, [rsp-57h]
0x18001c15b  sub     rsp, 0E0h
0x18001c162  mov     rax, cs:__security_cookie
0x18001c169  xor     rax, rsp
0x18001c16c  mov     [rbp+57h+var_10], rax
0x18001c170  mov     [rbp+57h+var_A8], 0
0x18001c178  lea     rcx, [rbp+57h+var_A8]
0x18001c17c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(void)
0x18001c181  mov     rcx, [rax]
0x18001c184  add     rcx, 8
0x18001c188  lea     rdx, [rbp+57h+var_98]
0x18001c18c  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18001c191  nop
0x18001c192  mov     [rbp+57h+hHandle], 0
0x18001c19a  mov     edx, 1
0x18001c19f  lea     rcx, [rbp+57h+hHandle]
0x18001c1a3  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001c1a8  mov     ebx, eax
0x18001c1aa  test    eax, eax
0x18001c1ac  jns     short loc_18001C1FE
0x18001c1ae  lea     rdx, [rbp+57h+var_B0]
0x18001c1b2  lea     rcx, [rbp+57h+var_A8]
0x18001c1b6  call    ??C?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::operator->(void)
0x18001c1bb  mov     rcx, [rax]
0x18001c1be  mov     dword ptr [rcx+110h], 2
0x18001c1c8  lea     rcx, [rbp+57h+var_B0]
0x18001c1cc  call    ??1?$test_data_control@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>(void)
0x18001c1d1  mov     rcx, [rbp+57h+var_A8]
0x18001c1d5  test    rcx, rcx
0x18001c1d8  jz      short loc_18001C1E4
0x18001c1da  add     rcx, 8
0x18001c1de  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18001c1e3  nop
0x18001c1e4  lea     rcx, [rbp+57h+hHandle]
0x18001c1e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c1ed  nop
0x18001c1ee  lea     rcx, [rbp+57h+var_A8]
0x18001c1f2  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>(void)
0x18001c1f7  mov     eax, ebx
0x18001c1f9  jmp     loc_18001C350
0x18001c1fe  mov     ecx, 20h ; ' '; Size
0x18001c203  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c208  mov     r8, rax
0x18001c20b  mov     [rbp+57h+var_B0], rax
0x18001c20f  lea     rcx, [rax+8]; this
0x18001c213  call    ??0implements_delegate_base@impl@winrt@@QEAA@XZ; winrt::impl::implements_delegate_base::implements_delegate_base(void)
0x18001c218  lea     rax, [rbp+57h+hHandle]
0x18001c21c  mov     [r8+10h], rax
0x18001c220  lea     rax, [rbp+57h+var_A8]
0x18001c224  mov     [r8+18h], rax
0x18001c228  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001c22f  lea     rax, off_180025340
0x18001c236  mov     [r8], rax
0x18001c239  mov     [rbp+57h+var_B0], r8
0x18001c23d  lea     r8, [rbp+57h+var_B0]
0x18001c241  lea     rcx, [rbp+57h+var_98]
0x18001c245  call    ?OutOfBoxExperienceStateChanged@SystemSetupInfo@Profile@System@Windows@winrt@@SA@Uauto_revoke_t@5@AEBU?$EventHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@45@@Z; winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceStateChanged(winrt::auto_revoke_t,winrt::Windows::Foundation::EventHandler<winrt::Windows::Foundation::IInspectable> const &)
0x18001c24a  nop
0x18001c24b  lea     rcx, [rbp+57h+var_B0]
0x18001c24f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c254  lea     rax, off_180025360
0x18001c25b  mov     [rbp+57h+var_80], rax
0x18001c25f  lea     rax, [rbp+57h+hHandle]
0x18001c263  mov     [rbp+57h+var_78], rax
0x18001c267  lea     rax, [rbp+57h+var_A8]
0x18001c26b  mov     [rbp+57h+var_70], rax
0x18001c26f  lea     rax, [rbp+57h+var_80]
0x18001c273  mov     [rbp+57h+var_18], rax
0x18001c277  mov     [rbp+57h+var_B0], 0
0x18001c27f  lea     rax, [rbp+57h+var_88]
0x18001c283  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001c288  lea     rcx, [rbp+57h+var_B0]
0x18001c28c  call    ?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18001c291  nop
0x18001c292  lea     rcx, [rbp+57h+var_88]
0x18001c296  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x18001c29b  cmp     [rbp+57h+var_B0], 0
0x18001c2a0  setz    al
0x18001c2a3  mov     rcx, [rbp+5Fh]; this
0x18001c2a7  test    al, al
0x18001c2a9  jz      short loc_18001C2C2
0x18001c2ab  mov     r9d, 8007000Eh; char *
0x18001c2b1  lea     r8, aPcshellShellSe; "pcshell\\shell\\settings\\settingsconfi"...
0x18001c2b8  mov     edx, 99h; void *
0x18001c2bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c2c2  xor     r8d, r8d; bAlertable
0x18001c2c5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c2c8  mov     rcx, [rbp+57h+hHandle]; hHandle
0x18001c2cc  call    cs:__imp_WaitForSingleObjectEx
0x18001c2d2  cmp     eax, 102h
0x18001c2d7  jz      short loc_18001C2F3
0x18001c2d9  test    eax, eax
0x18001c2db  jz      short loc_18001C2F3
0x18001c2dd  mov     rcx, [rbp+5Fh]; this
0x18001c2e1  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c2e8  mov     edx, 0B0Fh; void *
0x18001c2ed  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001c2f3  lea     rcx, [rbp+57h+var_B0]
0x18001c2f7  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x18001c2fc  lea     rcx, [rbp+57h+var_98]
0x18001c300  call    ??1?$factory_event_revoker@UISystemSetupInfoStatics@Profile@System@Windows@winrt@@$MP8type@?$abi@UISystemSetupInfoStatics@Profile@System@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BEA@AA@impl@winrt@@QEAA@XZ
0x18001c305  lea     rdx, [rbp+57h+var_B0]
0x18001c309  lea     rcx, [rbp+57h+var_A8]
0x18001c30d  call    ??C?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::operator->(void)
0x18001c312  mov     rcx, [rax]
0x18001c315  mov     dword ptr [rcx+110h], 5
0x18001c31f  lea     rcx, [rbp+57h+var_B0]
0x18001c323  call    ??1?$test_data_control@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>(void)
0x18001c328  mov     rcx, [rbp+57h+var_A8]
0x18001c32c  test    rcx, rcx
0x18001c32f  jz      short loc_18001C33B
0x18001c331  add     rcx, 8
0x18001c335  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18001c33a  nop
0x18001c33b  lea     rcx, [rbp+57h+hHandle]
0x18001c33f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c344  nop
0x18001c345  lea     rcx, [rbp+57h+var_A8]
0x18001c349  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>,wil::err_returncode_policy>(void)
0x18001c34e  xor     eax, eax
0x18001c350  mov     rcx, [rbp+57h+var_10]
0x18001c354  xor     rcx, rsp; StackCookie
0x18001c357  call    __security_check_cookie
0x18001c35c  mov     rbx, [rsp+0E0h+arg_0]
0x18001c364  add     rsp, 0E0h
0x18001c36b  pop     rbp
0x18001c36c  retn
```
