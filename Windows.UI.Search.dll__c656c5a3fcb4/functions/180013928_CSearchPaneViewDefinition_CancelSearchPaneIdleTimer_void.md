# CSearchPaneViewDefinition::_CancelSearchPaneIdleTimer(void)

- ea: `0x180013928`
- end: `0x180013974`
- name: `?_CancelSearchPaneIdleTimer@CSearchPaneViewDefinition@@AEAAXXZ`
- size: `76`
- prototype: `void __fastcall(CSearchPaneViewDefinition *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012d24`
- `0x180014c20`

## callees

- `0x180013928`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001393d`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18001393d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013956`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013956`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013968`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013968`

## pseudocode

```c
void __fastcall CSearchPaneViewDefinition::_CancelSearchPaneIdleTimer(CSearchPaneViewDefinition *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 25);
  if ( v2 )
  {
    if ( IsThreadpoolTimerSet(v2) )
    {
      SetThreadpoolTimer(*((PTP_TIMER *)this + 25), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 25), 1);
    }
  }
}

```

## disassembly

```asm
0x180013928  push    rbx
0x18001392a  sub     rsp, 20h
0x18001392e  mov     rbx, rcx
0x180013931  mov     rcx, [rcx+0C8h]; pti
0x180013938  test    rcx, rcx
0x18001393b  jz      short loc_18001396E
0x18001393d  call    cs:__imp_IsThreadpoolTimerSet
0x180013943  test    eax, eax
0x180013945  jz      short loc_18001396E
0x180013947  mov     rcx, [rbx+0C8h]; pti
0x18001394e  xor     r9d, r9d; msWindowLength
0x180013951  xor     r8d, r8d; msPeriod
0x180013954  xor     edx, edx; pftDueTime
0x180013956  call    cs:__imp_SetThreadpoolTimer
0x18001395c  mov     rcx, [rbx+0C8h]; pti
0x180013963  mov     edx, 1; fCancelPendingCallbacks
0x180013968  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001396e  add     rsp, 20h
0x180013972  pop     rbx
0x180013973  retn
```
