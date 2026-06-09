# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::~_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>(void)

- ea: `0x180016b78`
- end: `0x180016ba9`
- name: `??1?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA@XZ`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016cdc`

## callees

- `0x180016bb0`
- `0x180016c6c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::~_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>(
        __int64 a1)
{
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>(a1 + 24);
  return std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::~list<std::pair<int const,Docking::VirtualInput::TouchInput>>(a1 + 8);
}

```

## disassembly

```asm
0x180016b78  mov     [rsp+arg_0], rcx
0x180016b7d  sub     rsp, 28h
0x180016b81  mov     rax, [rsp+28h+arg_0]
0x180016b86  add     rax, 18h
0x180016b8a  mov     rcx, rax
0x180016b8d  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>(void)
0x180016b92  mov     rax, [rsp+28h+arg_0]
0x180016b97  add     rax, 8
0x180016b9b  mov     rcx, rax
0x180016b9e  call    ??1?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::~list<std::pair<int const,Docking::VirtualInput::TouchInput>>(void)
0x180016ba3  nop
0x180016ba4  add     rsp, 28h
0x180016ba8  retn
```
