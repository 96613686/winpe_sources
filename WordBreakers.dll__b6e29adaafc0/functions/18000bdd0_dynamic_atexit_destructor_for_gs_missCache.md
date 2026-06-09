# _dynamic_atexit_destructor_for__gs_missCache__

- ea: `0x18000bdd0`
- end: `0x18000bddc`
- name: `_dynamic_atexit_destructor_for__gs_missCache__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003c08`

## pseudocode

```c
void dynamic_atexit_destructor_for__gs_missCache__()
{
  std::_Hash<stdext::_Hset_traits<unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<unsigned long>,0>>::~_Hash<stdext::_Hset_traits<unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<unsigned long>,0>>((__int64)&qword_180012C10);
}

```

## disassembly

```asm
0x18000bdd0  lea     rcx, qword_180012C10
0x18000bdd7  jmp     ??1?$_Hash@V?$_Hset_traits@KV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@K@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<ulong>,0>>::~_Hash<stdext::_Hset_traits<ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<ulong>,0>>(void)
```
