# _CommandParamReceiver::GetKcv_::_1_::dtor$2

- ea: `0x140011e9e`
- end: `0x140011eaa`
- name: `_CommandParamReceiver::GetKcv_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008524`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::GetKcv_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char,wil::secure_allocator<unsigned char>>::~vector<unsigned char,wil::secure_allocator<unsigned char>>(a2 + 120);
}

```

## disassembly

```asm
0x140011e9e  lea     rcx, [rdx+78h]
0x140011ea5  jmp     ??1?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::~vector<uchar,wil::secure_allocator<uchar>>(void)
```
