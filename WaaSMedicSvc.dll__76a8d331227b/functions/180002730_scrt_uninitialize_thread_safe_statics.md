# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002730`
- end: `0x180002758`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000273b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000273b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000274d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000274d`

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
0x180002730  sub     rsp, 28h
0x180002734  lea     rcx, CriticalSection; lpCriticalSection
0x18000273b  call    cs:__imp_DeleteCriticalSection
0x180002741  mov     rcx, cs:hHandle; hObject
0x180002748  test    rcx, rcx
0x18000274b  jz      short loc_180002753
0x18000274d  call    cs:__imp_CloseHandle
0x180002753  add     rsp, 28h
0x180002757  retn
```
