# ??$call@P6A?AUBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUBitmapImage@Imaging@Media@Xaml@UI@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z

- ea: `0x18000db2c`
- end: `0x18000dc48`
- name: `??$call@P6A?AUBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUBitmapImage@Imaging@Media@Xaml@UI@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z`
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
- `0x18000db2c`
- `0x18000e204`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
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
  v8 = L"Windows.UI.Xaml.Media.Imaging.BitmapImage";
  v6 = v7;
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v9, &v6);
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v10);
    v10 = &qword_18003C1F8;
    _InterlockedIncrement64(&qword_18003C1F8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18003C200);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_18003C1F8);
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
0x18000db2c  mov     [rsp-8+arg_8], rbx
0x18000db31  mov     [rsp-8+arg_10], rdi
0x18000db36  mov     [rsp-8+arg_0], rcx
0x18000db3b  push    rbp
0x18000db3c  mov     rbp, rsp
0x18000db3f  sub     rsp, 50h
0x18000db43  mov     rdi, r8
0x18000db46  mov     rbx, rdx
0x18000db49  mov     [rbp+var_20], 1
0x18000db50  mov     [rbp+var_1C], 29h ; ')'
0x18000db57  lea     rax, aWindowsUiXamlM_0; "Windows.UI.Xaml.Media.Imaging.BitmapIma"...
0x18000db5e  mov     [rbp+var_10], rax
0x18000db62  lea     rax, [rbp+var_20]
0x18000db66  mov     [rbp+var_28], rax
0x18000db6a  lea     rdx, [rbp+var_28]
0x18000db6e  lea     rcx, [rbp+arg_0]
0x18000db72  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18000db77  nop
0x18000db78  mov     rcx, [rbp+arg_0]
0x18000db7c  test    rcx, rcx
0x18000db7f  jz      loc_18000DC15
0x18000db85  mov     [rbp+arg_18], 0
0x18000db8d  mov     rax, [rcx]
0x18000db90  lea     r8, [rbp+arg_18]
0x18000db94  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000db9b  mov     rax, [rax]
0x18000db9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba3  mov     rax, [rbp+arg_18]
0x18000dba7  mov     [rbp+arg_18], rax
0x18000dbab  test    rax, rax
0x18000dbae  jz      short loc_18000DC15
0x18000dbb0  lea     rcx, [rbp+arg_18]
0x18000dbb4  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000dbb9  lea     rax, qword_18003C1F8
0x18000dbc0  mov     [rbp+arg_18], rax
0x18000dbc4  lock inc cs:qword_18003C1F8
0x18000dbcc  mov     rcx, [rbp+arg_0]
0x18000dbd0  xor     eax, eax
0x18000dbd2  lock cmpxchg cs:??$factory_cache_entry_v@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A, rcx; factory_cache_entry<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>
0x18000dbdb  jnz     short loc_18000DBF8
0x18000dbdd  mov     [rbp+arg_0], 0
0x18000dbe5  lea     rdx, stru_18003C200; ListEntry
0x18000dbec  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000dbf3  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000dbf8  lea     rdx, ??$factory_cache_entry_v@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UBitmapImage@Imaging@Media@Xaml@UI@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A; factory_cache_entry<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Xaml::Media::Imaging::BitmapImage,winrt::Windows::Foundation::IActivationFactory>
0x18000dbff  mov     rcx, rbx
0x18000dc02  mov     rax, [rdi]
0x18000dc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc0a  nop
0x18000dc0b  lock dec cs:qword_18003C1F8
0x18000dc13  jmp     short loc_18000DC25
0x18000dc15  lea     rdx, [rbp+arg_0]
0x18000dc19  mov     rcx, rbx
0x18000dc1c  mov     rax, [rdi]
0x18000dc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc24  nop
0x18000dc25  cmp     [rbp+arg_0], 0
0x18000dc2a  jz      short loc_18000DC35
0x18000dc2c  lea     rcx, [rbp+arg_0]
0x18000dc30  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000dc35  mov     rax, rbx
0x18000dc38  mov     rbx, [rsp+50h+arg_8]
0x18000dc3d  mov     rdi, [rsp+50h+arg_10]
0x18000dc42  add     rsp, 50h
0x18000dc46  pop     rbp
0x18000dc47  retn
```
