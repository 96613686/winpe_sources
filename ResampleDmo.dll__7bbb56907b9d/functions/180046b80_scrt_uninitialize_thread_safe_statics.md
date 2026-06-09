# __scrt_uninitialize_thread_safe_statics

- ea: `0x180046b80`
- end: `0x180046ba8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180046b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046b8b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046b8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046b9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046b9d`

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
0x180046b80  sub     rsp, 28h
0x180046b84  lea     rcx, CriticalSection; lpCriticalSection
0x180046b8b  call    cs:__imp_DeleteCriticalSection
0x180046b91  mov     rcx, cs:hHandle; hObject
0x180046b98  test    rcx, rcx
0x180046b9b  jz      short loc_180046BA3
0x180046b9d  call    cs:__imp_CloseHandle
0x180046ba3  add     rsp, 28h
0x180046ba7  retn
```
