# CCredUIBrokerForNonAppContainers::PromptForPasskeySyncOTS(HWND__ *,IUnknown *)

- ea: `0x140010be0`
- end: `0x140010d02`
- name: `?PromptForPasskeySyncOTS@CCredUIBrokerForNonAppContainers@@UEAAJPEAUHWND__@@PEAUIUnknown@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(CCredUIBrokerForNonAppContainers *__hidden this, HWND, struct IUnknown *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140008e8c`
- `0x140009004`
- `0x14000903c`
- `0x140009138`
- `0x14000bb60`
- `0x14000e920`
- `0x140010be0`
- `0x140019084`
- `0x1400190b8`
- `0x14001bb28`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010c2c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140010c2c`

## pseudocode

```c
__int64 __fastcall CCredUIBrokerForNonAppContainers::PromptForPasskeySyncOTS(
        CCredUIBrokerForNonAppContainers *this,
        HWND a2,
        struct IUnknown *a3)
{
  HRESULT v5; // edi
  __int64 v6; // rbx
  __int64 v7; // rbx
  _QWORD v9[2]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v10[56]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v11; // [rsp+78h] [rbp-8h]
  LPVOID ppv; // [rsp+B8h] [rbp+38h] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v9[0] = 0;
  v5 = CoCreateInstance(
         &GUID_96b42929_01f1_468c_b521_6294ab438f4a,
         0,
         1u,
         &GUID_8e84d694_46f1_48d5_846e_e2663dd726a1,
         &ppv);
  tip2::tip_test<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>>::start_and_watch_errors(
    v9,
    v10);
  wil::com_ptr_t<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>,wil::err_returncode_policy>(v9);
  v6 = v11;
  v9[0] = v11;
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 288));
  tip2::details::shared_data<0,0,0>::begin_update(v6 + 8);
  *(_DWORD *)(v6 + 272) = v5;
  tip2::test_data_control<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>>(v9);
  if ( v5 >= 0 )
    v5 = (*(__int64 (__fastcall **)(LPVOID, HWND, struct IUnknown *))(*(_QWORD *)ppv + 40LL))(ppv, a2, a3);
  v7 = v11;
  wil::EnterCriticalSection(v9, v11 + 200);
  *(_DWORD *)(v7 + 72) |= 0x300u;
  if ( *(_QWORD *)(v7 + 248) )
    tip2::details::shared_data<0,0,0>::complete_helper(v7 + 8, 2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v9);
  tip2::test_watcher<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>>::~test_watcher<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>>(v10);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140010be0  mov     [rsp-18h+arg_0], rbx
0x140010be5  mov     [rsp-18h+arg_8], rsi
0x140010bea  push    rbp
0x140010beb  push    rdi
0x140010bec  push    r14
0x140010bee  mov     rbp, rsp
0x140010bf1  sub     rsp, 80h
0x140010bf8  lea     rcx, [rbp+arg_18]
0x140010bfc  mov     [rbp+arg_18], 0
0x140010c04  mov     rsi, r8
0x140010c07  mov     r14, rdx
0x140010c0a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010c0f  xor     edx, edx; pUnkOuter
0x140010c11  lea     rax, [rbp+arg_18]
0x140010c15  lea     r9, _GUID_8e84d694_46f1_48d5_846e_e2663dd726a1; riid
0x140010c1c  mov     [rsp+80h+ppv], rax; ppv
0x140010c21  lea     rcx, _GUID_96b42929_01f1_468c_b521_6294ab438f4a; rclsid
0x140010c28  lea     r8d, [rdx+1]; dwClsContext
0x140010c2c  call    cs:__imp_CoCreateInstance
0x140010c32  lea     rdx, [rbp+var_40]
0x140010c36  mov     [rbp+var_50], 0
0x140010c3e  lea     rcx, [rbp+var_50]
0x140010c42  mov     edi, eax
0x140010c44  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>>::start_and_watch_errors(void)
0x140010c49  lea     rcx, [rbp+var_50]
0x140010c4d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>,wil::err_returncode_policy>(void)
0x140010c52  mov     rbx, [rbp+var_8]
0x140010c56  mov     [rbp+var_50], rbx
0x140010c5a  test    rbx, rbx
0x140010c5d  jz      short loc_140010C66
0x140010c5f  lock inc dword ptr [rbx+120h]
0x140010c66  lea     rcx, [rbx+8]
0x140010c6a  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x140010c6f  lea     rcx, [rbp+var_50]
0x140010c73  mov     [rbx+110h], edi
0x140010c79  call    ??1?$test_data_control@V?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>>(void)
0x140010c7e  test    edi, edi
0x140010c80  js      short loc_140010C9A
0x140010c82  mov     rcx, [rbp+arg_18]
0x140010c86  mov     r8, rsi
0x140010c89  mov     rdx, r14
0x140010c8c  mov     rax, [rcx]
0x140010c8f  mov     rax, [rax+28h]
0x140010c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c98  mov     edi, eax
0x140010c9a  mov     rbx, [rbp+var_8]
0x140010c9e  lea     rcx, [rbp+var_50]
0x140010ca2  lea     rdx, [rbx+0C8h]
0x140010ca9  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x140010cae  or      dword ptr [rbx+48h], 300h
0x140010cb5  cmp     qword ptr [rbx+0F8h], 0
0x140010cbd  jz      short loc_140010CCD
0x140010cbf  mov     edx, 2
0x140010cc4  lea     rcx, [rbx+8]
0x140010cc8  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x140010ccd  lea     rcx, [rbp+var_50]
0x140010cd1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x140010cd6  lea     rcx, [rbp+var_40]
0x140010cda  call    ??1?$test_watcher@V?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>>::~test_watcher<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>>(void)
0x140010cdf  lea     rcx, [rbp+arg_18]
0x140010ce3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140010ce8  lea     r11, [rsp+80h+var_s0]
0x140010cf0  mov     eax, edi
0x140010cf2  mov     rbx, [r11+20h]
0x140010cf6  mov     rsi, [r11+28h]
0x140010cfa  mov     rsp, r11
0x140010cfd  pop     r14
0x140010cff  pop     rdi
0x140010d00  pop     rbp
0x140010d01  retn
```
