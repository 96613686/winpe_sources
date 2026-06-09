# __scrt_uninitialize_thread_safe_statics

- ea: `0x180001d90`
- end: `0x180001db8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001d90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001d9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001d9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001dad`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180017668);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180001d90  sub     rsp, 28h
0x180001d94  lea     rcx, stru_180017668; lpCriticalSection
0x180001d9b  call    cs:__imp_DeleteCriticalSection
0x180001da1  mov     rcx, cs:hHandle; hObject
0x180001da8  test    rcx, rcx
0x180001dab  jz      short loc_180001DB3
0x180001dad  call    cs:__imp_CloseHandle
0x180001db3  add     rsp, 28h
0x180001db7  retn
```
