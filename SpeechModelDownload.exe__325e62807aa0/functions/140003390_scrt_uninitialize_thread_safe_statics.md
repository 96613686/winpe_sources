# __scrt_uninitialize_thread_safe_statics

- ea: `0x140003390`
- end: `0x1400033b8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003390`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000339b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000339b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400033ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400033ad`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_140030548);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x140003390  sub     rsp, 28h
0x140003394  lea     rcx, stru_140030548; lpCriticalSection
0x14000339b  call    cs:__imp_DeleteCriticalSection
0x1400033a1  mov     rcx, cs:hHandle; hObject
0x1400033a8  test    rcx, rcx
0x1400033ab  jz      short loc_1400033B3
0x1400033ad  call    cs:__imp_CloseHandle
0x1400033b3  add     rsp, 28h
0x1400033b7  retn
```
