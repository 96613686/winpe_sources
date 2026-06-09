# _Init_thread_notify

- ea: `0x180003fb0`
- end: `0x180003fef`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ea0`
- `0x180003edc`

## callees

- `0x180003fb0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003fd7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003fd7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003fe8`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_18002D858 )
    return qword_18002D858(&qword_18002D818);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180003fb0  sub     rsp, 28h
0x180003fb4  mov     rax, cs:qword_18002D858
0x180003fbb  test    rax, rax
0x180003fbe  jz      short loc_180003FD0
0x180003fc0  lea     rcx, qword_18002D818
0x180003fc7  add     rsp, 28h
0x180003fcb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd0  mov     rcx, cs:hHandle; hEvent
0x180003fd7  call    cs:__imp_SetEvent
0x180003fdd  mov     rcx, cs:hHandle
0x180003fe4  add     rsp, 28h
0x180003fe8  jmp     cs:__imp_ResetEvent
```
