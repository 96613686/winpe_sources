# AutoLockWithWatchdog::~AutoLockWithWatchdog(void)

- ea: `0x18001f514`
- end: `0x18001f593`
- name: `??1AutoLockWithWatchdog@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(LPCRITICAL_SECTION *this)`
- caller_count: `126`
- callee_count: `2`
- tags: ``

## callers

- `0x1800211b0`
- `0x180021a30`
- `0x180021b20`
- `0x1800222c0`
- `0x1800224d0`
- `0x1800225e0`
- `0x180022720`
- `0x1800227c0`
- `0x180022980`
- `0x180022b10`
- `0x180022c90`
- `0x180022ee0`
- `0x180022f70`
- `0x1800233e0`
- `0x180023670`
- `0x180024100`
- `0x180024230`
- `0x180024de0`
- `0x180024ef0`
- `0x180025920`
- `0x180025a10`
- `0x180025b90`
- `0x1800265e0`
- `0x180026770`
- `0x180026910`
- `0x180026d80`
- `0x180026e20`
- `0x1800273e0`
- `0x1800275e0`
- `0x1800276c0`
- `0x180027840`
- `0x180027e70`
- `0x180027f90`
- `0x1800281d0`
- `0x180028290`
- `0x180028500`
- `0x1800285a0`
- `0x180028760`
- `0x180028aa0`
- `0x180028b20`
- `0x180028ca0`
- `0x180028e00`
- `0x180029180`
- `0x180029390`
- `0x180029570`
- `0x180029990`
- `0x180029bc0`
- `0x180029ca0`
- `0x180029d30`
- `0x180029e40`

## callees

- `0x18001f514`
- `0x180025ae4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f530`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f530`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f551`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f56b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f56b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f582`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f582`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f579`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f579`

## pseudocode

```c
void __fastcall AutoLockWithWatchdog::~AutoLockWithWatchdog(LPCRITICAL_SECTION *this)
{
  struct _TP_TIMER **v1; // rdi
  struct _TP_TIMER *v3; // rcx
  struct _TP_TIMER *v4; // rbx

  v1 = (struct _TP_TIMER **)(this + 1);
  OperationWatchdog::End((OperationWatchdog *)(this + 1));
  LeaveCriticalSection(*this);
  *v1 = (struct _TP_TIMER *)&OperationWatchdog::`vftable';
  OperationWatchdog::End((OperationWatchdog *)v1);
  v3 = v1[4];
  if ( v3 )
    LocalFree(v3);
  v4 = v1[2];
  if ( v4 )
  {
    SetThreadpoolTimer(v1[2], 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
  }
}

```

## disassembly

```asm
0x18001f514  mov     [rsp+arg_0], rbx
0x18001f519  push    rdi
0x18001f51a  sub     rsp, 20h
0x18001f51e  lea     rdi, [rcx+8]
0x18001f522  mov     rbx, rcx
0x18001f525  mov     rcx, rdi; this
0x18001f528  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x18001f52d  mov     rcx, [rbx]; lpCriticalSection
0x18001f530  call    cs:__imp_LeaveCriticalSection
0x18001f536  lea     rax, ??_7OperationWatchdog@@6B@; const OperationWatchdog::`vftable'
0x18001f53d  mov     rcx, rdi; this
0x18001f540  mov     [rdi], rax
0x18001f543  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x18001f548  mov     rcx, [rdi+20h]; hMem
0x18001f54c  test    rcx, rcx
0x18001f54f  jz      short loc_18001F557
0x18001f551  call    cs:__imp_LocalFree
0x18001f557  mov     rbx, [rdi+10h]
0x18001f55b  test    rbx, rbx
0x18001f55e  jz      short loc_18001F588
0x18001f560  xor     r9d, r9d; msWindowLength
0x18001f563  xor     r8d, r8d; msPeriod
0x18001f566  xor     edx, edx; pftDueTime
0x18001f568  mov     rcx, rbx; pti
0x18001f56b  call    cs:__imp_SetThreadpoolTimer
0x18001f571  mov     edx, 1; fCancelPendingCallbacks
0x18001f576  mov     rcx, rbx; pti
0x18001f579  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001f57f  mov     rcx, rbx; pti
0x18001f582  call    cs:__imp_CloseThreadpoolTimer
0x18001f588  mov     rbx, [rsp+28h+arg_0]
0x18001f58d  add     rsp, 20h
0x18001f591  pop     rdi
0x18001f592  retn
```
