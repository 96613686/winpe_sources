# _dynamic_initializer_for__gs_missCache__

- ea: `0x180001ce0`
- end: `0x180001d26`
- name: `_dynamic_initializer_for__gs_missCache__`
- size: `70`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002718`
- `0x18000656c`
- `0x1800066c8`

## pseudocode

```c
int dynamic_initializer_for__gs_missCache__()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  int v3; // r9d

  qword_180012C10 = std::_List_alloc<0,std::_List_base_types<unsigned long>>::_Buynode0();
  xmmword_180012C20 = 0;
  qword_180012C30 = 0;
  dword_180012C48 = 1065353216;
  std::_Hash<stdext::_Hset_traits<unsigned long,stdext::hash_compare<unsigned long,std::less<unsigned long>>,std::allocator<unsigned long>,0>>::_Init(
    v1,
    v0,
    v2,
    v3);
  return atexit(dynamic_atexit_destructor_for__gs_missCache__);
}

```

## disassembly

```asm
0x180001ce0  sub     rsp, 28h
0x180001ce4  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@KV?$allocator@K@std@@@std@@@std@@QEAAPEAU?$_List_node@KPEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<ulong>>::_Buynode0(std::_List_node<ulong,void *> *,std::_List_node<ulong,void *> *)
0x180001ce9  mov     cs:qword_180012C10, rax
0x180001cf0  xorps   xmm0, xmm0
0x180001cf3  movdqa  cs:xmmword_180012C20, xmm0
0x180001cfb  mov     cs:qword_180012C30, 0
0x180001d06  mov     cs:dword_180012C48, 3F800000h
0x180001d10  call    ?_Init@?$_Hash@V?$_Hset_traits@KV?$hash_compare@KU?$less@K@std@@@stdext@@V?$allocator@K@std@@$0A@@stdext@@@std@@IEAAX_K@Z; std::_Hash<stdext::_Hset_traits<ulong,stdext::hash_compare<ulong,std::less<ulong>>,std::allocator<ulong>,0>>::_Init(unsigned __int64)
0x180001d15  nop
0x180001d16  lea     rcx, _dynamic_atexit_destructor_for__gs_missCache__
0x180001d1d  add     rsp, 28h
0x180001d21  jmp     atexit
```
