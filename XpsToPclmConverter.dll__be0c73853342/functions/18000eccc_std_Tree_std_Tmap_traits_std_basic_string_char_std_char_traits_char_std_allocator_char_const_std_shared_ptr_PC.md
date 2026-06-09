# std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *)

- ea: `0x18000eccc`
- end: `0x18000edb7`
- name: `??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@PEAU21@0@Z`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e87c`
- `0x18000eccc`

## callees

- `0x180001f6c`
- `0x18000e7c8`
- `0x18000eccc`
- `0x18000f398`
- `0x18000f5bc`
- `0x18000f5e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Copy_nodes<0>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbp
  _QWORD *v7; // rsi
  __int64 *v9; // [rsp+20h] [rbp-58h] BYREF
  __int64 *v10; // [rsp+28h] [rbp-50h]
  _QWORD *v11; // [rsp+30h] [rbp-48h]

  v6 = *a1;
  if ( *(_BYTE *)(a2 + 25) )
    return (_QWORD *)*a1;
  v9 = a1;
  v7 = operator new(0x50u);
  std::string::string(v7 + 4);
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v7 + 8, (_QWORD *)(a2 + 64));
  *v7 = v6;
  v7[1] = v6;
  v7[2] = v6;
  *((_WORD *)v7 + 12) = 0;
  v10 = 0;
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(&v9);
  v7[1] = a3;
  *((_BYTE *)v7 + 24) = *(_BYTE *)(a2 + 24);
  v9 = a1;
  v10 = a1;
  v11 = v7;
  *v7 = std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Copy_nodes<0>(
          a1,
          *(_QWORD *)a2,
          v7);
  v7[2] = std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Copy_nodes<0>(
            a1,
            *(_QWORD *)(a2 + 16),
            v7);
  v9 = 0;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(&v9);
  return v7;
}

```

## disassembly

```asm
0x18000eccc  push    rbx
0x18000ecce  push    rbp
0x18000eccf  push    rsi
0x18000ecd0  push    rdi
0x18000ecd1  push    r12
0x18000ecd3  push    r14
0x18000ecd5  push    r15
0x18000ecd7  sub     rsp, 40h
0x18000ecdb  mov     r12, r8
0x18000ecde  mov     r15, rdx
0x18000ece1  mov     r14, rcx
0x18000ece4  mov     rbp, [rcx]
0x18000ece7  cmp     byte ptr [rdx+19h], 0
0x18000eceb  jnz     loc_18000EDA2
0x18000ecf1  mov     [rsp+78h+var_58], rcx
0x18000ecf6  mov     [rsp+78h+var_50], 0
0x18000ecff  mov     ecx, 50h ; 'P'; Size
0x18000ed04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ed09  mov     rsi, rax
0x18000ed0c  mov     [rsp+78h+var_50], rax
0x18000ed11  lea     rdx, [r15+20h]
0x18000ed15  lea     rcx, [rax+20h]
0x18000ed19  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18000ed1e  lea     rdx, [r15+40h]
0x18000ed22  lea     rcx, [rsi+40h]
0x18000ed26  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x18000ed2b  mov     [rsi], rbp
0x18000ed2e  mov     [rsi+8], rbp
0x18000ed32  mov     [rsi+10h], rbp
0x18000ed36  mov     word ptr [rsi+18h], 0
0x18000ed3c  mov     [rsp+78h+var_50], 0
0x18000ed45  lea     rcx, [rsp+78h+var_58]
0x18000ed4a  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(void)
0x18000ed4f  mov     [rsi+8], r12
0x18000ed53  mov     al, [r15+18h]
0x18000ed57  mov     [rsi+18h], al
0x18000ed5a  mov     [rsp+78h+var_58], r14
0x18000ed5f  mov     [rsp+78h+var_50], r14
0x18000ed64  mov     [rsp+78h+var_48], rsi
0x18000ed69  mov     r8, rsi
0x18000ed6c  mov     rdx, [r15]
0x18000ed6f  mov     rcx, r14
0x18000ed72  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *)
0x18000ed77  mov     [rsi], rax
0x18000ed7a  mov     r8, rsi
0x18000ed7d  mov     rdx, [r15+10h]
0x18000ed81  mov     rcx, r14
0x18000ed84  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *)
0x18000ed89  mov     [rsi+10h], rax
0x18000ed8d  mov     [rsp+78h+var_58], 0
0x18000ed96  lea     rcx, [rsp+78h+var_58]
0x18000ed9b  call    ??1?$_Erase_tree_and_orphan_guard@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAA@XZ; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(void)
0x18000eda0  jmp     short loc_18000EDA5
0x18000eda2  mov     rsi, rbp
0x18000eda5  mov     rax, rsi
0x18000eda8  add     rsp, 40h
0x18000edac  pop     r15
0x18000edae  pop     r14
0x18000edb0  pop     r12
0x18000edb2  pop     rdi
0x18000edb3  pop     rsi
0x18000edb4  pop     rbp
0x18000edb5  pop     rbx
0x18000edb6  retn
```
