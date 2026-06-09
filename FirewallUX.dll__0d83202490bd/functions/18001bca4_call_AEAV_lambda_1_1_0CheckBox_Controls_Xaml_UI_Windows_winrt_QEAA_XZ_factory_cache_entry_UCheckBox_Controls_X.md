# ??$call@AEAV_lambda_1_@?1???0CheckBox@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@@?$factory_cache_entry@UCheckBox@Controls@Xaml@UI@Windows@winrt@@UICheckBoxFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0CheckBox@Controls@Xaml@UI@Windows@2@QEAA@XZ@@Z

- ea: `0x18001bca4`
- end: `0x18001bdf2`
- name: `??$call@AEAV_lambda_1_@?1???0CheckBox@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@@?$factory_cache_entry@UCheckBox@Controls@Xaml@UI@Windows@winrt@@UICheckBoxFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0CheckBox@Controls@Xaml@UI@Windows@2@QEAA@XZ@@Z`
- size: `334`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001c978`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000e70c`
- `0x18000f3bc`
- `0x18001bca4`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1___0CheckBox_Controls_Xaml_UI_Windows_winrt__QEAA_XZ____factory_cache_entry_UCheckBox_Controls_Xaml_UI_Windows_winrt__UICheckBoxFactory_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1___0CheckBox_Controls_Xaml_UI_Windows_2_QEAA_XZ__Z(
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
  v10[1] = 33;
  v11 = L"Windows.UI.Xaml.Controls.CheckBox";
  v9 = v10;
  v13 = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::ICheckBoxFactory>,
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
    v13 = &qword_18003C118;
    _InterlockedIncrement64(&qword_18003C118);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::CheckBox,winrt::Windows::UI::Xaml::Controls::ICheckBoxFactory>,
            (signed __int64)v5,
            0) )
    {
      v5 = 0;
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C120);
    }
    `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton'::`2'::_lambda_1_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::CheckBox,winrt::Windows::UI::Xaml::Controls::ICheckBoxFactory>);
    _InterlockedDecrement64(&qword_18003C118);
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
0x18001bca4  mov     [rsp-18h+arg_8], rbx
0x18001bca9  mov     [rsp-18h+arg_0], rcx
0x18001bcae  push    rbp
0x18001bcaf  push    rsi
0x18001bcb0  push    rdi
0x18001bcb1  mov     rbp, rsp
0x18001bcb4  sub     rsp, 60h
0x18001bcb8  mov     rsi, r8
0x18001bcbb  mov     rdi, rdx
0x18001bcbe  mov     [rbp+var_18], 1
0x18001bcc5  mov     [rbp+var_14], 21h ; '!'
0x18001bccc  lea     rax, aWindowsUiXamlC_5; "Windows.UI.Xaml.Controls.CheckBox"
0x18001bcd3  mov     [rbp+var_8], rax
0x18001bcd7  lea     rax, [rbp+var_18]
0x18001bcdb  mov     [rbp+var_20], rax
0x18001bcdf  mov     [rbp+arg_18], 0
0x18001bce7  mov     [rbp+var_38], 0
0x18001bcee  xorps   xmm0, xmm0
0x18001bcf1  movdqu  [rbp+var_30], xmm0
0x18001bcf6  lea     r9, [rbp+arg_18]
0x18001bcfa  lea     r8, ??$guid_v@UICheckBoxFactory@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::ICheckBoxFactory>
0x18001bd01  lea     rdx, [rbp+var_20]
0x18001bd05  lea     rcx, [rbp+arg_0]
0x18001bd09  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001bd0e  mov     ecx, dword ptr [rbp+arg_0]
0x18001bd11  test    ecx, ecx
0x18001bd13  js      loc_18001BDE8
0x18001bd19  mov     rbx, [rbp+arg_18]
0x18001bd1d  mov     [rbp+arg_0], rbx
0x18001bd21  test    rbx, rbx
0x18001bd24  jz      loc_18001BDB7
0x18001bd2a  mov     [rbp+arg_18], 0
0x18001bd32  mov     rax, [rbx]
0x18001bd35  lea     r8, [rbp+arg_18]
0x18001bd39  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001bd40  mov     rcx, rbx
0x18001bd43  mov     rax, [rax]
0x18001bd46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd4b  mov     rax, [rbp+arg_18]
0x18001bd4f  mov     [rbp+arg_18], rax
0x18001bd53  test    rax, rax
0x18001bd56  jz      short loc_18001BDB7
0x18001bd58  lea     rcx, [rbp+arg_18]
0x18001bd5c  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001bd61  lea     rax, qword_18003C118
0x18001bd68  mov     [rbp+arg_18], rax
0x18001bd6c  lock inc cs:qword_18003C118
0x18001bd74  xor     eax, eax
0x18001bd76  lock cmpxchg cs:??$factory_cache_entry_v@UCheckBox@Controls@Xaml@UI@Windows@winrt@@UICheckBoxFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UCheckBox@Controls@Xaml@UI@Windows@winrt@@UICheckBoxFactory@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::CheckBox,winrt::Windows::UI::Xaml::Controls::ICheckBoxFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::CheckBox,winrt::Windows::UI::Xaml::Controls::ICheckBoxFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::CheckBox,winrt::Windows::UI::Xaml::Controls::ICheckBoxFactory>
0x18001bd7f  jnz     short loc_18001BD9A
0x18001bd81  xor     ebx, ebx
0x18001bd83  mov     [rbp+arg_0], rbx
0x18001bd87  lea     rdx, stru_18003C120; ListEntry
0x18001bd8e  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001bd95  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001bd9a  lea     r8, ??$factory_cache_entry_v@UCheckBox@Controls@Xaml@UI@Windows@winrt@@UICheckBoxFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UCheckBox@Controls@Xaml@UI@Windows@winrt@@UICheckBoxFactory@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::CheckBox,winrt::Windows::UI::Xaml::Controls::ICheckBoxFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::CheckBox,winrt::Windows::UI::Xaml::Controls::ICheckBoxFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::CheckBox,winrt::Windows::UI::Xaml::Controls::ICheckBoxFactory>
0x18001bda1  mov     rdx, rdi
0x18001bda4  mov     rcx, rsi
0x18001bda7  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x18001bdac  nop
0x18001bdad  lock dec cs:qword_18003C118
0x18001bdb5  jmp     short loc_18001BDC7
0x18001bdb7  lea     r8, [rbp+arg_0]
0x18001bdbb  mov     rdx, rdi
0x18001bdbe  mov     rcx, rsi
0x18001bdc1  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x18001bdc6  nop
0x18001bdc7  test    rbx, rbx
0x18001bdca  jz      short loc_18001BDD5
0x18001bdcc  lea     rcx, [rbp+arg_0]
0x18001bdd0  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001bdd5  mov     rax, rdi
0x18001bdd8  mov     rbx, [rsp+60h+arg_8]
0x18001bde0  add     rsp, 60h
0x18001bde4  pop     rdi
0x18001bde5  pop     rsi
0x18001bde6  pop     rbp
0x18001bde7  retn
0x18001bde8  lea     rdx, [rbp+var_38]
0x18001bdec  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
