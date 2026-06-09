# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>(std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>> const &,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>> const &)

- ea: `0x180016570`
- end: `0x180016650`
- name: `??0?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEAA@AEBV?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@1@AEBV?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@1@@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016864`

## callees

- `0x180015680`
- `0x180016788`
- `0x18001681c`
- `0x180018750`
- `0x180018f40`
- `0x18001945c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rax
  _BYTE v5[16]; // [rsp+48h] [rbp-10h] BYREF

  std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>(
    a1,
    a2);
  std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::list<std::pair<int const,Docking::VirtualInput::TouchInput>>(
    a1 + 8,
    a3);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>(
    a1 + 24,
    a3);
  *(_QWORD *)(a1 + 48) = 7;
  *(_QWORD *)(a1 + 56) = 8;
  *(float *)std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Getal(a1) = FLOAT_1_0;
  v3 = (_QWORD *)std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Unchecked_end(a1 + 8, v5);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::_Assign_grow(
    a1 + 24,
    16,
    *v3);
  return a1;
}

```

## disassembly

```asm
0x180016570  mov     [rsp+arg_10], r8
0x180016575  mov     [rsp+arg_8], rdx
0x18001657a  mov     [rsp+arg_0], rcx
0x18001657f  sub     rsp, 58h
0x180016583  mov     rax, [rsp+58h+arg_0]
0x180016588  mov     [rsp+58h+var_38], rax
0x18001658d  mov     rdx, [rsp+58h+arg_8]
0x180016592  mov     rcx, [rsp+58h+var_38]
0x180016597  call    ??0?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@QEAA@AEBV?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@1@@Z; std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>(std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>> const &)
0x18001659c  mov     rax, [rsp+58h+arg_0]
0x1800165a1  add     rax, 8
0x1800165a5  mov     [rsp+58h+var_30], rax
0x1800165aa  mov     rdx, [rsp+58h+arg_10]
0x1800165af  mov     rcx, [rsp+58h+var_30]
0x1800165b4  call    ??0?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@1@@Z; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::list<std::pair<int const,Docking::VirtualInput::TouchInput>>(std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>> const &)
0x1800165b9  nop
0x1800165ba  mov     rax, [rsp+58h+arg_0]
0x1800165bf  add     rax, 18h
0x1800165c3  mov     [rsp+58h+var_28], rax
0x1800165c8  mov     rdx, [rsp+58h+arg_10]
0x1800165cd  mov     rcx, [rsp+58h+var_28]
0x1800165d2  call    ??$?0AEBV?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>(std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>> const &)
0x1800165d7  nop
0x1800165d8  mov     rax, [rsp+58h+arg_0]
0x1800165dd  mov     qword ptr [rax+30h], 7
0x1800165e5  mov     rax, [rsp+58h+arg_0]
0x1800165ea  mov     qword ptr [rax+38h], 8
0x1800165f2  mov     rcx, [rsp+58h+arg_0]
0x1800165f7  call    ?_Getal@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@AEBAAEBV?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@2@XZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Getal(void)
0x1800165fc  movss   xmm0, cs:__real@3f800000
0x180016604  movss   dword ptr [rax], xmm0
0x180016608  mov     rax, [rsp+58h+arg_0]
0x18001660d  add     rax, 18h
0x180016611  mov     [rsp+58h+var_18], rax
0x180016616  mov     rax, [rsp+58h+arg_0]
0x18001661b  add     rax, 8
0x18001661f  mov     [rsp+58h+var_20], rax
0x180016624  lea     rdx, [rsp+58h+var_10]
0x180016629  mov     rcx, [rsp+58h+var_20]
0x18001662e  call    ?_Unchecked_end@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Unchecked_end(void)
0x180016633  mov     r8, [rax]
0x180016636  mov     edx, 10h
0x18001663b  mov     rcx, [rsp+58h+var_18]
0x180016640  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>)
0x180016645  nop
0x180016646  mov     rax, [rsp+58h+arg_0]
0x18001664b  add     rsp, 58h
0x18001664f  retn
```
