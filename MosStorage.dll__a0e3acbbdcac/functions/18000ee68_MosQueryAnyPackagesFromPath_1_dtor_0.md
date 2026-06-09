# _MosQueryAnyPackagesFromPath_::_1_::dtor$0

- ea: `0x18000ee68`
- end: `0x18000ee74`
- name: `_MosQueryAnyPackagesFromPath_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ae68`

## pseudocode

```c
__int64 __fastcall MosQueryAnyPackagesFromPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<unsigned int>::~vector<unsigned int>(a2 + 32);
}

```

## disassembly

```asm
0x18000ee68  lea     rcx, [rdx+20h]
0x18000ee6f  jmp     ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
```
