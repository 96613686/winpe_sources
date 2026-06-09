# ??$call@AEAV_lambda_9963adada1db90a1e471b6d32fa55098_@@@?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_9963adada1db90a1e471b6d32fa55098_@@@Z

- ea: `0x18000f888`
- end: `0x18000f9cd`
- name: `??$call@AEAV_lambda_9963adada1db90a1e471b6d32fa55098_@@@?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_9963adada1db90a1e471b6d32fa55098_@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180010f20`

## callees

- `0x1800038e9`
- `0x180009c74`
- `0x18000f888`
- `0x18000fe58`
- `0x1800109e8`
- `0x180010a38`
- `0x180010d4c`
- `0x180012e00`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::call<_lambda_9963adada1db90a1e471b6d32fa55098_ &>(
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
  v7 = L"Windows.UI.Notifications.ToastNotificationManager";
  *(_QWORD *)&v8 = 49;
  winrt::param::hstring::hstring(v9, &v7);
  v11 = 0;
  LODWORD(v7) = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v10,
    v9,
    winrt::impl::guid_v<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>,
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
    v11 = &qword_180027A38;
    _InterlockedIncrement64(&qword_180027A38);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>,
            (signed __int64)v5,
            0) )
    {
      v10 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180027A40);
    }
    _lambda_9963adada1db90a1e471b6d32fa55098_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>);
    _InterlockedDecrement64(&qword_180027A38);
  }
  else
  {
    _lambda_9963adada1db90a1e471b6d32fa55098_::operator()(a3, a2, &v10);
  }
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v10);
  return a2;
}

```

## disassembly

```asm
0x18000f888  mov     [rsp-18h+arg_8], rbx
0x18000f88d  mov     [rsp-18h+arg_0], rcx
0x18000f892  push    rbp
0x18000f893  push    rsi
0x18000f894  push    rdi
0x18000f895  mov     rbp, rsp
0x18000f898  sub     rsp, 60h
0x18000f89c  mov     rsi, r8
0x18000f89f  mov     rbx, rdx
0x18000f8a2  lea     rax, aWindowsUiNotif_0; "Windows.UI.Notifications.ToastNotificat"...
0x18000f8a9  mov     [rbp+var_38], rax
0x18000f8ad  mov     qword ptr [rbp+var_30], 31h ; '1'
0x18000f8b5  lea     rdx, [rbp+var_38]
0x18000f8b9  lea     rcx, [rbp+var_20]
0x18000f8bd  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18000f8c2  mov     [rbp+arg_18], 0
0x18000f8ca  mov     dword ptr [rbp+var_38], 0
0x18000f8d1  xorps   xmm0, xmm0
0x18000f8d4  movdqu  [rbp+var_30], xmm0
0x18000f8d9  lea     r9, [rbp+arg_18]
0x18000f8dd  lea     r8, ??$guid_v@UIToastNotificationManagerStatics@Notifications@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>
0x18000f8e4  lea     rdx, [rbp+var_20]
0x18000f8e8  lea     rcx, [rbp+arg_0]
0x18000f8ec  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000f8f1  lea     r8, [rbp+var_38]
0x18000f8f5  mov     edx, dword ptr [rbp+arg_0]
0x18000f8f8  lea     rcx, [rbp+arg_0]
0x18000f8fc  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000f901  mov     rdi, [rbp+arg_18]
0x18000f905  mov     [rbp+arg_0], rdi
0x18000f909  test    rdi, rdi
0x18000f90c  jz      loc_18000F9A1
0x18000f912  mov     [rbp+arg_18], 0
0x18000f91a  mov     rax, [rdi]
0x18000f91d  lea     r8, [rbp+arg_18]
0x18000f921  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000f928  mov     rcx, rdi
0x18000f92b  mov     rax, [rax]
0x18000f92e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f933  mov     rax, [rbp+arg_18]
0x18000f937  mov     [rbp+arg_18], rax
0x18000f93b  test    rax, rax
0x18000f93e  jz      short loc_18000F9A1
0x18000f940  lea     rcx, [rbp+arg_18]
0x18000f944  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000f949  lea     rax, qword_180027A38
0x18000f950  mov     [rbp+arg_18], rax
0x18000f954  lock inc cs:qword_180027A38
0x18000f95c  xor     eax, eax
0x18000f95e  lock cmpxchg cs:??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>
0x18000f967  jnz     short loc_18000F984
0x18000f969  mov     [rbp+arg_0], 0
0x18000f971  lea     rdx, stru_180027A40; ListEntry
0x18000f978  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000f97f  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000f984  lea     r8, ??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>
0x18000f98b  mov     rdx, rbx
0x18000f98e  mov     rcx, rsi
0x18000f991  call    ??R_lambda_9963adada1db90a1e471b6d32fa55098_@@QEBA@AEBUIToastNotificationManagerStatics@Notifications@UI@Windows@winrt@@@Z; _lambda_9963adada1db90a1e471b6d32fa55098_::operator()(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics const &)
0x18000f996  nop
0x18000f997  lock dec cs:qword_180027A38
0x18000f99f  jmp     short loc_18000F9B1
0x18000f9a1  lea     r8, [rbp+arg_0]
0x18000f9a5  mov     rdx, rbx
0x18000f9a8  mov     rcx, rsi
0x18000f9ab  call    ??R_lambda_9963adada1db90a1e471b6d32fa55098_@@QEBA@AEBUIToastNotificationManagerStatics@Notifications@UI@Windows@winrt@@@Z; _lambda_9963adada1db90a1e471b6d32fa55098_::operator()(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics const &)
0x18000f9b0  nop
0x18000f9b1  lea     rcx, [rbp+arg_0]
0x18000f9b5  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x18000f9ba  mov     rax, rbx
0x18000f9bd  mov     rbx, [rsp+60h+arg_8]
0x18000f9c5  add     rsp, 60h
0x18000f9c9  pop     rdi
0x18000f9ca  pop     rsi
0x18000f9cb  pop     rbp
0x18000f9cc  retn
```
