# _std::map_unsigned___int64_std::unique_ptr_IPxlatInterface_std::default_delete_IPxlatInterface____std::less_unsigned___int64__std::allocator_std::pair_unsigned___int64_const__std::unique_ptr_IPxlatInterface_std::default_delete_IPxlatInterface_________::insert_std::pair_unsigned___int64_std::unique_ptr_IPxlatInterface_std::default_delete_IPxlatInterface______0__::_1_::dtor$2

- ea: `0x1800186ac`
- end: `0x1800186b8`
- name: `_std::map_unsigned___int64_std::unique_ptr_IPxlatInterface_std::default_delete_IPxlatInterface____std::less_unsigned___int64__std::allocator_std::pair_unsigned___int64_const__std::unique_ptr_IPxlatInterface_std::default_delete_IPxlatInterface_________::insert_std::pair_unsigned___int64_std::unique_ptr_IPxlatInterface_std::default_delete_IPxlatInterface______0__::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f23c`

## pseudocode

```c
void __fastcall std::map_unsigned___int64_std::unique_ptr_IPxlatInterface_std::default_delete_IPxlatInterface____std::less_unsigned___int64__std::allocator_std::pair_unsigned___int64_const__std::unique_ptr_IPxlatInterface_std::default_delete_IPxlatInterface_________::insert_std::pair_unsigned___int64_std::unique_ptr_IPxlatInterface_std::default_delete_IPxlatInterface______0__::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x1800186ac  lea     rcx, [rdx+20h]
0x1800186b3  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>(void)
```
