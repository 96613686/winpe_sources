# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::begin(void)

- ea: `0x18001adfc`
- end: `0x18001ae31`
- name: `?begin@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a5d0`

## callees

- `0x18001ae38`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::begin(
        __int64 a1,
        __int64 a2)
{
  std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::begin(a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x18001adfc  mov     [rsp+arg_8], rdx
0x18001ae01  mov     [rsp+arg_0], rcx
0x18001ae06  sub     rsp, 38h
0x18001ae0a  mov     rax, [rsp+38h+arg_0]
0x18001ae0f  add     rax, 8
0x18001ae13  mov     [rsp+38h+var_18], rax
0x18001ae18  mov     rdx, [rsp+38h+arg_8]
0x18001ae1d  mov     rcx, [rsp+38h+var_18]
0x18001ae22  call    ?begin@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::begin(void)
0x18001ae27  mov     rax, [rsp+38h+arg_8]
0x18001ae2c  add     rsp, 38h
0x18001ae30  retn
```
