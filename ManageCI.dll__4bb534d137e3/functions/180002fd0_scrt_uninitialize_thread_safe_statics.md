# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002fd0`
- end: `0x180002ff8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002fd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002fdb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002fdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002fed`

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
0x180002fd0  sub     rsp, 28h
0x180002fd4  lea     rcx, CriticalSection; lpCriticalSection
0x180002fdb  call    cs:__imp_DeleteCriticalSection
0x180002fe1  mov     rcx, cs:hHandle; hObject
0x180002fe8  test    rcx, rcx
0x180002feb  jz      short loc_180002FF3
0x180002fed  call    cs:__imp_CloseHandle
0x180002ff3  add     rsp, 28h
0x180002ff7  retn
```
