# GameInputDispatcher::IsDispatchThread(void)

- ea: `0x180008550`
- end: `0x180008575`
- name: `?IsDispatchThread@GameInputDispatcher@@SA_NXZ`
- size: `37`
- prototype: `bool(void)`
- caller_count: `10`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800059d0`
- `0x1800063a4`
- `0x180008860`
- `0x180009050`
- `0x1800094b0`
- `0x18000a7d0`
- `0x18000a91c`
- `0x18000b840`
- `0x18000bb88`
- `0x18000bc50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000855d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000855d`

## pseudocode

```c
bool GameInputDispatcher::IsDispatchThread(void)
{
  int v0; // ebx

  v0 = GameInputDispatcher::s_dispatchThreadId;
  return GetCurrentThreadId() == v0;
}

```

## disassembly

```asm
0x180008550  push    rbx
0x180008552  sub     rsp, 20h
0x180008556  mov     ebx, cs:?s_dispatchThreadId@GameInputDispatcher@@0U?$atomic@K@utl@@A; utl::atomic<ulong> GameInputDispatcher::s_dispatchThreadId
0x18000855c  nop
0x18000855d  call    cs:__imp_GetCurrentThreadId
0x180008564  nop     dword ptr [rax+rax+00h]
0x180008569  cmp     eax, ebx
0x18000856b  setz    al
0x18000856e  add     rsp, 20h
0x180008572  pop     rbx
0x180008573  retn
```
