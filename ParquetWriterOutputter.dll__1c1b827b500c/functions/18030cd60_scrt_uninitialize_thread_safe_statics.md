# __scrt_uninitialize_thread_safe_statics

- ea: `0x18030cd60`
- end: `0x18030cd88`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18030cd60`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18030cd7d`
- `KERNEL32!CloseHandle` at `0x18030cd7d`
- `KERNEL32!DeleteCriticalSection` at `0x18030cd6b`
- `KERNEL32!DeleteCriticalSection` at `0x18030cd6b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1804C68E8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x18030cd60  sub     rsp, 28h
0x18030cd64  lea     rcx, stru_1804C68E8; lpCriticalSection
0x18030cd6b  call    cs:__imp_DeleteCriticalSection
0x18030cd71  mov     rcx, cs:hHandle; hObject
0x18030cd78  test    rcx, rcx
0x18030cd7b  jz      short loc_18030CD83
0x18030cd7d  call    cs:__imp_CloseHandle
0x18030cd83  add     rsp, 28h
0x18030cd87  retn
```
