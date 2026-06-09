# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004fc0`
- end: `0x180004fe8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004fcb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004fcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fdd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180004fc0  sub     rsp, 28h
0x180004fc4  lea     rcx, CriticalSection; lpCriticalSection
0x180004fcb  call    cs:__imp_DeleteCriticalSection
0x180004fd1  mov     rcx, cs:hHandle; hObject
0x180004fd8  test    rcx, rcx
0x180004fdb  jz      short loc_180004FE3
0x180004fdd  call    cs:__imp_CloseHandle
0x180004fe3  add     rsp, 28h
0x180004fe7  retn
```
