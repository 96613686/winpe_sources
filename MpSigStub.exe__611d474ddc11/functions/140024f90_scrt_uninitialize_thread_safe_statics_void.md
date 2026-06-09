# __scrt_uninitialize_thread_safe_statics(void)

- ea: `0x140024f90`
- end: `0x140024fb8`
- name: `?__scrt_uninitialize_thread_safe_statics@@YAXXZ`
- size: `40`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140024f90`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140024fad`
- `KERNEL32!CloseHandle` at `0x140024fad`
- `KERNEL32!DeleteCriticalSection` at `0x140024f9b`
- `KERNEL32!DeleteCriticalSection` at `0x140024f9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __scrt_uninitialize_thread_safe_statics()
{
  DeleteCriticalSection(&CriticalSection);
  if ( hHandle )
    CloseHandle(hHandle);
}

```

## disassembly

```asm
0x140024f90  sub     rsp, 28h
0x140024f94  lea     rcx, CriticalSection; lpCriticalSection
0x140024f9b  call    cs:DeleteCriticalSection
0x140024fa1  mov     rcx, cs:hHandle; hObject
0x140024fa8  test    rcx, rcx
0x140024fab  jz      short loc_140024FB3
0x140024fad  call    cs:CloseHandle
0x140024fb3  add     rsp, 28h
0x140024fb7  retn
```
