# __scrt_uninitialize_thread_safe_statics

- ea: `0x18000f770`
- end: `0x18000f798`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f77b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f77b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f78d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f78d`

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
0x18000f770  sub     rsp, 28h
0x18000f774  lea     rcx, CriticalSection; lpCriticalSection
0x18000f77b  call    cs:__imp_DeleteCriticalSection
0x18000f781  mov     rcx, cs:hHandle; hObject
0x18000f788  test    rcx, rcx
0x18000f78b  jz      short loc_18000F793
0x18000f78d  call    cs:__imp_CloseHandle
0x18000f793  add     rsp, 28h
0x18000f797  retn
```
