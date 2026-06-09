# DiagHubCommon::ThreadpoolTimerHelper::~ThreadpoolTimerHelper(void)

- ea: `0x140002368`
- end: `0x1400023be`
- name: `??1ThreadpoolTimerHelper@DiagHubCommon@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(DiagHubCommon::ThreadpoolTimerHelper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014f02`

## callees

- `0x140002368`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x1400023ab`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400023ab`
- `KERNEL32!IsThreadpoolTimerSet` at `0x14000237f`
- `KERNEL32!IsThreadpoolTimerSet` at `0x14000237f`
- `KERNEL32!SetThreadpoolTimer` at `0x140002394`
- `KERNEL32!SetThreadpoolTimer` at `0x140002394`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400023a2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400023a2`

## pseudocode

```c
void __fastcall DiagHubCommon::ThreadpoolTimerHelper::~ThreadpoolTimerHelper(PTP_TIMER *this)
{
  struct _TP_TIMER *v2; // rcx

  if ( *((_BYTE *)this + 8) )
  {
    v2 = *this;
    if ( v2 )
    {
      if ( IsThreadpoolTimerSet(v2) )
      {
        SetThreadpoolTimer(*this, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(*this, 1);
      }
      CloseThreadpoolTimer(*this);
      *this = 0;
    }
  }
}

```

## disassembly

```asm
0x140002368  push    rbx
0x14000236a  sub     rsp, 20h
0x14000236e  cmp     byte ptr [rcx+8], 0
0x140002372  mov     rbx, rcx
0x140002375  jz      short loc_1400023B8
0x140002377  mov     rcx, [rcx]; pti
0x14000237a  test    rcx, rcx
0x14000237d  jz      short loc_1400023B8
0x14000237f  call    cs:__imp_IsThreadpoolTimerSet
0x140002385  test    eax, eax
0x140002387  jz      short loc_1400023A8
0x140002389  mov     rcx, [rbx]; pti
0x14000238c  xor     r9d, r9d; msWindowLength
0x14000238f  xor     r8d, r8d; msPeriod
0x140002392  xor     edx, edx; pftDueTime
0x140002394  call    cs:__imp_SetThreadpoolTimer
0x14000239a  mov     rcx, [rbx]; pti
0x14000239d  mov     edx, 1; fCancelPendingCallbacks
0x1400023a2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400023a8  mov     rcx, [rbx]; pti
0x1400023ab  call    cs:__imp_CloseThreadpoolTimer
0x1400023b1  mov     qword ptr [rbx], 0
0x1400023b8  add     rsp, 20h
0x1400023bc  pop     rbx
0x1400023bd  retn
```
