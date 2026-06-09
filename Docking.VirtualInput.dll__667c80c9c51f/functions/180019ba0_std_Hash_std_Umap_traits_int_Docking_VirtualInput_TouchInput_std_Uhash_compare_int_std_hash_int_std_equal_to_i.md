# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::clear(void)

- ea: `0x180019ba0`
- end: `0x180019c63`
- name: `?clear@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAAXXZ`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016d80`

## callees

- `0x180016320`
- `0x180019420`
- `0x180019490`
- `0x180019b58`
- `0x180019ba0`
- `0x180019c6c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::clear(
        __int64 a1)
{
  __int64 result; // rax
  unsigned __int64 v2; // rax
  unsigned __int64 v3; // [rsp+20h] [rbp-38h]
  __int64 v4; // [rsp+30h] [rbp-28h]
  _BYTE v5[16]; // [rsp+48h] [rbp-10h] BYREF

  result = *(_QWORD *)(a1 + 16);
  v3 = result;
  if ( result )
  {
    v2 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket_count(a1);
    if ( v2 / 8 <= v3 )
    {
      std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::clear(a1 + 8, v2 % 8);
      v4 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_end(
             a1,
             v5);
      return std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>(
               *(_QWORD *)(a1 + 24),
               *(_QWORD *)(a1 + 32),
               v4);
    }
    else
    {
      return std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_erase(
               a1,
               **(_QWORD **)(a1 + 8),
               *(_QWORD *)(a1 + 8));
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019ba0  mov     [rsp+arg_0], rcx
0x180019ba5  sub     rsp, 58h
0x180019ba9  mov     rax, [rsp+58h+arg_0]
0x180019bae  mov     rax, [rax+10h]
0x180019bb2  mov     [rsp+58h+var_38], rax
0x180019bb7  cmp     [rsp+58h+var_38], 0
0x180019bbd  jnz     short loc_180019BC4
0x180019bbf  jmp     loc_180019C5E
0x180019bc4  mov     rcx, [rsp+58h+arg_0]
0x180019bc9  call    ?bucket_count@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket_count(void)
0x180019bce  xor     edx, edx
0x180019bd0  mov     ecx, 8
0x180019bd5  div     rcx
0x180019bd8  cmp     rax, [rsp+58h+var_38]
0x180019bdd  jbe     short loc_180019C07
0x180019bdf  mov     rax, [rsp+58h+arg_0]
0x180019be4  mov     rax, [rax+8]
0x180019be8  mov     [rsp+58h+var_30], rax
0x180019bed  mov     r8, [rsp+58h+var_30]
0x180019bf2  mov     rax, [rsp+58h+var_30]
0x180019bf7  mov     rdx, [rax]
0x180019bfa  mov     rcx, [rsp+58h+arg_0]
0x180019bff  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_erase(std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> * const)
0x180019c04  nop
0x180019c05  jmp     short loc_180019C5E
0x180019c07  mov     rax, [rsp+58h+arg_0]
0x180019c0c  add     rax, 8
0x180019c10  mov     rcx, rax
0x180019c13  call    ?clear@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEAAXXZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::clear(void)
0x180019c18  nop
0x180019c19  lea     rdx, [rsp+58h+var_10]
0x180019c1e  mov     rcx, [rsp+58h+arg_0]
0x180019c23  call    ?_Unchecked_end@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@2@XZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Unchecked_end(void)
0x180019c28  mov     [rsp+58h+var_28], rax
0x180019c2d  mov     rax, [rsp+58h+arg_0]
0x180019c32  mov     rax, [rax+20h]
0x180019c36  mov     [rsp+58h+var_20], rax
0x180019c3b  mov     rax, [rsp+58h+arg_0]
0x180019c40  mov     rax, [rax+18h]
0x180019c44  mov     [rsp+58h+var_18], rax
0x180019c49  mov     r8, [rsp+58h+var_28]
0x180019c4e  mov     rdx, [rsp+58h+var_20]
0x180019c53  mov     rcx, [rsp+58h+var_18]
0x180019c58  call    ??$fill@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@V12@@std@@YAXQEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>> const &)
0x180019c5d  nop
0x180019c5e  add     rsp, 58h
0x180019c62  retn
```
