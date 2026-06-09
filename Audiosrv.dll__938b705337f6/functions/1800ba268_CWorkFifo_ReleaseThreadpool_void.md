# CWorkFifo::ReleaseThreadpool(void)

- ea: `0x1800ba268`
- end: `0x1800ba2f0`
- name: `?ReleaseThreadpool@CWorkFifo@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(CWorkFifo *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800ba230`
- `0x18012fb00`

## callees

- `0x1800ba268`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ba2c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ba2c2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ba29b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ba29b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800ba2b8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800ba2b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ba28d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ba28d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800ba2d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800ba2d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ba2a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ba2a4`

## pseudocode

```c
void __fastcall CWorkFifo::ReleaseThreadpool(CWorkFifo *this)
{
  struct _TP_TIMER *v2; // rbx
  struct _TP_WORK *v3; // rcx

  if ( *((_QWORD *)this + 1) )
  {
    v2 = (struct _TP_TIMER *)_InterlockedExchange64((volatile __int64 *)this + 1, 0);
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
  }
  v3 = (struct _TP_WORK *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    WaitForThreadpoolWorkCallbacks(v3, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  if ( *(_QWORD *)this )
  {
    CloseThreadpool(*(PTP_POOL *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800ba268  mov     [rsp+arg_0], rbx
0x1800ba26d  push    rdi
0x1800ba26e  sub     rsp, 20h
0x1800ba272  cmp     qword ptr [rcx+8], 0
0x1800ba277  mov     rdi, rcx
0x1800ba27a  jz      short loc_1800BA2AA
0x1800ba27c  xor     ebx, ebx
0x1800ba27e  xor     r9d, r9d; msWindowLength
0x1800ba281  xchg    rbx, [rcx+8]
0x1800ba285  mov     rcx, rbx; pti
0x1800ba288  xor     r8d, r8d; msPeriod
0x1800ba28b  xor     edx, edx; pftDueTime
0x1800ba28d  call    cs:__imp_SetThreadpoolTimer
0x1800ba293  mov     edx, 1; fCancelPendingCallbacks
0x1800ba298  mov     rcx, rbx; pti
0x1800ba29b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800ba2a1  mov     rcx, rbx; pti
0x1800ba2a4  call    cs:__imp_CloseThreadpoolTimer
0x1800ba2aa  mov     rcx, [rdi+10h]; pwk
0x1800ba2ae  test    rcx, rcx
0x1800ba2b1  jz      short loc_1800BA2D0
0x1800ba2b3  mov     edx, 1; fCancelPendingCallbacks
0x1800ba2b8  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800ba2be  mov     rcx, [rdi+10h]; pwk
0x1800ba2c2  call    cs:__imp_CloseThreadpoolWork
0x1800ba2c8  mov     qword ptr [rdi+10h], 0
0x1800ba2d0  mov     rcx, [rdi]; ptpp
0x1800ba2d3  test    rcx, rcx
0x1800ba2d6  jz      short loc_1800BA2E5
0x1800ba2d8  call    cs:__imp_CloseThreadpool
0x1800ba2de  mov     qword ptr [rdi], 0
0x1800ba2e5  mov     rbx, [rsp+28h+arg_0]
0x1800ba2ea  add     rsp, 20h
0x1800ba2ee  pop     rdi
0x1800ba2ef  retn
```
