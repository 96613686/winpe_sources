# __scrt_uninitialize_thread_safe_statics

- ea: `0x14000fa50`
- end: `0x14000fa78`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000fa50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fa6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000fa6d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000fa5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000fa5b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_14009D428);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x14000fa50  sub     rsp, 28h
0x14000fa54  lea     rcx, stru_14009D428; lpCriticalSection
0x14000fa5b  call    cs:__imp_DeleteCriticalSection
0x14000fa61  mov     rcx, cs:hHandle; hObject
0x14000fa68  test    rcx, rcx
0x14000fa6b  jz      short loc_14000FA73
0x14000fa6d  call    cs:__imp_CloseHandle
0x14000fa73  add     rsp, 28h
0x14000fa77  retn
```
