# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find<int>(int const &,unsigned __int64)

- ea: `0x180015c80`
- end: `0x180015cd2`
- name: `??$_Find@H@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@1@AEBH_K@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019e08`

## callees

- `0x180015c80`
- `0x180015ce0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find<int>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // [rsp+20h] [rbp-28h]
  _QWORD v5[4]; // [rsp+28h] [rbp-20h] BYREF

  v4 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find_last<int>(
         a1,
         v5,
         a2,
         a3)[1];
  if ( v4 )
    return v4;
  else
    return a1[1];
}

```

## disassembly

```asm
0x180015c80  mov     [rsp+arg_10], r8
0x180015c85  mov     [rsp+arg_8], rdx
0x180015c8a  mov     [rsp+arg_0], rcx
0x180015c8f  sub     rsp, 48h
0x180015c93  mov     r9, [rsp+48h+arg_10]
0x180015c98  mov     r8, [rsp+48h+arg_8]
0x180015c9d  lea     rdx, [rsp+48h+var_20]
0x180015ca2  mov     rcx, [rsp+48h+arg_0]
0x180015ca7  call    ??$_Find_last@H@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@1@AEBH_K@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Find_last<int>(int const &,unsigned __int64)
0x180015cac  mov     rax, [rax+8]
0x180015cb0  mov     [rsp+48h+var_28], rax
0x180015cb5  cmp     [rsp+48h+var_28], 0
0x180015cbb  jz      short loc_180015CC4
0x180015cbd  mov     rax, [rsp+48h+var_28]
0x180015cc2  jmp     short loc_180015CCD
0x180015cc4  mov     rax, [rsp+48h+arg_0]
0x180015cc9  mov     rax, [rax+8]
0x180015ccd  add     rsp, 48h
0x180015cd1  retn
```
