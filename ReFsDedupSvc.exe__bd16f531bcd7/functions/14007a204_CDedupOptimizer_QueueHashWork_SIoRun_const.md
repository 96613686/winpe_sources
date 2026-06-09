# CDedupOptimizer::QueueHashWork(SIoRun * const)

- ea: `0x14007a204`
- end: `0x14007a2b2`
- name: `?QueueHashWork@CDedupOptimizer@@AEAAXQEAUSIoRun@@@Z`
- size: `174`
- prototype: `void __fastcall(PVOID pv, struct SIoRun *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14007a2c0`

## callees

- `0x14000dea0`
- `0x1400635dc`
- `0x1400747b4`
- `0x14007a204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14007a220`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14007a220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a26f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007a26f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14007a29a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14007a29a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14007a25e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14007a25e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDedupOptimizer::QueueHashWork(char *pv, struct SIoRun *const a2)
{
  char *v3; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct SIoRun *v5; // [rsp+30h] [rbp+8h] BYREF
  char *v6; // [rsp+38h] [rbp+10h] BYREF

  v5 = a2;
  v3 = pv + 736;
  AcquireSRWLockExclusive((PSRWLOCK)pv + 92);
  v6 = v3;
  std::deque<SIoRun *>::_Emplace_back_internal<SIoRun * const &>(pv + 744, &v5);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  ThreadpoolWork = CreateThreadpoolWork(CDedupOptimizer::HashWorkCallback, pv, (PTP_CALLBACK_ENVIRON)(pv + 312));
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
  }
  else
  {
    LODWORD(v5) = GetLastError();
    DedupUtil::Print<unsigned long &>(6, L"Unable to queue hash callback, error = 0x%x\n", &v5);
  }
}

```

## disassembly

```asm
0x14007a204  mov     [rsp+arg_10], rbx
0x14007a209  push    rdi
0x14007a20a  sub     rsp, 20h
0x14007a20e  mov     rdi, rcx
0x14007a211  mov     [rsp+28h+arg_0], rdx
0x14007a216  lea     rbx, [rcx+2E0h]
0x14007a21d  mov     rcx, rbx; SRWLock
0x14007a220  call    cs:__imp_AcquireSRWLockExclusive
0x14007a227  nop     dword ptr [rax+rax+00h]
0x14007a22c  mov     [rsp+28h+arg_8], rbx
0x14007a231  lea     rcx, [rdi+2E8h]
0x14007a238  lea     rdx, [rsp+28h+arg_0]
0x14007a23d  call    ??$_Emplace_back_internal@AEBQEAUSIoRun@@@?$deque@PEAUSIoRun@@V?$allocator@PEAUSIoRun@@@std@@@std@@AEAAXAEBQEAUSIoRun@@@Z; std::deque<SIoRun *>::_Emplace_back_internal<SIoRun * const &>(SIoRun * const &)
0x14007a242  nop
0x14007a243  lea     rcx, [rsp+28h+arg_8]
0x14007a248  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14007a24d  lea     r8, [rdi+138h]; pcbe
0x14007a254  mov     rdx, rdi; pv
0x14007a257  lea     rcx, ?HashWorkCallback@CDedupOptimizer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14007a25e  call    cs:__imp_CreateThreadpoolWork
0x14007a265  nop     dword ptr [rax+rax+00h]
0x14007a26a  test    rax, rax
0x14007a26d  jnz     short loc_14007A297
0x14007a26f  call    cs:__imp_GetLastError
0x14007a276  nop     dword ptr [rax+rax+00h]
0x14007a27b  mov     dword ptr [rsp+28h+arg_0], eax
0x14007a27f  lea     r8, [rsp+28h+arg_0]
0x14007a284  lea     rdx, aUnableToQueueH; "Unable to queue hash callback, error = "...
0x14007a28b  mov     ecx, 6
0x14007a290  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x14007a295  jmp     short loc_14007A2A6
0x14007a297  mov     rcx, rax; pwk
0x14007a29a  call    cs:__imp_SubmitThreadpoolWork
0x14007a2a1  nop     dword ptr [rax+rax+00h]
0x14007a2a6  mov     rbx, [rsp+28h+arg_10]
0x14007a2ab  add     rsp, 20h
0x14007a2af  pop     rdi
0x14007a2b0  retn
```
