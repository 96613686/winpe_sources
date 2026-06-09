# __dynamic_initializer_for__gs_missCache___::_1_::dtor$1

- ea: `0x18000baf1`
- end: `0x18000bafd`
- name: `__dynamic_initializer_for__gs_missCache___::_1_::dtor$1`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003c7c`

## pseudocode

```c
__int64 _dynamic_initializer_for__gs_missCache___::_1_::dtor_1()
{
  return std::list<unsigned long>::~list<unsigned long>(&qword_180012C10);
}

```

## disassembly

```asm
0x18000baf1  lea     rcx, qword_180012C10
0x18000baf8  jmp     ??1?$list@KV?$allocator@K@std@@@std@@QEAA@XZ; std::list<ulong>::~list<ulong>(void)
```
