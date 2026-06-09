# __scrt_uninitialize_thread_safe_statics

- ea: `0x1800046d0`
- end: `0x1800046f8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800046d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800046db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800046db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046ed`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18004A470);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x1800046d0  sub     rsp, 28h
0x1800046d4  lea     rcx, stru_18004A470; lpCriticalSection
0x1800046db  call    cs:__imp_DeleteCriticalSection
0x1800046e1  mov     rcx, cs:hHandle; hObject
0x1800046e8  test    rcx, rcx
0x1800046eb  jz      short loc_1800046F3
0x1800046ed  call    cs:__imp_CloseHandle
0x1800046f3  add     rsp, 28h
0x1800046f7  retn
```
