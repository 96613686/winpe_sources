# __scrt_uninitialize_thread_safe_statics

- ea: `0x180051e70`
- end: `0x180051e98`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180051e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051e7b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051e7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051e8d`

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
0x180051e70  sub     rsp, 28h
0x180051e74  lea     rcx, CriticalSection; lpCriticalSection
0x180051e7b  call    cs:__imp_DeleteCriticalSection
0x180051e81  mov     rcx, cs:hHandle; hObject
0x180051e88  test    rcx, rcx
0x180051e8b  jz      short loc_180051E93
0x180051e8d  call    cs:__imp_CloseHandle
0x180051e93  add     rsp, 28h
0x180051e97  retn
```
