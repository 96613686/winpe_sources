# ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)

- ea: `0x180007c2c`
- end: `0x180007c68`
- name: `?ResetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ`
- size: `60`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800076b4`

## callees

- `0x180007c2c`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x180007c42`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180007c42`

## pseudocode

```c
_BOOL8 ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)
{
  BOOL v0; // eax

  if ( !ALLOC_CACHE_HANDLER::sm_hTimer )
    return 1;
  v0 = DeleteTimerQueueTimer(0, ALLOC_CACHE_HANDLER::sm_hTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  ALLOC_CACHE_HANDLER::sm_hTimer = 0;
  return v0;
}

```

## disassembly

```asm
0x180007c2c  sub     rsp, 28h
0x180007c30  mov     rdx, cs:?sm_hTimer@ALLOC_CACHE_HANDLER@@0PEAXEA; Timer
0x180007c37  test    rdx, rdx
0x180007c3a  jz      short loc_180007C5E
0x180007c3c  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180007c40  xor     ecx, ecx; TimerQueue
0x180007c42  call    cs:__imp_DeleteTimerQueueTimer
0x180007c48  xor     ecx, ecx
0x180007c4a  mov     cs:?sm_hTimer@ALLOC_CACHE_HANDLER@@0PEAXEA, 0; void * ALLOC_CACHE_HANDLER::sm_hTimer
0x180007c55  test    eax, eax
0x180007c57  setnz   cl
0x180007c5a  mov     eax, ecx
0x180007c5c  jmp     short loc_180007C63
0x180007c5e  mov     eax, 1
0x180007c63  add     rsp, 28h
0x180007c67  retn
```
