# _PolicyModel::CFileHash::Deserialize_::_1_::dtor$4

- ea: `0x140014eef`
- end: `0x140014efb`
- name: `_PolicyModel::CFileHash::Deserialize_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000fef8`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFileHash::Deserialize_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::vector<unsigned short>::~vector<unsigned short>(a2 + 32);
}

```

## disassembly

```asm
0x140014eef  lea     rcx, [rdx+20h]
0x140014ef6  jmp     ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
```
