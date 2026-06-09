# _Init_thread_notify

- ea: `0x180002870`
- end: `0x1800028af`
- name: `_Init_thread_notify`
- size: `63`
- prototype: `int()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002760`
- `0x18000279c`

## callees

- `0x180002870`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002897`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002897`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800028a8`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180013438 )
    return qword_180013438(&qword_1800133F8);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002870  sub     rsp, 28h
0x180002874  mov     rax, cs:qword_180013438
0x18000287b  test    rax, rax
0x18000287e  jz      short loc_180002890
0x180002880  lea     rcx, qword_1800133F8
0x180002887  add     rsp, 28h
0x18000288b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002890  mov     rcx, cs:hHandle; hEvent
0x180002897  call    cs:__imp_SetEvent
0x18000289d  mov     rcx, cs:hHandle
0x1800028a4  add     rsp, 28h
0x1800028a8  jmp     cs:__imp_ResetEvent
```
