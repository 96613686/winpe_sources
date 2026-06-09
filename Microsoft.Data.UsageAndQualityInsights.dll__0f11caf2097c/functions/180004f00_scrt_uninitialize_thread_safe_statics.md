# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004f00`
- end: `0x180004f28`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004f00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004f0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004f0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004f1d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1801598E8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180004f00  sub     rsp, 28h
0x180004f04  lea     rcx, stru_1801598E8; lpCriticalSection
0x180004f0b  call    cs:__imp_DeleteCriticalSection
0x180004f11  mov     rcx, cs:hHandle; hObject
0x180004f18  test    rcx, rcx
0x180004f1b  jz      short loc_180004F23
0x180004f1d  call    cs:__imp_CloseHandle
0x180004f23  add     rsp, 28h
0x180004f27  retn
```
