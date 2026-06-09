# _dynamic_atexit_destructor_for__vhPreviousToken__

- ea: `0x140029f00`
- end: `0x140029f16`
- name: `_dynamic_atexit_destructor_for__vhPreviousToken__`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012a88`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__vhPreviousToken__()
{
  return Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 320LL);
}

```

## disassembly

```asm
0x140029f00  mov     rax, gs:58h
0x140029f09  mov     ecx, 140h
0x140029f0e  add     rcx, [rax]
0x140029f11  jmp     ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
```
