# _Init_thread_notify

- ea: `0x180046cc0`
- end: `0x180046cff`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180046bb0`
- `0x180046bec`

## callees

- `0x180046cc0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180046cf8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180046ce7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180046ce7`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_1800B4C20 )
    return qword_1800B4C20(&qword_1800B4BE0);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180046cc0  sub     rsp, 28h
0x180046cc4  mov     rax, cs:qword_1800B4C20
0x180046ccb  test    rax, rax
0x180046cce  jz      short loc_180046CE0
0x180046cd0  lea     rcx, qword_1800B4BE0
0x180046cd7  add     rsp, 28h
0x180046cdb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180046ce0  mov     rcx, cs:hHandle; hEvent
0x180046ce7  call    cs:__imp_SetEvent
0x180046ced  mov     rcx, cs:hHandle
0x180046cf4  add     rsp, 28h
0x180046cf8  jmp     cs:__imp_ResetEvent
```
