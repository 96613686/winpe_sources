# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::insert(std::pair<int const,Docking::VirtualInput::TouchInput> &&)

- ea: `0x180019e78`
- end: `0x180019eb1`
- name: `?insert@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@2@@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001984c`

## callees

- `0x18000b810`
- `0x180016100`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rax

  v3 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a3);
  std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::emplace<std::pair<int const,Docking::VirtualInput::TouchInput>>(
    a1,
    a2,
    v3);
  return a2;
}

```

## disassembly

```asm
0x180019e78  mov     [rsp+arg_10], r8
0x180019e7d  mov     [rsp+arg_8], rdx
0x180019e82  mov     [rsp+arg_0], rcx
0x180019e87  sub     rsp, 28h
0x180019e8b  mov     rcx, [rsp+28h+arg_10]
0x180019e90  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180019e95  mov     r8, rax
0x180019e98  mov     rdx, [rsp+28h+arg_8]
0x180019e9d  mov     rcx, [rsp+28h+arg_0]
0x180019ea2  call    ??$emplace@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@1@@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::emplace<std::pair<int const,Docking::VirtualInput::TouchInput>>(std::pair<int const,Docking::VirtualInput::TouchInput> &&)
0x180019ea7  mov     rax, [rsp+28h+arg_8]
0x180019eac  add     rsp, 28h
0x180019eb0  retn
```
