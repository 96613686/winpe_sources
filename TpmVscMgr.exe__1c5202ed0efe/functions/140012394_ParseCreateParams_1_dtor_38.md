# _ParseCreateParams_::_1_::dtor$38

- ea: `0x140012394`
- end: `0x1400123a0`
- name: `_ParseCreateParams_::_1_::dtor$38`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008530`

## pseudocode

```c
void __fastcall ParseCreateParams_::_1_::dtor_38(__int64 a1, __int64 a2)
{
  std::vector<unsigned char>::~vector<unsigned char>((char **)(a2 + 136));
}

```

## disassembly

```asm
0x140012394  lea     rcx, [rdx+88h]
0x14001239b  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
