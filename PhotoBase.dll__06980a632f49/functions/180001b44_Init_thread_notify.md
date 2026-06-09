# _Init_thread_notify

- ea: `0x180001b44`
- end: `0x180001b83`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001a70`

## callees

- `0x180001b44`
- `0x180008010`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180001b7c`
- `KERNEL32!SetEvent` at `0x180001b6b`
- `KERNEL32!SetEvent` at `0x180001b6b`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_18000D278 )
    return qword_18000D278(&qword_18000D238);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180001b44  sub     rsp, 28h
0x180001b48  mov     rax, cs:qword_18000D278
0x180001b4f  test    rax, rax
0x180001b52  jz      short loc_180001B64
0x180001b54  lea     rcx, qword_18000D238
0x180001b5b  add     rsp, 28h
0x180001b5f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001b64  mov     rcx, cs:hHandle; hEvent
0x180001b6b  call    cs:__imp_SetEvent
0x180001b71  mov     rcx, cs:hHandle
0x180001b78  add     rsp, 28h
0x180001b7c  jmp     cs:__imp_ResetEvent
```
