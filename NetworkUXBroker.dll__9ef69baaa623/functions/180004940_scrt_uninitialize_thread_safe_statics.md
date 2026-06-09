# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004940`
- end: `0x180004968`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000494b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000494b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000495d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000495d`

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
0x180004940  sub     rsp, 28h
0x180004944  lea     rcx, CriticalSection; lpCriticalSection
0x18000494b  call    cs:__imp_DeleteCriticalSection
0x180004951  mov     rcx, cs:hHandle; hObject
0x180004958  test    rcx, rcx
0x18000495b  jz      short loc_180004963
0x18000495d  call    cs:__imp_CloseHandle
0x180004963  add     rsp, 28h
0x180004967  retn
```
