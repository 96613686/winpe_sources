# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002890`
- end: `0x1800028b8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000289b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000289b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800028ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800028ad`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180059B28);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180002890  sub     rsp, 28h
0x180002894  lea     rcx, stru_180059B28; lpCriticalSection
0x18000289b  call    cs:__imp_DeleteCriticalSection
0x1800028a1  mov     rcx, cs:hHandle; hObject
0x1800028a8  test    rcx, rcx
0x1800028ab  jz      short loc_1800028B3
0x1800028ad  call    cs:__imp_CloseHandle
0x1800028b3  add     rsp, 28h
0x1800028b7  retn
```
