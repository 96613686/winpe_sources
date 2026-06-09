# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004010`
- end: `0x180004038`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000401b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000401b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000402d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000402d`

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
0x180004010  sub     rsp, 28h
0x180004014  lea     rcx, CriticalSection; lpCriticalSection
0x18000401b  call    cs:__imp_DeleteCriticalSection
0x180004021  mov     rcx, cs:hHandle; hObject
0x180004028  test    rcx, rcx
0x18000402b  jz      short loc_180004033
0x18000402d  call    cs:__imp_CloseHandle
0x180004033  add     rsp, 28h
0x180004037  retn
```
