# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800034e0`
- end: `0x180003508`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800034e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034fd`

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
0x1800034e0  sub     rsp, 28h
0x1800034e4  lea     rcx, CriticalSection; lpCriticalSection
0x1800034eb  call    cs:__imp_DeleteCriticalSection
0x1800034f1  mov     rcx, cs:hHandle; hObject
0x1800034f8  test    rcx, rcx
0x1800034fb  jz      short loc_180003503
0x1800034fd  call    cs:__imp_CloseHandle
0x180003503  add     rsp, 28h
0x180003507  retn
```
