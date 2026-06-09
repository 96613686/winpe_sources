# __scrt_uninitialize_thread_safe_statics

- ea: `0x180008790`
- end: `0x1800087b8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000879b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000879b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087ad`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18003AB80);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180008790  sub     rsp, 28h
0x180008794  lea     rcx, stru_18003AB80; lpCriticalSection
0x18000879b  call    cs:__imp_DeleteCriticalSection
0x1800087a1  mov     rcx, cs:hObject; hObject
0x1800087a8  test    rcx, rcx
0x1800087ab  jz      short loc_1800087B3
0x1800087ad  call    cs:__imp_CloseHandle
0x1800087b3  add     rsp, 28h
0x1800087b7  retn
```
