# _Init_thread_notify

- ea: `0x180002310`
- end: `0x18000234f`
- name: `_Init_thread_notify`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002200`
- `0x18000223c`

## callees

- `0x180002310`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180002348`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002337`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002337`

## pseudocode

```c
int Init_thread_notify()
{
  if ( qword_180010418 )
    return qword_180010418(&qword_1800103D8);
  SetEvent(hHandle);
  return ResetEvent(hHandle);
}

```

## disassembly

```asm
0x180002310  sub     rsp, 28h
0x180002314  mov     rax, cs:qword_180010418
0x18000231b  test    rax, rax
0x18000231e  jz      short loc_180002330
0x180002320  lea     rcx, qword_1800103D8
0x180002327  add     rsp, 28h
0x18000232b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002330  mov     rcx, cs:hHandle; hEvent
0x180002337  call    cs:__imp_SetEvent
0x18000233d  mov     rcx, cs:hHandle
0x180002344  add     rsp, 28h
0x180002348  jmp     cs:__imp_ResetEvent
```
