# __scrt_uninitialize_thread_safe_statics

- ea: `0x180005450`
- end: `0x180005478`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000545b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000545b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000546d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000546d`

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
0x180005450  sub     rsp, 28h
0x180005454  lea     rcx, CriticalSection; lpCriticalSection
0x18000545b  call    cs:__imp_DeleteCriticalSection
0x180005461  mov     rcx, cs:hHandle; hObject
0x180005468  test    rcx, rcx
0x18000546b  jz      short loc_180005473
0x18000546d  call    cs:__imp_CloseHandle
0x180005473  add     rsp, 28h
0x180005477  retn
```
