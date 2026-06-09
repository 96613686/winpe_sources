# _CommandParamReceiver::operator()_::_1_::dtor$6

- ea: `0x140011cc5`
- end: `0x140011cd1`
- name: `_CommandParamReceiver::operator()_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400083dc`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::operator()_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return optnllib::optional<std::vector<unsigned char>>::~optional<std::vector<unsigned char>>(a2 + 408);
}

```

## disassembly

```asm
0x140011cc5  lea     rcx, [rdx+198h]
0x140011ccc  jmp     ??1?$optional@V?$vector@EV?$allocator@E@std@@@std@@@optnllib@@QEAA@XZ; optnllib::optional<std::vector<uchar>>::~optional<std::vector<uchar>>(void)
```
