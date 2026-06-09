# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004330`
- end: `0x180004358`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000433b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000433b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000434d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000434d`

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
0x180004330  sub     rsp, 28h
0x180004334  lea     rcx, CriticalSection; lpCriticalSection
0x18000433b  call    cs:__imp_DeleteCriticalSection
0x180004341  mov     rcx, cs:hHandle; hObject
0x180004348  test    rcx, rcx
0x18000434b  jz      short loc_180004353
0x18000434d  call    cs:__imp_CloseHandle
0x180004353  add     rsp, 28h
0x180004357  retn
```
