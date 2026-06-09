# _Init_thread_notify

- ea: `0x1800035e4`
- end: `0x180003623`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003510`

## callees

- `0x1800035e4`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000361c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000360b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000360b`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180021658 )
    return qword_180021658(&qword_180021618);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x1800035e4  sub     rsp, 28h
0x1800035e8  mov     rax, cs:qword_180021658
0x1800035ef  test    rax, rax
0x1800035f2  jz      short loc_180003604
0x1800035f4  lea     rcx, qword_180021618
0x1800035fb  add     rsp, 28h
0x1800035ff  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003604  mov     rcx, cs:hHandle; hEvent
0x18000360b  call    cs:__imp_SetEvent
0x180003611  mov     rcx, cs:hHandle
0x180003618  add     rsp, 28h
0x18000361c  jmp     cs:__imp_ResetEvent
```
