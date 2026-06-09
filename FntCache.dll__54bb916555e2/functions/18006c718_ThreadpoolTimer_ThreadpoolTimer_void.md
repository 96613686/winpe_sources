# ThreadpoolTimer::~ThreadpoolTimer(void)

- ea: `0x18006c718`
- end: `0x18006c74f`
- name: `??1ThreadpoolTimer@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ThreadpoolTimer *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18006c558`
- `0x18006dce0`
- `0x18006dd6c`
- `0x1800a6b7c`

## callees

- `0x18006c718`
- `0x18006d3bc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006c748`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006c73a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006c73a`

## pseudocode

```c
void __fastcall ThreadpoolTimer::~ThreadpoolTimer(ThreadpoolTimer *this)
{
  if ( *(_QWORD *)this )
  {
    ThreadpoolTimer::Stop(this);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)this, 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)this);
  }
}

```

## disassembly

```asm
0x18006c718  push    rbx
0x18006c71a  sub     rsp, 20h
0x18006c71e  cmp     qword ptr [rcx], 0
0x18006c722  mov     rbx, rcx
0x18006c725  jnz     short loc_18006C72D
0x18006c727  add     rsp, 20h
0x18006c72b  pop     rbx
0x18006c72c  retn
0x18006c72d  call    ?Stop@ThreadpoolTimer@@QEAAXXZ; ThreadpoolTimer::Stop(void)
0x18006c732  mov     rcx, [rbx]; pti
0x18006c735  mov     edx, 1; fCancelPendingCallbacks
0x18006c73a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006c740  mov     rcx, [rbx]
0x18006c743  add     rsp, 20h
0x18006c747  pop     rbx
0x18006c748  jmp     cs:__imp_CloseThreadpoolTimer
```
