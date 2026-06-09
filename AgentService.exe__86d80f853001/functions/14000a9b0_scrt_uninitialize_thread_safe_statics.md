# __scrt_uninitialize_thread_safe_statics

- ea: `0x14000a9b0`
- end: `0x14000a9d8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000a9b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000a9cd`
- `KERNEL32!CloseHandle` at `0x14000a9cd`
- `KERNEL32!DeleteCriticalSection` at `0x14000a9bb`
- `KERNEL32!DeleteCriticalSection` at `0x14000a9bb`

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
0x14000a9b0  sub     rsp, 28h
0x14000a9b4  lea     rcx, CriticalSection; lpCriticalSection
0x14000a9bb  call    cs:__imp_DeleteCriticalSection
0x14000a9c1  mov     rcx, cs:hHandle; hObject
0x14000a9c8  test    rcx, rcx
0x14000a9cb  jz      short loc_14000A9D3
0x14000a9cd  call    cs:__imp_CloseHandle
0x14000a9d3  add     rsp, 28h
0x14000a9d7  retn
```
