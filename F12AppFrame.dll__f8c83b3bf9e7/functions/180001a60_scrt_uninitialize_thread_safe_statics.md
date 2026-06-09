# __scrt_uninitialize_thread_safe_statics

- ea: `0x180001a60`
- end: `0x180001a88`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001a60`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180001a7d`
- `KERNEL32!CloseHandle` at `0x180001a7d`
- `KERNEL32!DeleteCriticalSection` at `0x180001a6b`
- `KERNEL32!DeleteCriticalSection` at `0x180001a6b`

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
0x180001a60  sub     rsp, 28h
0x180001a64  lea     rcx, CriticalSection; lpCriticalSection
0x180001a6b  call    cs:__imp_DeleteCriticalSection
0x180001a71  mov     rcx, cs:hHandle; hObject
0x180001a78  test    rcx, rcx
0x180001a7b  jz      short loc_180001A83
0x180001a7d  call    cs:__imp_CloseHandle
0x180001a83  add     rsp, 28h
0x180001a87  retn
```
