# ??$call@AEAV_lambda_1_@?1??SetAutomationId@AutomationProperties@Automation@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@5678@AEBUhstring@param@8@@Z@@?$factory_cache_entry@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??SetAutomationId@AutomationProperties@Automation@Xaml@UI@Windows@2@SA@AEBUDependencyObject@7892@AEBUhstring@param@2@@Z@@Z

- ea: `0x18000d1b0`
- end: `0x18000d358`
- name: `??$call@AEAV_lambda_1_@?1??SetAutomationId@AutomationProperties@Automation@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@5678@AEBUhstring@param@8@@Z@@?$factory_cache_entry@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??SetAutomationId@AutomationProperties@Automation@Xaml@UI@Windows@2@SA@AEBUDependencyObject@7892@AEBUhstring@param@2@@Z@@Z`
- size: `424`
- prototype: `__int64 __fastcall(__int64 *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180013188`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000d1b0`
- `0x18000e70c`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__SetAutomationId_AutomationProperties_Automation_Xaml_UI_Windows_winrt__SA_AEBUDependencyObject_5678_AEBUhstring_param_8__Z____factory_cache_entry_UAutomationProperties_Automation_Xaml_UI_Windows_winrt__UIAutomationPropertiesStatics_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1__SetAutomationId_AutomationProperties_Automation_Xaml_UI_Windows_2_SA_AEBUDependencyObject_7892_AEBUhstring_param_2__Z__Z(
        __int64 *a1,
        _QWORD **a2)
{
  signed __int64 v3; // rbx
  __int64 result; // rax
  int v5; // eax
  int v6; // [rsp+20h] [rbp-40h] BYREF
  __int128 v7; // [rsp+28h] [rbp-38h]
  _DWORD *v8; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v9[4]; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v10; // [rsp+50h] [rbp-10h]
  __int64 *v11; // [rsp+70h] [rbp+10h] BYREF
  __int64 *v12; // [rsp+80h] [rbp+20h] BYREF

  v11 = a1;
  v9[0] = 1;
  v9[1] = 47;
  v10 = L"Windows.UI.Xaml.Automation.AutomationProperties";
  v8 = v9;
  v12 = 0;
  v6 = 0;
  v7 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v8,
    &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics>,
    &v12);
  if ( (int)v11 < 0 )
    winrt::throw_hresult((unsigned int)v11, &v6);
  v3 = (signed __int64)v12;
  v11 = v12;
  if ( !v12
    || (v12 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, __int64 **))v3)(
          v3,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v12),
        !v12) )
  {
    v6 = 0;
    v7 = 0;
    v5 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 112LL))(v3, **a2, *a2[1]);
    if ( v5 < 0 )
      winrt::throw_hresult((unsigned int)v5, &v6);
    return winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v11);
  }
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v12);
  v12 = &qword_18003C218;
  _InterlockedIncrement64(&qword_18003C218);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics>,
          v3,
          0) )
  {
    v3 = 0;
    v11 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C220);
  }
  v6 = 0;
  v7 = 0;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics>
                                                              + 112LL))(
             winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics>,
             **a2,
             *a2[1]);
  if ( (int)result < 0 )
    winrt::throw_hresult((unsigned int)result, &v6);
  _InterlockedDecrement64(&qword_18003C218);
  if ( v3 )
    return winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v11);
  return result;
}

```

## disassembly

