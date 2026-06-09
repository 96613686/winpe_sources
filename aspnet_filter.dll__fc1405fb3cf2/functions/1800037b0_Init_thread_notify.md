# _Init_thread_notify

- ea: `0x1800037b0`
- end: `0x1800037f1`
- name: `_Init_thread_notify`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800036e8`

## callees

- `0x1800037b0`
- `0x1800043b0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800037d9`
- `KERNEL32!SetEvent` at `0x1800037d9`
- `KERNEL32!ResetEvent` at `0x1800037ea`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180007220 )
    return qword_180007220(&qword_1800071E0);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x1800037b0  sub     rsp, 28h
0x1800037b4  mov     rax, cs:qword_180007220
0x1800037bb  test    rax, rax
0x1800037be  jz      short loc_1800037D2
0x1800037c0  lea     rcx, qword_1800071E0
0x1800037c7  add     rsp, 28h
0x1800037cb  jmp     cs:__guard_dispatch_icall_fptr
0x1800037d2  mov     rcx, cs:hHandle; hEvent
0x1800037d9  call    cs:__imp_SetEvent
0x1800037df  mov     rcx, cs:hHandle
0x1800037e6  add     rsp, 28h
0x1800037ea  jmp     cs:__imp_ResetEvent
```
