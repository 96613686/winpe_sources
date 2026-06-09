# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::end(void)

- ea: `0x180019d78`
- end: `0x180019dad`
- name: `?end@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001984c`
- `0x18001a5d0`

## callees

- `0x180019db4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::end(
        __int64 a1,
        __int64 a2)
{
  std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::end(a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x180019d78  mov     [rsp+arg_8], rdx
0x180019d7d  mov     [rsp+arg_0], rcx
0x180019d82  sub     rsp, 38h
0x180019d86  mov     rax, [rsp+38h+arg_0]
0x180019d8b  add     rax, 8
0x180019d8f  mov     [rsp+38h+var_18], rax
0x180019d94  mov     rdx, [rsp+38h+arg_8]
0x180019d99  mov     rcx, [rsp+38h+var_18]
0x180019d9e  call    ?end@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::end(void)
0x180019da3  mov     rax, [rsp+38h+arg_8]
0x180019da8  add     rsp, 38h
0x180019dac  retn
```
