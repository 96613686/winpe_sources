# ??$call@AEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@Z

- ea: `0x180010e20`
- end: `0x180010f30`
- name: `??$call@AEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180011464`

## callees

- `0x180003495`
- `0x18000750c`
- `0x18000a2b0`
- `0x18000a360`
- `0x180010e20`
- `0x180010f38`
- `0x18001192c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::call<_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        __int64 a3)
{
  signed __int64 v5; // rdi
  _QWORD v7[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+80h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+98h] [rbp+38h] BYREF

  v9 = a1;
  v7[0] = L"Windows.UI.Notifications.ToastNotification";
  v7[1] = 42;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::UI::Notifications::IToastNotificationFactory>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_1800227F8;
    _InterlockedIncrement64(&qword_1800227F8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180022800);
    }
    _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>);
    _InterlockedDecrement64(&qword_1800227F8);
  }
  else
  {
    _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(a3, a2, &v9);
  }
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v9);
  return a2;
}

```

## disassembly

```asm
0x180010e20  mov     [rsp-18h+arg_8], rbx
0x180010e25  mov     [rsp-18h+arg_0], rcx
0x180010e2a  push    rbp
0x180010e2b  push    rsi
0x180010e2c  push    rdi
0x180010e2d  mov     rbp, rsp
0x180010e30  sub     rsp, 60h
0x180010e34  mov     rsi, r8
0x180010e37  mov     rbx, rdx
0x180010e3a  lea     rax, aWindowsUiNotif; "Windows.UI.Notifications.ToastNotificat"...
0x180010e41  mov     [rbp+var_38], rax
0x180010e45  mov     [rbp+var_30], 2Ah ; '*'
0x180010e4d  lea     rdx, [rbp+var_38]
0x180010e51  lea     rcx, [rbp+var_28]
0x180010e55  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x180010e5a  lea     rdx, [rbp+var_28]
0x180010e5e  lea     rcx, [rbp+arg_0]
0x180010e62  call    ??$get_activation_factory@UIToastNotificationFactory@Notifications@UI@Windows@winrt@@@winrt@@YA?AUIToastNotificationFactory@Notifications@UI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::UI::Notifications::IToastNotificationFactory>(winrt::param::hstring const &)
0x180010e67  nop
0x180010e68  mov     rdi, [rbp+arg_0]
0x180010e6c  test    rdi, rdi
0x180010e6f  jz      loc_180010F04
0x180010e75  mov     [rbp+arg_18], 0
0x180010e7d  mov     rax, [rdi]
0x180010e80  lea     r8, [rbp+arg_18]
0x180010e84  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180010e8b  mov     rcx, rdi
0x180010e8e  mov     rax, [rax]
0x180010e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e96  mov     rax, [rbp+arg_18]
0x180010e9a  mov     [rbp+arg_18], rax
0x180010e9e  test    rax, rax
0x180010ea1  jz      short loc_180010F04
0x180010ea3  lea     rcx, [rbp+arg_18]
0x180010ea7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010eac  lea     rax, qword_1800227F8
0x180010eb3  mov     [rbp+arg_18], rax
0x180010eb7  lock inc cs:qword_1800227F8
0x180010ebf  xor     eax, eax
0x180010ec1  lock cmpxchg cs:??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x180010eca  jnz     short loc_180010EE7
0x180010ecc  mov     [rbp+arg_0], 0
0x180010ed4  lea     rdx, stru_180022800; ListEntry
0x180010edb  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180010ee2  call    WINRT_IMPL_InterlockedPushEntrySList
0x180010ee7  lea     r8, ??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x180010eee  mov     rdx, rbx
0x180010ef1  mov     rcx, rsi
0x180010ef4  call    ??R_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@QEBA@AEBUIToastNotificationFactory@Notifications@UI@Windows@winrt@@@Z; _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(winrt::Windows::UI::Notifications::IToastNotificationFactory const &)
0x180010ef9  nop
0x180010efa  lock dec cs:qword_1800227F8
0x180010f02  jmp     short loc_180010F14
0x180010f04  lea     r8, [rbp+arg_0]
0x180010f08  mov     rdx, rbx
0x180010f0b  mov     rcx, rsi
0x180010f0e  call    ??R_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@QEBA@AEBUIToastNotificationFactory@Notifications@UI@Windows@winrt@@@Z; _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(winrt::Windows::UI::Notifications::IToastNotificationFactory const &)
0x180010f13  nop
0x180010f14  lea     rcx, [rbp+arg_0]; this
0x180010f18  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x180010f1d  mov     rax, rbx
0x180010f20  mov     rbx, [rsp+60h+arg_8]
0x180010f28  add     rsp, 60h
0x180010f2c  pop     rdi
0x180010f2d  pop     rsi
0x180010f2e  pop     rbp
0x180010f2f  retn
```
