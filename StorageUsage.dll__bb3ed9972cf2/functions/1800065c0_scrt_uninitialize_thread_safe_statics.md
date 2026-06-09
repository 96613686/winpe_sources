# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800065c0`
- end: `0x1800065e8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800065c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800065cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800065cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065dd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x1800065c0  sub     rsp, 28h
0x1800065c4  lea     rcx, CriticalSection; lpCriticalSection
0x1800065cb  call    cs:__imp_DeleteCriticalSection
0x1800065d1  mov     rcx, cs:hObject; hObject
0x1800065d8  test    rcx, rcx
0x1800065db  jz      short loc_1800065E3
0x1800065dd  call    cs:__imp_CloseHandle
0x1800065e3  add     rsp, 28h
0x1800065e7  retn
```
