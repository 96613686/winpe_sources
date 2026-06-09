# _CTaskCounter::Increment_::_1_::catch$3

- ea: `0x18001e904`
- end: `0x18001e929`
- name: `_CTaskCounter::Increment_::_1_::catch$3`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CTaskCounter::Increment_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -805306219;
  return 0;
}

```

## disassembly

```asm
0x18001e904  mov     [rsp+arg_8], rdx
0x18001e909  push    rbp
0x18001e90a  sub     rsp, 30h
0x18001e90e  mov     rbp, rdx
0x18001e911  mov     dword ptr [rbp+30h], 0D0000095h
0x18001e918  mov     rax, 0
0x18001e922  add     rsp, 30h
0x18001e926  pop     rbp
0x18001e927  retn
```
