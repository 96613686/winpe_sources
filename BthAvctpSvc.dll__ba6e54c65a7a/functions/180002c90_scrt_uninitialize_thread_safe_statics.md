# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002c90`
- end: `0x180002cb8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002c90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002c9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002c9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002cad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002cad`

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
0x180002c90  sub     rsp, 28h
0x180002c94  lea     rcx, CriticalSection; lpCriticalSection
0x180002c9b  call    cs:__imp_DeleteCriticalSection
0x180002ca1  mov     rcx, cs:hHandle; hObject
0x180002ca8  test    rcx, rcx
0x180002cab  jz      short loc_180002CB3
0x180002cad  call    cs:__imp_CloseHandle
0x180002cb3  add     rsp, 28h
0x180002cb7  retn
```
