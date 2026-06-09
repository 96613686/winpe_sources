# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800159d8`
- end: `0x180015a93`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800788b0`

## callees

- `0x1800156bc`
- `0x1800159d8`
- `0x180015a9c`
- `0x1800162a8`
- `0x180016c2c`
- `0x180016c4c`
- `0x180016c90`
- `0x1800aa2bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015a33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015a33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015a1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015a1f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015a64`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015a64`

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
0x1800159d8  push    rbx
0x1800159da  push    rbp
0x1800159db  push    rsi
0x1800159dc  push    rdi
0x1800159dd  sub     rsp, 28h
0x1800159e1  mov     rdi, r9
0x1800159e4  mov     esi, r8d
0x1800159e7  mov     ebp, edx
0x1800159e9  mov     rbx, rcx
0x1800159ec  cmp     byte ptr [rcx], 0
0x1800159ef  jz      short loc_180015A3A
0x1800159f1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800159f6  test    al, al
0x1800159f8  jz      short loc_180015A3A
0x1800159fa  mov     r9, rdi
0x1800159fd  mov     r8d, esi
0x180015a00  mov     edx, ebp
0x180015a02  mov     rcx, [rbx+18h]
0x180015a06  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180015a0b  test    al, al
0x180015a0d  jz      short loc_180015A3A
0x180015a0f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180015a14  test    al, al
0x180015a16  jnz     short loc_180015A3A
0x180015a18  lea     rdi, [rbx+20h]
0x180015a1c  mov     rcx, rdi; SRWLock
0x180015a1f  call    cs:__imp_AcquireSRWLockExclusive
0x180015a25  cmp     byte ptr [rbx+41h], 0
0x180015a29  jz      short loc_180015A43
0x180015a2b  test    rdi, rdi
0x180015a2e  jz      short loc_180015A3A
0x180015a30  mov     rcx, rdi; SRWLock
0x180015a33  call    cs:__imp_ReleaseSRWLockExclusive
0x180015a39  nop
0x180015a3a  add     rsp, 28h
0x180015a3e  pop     rdi
0x180015a3f  pop     rsi
0x180015a40  pop     rbp
0x180015a41  pop     rbx
0x180015a42  retn
0x180015a43  lea     rsi, [rbx+30h]
0x180015a47  cmp     qword ptr [rsi], 0
0x180015a4b  jnz     short loc_180015A7F
0x180015a4d  lea     rcx, [rsp+48h+arg_0]; this
0x180015a52  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180015a57  xor     r8d, r8d; pcbe
0x180015a5a  mov     rdx, rbx; pv
0x180015a5d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180015a64  call    cs:__imp_CreateThreadpoolTimer
0x180015a6a  mov     rdx, rax
0x180015a6d  mov     rcx, rsi
0x180015a70  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180015a75  lea     rcx, [rsp+48h+arg_0]; this
0x180015a7a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180015a7f  mov     r8d, 493E0h
0x180015a85  lea     rdx, [rbx+41h]
0x180015a89  mov     rcx, rsi
0x180015a8c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180015a91  jmp     short loc_180015A2B
```
