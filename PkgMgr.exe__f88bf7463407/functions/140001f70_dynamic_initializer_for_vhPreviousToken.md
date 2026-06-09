# _dynamic_initializer_for__vhPreviousToken__

- ea: `0x140001f70`
- end: `0x140001f95`
- name: `_dynamic_initializer_for__vhPreviousToken__`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002fa8`

## pseudocode

```c
__int64 dynamic_initializer_for__vhPreviousToken__()
{
  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 320LL) = 0;
  return _tlregdtor(dynamic_atexit_destructor_for__vhPreviousToken__);
}

```

## disassembly

```asm
0x140001f70  mov     rax, gs:58h
0x140001f79  mov     edx, 140h
0x140001f7e  mov     rcx, [rax]
0x140001f81  mov     qword ptr [rdx+rcx], 0
0x140001f89  lea     rcx, _dynamic_atexit_destructor_for__vhPreviousToken__
0x140001f90  jmp     __tlregdtor
```
