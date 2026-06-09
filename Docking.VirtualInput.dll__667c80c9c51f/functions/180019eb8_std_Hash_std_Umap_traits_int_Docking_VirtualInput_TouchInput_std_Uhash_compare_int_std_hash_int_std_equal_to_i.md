# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::max_load_factor(void)

- ea: `0x180019eb8`
- end: `0x180019ed4`
- name: `?max_load_factor@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBAMXZ`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018960`
- `0x180019120`

## callees

- `0x180018f40`

## pseudocode

```c
float __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::max_load_factor(
        __int64 a1)
{
  return *(float *)std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Getal(a1);
}

```

## disassembly

```asm
0x180019eb8  mov     [rsp+arg_0], rcx
0x180019ebd  sub     rsp, 28h
0x180019ec1  mov     rcx, [rsp+28h+arg_0]
0x180019ec6  call    ?_Getal@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@AEBAAEBV?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@2@XZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Getal(void)
0x180019ecb  movss   xmm0, dword ptr [rax]
0x180019ecf  add     rsp, 28h
0x180019ed3  retn
```
