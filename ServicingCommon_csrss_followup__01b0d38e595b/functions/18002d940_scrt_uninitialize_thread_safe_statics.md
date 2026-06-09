# __scrt_uninitialize_thread_safe_statics

- ea: `0x18002d940`
- end: `0x18002d968`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002d940`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002d95d`
- `KERNEL32!CloseHandle` at `0x18002d95d`
- `KERNEL32!DeleteCriticalSection` at `0x18002d94b`
- `KERNEL32!DeleteCriticalSection` at `0x18002d94b`

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
0x18002d940  sub     rsp, 28h
0x18002d944  lea     rcx, CriticalSection; lpCriticalSection
0x18002d94b  call    cs:__imp_DeleteCriticalSection
0x18002d951  mov     rcx, cs:hHandle; hObject
0x18002d958  test    rcx, rcx
0x18002d95b  jz      short loc_18002D963
0x18002d95d  call    cs:__imp_CloseHandle
0x18002d963  add     rsp, 28h
0x18002d967  retn
```
