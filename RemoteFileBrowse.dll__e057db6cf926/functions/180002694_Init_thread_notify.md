# _Init_thread_notify

- ea: `0x180002694`
- end: `0x1800026d3`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800025c0`

## callees

- `0x180002694`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800026cc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800026bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800026bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int Init_thread_notify()
{
  if ( qword_1800234F8 )
    return qword_1800234F8(&qword_1800234B8);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002694  sub     rsp, 28h
0x180002698  mov     rax, cs:qword_1800234F8
0x18000269f  test    rax, rax
0x1800026a2  jz      short loc_1800026B4
0x1800026a4  lea     rcx, qword_1800234B8
0x1800026ab  add     rsp, 28h
0x1800026af  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800026b4  mov     rcx, cs:hHandle; hEvent
0x1800026bb  call    cs:__imp_SetEvent
0x1800026c1  mov     rcx, cs:hHandle
0x1800026c8  add     rsp, 28h
0x1800026cc  jmp     cs:__imp_ResetEvent
```
