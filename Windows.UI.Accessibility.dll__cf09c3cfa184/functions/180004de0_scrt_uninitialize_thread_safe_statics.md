# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004de0`
- end: `0x180004e08`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004deb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004deb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dfd`

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
0x180004de0  sub     rsp, 28h
0x180004de4  lea     rcx, CriticalSection; lpCriticalSection
0x180004deb  call    cs:__imp_DeleteCriticalSection
0x180004df1  mov     rcx, cs:hHandle; hObject
0x180004df8  test    rcx, rcx
0x180004dfb  jz      short loc_180004E03
0x180004dfd  call    cs:__imp_CloseHandle
0x180004e03  add     rsp, 28h
0x180004e07  retn
```
