# ??$call@AEAV_lambda_1_@?1??GetChild@VisualTreeHelper@Media@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@5678@H@Z@@?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetChild@VisualTreeHelper@Media@Xaml@UI@Windows@2@SA@AEBUDependencyObject@7892@H@Z@@Z

- ea: `0x18001c238`
- end: `0x18001c3db`
- name: `??$call@AEAV_lambda_1_@?1??GetChild@VisualTreeHelper@Media@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@5678@H@Z@@?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetChild@VisualTreeHelper@Media@Xaml@UI@Windows@2@SA@AEBUDependencyObject@7892@H@Z@@Z`
- size: `419`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e7ec`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18001c238`
- `0x18001c6f8`
- `0x18002d010`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__GetChild_VisualTreeHelper_Media_Xaml_UI_Windows_winrt__SA_AEBUDependencyObject_5678_H_Z____factory_cache_entry_UVisualTreeHelper_Media_Xaml_UI_Windows_winrt__UIVisualTreeHelperStatics_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1__GetChild_VisualTreeHelper_Media_Xaml_UI_Windows_2_SA_AEBUDependencyObject_7892_H_Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2,
        __int64 a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+40h] [rbp-40h] BYREF
  __int128 v10; // [rsp+48h] [rbp-38h]
  _DWORD *v11; // [rsp+58h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+60h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+70h] [rbp-10h]
  void (__fastcall ***v14)(_QWORD, __int64 *, __int64 *); // [rsp+A0h] [rbp+20h] BYREF
  __int64 v15; // [rsp+B8h] [rbp+38h] BYREF

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
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v5 + 80LL))(
           v5,
           **(_QWORD **)a3,
           **(unsigned int **)(a3 + 8),
           &v15);
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
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>
                                                                     + 80LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>,
         **(_QWORD **)a3,
         **(unsigned int **)(a3 + 8),
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
0x18001c238  mov     [rsp-18h+arg_8], rbx
0x18001c23d  mov     [rsp-18h+arg_0], rcx
0x18001c242  push    rbp
0x18001c243  push    rsi
0x18001c244  push    rdi
0x18001c245  mov     rbp, rsp
0x18001c248  sub     rsp, 80h
0x18001c24f  mov     rsi, r8
0x18001c252  mov     rdi, rdx
0x18001c255  mov     [rbp+var_20], 1
0x18001c25c  mov     [rbp+var_1C], 26h ; '&'
0x18001c263  lea     rax, aWindowsUiXamlM; "Windows.UI.Xaml.Media.VisualTreeHelper"
0x18001c26a  mov     [rbp+var_10], rax
0x18001c26e  lea     rax, [rbp+var_20]
0x18001c272  mov     [rbp+var_28], rax
0x18001c276  lea     rdx, [rbp+var_28]
0x18001c27a  lea     rcx, [rbp+arg_0]
0x18001c27e  call    ??$get_activation_factory@UIVisualTreeHelperStatics@Media@Xaml@UI@Windows@winrt@@@winrt@@YA?AUIVisualTreeHelperStatics@Media@Xaml@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>(winrt::param::hstring const &)
0x18001c283  nop
0x18001c284  mov     rbx, [rbp+arg_0]
0x18001c288  test    rbx, rbx
0x18001c28b  jz      loc_18001C362
0x18001c291  mov     [rbp+arg_18], 0
0x18001c299  mov     rax, [rbx]
0x18001c29c  lea     r8, [rbp+arg_18]
0x18001c2a0  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c2a7  mov     rcx, rbx
0x18001c2aa  mov     rax, [rax]
0x18001c2ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2b2  mov     rax, [rbp+arg_18]
0x18001c2b6  mov     [rbp+arg_18], rax
0x18001c2ba  test    rax, rax
0x18001c2bd  jz      loc_18001C362
0x18001c2c3  lea     rcx, [rbp+arg_18]
0x18001c2c7  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c2cc  lea     rax, qword_18003C2F8
0x18001c2d3  mov     [rbp+var_48], rax
0x18001c2d7  lock inc cs:qword_18003C2F8
0x18001c2df  xor     eax, eax
0x18001c2e1  lock cmpxchg cs:??$factory_cache_entry_v@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>
0x18001c2ea  jnz     short loc_18001C309
0x18001c2ec  mov     [rbp+arg_0], 0
0x18001c2f4  lea     rdx, stru_18003C300; ListEntry
0x18001c2fb  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c302  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c307  xor     ebx, ebx
0x18001c309  mov     [rbp+arg_18], 0
0x18001c311  mov     rcx, cs:??$factory_cache_entry_v@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>
0x18001c318  mov     [rbp+var_40], 0
0x18001c31f  xorps   xmm0, xmm0
0x18001c322  movdqu  [rbp+var_38], xmm0
0x18001c327  mov     rax, [rcx]
0x18001c32a  mov     r8, [rsi+8]
0x18001c32e  mov     rdx, [rsi]
0x18001c331  lea     r9, [rbp+arg_18]
0x18001c335  mov     r8d, [r8]
0x18001c338  mov     rdx, [rdx]
0x18001c33b  mov     rax, [rax+50h]
0x18001c33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c344  test    eax, eax
0x18001c346  js      loc_18001C3CF
0x18001c34c  mov     rax, [rbp+arg_18]
0x18001c350  mov     [rdi], rax
0x18001c353  lock dec cs:qword_18003C2F8
0x18001c35b  test    rbx, rbx
0x18001c35e  jz      short loc_18001C3AD
0x18001c360  jmp     short loc_18001C3A4
0x18001c362  mov     [rbp+arg_18], 0
0x18001c36a  mov     [rbp+var_40], 0
0x18001c371  xorps   xmm0, xmm0
0x18001c374  movdqu  [rbp+var_38], xmm0
0x18001c379  mov     rax, [rbx]
0x18001c37c  mov     r8, [rsi+8]
0x18001c380  mov     rdx, [rsi]
0x18001c383  lea     r9, [rbp+arg_18]
0x18001c387  mov     r8d, [r8]
0x18001c38a  mov     rdx, [rdx]
0x18001c38d  mov     rcx, rbx
0x18001c390  mov     rax, [rax+50h]
0x18001c394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c399  test    eax, eax
0x18001c39b  js      short loc_18001C3C3
0x18001c39d  mov     rax, [rbp+arg_18]
0x18001c3a1  mov     [rdi], rax
0x18001c3a4  lea     rcx, [rbp+arg_0]
0x18001c3a8  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c3ad  mov     rax, rdi
0x18001c3b0  mov     rbx, [rsp+80h+arg_8]
0x18001c3b8  add     rsp, 80h
0x18001c3bf  pop     rdi
0x18001c3c0  pop     rsi
0x18001c3c1  pop     rbp
0x18001c3c2  retn
0x18001c3c3  lea     rdx, [rbp+var_40]
0x18001c3c7  mov     ecx, eax
0x18001c3c9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001c3cf  lea     rdx, [rbp+var_40]
0x18001c3d3  mov     ecx, eax
0x18001c3d5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
