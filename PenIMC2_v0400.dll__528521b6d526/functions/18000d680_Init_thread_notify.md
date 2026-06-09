# _Init_thread_notify

- ea: `0x18000d680`
- end: `0x18000d6c1`
- name: `_Init_thread_notify`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d588`
- `0x18000d5b8`

## callees

- `0x18000d680`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000d6a9`
- `KERNEL32!SetEvent` at `0x18000d6a9`
- `KERNEL32!ResetEvent` at `0x18000d6ba`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180018918 )
    return qword_180018918(&qword_1800188D8);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x18000d680  sub     rsp, 28h
0x18000d684  mov     rax, cs:qword_180018918
0x18000d68b  test    rax, rax
0x18000d68e  jz      short loc_18000D6A2
0x18000d690  lea     rcx, qword_1800188D8
0x18000d697  add     rsp, 28h
0x18000d69b  jmp     cs:__guard_dispatch_icall_fptr
0x18000d6a2  mov     rcx, cs:hHandle; hEvent
0x18000d6a9  call    cs:__imp_SetEvent
0x18000d6af  mov     rcx, cs:hHandle
0x18000d6b6  add     rsp, 28h
0x18000d6ba  jmp     cs:__imp_ResetEvent
```
