# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004110`
- end: `0x180004138`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000411b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000411b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000412d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000412d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18008CCB0);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180004110  sub     rsp, 28h
0x180004114  lea     rcx, stru_18008CCB0; lpCriticalSection
0x18000411b  call    cs:__imp_DeleteCriticalSection
0x180004121  mov     rcx, cs:hHandle; hObject
0x180004128  test    rcx, rcx
0x18000412b  jz      short loc_180004133
0x18000412d  call    cs:__imp_CloseHandle
0x180004133  add     rsp, 28h
0x180004137  retn
```
