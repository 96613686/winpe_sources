# _Init_thread_notify

- ea: `0x140001b14`
- end: `0x140001b53`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001a40`

## callees

- `0x140001b14`
- `0x140011010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140001b3b`
- `KERNEL32!SetEvent` at `0x140001b3b`
- `KERNEL32!ResetEvent` at `0x140001b4c`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_140018C90 )
    return qword_140018C90(&qword_140018C50);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x140001b14  sub     rsp, 28h
0x140001b18  mov     rax, cs:qword_140018C90
0x140001b1f  test    rax, rax
0x140001b22  jz      short loc_140001B34
0x140001b24  lea     rcx, qword_140018C50
0x140001b2b  add     rsp, 28h
0x140001b2f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140001b34  mov     rcx, cs:hHandle; hEvent
0x140001b3b  call    cs:__imp_SetEvent
0x140001b41  mov     rcx, cs:hHandle
0x140001b48  add     rsp, 28h
0x140001b4c  jmp     cs:__imp_ResetEvent
```
