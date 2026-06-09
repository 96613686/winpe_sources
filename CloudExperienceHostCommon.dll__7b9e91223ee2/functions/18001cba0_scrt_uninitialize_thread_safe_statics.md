# __scrt_uninitialize_thread_safe_statics

- ea: `0x18001cba0`
- end: `0x18001cbc8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001cba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001cbab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001cbab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbbd`

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
0x18001cba0  sub     rsp, 28h
0x18001cba4  lea     rcx, CriticalSection; lpCriticalSection
0x18001cbab  call    cs:__imp_DeleteCriticalSection
0x18001cbb1  mov     rcx, cs:hHandle; hObject
0x18001cbb8  test    rcx, rcx
0x18001cbbb  jz      short loc_18001CBC3
0x18001cbbd  call    cs:__imp_CloseHandle
0x18001cbc3  add     rsp, 28h
0x18001cbc7  retn
```
