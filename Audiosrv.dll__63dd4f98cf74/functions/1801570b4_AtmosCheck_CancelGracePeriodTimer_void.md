# AtmosCheck::CancelGracePeriodTimer(void)

- ea: `0x1801570b4`
- end: `0x18015713d`
- name: `?CancelGracePeriodTimer@AtmosCheck@@AEAAXXZ`
- size: `137`
- prototype: `void __fastcall(AtmosCheck *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180158cb4`

## callees

- `0x1801570b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801570cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801570cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801570ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801570ed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18015711e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18015711e`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1801570fb`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1801570fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180157110`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180157110`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180157127`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180157127`

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
0x1801570b4  mov     [rsp+arg_0], rbx
0x1801570b9  mov     [rsp+arg_8], rsi
0x1801570be  push    rdi
0x1801570bf  sub     rsp, 20h
0x1801570c3  lea     rsi, [rcx+38h]
0x1801570c7  mov     rbx, rcx
0x1801570ca  mov     rcx, rsi; lpCriticalSection
0x1801570cd  call    cs:__imp_EnterCriticalSection
0x1801570d3  mov     rdi, [rbx+0D0h]
0x1801570da  mov     qword ptr [rbx+0D0h], 0
0x1801570e5  test    rsi, rsi
0x1801570e8  jz      short loc_1801570F3
0x1801570ea  mov     rcx, rsi; lpCriticalSection
0x1801570ed  call    cs:__imp_LeaveCriticalSection
0x1801570f3  test    rdi, rdi
0x1801570f6  jz      short loc_18015712D
0x1801570f8  mov     rcx, rdi; pti
0x1801570fb  call    cs:__imp_IsThreadpoolTimerSet
0x180157101  test    eax, eax
0x180157103  jz      short loc_180157124
0x180157105  xor     r9d, r9d; msWindowLength
0x180157108  xor     r8d, r8d; msPeriod
0x18015710b  xor     edx, edx; pftDueTime
0x18015710d  mov     rcx, rdi; pti
0x180157110  call    cs:__imp_SetThreadpoolTimer
0x180157116  mov     edx, 1; fCancelPendingCallbacks
0x18015711b  mov     rcx, rdi; pti
0x18015711e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180157124  mov     rcx, rdi; pti
0x180157127  call    cs:__imp_CloseThreadpoolTimer
0x18015712d  mov     rbx, [rsp+28h+arg_0]
0x180157132  mov     rsi, [rsp+28h+arg_8]
0x180157137  add     rsp, 20h
0x18015713b  pop     rdi
0x18015713c  retn
```
