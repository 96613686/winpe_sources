# __scrt_uninitialize_thread_safe_statics

- ea: `0x140001ac0`
- end: `0x140001ae8`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001ac0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140001add`
- `KERNEL32!CloseHandle` at `0x140001add`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001acb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001acb`

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
0x140001ac0  sub     rsp, 28h
0x140001ac4  lea     rcx, CriticalSection; lpCriticalSection
0x140001acb  call    cs:__imp_DeleteCriticalSection
0x140001ad1  mov     rcx, cs:hHandle; hObject
0x140001ad8  test    rcx, rcx
0x140001adb  jz      short loc_140001AE3
0x140001add  call    cs:__imp_CloseHandle
0x140001ae3  add     rsp, 28h
0x140001ae7  retn
```
