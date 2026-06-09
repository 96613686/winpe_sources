# __scrt_uninitialize_thread_safe_statics

- ea: `0x180031fc0`
- end: `0x180031fe8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180031fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031fcb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031fcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fdd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180063F28);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180031fc0  sub     rsp, 28h
0x180031fc4  lea     rcx, stru_180063F28; lpCriticalSection
0x180031fcb  call    cs:__imp_DeleteCriticalSection
0x180031fd1  mov     rcx, cs:hHandle; hObject
0x180031fd8  test    rcx, rcx
0x180031fdb  jz      short loc_180031FE3
0x180031fdd  call    cs:__imp_CloseHandle
0x180031fe3  add     rsp, 28h
0x180031fe7  retn
```
