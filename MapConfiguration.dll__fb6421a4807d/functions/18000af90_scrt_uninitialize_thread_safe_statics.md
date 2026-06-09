# __scrt_uninitialize_thread_safe_statics

- ea: `0x18000af90`
- end: `0x18000afb8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000af90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afad`

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
0x18000af90  sub     rsp, 28h
0x18000af94  lea     rcx, CriticalSection; lpCriticalSection
0x18000af9b  call    cs:__imp_DeleteCriticalSection
0x18000afa1  mov     rcx, cs:hHandle; hObject
0x18000afa8  test    rcx, rcx
0x18000afab  jz      short loc_18000AFB3
0x18000afad  call    cs:__imp_CloseHandle
0x18000afb3  add     rsp, 28h
0x18000afb7  retn
```
