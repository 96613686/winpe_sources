# _RegistryKey::GetValueString_::_1_::dtor$0

- ea: `0x180014256`
- end: `0x180014262`
- name: `_RegistryKey::GetValueString_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000d790`

## pseudocode

```c
__int64 __fastcall RegistryKey::GetValueString_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::~vector<unsigned char>(a2 + 56);
}

```

## disassembly

```asm
0x180014256  lea     rcx, [rdx+38h]
0x18001425d  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
