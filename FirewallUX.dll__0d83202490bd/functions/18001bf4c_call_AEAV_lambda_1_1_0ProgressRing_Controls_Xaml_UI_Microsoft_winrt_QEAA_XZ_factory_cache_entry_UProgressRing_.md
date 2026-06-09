# ??$call@AEAV_lambda_1_@?1???0ProgressRing@Controls@Xaml@UI@Microsoft@winrt@@QEAA@XZ@@?$factory_cache_entry@UProgressRing@Controls@Xaml@UI@Microsoft@winrt@@UIProgressRingFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0ProgressRing@Controls@Xaml@UI@Microsoft@2@QEAA@XZ@@Z

- ea: `0x18001bf4c`
- end: `0x18001c09a`
- name: `??$call@AEAV_lambda_1_@?1???0ProgressRing@Controls@Xaml@UI@Microsoft@winrt@@QEAA@XZ@@?$factory_cache_entry@UProgressRing@Controls@Xaml@UI@Microsoft@winrt@@UIProgressRingFactory@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1???0ProgressRing@Controls@Xaml@UI@Microsoft@2@QEAA@XZ@@Z`
- size: `334`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001e0b0`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000e70c`
- `0x18000f3bc`
- `0x18001bf4c`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1___0ProgressRing_Controls_Xaml_UI_Microsoft_winrt__QEAA_XZ____factory_cache_entry_UProgressRing_Controls_Xaml_UI_Microsoft_winrt__UIProgressRingFactory_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1___0ProgressRing_Controls_Xaml_UI_Microsoft_2_QEAA_XZ__Z(
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
  v10[1] = 39;
  v11 = L"Microsoft.UI.Xaml.Controls.ProgressRing";
  v9 = v10;
  v13 = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    &winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::Controls::IProgressRingFactory>,
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
    v13 = &qword_18003BE88;
    _InterlockedIncrement64(&qword_18003BE88);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::UI::Xaml::Controls::ProgressRing,winrt::Microsoft::UI::Xaml::Controls::IProgressRingFactory>,
            (signed __int64)v5,
            0) )
    {
      v5 = 0;
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003BE90);
    }
    `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton'::`2'::_lambda_1_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::UI::Xaml::Controls::ProgressRing,winrt::Microsoft::UI::Xaml::Controls::IProgressRingFactory>);
    _InterlockedDecrement64(&qword_18003BE88);
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
0x18001bf4c  mov     [rsp-18h+arg_8], rbx
0x18001bf51  mov     [rsp-18h+arg_0], rcx
0x18001bf56  push    rbp
0x18001bf57  push    rsi
0x18001bf58  push    rdi
0x18001bf59  mov     rbp, rsp
0x18001bf5c  sub     rsp, 60h
0x18001bf60  mov     rsi, r8
0x18001bf63  mov     rdi, rdx
0x18001bf66  mov     [rbp+var_18], 1
0x18001bf6d  mov     [rbp+var_14], 27h ; '''
0x18001bf74  lea     rax, aMicrosoftUiXam; "Microsoft.UI.Xaml.Controls.ProgressRing"
0x18001bf7b  mov     [rbp+var_8], rax
0x18001bf7f  lea     rax, [rbp+var_18]
0x18001bf83  mov     [rbp+var_20], rax
0x18001bf87  mov     [rbp+arg_18], 0
0x18001bf8f  mov     [rbp+var_38], 0
0x18001bf96  xorps   xmm0, xmm0
0x18001bf99  movdqu  [rbp+var_30], xmm0
0x18001bf9e  lea     r9, [rbp+arg_18]
0x18001bfa2  lea     r8, ??$guid_v@UIProgressRingFactory@Controls@Xaml@UI@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::UI::Xaml::Controls::IProgressRingFactory>
0x18001bfa9  lea     rdx, [rbp+var_20]
0x18001bfad  lea     rcx, [rbp+arg_0]
0x18001bfb1  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001bfb6  mov     ecx, dword ptr [rbp+arg_0]
0x18001bfb9  test    ecx, ecx
0x18001bfbb  js      loc_18001C090
0x18001bfc1  mov     rbx, [rbp+arg_18]
0x18001bfc5  mov     [rbp+arg_0], rbx
0x18001bfc9  test    rbx, rbx
0x18001bfcc  jz      loc_18001C05F
0x18001bfd2  mov     [rbp+arg_18], 0
0x18001bfda  mov     rax, [rbx]
0x18001bfdd  lea     r8, [rbp+arg_18]
0x18001bfe1  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001bfe8  mov     rcx, rbx
0x18001bfeb  mov     rax, [rax]
0x18001bfee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bff3  mov     rax, [rbp+arg_18]
0x18001bff7  mov     [rbp+arg_18], rax
0x18001bffb  test    rax, rax
0x18001bffe  jz      short loc_18001C05F
0x18001c000  lea     rcx, [rbp+arg_18]
0x18001c004  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c009  lea     rax, qword_18003BE88
0x18001c010  mov     [rbp+arg_18], rax
0x18001c014  lock inc cs:qword_18003BE88
0x18001c01c  xor     eax, eax
0x18001c01e  lock cmpxchg cs:??$factory_cache_entry_v@UProgressRing@Controls@Xaml@UI@Microsoft@winrt@@UIProgressRingFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UProgressRing@Controls@Xaml@UI@Microsoft@winrt@@UIProgressRingFactory@23456@@12@A, rbx; factory_cache_entry<winrt::Microsoft::UI::Xaml::Controls::ProgressRing,winrt::Microsoft::UI::Xaml::Controls::IProgressRingFactory>::winrt::factory_cache_entry<winrt::Microsoft::UI::Xaml::Controls::ProgressRing,winrt::Microsoft::UI::Xaml::Controls::IProgressRingFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::UI::Xaml::Controls::ProgressRing,winrt::Microsoft::UI::Xaml::Controls::IProgressRingFactory>
0x18001c027  jnz     short loc_18001C042
0x18001c029  xor     ebx, ebx
0x18001c02b  mov     [rbp+arg_0], rbx
0x18001c02f  lea     rdx, stru_18003BE90; ListEntry
0x18001c036  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c03d  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c042  lea     r8, ??$factory_cache_entry_v@UProgressRing@Controls@Xaml@UI@Microsoft@winrt@@UIProgressRingFactory@23456@@impl@winrt@@3U?$factory_cache_entry@UProgressRing@Controls@Xaml@UI@Microsoft@winrt@@UIProgressRingFactory@23456@@12@A; factory_cache_entry<winrt::Microsoft::UI::Xaml::Controls::ProgressRing,winrt::Microsoft::UI::Xaml::Controls::IProgressRingFactory>::winrt::factory_cache_entry<winrt::Microsoft::UI::Xaml::Controls::ProgressRing,winrt::Microsoft::UI::Xaml::Controls::IProgressRingFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::UI::Xaml::Controls::ProgressRing,winrt::Microsoft::UI::Xaml::Controls::IProgressRingFactory>
0x18001c049  mov     rdx, rdi
0x18001c04c  mov     rcx, rsi
0x18001c04f  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x18001c054  nop
0x18001c055  lock dec cs:qword_18003BE88
0x18001c05d  jmp     short loc_18001C06F
0x18001c05f  lea     r8, [rbp+arg_0]
0x18001c063  mov     rdx, rdi
0x18001c066  mov     rcx, rsi
0x18001c069  call    ??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z; `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)
0x18001c06e  nop
0x18001c06f  test    rbx, rbx
0x18001c072  jz      short loc_18001C07D
0x18001c074  lea     rcx, [rbp+arg_0]
0x18001c078  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c07d  mov     rax, rdi
0x18001c080  mov     rbx, [rsp+60h+arg_8]
0x18001c088  add     rsp, 60h
0x18001c08c  pop     rdi
0x18001c08d  pop     rsi
0x18001c08e  pop     rbp
0x18001c08f  retn
0x18001c090  lea     rdx, [rbp+var_38]
0x18001c094  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
