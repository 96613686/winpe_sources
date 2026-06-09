# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800021d0`
- end: `0x1800021f8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800021d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800021db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800021db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021ed`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_1800103E8);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x1800021d0  sub     rsp, 28h
0x1800021d4  lea     rcx, stru_1800103E8; lpCriticalSection
0x1800021db  call    cs:__imp_DeleteCriticalSection
0x1800021e1  mov     rcx, cs:hHandle; hObject
0x1800021e8  test    rcx, rcx
0x1800021eb  jz      short loc_1800021F3
0x1800021ed  call    cs:__imp_CloseHandle
0x1800021f3  add     rsp, 28h
0x1800021f7  retn
```
