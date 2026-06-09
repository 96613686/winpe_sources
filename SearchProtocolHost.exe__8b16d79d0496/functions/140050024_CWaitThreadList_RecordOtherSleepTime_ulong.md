# CWaitThreadList::RecordOtherSleepTime(ulong)

- ea: `0x140050024`
- end: `0x14005010c`
- name: `?RecordOtherSleepTime@CWaitThreadList@@QEAAXK@Z`
- size: `232`
- prototype: `void __fastcall(CWaitThreadList *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x14004fff8`
- `0x140050024`
- `0x140050114`
- `0x1400504b4`
- `0x140050534`
- `0x1400509ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140050079`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140050079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140050087`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140050093`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140050087`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140050093`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140050048`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140050048`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWaitThreadList::RecordOtherSleepTime(CWaitThreadList *this, int a2)
{
  _DWORD *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  unsigned int *v6; // rdx
  unsigned int v7; // r8d
  DWORD CurrentThreadId; // [rsp+50h] [rbp+8h] BYREF
  unsigned int *v9; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v4 = (_DWORD *)((char *)this + 8);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::GetImpl'::`2'::impl) )
  {
    while ( 1 )
    {
      CSyncReadWrite::SyncRead((CWaitThreadList *)((char *)this + 8));
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
      if ( !*v4 )
        break;
      LeaveCriticalSection(v5);
    }
    _InterlockedIncrement((volatile signed __int32 *)this + 4);
    LeaveCriticalSection(v5);
  }
  else
  {
    while ( 1 )
    {
      if ( *v4 )
        CSyncReadWrite::SyncRead((CWaitThreadList *)((char *)this + 8));
      _InterlockedIncrement((volatile signed __int32 *)this + 4);
      if ( !*v4 )
        break;
      CSyncReadWrite::SyncReadDecrement((CWaitThreadList *)((char *)this + 8));
    }
  }
  if ( (unsigned int)TKeyedLiteSList<unsigned long,CThreadSmartWait,TPointer<CThreadSmartWait>>::LookupByKey(
                       this,
                       &CurrentThreadId,
                       &v9) )
  {
    v6 = v9;
    v9[8] += a2;
    v7 = v6[8];
    if ( v7 >= *((_DWORD *)&CThreadSmartWait::m_sdwSleep + v6[4]) )
    {
      v6[5] += v7;
      v6[8] = 0;
    }
  }
  CSyncReadWrite::ReleaseReadAccess((CWaitThreadList *)((char *)this + 8));
}

```

## disassembly

```asm
0x140050024  push    rbp
0x140050026  push    rsi
0x140050027  push    rdi
0x140050028  sub     rsp, 30h
0x14005002c  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x140050035  mov     [rsp+48h+arg_8], rbx
0x14005003a  mov     ebp, edx
0x14005003c  mov     rsi, rcx
0x14005003f  mov     [rsp+48h+arg_10], 0
0x140050048  call    cs:__imp_GetCurrentThreadId
0x14005004e  mov     [rsp+48h+arg_0], eax
0x140050052  lea     rbx, [rsi+8]
0x140050056  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix> `wil::Feature<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::GetImpl(void)'::`2'::impl
0x14005005d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::__private_IsEnabled(void)
0x140050062  test    al, al
0x140050064  jz      loc_1400500EC
0x14005006a  lea     rdi, [rbx+38h]
0x14005006e  mov     rcx, rbx; this
0x140050071  call    ?SyncRead@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::SyncRead(void)
0x140050076  mov     rcx, rdi; lpCriticalSection
0x140050079  call    cs:__imp_EnterCriticalSection
0x14005007f  mov     rcx, rdi; lpCriticalSection
0x140050082  cmp     dword ptr [rbx], 0
0x140050085  jz      short loc_14005008F
0x140050087  call    cs:__imp_LeaveCriticalSection
0x14005008d  jmp     short loc_14005006E
0x14005008f  lock inc dword ptr [rbx+8]
0x140050093  call    cs:__imp_LeaveCriticalSection
0x140050099  lea     r8, [rsp+48h+arg_10]
0x14005009e  lea     rdx, [rsp+48h+arg_0]
0x1400500a3  mov     rcx, rsi
0x1400500a6  call    ?LookupByKey@?$TKeyedLiteSList@KVCThreadSmartWait@@V?$TPointer@VCThreadSmartWait@@@@@@QEAAHPEBKPEAPEAVCThreadSmartWait@@@Z; TKeyedLiteSList<ulong,CThreadSmartWait,TPointer<CThreadSmartWait>>::LookupByKey(ulong const *,CThreadSmartWait * *)
0x1400500ab  test    eax, eax
0x1400500ad  jz      short loc_1400500D6
0x1400500af  mov     rdx, [rsp+48h+arg_10]
0x1400500b4  add     [rdx+20h], ebp
0x1400500b7  mov     r8d, [rdx+20h]
0x1400500bb  mov     ecx, [rdx+10h]
0x1400500be  lea     rax, ?m_sdwSleep@CThreadSmartWait@@1PAKA; ulong near * CThreadSmartWait::m_sdwSleep
0x1400500c5  cmp     r8d, [rax+rcx*4]
0x1400500c9  jb      short loc_1400500D6
0x1400500cb  add     [rdx+14h], r8d
0x1400500cf  mov     dword ptr [rdx+20h], 0
0x1400500d6  mov     rcx, rbx; this
0x1400500d9  call    ?ReleaseReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseReadAccess(void)
0x1400500de  nop
0x1400500df  mov     rbx, [rsp+48h+arg_8]
0x1400500e4  add     rsp, 30h
0x1400500e8  pop     rdi
0x1400500e9  pop     rsi
0x1400500ea  pop     rbp
0x1400500eb  retn
0x1400500ec  cmp     dword ptr [rbx], 0
0x1400500ef  jz      short loc_1400500F9
0x1400500f1  mov     rcx, rbx; this
0x1400500f4  call    ?SyncRead@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::SyncRead(void)
0x1400500f9  lock inc dword ptr [rbx+8]
0x1400500fd  cmp     dword ptr [rbx], 0
0x140050100  jz      short loc_140050099
0x140050102  mov     rcx, rbx; this
0x140050105  call    ?SyncReadDecrement@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::SyncReadDecrement(void)
0x14005010a  jmp     short loc_1400500EC
```
