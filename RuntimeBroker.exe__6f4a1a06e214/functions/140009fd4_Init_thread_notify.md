# _Init_thread_notify

- ea: `0x140009fd4`
- end: `0x14000a013`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009f00`

## callees

- `0x140009fd4`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000a00c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140009ffb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140009ffb`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_140018488 )
    return qword_140018488(&qword_140018448);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x140009fd4  sub     rsp, 28h
0x140009fd8  mov     rax, cs:qword_140018488
0x140009fdf  test    rax, rax
0x140009fe2  jz      short loc_140009FF4
0x140009fe4  lea     rcx, qword_140018448
0x140009feb  add     rsp, 28h
0x140009fef  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140009ff4  mov     rcx, cs:hHandle; hEvent
0x140009ffb  call    cs:__imp_SetEvent
0x14000a001  mov     rcx, cs:hHandle
0x14000a008  add     rsp, 28h
0x14000a00c  jmp     cs:__imp_ResetEvent
```
