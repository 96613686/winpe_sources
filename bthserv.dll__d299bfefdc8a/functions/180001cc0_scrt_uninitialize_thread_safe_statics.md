# __scrt_uninitialize_thread_safe_statics

- ea: `0x180001cc0`
- end: `0x180001ce8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001ccb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001ccb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001cdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001cdd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800445A8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180001cc0  sub     rsp, 28h
0x180001cc4  lea     rcx, stru_1800445A8; lpCriticalSection
0x180001ccb  call    cs:__imp_DeleteCriticalSection
0x180001cd1  mov     rcx, cs:hHandle; hObject
0x180001cd8  test    rcx, rcx
0x180001cdb  jz      short loc_180001CE3
0x180001cdd  call    cs:__imp_CloseHandle
0x180001ce3  add     rsp, 28h
0x180001ce7  retn
```
