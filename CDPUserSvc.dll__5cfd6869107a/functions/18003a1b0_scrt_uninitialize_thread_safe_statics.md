# __scrt_uninitialize_thread_safe_statics

- ea: `0x18003a1b0`
- end: `0x18003a1d8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003a1b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a1bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a1bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a1cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a1cd`

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
0x18003a1b0  sub     rsp, 28h
0x18003a1b4  lea     rcx, CriticalSection; lpCriticalSection
0x18003a1bb  call    cs:__imp_DeleteCriticalSection
0x18003a1c1  mov     rcx, cs:hHandle; hObject
0x18003a1c8  test    rcx, rcx
0x18003a1cb  jz      short loc_18003A1D3
0x18003a1cd  call    cs:__imp_CloseHandle
0x18003a1d3  add     rsp, 28h
0x18003a1d7  retn
```
