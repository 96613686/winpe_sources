# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800050b0`
- end: `0x1800050d8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800050b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800050bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800050bb`

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
0x1800050b0  sub     rsp, 28h
0x1800050b4  lea     rcx, CriticalSection; lpCriticalSection
0x1800050bb  call    cs:__imp_DeleteCriticalSection
0x1800050c1  mov     rcx, cs:hHandle; hObject
0x1800050c8  test    rcx, rcx
0x1800050cb  jz      short loc_1800050D3
0x1800050cd  call    cs:__imp_CloseHandle
0x1800050d3  add     rsp, 28h
0x1800050d7  retn
```
