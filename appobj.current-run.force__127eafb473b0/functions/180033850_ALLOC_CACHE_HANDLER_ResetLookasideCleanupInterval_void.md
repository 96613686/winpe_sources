# ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)

- ea: `0x180033850`
- end: `0x18003388c`
- name: `?ResetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ`
- size: `60`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180033218`

## callees

- `0x180033850`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180033866`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180033866`

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
0x180033850  sub     rsp, 28h
0x180033854  mov     rdx, cs:?sm_hTimer@ALLOC_CACHE_HANDLER@@0PEAXEA; Timer
0x18003385b  test    rdx, rdx
0x18003385e  jz      short loc_180033882
0x180033860  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180033864  xor     ecx, ecx; TimerQueue
0x180033866  call    cs:__imp_DeleteTimerQueueTimer
0x18003386c  xor     ecx, ecx
0x18003386e  mov     cs:?sm_hTimer@ALLOC_CACHE_HANDLER@@0PEAXEA, 0; void * ALLOC_CACHE_HANDLER::sm_hTimer
0x180033879  test    eax, eax
0x18003387b  setnz   cl
0x18003387e  mov     eax, ecx
0x180033880  jmp     short loc_180033887
0x180033882  mov     eax, 1
0x180033887  add     rsp, 28h
0x18003388b  retn
```
