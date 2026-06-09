# _Init_thread_notify

- ea: `0x1800035f0`
- end: `0x18000362f`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034e0`
- `0x18000351c`

## callees

- `0x1800035f0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003617`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003617`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003628`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180025CC0 )
    return qword_180025CC0(&qword_180025C80);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x1800035f0  sub     rsp, 28h
0x1800035f4  mov     rax, cs:qword_180025CC0
0x1800035fb  test    rax, rax
0x1800035fe  jz      short loc_180003610
0x180003600  lea     rcx, qword_180025C80
0x180003607  add     rsp, 28h
0x18000360b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003610  mov     rcx, cs:hHandle; hEvent
0x180003617  call    cs:__imp_SetEvent
0x18000361d  mov     rcx, cs:hHandle
0x180003624  add     rsp, 28h
0x180003628  jmp     cs:__imp_ResetEvent
```
