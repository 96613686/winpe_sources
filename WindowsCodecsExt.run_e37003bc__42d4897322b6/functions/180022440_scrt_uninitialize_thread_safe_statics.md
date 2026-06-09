# __scrt_uninitialize_thread_safe_statics

- ea: `0x180022440`
- end: `0x180022468`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180022440`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002245d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002245d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002244b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002244b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180040230);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180022440  sub     rsp, 28h
0x180022444  lea     rcx, stru_180040230; lpCriticalSection
0x18002244b  call    cs:__imp_DeleteCriticalSection
0x180022451  mov     rcx, cs:hHandle; hObject
0x180022458  test    rcx, rcx
0x18002245b  jz      short loc_180022463
0x18002245d  call    cs:__imp_CloseHandle
0x180022463  add     rsp, 28h
0x180022467  retn
```
