# __scrt_uninitialize_thread_safe_statics

- ea: `0x18000d920`
- end: `0x18000d948`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d92b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d92b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d93d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d93d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_180066088);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x18000d920  sub     rsp, 28h
0x18000d924  lea     rcx, stru_180066088; lpCriticalSection
0x18000d92b  call    cs:__imp_DeleteCriticalSection
0x18000d931  mov     rcx, cs:hHandle; hObject
0x18000d938  test    rcx, rcx
0x18000d93b  jz      short loc_18000D943
0x18000d93d  call    cs:__imp_CloseHandle
0x18000d943  add     rsp, 28h
0x18000d947  retn
```
