# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_erase(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *)

- ea: `0x18001aca0`
- end: `0x18001ad07`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@PEAU32@@Z`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001a0c0`

## callees

- `0x18000b810`
- `0x180019b00`
- `0x18001aa20`
- `0x18001ad10`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_erase(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rax
  __int64 v4; // [rsp+20h] [rbp-18h]

  v2 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a2 + 16);
  v4 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket(
         a1,
         v2);
  std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Erase_bucket(
    a1,
    a2,
    v4);
  return std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Unchecked_erase(a1 + 8, a2);
}

```

## disassembly

```asm
0x18001aca0  mov     [rsp+arg_8], rdx
0x18001aca5  mov     [rsp+arg_0], rcx
0x18001acaa  sub     rsp, 38h
0x18001acae  mov     rax, [rsp+38h+arg_8]
0x18001acb3  add     rax, 10h
0x18001acb7  mov     rcx, rax
0x18001acba  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18001acbf  mov     rdx, rax
0x18001acc2  mov     rcx, [rsp+38h+arg_0]
0x18001acc7  call    ?bucket@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KAEBH@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket(int const &)
0x18001accc  mov     [rsp+38h+var_18], rax
0x18001acd1  mov     r8, [rsp+38h+var_18]
0x18001acd6  mov     rdx, [rsp+38h+arg_8]
0x18001acdb  mov     rcx, [rsp+38h+arg_0]
0x18001ace0  call    ?_Erase_bucket@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@_K@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Erase_bucket(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *,unsigned __int64)
0x18001ace5  mov     rax, [rsp+38h+arg_0]
0x18001acea  add     rax, 8
0x18001acee  mov     [rsp+38h+var_10], rax
0x18001acf3  mov     rdx, [rsp+38h+arg_8]
0x18001acf8  mov     rcx, [rsp+38h+var_10]
0x18001acfd  call    ?_Unchecked_erase@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@QEAU32@@Z; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Unchecked_erase(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const)
0x18001ad02  add     rsp, 38h
0x18001ad06  retn
```
