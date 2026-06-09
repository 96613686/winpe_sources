# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004b10`
- end: `0x180004b38`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004b10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004b1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b2d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180042A28);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180004b10  sub     rsp, 28h
0x180004b14  lea     rcx, stru_180042A28; lpCriticalSection
0x180004b1b  call    cs:__imp_DeleteCriticalSection
0x180004b21  mov     rcx, cs:hHandle; hObject
0x180004b28  test    rcx, rcx
0x180004b2b  jz      short loc_180004B33
0x180004b2d  call    cs:__imp_CloseHandle
0x180004b33  add     rsp, 28h
0x180004b37  retn
```
