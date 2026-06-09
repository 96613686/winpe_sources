# __scrt_uninitialize_thread_safe_statics

- ea: `0x180046c60`
- end: `0x180046c88`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180046c60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046c6b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046c6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046c7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046c7d`

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
0x180046c60  sub     rsp, 28h
0x180046c64  lea     rcx, CriticalSection; lpCriticalSection
0x180046c6b  call    cs:__imp_DeleteCriticalSection
0x180046c71  mov     rcx, cs:hHandle; hObject
0x180046c78  test    rcx, rcx
0x180046c7b  jz      short loc_180046C83
0x180046c7d  call    cs:__imp_CloseHandle
0x180046c83  add     rsp, 28h
0x180046c87  retn
```
