# __scrt_uninitialize_thread_safe_statics

- ea: `0x140004f80`
- end: `0x140004fa8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140004f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004f8b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140004f8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004f9d`

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
0x140004f80  sub     rsp, 28h
0x140004f84  lea     rcx, CriticalSection; lpCriticalSection
0x140004f8b  call    cs:__imp_DeleteCriticalSection
0x140004f91  mov     rcx, cs:hHandle; hObject
0x140004f98  test    rcx, rcx
0x140004f9b  jz      short loc_140004FA3
0x140004f9d  call    cs:__imp_CloseHandle
0x140004fa3  add     rsp, 28h
0x140004fa7  retn
```
