# OnDelete<void *,int (*)(void *),&CloseHandle(void *)>::~OnDelete<void *,int (*)(void *),&CloseHandle(void *)>(void)

- ea: `0x140004cdc`
- end: `0x140004cef`
- name: `??1?$OnDelete@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z@@QEAA@XZ`
- size: `19`
- prototype: `BOOL __fastcall(HANDLE *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140015159`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004ce3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004ce3`

## pseudocode

```c
BOOL __fastcall OnDelete<void *,int (*)(void *),&int CloseHandle(void *)>::~OnDelete<void *,int (*)(void *),&int CloseHandle(void *)>(
        HANDLE *a1)
{
  return CloseHandle(*a1);
}

```

## disassembly

```asm
0x140004cdc  sub     rsp, 28h
0x140004ce0  mov     rcx, [rcx]; hObject
0x140004ce3  call    cs:__imp_CloseHandle
0x140004ce9  nop
0x140004cea  add     rsp, 28h
0x140004cee  retn
```
