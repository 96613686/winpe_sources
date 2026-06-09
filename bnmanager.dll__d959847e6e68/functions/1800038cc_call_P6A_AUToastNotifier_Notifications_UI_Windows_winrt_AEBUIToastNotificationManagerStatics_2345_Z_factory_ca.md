# ??$call@P6A?AUToastNotifier@Notifications@UI@Windows@winrt@@AEBUIToastNotificationManagerStatics@2345@@Z@?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUToastNotifier@Notifications@UI@Windows@2@AEBUIToastNotificationManagerStatics@4562@@Z@Z

- ea: `0x1800038cc`
- end: `0x180003a20`
- name: `??$call@P6A?AUToastNotifier@Notifications@UI@Windows@winrt@@AEBUIToastNotificationManagerStatics@2345@@Z@?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUToastNotifier@Notifications@UI@Windows@2@AEBUIToastNotificationManagerStatics@4562@@Z@Z`
- size: `340`
- prototype: `__int64 __fastcall(__int64 *, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800062e0`

## callees

- `0x1800023ad`
- `0x1800038cc`
- `0x180004340`
- `0x18000bde4`
- `0x18000c010`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800038f1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800038f1`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::call<winrt::Windows::UI::Notifications::ToastNotifier (*)(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics const &)>(
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
  if ( aWindowsUiNotif_0[49] )
    abort();
  v10[0] = 1;
  v10[1] = 49;
  v11 = L"Windows.UI.Notifications.ToastNotificationManager";
  v9 = v10;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    winrt::impl::guid_v<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>,
    &v6);
  if ( (int)v12 < 0 )
    winrt::throw_hresult((unsigned int)v12, &v7);
  v13 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v6;
  if ( v6 && (v12 = 0, (**v6)(v6, winrt::impl::guid_v<winrt::impl::IAgileObject>, &v12), v12) )
  {
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v12);
    v12 = &qword_1800147A8;
    _InterlockedIncrement64(&qword_1800147A8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>,
            (signed __int64)v13,
            0) )
    {
      v13 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800147B0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>);
    _InterlockedDecrement64(&qword_1800147A8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v13);
  }
  if ( v13 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v13);
  return a2;
}

```

## disassembly

```asm
0x1800038cc  mov     [rsp-18h+arg_8], rbx
0x1800038d1  mov     [rsp-18h+arg_0], rcx
0x1800038d6  push    rbp
0x1800038d7  push    rsi
0x1800038d8  push    rdi
0x1800038d9  mov     rbp, rsp
0x1800038dc  sub     rsp, 70h
0x1800038e0  mov     rdi, r8
0x1800038e3  mov     rbx, rdx
0x1800038e6  xor     esi, esi
0x1800038e8  cmp     word ptr cs:aWindowsUiNotif_0+62h, si; ""
0x1800038ef  jz      short loc_1800038F8
0x1800038f1  call    cs:__imp_abort
0x1800038f8  mov     [rbp+var_20], 1
0x1800038ff  mov     [rbp+var_1C], 31h ; '1'
0x180003906  lea     rax, aWindowsUiNotif_0; "Windows.UI.Notifications.ToastNotificat"...
0x18000390d  mov     [rbp+var_10], rax
0x180003911  lea     rax, [rbp+var_20]
0x180003915  mov     [rbp+var_28], rax
0x180003919  mov     [rbp+var_48], rsi
0x18000391d  mov     [rbp+var_40], esi
0x180003920  xorps   xmm0, xmm0
0x180003923  movdqu  [rbp+var_38], xmm0
0x180003928  lea     r9, [rbp+var_48]
0x18000392c  lea     r8, ??$guid_v@UIToastNotificationManagerStatics@Notifications@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>
0x180003933  lea     rdx, [rbp+var_28]
0x180003937  lea     rcx, [rbp+arg_0]
0x18000393b  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180003940  mov     ecx, dword ptr [rbp+arg_0]
0x180003943  test    ecx, ecx
0x180003945  js      loc_180003A16
0x18000394b  mov     rcx, [rbp+var_48]
0x18000394f  mov     [rbp+arg_18], rcx
0x180003953  test    rcx, rcx
0x180003956  jz      loc_1800039E4
0x18000395c  mov     [rbp+arg_0], rsi
0x180003960  mov     rax, [rcx]
0x180003963  lea     r8, [rbp+arg_0]
0x180003967  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000396e  mov     rax, [rax]
0x180003971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003976  mov     rax, [rbp+arg_0]
0x18000397a  mov     [rbp+arg_0], rax
0x18000397e  test    rax, rax
0x180003981  jz      short loc_1800039E4
0x180003983  lea     rcx, [rbp+arg_0]
0x180003987  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000398c  lea     rax, qword_1800147A8
0x180003993  mov     [rbp+arg_0], rax
0x180003997  lock inc cs:qword_1800147A8
0x18000399f  mov     rcx, [rbp+arg_18]
0x1800039a3  xor     eax, eax
0x1800039a5  lock cmpxchg cs:??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@12@A, rcx; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>
0x1800039ae  jnz     short loc_1800039C7
0x1800039b0  mov     [rbp+arg_18], rsi
0x1800039b4  lea     rdx, stru_1800147B0; ListEntry
0x1800039bb  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800039c2  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800039c7  lea     rdx, ??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>
0x1800039ce  mov     rcx, rbx
0x1800039d1  mov     rax, [rdi]
0x1800039d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d9  nop
0x1800039da  lock dec cs:qword_1800147A8
0x1800039e2  jmp     short loc_1800039F4
0x1800039e4  lea     rdx, [rbp+arg_18]
0x1800039e8  mov     rcx, rbx
0x1800039eb  mov     rax, [rdi]
0x1800039ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f3  nop
0x1800039f4  cmp     [rbp+arg_18], rsi
0x1800039f8  jz      short loc_180003A03
0x1800039fa  lea     rcx, [rbp+arg_18]
0x1800039fe  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180003a03  mov     rax, rbx
0x180003a06  mov     rbx, [rsp+70h+arg_8]
0x180003a0e  add     rsp, 70h
0x180003a12  pop     rdi
0x180003a13  pop     rsi
0x180003a14  pop     rbp
0x180003a15  retn
0x180003a16  lea     rdx, [rbp+var_40]
0x180003a1a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
