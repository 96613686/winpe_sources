# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140003808`
- end: `0x14000387c`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140007cb0`

## callees

- `0x140003808`
- `0x140003ac0`
- `0x140003b84`
- `0x14000464c`
- `0x14000850c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000384f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000384f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000386d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000386d`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx

  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(&a1[6].Ptr, (_BYTE *)&a1[8].Ptr + 1, a1);
    if ( a1 != (RTL_SRWLOCK *)-32LL )
      ReleaseSRWLockExclusive(a1 + 4);
  }
}

```

## disassembly

```asm
0x140003808  push    rbx
0x14000380a  push    rbp
0x14000380b  push    rsi
0x14000380c  push    rdi
0x14000380d  sub     rsp, 28h
0x140003811  cmp     byte ptr [rcx], 0
0x140003814  mov     rdi, r9
0x140003817  mov     esi, r8d
0x14000381a  mov     ebp, edx
0x14000381c  mov     rbx, rcx
0x14000381f  jz      short loc_140003873
0x140003821  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140003826  test    al, al
0x140003828  jz      short loc_140003873
0x14000382a  mov     rcx, [rbx+18h]
0x14000382e  mov     r9, rdi
0x140003831  mov     r8d, esi
0x140003834  mov     edx, ebp
0x140003836  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000383b  test    al, al
0x14000383d  jz      short loc_140003873
0x14000383f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140003844  test    al, al
0x140003846  jnz     short loc_140003873
0x140003848  lea     rdi, [rbx+20h]
0x14000384c  mov     rcx, rdi; SRWLock
0x14000384f  call    cs:__imp_AcquireSRWLockExclusive
0x140003855  lea     rdx, [rbx+41h]
0x140003859  mov     r8, rbx
0x14000385c  lea     rcx, [rbx+30h]
0x140003860  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x140003865  test    rdi, rdi
0x140003868  jz      short loc_140003873
0x14000386a  mov     rcx, rdi; SRWLock
0x14000386d  call    cs:__imp_ReleaseSRWLockExclusive
0x140003873  add     rsp, 28h
0x140003877  pop     rdi
0x140003878  pop     rsi
0x140003879  pop     rbp
0x14000387a  pop     rbx
0x14000387b  retn
```
