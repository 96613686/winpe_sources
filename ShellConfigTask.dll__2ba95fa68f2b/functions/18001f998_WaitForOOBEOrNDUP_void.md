# WaitForOOBEOrNDUP(void)

- ea: `0x18001f998`
- end: `0x18001fd3c`
- name: `?WaitForOOBEOrNDUP@@YAJXZ`
- size: `932`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a754`

## callees

- `0x180002590`
- `0x180002998`
- `0x180006cb8`
- `0x18000c5d4`
- `0x180013b6c`
- `0x180013d90`
- `0x180014800`
- `0x18001cea8`
- `0x18001d6d0`
- `0x18001d768`
- `0x18001f998`
- `0x18002189c`
- `0x1800219c0`
- `0x180021cb8`
- `0x1800222c0`
- `0x18002334c`
- `0x1800248a0`
- `0x180024f28`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fa7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fa7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fc4b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001fbb9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001fbb9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001fb89`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001fb89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fbec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fa50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fbec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fc1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fa90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fc9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fa90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fc9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fccd`

## string_xrefs

- `0x18001fced`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001fd14`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001fcff`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001fd2a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 WaitForOOBEOrNDUP(void)
{
  _QWORD *v0; // rax
  int v1; // esi
  __int64 v2; // rbx
  char *v3; // rbx
  const char *v4; // r9
  _DWORD *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  struct wil::details::registry_watcher_state *v9; // rdx
  DWORD v10; // eax
  const char *v11; // r9
  const char *v12; // r9
  __int64 v13; // rbx
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  __int64 v15; // rbx
  const char *v16; // r9
  void *v17; // rbx
  wil::details *v18; // [rsp+30h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-71h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-69h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v22[13]; // [rsp+60h] [rbp-49h] BYREF
  _QWORD *v23; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  pv = 0;
  v0 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(&pv);
  tip2::details::shared_data<0,0,0>::start(*v0 + 8LL, v21);
  hObject = 0;
  v1 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &hObject,
         1);
  if ( v1 >= 0 )
  {
    v6 = operator new(0x20u);
    v6[2] = 1;
    *((_QWORD *)v6 + 2) = &hObject;
    *((_QWORD *)v6 + 3) = &pv;
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *(_QWORD *)v6 = off_1800342C8;
    v18 = (wil::details *)v6;
    winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceStateChanged(v21, v7, &v18);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
    v22[0] = off_180034310;
    v22[1] = &hObject;
    v22[2] = &pv;
    v23 = v22;
    wil::make_registry_watcher_nothrow(&v18, v8, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE");
    if ( v18 )
      wil::details::delete_registry_watcher_state(v18, v9);
    if ( v23 )
      (*(void (__fastcall **)(_QWORD *))(*v23 + 24LL))(v23);
    while ( 1 )
    {
      v10 = WaitForSingleObjectEx(hObject, 0xFFFFFFFF, 0);
      if ( v10 != 258 && v10 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB0F,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v11);
      if ( IsNDUPComplete()
        || (unsigned int)winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceState() == 2 )
      {
        break;
      }
      if ( !ResetEvent(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA06,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v12);
    }
    v13 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(&pv);
    v18 = (wil::details *)v13;
    if ( v13 )
      _InterlockedAdd((volatile signed __int32 *)(v13 + 280), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 200));
    ++*(_DWORD *)(v13 + 240);
    *(_DWORD *)(v13 + 272) = 5;
    tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(&v18);
    v14 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      LODWORD(v14[1].SpinCount) |= 0x300u;
      if ( *(_QWORD *)&v14[6].LockCount )
        tip2::details::shared_data<0,0,0>::complete_helper(&v14->LockCount, 2);
      if ( v14 != (struct _RTL_CRITICAL_SECTION *)-200LL )
        LeaveCriticalSection(v14 + 5);
    }
    v15 = v21[0];
    if ( v21[0] )
    {
      v18 = (wil::details *)v21[0];
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v21[0] + 8LL))(v21[0]);
       winrt::impl::abi<winrt::Windows::System::Profile::ISystemSetupInfoStatics,void>::type::`vcall'{64,{flat}}(
        v15,
        v21[1]);
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v21);
    }
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    v17 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(v17);
      CoTaskMemFree(v17);
    }
    return 0;
  }
  else
  {
    v2 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(&pv);
    v18 = (wil::details *)v2;
    if ( v2 )
      _InterlockedAdd((volatile signed __int32 *)(v2 + 280), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
    ++*(_DWORD *)(v2 + 240);
    *(_DWORD *)(v2 + 272) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(&v18);
    v3 = (char *)pv;
    if ( pv )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      *((_DWORD *)v3 + 18) |= 0x300u;
      if ( *((_QWORD *)v3 + 31) )
        tip2::details::shared_data<0,0,0>::complete_helper(v3 + 8, 2);
      if ( v3 != (char *)-200LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)v3 + 5);
      v3 = (char *)pv;
    }
    if ( hObject )
    {
      if ( !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v4);
      v3 = (char *)pv;
    }
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 70, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(v3);
        CoTaskMemFree(v3);
      }
    }
    return (unsigned int)v1;
  }
}

