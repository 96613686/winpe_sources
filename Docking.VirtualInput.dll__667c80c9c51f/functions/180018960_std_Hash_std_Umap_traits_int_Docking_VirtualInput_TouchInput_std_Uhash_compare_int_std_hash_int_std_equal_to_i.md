# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Check_rehash_required_1(void)

- ea: `0x180018960`
- end: `0x180018a2d`
- name: `?_Check_rehash_required_1@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016100`

## callees

- `0x180018960`
- `0x180019b58`
- `0x180019eb8`

## pseudocode

```c
_BOOL8 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Check_rehash_required_1(
        __int64 a1)
{
  __int64 v1; // rax
  float v2; // xmm0_4
  float v4; // [rsp+20h] [rbp-28h]
  float factor; // [rsp+28h] [rbp-20h]
  __int64 v6; // [rsp+38h] [rbp-10h]

  v6 = *(_QWORD *)(a1 + 16) + 1LL;
  factor = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::max_load_factor(a1);
  if ( v6 < 0 )
    v4 = (float)(v6 & 1 | (unsigned int)((unsigned __int64)v6 >> 1))
       + (float)(v6 & 1 | (unsigned int)((unsigned __int64)v6 >> 1));
  else
    v4 = (float)(int)v6;
  v1 = std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket_count(a1);
  if ( v1 < 0 )
    v2 = (float)(v1 & 1 | (unsigned int)((unsigned __int64)v1 >> 1))
       + (float)(v1 & 1 | (unsigned int)((unsigned __int64)v1 >> 1));
  else
    v2 = (float)(int)v1;
  return (float)(v4 / v2) > factor;
}

```

## disassembly

```asm
0x180018960  mov     [rsp+arg_0], rcx
0x180018965  sub     rsp, 48h
0x180018969  mov     rax, [rsp+48h+arg_0]
0x18001896e  mov     rax, [rax+10h]
0x180018972  mov     [rsp+48h+var_18], rax
0x180018977  mov     rax, [rsp+48h+var_18]
0x18001897c  inc     rax
0x18001897f  mov     [rsp+48h+var_10], rax
0x180018984  mov     rcx, [rsp+48h+arg_0]
0x180018989  call    ?max_load_factor@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBAMXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::max_load_factor(void)
0x18001898e  movss   [rsp+48h+var_20], xmm0
0x180018994  mov     rax, [rsp+48h+var_10]
0x180018999  test    rax, rax
0x18001899c  jl      short loc_1800189AB
0x18001899e  cvtsi2ss xmm1, rax
0x1800189a3  movss   [rsp+48h+var_28], xmm1
0x1800189a9  jmp     short loc_1800189CA
0x1800189ab  mov     rcx, rax
0x1800189ae  shr     rcx, 1
0x1800189b1  and     rax, 1
0x1800189b5  or      rcx, rax
0x1800189b8  cvtsi2ss xmm2, rcx
0x1800189bd  addss   xmm2, xmm2
0x1800189c1  movaps  xmm1, xmm2
0x1800189c4  movss   [rsp+48h+var_28], xmm1
0x1800189ca  mov     rcx, [rsp+48h+arg_0]
0x1800189cf  call    ?bucket_count@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket_count(void)
0x1800189d4  test    rax, rax
0x1800189d7  jl      short loc_1800189E0
0x1800189d9  cvtsi2ss xmm0, rax
0x1800189de  jmp     short loc_1800189F9
0x1800189e0  mov     rcx, rax
0x1800189e3  shr     rcx, 1
0x1800189e6  and     rax, 1
0x1800189ea  or      rcx, rax
0x1800189ed  cvtsi2ss xmm1, rcx
0x1800189f2  addss   xmm1, xmm1
0x1800189f6  movaps  xmm0, xmm1
0x1800189f9  movss   xmm1, [rsp+48h+var_28]
0x1800189ff  divss   xmm1, xmm0
0x180018a03  movaps  xmm0, xmm1
0x180018a06  movss   xmm1, [rsp+48h+var_20]
0x180018a0c  comiss  xmm0, xmm1
0x180018a0f  jbe     short loc_180018A1B
0x180018a11  mov     [rsp+48h+var_24], 1
0x180018a19  jmp     short loc_180018A23
0x180018a1b  mov     [rsp+48h+var_24], 0
0x180018a23  movzx   eax, byte ptr [rsp+48h+var_24]
0x180018a28  add     rsp, 48h
0x180018a2c  retn
```
