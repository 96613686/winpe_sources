# __scrt_uninitialize_thread_safe_statics

- ea: `0x140009ed0`
- end: `0x140009ef8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140009ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140009edb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140009edb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009eed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009eed`

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
0x140009ed0  sub     rsp, 28h
0x140009ed4  lea     rcx, CriticalSection; lpCriticalSection
0x140009edb  call    cs:__imp_DeleteCriticalSection
0x140009ee1  mov     rcx, cs:hHandle; hObject
0x140009ee8  test    rcx, rcx
0x140009eeb  jz      short loc_140009EF3
0x140009eed  call    cs:__imp_CloseHandle
0x140009ef3  add     rsp, 28h
0x140009ef7  retn
```
