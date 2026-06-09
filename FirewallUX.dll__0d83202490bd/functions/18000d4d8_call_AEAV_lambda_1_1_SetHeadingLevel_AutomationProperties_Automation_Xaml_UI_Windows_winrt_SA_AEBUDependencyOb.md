# ??$call@AEAV_lambda_1_@?1??SetHeadingLevel@AutomationProperties@Automation@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@5678@AEBW4AutomationHeadingLevel@Peers@45678@@Z@@?$factory_cache_entry@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics7@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??SetHeadingLevel@AutomationProperties@Automation@Xaml@UI@Windows@2@SA@AEBUDependencyObject@7892@AEBW4AutomationHeadingLevel@Peers@67892@@Z@@Z

- ea: `0x18000d4d8`
- end: `0x18000d680`
- name: `??$call@AEAV_lambda_1_@?1??SetHeadingLevel@AutomationProperties@Automation@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@5678@AEBW4AutomationHeadingLevel@Peers@45678@@Z@@?$factory_cache_entry@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics7@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??SetHeadingLevel@AutomationProperties@Automation@Xaml@UI@Windows@2@SA@AEBUDependencyObject@7892@AEBW4AutomationHeadingLevel@Peers@67892@@Z@@Z`
- size: `424`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180014058`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000d4d8`
- `0x18000e70c`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__SetHeadingLevel_AutomationProperties_Automation_Xaml_UI_Windows_winrt__SA_AEBUDependencyObject_5678_AEBW4AutomationHeadingLevel_Peers_45678__Z____factory_cache_entry_UAutomationProperties_Automation_Xaml_UI_Windows_winrt__UIAutomationPropertiesStatics7_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1__SetHeadingLevel_AutomationProperties_Automation_Xaml_UI_Windows_2_SA_AEBUDependencyObject_7892_AEBW4AutomationHeadingLevel_Peers_67892__Z__Z(
        __int64 *a1,
        __int64 a2)
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
    &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7>,
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
    v5 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 64LL))(
           v3,
           **(_QWORD **)a2,
           **(unsigned int **)(a2 + 8));
    if ( v5 < 0 )
      winrt::throw_hresult((unsigned int)v5, &v6);
    return winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v11);
  }
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v12);
  v12 = &qword_18003C2A8;
  _InterlockedIncrement64(&qword_18003C2A8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7>,
          v3,
          0) )
  {
    v3 = 0;
    v11 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C2B0);
  }
  v6 = 0;
  v7 = 0;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7>
                                                              + 64LL))(
             winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7>,
             **(_QWORD **)a2,
             **(unsigned int **)(a2 + 8));
  if ( (int)result < 0 )
    winrt::throw_hresult((unsigned int)result, &v6);
  _InterlockedDecrement64(&qword_18003C2A8);
  if ( v3 )
    return winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v11);
  return result;
}

