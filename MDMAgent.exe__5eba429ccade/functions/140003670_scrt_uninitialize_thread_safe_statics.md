# __scrt_uninitialize_thread_safe_statics

- ea: `0x140003670`
- end: `0x140003698`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000367b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000367b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000368d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000368d`

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
0x140003670  sub     rsp, 28h
0x140003674  lea     rcx, CriticalSection; lpCriticalSection
0x14000367b  call    cs:__imp_DeleteCriticalSection
0x140003681  mov     rcx, cs:hHandle; hObject
0x140003688  test    rcx, rcx
0x14000368b  jz      short loc_140003693
0x14000368d  call    cs:__imp_CloseHandle
0x140003693  add     rsp, 28h
0x140003697  retn
```
