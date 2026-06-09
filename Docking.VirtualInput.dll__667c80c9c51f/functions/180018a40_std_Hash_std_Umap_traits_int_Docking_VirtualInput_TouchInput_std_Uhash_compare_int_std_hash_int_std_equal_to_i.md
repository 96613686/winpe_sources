# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Desired_grow_bucket_count(unsigned __int64)

- ea: `0x180018a40`
- end: `0x180018acd`
- name: `?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBA_K_K@Z`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800191c0`

## callees

- `0x180016410`
- `0x180018a40`
- `0x180019120`
- `0x180019b58`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Desired_grow_bucket_count(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v3; // [rsp+20h] [rbp-28h]
  unsigned __int64 v4; // [rsp+28h] [rbp-20h]
  __int64 v5[3]; // [rsp+30h] [rbp-18h] BYREF

  v3 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket_count(a1);
  v5[0] = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Min_load_factor_buckets(
            a1,
            a2);
  v4 = *(_QWORD *)std::max<unsigned __int64>("\b", v5);
  if ( v3 >= v4 )
    return v3;
  if ( v3 >= 0x200 || 8 * v3 < v4 )
    return v4;
  return 8 * v3;
}

```

## disassembly

```asm
0x180018a40  mov     [rsp+arg_8], rdx
0x180018a45  mov     [rsp+arg_0], rcx
0x180018a4a  sub     rsp, 48h
0x180018a4e  mov     rcx, [rsp+48h+arg_0]
0x180018a53  call    ?bucket_count@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket_count(void)
0x180018a58  mov     [rsp+48h+var_28], rax
0x180018a5d  mov     rdx, [rsp+48h+arg_8]
0x180018a62  mov     rcx, [rsp+48h+arg_0]
0x180018a67  call    ?_Min_load_factor_buckets@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Min_load_factor_buckets(unsigned __int64)
0x180018a6c  mov     [rsp+48h+var_18], rax
0x180018a71  lea     rdx, [rsp+48h+var_18]
0x180018a76  lea     rcx, ?_Min_buckets@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@2_KB; "\b"
0x180018a7d  call    ??$max@_K@std@@YAAEB_KAEB_K0@Z; std::max<unsigned __int64>(unsigned __int64 const &,unsigned __int64 const &)
0x180018a82  mov     rax, [rax]
0x180018a85  mov     [rsp+48h+var_20], rax
0x180018a8a  mov     rax, [rsp+48h+var_20]
0x180018a8f  cmp     [rsp+48h+var_28], rax
0x180018a94  jb      short loc_180018A9D
0x180018a96  mov     rax, [rsp+48h+var_28]
0x180018a9b  jmp     short loc_180018AC8
0x180018a9d  cmp     [rsp+48h+var_28], 200h
0x180018aa6  jnb     short loc_180018AC3
0x180018aa8  mov     rax, [rsp+48h+var_28]
0x180018aad  shl     rax, 3
0x180018ab1  cmp     rax, [rsp+48h+var_20]
0x180018ab6  jb      short loc_180018AC3
0x180018ab8  mov     rax, [rsp+48h+var_28]
0x180018abd  shl     rax, 3
0x180018ac1  jmp     short loc_180018AC8
0x180018ac3  mov     rax, [rsp+48h+var_20]
0x180018ac8  add     rsp, 48h
0x180018acc  retn
```
