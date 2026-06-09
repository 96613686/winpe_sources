# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800044d0`
- end: `0x1800044f8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800044d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800044db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800044db`

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
0x1800044d0  sub     rsp, 28h
0x1800044d4  lea     rcx, CriticalSection; lpCriticalSection
0x1800044db  call    cs:__imp_DeleteCriticalSection
0x1800044e1  mov     rcx, cs:hHandle; hObject
0x1800044e8  test    rcx, rcx
0x1800044eb  jz      short loc_1800044F3
0x1800044ed  call    cs:__imp_CloseHandle
0x1800044f3  add     rsp, 28h
0x1800044f7  retn
```
