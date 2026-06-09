# __scrt_uninitialize_thread_safe_statics

- ea: `0x18000cb60`
- end: `0x18000cb88`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000cb60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cb6b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cb6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb7d`

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
0x18000cb60  sub     rsp, 28h
0x18000cb64  lea     rcx, CriticalSection; lpCriticalSection
0x18000cb6b  call    cs:__imp_DeleteCriticalSection
0x18000cb71  mov     rcx, cs:hHandle; hObject
0x18000cb78  test    rcx, rcx
0x18000cb7b  jz      short loc_18000CB83
0x18000cb7d  call    cs:__imp_CloseHandle
0x18000cb83  add     rsp, 28h
0x18000cb87  retn
```
