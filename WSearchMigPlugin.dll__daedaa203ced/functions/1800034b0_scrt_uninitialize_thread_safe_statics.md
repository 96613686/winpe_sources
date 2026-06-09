# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800034b0`
- end: `0x1800034d8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800034b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800034cd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180025C90);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x1800034b0  sub     rsp, 28h
0x1800034b4  lea     rcx, stru_180025C90; lpCriticalSection
0x1800034bb  call    cs:__imp_DeleteCriticalSection
0x1800034c1  mov     rcx, cs:hHandle; hObject
0x1800034c8  test    rcx, rcx
0x1800034cb  jz      short loc_1800034D3
0x1800034cd  call    cs:__imp_CloseHandle
0x1800034d3  add     rsp, 28h
0x1800034d7  retn
```
