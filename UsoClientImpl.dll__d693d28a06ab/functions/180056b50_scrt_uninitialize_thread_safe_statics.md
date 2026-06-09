# __scrt_uninitialize_thread_safe_statics

- ea: `0x180056b50`
- end: `0x180056b78`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180056b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180056b5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180056b5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056b6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056b6d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18009EEA8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180056b50  sub     rsp, 28h
0x180056b54  lea     rcx, stru_18009EEA8; lpCriticalSection
0x180056b5b  call    cs:__imp_DeleteCriticalSection
0x180056b61  mov     rcx, cs:hHandle; hObject
0x180056b68  test    rcx, rcx
0x180056b6b  jz      short loc_180056B73
0x180056b6d  call    cs:__imp_CloseHandle
0x180056b73  add     rsp, 28h
0x180056b77  retn
```
