# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18005c2d0`
- end: `0x18005c38c`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800801a0`

## callees

- `0x18005c2d0`
- `0x18005c394`
- `0x18005cb34`
- `0x18005cb68`
- `0x18005dafc`
- `0x18005db40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c32d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005c32d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c319`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005c319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c34a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c34a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c372`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c372`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005c35f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005c35f`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax

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
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        SetLastError(LastError);
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
0x18005c2d0  push    rbx
0x18005c2d2  push    rbp
0x18005c2d3  push    rsi
0x18005c2d4  push    rdi
0x18005c2d5  push    r14
0x18005c2d7  sub     rsp, 20h
0x18005c2db  mov     rbx, r9
0x18005c2de  mov     esi, r8d
0x18005c2e1  mov     ebp, edx
0x18005c2e3  mov     rdi, rcx
0x18005c2e6  cmp     byte ptr [rcx], 0
0x18005c2e9  jz      short loc_18005C334
0x18005c2eb  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18005c2f0  test    al, al
0x18005c2f2  jz      short loc_18005C334
0x18005c2f4  mov     r9, rbx
0x18005c2f7  mov     r8d, esi
0x18005c2fa  mov     edx, ebp
0x18005c2fc  mov     rcx, [rdi+18h]
0x18005c300  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18005c305  test    al, al
0x18005c307  jz      short loc_18005C334
0x18005c309  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18005c30e  test    al, al
0x18005c310  jnz     short loc_18005C334
0x18005c312  lea     rsi, [rdi+20h]
0x18005c316  mov     rcx, rsi; SRWLock
0x18005c319  call    cs:__imp_AcquireSRWLockExclusive
0x18005c31f  cmp     byte ptr [rdi+41h], 0
0x18005c323  jz      short loc_18005C33F
0x18005c325  test    rsi, rsi
0x18005c328  jz      short loc_18005C334
0x18005c32a  mov     rcx, rsi; SRWLock
0x18005c32d  call    cs:__imp_ReleaseSRWLockExclusive
0x18005c333  nop
0x18005c334  add     rsp, 20h
0x18005c338  pop     r14
0x18005c33a  pop     rdi
0x18005c33b  pop     rsi
0x18005c33c  pop     rbp
0x18005c33d  pop     rbx
0x18005c33e  retn
0x18005c33f  lea     rbp, [rdi+30h]
0x18005c343  cmp     qword ptr [rbp+0], 0
0x18005c348  jnz     short loc_18005C378
0x18005c34a  call    cs:__imp_GetLastError
0x18005c350  mov     ebx, eax
0x18005c352  xor     r8d, r8d; pcbe
0x18005c355  mov     rdx, rdi; pv
0x18005c358  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005c35f  call    cs:__imp_CreateThreadpoolTimer
0x18005c365  mov     rdx, rax
0x18005c368  mov     rcx, rbp
0x18005c36b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005c370  mov     ecx, ebx; dwErrCode
0x18005c372  call    cs:__imp_SetLastError
0x18005c378  mov     r8d, 493E0h
0x18005c37e  lea     rdx, [rdi+41h]
0x18005c382  mov     rcx, rbp
0x18005c385  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18005c38a  jmp     short loc_18005C325
```
