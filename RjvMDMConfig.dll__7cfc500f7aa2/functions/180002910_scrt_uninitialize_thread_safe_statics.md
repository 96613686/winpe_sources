# __scrt_uninitialize_thread_safe_statics

- ea: `0x180002910`
- end: `0x180002938`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000291b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000291b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000292d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000292d`

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
0x180002910  sub     rsp, 28h
0x180002914  lea     rcx, CriticalSection; lpCriticalSection
0x18000291b  call    cs:__imp_DeleteCriticalSection
0x180002921  mov     rcx, cs:hHandle; hObject
0x180002928  test    rcx, rcx
0x18000292b  jz      short loc_180002933
0x18000292d  call    cs:__imp_CloseHandle
0x180002933  add     rsp, 28h
0x180002937  retn
```
