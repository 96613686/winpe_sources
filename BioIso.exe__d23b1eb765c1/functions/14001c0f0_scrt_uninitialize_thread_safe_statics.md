# __scrt_uninitialize_thread_safe_statics

- ea: `0x14001c0f0`
- end: `0x14001c118`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14001c0f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001c0fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001c0fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c10d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c10d`

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
0x14001c0f0  sub     rsp, 28h
0x14001c0f4  lea     rcx, CriticalSection; lpCriticalSection
0x14001c0fb  call    cs:__imp_DeleteCriticalSection
0x14001c101  mov     rcx, cs:hHandle; hObject
0x14001c108  test    rcx, rcx
0x14001c10b  jz      short loc_14001C113
0x14001c10d  call    cs:__imp_CloseHandle
0x14001c113  add     rsp, 28h
0x14001c117  retn
```
