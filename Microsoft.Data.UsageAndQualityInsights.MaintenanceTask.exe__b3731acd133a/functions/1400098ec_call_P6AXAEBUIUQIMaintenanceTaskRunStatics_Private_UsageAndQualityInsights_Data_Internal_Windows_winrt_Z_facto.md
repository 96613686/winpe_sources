# ??$call@P6AXAEBUIUQIMaintenanceTaskRunStatics@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@@Z@?$factory_cache_entry@UUQIMaintenanceTaskRun@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UIUQIMaintenanceTaskRunStatics@234567@@impl@winrt@@QEAA?A_P$$QEAP6AXAEBUIUQIMaintenanceTaskRunStatics@Private@UsageAndQualityInsights@Data@Internal@Windows@2@@Z@Z

- ea: `0x1400098ec`
- end: `0x140009a37`
- name: `??$call@P6AXAEBUIUQIMaintenanceTaskRunStatics@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@@Z@?$factory_cache_entry@UUQIMaintenanceTaskRun@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UIUQIMaintenanceTaskRunStatics@234567@@impl@winrt@@QEAA?A_P$$QEAP6AXAEBUIUQIMaintenanceTaskRunStatics@Private@UsageAndQualityInsights@Data@Internal@Windows@2@@Z@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64 *, __int64 (__fastcall **)(__int64 *))`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000b410`

## callees

- `0x140002318`
- `0x1400098ec`
- `0x140009a40`
- `0x14000b0a8`
- `0x14000b3f0`
- `0x14000c010`

## string_xrefs

- `0x14000990f`: `Windows.Internal.Data.UsageAndQualityInsights.Private.UQIMaintenanceTaskRun`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics>::call<void (*)(winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics const &)>(
        __int64 *a1,
        __int64 (__fastcall **a2)(__int64 *))
{
  __int64 result; // rax
  int v4; // [rsp+20h] [rbp-40h] BYREF
  _DWORD *v5; // [rsp+38h] [rbp-28h] BYREF
  _DWORD v6[4]; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v7; // [rsp+50h] [rbp-10h]
  __int64 *v8; // [rsp+70h] [rbp+10h] BYREF
  void (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // [rsp+80h] [rbp+20h] BYREF
  void (__fastcall ***v10)(_QWORD, __int64 *, __int64 **); // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = 1;
  v6[1] = 75;
  v7 = L"Windows.Internal.Data.UsageAndQualityInsights.Private.UQIMaintenanceTaskRun";
  v5 = v6;
  v10 = 0;
  ((void (__fastcall *)(__int64 **, _DWORD **, __int64 *, void (__fastcall ****)(_QWORD, __int64 *, __int64 **), int, const char *, _QWORD))winrt::impl::get_runtime_activation_factory_impl<0>)(
    &v8,
    &v5,
    winrt::impl::guid_v<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics>,
    &v10,
    6172,
    "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/base.h",
    0);
  if ( (int)v8 < 0 )
    winrt::throw_hresult((unsigned int)v8, &v4);
  v9 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v10;
  if ( v10 && (v8 = 0, (**v10)(v10, winrt::impl::guid_v<winrt::impl::IAgileObject>, &v8), v8) )
  {
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v8);
    v8 = &qword_140011968;
    _InterlockedIncrement64(&qword_140011968);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics>,
            (signed __int64)v9,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    result = (*a2)(&winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics>);
    _InterlockedDecrement64(&qword_140011968);
  }
  else
  {
    result = (*a2)((__int64 *)&v9);
  }
  if ( v9 )
    return winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v9);
  return result;
}

```

## disassembly

```asm
0x1400098ec  mov     [rsp-8+arg_8], rbx
0x1400098f1  mov     [rsp-8+arg_0], rcx
0x1400098f6  push    rbp
0x1400098f7  mov     rbp, rsp
0x1400098fa  sub     rsp, 60h
0x1400098fe  mov     rbx, rdx
0x140009901  mov     [rbp+var_20], 1
0x140009908  mov     [rbp+var_1C], 4Bh ; 'K'
0x14000990f  lea     rax, aWindowsInterna; "Windows.Internal.Data.UsageAndQualityIn"...
0x140009916  mov     [rbp+var_10], rax
0x14000991a  lea     rax, [rbp+var_20]
0x14000991e  mov     [rbp+var_28], rax
0x140009922  mov     [rbp+arg_18], 0
0x14000992a  mov     [rbp+var_40], 181Ch
0x140009931  lea     rax, aOnecoreuapInte; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x140009938  mov     [rbp+var_38], rax
0x14000993c  mov     [rbp+var_30], 0
0x140009944  lea     r9, [rbp+arg_18]
0x140009948  lea     r8, ??$guid_v@UIUQIMaintenanceTaskRunStatics@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics>
0x14000994f  lea     rdx, [rbp+var_28]
0x140009953  lea     rcx, [rbp+arg_0]
0x140009957  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x14000995c  mov     ecx, dword ptr [rbp+arg_0]
0x14000995f  test    ecx, ecx
0x140009961  js      loc_140009A2D
0x140009967  mov     rcx, [rbp+arg_18]
0x14000996b  mov     [rbp+arg_10], rcx
0x14000996f  test    rcx, rcx
0x140009972  jz      loc_140009A05
0x140009978  mov     [rbp+arg_0], 0
0x140009980  mov     rax, [rcx]
0x140009983  lea     r8, [rbp+arg_0]
0x140009987  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x14000998e  mov     rax, [rax]
0x140009991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009996  mov     rax, [rbp+arg_0]
0x14000999a  mov     [rbp+arg_0], rax
0x14000999e  test    rax, rax
0x1400099a1  jz      short loc_140009A05
0x1400099a3  lea     rcx, [rbp+arg_0]
0x1400099a7  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1400099ac  lea     rax, qword_140011968
0x1400099b3  mov     [rbp+arg_0], rax
0x1400099b7  lock inc cs:qword_140011968
0x1400099bf  mov     rcx, [rbp+arg_10]
0x1400099c3  xor     eax, eax
0x1400099c5  lock cmpxchg cs:??$factory_cache_entry_v@UUQIMaintenanceTaskRun@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UIUQIMaintenanceTaskRunStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UUQIMaintenanceTaskRun@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UIUQIMaintenanceTaskRunStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics>
0x1400099ce  jnz     short loc_1400099EB
0x1400099d0  mov     [rbp+arg_10], 0
0x1400099d8  lea     rdx, ListEntry; ListEntry
0x1400099df  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1400099e6  call    WINRT_IMPL_InterlockedPushEntrySList
0x1400099eb  lea     rcx, ??$factory_cache_entry_v@UUQIMaintenanceTaskRun@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UIUQIMaintenanceTaskRunStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UUQIMaintenanceTaskRun@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UIUQIMaintenanceTaskRunStatics@234567@@12@A; factory_cache_entry<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics>
0x1400099f2  mov     rax, [rbx]
0x1400099f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099fa  nop
0x1400099fb  lock dec cs:qword_140011968
0x140009a03  jmp     short loc_140009A12
0x140009a05  lea     rcx, [rbp+arg_10]
0x140009a09  mov     rax, [rbx]
0x140009a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a11  nop
0x140009a12  cmp     [rbp+arg_10], 0
0x140009a17  jz      short loc_140009A22
0x140009a19  lea     rcx, [rbp+arg_10]
0x140009a1d  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x140009a22  mov     rbx, [rsp+60h+arg_8]
0x140009a27  add     rsp, 60h
0x140009a2b  pop     rbp
0x140009a2c  retn
0x140009a2d  lea     rdx, [rbp+var_40]
0x140009a31  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
