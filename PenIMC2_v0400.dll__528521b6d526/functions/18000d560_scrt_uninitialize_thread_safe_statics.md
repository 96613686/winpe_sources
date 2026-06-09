# __scrt_uninitialize_thread_safe_statics

- ea: `0x18000d560`
- end: `0x18000d588`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d560`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000d57d`
- `KERNEL32!CloseHandle` at `0x18000d57d`
- `KERNEL32!DeleteCriticalSection` at `0x18000d56b`
- `KERNEL32!DeleteCriticalSection` at `0x18000d56b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800188E8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x18000d560  sub     rsp, 28h
0x18000d564  lea     rcx, stru_1800188E8; lpCriticalSection
0x18000d56b  call    cs:__imp_DeleteCriticalSection
0x18000d571  mov     rcx, cs:hHandle; hObject
0x18000d578  test    rcx, rcx
0x18000d57b  jz      short loc_18000D583
0x18000d57d  call    cs:__imp_CloseHandle
0x18000d583  add     rsp, 28h
0x18000d587  retn
```
