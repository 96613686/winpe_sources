# _CommandParamReceiver::CreateInstance_::_1_::dtor$8

- ea: `0x140011e1a`
- end: `0x140011e26`
- name: `_CommandParamReceiver::CreateInstance_::_1_::dtor$8`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008524`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::CreateInstance_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char,wil::secure_allocator<unsigned char>>::~vector<unsigned char,wil::secure_allocator<unsigned char>>(a2 + 216);
}

```

## disassembly

```asm
0x140011e1a  lea     rcx, [rdx+0D8h]
0x140011e21  jmp     ??1?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::~vector<uchar,wil::secure_allocator<uchar>>(void)
```
