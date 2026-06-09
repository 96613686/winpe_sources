# _Init_thread_notify

- ea: `0x180003430`
- end: `0x18000346f`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003320`
- `0x18000335c`

## callees

- `0x180003430`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003468`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003457`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003457`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180059C48 )
    return qword_180059C48(&qword_180059C08);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180003430  sub     rsp, 28h
0x180003434  mov     rax, cs:qword_180059C48
0x18000343b  test    rax, rax
0x18000343e  jz      short loc_180003450
0x180003440  lea     rcx, qword_180059C08
0x180003447  add     rsp, 28h
0x18000344b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003450  mov     rcx, cs:hHandle; hEvent
0x180003457  call    cs:__imp_SetEvent
0x18000345d  mov     rcx, cs:hHandle
0x180003464  add     rsp, 28h
0x180003468  jmp     cs:__imp_ResetEvent
```
