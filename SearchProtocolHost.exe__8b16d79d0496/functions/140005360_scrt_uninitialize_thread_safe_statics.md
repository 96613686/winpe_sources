# __scrt_uninitialize_thread_safe_statics

- ea: `0x140005360`
- end: `0x140005388`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000536b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000536b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000537d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000537d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1400972A0);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x140005360  sub     rsp, 28h
0x140005364  lea     rcx, stru_1400972A0; lpCriticalSection
0x14000536b  call    cs:__imp_DeleteCriticalSection
0x140005371  mov     rcx, cs:hHandle; hObject
0x140005378  test    rcx, rcx
0x14000537b  jz      short loc_140005383
0x14000537d  call    cs:__imp_CloseHandle
0x140005383  add     rsp, 28h
0x140005387  retn
```
