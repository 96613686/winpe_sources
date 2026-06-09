# AtmosCheck::CancelGracePeriodTimer(void)

- ea: `0x1801563a4`
- end: `0x18015642d`
- name: `?CancelGracePeriodTimer@AtmosCheck@@AEAAXXZ`
- size: `137`
- prototype: `void __fastcall(AtmosCheck *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180157fa4`

## callees

- `0x1801563a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801563bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801563bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801563dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801563dd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18015640e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18015640e`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1801563eb`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1801563eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180156400`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180156400`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180156417`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180156417`

## pseudocode

```c
void __fastcall AtmosCheck::CancelGracePeriodTimer(AtmosCheck *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct _TP_TIMER *v3; // rdi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 26);
  *((_QWORD *)this + 26) = 0;
  if ( v1 )
    LeaveCriticalSection(v1);
  if ( v3 )
  {
    if ( IsThreadpoolTimerSet(v3) )
    {
      SetThreadpoolTimer(v3, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v3, 1);
    }
    CloseThreadpoolTimer(v3);
  }
}

```

## disassembly

```asm
0x1801563a4  mov     [rsp+arg_0], rbx
0x1801563a9  mov     [rsp+arg_8], rsi
0x1801563ae  push    rdi
0x1801563af  sub     rsp, 20h
0x1801563b3  lea     rsi, [rcx+38h]
0x1801563b7  mov     rbx, rcx
0x1801563ba  mov     rcx, rsi; lpCriticalSection
0x1801563bd  call    cs:__imp_EnterCriticalSection
0x1801563c3  mov     rdi, [rbx+0D0h]
0x1801563ca  mov     qword ptr [rbx+0D0h], 0
0x1801563d5  test    rsi, rsi
0x1801563d8  jz      short loc_1801563E3
0x1801563da  mov     rcx, rsi; lpCriticalSection
0x1801563dd  call    cs:__imp_LeaveCriticalSection
0x1801563e3  test    rdi, rdi
0x1801563e6  jz      short loc_18015641D
0x1801563e8  mov     rcx, rdi; pti
0x1801563eb  call    cs:__imp_IsThreadpoolTimerSet
0x1801563f1  test    eax, eax
0x1801563f3  jz      short loc_180156414
0x1801563f5  xor     r9d, r9d; msWindowLength
0x1801563f8  xor     r8d, r8d; msPeriod
0x1801563fb  xor     edx, edx; pftDueTime
0x1801563fd  mov     rcx, rdi; pti
0x180156400  call    cs:__imp_SetThreadpoolTimer
0x180156406  mov     edx, 1; fCancelPendingCallbacks
0x18015640b  mov     rcx, rdi; pti
0x18015640e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180156414  mov     rcx, rdi; pti
0x180156417  call    cs:__imp_CloseThreadpoolTimer
0x18015641d  mov     rbx, [rsp+28h+arg_0]
0x180156422  mov     rsi, [rsp+28h+arg_8]
0x180156427  add     rsp, 20h
0x18015642b  pop     rdi
0x18015642c  retn
```
