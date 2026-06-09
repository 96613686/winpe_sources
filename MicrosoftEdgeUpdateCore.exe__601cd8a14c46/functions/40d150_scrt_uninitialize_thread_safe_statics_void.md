# __scrt_uninitialize_thread_safe_statics(void)

- ea: `0x40d150`
- end: `0x40d16c`
- name: `?__scrt_uninitialize_thread_safe_statics@@YAXXZ`
- size: `28`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40d150`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x40d155`
- `KERNEL32!DeleteCriticalSection` at `0x40d155`
- `KERNEL32!CloseHandle` at `0x40d165`
- `KERNEL32!CloseHandle` at `0x40d165`

## pseudocode

```c
void __cdecl __scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&stru_43DCA4);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x40d150  push    offset stru_43DCA4; lpCriticalSection
0x40d155  call    ds:DeleteCriticalSection
0x40d15b  mov     eax, hHandle
0x40d160  test    eax, eax
0x40d162  jz      short locret_40D16B
0x40d164  push    eax; hObject
0x40d165  call    ds:CloseHandle
0x40d16b  retn
```
