# __scrt_uninitialize_thread_safe_statics

- ea: `0x18000dbb0`
- end: `0x18000dbd8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000dbb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dbbb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dbbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbcd`

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
0x18000dbb0  sub     rsp, 28h
0x18000dbb4  lea     rcx, CriticalSection; lpCriticalSection
0x18000dbbb  call    cs:__imp_DeleteCriticalSection
0x18000dbc1  mov     rcx, cs:hHandle; hObject
0x18000dbc8  test    rcx, rcx
0x18000dbcb  jz      short loc_18000DBD3
0x18000dbcd  call    cs:__imp_CloseHandle
0x18000dbd3  add     rsp, 28h
0x18000dbd7  retn
```
