# ??$call@P6A?AUToastNotificationManagerForUser@Notifications@UI@Windows@winrt@@AEBUIToastNotificationManagerStatics5@2345@@Z@?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUToastNotificationManagerForUser@Notifications@UI@Windows@2@AEBUIToastNotificationManagerStatics5@4562@@Z@Z

- ea: `0x180015920`
- end: `0x180015a36`
- name: `??$call@P6A?AUToastNotificationManagerForUser@Notifications@UI@Windows@winrt@@AEBUIToastNotificationManagerStatics5@2345@@Z@?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUToastNotificationManagerForUser@Notifications@UI@Windows@2@AEBUIToastNotificationManagerStatics5@4562@@Z@Z`
- size: `278`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180015d18`

## callees

- `0x180003495`
- `0x18000750c`
- `0x18000a2b0`
- `0x18000a360`
- `0x180015920`
- `0x180015a3c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::call<winrt::Windows::UI::Notifications::ToastNotificationManagerForUser (*)(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5 const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Windows.UI.Notifications.ToastNotificationManager";
  v6[1] = 49;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
    v9 = &qword_180022818;
    _InterlockedIncrement64(&qword_180022818);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180022820);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>);
    _InterlockedDecrement64(&qword_180022818);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v8);
  }
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v8);
  return a2;
}

```

## disassembly

```asm
0x180015920  mov     [rsp-8+arg_8], rbx
0x180015925  mov     [rsp-8+arg_10], rdi
0x18001592a  mov     [rsp-8+arg_0], rcx
0x18001592f  push    rbp
0x180015930  mov     rbp, rsp
0x180015933  sub     rsp, 60h
0x180015937  mov     rdi, r8
0x18001593a  mov     rbx, rdx
0x18001593d  lea     rax, aWindowsUiNotif_0; "Windows.UI.Notifications.ToastNotificat"...
0x180015944  mov     [rbp+var_38], rax
0x180015948  mov     [rbp+var_30], 31h ; '1'
0x180015950  lea     rdx, [rbp+var_38]
0x180015954  lea     rcx, [rbp+var_28]
0x180015958  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001595d  lea     rdx, [rbp+var_28]
0x180015961  lea     rcx, [rbp+arg_0]
0x180015965  call    ??$get_activation_factory@UIToastNotificationManagerStatics5@Notifications@UI@Windows@winrt@@@winrt@@YA?AUIToastNotificationManagerStatics5@Notifications@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>(winrt::param::hstring const &)
0x18001596a  nop
0x18001596b  mov     rcx, [rbp+arg_0]
0x18001596f  test    rcx, rcx
0x180015972  jz      loc_180015A08
0x180015978  mov     [rbp+arg_18], 0
0x180015980  mov     rax, [rcx]
0x180015983  lea     r8, [rbp+arg_18]
0x180015987  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001598e  mov     rax, [rax]
0x180015991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015996  mov     rax, [rbp+arg_18]
0x18001599a  mov     [rbp+arg_18], rax
0x18001599e  test    rax, rax
0x1800159a1  jz      short loc_180015A08
0x1800159a3  lea     rcx, [rbp+arg_18]
0x1800159a7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800159ac  lea     rax, qword_180022818
0x1800159b3  mov     [rbp+arg_18], rax
0x1800159b7  lock inc cs:qword_180022818
0x1800159bf  mov     rcx, [rbp+arg_0]
0x1800159c3  xor     eax, eax
0x1800159c5  lock cmpxchg cs:??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@12@A, rcx; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>
0x1800159ce  jnz     short loc_1800159EB
0x1800159d0  mov     [rbp+arg_0], 0
0x1800159d8  lea     rdx, stru_180022820; ListEntry
0x1800159df  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800159e6  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800159eb  lea     rdx, ??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics5@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics5>
0x1800159f2  mov     rcx, rbx
0x1800159f5  mov     rax, [rdi]
0x1800159f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159fd  nop
0x1800159fe  lock dec cs:qword_180022818
0x180015a06  jmp     short loc_180015A18
0x180015a08  lea     rdx, [rbp+arg_0]
0x180015a0c  mov     rcx, rbx
0x180015a0f  mov     rax, [rdi]
0x180015a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a17  nop
0x180015a18  lea     rcx, [rbp+arg_0]; this
0x180015a1c  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180015a21  mov     rax, rbx
0x180015a24  lea     r11, [rsp+60h+var_s0]
0x180015a29  mov     rbx, [r11+18h]
0x180015a2d  mov     rdi, [r11+20h]
0x180015a31  mov     rsp, r11
0x180015a34  pop     rbp
0x180015a35  retn
```
