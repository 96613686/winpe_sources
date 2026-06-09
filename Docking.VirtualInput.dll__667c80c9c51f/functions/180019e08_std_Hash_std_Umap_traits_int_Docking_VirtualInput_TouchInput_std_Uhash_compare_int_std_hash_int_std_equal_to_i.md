# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::find(int const &)

- ea: `0x180019e08`
- end: `0x180019e70`
- name: `?find@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@AEBH@Z`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001984c`
- `0x18001a5d0`

## callees

- `0x1800159c0`
- `0x180015c80`
- `0x1800190d0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::find(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v6; // [rsp+28h] [rbp-10h]

  v6 = a1 + 8;
  v3 = std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int>(a1, a3);
  v4 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find<int>(
         a1,
         a3,
         v3);
  std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Make_iter(v6, a2, v4);
  return a2;
}

```

## disassembly

```asm
0x180019e08  mov     [rsp+arg_10], r8
0x180019e0d  mov     [rsp+arg_8], rdx
0x180019e12  mov     [rsp+arg_0], rcx
0x180019e17  sub     rsp, 38h
0x180019e1b  mov     rax, [rsp+38h+arg_0]
0x180019e20  add     rax, 8
0x180019e24  mov     [rsp+38h+var_10], rax
0x180019e29  mov     rax, [rsp+38h+arg_0]
0x180019e2e  mov     [rsp+38h+var_18], rax
0x180019e33  mov     rdx, [rsp+38h+arg_10]
0x180019e38  mov     rcx, [rsp+38h+var_18]
0x180019e3d  call    ??$?RH@?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@QEBA_KAEBH@Z; std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int>(int const &)
0x180019e42  mov     r8, rax
0x180019e45  mov     rdx, [rsp+38h+arg_10]
0x180019e4a  mov     rcx, [rsp+38h+arg_0]
0x180019e4f  call    ??$_Find@H@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@1@AEBH_K@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find<int>(int const &,unsigned __int64)
0x180019e54  mov     r8, rax
0x180019e57  mov     rdx, [rsp+38h+arg_8]
0x180019e5c  mov     rcx, [rsp+38h+var_10]
0x180019e61  call    ?_Make_iter@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEBA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@PEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@@Z; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Make_iter(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *)
0x180019e66  mov     rax, [rsp+38h+arg_8]
0x180019e6b  add     rsp, 38h
0x180019e6f  retn
```
