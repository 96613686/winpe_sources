# __scrt_uninitialize_thread_safe_statics

- ea: `0x18002cc00`
- end: `0x18002cc28`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002cc00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002cc0b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002cc0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cc1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cc1d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800C0628);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x18002cc00  sub     rsp, 28h
0x18002cc04  lea     rcx, stru_1800C0628; lpCriticalSection
0x18002cc0b  call    cs:__imp_DeleteCriticalSection
0x18002cc11  mov     rcx, cs:hHandle; hObject
0x18002cc18  test    rcx, rcx
0x18002cc1b  jz      short loc_18002CC23
0x18002cc1d  call    cs:__imp_CloseHandle
0x18002cc23  add     rsp, 28h
0x18002cc27  retn
```
