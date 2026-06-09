# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Rehash_for_1(void)

- ea: `0x1800191c0`
- end: `0x180019206`
- name: `?_Rehash_for_1@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEAAXXZ`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016100`

## callees

- `0x180018a40`
- `0x180018bd0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Rehash_for_1(
        _QWORD *a1)
{
  unsigned __int64 v1; // rax

  v1 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Desired_grow_bucket_count(
         (__int64)a1,
         a1[2] + 1LL);
  return std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Forced_rehash(
           a1,
           v1);
}

```

## disassembly

```asm
0x1800191c0  mov     [rsp+arg_0], rcx
0x1800191c5  sub     rsp, 38h
0x1800191c9  mov     rax, [rsp+38h+arg_0]
0x1800191ce  mov     rax, [rax+10h]
0x1800191d2  mov     [rsp+38h+var_18], rax
0x1800191d7  mov     rax, [rsp+38h+var_18]
0x1800191dc  inc     rax
0x1800191df  mov     [rsp+38h+var_10], rax
0x1800191e4  mov     rdx, [rsp+38h+var_10]
0x1800191e9  mov     rcx, [rsp+38h+arg_0]
0x1800191ee  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x1800191f3  mov     rdx, rax
0x1800191f6  mov     rcx, [rsp+38h+arg_0]
0x1800191fb  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Forced_rehash(unsigned __int64)
0x180019200  nop
0x180019201  add     rsp, 38h
0x180019205  retn
```