```asm
0x18000d1b0  mov     [rsp-8+arg_8], rbx
0x18000d1b5  mov     [rsp-8+arg_18], rdi
0x18000d1ba  mov     [rsp-8+arg_0], rcx
0x18000d1bf  push    rbp
0x18000d1c0  mov     rbp, rsp
0x18000d1c3  sub     rsp, 60h
0x18000d1c7  mov     rdi, rdx
0x18000d1ca  mov     [rbp+var_20], 1
0x18000d1d1  mov     [rbp+var_1C], 2Fh ; '/'
0x18000d1d8  lea     rax, aWindowsUiXamlA; "Windows.UI.Xaml.Automation.AutomationPr"...
0x18000d1df  mov     [rbp+var_10], rax
0x18000d1e3  lea     rax, [rbp+var_20]
0x18000d1e7  mov     [rbp+var_28], rax
0x18000d1eb  mov     [rbp+arg_10], 0
0x18000d1f3  mov     [rbp+var_40], 0
0x18000d1fa  xorps   xmm0, xmm0
0x18000d1fd  movdqu  [rbp+var_38], xmm0
0x18000d202  lea     r9, [rbp+arg_10]
0x18000d206  lea     r8, ??$guid_v@UIAutomationPropertiesStatics@Automation@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics>
0x18000d20d  lea     rdx, [rbp+var_28]
0x18000d211  lea     rcx, [rbp+arg_0]
0x18000d215  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000d21a  mov     ecx, dword ptr [rbp+arg_0]
0x18000d21d  test    ecx, ecx
0x18000d21f  js      loc_18000D342
0x18000d225  mov     rbx, [rbp+arg_10]
0x18000d229  mov     [rbp+arg_0], rbx
0x18000d22d  test    rbx, rbx
0x18000d230  jz      loc_18000D2EC
0x18000d236  mov     [rbp+arg_10], 0
0x18000d23e  mov     rax, [rbx]
0x18000d241  lea     r8, [rbp+arg_10]
0x18000d245  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000d24c  mov     rcx, rbx
0x18000d24f  mov     rax, [rax]
0x18000d252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d257  mov     rax, [rbp+arg_10]
0x18000d25b  mov     [rbp+arg_10], rax
0x18000d25f  test    rax, rax
0x18000d262  jz      loc_18000D2EC
0x18000d268  lea     rcx, [rbp+arg_10]
0x18000d26c  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d271  lea     rax, qword_18003C218
0x18000d278  mov     [rbp+arg_10], rax
0x18000d27c  lock inc cs:qword_18003C218
0x18000d284  xor     eax, eax
0x18000d286  lock cmpxchg cs:??$factory_cache_entry_v@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics>
0x18000d28f  jnz     short loc_18000D2AA
0x18000d291  xor     ebx, ebx
0x18000d293  mov     [rbp+arg_0], rbx
0x18000d297  lea     rdx, stru_18003C220; ListEntry
0x18000d29e  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000d2a5  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000d2aa  mov     rcx, cs:??$factory_cache_entry_v@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics>
0x18000d2b1  mov     [rbp+var_40], 0
0x18000d2b8  xorps   xmm0, xmm0
0x18000d2bb  movdqu  [rbp+var_38], xmm0
0x18000d2c0  mov     rax, [rcx]
0x18000d2c3  mov     r8, [rdi+8]
0x18000d2c7  mov     rdx, [rdi]
0x18000d2ca  mov     r8, [r8]
0x18000d2cd  mov     rdx, [rdx]
0x18000d2d0  mov     rax, [rax+70h]
0x18000d2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2d9  test    eax, eax
0x18000d2db  js      short loc_18000D34C
0x18000d2dd  lock dec cs:qword_18003C218
0x18000d2e5  test    rbx, rbx
0x18000d2e8  jz      short loc_18000D324
0x18000d2ea  jmp     short loc_18000D31B
0x18000d2ec  mov     [rbp+var_40], 0
0x18000d2f3  xorps   xmm0, xmm0
0x18000d2f6  movdqu  [rbp+var_38], xmm0
0x18000d2fb  mov     rax, [rbx]
0x18000d2fe  mov     r8, [rdi+8]
0x18000d302  mov     rdx, [rdi]
0x18000d305  mov     r8, [r8]
0x18000d308  mov     rdx, [rdx]
0x18000d30b  mov     rcx, rbx
0x18000d30e  mov     rax, [rax+70h]
0x18000d312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d317  test    eax, eax
0x18000d319  js      short loc_18000D336
0x18000d31b  lea     rcx, [rbp+arg_0]
0x18000d31f  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d324  lea     r11, [rsp+60h+var_s0]
0x18000d329  mov     rbx, [r11+18h]
0x18000d32d  mov     rdi, [r11+28h]
0x18000d331  mov     rsp, r11
0x18000d334  pop     rbp
0x18000d335  retn
0x18000d336  lea     rdx, [rbp+var_40]
0x18000d33a  mov     ecx, eax
0x18000d33c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d342  lea     rdx, [rbp+var_40]
0x18000d346  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d34c  lea     rdx, [rbp+var_40]
0x18000d350  mov     ecx, eax
0x18000d352  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
