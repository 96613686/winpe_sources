# __scrt_uninitialize_thread_safe_statics

- ea: `0x18001ced0`
- end: `0x18001cef8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001ced0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001cedb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001cedb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ceed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ceed`

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
0x18001ced0  sub     rsp, 28h
0x18001ced4  lea     rcx, CriticalSection; lpCriticalSection
0x18001cedb  call    cs:__imp_DeleteCriticalSection
0x18001cee1  mov     rcx, cs:hHandle; hObject
0x18001cee8  test    rcx, rcx
0x18001ceeb  jz      short loc_18001CEF3
0x18001ceed  call    cs:__imp_CloseHandle
0x18001cef3  add     rsp, 28h
0x18001cef7  retn
```
