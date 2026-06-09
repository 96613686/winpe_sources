# ??$call@AEAV_lambda_1_@?1??GetParent@VisualTreeHelper@Media@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@5678@@Z@@?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetParent@VisualTreeHelper@Media@Xaml@UI@Windows@2@SA@AEBUDependencyObject@7892@@Z@@Z

- ea: `0x18001c564`
- end: `0x18001c6ef`
- name: `??$call@AEAV_lambda_1_@?1??GetParent@VisualTreeHelper@Media@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@5678@@Z@@?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetParent@VisualTreeHelper@Media@Xaml@UI@Windows@2@SA@AEBUDependencyObject@7892@@Z@@Z`
- size: `395`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001eaec`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18001c564`
- `0x18001c6f8`
- `0x18002d010`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__GetParent_VisualTreeHelper_Media_Xaml_UI_Windows_winrt__SA_AEBUDependencyObject_5678__Z____factory_cache_entry_UVisualTreeHelper_Media_Xaml_UI_Windows_winrt__UIVisualTreeHelperStatics_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1__GetParent_VisualTreeHelper_Media_Xaml_UI_Windows_2_SA_AEBUDependencyObject_7892__Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rdi
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h]
  _DWORD *v11; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-10h]
  void (__fastcall ***v14)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+20h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a1;
  v12[0] = 1;
  v12[1] = 38;
  v13 = L"Windows.UI.Xaml.Media.VisualTreeHelper";
  v11 = v12;
  winrt::get_activation_factory<winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>(&v14, &v11);
  v5 = (signed __int64)v14;
  if ( !v14 || (v15 = 0, (**v14)(v14, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v15), !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v5 + 96LL))(v5, **a3, &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_10;
  }
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_18003C2F8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>,
          v5,
          0) )
  {
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C300);
    v5 = 0;
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>
                                                             + 96LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>,
         **a3,
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_18003C2F8);
  if ( v5 )
LABEL_10:
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x18001c564  mov     [rsp-18h+arg_8], rbx
0x18001c569  mov     [rsp-18h+arg_0], rcx
0x18001c56e  push    rbp
0x18001c56f  push    rsi
0x18001c570  push    rdi
0x18001c571  mov     rbp, rsp
0x18001c574  sub     rsp, 70h
0x18001c578  mov     rsi, r8
0x18001c57b  mov     rbx, rdx
0x18001c57e  mov     [rbp+var_20], 1
0x18001c585  mov     [rbp+var_1C], 26h ; '&'
0x18001c58c  lea     rax, aWindowsUiXamlM; "Windows.UI.Xaml.Media.VisualTreeHelper"
0x18001c593  mov     [rbp+var_10], rax
0x18001c597  lea     rax, [rbp+var_20]
0x18001c59b  mov     [rbp+var_28], rax
0x18001c59f  lea     rdx, [rbp+var_28]
0x18001c5a3  lea     rcx, [rbp+arg_0]
0x18001c5a7  call    ??$get_activation_factory@UIVisualTreeHelperStatics@Media@Xaml@UI@Windows@winrt@@@winrt@@YA?AUIVisualTreeHelperStatics@Media@Xaml@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>(winrt::param::hstring const &)
0x18001c5ac  nop
0x18001c5ad  mov     rdi, [rbp+arg_0]
0x18001c5b1  test    rdi, rdi
0x18001c5b4  jz      loc_18001C680
0x18001c5ba  mov     [rbp+arg_18], 0
0x18001c5c2  mov     rax, [rdi]
0x18001c5c5  lea     r8, [rbp+arg_18]
0x18001c5c9  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c5d0  mov     rcx, rdi
0x18001c5d3  mov     rax, [rax]
0x18001c5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5db  mov     rax, [rbp+arg_18]
0x18001c5df  mov     [rbp+arg_18], rax
0x18001c5e3  test    rax, rax
0x18001c5e6  jz      loc_18001C680
0x18001c5ec  lea     rcx, [rbp+arg_18]
0x18001c5f0  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c5f5  lea     rax, qword_18003C2F8
0x18001c5fc  mov     [rbp+var_48], rax
0x18001c600  lock inc cs:qword_18003C2F8
0x18001c608  xor     eax, eax
0x18001c60a  lock cmpxchg cs:??$factory_cache_entry_v@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@12@A, rdi; factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>
0x18001c613  jnz     short loc_18001C632
0x18001c615  mov     [rbp+arg_0], 0
0x18001c61d  lea     rdx, stru_18003C300; ListEntry
0x18001c624  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c62b  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c630  xor     edi, edi
0x18001c632  mov     [rbp+arg_18], 0
0x18001c63a  mov     rcx, cs:??$factory_cache_entry_v@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>
0x18001c641  mov     [rbp+var_40], 0
0x18001c648  xorps   xmm0, xmm0
0x18001c64b  movdqu  [rbp+var_38], xmm0
0x18001c650  mov     rax, [rcx]
0x18001c653  mov     rdx, [rsi]
0x18001c656  lea     r8, [rbp+arg_18]
0x18001c65a  mov     rdx, [rdx]
0x18001c65d  mov     rax, [rax+60h]
0x18001c661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c666  test    eax, eax
0x18001c668  js      short loc_18001C6E3
0x18001c66a  mov     rax, [rbp+arg_18]
0x18001c66e  mov     [rbx], rax
0x18001c671  lock dec cs:qword_18003C2F8
0x18001c679  test    rdi, rdi
0x18001c67c  jz      short loc_18001C6C4
0x18001c67e  jmp     short loc_18001C6BB
0x18001c680  mov     [rbp+arg_18], 0
0x18001c688  mov     [rbp+var_40], 0
0x18001c68f  xorps   xmm0, xmm0
0x18001c692  movdqu  [rbp+var_38], xmm0
0x18001c697  mov     rax, [rdi]
0x18001c69a  mov     rdx, [rsi]
0x18001c69d  lea     r8, [rbp+arg_18]
0x18001c6a1  mov     rdx, [rdx]
0x18001c6a4  mov     rcx, rdi
0x18001c6a7  mov     rax, [rax+60h]
0x18001c6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6b0  test    eax, eax
0x18001c6b2  js      short loc_18001C6D7
0x18001c6b4  mov     rax, [rbp+arg_18]
0x18001c6b8  mov     [rbx], rax
0x18001c6bb  lea     rcx, [rbp+arg_0]
0x18001c6bf  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c6c4  mov     rax, rbx
0x18001c6c7  mov     rbx, [rsp+70h+arg_8]
0x18001c6cf  add     rsp, 70h
0x18001c6d3  pop     rdi
0x18001c6d4  pop     rsi
0x18001c6d5  pop     rbp
0x18001c6d6  retn
0x18001c6d7  lea     rdx, [rbp+var_40]
0x18001c6db  mov     ecx, eax
0x18001c6dd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001c6e3  lea     rdx, [rbp+var_40]
0x18001c6e7  mov     ecx, eax
0x18001c6e9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
