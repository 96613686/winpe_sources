# __scrt_uninitialize_thread_safe_statics

- ea: `0x18001bbe0`
- end: `0x18001bc08`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001bbe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001bbeb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001bbeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bbfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bbfd`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hEvent )
    CloseHandle(hEvent);
}

```

## disassembly

```asm
0x18001bbe0  sub     rsp, 28h
0x18001bbe4  lea     rcx, CriticalSection; lpCriticalSection
0x18001bbeb  call    cs:__imp_DeleteCriticalSection
0x18001bbf1  mov     rcx, cs:hEvent; hObject
0x18001bbf8  test    rcx, rcx
0x18001bbfb  jz      short loc_18001BC03
0x18001bbfd  call    cs:__imp_CloseHandle
0x18001bc03  add     rsp, 28h
0x18001bc07  retn
```
