# __scrt_uninitialize_thread_safe_statics

- ea: `0x180001a40`
- end: `0x180001a68`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001a40`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180001a5d`
- `KERNEL32!CloseHandle` at `0x180001a5d`
- `KERNEL32!DeleteCriticalSection` at `0x180001a4b`
- `KERNEL32!DeleteCriticalSection` at `0x180001a4b`

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
0x180001a40  sub     rsp, 28h
0x180001a44  lea     rcx, CriticalSection; lpCriticalSection
0x180001a4b  call    cs:__imp_DeleteCriticalSection
0x180001a51  mov     rcx, cs:hHandle; hObject
0x180001a58  test    rcx, rcx
0x180001a5b  jz      short loc_180001A63
0x180001a5d  call    cs:__imp_CloseHandle
0x180001a63  add     rsp, 28h
0x180001a67  retn
```
