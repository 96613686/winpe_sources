# __scrt_uninitialize_thread_safe_statics

- ea: `0x180005250`
- end: `0x180005278`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000525b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000525b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000526d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000526d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800FEA68);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180005250  sub     rsp, 28h
0x180005254  lea     rcx, stru_1800FEA68; lpCriticalSection
0x18000525b  call    cs:__imp_DeleteCriticalSection
0x180005261  mov     rcx, cs:hHandle; hObject
0x180005268  test    rcx, rcx
0x18000526b  jz      short loc_180005273
0x18000526d  call    cs:__imp_CloseHandle
0x180005273  add     rsp, 28h
0x180005277  retn
```
