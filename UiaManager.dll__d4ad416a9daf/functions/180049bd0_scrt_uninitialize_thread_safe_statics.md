# __scrt_uninitialize_thread_safe_statics

- ea: `0x180049bd0`
- end: `0x180049bf8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180049bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180049bdb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180049bdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049bed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049bed`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800C4B98);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180049bd0  sub     rsp, 28h
0x180049bd4  lea     rcx, stru_1800C4B98; lpCriticalSection
0x180049bdb  call    cs:__imp_DeleteCriticalSection
0x180049be1  mov     rcx, cs:hHandle; hObject
0x180049be8  test    rcx, rcx
0x180049beb  jz      short loc_180049BF3
0x180049bed  call    cs:__imp_CloseHandle
0x180049bf3  add     rsp, 28h
0x180049bf7  retn
```
