# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_end(void)

- ea: `0x180019420`
- end: `0x180019455`
- name: `?_Unchecked_end@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018bd0`
- `0x180019ba0`

## callees

- `0x18001945c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_end(
        __int64 a1,
        __int64 a2)
{
  std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Unchecked_end(a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x180019420  mov     [rsp+arg_8], rdx
0x180019425  mov     [rsp+arg_0], rcx
0x18001942a  sub     rsp, 38h
0x18001942e  mov     rax, [rsp+38h+arg_0]
0x180019433  add     rax, 8
0x180019437  mov     [rsp+38h+var_18], rax
0x18001943c  mov     rdx, [rsp+38h+arg_8]
0x180019441  mov     rcx, [rsp+38h+var_18]
0x180019446  call    ?_Unchecked_end@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Unchecked_end(void)
0x18001944b  mov     rax, [rsp+38h+arg_8]
0x180019450  add     rsp, 38h
0x180019454  retn
```
