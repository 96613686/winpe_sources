# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800bd8a0`
- end: `0x1800bd8c8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800bd8a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bd8ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bd8ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd8bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd8bd`

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
0x1800bd8a0  sub     rsp, 28h
0x1800bd8a4  lea     rcx, CriticalSection; lpCriticalSection
0x1800bd8ab  call    cs:__imp_DeleteCriticalSection
0x1800bd8b1  mov     rcx, cs:hHandle; hObject
0x1800bd8b8  test    rcx, rcx
0x1800bd8bb  jz      short loc_1800BD8C3
0x1800bd8bd  call    cs:__imp_CloseHandle
0x1800bd8c3  add     rsp, 28h
0x1800bd8c7  retn
```
