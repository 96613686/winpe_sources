# _CThread::CThread_::_1_::dtor$3

- ea: `0x18000a46f`
- end: `0x18000a47b`
- name: `_CThread::CThread_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800069e8`

## pseudocode

```c
void __fastcall CThread::CThread_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(a2 + 48);
}

```

## disassembly

```asm
0x18000a46f  lea     rcx, [rdx+30h]
0x18000a476  jmp     ??1?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAA@XZ; locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(void)
```
