# PCLmWriter::DictionaryObject::~DictionaryObject(void)

- ea: `0x180011a00`
- end: `0x180011a33`
- name: `??1DictionaryObject@PCLmWriter@@UEAA@XZ`
- size: `51`
- prototype: `void __fastcall(PCLmWriter::DictionaryObject *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180012100`
- `0x1800199e0`
- `0x18001e01c`

## callees

- `0x18000efa8`
- `0x1800101cc`
- `0x180011a00`

## pseudocode

```c
void __fastcall PCLmWriter::DictionaryObject::~DictionaryObject(PCLmWriter::DictionaryObject *this)
{
  std::_Ref_count_base *v2; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    (_QWORD *)this + 3,
    (__int64)this + 24);
  *(_QWORD *)this = &PCLmWriter::IObject::`vftable';
}

```

## disassembly

```asm
0x180011a00  push    rbx
0x180011a02  sub     rsp, 20h
0x180011a06  mov     rbx, rcx
0x180011a09  mov     rcx, [rcx+30h]; this
0x180011a0d  test    rcx, rcx
0x180011a10  jz      short loc_180011A17
0x180011a12  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011a17  lea     rcx, [rbx+18h]
0x180011a1b  mov     rdx, rcx
0x180011a1e  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x180011a23  lea     rax, ??_7IObject@PCLmWriter@@6B@; const PCLmWriter::IObject::`vftable'
0x180011a2a  mov     [rbx], rax
0x180011a2d  add     rsp, 20h
0x180011a31  pop     rbx
0x180011a32  retn
```
