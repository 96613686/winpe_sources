# UninitializeWorkQueue

- ea: `0x18002c924`
- end: `0x18002c943`
- name: `UninitializeWorkQueue`
- size: `31`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800164a4`
- `0x18001ae2c`
- `0x18002c504`
- `0x18002d00c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c92d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c92d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c93c`

## pseudocode

```c
BOOL __fastcall UninitializeWorkQueue(__int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
  return CloseHandle(*(HANDLE *)(a1 + 48));
}

```

## disassembly

```asm
0x18002c924  push    rbx
0x18002c926  sub     rsp, 20h
0x18002c92a  mov     rbx, rcx
0x18002c92d  call    cs:__imp_DeleteCriticalSection
0x18002c933  mov     rcx, [rbx+30h]
0x18002c937  add     rsp, 20h
0x18002c93b  pop     rbx
0x18002c93c  jmp     cs:__imp_CloseHandle
```
