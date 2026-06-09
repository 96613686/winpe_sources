# __scrt_uninitialize_thread_safe_statics

- ea: `0x18000ce10`
- end: `0x18000ce38`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ce10`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000ce1b`
- `KERNEL32!DeleteCriticalSection` at `0x18000ce1b`
- `KERNEL32!CloseHandle` at `0x18000ce2d`
- `KERNEL32!CloseHandle` at `0x18000ce2d`

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
0x18000ce10  sub     rsp, 28h
0x18000ce14  lea     rcx, CriticalSection; lpCriticalSection
0x18000ce1b  call    cs:__imp_DeleteCriticalSection
0x18000ce21  mov     rcx, cs:hHandle; hObject
0x18000ce28  test    rcx, rcx
0x18000ce2b  jz      short loc_18000CE33
0x18000ce2d  call    cs:__imp_CloseHandle
0x18000ce33  add     rsp, 28h
0x18000ce37  retn
```
