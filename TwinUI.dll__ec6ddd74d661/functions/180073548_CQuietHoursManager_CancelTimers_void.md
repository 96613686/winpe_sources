# CQuietHoursManager::_CancelTimers(void)

- ea: `0x180073548`
- end: `0x180073622`
- name: `?_CancelTimers@CQuietHoursManager@@AEAAXXZ`
- size: `218`
- prototype: `void __fastcall(CQuietHoursManager *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180072c10`
- `0x1802d62f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073560`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073593`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800735c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800735f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073560`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180073593`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800735c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800735f9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180073578`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800735ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800735de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180073578`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800735ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800735de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180073616`

## pseudocode

```c
void __fastcall CQuietHoursManager::_CancelTimers(PTP_TIMER *this)
{
  SetThreadpoolTimer(this[25], 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(this[25], 1);
  SetThreadpoolTimer(this[26], 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(this[26], 1);
  SetThreadpoolTimer(this[27], 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(this[27], 1);
  SetThreadpoolTimer(this[28], 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(this[28], 1);
}

```

## disassembly

```asm
0x180073548  push    rbx
0x18007354a  sub     rsp, 20h
0x18007354e  mov     rbx, rcx
0x180073551  xor     r9d, r9d; msWindowLength
0x180073554  mov     rcx, [rcx+0C8h]; pti
0x18007355b  xor     r8d, r8d; msPeriod
0x18007355e  xor     edx, edx; pftDueTime
0x180073560  call    cs:__imp_SetThreadpoolTimer
0x180073567  nop     dword ptr [rax+rax+00h]
0x18007356c  mov     rcx, [rbx+0C8h]; pti
0x180073573  mov     edx, 1; fCancelPendingCallbacks
0x180073578  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007357f  nop     dword ptr [rax+rax+00h]
0x180073584  mov     rcx, [rbx+0D0h]; pti
0x18007358b  xor     r9d, r9d; msWindowLength
0x18007358e  xor     r8d, r8d; msPeriod
0x180073591  xor     edx, edx; pftDueTime
0x180073593  call    cs:__imp_SetThreadpoolTimer
0x18007359a  nop     dword ptr [rax+rax+00h]
0x18007359f  mov     rcx, [rbx+0D0h]; pti
0x1800735a6  mov     edx, 1; fCancelPendingCallbacks
0x1800735ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800735b2  nop     dword ptr [rax+rax+00h]
0x1800735b7  mov     rcx, [rbx+0D8h]; pti
0x1800735be  xor     r9d, r9d; msWindowLength
0x1800735c1  xor     r8d, r8d; msPeriod
0x1800735c4  xor     edx, edx; pftDueTime
0x1800735c6  call    cs:__imp_SetThreadpoolTimer
0x1800735cd  nop     dword ptr [rax+rax+00h]
0x1800735d2  mov     rcx, [rbx+0D8h]; pti
0x1800735d9  mov     edx, 1; fCancelPendingCallbacks
0x1800735de  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800735e5  nop     dword ptr [rax+rax+00h]
0x1800735ea  mov     rcx, [rbx+0E0h]; pti
0x1800735f1  xor     r9d, r9d; msWindowLength
0x1800735f4  xor     r8d, r8d; msPeriod
0x1800735f7  xor     edx, edx; pftDueTime
0x1800735f9  call    cs:__imp_SetThreadpoolTimer
0x180073600  nop     dword ptr [rax+rax+00h]
0x180073605  mov     rcx, [rbx+0E0h]
0x18007360c  mov     edx, 1
0x180073611  add     rsp, 20h
0x180073615  pop     rbx
0x180073616  jmp     cs:__imp_WaitForThreadpoolTimerCallbacks
```
