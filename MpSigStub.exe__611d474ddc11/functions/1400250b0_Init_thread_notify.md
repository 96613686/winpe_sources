# _Init_thread_notify

- ea: `0x1400250b0`
- end: `0x1400250f1`
- name: `_Init_thread_notify`
- size: `65`
- prototype: `int()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140024fb8`
- `0x140024fe8`

## callees

- `0x1400250b0`
- `0x1400ae030`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1400250d9`
- `KERNEL32!SetEvent` at `0x1400250d9`
- `KERNEL32!ResetEvent` at `0x1400250ea`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_1400D7C50 )
    return qword_1400D7C50(&qword_1400D7C10);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x1400250b0  sub     rsp, 28h
0x1400250b4  mov     rax, cs:qword_1400D7C50
0x1400250bb  test    rax, rax
0x1400250be  jz      short loc_1400250D2
0x1400250c0  lea     rcx, qword_1400D7C10
0x1400250c7  add     rsp, 28h
0x1400250cb  jmp     cs:__guard_dispatch_icall_fptr
0x1400250d2  mov     rcx, cs:hHandle; hEvent
0x1400250d9  call    cs:SetEvent
0x1400250df  mov     rcx, cs:hHandle
0x1400250e6  add     rsp, 28h
0x1400250ea  jmp     cs:ResetEvent
```
