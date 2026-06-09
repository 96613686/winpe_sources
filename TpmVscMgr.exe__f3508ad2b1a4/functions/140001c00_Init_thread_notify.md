# _Init_thread_notify

- ea: `0x140001c00`
- end: `0x140001c3f`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001af0`
- `0x140001b2c`

## callees

- `0x140001c00`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140001c38`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140001c27`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140001c27`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_14001A478 )
    return qword_14001A478(&qword_14001A438);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x140001c00  sub     rsp, 28h
0x140001c04  mov     rax, cs:qword_14001A478
0x140001c0b  test    rax, rax
0x140001c0e  jz      short loc_140001C20
0x140001c10  lea     rcx, qword_14001A438
0x140001c17  add     rsp, 28h
0x140001c1b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140001c20  mov     rcx, cs:hHandle; hEvent
0x140001c27  call    cs:__imp_SetEvent
0x140001c2d  mov     rcx, cs:hHandle
0x140001c34  add     rsp, 28h
0x140001c38  jmp     cs:__imp_ResetEvent
```
