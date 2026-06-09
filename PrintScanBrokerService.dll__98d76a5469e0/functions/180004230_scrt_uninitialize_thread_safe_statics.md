# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004230`
- end: `0x180004258`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000423b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000423b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000424d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000424d`

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
0x180004230  sub     rsp, 28h
0x180004234  lea     rcx, CriticalSection; lpCriticalSection
0x18000423b  call    cs:__imp_DeleteCriticalSection
0x180004241  mov     rcx, cs:hHandle; hObject
0x180004248  test    rcx, rcx
0x18000424b  jz      short loc_180004253
0x18000424d  call    cs:__imp_CloseHandle
0x180004253  add     rsp, 28h
0x180004257  retn
```
