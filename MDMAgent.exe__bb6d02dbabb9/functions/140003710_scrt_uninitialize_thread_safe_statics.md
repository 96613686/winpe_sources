# __scrt_uninitialize_thread_safe_statics

- ea: `0x140003710`
- end: `0x140003738`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000371b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000371b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000372d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000372d`

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
0x140003710  sub     rsp, 28h
0x140003714  lea     rcx, CriticalSection; lpCriticalSection
0x14000371b  call    cs:__imp_DeleteCriticalSection
0x140003721  mov     rcx, cs:hHandle; hObject
0x140003728  test    rcx, rcx
0x14000372b  jz      short loc_140003733
0x14000372d  call    cs:__imp_CloseHandle
0x140003733  add     rsp, 28h
0x140003737  retn
```
