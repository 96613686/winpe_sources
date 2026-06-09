# _CommandParamReceiver::operator()_::_1_::dtor$3

- ea: `0x140011c8f`
- end: `0x140011c9b`
- name: `_CommandParamReceiver::operator()_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008524`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::operator()_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char,wil::secure_allocator<unsigned char>>::~vector<unsigned char,wil::secure_allocator<unsigned char>>(a2 + 312);
}

```

## disassembly

```asm
0x140011c8f  lea     rcx, [rdx+138h]
0x140011c96  jmp     ??1?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::~vector<uchar,wil::secure_allocator<uchar>>(void)
```
