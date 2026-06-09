# __scrt_uninitialize_thread_safe_statics

- ea: `0x180061aa0`
- end: `0x180061ac8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180061aa0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061abd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061abd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180061aab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180061aab`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18013F620);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180061aa0  sub     rsp, 28h
0x180061aa4  lea     rcx, stru_18013F620; lpCriticalSection
0x180061aab  call    cs:__imp_DeleteCriticalSection
0x180061ab1  mov     rcx, cs:hHandle; hObject
0x180061ab8  test    rcx, rcx
0x180061abb  jz      short loc_180061AC3
0x180061abd  call    cs:__imp_CloseHandle
0x180061ac3  add     rsp, 28h
0x180061ac7  retn
```
