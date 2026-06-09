# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800197ac`
- end: `0x18001986d`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18000a720`

## callees

- `0x18000a3f0`
- `0x18000a52c`
- `0x1800197ac`
- `0x180019874`
- `0x180019938`
- `0x180019958`
- `0x18001999c`
- `0x180029bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800197fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800197fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001985d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001985d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019828`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019828`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  char v10; // [rsp+50h] [rbp+8h] BYREF

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    if ( !BYTE1(a1[8].Ptr) )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    if ( a1 != (RTL_SRWLOCK *)-32LL )
      ReleaseSRWLockExclusive(a1 + 4);
  }
}

```

## disassembly

```asm
0x1800197ac  push    rbx
0x1800197ae  push    rbp
0x1800197af  push    rsi
0x1800197b0  push    rdi
0x1800197b1  sub     rsp, 28h
0x1800197b5  mov     rdi, r9
0x1800197b8  mov     esi, r8d
0x1800197bb  mov     ebp, edx
0x1800197bd  mov     rbx, rcx
0x1800197c0  cmp     byte ptr [rcx], 0
0x1800197c3  jz      loc_180019864
0x1800197c9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800197ce  test    al, al
0x1800197d0  jz      loc_180019864
0x1800197d6  mov     r9, rdi
0x1800197d9  mov     r8d, esi
0x1800197dc  mov     edx, ebp
0x1800197de  mov     rcx, [rbx+18h]
0x1800197e2  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800197e7  test    al, al
0x1800197e9  jz      short loc_180019864
0x1800197eb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800197f0  test    al, al
0x1800197f2  jnz     short loc_180019864
0x1800197f4  lea     rdi, [rbx+20h]
0x1800197f8  mov     rcx, rdi; SRWLock
0x1800197fb  call    cs:__imp_AcquireSRWLockExclusive
0x180019801  cmp     byte ptr [rbx+41h], 0
0x180019805  jnz     short loc_180019855
0x180019807  lea     rsi, [rbx+30h]
0x18001980b  cmp     qword ptr [rsi], 0
0x18001980f  jnz     short loc_180019843
0x180019811  lea     rcx, [rsp+48h+arg_0]; this
0x180019816  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001981b  xor     r8d, r8d; pcbe
0x18001981e  mov     rdx, rbx; pv
0x180019821  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019828  call    cs:__imp_CreateThreadpoolTimer
0x18001982e  mov     rdx, rax
0x180019831  mov     rcx, rsi
0x180019834  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180019839  lea     rcx, [rsp+48h+arg_0]; this
0x18001983e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180019843  mov     r8d, 493E0h
0x180019849  lea     rdx, [rbx+41h]
0x18001984d  mov     rcx, rsi
0x180019850  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180019855  test    rdi, rdi
0x180019858  jz      short loc_180019864
0x18001985a  mov     rcx, rdi; SRWLock
0x18001985d  call    cs:__imp_ReleaseSRWLockExclusive
0x180019863  nop
0x180019864  add     rsp, 28h
0x180019868  pop     rdi
0x180019869  pop     rsi
0x18001986a  pop     rbp
0x18001986b  pop     rbx
0x18001986c  retn
```
