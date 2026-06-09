# `UsageAndQualityInsights::Utilities::CreateWnfSubscription<_LARGE_INTEGER,UsageAndQualityInsights::Signals::ExpIdSubscription>(_WNF_STATE_NAME,std::weak_ptr<UsageAndQualityInsights::Signals::ExpIdSubscription>)'::`3'::_lambda_1_::operator()(_LARGE_INTEGER)

- ea: `0x18001d95c`
- end: `0x18001da9a`
- name: `??R_lambda_1_@?2???$CreateWnfSubscription@T_LARGE_INTEGER@@VExpIdSubscription@Signals@UsageAndQualityInsights@@@Utilities@UsageAndQualityInsights@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@U_WNF_STATE_NAME@@V?$weak_ptr@VExpIdSubscription@Signals@UsageAndQualityInsights@@@std@@@Z@QEBA@T_LARGE_INTEGER@@@Z`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001daa0`

## callees

- `0x180012998`
- `0x180013bbc`
- `0x180013dbc`
- `0x1800149fc`
- `0x180016dcc`
- `0x18001d95c`
- `0x18001f870`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001da0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001da0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall `UsageAndQualityInsights::Utilities::CreateWnfSubscription<_LARGE_INTEGER,UsageAndQualityInsights::Signals::ExpIdSubscription>'::`3'::_lambda_1_::operator()(
        __int128 *a1)
{
  union _LARGE_INTEGER v2; // rdx
  signed __int32 v3; // eax
  signed __int32 v4; // ett
  __int128 v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // rax
  __int64 p_LockCount; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  _BYTE v9[8]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v10[48]; // [rsp+38h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-10h]
  LPVOID v12; // [rsp+80h] [rbp+8h] BYREF

  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>>((__int64)v9);
  try
  {
    v2 = *(union _LARGE_INTEGER *)((char *)a1 + 8);
    if ( v2.QuadPart )
    {
      v3 = *(_DWORD *)(v2.QuadPart + 8);
      while ( v3 )
      {
        v4 = v3;
        v3 = _InterlockedCompareExchange((volatile signed __int32 *)(v2.QuadPart + 8), v3 + 1, v3);
        if ( v4 == v3 )
        {
          v5 = *a1;
          goto LABEL_7;
        }
      }
    }
    v5 = 0;
LABEL_7:
    if ( (_QWORD)v5 )
      UsageAndQualityInsights::Signals::ExpIdSubscription::ProcessWnf(
        (UsageAndQualityInsights::Signals::ExpIdSubscription *)v5,
        v2);
    if ( *((_QWORD *)&v5 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v5 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (***((void (__fastcall ****)(_QWORD))&v5 + 1))(*((_QWORD *)&v5 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v5 + 1) + 12LL), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v5 + 1) + 8LL))(*((_QWORD *)&v5 + 1));
      }
    }
    v6 = (struct _RTL_CRITICAL_SECTION *)pv;
    v12 = pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 70);
    p_LockCount = (__int64)&v6->LockCount;
    EnterCriticalSection(v6 + 5);
    ++*(_DWORD *)(p_LockCount + 232);
    *(_DWORD *)(p_LockCount + 64) |= 0xB00u;
    if ( *(_QWORD *)(p_LockCount + 240) )
      tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 0xAu);
    tip2::test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>((__int64 *)&v12);
    v8 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(v8);
      CoTaskMemFree(v8);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v10);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x18001d95c  push    rbx
