# _Init_thread_notify

- ea: `0x140003494`
- end: `0x1400034d3`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400033c0`

## callees

- `0x140003494`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1400034cc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400034bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400034bb`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_140030578 )
    return qword_140030578(&qword_140030538);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x140003494  sub     rsp, 28h
0x140003498  mov     rax, cs:qword_140030578
0x14000349f  test    rax, rax
0x1400034a2  jz      short loc_1400034B4
0x1400034a4  lea     rcx, qword_140030538
0x1400034ab  add     rsp, 28h
0x1400034af  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1400034b4  mov     rcx, cs:hHandle; hEvent
0x1400034bb  call    cs:__imp_SetEvent
0x1400034c1  mov     rcx, cs:hHandle
0x1400034c8  add     rsp, 28h
0x1400034cc  jmp     cs:__imp_ResetEvent
```
