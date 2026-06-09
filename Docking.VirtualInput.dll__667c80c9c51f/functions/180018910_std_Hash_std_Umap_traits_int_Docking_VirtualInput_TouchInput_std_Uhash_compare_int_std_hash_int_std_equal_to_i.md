# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Check_max_size(void)

- ea: `0x180018910`
- end: `0x180018952`
- name: `?_Check_max_size@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBAXXZ`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016100`

## callees

- `0x180018910`
- `0x180019f6c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018946`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018946`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Check_max_size(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v2; // [rsp+20h] [rbp-18h]

  v2 = *(_QWORD *)(a1 + 16);
  result = std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::max_size(a1 + 8);
  if ( v2 == result )
    std::_Xlength_error("unordered_map/set too long");
  return result;
}

```

## disassembly

```asm
0x180018910  mov     [rsp+arg_0], rcx
0x180018915  sub     rsp, 38h
0x180018919  mov     rax, [rsp+38h+arg_0]
0x18001891e  mov     rax, [rax+10h]
0x180018922  mov     [rsp+38h+var_18], rax
0x180018927  mov     rax, [rsp+38h+arg_0]
0x18001892c  add     rax, 8
0x180018930  mov     rcx, rax
0x180018933  call    ?max_size@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEBA_KXZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::max_size(void)
0x180018938  cmp     [rsp+38h+var_18], rax
0x18001893d  jnz     short loc_18001894D
0x18001893f  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180018946  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001894d  add     rsp, 38h
0x180018951  retn
```
