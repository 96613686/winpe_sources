# ??$call@AEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@Z

- ea: `0x18000f9d4`
- end: `0x18000fb19`
- name: `??$call@AEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001066c`

## callees

- `0x1800038e9`
- `0x180009c74`
- `0x18000f9d4`
- `0x18000fe58`
- `0x1800109e8`
- `0x180010a38`
- `0x180010e00`
- `0x180012e00`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::call<_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_ &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // rdi
  const wchar_t *v7; // [rsp+28h] [rbp-38h] BYREF
  __int128 v8; // [rsp+30h] [rbp-30h]
  _BYTE v9[32]; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+80h] [rbp+20h] BYREF
  __int64 *v11; // [rsp+98h] [rbp+38h] BYREF

  v10 = a1;
  v7 = L"Windows.UI.Notifications.ToastNotification";
  *(_QWORD *)&v8 = 42;
  winrt::param::hstring::hstring(v9, &v7);
  v11 = 0;
  LODWORD(v7) = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v10,
    v9,
    winrt::impl::guid_v<winrt::Windows::UI::Notifications::IToastNotificationFactory>,
    &v11);
  winrt::check_hresult(&v10, (unsigned int)v10, &v7);
  v5 = v11;
  v10 = v11;
  if ( v11
    && (v11 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v5)(
          v5,
          winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v11),
        v11) )
  {
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v11);
    v11 = &qword_180027A18;
    _InterlockedIncrement64(&qword_180027A18);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>,
            (signed __int64)v5,
            0) )
    {
      v10 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180027A20);
    }
    _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>);
    _InterlockedDecrement64(&qword_180027A18);
  }
  else
  {
    _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(a3, a2, &v10);
  }
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v10);
  return a2;
}

```

## disassembly

```asm
0x18000f9d4  mov     [rsp-18h+arg_8], rbx
0x18000f9d9  mov     [rsp-18h+arg_0], rcx
0x18000f9de  push    rbp
0x18000f9df  push    rsi
0x18000f9e0  push    rdi
0x18000f9e1  mov     rbp, rsp
0x18000f9e4  sub     rsp, 60h
0x18000f9e8  mov     rsi, r8
0x18000f9eb  mov     rbx, rdx
0x18000f9ee  lea     rax, aWindowsUiNotif; "Windows.UI.Notifications.ToastNotificat"...
0x18000f9f5  mov     [rbp+var_38], rax
0x18000f9f9  mov     qword ptr [rbp+var_30], 2Ah ; '*'
0x18000fa01  lea     rdx, [rbp+var_38]
0x18000fa05  lea     rcx, [rbp+var_20]
0x18000fa09  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000fa0e  mov     [rbp+arg_18], 0
0x18000fa16  mov     dword ptr [rbp+var_38], 0
0x18000fa1d  xorps   xmm0, xmm0
0x18000fa20  movdqu  [rbp+var_30], xmm0
0x18000fa25  lea     r9, [rbp+arg_18]
0x18000fa29  lea     r8, ??$guid_v@UIToastNotificationFactory@Notifications@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x18000fa30  lea     rdx, [rbp+var_20]
0x18000fa34  lea     rcx, [rbp+arg_0]
0x18000fa38  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000fa3d  lea     r8, [rbp+var_38]
0x18000fa41  mov     edx, dword ptr [rbp+arg_0]
0x18000fa44  lea     rcx, [rbp+arg_0]
0x18000fa48  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000fa4d  mov     rdi, [rbp+arg_18]
0x18000fa51  mov     [rbp+arg_0], rdi
0x18000fa55  test    rdi, rdi
0x18000fa58  jz      loc_18000FAED
0x18000fa5e  mov     [rbp+arg_18], 0
0x18000fa66  mov     rax, [rdi]
0x18000fa69  lea     r8, [rbp+arg_18]
0x18000fa6d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000fa74  mov     rcx, rdi
0x18000fa77  mov     rax, [rax]
0x18000fa7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa7f  mov     rax, [rbp+arg_18]
0x18000fa83  mov     [rbp+arg_18], rax
0x18000fa87  test    rax, rax
0x18000fa8a  jz      short loc_18000FAED
0x18000fa8c  lea     rcx, [rbp+arg_18]
0x18000fa90  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000fa95  lea     rax, qword_180027A18
0x18000fa9c  mov     [rbp+arg_18], rax
0x18000faa0  lock inc cs:qword_180027A18
0x18000faa8  xor     eax, eax
0x18000faaa  lock cmpxchg cs:??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x18000fab3  jnz     short loc_18000FAD0
0x18000fab5  mov     [rbp+arg_0], 0
0x18000fabd  lea     rdx, stru_180027A20; ListEntry
0x18000fac4  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000facb  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000fad0  lea     r8, ??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x18000fad7  mov     rdx, rbx
0x18000fada  mov     rcx, rsi
0x18000fadd  call    ??R_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@QEBA@AEBUIToastNotificationFactory@Notifications@UI@Windows@winrt@@@Z; _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(winrt::Windows::UI::Notifications::IToastNotificationFactory const &)
0x18000fae2  nop
0x18000fae3  lock dec cs:qword_180027A18
0x18000faeb  jmp     short loc_18000FAFD
0x18000faed  lea     r8, [rbp+arg_0]
0x18000faf1  mov     rdx, rbx
0x18000faf4  mov     rcx, rsi
0x18000faf7  call    ??R_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@QEBA@AEBUIToastNotificationFactory@Notifications@UI@Windows@winrt@@@Z; _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(winrt::Windows::UI::Notifications::IToastNotificationFactory const &)
0x18000fafc  nop
0x18000fafd  lea     rcx, [rbp+arg_0]
0x18000fb01  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x18000fb06  mov     rax, rbx
0x18000fb09  mov     rbx, [rsp+60h+arg_8]
0x18000fb11  add     rsp, 60h
0x18000fb15  pop     rdi
0x18000fb16  pop     rsi
0x18000fb17  pop     rbp
0x18000fb18  retn
```
