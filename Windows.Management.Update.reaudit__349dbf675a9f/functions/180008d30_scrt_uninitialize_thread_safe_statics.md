# __scrt_uninitialize_thread_safe_statics

- ea: `0x180008d30`
- end: `0x180008d58`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008d30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d3b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008d3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d4d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18003D0D8);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180008d30  sub     rsp, 28h
0x180008d34  lea     rcx, stru_18003D0D8; lpCriticalSection
0x180008d3b  call    cs:__imp_DeleteCriticalSection
0x180008d41  mov     rcx, cs:hObject; hObject
0x180008d48  test    rcx, rcx
0x180008d4b  jz      short loc_180008D53
0x180008d4d  call    cs:__imp_CloseHandle
0x180008d53  add     rsp, 28h
0x180008d57  retn
```
