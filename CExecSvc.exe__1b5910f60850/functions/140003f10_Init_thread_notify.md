# _Init_thread_notify

- ea: `0x140003f10`
- end: `0x140003f4f`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003e00`
- `0x140003e3c`

## callees

- `0x140003f10`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140003f48`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003f37`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003f37`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_140039DE8 )
    return qword_140039DE8(&qword_140039DA8);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x140003f10  sub     rsp, 28h
0x140003f14  mov     rax, cs:qword_140039DE8
0x140003f1b  test    rax, rax
0x140003f1e  jz      short loc_140003F30
0x140003f20  lea     rcx, qword_140039DA8
0x140003f27  add     rsp, 28h
0x140003f2b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140003f30  mov     rcx, cs:hHandle; hEvent
0x140003f37  call    cs:__imp_SetEvent
0x140003f3d  mov     rcx, cs:hHandle
0x140003f44  add     rsp, 28h
0x140003f48  jmp     cs:__imp_ResetEvent
```
