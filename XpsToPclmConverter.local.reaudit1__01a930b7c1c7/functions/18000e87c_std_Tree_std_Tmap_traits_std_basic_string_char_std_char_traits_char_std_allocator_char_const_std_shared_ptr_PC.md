# std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>(std::_Tree<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &&)

- ea: `0x18000e87c`
- end: `0x18000e92b`
- name: `??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z`
- size: `175`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180010290`
- `0x180010a50`
- `0x180011538`
- `0x1800199e0`

## callees

- `0x18000e87c`
- `0x18000eae8`
- `0x18000eccc`
- `0x18000f608`
- `0x1800105f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 *v6; // r8
  __int64 i; // rcx
  __int64 *v9; // [rsp+20h] [rbp-18h] BYREF
  __int64 *v10; // [rsp+28h] [rbp-10h]

  *a1 = 0;
  a1[1] = 0;
  v9 = a1;
  v10 = a1;
  v4 = std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
         a1,
         a2);
  *a1 = v4;
  *(_QWORD *)(*a1 + 8) = std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Copy_nodes<0>(
                           a1,
                           *(_QWORD *)(*a2 + 8LL),
                           v4);
  a1[1] = a2[1];
  if ( *(_BYTE *)(*(_QWORD *)(*a1 + 8) + 25LL) )
  {
    *(_QWORD *)*a1 = *a1;
    *(_QWORD *)(*a1 + 16) = *a1;
  }
  else
  {
    v5 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Min();
    *v6 = v5;
    for ( i = *(_QWORD *)(*a1 + 8); !*(_BYTE *)(*(_QWORD *)(i + 16) + 25LL); i = *(_QWORD *)(i + 16) )
      ;
    *(_QWORD *)(*a1 + 16) = i;
  }
  v10 = 0;
  std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>>(&v9);
  return a1;
}

```

## disassembly

```asm
0x18000e87c  mov     [rsp+arg_0], rbx
0x18000e881  push    rdi
0x18000e882  sub     rsp, 30h
0x18000e886  mov     rbx, rdx
0x18000e889  mov     rdi, rcx
0x18000e88c  mov     qword ptr [rcx], 0
0x18000e893  mov     qword ptr [rcx+8], 0
0x18000e89b  mov     [rsp+38h+var_18], rcx
0x18000e8a0  mov     [rsp+38h+var_10], rcx
0x18000e8a5  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x18000e8aa  mov     [rdi], rax
0x18000e8ad  mov     rdx, [rbx]
0x18000e8b0  mov     r8, rax
0x18000e8b3  mov     rdx, [rdx+8]
0x18000e8b7  mov     rcx, rdi
0x18000e8ba  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *)
0x18000e8bf  mov     rcx, [rdi]
0x18000e8c2  mov     [rcx+8], rax
0x18000e8c6  mov     rax, [rbx+8]
0x18000e8ca  mov     [rdi+8], rax
0x18000e8ce  mov     r8, [rdi]
0x18000e8d1  mov     rcx, [r8+8]
0x18000e8d5  cmp     byte ptr [rcx+19h], 0
0x18000e8d9  jnz     short loc_18000E900
0x18000e8db  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Min(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *)
0x18000e8e0  mov     [r8], rax
0x18000e8e3  mov     rdx, [rdi]
0x18000e8e6  mov     rcx, [rdx+8]
0x18000e8ea  jmp     short loc_18000E8F0
0x18000e8ec  mov     rcx, [rcx+10h]
0x18000e8f0  mov     rax, [rcx+10h]
0x18000e8f4  cmp     byte ptr [rax+19h], 0
0x18000e8f8  jz      short loc_18000E8EC
0x18000e8fa  mov     [rdx+10h], rcx
0x18000e8fe  jmp     short loc_18000E90A
0x18000e900  mov     [r8], r8
0x18000e903  mov     rax, [rdi]
0x18000e906  mov     [rax+10h], rax
0x18000e90a  mov     [rsp+38h+var_10], 0
0x18000e913  lea     rcx, [rsp+38h+var_18]
0x18000e918  call    ??1?$_Tree_head_scoped_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@2@@std@@QEAA@XZ; std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>>(void)
0x18000e91d  mov     rax, rdi
0x18000e920  mov     rbx, [rsp+38h+arg_0]
0x18000e925  add     rsp, 30h
0x18000e929  pop     rdi
0x18000e92a  retn
```
