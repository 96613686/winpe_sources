# ??$call@AEAV_lambda_1_@?1??SetColumn@Grid@Controls@Xaml@UI@Windows@winrt@@SA@AEBUFrameworkElement@5678@H@Z@@?$factory_cache_entry@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??SetColumn@Grid@Controls@Xaml@UI@Windows@2@SA@AEBUFrameworkElement@7892@H@Z@@Z

- ea: `0x18000d360`
- end: `0x18000d4d2`
- name: `??$call@AEAV_lambda_1_@?1??SetColumn@Grid@Controls@Xaml@UI@Windows@winrt@@SA@AEBUFrameworkElement@5678@H@Z@@?$factory_cache_entry@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??SetColumn@Grid@Controls@Xaml@UI@Windows@2@SA@AEBUFrameworkElement@7892@H@Z@@Z`
- size: `370`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180013214`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000d360`
- `0x18000e264`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__SetColumn_Grid_Controls_Xaml_UI_Windows_winrt__SA_AEBUFrameworkElement_5678_H_Z____factory_cache_entry_UGrid_Controls_Xaml_UI_Windows_winrt__UIGridStatics_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1__SetColumn_Grid_Controls_Xaml_UI_Windows_2_SA_AEBUFrameworkElement_7892_H_Z__Z(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
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
  void (__fastcall ***v11)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v12; // [rsp+80h] [rbp+20h] BYREF

  v11 = a1;
  v9[0] = 1;
  v9[1] = 29;
  v10 = L"Windows.UI.Xaml.Controls.Grid";
  v8 = v9;
  winrt::get_activation_factory<winrt::Windows::UI::Xaml::Controls::IGridStatics>(&v11, &v8);
  v3 = (signed __int64)v11;
  if ( !v11 || (v12 = 0, (**v11)(v11, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v12), !v12) )
  {
    v6 = 0;
    v7 = 0;
    v5 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 88LL))(
           v3,
           **(_QWORD **)a2,
           **(unsigned int **)(a2 + 8));
    if ( v5 < 0 )
      winrt::throw_hresult((unsigned int)v5, &v6);
    return winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v11);
  }
  winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v12);
  v12 = &qword_18003C178;
  _InterlockedIncrement64(&qword_18003C178);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>,
          v3,
          0) )
  {
    v11 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C180);
    v3 = 0;
  }
  v6 = 0;
  v7 = 0;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>
                                                              + 88LL))(
             winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>,
             **(_QWORD **)a2,
             **(unsigned int **)(a2 + 8));
  if ( (int)result < 0 )
    winrt::throw_hresult((unsigned int)result, &v6);
  _InterlockedDecrement64(&qword_18003C178);
  if ( v3 )
    return winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v11);
  return result;
}

```

## disassembly

```asm
0x18000d360  mov     [rsp-8+arg_8], rbx
0x18000d365  mov     [rsp-8+arg_18], rdi
0x18000d36a  mov     [rsp-8+arg_0], rcx
0x18000d36f  push    rbp
0x18000d370  mov     rbp, rsp
0x18000d373  sub     rsp, 60h
0x18000d377  mov     rdi, rdx
0x18000d37a  mov     [rbp+var_20], 1
0x18000d381  mov     [rbp+var_1C], 1Dh
0x18000d388  lea     rax, aWindowsUiXamlC_8; "Windows.UI.Xaml.Controls.Grid"
0x18000d38f  mov     [rbp+var_10], rax
0x18000d393  lea     rax, [rbp+var_20]
0x18000d397  mov     [rbp+var_28], rax
0x18000d39b  lea     rdx, [rbp+var_28]
0x18000d39f  lea     rcx, [rbp+arg_0]
0x18000d3a3  call    ??$get_activation_factory@UIGridStatics@Controls@Xaml@UI@Windows@winrt@@@winrt@@YA?AUIGridStatics@Controls@Xaml@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Xaml::Controls::IGridStatics>(winrt::param::hstring const &)
0x18000d3a8  nop
0x18000d3a9  mov     rbx, [rbp+arg_0]
0x18000d3ad  test    rbx, rbx
0x18000d3b0  jz      loc_18000D470
0x18000d3b6  mov     [rbp+arg_10], 0
0x18000d3be  mov     rax, [rbx]
0x18000d3c1  lea     r8, [rbp+arg_10]
0x18000d3c5  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000d3cc  mov     rcx, rbx
0x18000d3cf  mov     rax, [rax]
0x18000d3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d7  mov     rax, [rbp+arg_10]
0x18000d3db  mov     [rbp+arg_10], rax
0x18000d3df  test    rax, rax
0x18000d3e2  jz      loc_18000D470
0x18000d3e8  lea     rcx, [rbp+arg_10]
0x18000d3ec  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d3f1  lea     rax, qword_18003C178
0x18000d3f8  mov     [rbp+arg_10], rax
0x18000d3fc  lock inc cs:qword_18003C178
0x18000d404  xor     eax, eax
0x18000d406  lock cmpxchg cs:??$factory_cache_entry_v@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>
0x18000d40f  jnz     short loc_18000D42E
0x18000d411  mov     [rbp+arg_0], 0
0x18000d419  lea     rdx, stru_18003C180; ListEntry
0x18000d420  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000d427  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000d42c  xor     ebx, ebx
0x18000d42e  mov     rcx, cs:??$factory_cache_entry_v@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>
0x18000d435  mov     [rbp+var_40], 0
0x18000d43c  xorps   xmm0, xmm0
0x18000d43f  movdqu  [rbp+var_38], xmm0
0x18000d444  mov     rax, [rcx]
0x18000d447  mov     r8, [rdi+8]
0x18000d44b  mov     rdx, [rdi]
0x18000d44e  mov     r8d, [r8]
0x18000d451  mov     rdx, [rdx]
0x18000d454  mov     rax, [rax+58h]
0x18000d458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d45d  test    eax, eax
0x18000d45f  js      short loc_18000D4C6
0x18000d461  lock dec cs:qword_18003C178
0x18000d469  test    rbx, rbx
0x18000d46c  jz      short loc_18000D4A8
0x18000d46e  jmp     short loc_18000D49F
0x18000d470  mov     [rbp+var_40], 0
0x18000d477  xorps   xmm0, xmm0
0x18000d47a  movdqu  [rbp+var_38], xmm0
0x18000d47f  mov     rax, [rbx]
0x18000d482  mov     r8, [rdi+8]
0x18000d486  mov     rdx, [rdi]
0x18000d489  mov     r8d, [r8]
0x18000d48c  mov     rdx, [rdx]
0x18000d48f  mov     rcx, rbx
0x18000d492  mov     rax, [rax+58h]
0x18000d496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d49b  test    eax, eax
0x18000d49d  js      short loc_18000D4BA
0x18000d49f  lea     rcx, [rbp+arg_0]
0x18000d4a3  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d4a8  lea     r11, [rsp+60h+var_s0]
0x18000d4ad  mov     rbx, [r11+18h]
0x18000d4b1  mov     rdi, [r11+28h]
0x18000d4b5  mov     rsp, r11
0x18000d4b8  pop     rbp
0x18000d4b9  retn
0x18000d4ba  lea     rdx, [rbp+var_40]
0x18000d4be  mov     ecx, eax
0x18000d4c0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d4c6  lea     rdx, [rbp+var_40]
0x18000d4ca  mov     ecx, eax
0x18000d4cc  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
