# __scrt_uninitialize_thread_safe_statics

- ea: `0x180001620`
- end: `0x180001648`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001620`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000163d`
- `KERNEL32!CloseHandle` at `0x18000163d`
- `KERNEL32!DeleteCriticalSection` at `0x18000162b`
- `KERNEL32!DeleteCriticalSection` at `0x18000162b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180001620  sub     rsp, 28h
0x180001624  lea     rcx, CriticalSection; lpCriticalSection
0x18000162b  call    cs:__imp_DeleteCriticalSection
0x180001631  mov     rcx, cs:hObject; hObject
0x180001638  test    rcx, rcx
0x18000163b  jz      short loc_180001643
0x18000163d  call    cs:__imp_CloseHandle
0x180001643  add     rsp, 28h
0x180001647  retn
```
