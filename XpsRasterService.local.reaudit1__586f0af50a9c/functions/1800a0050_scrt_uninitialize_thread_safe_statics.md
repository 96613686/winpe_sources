# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800a0050`
- end: `0x1800a0078`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800a0050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a005b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a005b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a006d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a006d`

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
0x1800a0050  sub     rsp, 28h
0x1800a0054  lea     rcx, CriticalSection; lpCriticalSection
0x1800a005b  call    cs:__imp_DeleteCriticalSection
0x1800a0061  mov     rcx, cs:hHandle; hObject
0x1800a0068  test    rcx, rcx
0x1800a006b  jz      short loc_1800A0073
0x1800a006d  call    cs:__imp_CloseHandle
0x1800a0073  add     rsp, 28h
0x1800a0077  retn
```
