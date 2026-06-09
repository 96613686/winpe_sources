# ??$call@AEAV_lambda_1_@?1???0StackPanel@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@@?$factory_cache_entry@UStackPanel@Controls@Xaml@UI@Windows@winrt@@UIStackPanelFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0StackPanel@Controls@Xaml@UI@Windows@2@QEAA@XZ@@Z

- ea: `0x18000ccf8`
- end: `0x18000ce46`
- name: `??$call@AEAV_lambda_1_@?1???0StackPanel@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@@?$factory_cache_entry@UStackPanel@Controls@Xaml@UI@Windows@winrt@@UIStackPanelFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0StackPanel@Controls@Xaml@UI@Windows@2@QEAA@XZ@@Z`
- size: `334`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000ed88`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000ccf8`
- `0x18000e70c`
- `0x18000f3bc`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1___0StackPanel_Controls_Xaml_UI_Windows_winrt__QEAA_XZ____factory_cache_entry_UStackPanel_Controls_Xaml_UI_Windows_winrt__UIStackPanelFactory_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1___0StackPanel_Controls_Xaml_UI_Windows_2_QEAA_XZ__Z(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // rbx
  int v7; // [rsp+28h] [rbp-38h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h]
  _DWORD *v9; // [rsp+40h] [rbp-20h] BYREF
  _DWORD v10[4]; // [rsp+48h] [rbp-18h] BYREF
  const wchar_t *v11; // [rsp+58h] [rbp-8h]
  __int64 *v12; // [rsp+80h] [rbp+20h] BYREF
  __int64 *v13; // [rsp+98h] [rbp+38h] BYREF

  v12 = a1;
  v10[0] = 1;
  v10[1] = 35;
  v11 = L"Windows.UI.Xaml.Controls.StackPanel";
  v9 = v10;
  v13 = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IStackPanelFactory>,
    &v13);
  if ( (int)v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, &v7);
  v5 = v13;
  v12 = v13;
  if ( v13
    && (v13 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v13),
        v13) )
  {
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v13);
    v13 = &qword_18003BE28;
    _InterlockedIncrement64(&qword_18003BE28);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::StackPanel,winrt::Windows::UI::Xaml::Controls::IStackPanelFactory>,
            (signed __int64)v5,
            0) )
    {
      v5 = 0;
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003BE30);
    }
    `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton'::`2'::_lambda_1_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::StackPanel,winrt::Windows::UI::Xaml::Controls::IStackPanelFactory>);
    _InterlockedDecrement64(&qword_18003BE28);
  }
  else
  {
    `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton'::`2'::_lambda_1_::operator()(a3, a2, &v12);
  }
  if ( v5 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v12);
  return a2;
}

