# __scrt_uninitialize_thread_safe_statics

- ea: `0x180029a30`
- end: `0x180029a58`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180029a30`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180029a4d`
- `KERNEL32!CloseHandle` at `0x180029a4d`
- `KERNEL32!DeleteCriticalSection` at `0x180029a3b`
- `KERNEL32!DeleteCriticalSection` at `0x180029a3b`

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
0x180029a30  sub     rsp, 28h
0x180029a34  lea     rcx, CriticalSection; lpCriticalSection
0x180029a3b  call    cs:__imp_DeleteCriticalSection
0x180029a41  mov     rcx, cs:hHandle; hObject
0x180029a48  test    rcx, rcx
0x180029a4b  jz      short loc_180029A53
0x180029a4d  call    cs:__imp_CloseHandle
0x180029a53  add     rsp, 28h
0x180029a57  retn
```
