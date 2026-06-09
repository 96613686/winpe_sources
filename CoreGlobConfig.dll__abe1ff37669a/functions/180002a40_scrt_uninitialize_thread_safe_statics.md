# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002a40`
- end: `0x180002a68`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002a4b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002a4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002a5d`

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
0x180002a40  sub     rsp, 28h
0x180002a44  lea     rcx, CriticalSection; lpCriticalSection
0x180002a4b  call    cs:__imp_DeleteCriticalSection
0x180002a51  mov     rcx, cs:hHandle; hObject
0x180002a58  test    rcx, rcx
0x180002a5b  jz      short loc_180002A63
0x180002a5d  call    cs:__imp_CloseHandle
0x180002a63  add     rsp, 28h
0x180002a67  retn
```
