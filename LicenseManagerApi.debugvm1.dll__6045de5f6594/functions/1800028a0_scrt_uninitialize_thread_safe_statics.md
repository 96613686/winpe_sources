# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800028a0`
- end: `0x1800028c8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800028a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800028ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800028ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800028bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800028bd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x1800028a0  sub     rsp, 28h
0x1800028a4  lea     rcx, CriticalSection; lpCriticalSection
0x1800028ab  call    cs:__imp_DeleteCriticalSection
0x1800028b1  mov     rcx, cs:hObject; hObject
0x1800028b8  test    rcx, rcx
0x1800028bb  jz      short loc_1800028C3
0x1800028bd  call    cs:__imp_CloseHandle
0x1800028c3  add     rsp, 28h
0x1800028c7  retn
```
