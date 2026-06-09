# __scrt_uninitialize_thread_safe_statics

- ea: `0x180004ff0`
- end: `0x180005018`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004ff0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000500d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000500d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004ffb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004ffb`

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
0x180004ff0  sub     rsp, 28h
0x180004ff4  lea     rcx, CriticalSection; lpCriticalSection
0x180004ffb  call    cs:__imp_DeleteCriticalSection
0x180005001  mov     rcx, cs:hHandle; hObject
0x180005008  test    rcx, rcx
0x18000500b  jz      short loc_180005013
0x18000500d  call    cs:__imp_CloseHandle
0x180005013  add     rsp, 28h
0x180005017  retn
```
