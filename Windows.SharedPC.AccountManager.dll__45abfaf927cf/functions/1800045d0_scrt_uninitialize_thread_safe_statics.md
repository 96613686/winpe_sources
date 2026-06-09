# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800045d0`
- end: `0x1800045f8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800045d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800045db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800045db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045ed`

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
0x1800045d0  sub     rsp, 28h
0x1800045d4  lea     rcx, CriticalSection; lpCriticalSection
0x1800045db  call    cs:__imp_DeleteCriticalSection
0x1800045e1  mov     rcx, cs:hHandle; hObject
0x1800045e8  test    rcx, rcx
0x1800045eb  jz      short loc_1800045F3
0x1800045ed  call    cs:__imp_CloseHandle
0x1800045f3  add     rsp, 28h
0x1800045f7  retn
```
