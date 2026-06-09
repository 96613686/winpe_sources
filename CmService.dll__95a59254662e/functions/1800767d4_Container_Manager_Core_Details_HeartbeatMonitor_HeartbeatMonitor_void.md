# Container::Manager::Core::Details::HeartbeatMonitor::~HeartbeatMonitor(void)

- ea: `0x1800767d4`
- end: `0x180076910`
- name: `??1HeartbeatMonitor@Details@Core@Manager@Container@@QEAA@XZ`
- size: `316`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800764b0`

## callees

- `0x1800471dc`
- `0x1800767d4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180076852`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800768f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180076852`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800768f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007687d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007687d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007682c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007682c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800768a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800768dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800768a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800768dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800767f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800767f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076817`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076892`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180076860`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800768b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180076860`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800768b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800767fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800767fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Core::Details::HeartbeatMonitor::~HeartbeatMonitor(PSRWLOCK SRWLock)
{
  struct _TP_TIMER *Ptr; // rsi
  DWORD LastError; // ebx
  struct _TP_WORK *v4; // rsi
  DWORD v5; // ebx
  utl::_RefCountBase *v6; // rcx
  struct _TP_WORK *v7; // rcx
  struct _TP_TIMER *v8; // rcx

  if ( SRWLock[6].Ptr )
  {
    AcquireSRWLockExclusive(SRWLock);
    GetCurrentThreadId();
    LODWORD(SRWLock[2].Ptr) |= 4u;
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(SRWLock);
    WaitForThreadpoolTimerCallbacks((PTP_TIMER)SRWLock[6].Ptr, 1);
    Ptr = (struct _TP_TIMER *)SRWLock[6].Ptr;
    if ( Ptr )
    {
      LastError = GetLastError();
      CloseThreadpoolTimer(Ptr);
      SetLastError(LastError);
    }
    SRWLock[6].Ptr = 0;
    WaitForThreadpoolWorkCallbacks((PTP_WORK)SRWLock[9].Ptr, 1);
    v4 = (struct _TP_WORK *)SRWLock[9].Ptr;
    if ( v4 )
    {
      v5 = GetLastError();
      CloseThreadpoolWork(v4);
      SetLastError(v5);
    }
    SRWLock[9].Ptr = 0;
  }
  v6 = (utl::_RefCountBase *)SRWLock[11].Ptr;
  if ( v6 )
    utl::_RefCountBase::_DecStrong(v6);
  v7 = (struct _TP_WORK *)SRWLock[9].Ptr;
  if ( v7 )
    CloseThreadpoolWork(v7);
  v8 = (struct _TP_TIMER *)SRWLock[6].Ptr;
  if ( v8 )
    CloseThreadpoolTimer(v8);
}

```

## disassembly

```asm
0x1800767d4  mov     [rsp+arg_8], rbx
0x1800767d9  mov     [rsp+arg_10], rsi
0x1800767de  push    rdi
0x1800767df  sub     rsp, 20h
0x1800767e3  mov     rdi, rcx
0x1800767e6  cmp     qword ptr [rcx+30h], 0
0x1800767eb  jz      loc_1800768C5
0x1800767f1  call    cs:__imp_AcquireSRWLockExclusive
0x1800767f8  nop     dword ptr [rax+rax+00h]
0x1800767fd  call    cs:__imp_GetCurrentThreadId
0x180076804  nop     dword ptr [rax+rax+00h]
0x180076809  or      dword ptr [rdi+10h], 4
0x18007680d  mov     dword ptr [rdi+8], 0
0x180076814  mov     rcx, rdi; SRWLock
0x180076817  call    cs:__imp_ReleaseSRWLockExclusive
0x18007681e  nop     dword ptr [rax+rax+00h]
0x180076823  mov     edx, 1; fCancelPendingCallbacks
0x180076828  mov     rcx, [rdi+30h]; pti
0x18007682c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180076833  nop     dword ptr [rax+rax+00h]
0x180076838  mov     rsi, [rdi+30h]
0x18007683c  test    rsi, rsi
0x18007683f  jz      short loc_18007686C
0x180076841  call    cs:__imp_GetLastError
0x180076848  nop     dword ptr [rax+rax+00h]
0x18007684d  mov     ebx, eax
0x18007684f  mov     rcx, rsi; pti
0x180076852  call    cs:__imp_CloseThreadpoolTimer
0x180076859  nop     dword ptr [rax+rax+00h]
0x18007685e  mov     ecx, ebx; dwErrCode
0x180076860  call    cs:__imp_SetLastError
0x180076867  nop     dword ptr [rax+rax+00h]
0x18007686c  mov     qword ptr [rdi+30h], 0
0x180076874  mov     edx, 1; fCancelPendingCallbacks
0x180076879  mov     rcx, [rdi+48h]; pwk
0x18007687d  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180076884  nop     dword ptr [rax+rax+00h]
0x180076889  mov     rsi, [rdi+48h]
0x18007688d  test    rsi, rsi
0x180076890  jz      short loc_1800768BD
0x180076892  call    cs:__imp_GetLastError
0x180076899  nop     dword ptr [rax+rax+00h]
0x18007689e  mov     ebx, eax
0x1800768a0  mov     rcx, rsi; pwk
0x1800768a3  call    cs:__imp_CloseThreadpoolWork
0x1800768aa  nop     dword ptr [rax+rax+00h]
0x1800768af  mov     ecx, ebx; dwErrCode
0x1800768b1  call    cs:__imp_SetLastError
0x1800768b8  nop     dword ptr [rax+rax+00h]
0x1800768bd  mov     qword ptr [rdi+48h], 0
0x1800768c5  mov     rcx, [rdi+58h]; this
0x1800768c9  test    rcx, rcx
0x1800768cc  jz      short loc_1800768D4
0x1800768ce  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800768d3  nop
0x1800768d4  mov     rcx, [rdi+48h]; pwk
0x1800768d8  test    rcx, rcx
0x1800768db  jz      short loc_1800768E9
0x1800768dd  call    cs:__imp_CloseThreadpoolWork
0x1800768e4  nop     dword ptr [rax+rax+00h]
0x1800768e9  mov     rcx, [rdi+30h]; pti
0x1800768ed  test    rcx, rcx
0x1800768f0  jz      short loc_1800768FF
0x1800768f2  call    cs:__imp_CloseThreadpoolTimer
0x1800768f9  nop     dword ptr [rax+rax+00h]
0x1800768fe  nop
0x1800768ff  mov     rbx, [rsp+28h+arg_8]
0x180076904  mov     rsi, [rsp+28h+arg_10]
0x180076909  add     rsp, 20h
0x18007690d  pop     rdi
0x18007690e  retn
```
