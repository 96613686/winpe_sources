# _Init_thread_notify

- ea: `0x140003774`
- end: `0x1400037b3`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400036a0`

## callees

- `0x140003774`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000379b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000379b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1400037ac`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_1400244B8 )
    return qword_1400244B8(&qword_140024478);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x140003774  sub     rsp, 28h
0x140003778  mov     rax, cs:qword_1400244B8
0x14000377f  test    rax, rax
0x140003782  jz      short loc_140003794
0x140003784  lea     rcx, qword_140024478
0x14000378b  add     rsp, 28h
0x14000378f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140003794  mov     rcx, cs:hHandle; hEvent
0x14000379b  call    cs:__imp_SetEvent
0x1400037a1  mov     rcx, cs:hHandle
0x1400037a8  add     rsp, 28h
0x1400037ac  jmp     cs:__imp_ResetEvent
```
