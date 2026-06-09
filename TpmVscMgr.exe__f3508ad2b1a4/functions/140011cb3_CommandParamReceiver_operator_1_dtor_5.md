# _CommandParamReceiver::operator()_::_1_::dtor$5

- ea: `0x140011cb3`
- end: `0x140011cbf`
- name: `_CommandParamReceiver::operator()_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008524`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::operator()_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char,wil::secure_allocator<unsigned char>>::~vector<unsigned char,wil::secure_allocator<unsigned char>>(a2 + 280);
}

```

## disassembly

```asm
0x140011cb3  lea     rcx, [rdx+118h]
0x140011cba  jmp     ??1?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::~vector<uchar,wil::secure_allocator<uchar>>(void)
```
