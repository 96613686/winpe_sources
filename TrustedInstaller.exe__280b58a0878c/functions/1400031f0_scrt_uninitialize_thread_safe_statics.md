# __scrt_uninitialize_thread_safe_statics

- ea: `0x1400031f0`
- end: `0x140003218`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400031f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400031fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400031fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000320d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000320d`

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
0x1400031f0  sub     rsp, 28h
0x1400031f4  lea     rcx, CriticalSection; lpCriticalSection
0x1400031fb  call    cs:__imp_DeleteCriticalSection
0x140003201  mov     rcx, cs:hHandle; hObject
0x140003208  test    rcx, rcx
0x14000320b  jz      short loc_140003213
0x14000320d  call    cs:__imp_CloseHandle
0x140003213  add     rsp, 28h
0x140003217  retn
```
