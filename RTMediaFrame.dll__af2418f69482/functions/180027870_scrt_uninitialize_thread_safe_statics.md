# __scrt_uninitialize_thread_safe_statics

- ea: `0x180027870`
- end: `0x180027898`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180027870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002787b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002787b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002788d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002788d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180071C18);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180027870  sub     rsp, 28h
0x180027874  lea     rcx, stru_180071C18; lpCriticalSection
0x18002787b  call    cs:__imp_DeleteCriticalSection
0x180027881  mov     rcx, cs:hHandle; hObject
0x180027888  test    rcx, rcx
0x18002788b  jz      short loc_180027893
0x18002788d  call    cs:__imp_CloseHandle
0x180027893  add     rsp, 28h
0x180027897  retn
```
