# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002cb0`
- end: `0x180002cd8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002cb0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002cbb`
- `KERNEL32!DeleteCriticalSection` at `0x180002cbb`
- `KERNEL32!CloseHandle` at `0x180002ccd`
- `KERNEL32!CloseHandle` at `0x180002ccd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800975C8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x180002cb0  sub     rsp, 28h
0x180002cb4  lea     rcx, stru_1800975C8; lpCriticalSection
0x180002cbb  call    cs:__imp_DeleteCriticalSection
0x180002cc1  mov     rcx, cs:hHandle; hObject
0x180002cc8  test    rcx, rcx
0x180002ccb  jz      short loc_180002CD3
0x180002ccd  call    cs:__imp_CloseHandle
0x180002cd3  add     rsp, 28h
0x180002cd7  retn
```
