# _ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor$4

- ea: `0x18000c682`
- end: `0x18000c695`
- name: `_ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor$4`
- size: `19`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800061b4`

## pseudocode

```c
void __fastcall ON_CREATE_PROC_DATA::_ON_CREATE_PROC_DATA_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  std::vector<unsigned char>::_Tidy(*(_QWORD *)(a2 + 48) + 184LL);
}

```

## disassembly

```asm
0x18000c682  mov     rcx, [rdx+30h]
0x18000c689  add     rcx, 0B8h
0x18000c690  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
```
