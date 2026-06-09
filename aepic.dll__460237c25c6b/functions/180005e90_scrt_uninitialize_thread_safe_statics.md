# __scrt_uninitialize_thread_safe_statics

- ea: `0x180005e90`
- end: `0x180005eb8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005e90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005e9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005e9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ead`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ead`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180121168);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180005e90  sub     rsp, 28h
0x180005e94  lea     rcx, stru_180121168; lpCriticalSection
0x180005e9b  call    cs:__imp_DeleteCriticalSection
0x180005ea1  mov     rcx, cs:hHandle; hObject
0x180005ea8  test    rcx, rcx
0x180005eab  jz      short loc_180005EB3
0x180005ead  call    cs:__imp_CloseHandle
0x180005eb3  add     rsp, 28h
0x180005eb7  retn
```
