# ??$call@P6A?AUImage@Controls@Xaml@UI@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUImage@Controls@Xaml@UI@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z

- ea: `0x18000dd74`
- end: `0x18000de90`
- name: `??$call@P6A?AUImage@Controls@Xaml@UI@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUImage@Controls@Xaml@UI@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z`
- size: `284`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800104e8`

## callees

- `0x180003e21`
- `0x18000b5d0`
- `0x18000dd74`
- `0x18000e204`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::UI::Xaml::Controls::Image (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
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
  v7[1] = 30;
  v8 = L"Windows.UI.Xaml.Controls.Image";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v10);
    v10 = &qword_18003C1B8;
    _InterlockedIncrement64(&qword_18003C1B8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C1C0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18003C1B8);
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
0x18000dd74  mov     [rsp-8+arg_8], rbx
0x18000dd79  mov     [rsp-8+arg_10], rdi
0x18000dd7e  mov     [rsp-8+arg_0], rcx
0x18000dd83  push    rbp
0x18000dd84  mov     rbp, rsp
0x18000dd87  sub     rsp, 50h
0x18000dd8b  mov     rdi, r8
0x18000dd8e  mov     rbx, rdx
0x18000dd91  mov     [rbp+var_20], 1
0x18000dd98  mov     [rbp+var_1C], 1Eh
0x18000dd9f  lea     rax, aWindowsUiXamlC_4; "Windows.UI.Xaml.Controls.Image"
0x18000dda6  mov     [rbp+var_10], rax
0x18000ddaa  lea     rax, [rbp+var_20]
0x18000ddae  mov     [rbp+var_28], rax
0x18000ddb2  lea     rdx, [rbp+var_28]
0x18000ddb6  lea     rcx, [rbp+arg_0]
0x18000ddba  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18000ddbf  nop
0x18000ddc0  mov     rcx, [rbp+arg_0]
0x18000ddc4  test    rcx, rcx
0x18000ddc7  jz      loc_18000DE5D
0x18000ddcd  mov     [rbp+arg_18], 0
0x18000ddd5  mov     rax, [rcx]
0x18000ddd8  lea     r8, [rbp+arg_18]
0x18000dddc  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000dde3  mov     rax, [rax]
0x18000dde6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddeb  mov     rax, [rbp+arg_18]
0x18000ddef  mov     [rbp+arg_18], rax
0x18000ddf3  test    rax, rax
0x18000ddf6  jz      short loc_18000DE5D
0x18000ddf8  lea     rcx, [rbp+arg_18]
0x18000ddfc  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000de01  lea     rax, qword_18003C1B8
0x18000de08  mov     [rbp+arg_18], rax
0x18000de0c  lock inc cs:qword_18003C1B8
0x18000de14  mov     rcx, [rbp+arg_0]
0x18000de18  xor     eax, eax
0x18000de1a  lock cmpxchg cs:??$factory_cache_entry_v@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, rcx; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>
0x18000de23  jnz     short loc_18000DE40
0x18000de25  mov     [rbp+arg_0], 0
0x18000de2d  lea     rdx, stru_18003C1C0; ListEntry
0x18000de34  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000de3b  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000de40  lea     rdx, ??$factory_cache_entry_v@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UImage@Controls@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Controls::Image,winrt::Windows::Foundation::IActivationFactory>
0x18000de47  mov     rcx, rbx
0x18000de4a  mov     rax, [rdi]
0x18000de4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de52  nop
0x18000de53  lock dec cs:qword_18003C1B8
0x18000de5b  jmp     short loc_18000DE6D
0x18000de5d  lea     rdx, [rbp+arg_0]
0x18000de61  mov     rcx, rbx
0x18000de64  mov     rax, [rdi]
0x18000de67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de6c  nop
0x18000de6d  cmp     [rbp+arg_0], 0
0x18000de72  jz      short loc_18000DE7D
0x18000de74  lea     rcx, [rbp+arg_0]
0x18000de78  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000de7d  mov     rax, rbx
0x18000de80  mov     rbx, [rsp+50h+arg_8]
0x18000de85  mov     rdi, [rsp+50h+arg_10]
0x18000de8a  add     rsp, 50h
0x18000de8e  pop     rbp
0x18000de8f  retn
```
