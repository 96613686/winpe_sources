# _CThread::CThread_::_1_::dtor$6

- ea: `0x18000a493`
- end: `0x18000a49f`
- name: `_CThread::CThread_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000698c`

## pseudocode

```c
void __fastcall CThread::CThread_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  std::_Alloc_construct_ptr<std::allocator<std::_List_node<CThread *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<CThread *,void *>>>(a2 + 64);
}

```

## disassembly

```asm
0x18000a493  lea     rcx, [rdx+40h]
0x18000a49a  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAVCThread@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<CThread *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<CThread *,void *>>>(void)
```
