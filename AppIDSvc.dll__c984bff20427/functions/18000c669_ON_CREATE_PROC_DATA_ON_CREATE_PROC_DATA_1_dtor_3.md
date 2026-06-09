# _ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor$3

- ea: `0x18000c669`
- end: `0x18000c67c`
- name: `_ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor$3`
- size: `19`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800061b4`

## pseudocode

```c
void __fastcall ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  std::vector<unsigned char>::_Tidy(*(_QWORD *)(a2 + 48) + 160LL);
}

```

## disassembly

```asm
0x18000c669  mov     rcx, [rdx+30h]
0x18000c670  add     rcx, 0A0h
0x18000c677  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
```
