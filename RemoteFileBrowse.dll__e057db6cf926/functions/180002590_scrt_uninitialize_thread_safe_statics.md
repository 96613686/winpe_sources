# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002590`
- end: `0x1800025b8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000259b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000259b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025ad`

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
0x180002590  sub     rsp, 28h
0x180002594  lea     rcx, CriticalSection; lpCriticalSection
0x18000259b  call    cs:__imp_DeleteCriticalSection
0x1800025a1  mov     rcx, cs:hHandle; hObject
0x1800025a8  test    rcx, rcx
0x1800025ab  jz      short loc_1800025B3
0x1800025ad  call    cs:__imp_CloseHandle
0x1800025b3  add     rsp, 28h
0x1800025b7  retn
```
