# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004e40`
- end: `0x180004e68`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004e4b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004e4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e5d`

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
0x180004e40  sub     rsp, 28h
0x180004e44  lea     rcx, CriticalSection; lpCriticalSection
0x180004e4b  call    cs:__imp_DeleteCriticalSection
0x180004e51  mov     rcx, cs:hHandle; hObject
0x180004e58  test    rcx, rcx
0x180004e5b  jz      short loc_180004E63
0x180004e5d  call    cs:__imp_CloseHandle
0x180004e63  add     rsp, 28h
0x180004e67  retn
```
