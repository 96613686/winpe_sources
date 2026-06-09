# UsageAndQualityInsights::Configuration::ConfigStore::EnableMetricGroup(void)

- ea: `0x1800e6bb8`
- end: `0x1800e6dc6`
- name: `?EnableMetricGroup@ConfigStore@Configuration@UsageAndQualityInsights@@AEAAXXZ`
- size: `526`
- prototype: `void __fastcall(UsageAndQualityInsights::Configuration::ConfigStore *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e75bc`

## callees

- `0x180008320`
- `0x180013c48`
- `0x180013e44`
- `0x1800149fc`
- `0x180016628`
- `0x180016d2c`
- `0x180016dcc`
- `0x180018e64`
- `0x18001a120`
- `0x1800e427c`
- `0x1800e5030`
- `0x1800e6bb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6d38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6d38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e6c77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e6c77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e6c06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e6cb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e6d90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e6c06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e6cb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e6d90`
- `RPCRT4!RpcBindingFree` at `0x1800e6d13`
- `RPCRT4!RpcBindingFree` at `0x1800e6d13`

## string_xrefs

- `0x1800e6db4`: `onecore\base\usageandqualityinsights\service\lib\configuration\configstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UsageAndQualityInsights::Configuration::ConfigStore::EnableMetricGroup(
        UsageAndQualityInsights::Configuration::ConfigStore *this)
{
  __int64 *v1; // rax
  __int64 v2; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 *Local; // rax
  const wchar_t *v7; // rdx
  const wchar_t *v8; // r8
  int v9; // eax
  struct _RTL_CRITICAL_SECTION *v10; // rax
  LONG *p_LockCount; // rbx
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  void **v13; // [rsp+20h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-48h] BYREF
  void **v15; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v16[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v17; // [rsp+48h] [rbp-28h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-20h]
  __int64 v19; // [rsp+58h] [rbp-18h]
  char v20; // [rsp+60h] [rbp-10h]
  LPVOID v21; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  UsageAndQualityInsights::Configuration::ConfigStore *v23; // [rsp+80h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+18h] BYREF

  v23 = this;
  v1 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>,>(&pv);
  v2 = *v1;
  *v1 = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v3);
    CoTaskMemFree(v3);
  }
  tip2::details::shared_data<0,0,0>::start(v2 + 8, &v13);
  v15 = &tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable';
  v16[0] = 0;
  v16[1] = &v15;
  v17 = 0;
  CurrentThreadId = 0;
  v19 = 0;
  v20 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(v4) = 1;
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         v5,
                         v4);
    v16[0] = Local;
    if ( Local )
    {
      v17 = *Local;
      *Local = (__int64)v16;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  else
  {
    v16[0] = 0;
  }
  v21 = (LPVOID)v2;
  if ( v2 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 272));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 272), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>((struct _RTL_CRITICAL_SECTION *)v2);
      CoTaskMemFree((LPVOID)v2);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl) )
  {
    Binding = 0;
    v13 = &Microsoft::Diagnostics::UtcMetricsApiWrapper::`vftable';
    Microsoft::Diagnostics::UtcWrapperBase::Initialize((Microsoft::Diagnostics::UtcWrapperBase *)&v13);
    v9 = Microsoft::Diagnostics::UtcMetricsApiWrapper::EnableMetricGroup(
           (Microsoft::Diagnostics::UtcMetricsApiWrapper *)&v13,
           v7,
           v8);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\configstore.cpp",
        (const char *)(unsigned int)v9,
        (int)v13);
    v13 = &Microsoft::Diagnostics::UtcMetricsApiWrapper::`vftable';
    if ( Binding )
      RpcBindingFree(&Binding);
  }
  v10 = (struct _RTL_CRITICAL_SECTION *)v21;
  v23 = (UsageAndQualityInsights::Configuration::ConfigStore *)v21;
  if ( v21 )
    _InterlockedIncrement((volatile signed __int32 *)v21 + 68);
  p_LockCount = &v10->LockCount;
  EnterCriticalSection(v10 + 5);
  ++p_LockCount[58];
  p_LockCount[16] |= 0xB00u;
  if ( *((_QWORD *)p_LockCount + 30) )
    tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 10);
  tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>((__int64 *)&v23);
  v12 = (struct _RTL_CRITICAL_SECTION *)v21;
  if ( v21 && _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 68, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(v12);
    CoTaskMemFree(v12);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v16);
}

```