```

## disassembly

```asm
0x18000d4d8  mov     [rsp-8+arg_8], rbx
0x18000d4dd  mov     [rsp-8+arg_18], rdi
0x18000d4e2  mov     [rsp-8+arg_0], rcx
0x18000d4e7  push    rbp
0x18000d4e8  mov     rbp, rsp
0x18000d4eb  sub     rsp, 60h
0x18000d4ef  mov     rdi, rdx
0x18000d4f2  mov     [rbp+var_20], 1
0x18000d4f9  mov     [rbp+var_1C], 2Fh ; '/'
0x18000d500  lea     rax, aWindowsUiXamlA; "Windows.UI.Xaml.Automation.AutomationPr"...
0x18000d507  mov     [rbp+var_10], rax
0x18000d50b  lea     rax, [rbp+var_20]
0x18000d50f  mov     [rbp+var_28], rax
0x18000d513  mov     [rbp+arg_10], 0
0x18000d51b  mov     [rbp+var_40], 0
0x18000d522  xorps   xmm0, xmm0
0x18000d525  movdqu  [rbp+var_38], xmm0
0x18000d52a  lea     r9, [rbp+arg_10]
0x18000d52e  lea     r8, ??$guid_v@UIAutomationPropertiesStatics7@Automation@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7>
0x18000d535  lea     rdx, [rbp+var_28]
0x18000d539  lea     rcx, [rbp+arg_0]
0x18000d53d  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000d542  mov     ecx, dword ptr [rbp+arg_0]
0x18000d545  test    ecx, ecx
0x18000d547  js      loc_18000D66A
0x18000d54d  mov     rbx, [rbp+arg_10]
0x18000d551  mov     [rbp+arg_0], rbx
0x18000d555  test    rbx, rbx
0x18000d558  jz      loc_18000D614
0x18000d55e  mov     [rbp+arg_10], 0
0x18000d566  mov     rax, [rbx]
0x18000d569  lea     r8, [rbp+arg_10]
0x18000d56d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000d574  mov     rcx, rbx
0x18000d577  mov     rax, [rax]
0x18000d57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d57f  mov     rax, [rbp+arg_10]
0x18000d583  mov     [rbp+arg_10], rax
0x18000d587  test    rax, rax
0x18000d58a  jz      loc_18000D614
0x18000d590  lea     rcx, [rbp+arg_10]
0x18000d594  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d599  lea     rax, qword_18003C2A8
0x18000d5a0  mov     [rbp+arg_10], rax
0x18000d5a4  lock inc cs:qword_18003C2A8
0x18000d5ac  xor     eax, eax
0x18000d5ae  lock cmpxchg cs:??$factory_cache_entry_v@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics7@23456@@impl@winrt@@3U?$factory_cache_entry@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics7@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7>
0x18000d5b7  jnz     short loc_18000D5D2
0x18000d5b9  xor     ebx, ebx
0x18000d5bb  mov     [rbp+arg_0], rbx
0x18000d5bf  lea     rdx, stru_18003C2B0; ListEntry
0x18000d5c6  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000d5cd  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000d5d2  mov     rcx, cs:??$factory_cache_entry_v@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics7@23456@@impl@winrt@@3U?$factory_cache_entry@UAutomationProperties@Automation@Xaml@UI@Windows@winrt@@UIAutomationPropertiesStatics7@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Automation::AutomationProperties,winrt::Windows::UI::Xaml::Automation::IAutomationPropertiesStatics7>
0x18000d5d9  mov     [rbp+var_40], 0
0x18000d5e0  xorps   xmm0, xmm0
0x18000d5e3  movdqu  [rbp+var_38], xmm0
0x18000d5e8  mov     rax, [rcx]
0x18000d5eb  mov     r8, [rdi+8]
0x18000d5ef  mov     rdx, [rdi]
0x18000d5f2  mov     r8d, [r8]
0x18000d5f5  mov     rdx, [rdx]
0x18000d5f8  mov     rax, [rax+40h]
0x18000d5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d601  test    eax, eax
0x18000d603  js      short loc_18000D674
0x18000d605  lock dec cs:qword_18003C2A8
0x18000d60d  test    rbx, rbx
0x18000d610  jz      short loc_18000D64C
0x18000d612  jmp     short loc_18000D643
0x18000d614  mov     [rbp+var_40], 0
0x18000d61b  xorps   xmm0, xmm0
0x18000d61e  movdqu  [rbp+var_38], xmm0
0x18000d623  mov     rax, [rbx]
0x18000d626  mov     r8, [rdi+8]
0x18000d62a  mov     rdx, [rdi]
0x18000d62d  mov     r8d, [r8]
0x18000d630  mov     rdx, [rdx]
0x18000d633  mov     rcx, rbx
0x18000d636  mov     rax, [rax+40h]
0x18000d63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d63f  test    eax, eax
0x18000d641  js      short loc_18000D65E
0x18000d643  lea     rcx, [rbp+arg_0]
0x18000d647  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d64c  lea     r11, [rsp+60h+var_s0]
0x18000d651  mov     rbx, [r11+18h]
0x18000d655  mov     rdi, [r11+28h]
0x18000d659  mov     rsp, r11
0x18000d65c  pop     rbp
0x18000d65d  retn
0x18000d65e  lea     rdx, [rbp+var_40]
0x18000d662  mov     ecx, eax
0x18000d664  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d66a  lea     rdx, [rbp+var_40]
0x18000d66e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d674  lea     rdx, [rbp+var_40]
0x18000d678  mov     ecx, eax
0x18000d67a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
