# ??$call@P6A?AUHapticFeedbackSettings@Input@Devices@Internal@Windows@winrt@@AEBUIDeviceSettingsStatics@23456@@Z@?$factory_cache_entry@UDeviceSettings@Input@Devices@Internal@Windows@winrt@@UIDeviceSettingsStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AUHapticFeedbackSettings@Input@Devices@Internal@Windows@2@AEBUIDeviceSettingsStatics@45672@@Z@Z

- ea: `0x18001296c`
- end: `0x180012ab5`
- name: `??$call@P6A?AUHapticFeedbackSettings@Input@Devices@Internal@Windows@winrt@@AEBUIDeviceSettingsStatics@23456@@Z@?$factory_cache_entry@UDeviceSettings@Input@Devices@Internal@Windows@winrt@@UIDeviceSettingsStatics@23456@@impl@winrt@@QEAA?A_P$$QEAP6A?AUHapticFeedbackSettings@Input@Devices@Internal@Windows@2@AEBUIDeviceSettingsStatics@45672@@Z@Z`
- size: `329`
- prototype: `__int64 __fastcall(__int64 *, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001feb0`

## callees

- `0x1800043b9`
- `0x18001296c`
- `0x180014d2c`
- `0x18001b738`
- `0x180022f90`
- `0x1800260f8`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012991`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012991`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Internal::Devices::Input::DeviceSettings,winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics>::call<winrt::Windows::Internal::Devices::Input::HapticFeedbackSettings (*)(winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics const &)>(
        __int64 *a1,
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 **); // [rsp+28h] [rbp-48h] BYREF
  int v7; // [rsp+30h] [rbp-40h] BYREF
  __int128 v8; // [rsp+38h] [rbp-38h]
  _DWORD *v9; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v10[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v11; // [rsp+60h] [rbp-10h]
  __int64 *v12; // [rsp+90h] [rbp+20h] BYREF
  void (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // [rsp+A8h] [rbp+38h] BYREF

  v12 = a1;
  if ( aWindowsInterna[45] )
    abort();
  v10[0] = 1;
  v10[1] = 45;
  v11 = L"Windows.Internal.Devices.Input.DeviceSettings";
  v9 = v10;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    winrt::impl::guid_v<winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics>,
    &v6);
  winrt::check_hresult(&v12, (unsigned int)v12, &v7);
  v13 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v6;
  if ( v6 && (v12 = 0, (**v6)(v6, winrt::impl::guid_v<winrt::impl::IAgileObject>, &v12), v12) )
  {
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v12);
    v12 = &qword_1800438F8;
    _InterlockedIncrement64(&qword_1800438F8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Devices::Input::DeviceSettings,winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics>,
            (signed __int64)v13,
            0) )
    {
      v13 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Devices::Input::DeviceSettings,winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics>);
    _InterlockedDecrement64(&qword_1800438F8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v13);
  }
  winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics::~IDeviceSettingsStatics((winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics *)&v13);
  return a2;
}

