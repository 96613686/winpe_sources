# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800036c0`
- end: `0x1800036e8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800036c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800036dd`
- `KERNEL32!CloseHandle` at `0x1800036dd`
- `KERNEL32!DeleteCriticalSection` at `0x1800036cb`
- `KERNEL32!DeleteCriticalSection` at `0x1800036cb`

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
0x1800036c0  sub     rsp, 28h
0x1800036c4  lea     rcx, CriticalSection; lpCriticalSection
0x1800036cb  call    cs:__imp_DeleteCriticalSection
0x1800036d1  mov     rcx, cs:hHandle; hObject
0x1800036d8  test    rcx, rcx
0x1800036db  jz      short loc_1800036E3
0x1800036dd  call    cs:__imp_CloseHandle
0x1800036e3  add     rsp, 28h
0x1800036e7  retn
```
