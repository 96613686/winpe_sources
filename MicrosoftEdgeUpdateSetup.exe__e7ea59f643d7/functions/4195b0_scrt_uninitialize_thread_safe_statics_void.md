# __scrt_uninitialize_thread_safe_statics(void)

- ea: `0x4195b0`
- end: `0x4195cc`
- name: `?__scrt_uninitialize_thread_safe_statics@@YAXXZ`
- size: `28`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x4195b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x4195c5`
- `KERNEL32!CloseHandle` at `0x4195c5`
- `KERNEL32!DeleteCriticalSection` at `0x4195b5`
- `KERNEL32!DeleteCriticalSection` at `0x4195b5`

## pseudocode

```c
void __cdecl __scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x4195b0  push    offset CriticalSection; lpCriticalSection
0x4195b5  call    ds:DeleteCriticalSection
0x4195bb  mov     eax, hHandle
0x4195c0  test    eax, eax
0x4195c2  jz      short locret_4195CB
0x4195c4  push    eax; hObject
0x4195c5  call    ds:CloseHandle
0x4195cb  retn
```
