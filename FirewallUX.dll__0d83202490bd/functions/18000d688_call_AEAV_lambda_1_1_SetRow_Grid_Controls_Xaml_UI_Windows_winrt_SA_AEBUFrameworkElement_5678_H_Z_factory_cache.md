# ??$call@AEAV_lambda_1_@?1??SetRow@Grid@Controls@Xaml@UI@Windows@winrt@@SA@AEBUFrameworkElement@5678@H@Z@@?$factory_cache_entry@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??SetRow@Grid@Controls@Xaml@UI@Windows@2@SA@AEBUFrameworkElement@7892@H@Z@@Z

- ea: `0x18000d688`
- end: `0x18000d7fa`
- name: `??$call@AEAV_lambda_1_@?1??SetRow@Grid@Controls@Xaml@UI@Windows@winrt@@SA@AEBUFrameworkElement@5678@H@Z@@?$factory_cache_entry@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??SetRow@Grid@Controls@Xaml@UI@Windows@2@SA@AEBUFrameworkElement@7892@H@Z@@Z`
- size: `370`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800132ac`

## callees

- `0x180003e21`
- `0x18000b24c`
- `0x18000b5d0`
- `0x18000d688`
- `0x18000e264`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__SetRow_Grid_Controls_Xaml_UI_Windows_winrt__SA_AEBUFrameworkElement_5678_H_Z____factory_cache_entry_UGrid_Controls_Xaml_UI_Windows_winrt__UIGridStatics_23456__impl_winrt__QEAA_A_PAEAV_lambda_1___1__SetRow_Grid_Controls_Xaml_UI_Windows_2_SA_AEBUFrameworkElement_7892_H_Z__Z(
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
    v5 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 64LL))(
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
                                                              + 64LL))(
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
0x18000d688  mov     [rsp-8+arg_8], rbx
0x18000d68d  mov     [rsp-8+arg_18], rdi
0x18000d692  mov     [rsp-8+arg_0], rcx
0x18000d697  push    rbp
0x18000d698  mov     rbp, rsp
0x18000d69b  sub     rsp, 60h
0x18000d69f  mov     rdi, rdx
0x18000d6a2  mov     [rbp+var_20], 1
0x18000d6a9  mov     [rbp+var_1C], 1Dh
0x18000d6b0  lea     rax, aWindowsUiXamlC_8; "Windows.UI.Xaml.Controls.Grid"
0x18000d6b7  mov     [rbp+var_10], rax
0x18000d6bb  lea     rax, [rbp+var_20]
0x18000d6bf  mov     [rbp+var_28], rax
0x18000d6c3  lea     rdx, [rbp+var_28]
0x18000d6c7  lea     rcx, [rbp+arg_0]
0x18000d6cb  call    ??$get_activation_factory@UIGridStatics@Controls@Xaml@UI@Windows@winrt@@@winrt@@YA?AUIGridStatics@Controls@Xaml@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Xaml::Controls::IGridStatics>(winrt::param::hstring const &)
0x18000d6d0  nop
0x18000d6d1  mov     rbx, [rbp+arg_0]
0x18000d6d5  test    rbx, rbx
0x18000d6d8  jz      loc_18000D798
0x18000d6de  mov     [rbp+arg_10], 0
0x18000d6e6  mov     rax, [rbx]
0x18000d6e9  lea     r8, [rbp+arg_10]
0x18000d6ed  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000d6f4  mov     rcx, rbx
0x18000d6f7  mov     rax, [rax]
0x18000d6fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6ff  mov     rax, [rbp+arg_10]
0x18000d703  mov     [rbp+arg_10], rax
0x18000d707  test    rax, rax
0x18000d70a  jz      loc_18000D798
0x18000d710  lea     rcx, [rbp+arg_10]
0x18000d714  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d719  lea     rax, qword_18003C178
0x18000d720  mov     [rbp+arg_10], rax
0x18000d724  lock inc cs:qword_18003C178
0x18000d72c  xor     eax, eax
0x18000d72e  lock cmpxchg cs:??$factory_cache_entry_v@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>
0x18000d737  jnz     short loc_18000D756
0x18000d739  mov     [rbp+arg_0], 0
0x18000d741  lea     rdx, stru_18003C180; ListEntry
0x18000d748  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000d74f  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000d754  xor     ebx, ebx
0x18000d756  mov     rcx, cs:??$factory_cache_entry_v@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UGrid@Controls@Xaml@UI@Windows@winrt@@UIGridStatics@23456@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Grid,winrt::Windows::UI::Xaml::Controls::IGridStatics>
0x18000d75d  mov     [rbp+var_40], 0
0x18000d764  xorps   xmm0, xmm0
0x18000d767  movdqu  [rbp+var_38], xmm0
0x18000d76c  mov     rax, [rcx]
0x18000d76f  mov     r8, [rdi+8]
0x18000d773  mov     rdx, [rdi]
0x18000d776  mov     r8d, [r8]
0x18000d779  mov     rdx, [rdx]
0x18000d77c  mov     rax, [rax+40h]
0x18000d780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d785  test    eax, eax
0x18000d787  js      short loc_18000D7EE
0x18000d789  lock dec cs:qword_18003C178
0x18000d791  test    rbx, rbx
0x18000d794  jz      short loc_18000D7D0
0x18000d796  jmp     short loc_18000D7C7
0x18000d798  mov     [rbp+var_40], 0
0x18000d79f  xorps   xmm0, xmm0
0x18000d7a2  movdqu  [rbp+var_38], xmm0
0x18000d7a7  mov     rax, [rbx]
0x18000d7aa  mov     r8, [rdi+8]
0x18000d7ae  mov     rdx, [rdi]
0x18000d7b1  mov     r8d, [r8]
0x18000d7b4  mov     rdx, [rdx]
0x18000d7b7  mov     rcx, rbx
0x18000d7ba  mov     rax, [rax+40h]
0x18000d7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7c3  test    eax, eax
0x18000d7c5  js      short loc_18000D7E2
0x18000d7c7  lea     rcx, [rbp+arg_0]
0x18000d7cb  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000d7d0  lea     r11, [rsp+60h+var_s0]
0x18000d7d5  mov     rbx, [r11+18h]
0x18000d7d9  mov     rdi, [r11+28h]
0x18000d7dd  mov     rsp, r11
0x18000d7e0  pop     rbp
0x18000d7e1  retn
0x18000d7e2  lea     rdx, [rbp+var_40]
0x18000d7e6  mov     ecx, eax
0x18000d7e8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000d7ee  lea     rdx, [rbp+var_40]
0x18000d7f2  mov     ecx, eax
0x18000d7f4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
