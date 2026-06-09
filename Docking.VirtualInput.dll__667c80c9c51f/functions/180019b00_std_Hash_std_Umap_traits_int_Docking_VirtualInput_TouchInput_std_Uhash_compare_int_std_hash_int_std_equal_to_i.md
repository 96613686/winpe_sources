# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket(int const &)

- ea: `0x180019b00`
- end: `0x180019b4f`
- name: `?bucket@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KAEBH@Z`
- size: `79`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018bd0`
- `0x180019490`
- `0x18001aca0`

## callees

- `0x1800159c0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket(
        __int64 a1,
        __int64 a2)
{
  return *(_QWORD *)(a1 + 48) & std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int>(a1, a2);
}

```

## disassembly

```asm
0x180019b00  mov     [rsp+arg_8], rdx
0x180019b05  mov     [rsp+arg_0], rcx
0x180019b0a  sub     rsp, 48h
0x180019b0e  mov     rax, [rsp+48h+arg_0]
0x180019b13  mov     [rsp+48h+var_28], rax
0x180019b18  mov     rdx, [rsp+48h+arg_8]
0x180019b1d  mov     rcx, [rsp+48h+var_28]
0x180019b22  call    ??$?RH@?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@QEBA_KAEBH@Z; std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int>(int const &)
0x180019b27  mov     [rsp+48h+var_18], rax
0x180019b2c  mov     rax, [rsp+48h+arg_0]
0x180019b31  mov     rax, [rax+30h]
0x180019b35  mov     [rsp+48h+var_20], rax
0x180019b3a  mov     rax, [rsp+48h+var_20]
0x180019b3f  mov     rcx, [rsp+48h+var_18]
0x180019b44  and     rcx, rax
0x180019b47  mov     rax, rcx
0x180019b4a  add     rsp, 48h
0x180019b4e  retn
```
