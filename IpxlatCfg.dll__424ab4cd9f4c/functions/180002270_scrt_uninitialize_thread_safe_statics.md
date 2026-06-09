# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002270`
- end: `0x180002298`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002270`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000228d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000228d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000227b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000227b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180023528);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180002270  sub     rsp, 28h
0x180002274  lea     rcx, stru_180023528; lpCriticalSection
0x18000227b  call    cs:__imp_DeleteCriticalSection
0x180002281  mov     rcx, cs:hHandle; hObject
0x180002288  test    rcx, rcx
0x18000228b  jz      short loc_180002293
0x18000228d  call    cs:__imp_CloseHandle
0x180002293  add     rsp, 28h
0x180002297  retn
```
