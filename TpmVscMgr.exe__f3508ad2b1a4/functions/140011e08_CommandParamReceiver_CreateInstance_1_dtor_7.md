# _CommandParamReceiver::CreateInstance_::_1_::dtor$7

- ea: `0x140011e08`
- end: `0x140011e14`
- name: `_CommandParamReceiver::CreateInstance_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008524`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::CreateInstance_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char,wil::secure_allocator<unsigned char>>::~vector<unsigned char,wil::secure_allocator<unsigned char>>(a2 + 240);
}

```

## disassembly

```asm
0x140011e08  lea     rcx, [rdx+0F0h]
0x140011e0f  jmp     ??1?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::~vector<uchar,wil::secure_allocator<uchar>>(void)
```
