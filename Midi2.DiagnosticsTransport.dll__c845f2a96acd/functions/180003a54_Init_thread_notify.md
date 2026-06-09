# _Init_thread_notify

- ea: `0x180003a54`
- end: `0x180003a93`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003980`

## callees

- `0x180003a54`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003a8c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003a7b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003a7b`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_18001A498 )
    return qword_18001A498(&qword_18001A458);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180003a54  sub     rsp, 28h
0x180003a58  mov     rax, cs:qword_18001A498
0x180003a5f  test    rax, rax
0x180003a62  jz      short loc_180003A74
0x180003a64  lea     rcx, qword_18001A458
0x180003a6b  add     rsp, 28h
0x180003a6f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003a74  mov     rcx, cs:hHandle; hEvent
0x180003a7b  call    cs:__imp_SetEvent
0x180003a81  mov     rcx, cs:hHandle
0x180003a88  add     rsp, 28h
0x180003a8c  jmp     cs:__imp_ResetEvent
```
