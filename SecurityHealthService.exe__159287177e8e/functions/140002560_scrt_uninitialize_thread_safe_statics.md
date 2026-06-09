# __scrt_uninitialize_thread_safe_statics

- ea: `0x140002560`
- end: `0x140002588`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002560`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000257d`
- `KERNEL32!CloseHandle` at `0x14000257d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000256b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000256b`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_14001B8F8);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x140002560  sub     rsp, 28h
0x140002564  lea     rcx, stru_14001B8F8; lpCriticalSection
0x14000256b  call    cs:__imp_DeleteCriticalSection
0x140002571  mov     rcx, cs:hObject; hObject
0x140002578  test    rcx, rcx
0x14000257b  jz      short loc_140002583
0x14000257d  call    cs:__imp_CloseHandle
0x140002583  add     rsp, 28h
0x140002587  retn
```
