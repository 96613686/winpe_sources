# _CommandParamReceiver::operator()_::_1_::dtor$4

- ea: `0x140011ca1`
- end: `0x140011cad`
- name: `_CommandParamReceiver::operator()_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400083bc`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::operator()_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return optnllib::optional<std::vector<unsigned char,wil::secure_allocator<unsigned char>>>::~optional<std::vector<unsigned char,wil::secure_allocator<unsigned char>>>(a2 + 368);
}

```

## disassembly

```asm
0x140011ca1  lea     rcx, [rdx+170h]
0x140011ca8  jmp     ??1?$optional@V?$vector@EU?$secure_allocator@E@wil@@@std@@@optnllib@@QEAA@XZ; optnllib::optional<std::vector<uchar,wil::secure_allocator<uchar>>>::~optional<std::vector<uchar,wil::secure_allocator<uchar>>>(void)
```
