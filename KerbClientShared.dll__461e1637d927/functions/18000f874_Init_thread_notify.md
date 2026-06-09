# _Init_thread_notify

- ea: `0x18000f874`
- end: `0x18000f8b3`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f7a0`

## callees

- `0x18000f874`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f89b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f89b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f8ac`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_1800332A8 )
    return qword_1800332A8(&qword_180033268);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x18000f874  sub     rsp, 28h
0x18000f878  mov     rax, cs:qword_1800332A8
0x18000f87f  test    rax, rax
0x18000f882  jz      short loc_18000F894
0x18000f884  lea     rcx, qword_180033268
0x18000f88b  add     rsp, 28h
0x18000f88f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000f894  mov     rcx, cs:hHandle; hEvent
0x18000f89b  call    cs:__imp_SetEvent
0x18000f8a1  mov     rcx, cs:hHandle
0x18000f8a8  add     rsp, 28h
0x18000f8ac  jmp     cs:__imp_ResetEvent
```