```

## disassembly

```asm
0x18001296c  mov     [rsp-18h+arg_8], rbx
0x180012971  mov     [rsp-18h+arg_0], rcx
0x180012976  push    rbp
0x180012977  push    rsi
0x180012978  push    rdi
0x180012979  mov     rbp, rsp
0x18001297c  sub     rsp, 70h
0x180012980  mov     rdi, r8
0x180012983  mov     rbx, rdx
0x180012986  xor     esi, esi
0x180012988  cmp     word ptr cs:aWindowsInterna+5Ah, si; ""
0x18001298f  jz      short loc_180012998
0x180012991  call    cs:__imp_abort
0x180012998  mov     [rbp+var_20], 1
0x18001299f  mov     [rbp+var_1C], 2Dh ; '-'
0x1800129a6  lea     rax, aWindowsInterna; "Windows.Internal.Devices.Input.DeviceSe"...
0x1800129ad  mov     [rbp+var_10], rax
0x1800129b1  lea     rax, [rbp+var_20]
0x1800129b5  mov     [rbp+var_28], rax
0x1800129b9  mov     [rbp+var_48], rsi
0x1800129bd  mov     [rbp+var_40], esi
0x1800129c0  xorps   xmm0, xmm0
0x1800129c3  movdqu  [rbp+var_38], xmm0
0x1800129c8  lea     r9, [rbp+var_48]
0x1800129cc  lea     r8, ??$guid_v@UIDeviceSettingsStatics@Input@Devices@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics>
0x1800129d3  lea     rdx, [rbp+var_28]
0x1800129d7  lea     rcx, [rbp+arg_0]
0x1800129db  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x1800129e0  lea     r8, [rbp+var_40]
0x1800129e4  mov     edx, dword ptr [rbp+arg_0]
0x1800129e7  lea     rcx, [rbp+arg_0]
0x1800129eb  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800129f0  mov     rcx, [rbp+var_48]
0x1800129f4  mov     [rbp+arg_18], rcx
0x1800129f8  test    rcx, rcx
0x1800129fb  jz      loc_180012A89
0x180012a01  mov     [rbp+arg_0], rsi
0x180012a05  mov     rax, [rcx]
0x180012a08  lea     r8, [rbp+arg_0]
0x180012a0c  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180012a13  mov     rax, [rax]
0x180012a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a1b  mov     rax, [rbp+arg_0]
0x180012a1f  mov     [rbp+arg_0], rax
0x180012a23  test    rax, rax
0x180012a26  jz      short loc_180012A89
0x180012a28  lea     rcx, [rbp+arg_0]
0x180012a2c  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180012a31  lea     rax, qword_1800438F8
0x180012a38  mov     [rbp+arg_0], rax
0x180012a3c  lock inc cs:qword_1800438F8
0x180012a44  mov     rcx, [rbp+arg_18]
0x180012a48  xor     eax, eax
0x180012a4a  lock cmpxchg cs:??$factory_cache_entry_v@UDeviceSettings@Input@Devices@Internal@Windows@winrt@@UIDeviceSettingsStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UDeviceSettings@Input@Devices@Internal@Windows@winrt@@UIDeviceSettingsStatics@23456@@12@A, rcx; factory_cache_entry<winrt::Windows::Internal::Devices::Input::DeviceSettings,winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::Devices::Input::DeviceSettings,winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Devices::Input::DeviceSettings,winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics>
0x180012a53  jnz     short loc_180012A6C
0x180012a55  mov     [rbp+arg_18], rsi
0x180012a59  lea     rdx, ListEntry; ListEntry
0x180012a60  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180012a67  call    WINRT_IMPL_InterlockedPushEntrySList
0x180012a6c  lea     rdx, ??$factory_cache_entry_v@UDeviceSettings@Input@Devices@Internal@Windows@winrt@@UIDeviceSettingsStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UDeviceSettings@Input@Devices@Internal@Windows@winrt@@UIDeviceSettingsStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Internal::Devices::Input::DeviceSettings,winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::Devices::Input::DeviceSettings,winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Devices::Input::DeviceSettings,winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics>
0x180012a73  mov     rcx, rbx
0x180012a76  mov     rax, [rdi]
0x180012a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a7e  nop
0x180012a7f  lock dec cs:qword_1800438F8
0x180012a87  jmp     short loc_180012A99
0x180012a89  lea     rdx, [rbp+arg_18]
0x180012a8d  mov     rcx, rbx
0x180012a90  mov     rax, [rdi]
0x180012a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a98  nop
0x180012a99  lea     rcx, [rbp+arg_18]; this
0x180012a9d  call    ??1IDeviceSettingsStatics@Input@Devices@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Devices::Input::IDeviceSettingsStatics::~IDeviceSettingsStatics(void)
0x180012aa2  mov     rax, rbx
0x180012aa5  mov     rbx, [rsp+70h+arg_8]
0x180012aad  add     rsp, 70h
0x180012ab1  pop     rdi
0x180012ab2  pop     rsi
0x180012ab3  pop     rbp
0x180012ab4  retn
```
