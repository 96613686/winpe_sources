# __scrt_uninitialize_thread_safe_statics

- ea: `0x180005650`
- end: `0x180005678`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000565b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000565b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000566d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000566d`

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
0x180005650  sub     rsp, 28h
0x180005654  lea     rcx, CriticalSection; lpCriticalSection
0x18000565b  call    cs:__imp_DeleteCriticalSection
0x180005661  mov     rcx, cs:hHandle; hObject
0x180005668  test    rcx, rcx
0x18000566b  jz      short loc_180005673
0x18000566d  call    cs:__imp_CloseHandle
0x180005673  add     rsp, 28h
0x180005677  retn
```
