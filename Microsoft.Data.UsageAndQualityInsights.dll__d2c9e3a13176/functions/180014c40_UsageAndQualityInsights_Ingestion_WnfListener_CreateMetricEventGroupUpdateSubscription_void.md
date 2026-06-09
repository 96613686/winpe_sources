# UsageAndQualityInsights::Ingestion::WnfListener::CreateMetricEventGroupUpdateSubscription(void)

- ea: `0x180014c40`
- end: `0x180014dc0`
- name: `?CreateMetricEventGroupUpdateSubscription@WnfListener@Ingestion@UsageAndQualityInsights@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180010d9c`

## callees

- `0x1800033d0`
- `0x1800122bc`
- `0x180012aa4`
- `0x180013c48`
- `0x180013e44`
- `0x1800149fc`
- `0x180014c40`
- `0x180016628`
- `0x180016dcc`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
_QWORD *__fastcall UsageAndQualityInsights::Ingestion::WnfListener::CreateMetricEventGroupUpdateSubscription(
        _QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // eax
  __int64 v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rax
  __int64 p_LockCount; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  int v10[2]; // [rsp+20h] [rbp-E8h] BYREF
  _QWORD *v11; // [rsp+28h] [rbp-E0h]
  _BYTE v12[8]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v13[48]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-90h]
  _BYTE v15[8]; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v16[13]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v17; // [rsp+F0h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v11 = a1;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_UQIWnfSubscriptionCreationTipTest,_tip_UQIWnfSubscriptionCreationTipTest>>>((__int64)v12);
  v16[0] = ___7____func_P6AXUMetricApiWnf_Ingestion_UsageAndQualityInsights____E__A6AXAEBU123__Z___function_wistd__6B_;
  v16[1] = UsageAndQualityInsights::Ingestion::WnfListener::ProcessMetricEventGroupUpdate;
  v17 = v16;
  *(_QWORD *)v10 = 0;
  v4 = wil::details::make_wnf_subscription_state<UsageAndQualityInsights::Ingestion::MetricApiWnf>(v2, v15, v3, v10);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43C,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v4,
      v10[0]);
  v5 = *(_QWORD *)v10;
  if ( v17 )
    (*(void (__fastcall **)(_QWORD *))(*v17 + 24LL))(v17);
  v6 = (struct _RTL_CRITICAL_SECTION *)pv;
  *(_QWORD *)v10 = pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 68);
  p_LockCount = (__int64)&v6->LockCount;
  EnterCriticalSection(v6 + 5);
  ++*(_DWORD *)(p_LockCount + 232);
  *(_DWORD *)(p_LockCount + 64) |= 0xB00u;
  if ( *(_QWORD *)(p_LockCount + 240) )
    tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 0xAu);
  tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>((__int64 *)v10);
  *a1 = v5;
  v8 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v8);
    CoTaskMemFree(v8);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v13);
  return a1;
}

