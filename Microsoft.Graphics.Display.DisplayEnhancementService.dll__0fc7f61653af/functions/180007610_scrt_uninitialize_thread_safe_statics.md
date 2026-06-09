# __scrt_uninitialize_thread_safe_statics

- ea: `0x180007610`
- end: `0x180007638`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000761b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000761b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000762d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000762d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180007610  sub     rsp, 28h
0x180007614  lea     rcx, CriticalSection; lpCriticalSection
0x18000761b  call    cs:__imp_DeleteCriticalSection
0x180007621  mov     rcx, cs:hHandle; hObject
0x180007628  test    rcx, rcx
0x18000762b  jz      short loc_180007633
0x18000762d  call    cs:__imp_CloseHandle
0x180007633  add     rsp, 28h
0x180007637  retn
```
