# ??$call@P6A?AUQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@winrt@@AEBUIQuietHoursSettingsInteropStatics@23456@@Z@?$factory_cache_entry@UQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@winrt@@UIQuietHoursSettingsInteropStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AUQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@2@AEBUIQuietHoursSettingsInteropStatics@45672@@Z@Z

- ea: `0x18002c988`
- end: `0x18002ca9e`
- name: `??$call@P6A?AUQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@winrt@@AEBUIQuietHoursSettingsInteropStatics@23456@@Z@?$factory_cache_entry@UQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@winrt@@UIQuietHoursSettingsInteropStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AUQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@2@AEBUIQuietHoursSettingsInteropStatics@45672@@Z@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d0ec`

## callees

- `0x180005236`
- `0x1800072d8`
- `0x18000dfc0`
- `0x180020388`
- `0x18002c988`
- `0x18002cb08`
- `0x180035010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Internal::UI::Notifications::QuietHoursSettingsInterop,winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::call<winrt::Windows::Internal::UI::Notifications::QuietHoursSettingsInterop (*)(winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Windows.Internal.UI.Notifications.QuietHoursSettingsInterop";
  v6[1] = 59;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v9);
    v9 = &qword_180046C98;
    _InterlockedIncrement64(&qword_180046C98);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::UI::Notifications::QuietHoursSettingsInterop,winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180046CA0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::UI::Notifications::QuietHoursSettingsInterop,winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>);
    _InterlockedDecrement64(&qword_180046C98);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v8);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v8);
  return a2;
}

```

## disassembly

```asm
0x18002c988  mov     [rsp-8+arg_8], rbx
0x18002c98d  mov     [rsp-8+arg_10], rdi
0x18002c992  mov     [rsp-8+arg_0], rcx
0x18002c997  push    rbp
0x18002c998  mov     rbp, rsp
0x18002c99b  sub     rsp, 60h
0x18002c99f  mov     rdi, r8
0x18002c9a2  mov     rbx, rdx
0x18002c9a5  lea     rax, aWindowsInterna; "Windows.Internal.UI.Notifications.Quiet"...
0x18002c9ac  mov     [rbp+var_38], rax
0x18002c9b0  mov     [rbp+var_30], 3Bh ; ';'
0x18002c9b8  lea     rdx, [rbp+var_38]
0x18002c9bc  lea     rcx, [rbp+var_28]
0x18002c9c0  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18002c9c5  lea     rdx, [rbp+var_28]
0x18002c9c9  lea     rcx, [rbp+arg_0]
0x18002c9cd  call    ??$get_activation_factory@UIQuietHoursSettingsInteropStatics@Notifications@UI@Internal@Windows@winrt@@@winrt@@YA?AUIQuietHoursSettingsInteropStatics@Notifications@UI@Internal@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>(winrt::param::hstring const &)
0x18002c9d2  nop
0x18002c9d3  mov     rcx, [rbp+arg_0]
0x18002c9d7  test    rcx, rcx
0x18002c9da  jz      loc_18002CA70
0x18002c9e0  mov     [rbp+arg_18], 0
0x18002c9e8  mov     rax, [rcx]
0x18002c9eb  lea     r8, [rbp+arg_18]
0x18002c9ef  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18002c9f6  mov     rax, [rax]
0x18002c9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9fe  mov     rax, [rbp+arg_18]
0x18002ca02  mov     [rbp+arg_18], rax
0x18002ca06  test    rax, rax
0x18002ca09  jz      short loc_18002CA70
0x18002ca0b  lea     rcx, [rbp+arg_18]
0x18002ca0f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002ca14  lea     rax, qword_180046C98
0x18002ca1b  mov     [rbp+arg_18], rax
0x18002ca1f  lock inc cs:qword_180046C98
0x18002ca27  mov     rcx, [rbp+arg_0]
0x18002ca2b  xor     eax, eax
0x18002ca2d  lock cmpxchg cs:??$factory_cache_entry_v@UQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@winrt@@UIQuietHoursSettingsInteropStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@winrt@@UIQuietHoursSettingsInteropStatics@23456@@12@A, rcx; factory_cache_entry<winrt::Windows::Internal::UI::Notifications::QuietHoursSettingsInterop,winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::UI::Notifications::QuietHoursSettingsInterop,winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::UI::Notifications::QuietHoursSettingsInterop,winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>
0x18002ca36  jnz     short loc_18002CA53
0x18002ca38  mov     [rbp+arg_0], 0
0x18002ca40  lea     rdx, stru_180046CA0; ListEntry
0x18002ca47  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18002ca4e  call    WINRT_IMPL_InterlockedPushEntrySList
0x18002ca53  lea     rdx, ??$factory_cache_entry_v@UQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@winrt@@UIQuietHoursSettingsInteropStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UQuietHoursSettingsInterop@Notifications@UI@Internal@Windows@winrt@@UIQuietHoursSettingsInteropStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Internal::UI::Notifications::QuietHoursSettingsInterop,winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::UI::Notifications::QuietHoursSettingsInterop,winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::UI::Notifications::QuietHoursSettingsInterop,winrt::Windows::Internal::UI::Notifications::IQuietHoursSettingsInteropStatics>
0x18002ca5a  mov     rcx, rbx
0x18002ca5d  mov     rax, [rdi]
0x18002ca60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca65  nop
0x18002ca66  lock dec cs:qword_180046C98
0x18002ca6e  jmp     short loc_18002CA80
0x18002ca70  lea     rdx, [rbp+arg_0]
0x18002ca74  mov     rcx, rbx
0x18002ca77  mov     rax, [rdi]
0x18002ca7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca7f  nop
0x18002ca80  lea     rcx, [rbp+arg_0]
0x18002ca84  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18002ca89  mov     rax, rbx
0x18002ca8c  lea     r11, [rsp+60h+var_s0]
0x18002ca91  mov     rbx, [r11+18h]
0x18002ca95  mov     rdi, [r11+20h]
0x18002ca99  mov     rsp, r11
0x18002ca9c  pop     rbp
0x18002ca9d  retn
```
