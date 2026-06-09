# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800059b0`
- end: `0x1800059d8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800059b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800059bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800059bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800059cd`

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
0x1800059b0  sub     rsp, 28h
0x1800059b4  lea     rcx, CriticalSection; lpCriticalSection
0x1800059bb  call    cs:__imp_DeleteCriticalSection
0x1800059c1  mov     rcx, cs:hObject; hObject
0x1800059c8  test    rcx, rcx
0x1800059cb  jz      short loc_1800059D3
0x1800059cd  call    cs:__imp_CloseHandle
0x1800059d3  add     rsp, 28h
0x1800059d7  retn
```
