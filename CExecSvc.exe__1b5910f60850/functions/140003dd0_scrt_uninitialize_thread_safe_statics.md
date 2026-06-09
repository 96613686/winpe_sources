# __scrt_uninitialize_thread_safe_statics

- ea: `0x140003dd0`
- end: `0x140003df8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003ddb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003ddb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003ded`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003ded`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_140039DB8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x140003dd0  sub     rsp, 28h
0x140003dd4  lea     rcx, stru_140039DB8; lpCriticalSection
0x140003ddb  call    cs:__imp_DeleteCriticalSection
0x140003de1  mov     rcx, cs:hHandle; hObject
0x140003de8  test    rcx, rcx
0x140003deb  jz      short loc_140003DF3
0x140003ded  call    cs:__imp_CloseHandle
0x140003df3  add     rsp, 28h
0x140003df7  retn
```
