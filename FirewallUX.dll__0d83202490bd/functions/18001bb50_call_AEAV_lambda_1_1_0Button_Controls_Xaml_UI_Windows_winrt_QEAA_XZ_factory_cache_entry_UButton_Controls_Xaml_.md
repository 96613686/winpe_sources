# ??$call@AEAV_lambda_1_@?1???0Button@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@@?$factory_cache_entry@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0Button@Controls@Xaml@UI@Windows@2@QEAA@XZ@@Z

- ea: `0x18001bb50`
- end: `0x18001bc9e`
- name: `??$call@AEAV_lambda_1_@?1???0Button@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@@?$factory_cache_entry@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0Button@Controls@Xaml@UI@Windows@2@QEAA@XZ@@Z`
- size: `334`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180021d68`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000e70c`
- `0x18000f3bc`
- `0x18001bb50`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1___0Button_Controls_Xaml_UI_Windows_winrt__QEAA_XZ____factory_cache_entry_UButton_Controls_Xaml_UI_Windows_winrt__UIButtonFactory_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1___0Button_Controls_Xaml_UI_Windows_2_QEAA_XZ__Z(
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
  v10[1] = 31;
  v11 = L"Windows.UI.Xaml.Controls.Button";
  v9 = v10;
  v13 = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    &winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IButtonFactory>,
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
    v13 = &qword_18003C0F8;
    _InterlockedIncrement64(&qword_18003C0F8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>,
            (signed __int64)v5,
            0) )
    {
      v5 = 0;
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C100);
    }
    `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton'::`2'::_lambda_1_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>);
    _InterlockedDecrement64(&qword_18003C0F8);
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
0x18001bb50  mov     [rsp-18h+arg_8], rbx
0x18001bb55  mov     [rsp-18h+arg_0], rcx
0x18001bb5a  push    rbp
0x18001bb5b  push    rsi
0x18001bb5c  push    rdi
0x18001bb5d  mov     rbp, rsp
0x18001bb60  sub     rsp, 60h
0x18001bb64  mov     rsi, r8
0x18001bb67  mov     rdi, rdx
0x18001bb6a  mov     [rbp+var_18], 1
0x18001bb71  mov     [rbp+var_14], 1Fh
0x18001bb78  lea     rax, aWindowsUiXamlC; "Windows.UI.Xaml.Controls.Button"
0x18001bb7f  mov     [rbp+var_8], rax
0x18001bb83  lea     rax, [rbp+var_18]
0x18001bb87  mov     [rbp+var_20], rax
0x18001bb8b  mov     [rbp+arg_18], 0
0x18001bb93  mov     [rbp+var_38], 0
0x18001bb9a  xorps   xmm0, xmm0
0x18001bb9d  movdqu  [rbp+var_30], xmm0
0x18001bba2  lea     r9, [rbp+arg_18]
0x18001bba6  lea     r8, ??$guid_v@UIButtonFactory@Controls@Xaml@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Xaml::Controls::IButtonFactory>
0x18001bbad  lea     rdx, [rbp+var_20]
0x18001bbb1  lea     rcx, [rbp+arg_0]
0x18001bbb5  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001bbba  mov     ecx, dword ptr [rbp+arg_0]
0x18001bbbd  test    ecx, ecx
0x18001bbbf  js      loc_18001BC94
0x18001bbc5  mov     rbx, [rbp+arg_18]
0x18001bbc9  mov     [rbp+arg_0], rbx
0x18001bbcd  test    rbx, rbx
0x18001bbd0  jz      loc_18001BC63
0x18001bbd6  mov     [rbp+arg_18], 0
0x18001bbde  mov     rax, [rbx]
0x18001bbe1  lea     r8, [rbp+arg_18]
0x18001bbe5  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001bbec  mov     rcx, rbx
0x18001bbef  mov     rax, [rax]
0x18001bbf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbf7  mov     rax, [rbp+arg_18]
0x18001bbfb  mov     [rbp+arg_18], rax
0x18001bbff  test    rax, rax
0x18001bc02  jz      short loc_18001BC63
0x18001bc04  lea     rcx, [rbp+arg_18]
0x18001bc08  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001bc0d  lea     rax, qword_18003C0F8
0x18001bc14  mov     [rbp+arg_18], rax
0x18001bc18  lock inc cs:qword_18003C0F8
0x18001bc20  xor     eax, eax
0x18001bc22  lock cmpxchg cs:??$factory_cache_entry_v@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>
0x18001bc2b  jnz     short loc_18001BC46
0x18001bc2d  xor     ebx, ebx
0x18001bc2f  mov     [rbp+arg_0], rbx
0x18001bc33  lea     rdx, stru_18003C100; ListEntry
0x18001bc3a  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001bc41  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001bc46  lea     r8, ??$factory_cache_entry_v@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UButton@Controls@Xaml@UI@Windows@winrt@@UIButtonFactory@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Button,winrt::Windows::UI::Xaml::Controls::IButtonFactory>
0x18001bc4d  mov     rdx, rdi
0x18001bc50  mov     rcx, rsi
0x18001bc53  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x18001bc58  nop
0x18001bc59  lock dec cs:qword_18003C0F8
0x18001bc61  jmp     short loc_18001BC73
0x18001bc63  lea     r8, [rbp+arg_0]
0x18001bc67  mov     rdx, rdi
0x18001bc6a  mov     rcx, rsi
0x18001bc6d  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x18001bc72  nop
0x18001bc73  test    rbx, rbx
0x18001bc76  jz      short loc_18001BC81
0x18001bc78  lea     rcx, [rbp+arg_0]
0x18001bc7c  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001bc81  mov     rax, rdi
0x18001bc84  mov     rbx, [rsp+60h+arg_8]
0x18001bc8c  add     rsp, 60h
0x18001bc90  pop     rdi
0x18001bc91  pop     rsi
0x18001bc92  pop     rbp
0x18001bc93  retn
0x18001bc94  lea     rdx, [rbp+var_38]
0x18001bc98  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
