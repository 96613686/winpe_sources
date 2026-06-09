# _Init_thread_notify

- ea: `0x140003814`
- end: `0x140003853`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003740`

## callees

- `0x140003814`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000383b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000383b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000384c`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_1400255B8 )
    return qword_1400255B8(&qword_140025578);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x140003814  sub     rsp, 28h
0x140003818  mov     rax, cs:qword_1400255B8
0x14000381f  test    rax, rax
0x140003822  jz      short loc_140003834
0x140003824  lea     rcx, qword_140025578
0x14000382b  add     rsp, 28h
0x14000382f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140003834  mov     rcx, cs:hHandle; hEvent
0x14000383b  call    cs:__imp_SetEvent
0x140003841  mov     rcx, cs:hHandle
0x140003848  add     rsp, 28h
0x14000384c  jmp     cs:__imp_ResetEvent
```