```

## disassembly

```asm
0x180014c40  mov     [rsp+arg_8], rbx
0x180014c45  mov     [rsp+arg_10], rsi
0x180014c4a  push    rdi
0x180014c4b  sub     rsp, 100h
0x180014c52  mov     rax, cs:__security_cookie
0x180014c59  xor     rax, rsp
0x180014c5c  mov     [rsp+108h+var_10], rax
0x180014c64  mov     rsi, rcx
0x180014c67  mov     [rsp+108h+var_E0], rcx
0x180014c6c  lea     rcx, [rsp+108h+var_C8]
0x180014c71  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIWnfSubscriptionCreationTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180014c76  nop
0x180014c77  lea     rax, ??_7?$__func@P6AXUMetricApiWnf@Ingestion@UsageAndQualityInsights@@@_E$$A6AXAEBU123@@Z@__function@wistd@@6B@
0x180014c7e  mov     [rsp+108h+var_80], rax
0x180014c86  lea     rax, ?ProcessMetricEventGroupUpdate@WnfListener@Ingestion@UsageAndQualityInsights@@CAXUMetricApiWnf@23@@Z; UsageAndQualityInsights::Ingestion::WnfListener::ProcessMetricEventGroupUpdate(UsageAndQualityInsights::Ingestion::MetricApiWnf)
0x180014c8d  mov     [rsp+108h+var_78], rax
0x180014c95  lea     rax, [rsp+108h+var_80]
0x180014c9d  mov     [rsp+108h+var_18], rax
0x180014ca5  mov     qword ptr [rsp+108h+var_E8], 0; int
0x180014cae  lea     r9, [rsp+108h+var_E8]
0x180014cb3  lea     rdx, [rsp+108h+var_88]
0x180014cbb  call    ??$make_wnf_subscription_state@UMetricApiWnf@Ingestion@UsageAndQualityInsights@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBUMetricApiWnf@Ingestion@UsageAndQualityInsights@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@UMetricApiWnf@Ingestion@UsageAndQualityInsights@@@01@@Z; wil::details::make_wnf_subscription_state<UsageAndQualityInsights::Ingestion::MetricApiWnf>(_WNF_STATE_NAME const &,wistd::function<void (UsageAndQualityInsights::Ingestion::MetricApiWnf const &)> &&,ulong,wil::details::wnf_subscription_state<UsageAndQualityInsights::Ingestion::MetricApiWnf> * *)
0x180014cc0  mov     rcx, [rsp+108h]; this
0x180014cc8  test    eax, eax
0x180014cca  js      loc_180014DAA
0x180014cd0  mov     rbx, qword ptr [rsp+108h+var_E8]
0x180014cd5  mov     rcx, [rsp+108h+var_18]
0x180014cdd  test    rcx, rcx
0x180014ce0  jz      short loc_180014CEE
0x180014ce2  mov     rax, [rcx]
0x180014ce5  mov     rax, [rax+18h]
0x180014ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cee  mov     rax, [rsp+108h+pv]
0x180014cf3  mov     qword ptr [rsp+108h+var_E8], rax
0x180014cf8  test    rax, rax
0x180014cfb  jz      short loc_180014D04
0x180014cfd  lock inc dword ptr [rax+110h]
0x180014d04  lea     rdi, [rax+8]
0x180014d08  lea     rcx, [rdi+0C0h]; lpCriticalSection
0x180014d0f  call    cs:__imp_EnterCriticalSection
0x180014d15  inc     dword ptr [rdi+0E8h]
0x180014d1b  or      dword ptr [rdi+40h], 0B00h
0x180014d22  cmp     qword ptr [rdi+0F0h], 0
0x180014d2a  jz      short loc_180014D39
0x180014d2c  mov     edx, 0Ah
0x180014d31  mov     rcx, rdi
0x180014d34  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180014d39  lea     rcx, [rsp+108h+var_E8]
0x180014d3e  call    ??1?$test_data_control@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(void)
0x180014d43  mov     [rsi], rbx
0x180014d46  mov     rbx, [rsp+108h+pv]
0x180014d4b  test    rbx, rbx
0x180014d4e  jz      short loc_180014D71
0x180014d50  or      edx, 0FFFFFFFFh
0x180014d53  lock xadd [rbx+110h], edx
0x180014d5b  cmp     edx, 1
0x180014d5e  jnz     short loc_180014D71
0x180014d60  mov     rcx, rbx
0x180014d63  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x180014d68  mov     rcx, rbx; pv
0x180014d6b  call    cs:__imp_CoTaskMemFree
0x180014d71  lea     rcx, [rsp+108h+var_C0]; this
0x180014d76  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180014d7b  mov     rax, rsi
0x180014d7e  jmp     short loc_180014D85
0x180014d80  mov     rax, [rsp+108h+var_E0]
0x180014d85  mov     rcx, [rsp+108h+var_10]
0x180014d8d  xor     rcx, rsp; StackCookie
0x180014d90  call    __security_check_cookie
0x180014d95  lea     r11, [rsp+108h+var_8]
0x180014d9d  mov     rbx, [r11+18h]
0x180014da1  mov     rsi, [r11+20h]
0x180014da5  mov     rsp, r11
0x180014da8  pop     rdi
0x180014da9  retn
0x180014daa  mov     r9d, eax; char *
0x180014dad  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180014db4  mov     edx, 43Ch; void *
0x180014db9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
