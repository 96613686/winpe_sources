# _Init_thread_notify

- ea: `0x180001e94`
- end: `0x180001ed3`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001dc0`

## callees

- `0x180001e94`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180001ecc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001ebb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180001ebb`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180017698 )
    return qword_180017698(&qword_180017658);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180001e94  sub     rsp, 28h
0x180001e98  mov     rax, cs:qword_180017698
0x180001e9f  test    rax, rax
0x180001ea2  jz      short loc_180001EB4
0x180001ea4  lea     rcx, qword_180017658
0x180001eab  add     rsp, 28h
0x180001eaf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001eb4  mov     rcx, cs:hHandle; hEvent
0x180001ebb  call    cs:__imp_SetEvent
0x180001ec1  mov     rcx, cs:hHandle
0x180001ec8  add     rsp, 28h
0x180001ecc  jmp     cs:__imp_ResetEvent
```