## disassembly

```asm
0x1800e6bb8  mov     [rsp-8+arg_10], rbx
0x1800e6bbd  mov     [rsp-8+arg_18], rdi
0x1800e6bc2  mov     [rsp-8+arg_0], rcx
0x1800e6bc7  push    rbp
0x1800e6bc8  mov     rbp, rsp
0x1800e6bcb  sub     rsp, 70h
0x1800e6bcf  lea     rcx, [rbp+pv]
0x1800e6bd3  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>,>(void)
0x1800e6bd8  mov     rbx, [rax]
0x1800e6bdb  mov     qword ptr [rax], 0
0x1800e6be2  mov     rdi, [rbp+pv]
0x1800e6be6  test    rdi, rdi
0x1800e6be9  jz      short loc_1800E6C0C
0x1800e6beb  or      eax, 0FFFFFFFFh
0x1800e6bee  lock xadd [rdi+110h], eax
0x1800e6bf6  cmp     eax, 1
0x1800e6bf9  jnz     short loc_1800E6C0C
0x1800e6bfb  mov     rcx, rdi
0x1800e6bfe  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x1800e6c03  mov     rcx, rdi; pv
0x1800e6c06  call    cs:__imp_CoTaskMemFree
0x1800e6c0c  lea     rcx, [rbx+8]
0x1800e6c10  lea     rdx, [rbp+var_50]
0x1800e6c14  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800e6c19  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_UQIWnfCallbackExecutionTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_UQIWnfCallbackExecutionTipTest,_tip_UQIWnfCallbackExecutionTipTest>>::`vftable'
0x1800e6c20  mov     [rbp+var_40], rax
0x1800e6c24  mov     [rbp+var_38], 0
0x1800e6c2c  lea     rax, [rbp+var_40]
0x1800e6c30  mov     [rbp+var_30], rax
0x1800e6c34  mov     [rbp+var_28], 0
0x1800e6c3c  mov     [rbp+var_20], 0
0x1800e6c43  mov     [rbp+var_18], 0
0x1800e6c4b  mov     [rbp+var_10], 0
0x1800e6c4f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800e6c57  jz      short loc_1800E6C82
0x1800e6c59  mov     dl, 1
0x1800e6c5b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800e6c60  mov     [rbp+var_38], rax
0x1800e6c64  test    rax, rax
0x1800e6c67  jz      short loc_1800E6C8A
0x1800e6c69  mov     rcx, [rax]
0x1800e6c6c  mov     [rbp+var_28], rcx
0x1800e6c70  lea     rcx, [rbp+var_38]
0x1800e6c74  mov     [rax], rcx
0x1800e6c77  call    cs:__imp_GetCurrentThreadId
0x1800e6c7d  mov     [rbp+var_20], eax
0x1800e6c80  jmp     short loc_1800E6C8A
0x1800e6c82  mov     [rbp+var_38], 0
0x1800e6c8a  mov     [rbp+var_8], rbx
0x1800e6c8e  test    rbx, rbx
0x1800e6c91  jz      short loc_1800E6CBC
0x1800e6c93  lock inc dword ptr [rbx+110h]
0x1800e6c9a  or      eax, 0FFFFFFFFh
0x1800e6c9d  lock xadd [rbx+110h], eax
0x1800e6ca5  cmp     eax, 1
0x1800e6ca8  jnz     short loc_1800E6CBC
0x1800e6caa  mov     rcx, rbx
0x1800e6cad  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x1800e6cb2  mov     rcx, rbx; pv
0x1800e6cb5  call    cs:__imp_CoTaskMemFree
0x1800e6cbb  nop
0x1800e6cbc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport> `wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl(void)'::`2'::impl
0x1800e6cc3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(void)
0x1800e6cc8  test    al, al
0x1800e6cca  jz      short loc_1800E6D19
0x1800e6ccc  mov     [rbp+Binding], 0
0x1800e6cd4  lea     rax, ??_7UtcMetricsApiWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcMetricsApiWrapper::`vftable'
0x1800e6cdb  mov     [rbp+var_50], rax
0x1800e6cdf  lea     rcx, [rbp+var_50]; this
0x1800e6ce3  call    ?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)
0x1800e6ce8  lea     rcx, [rbp+var_50]; this
0x1800e6cec  call    ?EnableMetricGroup@UtcMetricsApiWrapper@Diagnostics@Microsoft@@QEBAJPEB_W0@Z; Microsoft::Diagnostics::UtcMetricsApiWrapper::EnableMetricGroup(wchar_t const *,wchar_t const *)
0x1800e6cf1  mov     rcx, [rbp+8]; this
0x1800e6cf5  test    eax, eax
0x1800e6cf7  js      loc_1800E6DB1
0x1800e6cfd  lea     rax, ??_7UtcMetricsApiWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcMetricsApiWrapper::`vftable'
0x1800e6d04  mov     [rbp+var_50], rax
0x1800e6d08  cmp     [rbp+Binding], 0
0x1800e6d0d  jz      short loc_1800E6D19
0x1800e6d0f  lea     rcx, [rbp+Binding]; Binding
0x1800e6d13  call    cs:__imp_RpcBindingFree
0x1800e6d19  mov     rax, [rbp+var_8]
0x1800e6d1d  mov     [rbp+arg_0], rax
0x1800e6d21  test    rax, rax
0x1800e6d24  jz      short loc_1800E6D2D
0x1800e6d26  lock inc dword ptr [rax+110h]
0x1800e6d2d  lea     rbx, [rax+8]
0x1800e6d31  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800e6d38  call    cs:__imp_EnterCriticalSection
0x1800e6d3e  inc     dword ptr [rbx+0E8h]
0x1800e6d44  or      dword ptr [rbx+40h], 0B00h
0x1800e6d4b  cmp     qword ptr [rbx+0F0h], 0
0x1800e6d53  jz      short loc_1800E6D62
0x1800e6d55  mov     edx, 0Ah
0x1800e6d5a  mov     rcx, rbx
0x1800e6d5d  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800e6d62  lea     rcx, [rbp+arg_0]
0x1800e6d66  call    ??1?$test_data_control@V?$merged_data@U_tip_UQISaveFactsToFactStoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_UQISaveFactsToFactStoreTipTest,_tip_UQISaveFactsToFactStoreTipTest>>(void)
0x1800e6d6b  nop
0x1800e6d6c  mov     rbx, [rbp+var_8]
0x1800e6d70  test    rbx, rbx
0x1800e6d73  jz      short loc_1800E6D96
0x1800e6d75  or      eax, 0FFFFFFFFh
0x1800e6d78  lock xadd [rbx+110h], eax
0x1800e6d80  cmp     eax, 1
0x1800e6d83  jnz     short loc_1800E6D96
0x1800e6d85  mov     rcx, rbx
0x1800e6d88  call    ??1?$merged_data@U_tip_UQIGetOrCreateDatabaseTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>::~merged_data<_tip_UQIGetOrCreateDatabaseTipTest,_tip_UQIGetOrCreateDatabaseTipTest>(void)
0x1800e6d8d  mov     rcx, rbx; pv
0x1800e6d90  call    cs:__imp_CoTaskMemFree
0x1800e6d96  lea     rcx, [rbp+var_38]; this
0x1800e6d9a  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800e6d9f  lea     r11, [rsp+70h+var_s0]
0x1800e6da4  mov     rbx, [r11+20h]
0x1800e6da8  mov     rdi, [r11+28h]
0x1800e6dac  mov     rsp, r11
0x1800e6daf  pop     rbp
0x1800e6db0  retn
0x1800e6db1  mov     r9d, eax; char *
0x1800e6db4  lea     r8, aOnecoreBaseUsa_17; "onecore\\base\\usageandqualityinsights"...
0x1800e6dbb  mov     edx, 54h ; 'T'; void *
0x1800e6dc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
