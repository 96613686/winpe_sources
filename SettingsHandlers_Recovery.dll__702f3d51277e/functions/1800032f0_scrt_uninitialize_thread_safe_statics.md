# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800032f0`
- end: `0x180003318`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800032f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800032fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800032fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000330d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000330d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180059C18);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x1800032f0  sub     rsp, 28h
0x1800032f4  lea     rcx, stru_180059C18; lpCriticalSection
0x1800032fb  call    cs:__imp_DeleteCriticalSection
0x180003301  mov     rcx, cs:hHandle; hObject
0x180003308  test    rcx, rcx
0x18000330b  jz      short loc_180003313
0x18000330d  call    cs:__imp_CloseHandle
0x180003313  add     rsp, 28h
0x180003317  retn
```
