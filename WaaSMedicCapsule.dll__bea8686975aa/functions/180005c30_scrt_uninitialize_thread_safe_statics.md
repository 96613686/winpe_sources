# __scrt_uninitialize_thread_safe_statics

- ea: `0x180005c30`
- end: `0x180005c58`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005c3b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005c3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c4d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180098248);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180005c30  sub     rsp, 28h
0x180005c34  lea     rcx, stru_180098248; lpCriticalSection
0x180005c3b  call    cs:__imp_DeleteCriticalSection
0x180005c41  mov     rcx, cs:hHandle; hObject
0x180005c48  test    rcx, rcx
0x180005c4b  jz      short loc_180005C53
0x180005c4d  call    cs:__imp_CloseHandle
0x180005c53  add     rsp, 28h
0x180005c57  retn
```
