# _Init_thread_notify

- ea: `0x140003224`
- end: `0x140003263`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003150`

## callees

- `0x140003224`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000324b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000324b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000325c`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_140050338 )
    return qword_140050338(&unk_1400502F8);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x140003224  sub     rsp, 28h
0x140003228  mov     rax, cs:qword_140050338
0x14000322f  test    rax, rax
0x140003232  jz      short loc_140003244
0x140003234  lea     rcx, unk_1400502F8
0x14000323b  add     rsp, 28h
0x14000323f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140003244  mov     rcx, cs:hHandle; hEvent
0x14000324b  call    cs:__imp_SetEvent
0x140003251  mov     rcx, cs:hHandle
0x140003258  add     rsp, 28h
0x14000325c  jmp     cs:__imp_ResetEvent
```
