# __scrt_uninitialize_thread_safe_statics

- ea: `0x180003050`
- end: `0x180003078`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000305b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000305b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000306d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000306d`

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
0x180003050  sub     rsp, 28h
0x180003054  lea     rcx, CriticalSection; lpCriticalSection
0x18000305b  call    cs:__imp_DeleteCriticalSection
0x180003061  mov     rcx, cs:hHandle; hObject
0x180003068  test    rcx, rcx
0x18000306b  jz      short loc_180003073
0x18000306d  call    cs:__imp_CloseHandle
0x180003073  add     rsp, 28h
0x180003077  retn
```
