# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>)

- ea: `0x18001a0c0`
- end: `0x18001a10c`
- name: `??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@1@V21@@Z`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a5d0`

## callees

- `0x1800190d0`
- `0x18001aca0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>,0>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rax
  __int64 v5; // [rsp+20h] [rbp-18h]

  v5 = a1 + 8;
  v3 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_erase(
         a1,
         a3);
  std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Make_iter(v5, a2, v3);
  return a2;
}

```

## disassembly

```asm
0x18001a0c0  mov     [rsp+arg_10], r8
0x18001a0c5  mov     [rsp+arg_8], rdx
0x18001a0ca  mov     [rsp+arg_0], rcx
0x18001a0cf  sub     rsp, 38h
0x18001a0d3  mov     rax, [rsp+38h+arg_0]
0x18001a0d8  add     rax, 8
0x18001a0dc  mov     [rsp+38h+var_18], rax
0x18001a0e1  mov     rdx, [rsp+38h+arg_10]
0x18001a0e6  mov     rcx, [rsp+38h+arg_0]
0x18001a0eb  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@PEAU32@@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_erase(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *)
0x18001a0f0  mov     r8, rax
0x18001a0f3  mov     rdx, [rsp+38h+arg_8]
0x18001a0f8  mov     rcx, [rsp+38h+var_18]
0x18001a0fd  call    ?_Make_iter@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEBA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@PEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@@Z; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Make_iter(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *)
0x18001a102  mov     rax, [rsp+38h+arg_8]
0x18001a107  add     rsp, 38h
0x18001a10b  retn
```
