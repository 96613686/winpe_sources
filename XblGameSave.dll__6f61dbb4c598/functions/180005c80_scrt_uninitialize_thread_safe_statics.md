# __scrt_uninitialize_thread_safe_statics

- ea: `0x180005c80`
- end: `0x180005ca8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005c80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005c8b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005c8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c9d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800C0630);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180005c80  sub     rsp, 28h
0x180005c84  lea     rcx, stru_1800C0630; lpCriticalSection
0x180005c8b  call    cs:__imp_DeleteCriticalSection
0x180005c91  mov     rcx, cs:hHandle; hObject
0x180005c98  test    rcx, rcx
0x180005c9b  jz      short loc_180005CA3
0x180005c9d  call    cs:__imp_CloseHandle
0x180005ca3  add     rsp, 28h
0x180005ca7  retn
```
