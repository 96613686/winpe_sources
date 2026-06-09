# ??$call@AEAV_lambda_1_@?1??GetChildrenCount@VisualTreeHelper@Media@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@5678@@Z@@?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetChildrenCount@VisualTreeHelper@Media@Xaml@UI@Windows@2@SA@AEBUDependencyObject@7892@@Z@@Z

- ea: `0x18001c3e4`
- end: `0x18001c55d`
- name: `??$call@AEAV_lambda_1_@?1??GetChildrenCount@VisualTreeHelper@Media@Xaml@UI@Windows@winrt@@SA@AEBUDependencyObject@5678@@Z@@?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetChildrenCount@VisualTreeHelper@Media@Xaml@UI@Windows@2@SA@AEBUDependencyObject@7892@@Z@@Z`
- size: `377`
- prototype: `__int64 __fastcall(__int64, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e8a4`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18001c3e4`
- `0x18001c6f8`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__GetChildrenCount_VisualTreeHelper_Media_Xaml_UI_Windows_winrt__SA_AEBUDependencyObject_5678__Z____factory_cache_entry_UVisualTreeHelper_Media_Xaml_UI_Windows_winrt__UIVisualTreeHelperStatics_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1__GetChildrenCount_VisualTreeHelper_Media_Xaml_UI_Windows_2_SA_AEBUDependencyObject_7892__Z__Z(
        __int64 a1,
        _QWORD **a2)
{
  signed __int64 v3; // rbx
  int v4; // eax
  unsigned int v5; // edi
  int v7; // eax
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int128 v9; // [rsp+28h] [rbp-38h]
  _DWORD *v10; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v11[4]; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v12; // [rsp+50h] [rbp-10h]
  __int64 v13; // [rsp+80h] [rbp+20h] BYREF
  void (__fastcall ***v14)(_QWORD, __int64 *, __int64 *); // [rsp+90h] [rbp+30h] BYREF
  __int64 *v15; // [rsp+98h] [rbp+38h]

  v13 = a1;
  v11[0] = 1;
  v11[1] = 38;
  v12 = L"Windows.UI.Xaml.Media.VisualTreeHelper";
  v10 = v11;
  winrt::get_activation_factory<winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>(&v14, &v10);
  v3 = (signed __int64)v14;
  if ( v14 && (v13 = 0, (**v14)(v14, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v13), v13) )
  {
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v13);
    v15 = &qword_18003C2F8;
    _InterlockedIncrement64(&qword_18003C2F8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>,
            v3,
            0) )
    {
      v14 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C300);
      v3 = 0;
    }
    LODWORD(v13) = 0;
    v8 = 0;
    v9 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>
                                                               + 88LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>,
           **a2,
           &v13);
    if ( v4 < 0 )
      winrt::throw_hresult((unsigned int)v4, &v8);
    v5 = v13;
    _InterlockedDecrement64(&qword_18003C2F8);
    if ( v3 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v14);
    return v5;
  }
  else
  {
    LODWORD(v13) = 0;
    v8 = 0;
    v9 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, __int64 *))(*(_QWORD *)v3 + 88LL))(v3, **a2, &v13);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v8);
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v14);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x18001c3e4  mov     [rsp-18h+arg_0], rcx
0x18001c3e9  push    rbp
0x18001c3ea  push    rbx
0x18001c3eb  push    rdi
0x18001c3ec  mov     rbp, rsp
0x18001c3ef  sub     rsp, 60h
0x18001c3f3  mov     rdi, rdx
0x18001c3f6  mov     [rbp+var_20], 1
0x18001c3fd  mov     [rbp+var_1C], 26h ; '&'
0x18001c404  lea     rax, aWindowsUiXamlM; "Windows.UI.Xaml.Media.VisualTreeHelper"
0x18001c40b  mov     [rbp+var_10], rax
0x18001c40f  lea     rax, [rbp+var_20]
0x18001c413  mov     [rbp+var_28], rax
0x18001c417  lea     rdx, [rbp+var_28]
0x18001c41b  lea     rcx, [rbp+arg_10]
0x18001c41f  call    ??$get_activation_factory@UIVisualTreeHelperStatics@Media@Xaml@UI@Windows@winrt@@@winrt@@YA?AUIVisualTreeHelperStatics@Media@Xaml@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>(winrt::param::hstring const &)
0x18001c424  nop
0x18001c425  mov     rbx, [rbp+arg_10]
0x18001c429  test    rbx, rbx
0x18001c42c  jz      loc_18001C4FE
0x18001c432  mov     [rbp+arg_0], 0
0x18001c43a  mov     rax, [rbx]
0x18001c43d  lea     r8, [rbp+arg_0]
0x18001c441  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001c448  mov     rcx, rbx
0x18001c44b  mov     rax, [rax]
0x18001c44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c453  mov     rax, [rbp+arg_0]
0x18001c457  mov     [rbp+arg_0], rax
0x18001c45b  test    rax, rax
0x18001c45e  jz      loc_18001C4FE
0x18001c464  lea     rcx, [rbp+arg_0]
0x18001c468  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c46d  lea     rax, qword_18003C2F8
0x18001c474  mov     [rbp+arg_18], rax
0x18001c478  lock inc cs:qword_18003C2F8
0x18001c480  xor     eax, eax
0x18001c482  lock cmpxchg cs:??$factory_cache_entry_v@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>
0x18001c48b  jnz     short loc_18001C4AA
0x18001c48d  mov     [rbp+arg_10], 0
0x18001c495  lea     rdx, stru_18003C300; ListEntry
0x18001c49c  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001c4a3  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001c4a8  xor     ebx, ebx
0x18001c4aa  mov     dword ptr [rbp+arg_0], 0
0x18001c4b1  mov     rcx, cs:??$factory_cache_entry_v@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UVisualTreeHelper@Media@Xaml@UI@Windows@winrt@@UIVisualTreeHelperStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::VisualTreeHelper,winrt::Windows::UI::Xaml::Media::IVisualTreeHelperStatics>
0x18001c4b8  mov     [rbp+var_40], 0
0x18001c4bf  xorps   xmm0, xmm0
0x18001c4c2  movdqu  [rbp+var_38], xmm0
0x18001c4c7  mov     rax, [rcx]
0x18001c4ca  mov     rdx, [rdi]
0x18001c4cd  lea     r8, [rbp+arg_0]
0x18001c4d1  mov     rdx, [rdx]
0x18001c4d4  mov     rax, [rax+58h]
0x18001c4d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4dd  test    eax, eax
0x18001c4df  js      short loc_18001C551
0x18001c4e1  mov     edi, dword ptr [rbp+arg_0]
0x18001c4e4  lock dec cs:qword_18003C2F8
0x18001c4ec  test    rbx, rbx
0x18001c4ef  jz      short loc_18001C4FA
0x18001c4f1  lea     rcx, [rbp+arg_10]
0x18001c4f5  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c4fa  mov     eax, edi
0x18001c4fc  jmp     short loc_18001C53D
0x18001c4fe  mov     dword ptr [rbp+arg_0], 0
0x18001c505  mov     [rbp+var_40], 0
0x18001c50c  xorps   xmm0, xmm0
0x18001c50f  movdqu  [rbp+var_38], xmm0
0x18001c514  mov     rax, [rbx]
0x18001c517  mov     rdx, [rdi]
0x18001c51a  lea     r8, [rbp+arg_0]
0x18001c51e  mov     rdx, [rdx]
0x18001c521  mov     rcx, rbx
0x18001c524  mov     rax, [rax+58h]
0x18001c528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c52d  test    eax, eax
0x18001c52f  js      short loc_18001C545
0x18001c531  lea     rcx, [rbp+arg_10]
0x18001c535  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18001c53a  mov     eax, dword ptr [rbp+arg_0]
0x18001c53d  add     rsp, 60h
0x18001c541  pop     rdi
0x18001c542  pop     rbx
0x18001c543  pop     rbp
0x18001c544  retn
0x18001c545  lea     rdx, [rbp+var_40]
0x18001c549  mov     ecx, eax
0x18001c54b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001c551  lea     rdx, [rbp+var_40]
0x18001c555  mov     ecx, eax
0x18001c557  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