```

## disassembly

```asm
0x18001f998  push    rbp
0x18001f99a  push    rbx
0x18001f99b  push    rsi
0x18001f99c  push    rdi
0x18001f99d  lea     rbp, [rsp-3Fh]
0x18001f9a2  sub     rsp, 0E8h
0x18001f9a9  mov     rax, cs:__security_cookie
0x18001f9b0  xor     rax, rsp
0x18001f9b3  mov     [rbp+57h+var_30], rax
0x18001f9b7  mov     [rbp+57h+pv], 0
0x18001f9bf  lea     rcx, [rbp+57h+pv]
0x18001f9c3  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(void)
0x18001f9c8  mov     rcx, [rax]
0x18001f9cb  add     rcx, 8
0x18001f9cf  lea     rdx, [rbp+57h+var_B8]
0x18001f9d3  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18001f9d8  nop
0x18001f9d9  mov     [rbp+57h+hObject], 0
0x18001f9e1  mov     edi, 1
0x18001f9e6  mov     edx, edi
0x18001f9e8  lea     rcx, [rbp+57h+hObject]
0x18001f9ec  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001f9f1  mov     esi, eax
0x18001f9f3  test    eax, eax
0x18001f9f5  jns     loc_18001FAD3
0x18001f9fb  lea     rcx, [rbp+57h+pv]
0x18001f9ff  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(void)
0x18001fa04  mov     rbx, [rax]
0x18001fa07  mov     [rbp+57h+var_D0], rbx
0x18001fa0b  test    rbx, rbx
0x18001fa0e  jz      short loc_18001FA17
0x18001fa10  lock add [rbx+118h], edi
0x18001fa17  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001fa1e  call    cs:__imp_EnterCriticalSection
0x18001fa24  add     [rbx+0F0h], edi
0x18001fa2a  mov     dword ptr [rbx+110h], 2
0x18001fa34  lea     rcx, [rbp+57h+var_D0]
0x18001fa38  call    ??1?$test_data_control@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(void)
0x18001fa3d  mov     rbx, [rbp+57h+pv]
0x18001fa41  test    rbx, rbx
0x18001fa44  jz      short loc_18001FA87
0x18001fa46  lea     rdi, [rbx+0C8h]
0x18001fa4d  mov     rcx, rdi; lpCriticalSection
0x18001fa50  call    cs:__imp_EnterCriticalSection
0x18001fa56  or      dword ptr [rbx+48h], 300h
0x18001fa5d  cmp     qword ptr [rbx+0F8h], 0
0x18001fa65  jz      short loc_18001FA75
0x18001fa67  mov     edx, 2
0x18001fa6c  lea     rcx, [rbx+8]
0x18001fa70  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001fa75  test    rdi, rdi
0x18001fa78  jz      short loc_18001FA83
0x18001fa7a  mov     rcx, rdi; lpCriticalSection
0x18001fa7d  call    cs:__imp_LeaveCriticalSection
0x18001fa83  mov     rbx, [rbp+57h+pv]
0x18001fa87  mov     rcx, [rbp+57h+hObject]; hObject
0x18001fa8b  test    rcx, rcx
0x18001fa8e  jz      short loc_18001FAA6
0x18001fa90  call    cs:__imp_CloseHandle
0x18001fa96  mov     rcx, [rbp+5Fh]; this
0x18001fa9a  test    eax, eax
0x18001fa9c  jz      loc_18001FD14
0x18001faa2  mov     rbx, [rbp+57h+pv]
0x18001faa6  test    rbx, rbx
0x18001faa9  jz      short loc_18001FACC
0x18001faab  or      eax, 0FFFFFFFFh
0x18001faae  lock xadd [rbx+118h], eax
0x18001fab6  cmp     eax, 1
0x18001fab9  jnz     short loc_18001FACC
0x18001fabb  mov     rcx, rbx
0x18001fabe  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x18001fac3  mov     rcx, rbx; pv
0x18001fac6  call    cs:__imp_CoTaskMemFree
0x18001facc  mov     eax, esi
0x18001face  jmp     loc_18001FCD5
0x18001fad3  mov     ecx, 20h ; ' '; Size
0x18001fad8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fadd  mov     [rbp+57h+var_D0], rax
0x18001fae1  mov     [rax+8], edi
0x18001fae4  lea     rcx, [rbp+57h+hObject]
0x18001fae8  mov     [rax+10h], rcx
0x18001faec  lea     rcx, [rbp+57h+pv]
0x18001faf0  mov     [rax+18h], rcx
0x18001faf4  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001fafb  lea     rcx, off_1800342C8
0x18001fb02  mov     [rax], rcx
0x18001fb05  mov     [rbp+57h+var_D0], rax
0x18001fb09  lea     r8, [rbp+57h+var_D0]
0x18001fb0d  lea     rcx, [rbp+57h+var_B8]
0x18001fb11  call    ?OutOfBoxExperienceStateChanged@SystemSetupInfo@Profile@System@Windows@winrt@@SA@Uauto_revoke_t@5@AEBU?$EventHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@45@@Z; winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceStateChanged(winrt::auto_revoke_t,winrt::Windows::Foundation::EventHandler<winrt::Windows::Foundation::IInspectable> const &)
0x18001fb16  nop
0x18001fb17  lea     rcx, [rbp+57h+var_D0]
0x18001fb1b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fb20  lea     rax, off_180034310
0x18001fb27  mov     [rbp+57h+var_A0], rax
0x18001fb2b  lea     rax, [rbp+57h+hObject]
0x18001fb2f  mov     [rbp+57h+var_98], rax
0x18001fb33  lea     rax, [rbp+57h+pv]
0x18001fb37  mov     [rbp+57h+var_90], rax
0x18001fb3b  lea     rax, [rbp+57h+var_A0]
0x18001fb3f  mov     [rbp+57h+var_38], rax
0x18001fb43  lea     rax, [rbp+57h+var_A8]
0x18001fb47  mov     [rsp+100h+var_E0], rax
0x18001fb4c  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001fb53  lea     rcx, [rbp+57h+var_D0]
0x18001fb57  call    ?make_registry_watcher_nothrow@wil@@YA?AV?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@1@PEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::make_registry_watcher_nothrow(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18001fb5c  mov     rcx, [rbp+57h+var_D0]; this
0x18001fb60  test    rcx, rcx
0x18001fb63  jz      short loc_18001FB6A
0x18001fb65  call    ?delete_registry_watcher_state@details@wil@@YAXPEAUregistry_watcher_state@12@@Z; wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *)
0x18001fb6a  mov     rcx, [rbp+57h+var_38]
0x18001fb6e  test    rcx, rcx
0x18001fb71  jz      short loc_18001FB7F
0x18001fb73  mov     rax, [rcx]
0x18001fb76  mov     rax, [rax+18h]
0x18001fb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb7f  xor     r8d, r8d; bAlertable
0x18001fb82  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001fb85  mov     rcx, [rbp+57h+hObject]; hHandle
0x18001fb89  call    cs:__imp_WaitForSingleObjectEx
0x18001fb8f  cmp     eax, 102h
0x18001fb94  jz      short loc_18001FB9E
0x18001fb96  test    eax, eax
0x18001fb98  jnz     loc_18001FD26
0x18001fb9e  call    ?IsNDUPComplete@@YA_NXZ; IsNDUPComplete(void)
0x18001fba3  test    al, al
0x18001fba5  jnz     short loc_18001FBC9
0x18001fba7  call    ?OutOfBoxExperienceState@SystemSetupInfo@Profile@System@Windows@winrt@@SA@XZ; winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceState(void)
0x18001fbac  cmp     eax, 2
0x18001fbaf  jz      short loc_18001FBC9
0x18001fbb1  mov     rbx, [rbp+5Fh]
0x18001fbb5  mov     rcx, [rbp+57h+hObject]; hEvent
0x18001fbb9  call    cs:__imp_ResetEvent
0x18001fbbf  test    eax, eax
0x18001fbc1  jz      loc_18001FCFF
0x18001fbc7  jmp     short loc_18001FB7F
0x18001fbc9  lea     rcx, [rbp+57h+pv]
0x18001fbcd  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(void)
0x18001fbd2  mov     rbx, [rax]
0x18001fbd5  mov     [rbp+57h+var_D0], rbx
0x18001fbd9  test    rbx, rbx
0x18001fbdc  jz      short loc_18001FBE5
0x18001fbde  lock add [rbx+118h], edi
0x18001fbe5  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001fbec  call    cs:__imp_EnterCriticalSection
0x18001fbf2  add     [rbx+0F0h], edi
0x18001fbf8  mov     dword ptr [rbx+110h], 5
0x18001fc02  lea     rcx, [rbp+57h+var_D0]
0x18001fc06  call    ??1?$test_data_control@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(void)
0x18001fc0b  mov     rbx, [rbp+57h+pv]
0x18001fc0f  test    rbx, rbx
0x18001fc12  jz      short loc_18001FC52
0x18001fc14  lea     rdi, [rbx+0C8h]
0x18001fc1b  mov     rcx, rdi; lpCriticalSection
0x18001fc1e  call    cs:__imp_EnterCriticalSection
0x18001fc24  or      dword ptr [rbx+48h], 300h
0x18001fc2b  cmp     qword ptr [rbx+0F8h], 0
0x18001fc33  jz      short loc_18001FC43
0x18001fc35  mov     edx, 2
0x18001fc3a  lea     rcx, [rbx+8]
0x18001fc3e  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001fc43  test    rdi, rdi
0x18001fc46  jz      short loc_18001FC52
0x18001fc48  mov     rcx, rdi; lpCriticalSection
0x18001fc4b  call    cs:__imp_LeaveCriticalSection
0x18001fc51  nop
0x18001fc52  mov     rbx, [rbp+57h+var_B8]
0x18001fc56  test    rbx, rbx
0x18001fc59  jz      short loc_18001FC92
0x18001fc5b  mov     [rbp+57h+var_D0], rbx
0x18001fc5f  mov     rax, [rbx]
0x18001fc62  mov     rcx, rbx
0x18001fc65  mov     rax, [rax+8]
0x18001fc69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc6e  mov     rdx, [rbp+57h+var_B0]
0x18001fc72  mov     rcx, rbx
0x18001fc75  call    ??_9type@?$abi@UISystemSetupInfoStatics@Profile@System@Windows@winrt@@X@impl@winrt@@$BEA@AA; [thunk]: winrt::impl::abi<winrt::Windows::System::Profile::ISystemSetupInfoStatics,void>::type::`vcall'{64,{flat}}
0x18001fc7a  lea     rcx, [rbp+57h+var_D0]
0x18001fc7e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fc83  test    rbx, rbx
0x18001fc86  jz      short loc_18001FC92
0x18001fc88  lea     rcx, [rbp+57h+var_B8]
0x18001fc8c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fc91  nop
0x18001fc92  mov     rcx, [rbp+57h+hObject]; hObject
0x18001fc96  test    rcx, rcx
0x18001fc99  jz      short loc_18001FCA9
0x18001fc9b  call    cs:__imp_CloseHandle
0x18001fca1  mov     rcx, [rbp+5Fh]; this
0x18001fca5  test    eax, eax
0x18001fca7  jz      short loc_18001FCED
0x18001fca9  mov     rbx, [rbp+57h+pv]
0x18001fcad  test    rbx, rbx
0x18001fcb0  jz      short loc_18001FCD3
0x18001fcb2  or      eax, 0FFFFFFFFh
0x18001fcb5  lock xadd [rbx+118h], eax
0x18001fcbd  cmp     eax, 1
0x18001fcc0  jnz     short loc_18001FCD3
0x18001fcc2  mov     rcx, rbx
0x18001fcc5  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x18001fcca  mov     rcx, rbx; pv
0x18001fccd  call    cs:__imp_CoTaskMemFree
0x18001fcd3  xor     eax, eax
0x18001fcd5  mov     rcx, [rbp+57h+var_30]
0x18001fcd9  xor     rcx, rsp; StackCookie
0x18001fcdc  call    __security_check_cookie
0x18001fce1  add     rsp, 0E8h
0x18001fce8  pop     rdi
0x18001fce9  pop     rsi
0x18001fcea  pop     rbx
0x18001fceb  pop     rbp
0x18001fcec  retn
0x18001fced  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fcf4  mov     edx, 0A0Bh; void *
0x18001fcf9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001fcff  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fd06  mov     edx, 0A06h; void *
0x18001fd0b  mov     rcx, rbx; this
0x18001fd0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001fd14  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fd1b  mov     edx, 0A0Bh; void *
0x18001fd20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001fd26  mov     rcx, [rbp+5Fh]; this
0x18001fd2a  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fd31  mov     edx, 0B0Fh; void *
0x18001fd36  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
