# UsageAndQualityInsights::Utilities::CreateWnfSubscription<_LARGE_INTEGER,UsageAndQualityInsights::Signals::ExpIdSubscription>(_WNF_STATE_NAME,std::weak_ptr<UsageAndQualityInsights::Signals::ExpIdSubscription>)

- ea: `0x18001c64c`
- end: `0x18001c88d`
- name: `??$CreateWnfSubscription@T_LARGE_INTEGER@@VExpIdSubscription@Signals@UsageAndQualityInsights@@@Utilities@UsageAndQualityInsights@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@U_WNF_STATE_NAME@@V?$weak_ptr@VExpIdSubscription@Signals@UsageAndQualityInsights@@@std@@@Z`
- size: `577`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f488`

## callees

- `0x1800033d0`
- `0x180012aa4`
- `0x180013c48`
- `0x180013e44`
- `0x1800149fc`
- `0x180016628`
- `0x180016dcc`
- `0x18001c64c`
- `0x18001ce3c`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c776`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c7f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c7f7`

## pseudocode

```c
_QWORD *__fastcall UsageAndQualityInsights::Utilities::CreateWnfSubscription<_LARGE_INTEGER,UsageAndQualityInsights::Signals::ExpIdSubscription>(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v5; // r8
  volatile signed __int32 **v6; // r15
  volatile signed __int32 *v7; // rdi
  __int64 v8; // rcx
  volatile signed __int32 *v9; // rax
  int wnf_subscription; // eax
  __int64 v11; // rbx
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  void *v13; // rdi
  volatile signed __int32 *v14; // rcx
  volatile signed __int32 *v16; // rcx
  int v17[4]; // [rsp+20h] [rbp-138h] BYREF
  _QWORD *v18; // [rsp+30h] [rbp-128h]
  volatile signed __int32 **v19; // [rsp+40h] [rbp-118h]
  __int128 v20; // [rsp+48h] [rbp-110h]
  _QWORD *v21; // [rsp+58h] [rbp-100h]
  _BYTE v22[8]; // [rsp+60h] [rbp-F8h] BYREF
  _BYTE v23[48]; // [rsp+68h] [rbp-F0h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-C0h]
  __int64 v25; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE v26[8]; // [rsp+A8h] [rbp-B0h] BYREF
  _QWORD v27[13]; // [rsp+B0h] [rbp-A8h] BYREF
  _QWORD *v28; // [rsp+118h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v18 = a1;
  v25 = a2;
  v21 = a3;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_UQIWnfSubscriptionCreationTipTest,_tip_UQIWnfSubscriptionCreationTipTest>>>(v22);
  v20 = 0;
  v6 = (volatile signed __int32 **)(a3 + 1);
  v19 = (volatile signed __int32 **)(a3 + 1);
  v7 = (volatile signed __int32 *)a3[1];
  if ( v7 )
  {
    v8 = *a3;
    *(_QWORD *)&v20 = *a3;
    *((_QWORD *)&v20 + 1) = v7;
    _InterlockedIncrement(v7 + 3);
    v9 = v7;
  }
  else
  {
    v8 = 0;
    v9 = 0;
    v7 = (volatile signed __int32 *)*((_QWORD *)&v20 + 1);
  }
  if ( v9 )
    _InterlockedIncrement(v9 + 3);
  else
    v8 = 0;
  v27[0] = &___7____func_V_lambda_1___2____CreateWnfSubscription_T_LARGE_INTEGER__VExpIdSubscription_Signals_UsageAndQualityInsights___Utilities_UsageAndQualityInsights__YA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAUwnf_subscription_state_base_details_wil__P6AXPEAU123__Z_1_delete_wnf_subscription_state_23_YAX0_ZU__integral_constant__K_01_wistd__PEAU123_PEAU123__0A___T_details_wil___details_wil___wil__U_WNF_STATE_NAME__V__weak_ptr_VExpIdSubscription_Signals_UsageAndQualityInsights___std___Z___A6AXAEBT_LARGE_INTEGER___Z___function_wistd__6B_;
  v27[1] = v8;
  v27[2] = v9;
  v28 = v27;
  *(_QWORD *)v17 = 0;
  wnf_subscription = wil::details::make_wnf_subscription_state<_LARGE_INTEGER>(&v25, v26, v5, v17);
  if ( wnf_subscription < 0 )
  {
    try
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43C,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
        (const char *)(unsigned int)wnf_subscription,
        v17[0]);
    }
    catch ( ... )
    {
      *v18 = 0;
      v16 = *v19;
      if ( *v19 && _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      return v18;
    }
  }
  v11 = *(_QWORD *)v17;
  if ( v28 )
    (*(void (__fastcall **)(_QWORD *))(*v28 + 24LL))(v28);
  v12 = (struct _RTL_CRITICAL_SECTION *)pv;
  *(_QWORD *)v17 = pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 68);
  EnterCriticalSection(v12 + 5);
  ++LODWORD(v12[6].DebugInfo);
  LODWORD(v12[1].SpinCount) |= 0xB00u;
  if ( *(_QWORD *)&v12[6].LockCount )
    tip2::details::shared_data<0,0,0>::complete_helper(&v12->LockCount, 10);
  tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(v17);
  *a1 = v11;
  if ( v7 && _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
  v13 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v13);
    CoTaskMemFree(v13);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v23);
  v14 = *v6;
  if ( *v6 )
  {
    if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
  }
  return a1;
}

