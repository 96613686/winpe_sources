# __scrt_uninitialize_thread_safe_statics

- ea: `0x1400038c0`
- end: `0x1400038e8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400038c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400038cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400038cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400038dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400038dd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1400204A8);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x1400038c0  sub     rsp, 28h
0x1400038c4  lea     rcx, stru_1400204A8; lpCriticalSection
0x1400038cb  call    cs:__imp_DeleteCriticalSection
0x1400038d1  mov     rcx, cs:hObject; hObject
0x1400038d8  test    rcx, rcx
0x1400038db  jz      short loc_1400038E3
0x1400038dd  call    cs:__imp_CloseHandle
0x1400038e3  add     rsp, 28h
0x1400038e7  retn
```
