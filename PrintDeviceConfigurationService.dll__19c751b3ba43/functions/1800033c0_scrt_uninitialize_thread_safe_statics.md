# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800033c0`
- end: `0x1800033e8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800033c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033dd`

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
0x1800033c0  sub     rsp, 28h
0x1800033c4  lea     rcx, CriticalSection; lpCriticalSection
0x1800033cb  call    cs:__imp_DeleteCriticalSection
0x1800033d1  mov     rcx, cs:hHandle; hObject
0x1800033d8  test    rcx, rcx
0x1800033db  jz      short loc_1800033E3
0x1800033dd  call    cs:__imp_CloseHandle
0x1800033e3  add     rsp, 28h
0x1800033e7  retn
```
