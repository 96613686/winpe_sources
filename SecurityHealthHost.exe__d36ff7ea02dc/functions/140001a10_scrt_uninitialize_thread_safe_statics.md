# __scrt_uninitialize_thread_safe_statics

- ea: `0x140001a10`
- end: `0x140001a38`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001a10`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140001a2d`
- `KERNEL32!CloseHandle` at `0x140001a2d`
- `KERNEL32!DeleteCriticalSection` at `0x140001a1b`
- `KERNEL32!DeleteCriticalSection` at `0x140001a1b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_140018C60);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x140001a10  sub     rsp, 28h
0x140001a14  lea     rcx, stru_140018C60; lpCriticalSection
0x140001a1b  call    cs:__imp_DeleteCriticalSection
0x140001a21  mov     rcx, cs:hHandle; hObject
0x140001a28  test    rcx, rcx
0x140001a2b  jz      short loc_140001A33
0x140001a2d  call    cs:__imp_CloseHandle
0x140001a33  add     rsp, 28h
0x140001a37  retn
```
