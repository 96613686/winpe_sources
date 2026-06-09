# CWorkFifo::ReleaseThreadpool(void)

- ea: `0x1800b8718`
- end: `0x1800b87a0`
- name: `?ReleaseThreadpool@CWorkFifo@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(CWorkFifo *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b86e0`
- `0x18012fd9c`

## callees

- `0x1800b8718`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b8772`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b8772`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b874b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b874b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b8768`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b8768`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b873d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b873d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800b8788`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800b8788`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b8754`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b8754`

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
0x1800b8718  mov     [rsp+arg_0], rbx
0x1800b871d  push    rdi
0x1800b871e  sub     rsp, 20h
0x1800b8722  cmp     qword ptr [rcx+8], 0
0x1800b8727  mov     rdi, rcx
0x1800b872a  jz      short loc_1800B875A
0x1800b872c  xor     ebx, ebx
0x1800b872e  xor     r9d, r9d; msWindowLength
0x1800b8731  xchg    rbx, [rcx+8]
0x1800b8735  mov     rcx, rbx; pti
0x1800b8738  xor     r8d, r8d; msPeriod
0x1800b873b  xor     edx, edx; pftDueTime
0x1800b873d  call    cs:__imp_SetThreadpoolTimer
0x1800b8743  mov     edx, 1; fCancelPendingCallbacks
0x1800b8748  mov     rcx, rbx; pti
0x1800b874b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b8751  mov     rcx, rbx; pti
0x1800b8754  call    cs:__imp_CloseThreadpoolTimer
0x1800b875a  mov     rcx, [rdi+10h]; pwk
0x1800b875e  test    rcx, rcx
0x1800b8761  jz      short loc_1800B8780
0x1800b8763  mov     edx, 1; fCancelPendingCallbacks
0x1800b8768  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800b876e  mov     rcx, [rdi+10h]; pwk
0x1800b8772  call    cs:__imp_CloseThreadpoolWork
0x1800b8778  mov     qword ptr [rdi+10h], 0
0x1800b8780  mov     rcx, [rdi]; ptpp
0x1800b8783  test    rcx, rcx
0x1800b8786  jz      short loc_1800B8795
0x1800b8788  call    cs:__imp_CloseThreadpool
0x1800b878e  mov     qword ptr [rdi], 0
0x1800b8795  mov     rbx, [rsp+28h+arg_0]
0x1800b879a  add     rsp, 20h
0x1800b879e  pop     rdi
0x1800b879f  retn
```
