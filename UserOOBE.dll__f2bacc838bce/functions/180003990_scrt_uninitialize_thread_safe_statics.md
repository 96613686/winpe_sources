# __scrt_uninitialize_thread_safe_statics

- ea: `0x180003990`
- end: `0x1800039b8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000399b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000399b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039ad`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18006DEA8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180003990  sub     rsp, 28h
0x180003994  lea     rcx, stru_18006DEA8; lpCriticalSection
0x18000399b  call    cs:__imp_DeleteCriticalSection
0x1800039a1  mov     rcx, cs:hHandle; hObject
0x1800039a8  test    rcx, rcx
0x1800039ab  jz      short loc_1800039B3
0x1800039ad  call    cs:__imp_CloseHandle
0x1800039b3  add     rsp, 28h
0x1800039b7  retn
```
