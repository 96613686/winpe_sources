# __scrt_uninitialize_thread_safe_statics

- ea: `0x180003730`
- end: `0x180003758`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000373b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000373b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000374d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000374d`

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
0x180003730  sub     rsp, 28h
0x180003734  lea     rcx, CriticalSection; lpCriticalSection
0x18000373b  call    cs:__imp_DeleteCriticalSection
0x180003741  mov     rcx, cs:hHandle; hObject
0x180003748  test    rcx, rcx
0x18000374b  jz      short loc_180003753
0x18000374d  call    cs:__imp_CloseHandle
0x180003753  add     rsp, 28h
0x180003757  retn
```
