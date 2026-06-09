# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_begin(void)

- ea: `0x1800193ac`
- end: `0x1800193e1`
- name: `?_Unchecked_begin@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018bd0`

## callees

- `0x1800193e8`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_begin(
        __int64 a1,
        __int64 a2)
{
  std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Unchecked_begin(a1 + 8, a2);
  return a2;
}

```

## disassembly

```asm
0x1800193ac  mov     [rsp+arg_8], rdx
0x1800193b1  mov     [rsp+arg_0], rcx
0x1800193b6  sub     rsp, 38h
0x1800193ba  mov     rax, [rsp+38h+arg_0]
0x1800193bf  add     rax, 8
0x1800193c3  mov     [rsp+38h+var_18], rax
0x1800193c8  mov     rdx, [rsp+38h+arg_8]
0x1800193cd  mov     rcx, [rsp+38h+var_18]
0x1800193d2  call    ?_Unchecked_begin@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Unchecked_begin(void)
0x1800193d7  mov     rax, [rsp+38h+arg_8]
0x1800193dc  add     rsp, 38h
0x1800193e0  retn
```
