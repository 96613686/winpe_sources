# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &,std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::piecewise_construct_t const &,std::tuple<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &> &&,std::tuple<> &&)

- ea: `0x18000e7fc`
- end: `0x18000e875`
- name: `??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f1b8`
- `0x180014470`

## callees

- `0x18000e7fc`
- `0x18000ec28`
- `0x18000f2ac`
- `0x18000f360`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 i; // rcx
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = a3;
  std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
    a1,
    a2);
  std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::construct<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,std::piecewise_construct_t const &,std::tuple<std::string const &>,std::tuple<>>(
    v6,
    *(_QWORD *)(a1 + 8) + 32LL,
    v7,
    a5);
  std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(
    *(_QWORD *)(a1 + 8),
    &v10);
  std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(
    *(_QWORD *)(a1 + 8) + 8LL,
    &v10);
  std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(
    *(_QWORD *)(a1 + 8) + 16LL,
    &v10);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(*(_QWORD *)(a1 + 8) + i + 24) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000e7fc  mov     [rsp+arg_10], r8
0x18000e801  mov     [rsp+arg_0], rcx
0x18000e806  push    rbx
0x18000e807  sub     rsp, 30h
0x18000e80b  mov     rbx, rcx
0x18000e80e  call    ??0?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x18000e813  nop
0x18000e814  mov     rdx, [rbx+8]
0x18000e818  add     rdx, 20h ; ' '
0x18000e81c  mov     r9, [rsp+38h+arg_20]
0x18000e821  call    ??$construct@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>::construct<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,std::piecewise_construct_t const &,std::tuple<std::string const &>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &,std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>> * const,std::piecewise_construct_t const &,std::tuple<std::string const &> &&,std::tuple<> &&)
0x18000e826  lea     rdx, [rsp+38h+arg_10]
0x18000e82b  mov     rcx, [rbx+8]
0x18000e82f  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &)
0x18000e834  mov     rcx, [rbx+8]
0x18000e838  add     rcx, 8
0x18000e83c  lea     rdx, [rsp+38h+arg_10]
0x18000e841  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &)
0x18000e846  mov     rcx, [rbx+8]
0x18000e84a  add     rcx, 10h
0x18000e84e  lea     rdx, [rsp+38h+arg_10]
0x18000e853  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> *,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &>(std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &,std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *> * &)
0x18000e858  xor     ecx, ecx
0x18000e85a  mov     rax, [rbx+8]
0x18000e85e  mov     byte ptr [rax+rcx+18h], 0
0x18000e863  inc     rcx
0x18000e866  cmp     rcx, 2
0x18000e86a  jnz     short loc_18000E85A
0x18000e86c  mov     rax, rbx
0x18000e86f  add     rsp, 30h
0x18000e873  pop     rbx
0x18000e874  retn
```
