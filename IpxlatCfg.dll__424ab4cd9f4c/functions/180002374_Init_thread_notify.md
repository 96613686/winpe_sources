# _Init_thread_notify

- ea: `0x180002374`
- end: `0x1800023b3`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022a0`

## callees

- `0x180002374`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800023ac`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000239b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000239b`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180023558 )
    return qword_180023558(&qword_180023518);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002374  sub     rsp, 28h
0x180002378  mov     rax, cs:qword_180023558
0x18000237f  test    rax, rax
0x180002382  jz      short loc_180002394
0x180002384  lea     rcx, qword_180023518
0x18000238b  add     rsp, 28h
0x18000238f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002394  mov     rcx, cs:hHandle; hEvent
0x18000239b  call    cs:__imp_SetEvent
0x1800023a1  mov     rcx, cs:hHandle
0x1800023a8  add     rsp, 28h
0x1800023ac  jmp     cs:__imp_ResetEvent
```