```

## disassembly

```asm
0x18000ccf8  mov     [rsp-18h+arg_8], rbx
0x18000ccfd  mov     [rsp-18h+arg_0], rcx
0x18000cd02  push    rbp
0x18000cd03  push    rsi
0x18000cd04  push    rdi
0x18000cd05  mov     rbp, rsp
0x18000cd08  sub     rsp, 60h
0x18000cd0c  mov     rsi, r8
0x18000cd0f  mov     rdi, rdx
0x18000cd12  mov     [rbp+var_18], 1
0x18000cd19  mov     [rbp+var_14], 23h ; '#'
0x18000cd20  lea     rax, aWindowsUiXamlC_7; "Windows.UI.Xaml.Controls.StackPanel"
0x18000cd27  mov     [rbp+var_8], rax
0x18000cd2b  lea     rax, [rbp+var_18]
0x18000cd2f  mov     [rbp+var_20], rax
0x18000cd33  mov     [rbp+arg_18], 0
0x18000cd3b  mov     [rbp+var_38], 0
0x18000cd42  xorps   xmm0, xmm0
0x18000cd45  movdqu  [rbp+var_30], xmm0
0x18000cd4a  lea     r9, [rbp+arg_18]
0x18000cd4e  lea     r8, ??$guid_v@UIStackPanelFactory@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IStackPanelFactory>
0x18000cd55  lea     rdx, [rbp+var_20]
0x18000cd59  lea     rcx, [rbp+arg_0]
0x18000cd5d  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000cd62  mov     ecx, dword ptr [rbp+arg_0]
0x18000cd65  test    ecx, ecx
0x18000cd67  js      loc_18000CE3C
0x18000cd6d  mov     rbx, [rbp+arg_18]
0x18000cd71  mov     [rbp+arg_0], rbx
0x18000cd75  test    rbx, rbx
0x18000cd78  jz      loc_18000CE0B
0x18000cd7e  mov     [rbp+arg_18], 0
0x18000cd86  mov     rax, [rbx]
0x18000cd89  lea     r8, [rbp+arg_18]
0x18000cd8d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000cd94  mov     rcx, rbx
0x18000cd97  mov     rax, [rax]
0x18000cd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd9f  mov     rax, [rbp+arg_18]
0x18000cda3  mov     [rbp+arg_18], rax
0x18000cda7  test    rax, rax
0x18000cdaa  jz      short loc_18000CE0B
0x18000cdac  lea     rcx, [rbp+arg_18]
0x18000cdb0  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000cdb5  lea     rax, qword_18003BE28
0x18000cdbc  mov     [rbp+arg_18], rax
0x18000cdc0  lock inc cs:qword_18003BE28
0x18000cdc8  xor     eax, eax
0x18000cdca  lock cmpxchg cs:??$factory_cache_entry_v@UStackPanel@Controls@Xaml@UI@Windows@winrt@@UIStackPanelFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UStackPanel@Controls@Xaml@UI@Windows@winrt@@UIStackPanelFactory@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::StackPanel,winrt::Windows::UI::Xaml::Controls::IStackPanelFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::StackPanel,winrt::Windows::UI::Xaml::Controls::IStackPanelFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::StackPanel,winrt::Windows::UI::Xaml::Controls::IStackPanelFactory>
0x18000cdd3  jnz     short loc_18000CDEE
0x18000cdd5  xor     ebx, ebx
0x18000cdd7  mov     [rbp+arg_0], rbx
0x18000cddb  lea     rdx, stru_18003BE30; ListEntry
0x18000cde2  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000cde9  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000cdee  lea     r8, ??$factory_cache_entry_v@UStackPanel@Controls@Xaml@UI@Windows@winrt@@UIStackPanelFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UStackPanel@Controls@Xaml@UI@Windows@winrt@@UIStackPanelFactory@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::StackPanel,winrt::Windows::UI::Xaml::Controls::IStackPanelFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::StackPanel,winrt::Windows::UI::Xaml::Controls::IStackPanelFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::StackPanel,winrt::Windows::UI::Xaml::Controls::IStackPanelFactory>
0x18000cdf5  mov     rdx, rdi
0x18000cdf8  mov     rcx, rsi
0x18000cdfb  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x18000ce00  nop
0x18000ce01  lock dec cs:qword_18003BE28
0x18000ce09  jmp     short loc_18000CE1B
0x18000ce0b  lea     r8, [rbp+arg_0]
0x18000ce0f  mov     rdx, rdi
0x18000ce12  mov     rcx, rsi
0x18000ce15  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x18000ce1a  nop
0x18000ce1b  test    rbx, rbx
0x18000ce1e  jz      short loc_18000CE29
0x18000ce20  lea     rcx, [rbp+arg_0]
0x18000ce24  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000ce29  mov     rax, rdi
0x18000ce2c  mov     rbx, [rsp+60h+arg_8]
0x18000ce34  add     rsp, 60h
0x18000ce38  pop     rdi
0x18000ce39  pop     rsi
0x18000ce3a  pop     rbp
0x18000ce3b  retn
0x18000ce3c  lea     rdx, [rbp+var_38]
0x18000ce40  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
