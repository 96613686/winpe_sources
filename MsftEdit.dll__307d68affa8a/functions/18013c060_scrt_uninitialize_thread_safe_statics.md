# __scrt_uninitialize_thread_safe_statics

- ea: `0x18013c060`
- end: `0x18013c088`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18013c060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18013c06b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18013c06b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013c07d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18013c07d`

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
0x18013c060  sub     rsp, 28h
0x18013c064  lea     rcx, CriticalSection; lpCriticalSection
0x18013c06b  call    cs:__imp_DeleteCriticalSection
0x18013c071  mov     rcx, cs:hHandle; hObject
0x18013c078  test    rcx, rcx
0x18013c07b  jz      short loc_18013C083
0x18013c07d  call    cs:__imp_CloseHandle
0x18013c083  add     rsp, 28h
0x18013c087  retn
```
