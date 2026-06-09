# __scrt_uninitialize_thread_safe_statics

- ea: `0x1832ce530`
- end: `0x1832ce558`
- name: `__scrt_uninitialize_thread_safe_statics`
- size: `40`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1832ce530`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1832ce53b`
- `KERNEL32!DeleteCriticalSection` at `0x1832ce53b`
- `KERNEL32!CloseHandle` at `0x1832ce54d`
- `KERNEL32!CloseHandle` at `0x1832ce54d`

## pseudocode

```c
void __fastcall _scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_18371FB58);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x1832ce530  sub     rsp, 28h
0x1832ce534  lea     rcx, stru_18371FB58; lpCriticalSection
0x1832ce53b  call    cs:__imp_DeleteCriticalSection
0x1832ce541  mov     rcx, cs:hHandle; hObject
0x1832ce548  test    rcx, rcx
0x1832ce54b  jz      short loc_1832CE553
0x1832ce54d  call    cs:__imp_CloseHandle
0x1832ce553  add     rsp, 28h
0x1832ce557  retn
```
