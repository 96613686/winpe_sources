# _CThread::Exit_::_1_::dtor$0

- ea: `0x18000a4da`
- end: `0x18000a4e6`
- name: `_CThread::Exit_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800069e8`

## pseudocode

```c
void __fastcall CThread::Exit_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(a2 + 32);
}

```

## disassembly

```asm
0x18000a4da  lea     rcx, [rdx+20h]
0x18000a4e1  jmp     ??1?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAA@XZ; locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(void)
```
