# WaitForEnduserSessionOOBEOrOOBEComplete(void)

- ea: `0x18001f604`
- end: `0x18001f992`
- name: `?WaitForEnduserSessionOOBEOrOOBEComplete@@YAJXZ`
- size: `910`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

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
- `0x18001d768`
- `0x18001f604`
- `0x18002062c`
- `0x18002189c`
- `0x1800219c0`
- `0x180021cb8`
- `0x18002222c`
- `0x18002334c`
- `0x1800248a0`
- `0x180024f28`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f6ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f8f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f6ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f8f6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001f810`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001f810`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f68a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f6c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f894`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f8ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f68a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f6c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f894`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f8ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f906`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f906`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f732`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f732`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f938`

## string_xrefs

- `0x18001f958`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001f96a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001f7f5`: `pcshell\shell\aix\shellconfigtask\lib\recallconfigtaskhandler.cpp`
- `0x18001f980`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 WaitForEnduserSessionOOBEOrOOBEComplete(void)
{
  __int64 *v0; // rax
  int v1; // esi
  __int64 v2; // rbx
  char *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  const char *v5; // r9
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  _DWORD *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wil::details *v11; // rbx
  DWORD v12; // eax
  struct wil::details::registry_watcher_state *v13; // rdx
  const char *v14; // r9
  __int64 v15; // rbx
  __int64 v16; // rbx
  char *v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // rdi
  const char *v19; // r9
  struct _RTL_CRITICAL_SECTION *v20; // rbx
  wil::details *v21; // [rsp+30h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-71h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-69h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v25[13]; // [rsp+60h] [rbp-49h] BYREF
  _QWORD *v26; // [rsp+C8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  pv = 0;
  v0 = tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data((__int64 *)&pv);
  tip2::details::shared_data<0,0,0>::start(*v0 + 8, v24);
  hObject = 0;
  v1 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &hObject,
         1);
  if ( v1 >= 0 )
  {
    v8 = operator new(0x20u);
    v8[2] = 1;
    *((_QWORD *)v8 + 2) = &hObject;
    *((_QWORD *)v8 + 3) = &pv;
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *(_QWORD *)v8 = off_1800342A8;
    v21 = (wil::details *)v8;
    winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceStateChanged(v24, v9, &v21);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
    v25[0] = off_1800342E8;
    v25[1] = &hObject;
    v25[2] = &pv;
    v26 = v25;
    wil::make_registry_watcher_nothrow(&v21, v10, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE");
    if ( v26 )
      (*(void (__fastcall **)(_QWORD *))(*v26 + 24LL))(v26);
    v11 = v21;
    if ( !v21 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAC,
        (int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\recallconfigtaskhandler.cpp",
        (const char *)0x8007000ELL);
    v12 = WaitForSingleObjectEx(hObject, 0xFFFFFFFF, 0);
    if ( v12 != 258 && v12 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v14);
    if ( v11 )
      wil::details::delete_registry_watcher_state(v11, v13);
    v15 = v24[0];
    if ( v24[0] )
    {
      v21 = (wil::details *)v24[0];
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v24[0] + 8LL))(v24[0]);
       winrt::impl::abi<winrt::Windows::System::Profile::ISystemSetupInfoStatics,void>::type::`vcall'{64,{flat}}(
        v15,
        v24[1]);
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v24);
    }
    v16 = *tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data((__int64 *)&pv);
    v21 = (wil::details *)v16;
    if ( v16 )
      _InterlockedAdd((volatile signed __int32 *)(v16 + 280), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 200));
    ++*(_DWORD *)(v16 + 240);
    *(_DWORD *)(v16 + 272) = 5;
    tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>((__int64 *)&v21);
    if ( pv )
    {
      v17 = (char *)pv + 8;
      v18 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      *((_DWORD *)v17 + 16) |= 0x300u;
      if ( *((_QWORD *)v17 + 30) )
        tip2::details::shared_data<0,0,0>::complete_helper((__int64)v17, 2u);
      if ( v18 )
        LeaveCriticalSection(v18);
    }
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v19);
    v20 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(v20);
      CoTaskMemFree(v20);
    }
    return 0;
  }
  else
  {
    v2 = *tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data((__int64 *)&pv);
    v21 = (wil::details *)v2;
    if ( v2 )
      _InterlockedAdd((volatile signed __int32 *)(v2 + 280), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
    ++*(_DWORD *)(v2 + 240);
    *(_DWORD *)(v2 + 272) = 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>((__int64 *)&v21);
    if ( pv )
    {
      v3 = (char *)pv + 8;
      v4 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      *((_DWORD *)v3 + 16) |= 0x300u;
      if ( *((_QWORD *)v3 + 30) )
        tip2::details::shared_data<0,0,0>::complete_helper((__int64)v3, 2u);
      if ( v4 )
        LeaveCriticalSection(v4);
    }
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v5);
    v6 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(v6);
        CoTaskMemFree(v6);
      }
    }
    return (unsigned int)v1;
  }
}

```

## disassembly

```asm
0x18001f604  push    rbp
0x18001f606  push    rbx
0x18001f607  push    rsi
0x18001f608  push    rdi
0x18001f609  lea     rbp, [rsp-3Fh]
0x18001f60e  sub     rsp, 0E8h
0x18001f615  mov     rax, cs:__security_cookie
0x18001f61c  xor     rax, rsp
0x18001f61f  mov     [rbp+57h+var_30], rax
0x18001f623  mov     [rbp+57h+pv], 0
0x18001f62b  lea     rcx, [rbp+57h+pv]
0x18001f62f  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(void)
0x18001f634  mov     rcx, [rax]
0x18001f637  add     rcx, 8
0x18001f63b  lea     rdx, [rbp+57h+var_B8]
0x18001f63f  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18001f644  nop
0x18001f645  mov     [rbp+57h+hObject], 0
0x18001f64d  mov     edi, 1
0x18001f652  mov     edx, edi
0x18001f654  lea     rcx, [rbp+57h+hObject]
0x18001f658  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001f65d  mov     esi, eax
0x18001f65f  test    eax, eax
0x18001f661  jns     loc_18001F73F
0x18001f667  lea     rcx, [rbp+57h+pv]
0x18001f66b  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(void)
0x18001f670  mov     rbx, [rax]
0x18001f673  mov     [rbp+57h+var_D0], rbx
0x18001f677  test    rbx, rbx
0x18001f67a  jz      short loc_18001F683
0x18001f67c  lock add [rbx+118h], edi
0x18001f683  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001f68a  call    cs:__imp_EnterCriticalSection
0x18001f690  add     [rbx+0F0h], edi
0x18001f696  mov     dword ptr [rbx+110h], 2
0x18001f6a0  lea     rcx, [rbp+57h+var_D0]
0x18001f6a4  call    ??1?$test_data_control@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(void)
0x18001f6a9  mov     rax, [rbp+57h+pv]
0x18001f6ad  test    rax, rax
0x18001f6b0  jz      short loc_18001F6F3
0x18001f6b2  lea     rbx, [rax+8]
0x18001f6b6  lea     rdi, [rbx+0C0h]
0x18001f6bd  mov     rcx, rdi; lpCriticalSection
0x18001f6c0  call    cs:__imp_EnterCriticalSection
0x18001f6c6  or      dword ptr [rbx+40h], 300h
0x18001f6cd  cmp     qword ptr [rbx+0F0h], 0
0x18001f6d5  jz      short loc_18001F6E4
0x18001f6d7  mov     edx, 2
0x18001f6dc  mov     rcx, rbx
0x18001f6df  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001f6e4  test    rdi, rdi
0x18001f6e7  jz      short loc_18001F6F3
0x18001f6e9  mov     rcx, rdi; lpCriticalSection
0x18001f6ec  call    cs:__imp_LeaveCriticalSection
0x18001f6f2  nop
0x18001f6f3  mov     rcx, [rbp+57h+hObject]; hObject
0x18001f6f7  test    rcx, rcx
0x18001f6fa  jz      short loc_18001F70E
0x18001f6fc  call    cs:__imp_CloseHandle
0x18001f702  mov     rcx, [rbp+5Fh]; this
0x18001f706  test    eax, eax
0x18001f708  jz      loc_18001F96A
0x18001f70e  mov     rbx, [rbp+57h+pv]
0x18001f712  test    rbx, rbx
0x18001f715  jz      short loc_18001F738
0x18001f717  or      eax, 0FFFFFFFFh
0x18001f71a  lock xadd [rbx+118h], eax
0x18001f722  cmp     eax, 1
0x18001f725  jnz     short loc_18001F738
0x18001f727  mov     rcx, rbx
0x18001f72a  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x18001f72f  mov     rcx, rbx; pv
0x18001f732  call    cs:__imp_CoTaskMemFree
0x18001f738  mov     eax, esi
0x18001f73a  jmp     loc_18001F940
0x18001f73f  mov     ecx, 20h ; ' '; Size
0x18001f744  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f749  mov     [rbp+57h+var_D0], rax
0x18001f74d  mov     [rax+8], edi
0x18001f750  lea     rcx, [rbp+57h+hObject]
0x18001f754  mov     [rax+10h], rcx
0x18001f758  lea     rcx, [rbp+57h+pv]
0x18001f75c  mov     [rax+18h], rcx
0x18001f760  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f767  lea     rcx, off_1800342A8
0x18001f76e  mov     [rax], rcx
0x18001f771  mov     [rbp+57h+var_D0], rax
0x18001f775  lea     r8, [rbp+57h+var_D0]
0x18001f779  lea     rcx, [rbp+57h+var_B8]
0x18001f77d  call    ?OutOfBoxExperienceStateChanged@SystemSetupInfo@Profile@System@Windows@winrt@@SA@Uauto_revoke_t@5@AEBU?$EventHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@45@@Z; winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceStateChanged(winrt::auto_revoke_t,winrt::Windows::Foundation::EventHandler<winrt::Windows::Foundation::IInspectable> const &)
0x18001f782  nop
0x18001f783  lea     rcx, [rbp+57h+var_D0]
0x18001f787  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f78c  lea     rax, off_1800342E8
0x18001f793  mov     [rbp+57h+var_A0], rax
0x18001f797  lea     rax, [rbp+57h+hObject]
0x18001f79b  mov     [rbp+57h+var_98], rax
0x18001f79f  lea     rax, [rbp+57h+pv]
0x18001f7a3  mov     [rbp+57h+var_90], rax
0x18001f7a7  lea     rax, [rbp+57h+var_A0]
0x18001f7ab  mov     [rbp+57h+var_38], rax
0x18001f7af  lea     rax, [rbp+57h+var_A8]
0x18001f7b3  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18001f7b8  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001f7bf  lea     rcx, [rbp+57h+var_D0]
0x18001f7c3  call    ?make_registry_watcher_nothrow@wil@@YA?AV?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@1@PEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::make_registry_watcher_nothrow(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18001f7c8  mov     rcx, [rbp+57h+var_38]
0x18001f7cc  test    rcx, rcx
0x18001f7cf  jz      short loc_18001F7DD
0x18001f7d1  mov     rax, [rcx]
0x18001f7d4  mov     rax, [rax+18h]
0x18001f7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7dd  mov     rbx, [rbp+57h+var_D0]
0x18001f7e1  test    rbx, rbx
0x18001f7e4  setz    al
0x18001f7e7  mov     rcx, [rbp+5Fh]; this
0x18001f7eb  test    al, al
0x18001f7ed  jz      short loc_18001F806
0x18001f7ef  mov     r9d, 8007000Eh; char *
0x18001f7f5  lea     r8, aPcshellShellAi; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18001f7fc  mov     edx, 0ACh; void *
0x18001f801  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f806  xor     r8d, r8d; bAlertable
0x18001f809  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f80c  mov     rcx, [rbp+57h+hObject]; hHandle
0x18001f810  call    cs:__imp_WaitForSingleObjectEx
0x18001f816  cmp     eax, 102h
0x18001f81b  jz      short loc_18001F825
0x18001f81d  test    eax, eax
0x18001f81f  jnz     loc_18001F97C
0x18001f825  test    rbx, rbx
0x18001f828  jz      short loc_18001F832
0x18001f82a  mov     rcx, rbx; this
0x18001f82d  call    ?delete_registry_watcher_state@details@wil@@YAXPEAUregistry_watcher_state@12@@Z; wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *)
0x18001f832  mov     rbx, [rbp+57h+var_B8]
0x18001f836  test    rbx, rbx
0x18001f839  jz      short loc_18001F871
0x18001f83b  mov     [rbp+57h+var_D0], rbx
0x18001f83f  mov     rax, [rbx]
0x18001f842  mov     rcx, rbx
0x18001f845  mov     rax, [rax+8]
0x18001f849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f84e  mov     rdx, [rbp+57h+var_B0]
0x18001f852  mov     rcx, rbx
0x18001f855  call    ??_9type@?$abi@UISystemSetupInfoStatics@Profile@System@Windows@winrt@@X@impl@winrt@@$BEA@AA; [thunk]: winrt::impl::abi<winrt::Windows::System::Profile::ISystemSetupInfoStatics,void>::type::`vcall'{64,{flat}}
0x18001f85a  lea     rcx, [rbp+57h+var_D0]
0x18001f85e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f863  test    rbx, rbx
0x18001f866  jz      short loc_18001F871
0x18001f868  lea     rcx, [rbp+57h+var_B8]
0x18001f86c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f871  lea     rcx, [rbp+57h+pv]
0x18001f875  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>>::ensure_data(void)
0x18001f87a  mov     rbx, [rax]
0x18001f87d  mov     [rbp+57h+var_D0], rbx
0x18001f881  test    rbx, rbx
0x18001f884  jz      short loc_18001F88D
0x18001f886  lock add [rbx+118h], edi
0x18001f88d  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001f894  call    cs:__imp_EnterCriticalSection
0x18001f89a  add     [rbx+0F0h], edi
0x18001f8a0  mov     dword ptr [rbx+110h], 5
0x18001f8aa  lea     rcx, [rbp+57h+var_D0]
0x18001f8ae  call    ??1?$test_data_control@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(void)
0x18001f8b3  mov     rax, [rbp+57h+pv]
0x18001f8b7  test    rax, rax
0x18001f8ba  jz      short loc_18001F8FD
0x18001f8bc  lea     rbx, [rax+8]
0x18001f8c0  lea     rdi, [rbx+0C0h]
0x18001f8c7  mov     rcx, rdi; lpCriticalSection
0x18001f8ca  call    cs:__imp_EnterCriticalSection
0x18001f8d0  or      dword ptr [rbx+40h], 300h
0x18001f8d7  cmp     qword ptr [rbx+0F0h], 0
0x18001f8df  jz      short loc_18001F8EE
0x18001f8e1  mov     edx, 2
0x18001f8e6  mov     rcx, rbx
0x18001f8e9  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001f8ee  test    rdi, rdi
0x18001f8f1  jz      short loc_18001F8FD
0x18001f8f3  mov     rcx, rdi; lpCriticalSection
0x18001f8f6  call    cs:__imp_LeaveCriticalSection
0x18001f8fc  nop
0x18001f8fd  mov     rcx, [rbp+57h+hObject]; hObject
0x18001f901  test    rcx, rcx
0x18001f904  jz      short loc_18001F914
0x18001f906  call    cs:__imp_CloseHandle
0x18001f90c  mov     rcx, [rbp+5Fh]; this
0x18001f910  test    eax, eax
0x18001f912  jz      short loc_18001F958
0x18001f914  mov     rbx, [rbp+57h+pv]
0x18001f918  test    rbx, rbx
0x18001f91b  jz      short loc_18001F93E
0x18001f91d  or      eax, 0FFFFFFFFh
0x18001f920  lock xadd [rbx+118h], eax
0x18001f928  cmp     eax, 1
0x18001f92b  jnz     short loc_18001F93E
0x18001f92d  mov     rcx, rbx
0x18001f930  call    ??1?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>::~merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>(void)
0x18001f935  mov     rcx, rbx; pv
0x18001f938  call    cs:__imp_CoTaskMemFree
0x18001f93e  xor     eax, eax
0x18001f940  mov     rcx, [rbp+57h+var_30]
0x18001f944  xor     rcx, rsp; StackCookie
0x18001f947  call    __security_check_cookie
0x18001f94c  add     rsp, 0E8h
0x18001f953  pop     rdi
0x18001f954  pop     rsi
0x18001f955  pop     rbx
0x18001f956  pop     rbp
0x18001f957  retn
0x18001f958  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f95f  mov     edx, 0A0Bh; void *
0x18001f964  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001f96a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f971  mov     edx, 0A0Bh; void *
0x18001f976  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001f97c  mov     rcx, [rbp+5Fh]; this
0x18001f980  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001f987  mov     edx, 0B0Fh; void *
0x18001f98c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
