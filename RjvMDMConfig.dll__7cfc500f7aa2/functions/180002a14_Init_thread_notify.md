# _Init_thread_notify

- ea: `0x180002a14`
- end: `0x180002a53`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002940`

## callees

- `0x180002a14`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002a3b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002a3b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180002a4c`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_1800298C0 )
    return qword_1800298C0(&qword_180029880);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002a14  sub     rsp, 28h
0x180002a18  mov     rax, cs:qword_1800298C0
0x180002a1f  test    rax, rax
0x180002a22  jz      short loc_180002A34
0x180002a24  lea     rcx, qword_180029880
0x180002a2b  add     rsp, 28h
0x180002a2f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002a34  mov     rcx, cs:hHandle; hEvent
0x180002a3b  call    cs:__imp_SetEvent
0x180002a41  mov     rcx, cs:hHandle
0x180002a48  add     rsp, 28h
0x180002a4c  jmp     cs:__imp_ResetEvent
```
