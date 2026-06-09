# __scrt_uninitialize_thread_safe_statics

- ea: `0x18000e0f0`
- end: `0x18000e118`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000e0f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e0fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e0fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e10d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e10d`

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
0x18000e0f0  sub     rsp, 28h
0x18000e0f4  lea     rcx, CriticalSection; lpCriticalSection
0x18000e0fb  call    cs:__imp_DeleteCriticalSection
0x18000e101  mov     rcx, cs:hHandle; hObject
0x18000e108  test    rcx, rcx
0x18000e10b  jz      short loc_18000E113
0x18000e10d  call    cs:__imp_CloseHandle
0x18000e113  add     rsp, 28h
0x18000e117  retn
```