```

## disassembly

```asm
0x18001c64c  push    rbx
0x18001c64e  push    rsi
0x18001c64f  push    rdi
0x18001c650  push    r14
0x18001c652  push    r15
0x18001c654  sub     rsp, 130h
0x18001c65b  mov     rax, cs:__security_cookie
0x18001c662  xor     rax, rsp
0x18001c665  mov     [rsp+158h+var_38], rax
0x18001c66d  mov     rbx, r8
0x18001c670  mov     r14, rcx
0x18001c673  mov     [rsp+158h+var_128], rcx
0x18001c678  mov     [rsp+158h+var_B8], rdx
0x18001c680  mov     [rsp+158h+var_100], rbx
0x18001c685  lea     rcx, [rsp+158h+var_F8]
0x18001c68a  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIWnfSubscriptionCreationTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18001c68f  nop
0x18001c690  xorps   xmm0, xmm0
0x18001c693  movdqu  [rsp+158h+var_110], xmm0
0x18001c699  lea     r15, [rbx+8]
0x18001c69d  mov     [rsp+158h+var_118], r15
0x18001c6a2  mov     rdi, [r15]
0x18001c6a5  test    rdi, rdi
0x18001c6a8  jz      short loc_18001C6C0
0x18001c6aa  mov     rcx, [rbx]
0x18001c6ad  mov     qword ptr [rsp+158h+var_110], rcx
0x18001c6b2  mov     qword ptr [rsp+158h+var_110+8], rdi
0x18001c6b7  lock inc dword ptr [rdi+0Ch]
0x18001c6bb  mov     rax, rdi
0x18001c6be  jmp     short loc_18001C6C9
0x18001c6c0  xor     ecx, ecx
0x18001c6c2  xor     eax, eax
0x18001c6c4  mov     rdi, qword ptr [rsp+158h+var_110+8]
0x18001c6c9  test    rax, rax
0x18001c6cc  jz      short loc_18001C6D4
0x18001c6ce  lock inc dword ptr [rax+0Ch]
0x18001c6d2  jmp     short loc_18001C6D6
0x18001c6d4  xor     ecx, ecx
0x18001c6d6  lea     rdx, ??_7?$__func@V_lambda_1_@?2???$CreateWnfSubscription@T_LARGE_INTEGER@@VExpIdSubscription@Signals@UsageAndQualityInsights@@@Utilities@UsageAndQualityInsights@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@U_WNF_STATE_NAME@@V?$weak_ptr@VExpIdSubscription@Signals@UsageAndQualityInsights@@@std@@@Z@$$A6AXAEBT_LARGE_INTEGER@@@Z@__function@wistd@@6B@; const wistd::__function::__func<`UsageAndQualityInsights::Utilities::CreateWnfSubscription<_LARGE_INTEGER,UsageAndQualityInsights::Signals::ExpIdSubscription>(_WNF_STATE_NAME,std::weak_ptr<UsageAndQualityInsights::Signals::ExpIdSubscription>)'::`3'::_lambda_1_,void (_LARGE_INTEGER const &)>::`vftable'
0x18001c6dd  mov     [rsp+158h+var_A8], rdx
0x18001c6e5  mov     [rsp+158h+var_A0], rcx
0x18001c6ed  mov     [rsp+158h+var_98], rax
0x18001c6f5  lea     rax, [rsp+158h+var_A8]
0x18001c6fd  mov     [rsp+158h+var_40], rax
0x18001c705  mov     qword ptr [rsp+158h+var_138], 0; int
0x18001c70e  lea     r9, [rsp+158h+var_138]
0x18001c713  lea     rdx, [rsp+158h+var_B0]
0x18001c71b  lea     rcx, [rsp+158h+var_B8]
0x18001c723  call    ??$make_wnf_subscription_state@T_LARGE_INTEGER@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBT_LARGE_INTEGER@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@T_LARGE_INTEGER@@@01@@Z; wil::details::make_wnf_subscription_state<_LARGE_INTEGER>(_WNF_STATE_NAME const &,wistd::function<void (_LARGE_INTEGER const &)> &&,ulong,wil::details::wnf_subscription_state<_LARGE_INTEGER> * *)
0x18001c728  mov     rcx, [rsp+158h]; this
0x18001c730  test    eax, eax
0x18001c732  js      loc_18001C877
0x18001c738  mov     rbx, qword ptr [rsp+158h+var_138]
0x18001c73d  mov     rcx, [rsp+158h+var_40]
0x18001c745  test    rcx, rcx
0x18001c748  jz      short loc_18001C756
0x18001c74a  mov     rax, [rcx]
0x18001c74d  mov     rax, [rax+18h]
0x18001c751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c756  mov     rsi, [rsp+158h+pv]
0x18001c75e  mov     qword ptr [rsp+158h+var_138], rsi
0x18001c763  test    rsi, rsi
0x18001c766  jz      short loc_18001C76F
0x18001c768  lock inc dword ptr [rsi+110h]
0x18001c76f  lea     rcx, [rsi+0C8h]; lpCriticalSection
0x18001c776  call    cs:__imp_EnterCriticalSection
0x18001c77c  inc     dword ptr [rsi+0F0h]
0x18001c782  or      dword ptr [rsi+48h], 0B00h
0x18001c789  cmp     qword ptr [rsi+0F8h], 0
0x18001c791  jz      short loc_18001C7A1
0x18001c793  mov     edx, 0Ah
0x18001c798  lea     rcx, [rsi+8]
0x18001c79c  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001c7a1  lea     rcx, [rsp+158h+var_138]
0x18001c7a6  call    ??1?$test_data_control@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(void)
0x18001c7ab  mov     [r14], rbx
0x18001c7ae  or      ebx, 0FFFFFFFFh
0x18001c7b1  test    rdi, rdi
0x18001c7b4  jz      short loc_18001C7D1
0x18001c7b6  mov     eax, ebx
0x18001c7b8  lock xadd [rdi+0Ch], eax
0x18001c7bd  add     eax, ebx
0x18001c7bf  jnz     short loc_18001C7D1
0x18001c7c1  mov     rax, [rdi]
0x18001c7c4  mov     rcx, rdi
0x18001c7c7  mov     rax, [rax+8]
0x18001c7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7d0  nop
0x18001c7d1  mov     rdi, [rsp+158h+pv]
0x18001c7d9  test    rdi, rdi
0x18001c7dc  jz      short loc_18001C7FD
0x18001c7de  mov     eax, ebx
0x18001c7e0  lock xadd [rdi+110h], eax
0x18001c7e8  add     eax, ebx
0x18001c7ea  jnz     short loc_18001C7FD
0x18001c7ec  mov     rcx, rdi
0x18001c7ef  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x18001c7f4  mov     rcx, rdi; pv
0x18001c7f7  call    cs:__imp_CoTaskMemFree
0x18001c7fd  lea     rcx, [rsp+158h+var_F0]; this
0x18001c802  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001c807  nop
0x18001c808  mov     rcx, [r15]
0x18001c80b  test    rcx, rcx
0x18001c80e  jz      short loc_18001C827
0x18001c810  mov     edx, ebx
0x18001c812  lock xadd [rcx+0Ch], edx
0x18001c817  add     edx, ebx
0x18001c819  jnz     short loc_18001C827
0x18001c81b  mov     rdx, [rcx]
0x18001c81e  mov     rax, [rdx+8]
0x18001c822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c827  mov     rax, r14
0x18001c82a  jmp     short loc_18001C858
0x18001c82c  mov     rax, [rsp+158h+var_118]
0x18001c831  mov     rcx, [rax]
0x18001c834  test    rcx, rcx
0x18001c837  jz      short loc_18001C853
0x18001c839  or      ebx, 0FFFFFFFFh
0x18001c83c  mov     eax, ebx
0x18001c83e  lock xadd [rcx+0Ch], eax
0x18001c843  add     eax, ebx
0x18001c845  jnz     short loc_18001C853
0x18001c847  mov     rax, [rcx]
0x18001c84a  mov     rax, [rax+8]
0x18001c84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c853  mov     rax, [rsp+158h+var_128]
0x18001c858  mov     rcx, [rsp+158h+var_38]
0x18001c860  xor     rcx, rsp; StackCookie
0x18001c863  call    __security_check_cookie
0x18001c868  add     rsp, 130h
0x18001c86f  pop     r15
0x18001c871  pop     r14
0x18001c873  pop     rdi
0x18001c874  pop     rsi
0x18001c875  pop     rbx
0x18001c876  retn
0x18001c877  mov     r9d, eax; char *
0x18001c87a  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x18001c881  mov     edx, 43Ch; void *
0x18001c886  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
