# _ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor$3

- ea: `0x18000c596`
- end: `0x18000c5a9`
- name: `_ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor$3`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800061b4`

## pseudocode

```c
__int64 __fastcall ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::_Tidy(*(_QWORD *)(a2 + 56) + 160LL);
}

```

## disassembly

```asm
0x18000c596  mov     rcx, [rdx+38h]
0x18000c59d  add     rcx, 0A0h
0x18000c5a4  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
```
