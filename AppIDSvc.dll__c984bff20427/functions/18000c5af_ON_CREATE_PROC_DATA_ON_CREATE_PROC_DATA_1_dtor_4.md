# _ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor$4

- ea: `0x18000c5af`
- end: `0x18000c5c2`
- name: `_ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor$4`
- size: `19`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800061b4`

## pseudocode

```c
void __fastcall ON_CREATE_PROC_DATA::ON_CREATE_PROC_DATA_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  std::vector<unsigned char>::_Tidy(*(_QWORD *)(a2 + 56) + 184LL);
}

```

## disassembly

```asm
0x18000c5af  mov     rcx, [rdx+38h]
0x18000c5b6  add     rcx, 0B8h
0x18000c5bd  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
```
