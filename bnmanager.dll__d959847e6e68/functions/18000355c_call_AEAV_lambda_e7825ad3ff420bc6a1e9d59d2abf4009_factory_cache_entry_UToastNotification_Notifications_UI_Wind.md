# ??$call@AEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@Z

- ea: `0x18000355c`
- end: `0x180003728`
- name: `??$call@AEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@Z`
- size: `460`
- prototype: `signed __int64 *__fastcall(signed __int64, signed __int64 *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800062e0`

## callees

- `0x1800023ad`
- `0x18000355c`
- `0x180004340`
- `0x18000bde4`
- `0x18000c010`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180003589`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180003589`

## pseudocode

```c
signed __int64 *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::call<_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_ &>(
        signed __int64 a1,
        signed __int64 *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h]
  _DWORD *v11; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-10h]
  signed __int64 v14; // [rsp+90h] [rbp+20h] BYREF
  signed __int64 v15; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a1;
  if ( aWindowsUiNotif[42] )
    abort();
  v12[0] = 1;
  v12[1] = 42;
  v13 = L"Windows.UI.Notifications.ToastNotification";
  v11 = v12;
  v15 = 0;
  v9 = 0;
  v10 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v14,
    &v11,
    winrt::impl::guid_v<winrt::Windows::UI::Notifications::IToastNotificationFactory>,
    &v15);
  if ( (int)v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v9);
  v5 = v15;
  v14 = v15;
  if ( !v15
    || (v15 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, signed __int64 *))v5)(
          v5,
          winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v15),
        !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, signed __int64 *))(*(_QWORD *)v5 + 48LL))(v5, **a3, &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_13;
  }
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_1800147C8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>,
          v5,
          0) )
  {
    v5 = 0;
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800147D0);
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, signed __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
                                                                    + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>,
         **a3,
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_1800147C8);
  if ( v5 )
LABEL_13:
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x18000355c  mov     [rsp-18h+arg_8], rbx
0x180003561  mov     [rsp-18h+arg_10], rsi
0x180003566  mov     [rsp-18h+arg_0], rcx
0x18000356b  push    rbp
0x18000356c  push    rdi
0x18000356d  push    r14
0x18000356f  mov     rbp, rsp
0x180003572  sub     rsp, 70h
0x180003576  mov     rsi, r8
0x180003579  mov     rdi, rdx
0x18000357c  xor     r14d, r14d
0x18000357f  cmp     word ptr cs:aWindowsUiNotif+54h, r14w; ""
0x180003587  jz      short loc_180003590
0x180003589  call    cs:__imp_abort
0x180003590  mov     [rbp+var_20], 1
0x180003597  mov     [rbp+var_1C], 2Ah ; '*'
0x18000359e  lea     rax, aWindowsUiNotif; "Windows.UI.Notifications.ToastNotificat"...
0x1800035a5  mov     [rbp+var_10], rax
0x1800035a9  lea     rax, [rbp+var_20]
0x1800035ad  mov     [rbp+var_28], rax
0x1800035b1  mov     [rbp+arg_18], r14
0x1800035b5  mov     [rbp+var_40], r14d
0x1800035b9  xorps   xmm0, xmm0
0x1800035bc  movdqu  [rbp+var_38], xmm0
0x1800035c1  lea     r9, [rbp+arg_18]
0x1800035c5  lea     r8, ??$guid_v@UIToastNotificationFactory@Notifications@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x1800035cc  lea     rdx, [rbp+var_28]
0x1800035d0  lea     rcx, [rbp+arg_0]
0x1800035d4  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x1800035d9  mov     ecx, dword ptr [rbp+arg_0]
0x1800035dc  test    ecx, ecx
0x1800035de  js      loc_180003712
0x1800035e4  mov     rbx, [rbp+arg_18]
0x1800035e8  mov     [rbp+arg_0], rbx
0x1800035ec  test    rbx, rbx
0x1800035ef  jz      loc_1800036B1
0x1800035f5  mov     [rbp+arg_18], r14
0x1800035f9  mov     rax, [rbx]
0x1800035fc  lea     r8, [rbp+arg_18]
0x180003600  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180003607  mov     rcx, rbx
0x18000360a  mov     rax, [rax]
0x18000360d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003612  mov     rax, [rbp+arg_18]
0x180003616  mov     [rbp+arg_18], rax
0x18000361a  test    rax, rax
0x18000361d  jz      loc_1800036B1
0x180003623  lea     rcx, [rbp+arg_18]
0x180003627  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000362c  lea     rax, qword_1800147C8
0x180003633  mov     [rbp+var_48], rax
0x180003637  lock inc cs:qword_1800147C8
0x18000363f  xor     eax, eax
0x180003641  lock cmpxchg cs:??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A, rbx; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x18000364a  jnz     short loc_180003666
0x18000364c  mov     rbx, r14
0x18000364f  mov     [rbp+arg_0], rbx
0x180003653  lea     rdx, stru_1800147D0; ListEntry
0x18000365a  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180003661  call    WINRT_IMPL_InterlockedPushEntrySList
0x180003666  mov     [rbp+arg_18], r14
0x18000366a  mov     rcx, cs:??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x180003671  mov     [rbp+var_40], r14d
0x180003675  xorps   xmm0, xmm0
0x180003678  movdqu  [rbp+var_38], xmm0
0x18000367d  mov     rax, [rcx]
0x180003680  mov     rdx, [rsi]
0x180003683  lea     r8, [rbp+arg_18]
0x180003687  mov     rdx, [rdx]
0x18000368a  mov     rax, [rax+30h]
0x18000368e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003693  test    eax, eax
0x180003695  js      loc_18000371C
0x18000369b  mov     rax, [rbp+arg_18]
0x18000369f  mov     [rdi], rax
0x1800036a2  lock dec cs:qword_1800147C8
0x1800036aa  test    rbx, rbx
0x1800036ad  jz      short loc_1800036EE
0x1800036af  jmp     short loc_1800036E5
0x1800036b1  mov     [rbp+arg_18], r14
0x1800036b5  mov     [rbp+var_40], r14d
0x1800036b9  xorps   xmm0, xmm0
0x1800036bc  movdqu  [rbp+var_38], xmm0
0x1800036c1  mov     rax, [rbx]
0x1800036c4  mov     rdx, [rsi]
0x1800036c7  lea     r8, [rbp+arg_18]
0x1800036cb  mov     rdx, [rdx]
0x1800036ce  mov     rcx, rbx
0x1800036d1  mov     rax, [rax+30h]
0x1800036d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036da  test    eax, eax
0x1800036dc  js      short loc_180003706
0x1800036de  mov     rax, [rbp+arg_18]
0x1800036e2  mov     [rdi], rax
0x1800036e5  lea     rcx, [rbp+arg_0]
0x1800036e9  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800036ee  mov     rax, rdi
0x1800036f1  lea     r11, [rsp+70h+var_s0]
0x1800036f6  mov     rbx, [r11+28h]
0x1800036fa  mov     rsi, [r11+30h]
0x1800036fe  mov     rsp, r11
0x180003701  pop     r14
0x180003703  pop     rdi
0x180003704  pop     rbp
0x180003705  retn
0x180003706  lea     rdx, [rbp+var_40]
0x18000370a  mov     ecx, eax
0x18000370c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180003712  lea     rdx, [rbp+var_40]
0x180003716  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000371c  lea     rdx, [rbp+var_40]
0x180003720  mov     ecx, eax
0x180003722  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
