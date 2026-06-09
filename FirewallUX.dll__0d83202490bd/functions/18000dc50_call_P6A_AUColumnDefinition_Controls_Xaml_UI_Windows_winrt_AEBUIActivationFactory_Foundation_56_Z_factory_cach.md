# ??$call@P6A?AUColumnDefinition@Controls@Xaml@UI@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUColumnDefinition@Controls@Xaml@UI@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z

- ea: `0x18000dc50`
- end: `0x18000dd6c`
- name: `??$call@P6A?AUColumnDefinition@Controls@Xaml@UI@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUColumnDefinition@Controls@Xaml@UI@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z`
- size: `284`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ec0c`

## callees

- `0x180003e21`
- `0x18000b5d0`
- `0x18000dc50`
- `0x18000e204`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::ColumnDefinition,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::UI::Xaml::Controls::ColumnDefinition (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _DWORD *v6; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v7[4]; // [rsp+30h] [rbp-20h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-10h]
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+60h] [rbp+10h] BYREF
  __int64 *v10; // [rsp+78h] [rbp+28h] BYREF

  v9 = a1;
  v7[0] = 1;
  v7[1] = 41;
  v8 = L"Windows.UI.Xaml.Controls.ColumnDefinition";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v10);
    v10 = &qword_18003C138;
    _InterlockedIncrement64(&qword_18003C138);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::ColumnDefinition,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C140);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::ColumnDefinition,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18003C138);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v9);
  }
  if ( v9 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x18000dc50  mov     [rsp-8+arg_8], rbx
0x18000dc55  mov     [rsp-8+arg_10], rdi
0x18000dc5a  mov     [rsp-8+arg_0], rcx
0x18000dc5f  push    rbp
0x18000dc60  mov     rbp, rsp
0x18000dc63  sub     rsp, 50h
0x18000dc67  mov     rdi, r8
0x18000dc6a  mov     rbx, rdx
0x18000dc6d  mov     [rbp+var_20], 1
0x18000dc74  mov     [rbp+var_1C], 29h ; ')'
0x18000dc7b  lea     rax, aWindowsUiXamlC_6; "Windows.UI.Xaml.Controls.ColumnDefiniti"...
0x18000dc82  mov     [rbp+var_10], rax
0x18000dc86  lea     rax, [rbp+var_20]
0x18000dc8a  mov     [rbp+var_28], rax
0x18000dc8e  lea     rdx, [rbp+var_28]
0x18000dc92  lea     rcx, [rbp+arg_0]
0x18000dc96  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18000dc9b  nop
0x18000dc9c  mov     rcx, [rbp+arg_0]
0x18000dca0  test    rcx, rcx
0x18000dca3  jz      loc_18000DD39
0x18000dca9  mov     [rbp+arg_18], 0
0x18000dcb1  mov     rax, [rcx]
0x18000dcb4  lea     r8, [rbp+arg_18]
0x18000dcb8  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000dcbf  mov     rax, [rax]
0x18000dcc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcc7  mov     rax, [rbp+arg_18]
0x18000dccb  mov     [rbp+arg_18], rax
0x18000dccf  test    rax, rax
0x18000dcd2  jz      short loc_18000DD39
0x18000dcd4  lea     rcx, [rbp+arg_18]
0x18000dcd8  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000dcdd  lea     rax, qword_18003C138
0x18000dce4  mov     [rbp+arg_18], rax
0x18000dce8  lock inc cs:qword_18003C138
0x18000dcf0  mov     rcx, [rbp+arg_0]
0x18000dcf4  xor     eax, eax
0x18000dcf6  lock cmpxchg cs:??$factory_cache_entry_v@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, rcx; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::ColumnDefinition,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::ColumnDefinition,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::ColumnDefinition,winrt::Windows::Foundation::IActivationFactory>
0x18000dcff  jnz     short loc_18000DD1C
0x18000dd01  mov     [rbp+arg_0], 0
0x18000dd09  lea     rdx, stru_18003C140; ListEntry
0x18000dd10  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000dd17  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000dd1c  lea     rdx, ??$factory_cache_entry_v@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UColumnDefinition@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::ColumnDefinition,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::ColumnDefinition,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::ColumnDefinition,winrt::Windows::Foundation::IActivationFactory>
0x18000dd23  mov     rcx, rbx
0x18000dd26  mov     rax, [rdi]
0x18000dd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd2e  nop
0x18000dd2f  lock dec cs:qword_18003C138
0x18000dd37  jmp     short loc_18000DD49
0x18000dd39  lea     rdx, [rbp+arg_0]
0x18000dd3d  mov     rcx, rbx
0x18000dd40  mov     rax, [rdi]
0x18000dd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd48  nop
0x18000dd49  cmp     [rbp+arg_0], 0
0x18000dd4e  jz      short loc_18000DD59
0x18000dd50  lea     rcx, [rbp+arg_0]
0x18000dd54  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000dd59  mov     rax, rbx
0x18000dd5c  mov     rbx, [rsp+50h+arg_8]
0x18000dd61  mov     rdi, [rsp+50h+arg_10]
0x18000dd66  add     rsp, 50h
0x18000dd6a  pop     rbp
0x18000dd6b  retn
```
