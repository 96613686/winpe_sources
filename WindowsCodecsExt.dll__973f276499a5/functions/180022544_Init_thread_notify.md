# _Init_thread_notify

- ea: `0x180022544`
- end: `0x180022583`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022470`

## callees

- `0x180022544`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002257c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002256b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002256b`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180040260 )
    return qword_180040260(&unk_180040220);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180022544  sub     rsp, 28h
0x180022548  mov     rax, cs:qword_180040260
0x18002254f  test    rax, rax
0x180022552  jz      short loc_180022564
0x180022554  lea     rcx, unk_180040220
0x18002255b  add     rsp, 28h
0x18002255f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180022564  mov     rcx, cs:hHandle; hEvent
0x18002256b  call    cs:__imp_SetEvent
0x180022571  mov     rcx, cs:hHandle
0x180022578  add     rsp, 28h
0x18002257c  jmp     cs:__imp_ResetEvent
```
