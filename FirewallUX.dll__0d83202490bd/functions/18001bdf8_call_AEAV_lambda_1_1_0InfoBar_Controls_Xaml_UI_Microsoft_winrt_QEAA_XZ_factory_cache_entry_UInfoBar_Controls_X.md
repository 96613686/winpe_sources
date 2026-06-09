# ??$call@AEAV_lambda_1_@?1???0InfoBar@Controls@Xaml@UI@Microsoft@winrt@@QEAA@XZ@@?$factory_cache_entry@UInfoBar@Controls@Xaml@UI@Microsoft@winrt@@UIInfoBarFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0InfoBar@Controls@Xaml@UI@Microsoft@2@QEAA@XZ@@Z

- ea: `0x18001bdf8`
- end: `0x18001bf46`
- name: `??$call@AEAV_lambda_1_@?1???0InfoBar@Controls@Xaml@UI@Microsoft@winrt@@QEAA@XZ@@?$factory_cache_entry@UInfoBar@Controls@Xaml@UI@Microsoft@winrt@@UIInfoBarFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0InfoBar@Controls@Xaml@UI@Microsoft@2@QEAA@XZ@@Z`
- size: `334`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001ca68`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000e70c`
- `0x18000f3bc`
- `0x18001bdf8`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1___0InfoBar_Controls_Xaml_UI_Microsoft_winrt__QEAA_XZ____factory_cache_entry_UInfoBar_Controls_Xaml_UI_Microsoft_winrt__UIInfoBarFactory_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1___0InfoBar_Controls_Xaml_UI_Microsoft_2_QEAA_XZ__Z(
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
  v10[1] = 34;
  v11 = L"Microsoft.UI.Xaml.Controls.InfoBar";
  v9 = v10;
  v13 = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    &winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::Controls::IInfoBarFactory>,
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
    v13 = &qword_18003BE68;
    _InterlockedIncrement64(&qword_18003BE68);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::UI::Xaml::Controls::InfoBar,winrt::Microsoft::UI::Xaml::Controls::IInfoBarFactory>,
            (signed __int64)v5,
            0) )
    {
      v5 = 0;
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003BE70);
    }
    `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton'::`2'::_lambda_1_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::UI::Xaml::Controls::InfoBar,winrt::Microsoft::UI::Xaml::Controls::IInfoBarFactory>);
    _InterlockedDecrement64(&qword_18003BE68);
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
0x18001bdf8  mov     [rsp-18h+arg_8], rbx
0x18001bdfd  mov     [rsp-18h+arg_0], rcx
0x18001be02  push    rbp
0x18001be03  push    rsi
0x18001be04  push    rdi
0x18001be05  mov     rbp, rsp
0x18001be08  sub     rsp, 60h
0x18001be0c  mov     rsi, r8
0x18001be0f  mov     rdi, rdx
0x18001be12  mov     [rbp+var_18], 1
0x18001be19  mov     [rbp+var_14], 22h ; '"'
0x18001be20  lea     rax, aMicrosoftUiXam_0; "Microsoft.UI.Xaml.Controls.InfoBar"
0x18001be27  mov     [rbp+var_8], rax
0x18001be2b  lea     rax, [rbp+var_18]
0x18001be2f  mov     [rbp+var_20], rax
0x18001be33  mov     [rbp+arg_18], 0
0x18001be3b  mov     [rbp+var_38], 0
0x18001be42  xorps   xmm0, xmm0
0x18001be45  movdqu  [rbp+var_30], xmm0
0x18001be4a  lea     r9, [rbp+arg_18]
0x18001be4e  lea     r8, ??$guid_v@UIInfoBarFactory@Controls@Xaml@UI@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::Controls::IInfoBarFactory>
0x18001be55  lea     rdx, [rbp+var_20]
0x18001be59  lea     rcx, [rbp+arg_0]
0x18001be5d  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001be62  mov     ecx, dword ptr [rbp+arg_0]
0x18001be65  test    ecx, ecx
0x18001be67  js      loc_18001BF3C
0x18001be6d  mov     rbx, [rbp+arg_18]
0x18001be71  mov     [rbp+arg_0], rbx
0x18001be75  test    rbx, rbx
0x18001be78  jz      loc_18001BF0B
0x18001be7e  mov     [rbp+arg_18], 0
0x18001be86  mov     rax, [rbx]
0x18001be89  lea     r8, [rbp+arg_18]
0x18001be8d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001be94  mov     rcx, rbx
0x18001be97  mov     rax, [rax]
0x18001be9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be9f  mov     rax, [rbp+arg_18]
0x18001bea3  mov     [rbp+arg_18], rax
0x18001bea7  test    rax, rax
0x18001beaa  jz      short loc_18001BF0B
0x18001beac  lea     rcx, [rbp+arg_18]
0x18001beb0  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001beb5  lea     rax, qword_18003BE68
0x18001bebc  mov     [rbp+arg_18], rax
0x18001bec0  lock inc cs:qword_18003BE68
0x18001bec8  xor     eax, eax
0x18001beca  lock cmpxchg cs:??$factory_cache_entry_v@UInfoBar@Controls@Xaml@UI@Microsoft@winrt@@UIInfoBarFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UInfoBar@Controls@Xaml@UI@Microsoft@winrt@@UIInfoBarFactory@23456@@12@A, rbx; factory_cache_entry<winrt::Microsoft::UI::Xaml::Controls::InfoBar,winrt::Microsoft::UI::Xaml::Controls::IInfoBarFactory>::winrt::factory_cache_entry<winrt::Microsoft::UI::Xaml::Controls::InfoBar,winrt::Microsoft::UI::Xaml::Controls::IInfoBarFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::UI::Xaml::Controls::InfoBar,winrt::Microsoft::UI::Xaml::Controls::IInfoBarFactory>
0x18001bed3  jnz     short loc_18001BEEE
0x18001bed5  xor     ebx, ebx
0x18001bed7  mov     [rbp+arg_0], rbx
0x18001bedb  lea     rdx, stru_18003BE70; ListEntry
0x18001bee2  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001bee9  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001beee  lea     r8, ??$factory_cache_entry_v@UInfoBar@Controls@Xaml@UI@Microsoft@winrt@@UIInfoBarFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UInfoBar@Controls@Xaml@UI@Microsoft@winrt@@UIInfoBarFactory@23456@@12@A; factory_cache_entry<winrt::Microsoft::UI::Xaml::Controls::InfoBar,winrt::Microsoft::UI::Xaml::Controls::IInfoBarFactory>::winrt::factory_cache_entry<winrt::Microsoft::UI::Xaml::Controls::InfoBar,winrt::Microsoft::UI::Xaml::Controls::IInfoBarFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::UI::Xaml::Controls::InfoBar,winrt::Microsoft::UI::Xaml::Controls::IInfoBarFactory>
0x18001bef5  mov     rdx, rdi
0x18001bef8  mov     rcx, rsi
0x18001befb  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x18001bf00  nop
0x18001bf01  lock dec cs:qword_18003BE68
0x18001bf09  jmp     short loc_18001BF1B
0x18001bf0b  lea     r8, [rbp+arg_0]
0x18001bf0f  mov     rdx, rdi
0x18001bf12  mov     rcx, rsi
0x18001bf15  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x18001bf1a  nop
0x18001bf1b  test    rbx, rbx
0x18001bf1e  jz      short loc_18001BF29
0x18001bf20  lea     rcx, [rbp+arg_0]
0x18001bf24  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001bf29  mov     rax, rdi
0x18001bf2c  mov     rbx, [rsp+60h+arg_8]
0x18001bf34  add     rsp, 60h
0x18001bf38  pop     rdi
0x18001bf39  pop     rsi
0x18001bf3a  pop     rbp
0x18001bf3b  retn
0x18001bf3c  lea     rdx, [rbp+var_38]
0x18001bf40  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