0x18001d95e  sub     rsp, 70h
0x18001d962  mov     rbx, rcx
0x18001d965  lea     rcx, [rsp+78h+var_48]
0x18001d96a  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18001d96f  nop
0x18001d970  xorps   xmm0, xmm0
0x18001d973  movdqu  xmmword ptr [rsp+78h+var_58], xmm0
0x18001d979  mov     rdx, [rbx+8]; union _LARGE_INTEGER
0x18001d97d  test    rdx, rdx
0x18001d980  jz      short loc_18001D999
0x18001d982  mov     eax, [rdx+8]
0x18001d985  jmp     short loc_18001D995
0x18001d987  lea     ecx, [rax+1]
0x18001d98a  lock cmpxchg [rdx+8], ecx
0x18001d98f  jz      loc_18001DA82
0x18001d995  test    eax, eax
0x18001d997  jnz     short loc_18001D987
0x18001d999  mov     rcx, [rsp+78h+var_58]; this
0x18001d99e  mov     rbx, [rsp+78h+var_58+8]
0x18001d9a3  test    rcx, rcx
0x18001d9a6  jz      short loc_18001D9AE
0x18001d9a8  call    ?ProcessWnf@ExpIdSubscription@Signals@UsageAndQualityInsights@@QEAAXT_LARGE_INTEGER@@@Z; UsageAndQualityInsights::Signals::ExpIdSubscription::ProcessWnf(_LARGE_INTEGER)
0x18001d9ad  nop
0x18001d9ae  test    rbx, rbx
0x18001d9b1  jz      short loc_18001D9EA
0x18001d9b3  or      eax, 0FFFFFFFFh
0x18001d9b6  lock xadd [rbx+8], eax
0x18001d9bb  cmp     eax, 1
0x18001d9be  jnz     short loc_18001D9EA
0x18001d9c0  mov     rax, [rbx]
0x18001d9c3  mov     rcx, rbx
0x18001d9c6  mov     rax, [rax]
0x18001d9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9ce  or      eax, 0FFFFFFFFh
0x18001d9d1  lock xadd [rbx+0Ch], eax
0x18001d9d6  cmp     eax, 1
0x18001d9d9  jnz     short loc_18001D9EA
0x18001d9db  mov     rax, [rbx]
0x18001d9de  mov     rcx, rbx
0x18001d9e1  mov     rax, [rax+8]
0x18001d9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9ea  mov     rax, [rsp+78h+pv]
0x18001d9ef  mov     [rsp+78h+arg_0], rax
0x18001d9f7  test    rax, rax
0x18001d9fa  jz      short loc_18001DA03
0x18001d9fc  lock inc dword ptr [rax+118h]
0x18001da03  lea     rbx, [rax+8]
0x18001da07  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18001da0e  call    cs:__imp_EnterCriticalSection
0x18001da14  inc     dword ptr [rbx+0E8h]
0x18001da1a  or      dword ptr [rbx+40h], 0B00h
0x18001da21  cmp     qword ptr [rbx+0F0h], 0
0x18001da29  jz      short loc_18001DA38
0x18001da2b  mov     edx, 0Ah
0x18001da30  mov     rcx, rbx
0x18001da33  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001da38  lea     rcx, [rsp+78h+arg_0]
0x18001da40  call    ??1?$test_data_control@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>(void)
0x18001da45  nop
0x18001da46  mov     rbx, [rsp+78h+pv]
0x18001da4b  test    rbx, rbx
0x18001da4e  jz      short loc_18001DA71
0x18001da50  or      eax, 0FFFFFFFFh
0x18001da53  lock xadd [rbx+118h], eax
0x18001da5b  cmp     eax, 1
0x18001da5e  jnz     short loc_18001DA71
0x18001da60  mov     rcx, rbx
0x18001da63  call    ??1?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>::~merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>(void)
0x18001da68  mov     rcx, rbx; pv
0x18001da6b  call    cs:__imp_CoTaskMemFree
0x18001da71  lea     rcx, [rsp+78h+var_40]; this
0x18001da76  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001da7b  nop
0x18001da7c  add     rsp, 70h
0x18001da80  pop     rbx
0x18001da81  retn
0x18001da82  mov     rcx, [rbx]
0x18001da85  mov     [rsp+78h+var_58], rcx
0x18001da8a  mov     rbx, [rbx+8]
0x18001da8e  mov     [rsp+78h+var_58+8], rbx
0x18001da93  jmp     loc_18001D9A3
```
