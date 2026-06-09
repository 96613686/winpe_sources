# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Min_load_factor_buckets(unsigned __int64)

- ea: `0x180019120`
- end: `0x1800191b9`
- name: `?_Min_load_factor_buckets@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@IEBA_K_K@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018a40`

## callees

- `0x180004024`
- `0x180019120`
- `0x180019eb8`

## pseudocode

```c
unsigned __int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Min_load_factor_buckets(
        __int64 a1,
        __int64 a2)
{
  float v2; // xmm1_4
  float v3; // xmm0_4
  unsigned __int64 v4; // rax
  float v6; // [rsp+20h] [rbp-18h]

  if ( a2 < 0 )
    v6 = (float)(a2 & 1 | (unsigned int)((unsigned __int64)a2 >> 1))
       + (float)(a2 & 1 | (unsigned int)((unsigned __int64)a2 >> 1));
  else
    v6 = (float)(int)a2;
  v2 = v6
     / std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::max_load_factor(a1);
  v3 = o_ceilf_0(v2);
  v4 = 0;
  if ( v3 >= 9.223372e18 )
  {
    v3 = v3 - 9.223372e18;
    if ( v3 < 9.223372e18 )
      v4 = 0x8000000000000000uLL;
  }
  return v4 + (unsigned int)(int)v3;
}

```

## disassembly

```asm
0x180019120  mov     [rsp+arg_8], rdx
0x180019125  mov     [rsp+arg_0], rcx
0x18001912a  sub     rsp, 38h
0x18001912e  mov     rax, [rsp+38h+arg_8]
0x180019133  test    rax, rax
0x180019136  jl      short loc_180019145
0x180019138  cvtsi2ss xmm0, rax
0x18001913d  movss   [rsp+38h+var_18], xmm0
0x180019143  jmp     short loc_180019164
0x180019145  mov     rcx, rax
0x180019148  shr     rcx, 1
0x18001914b  and     rax, 1
0x18001914f  or      rcx, rax
0x180019152  cvtsi2ss xmm1, rcx
0x180019157  addss   xmm1, xmm1
0x18001915b  movaps  xmm0, xmm1
0x18001915e  movss   [rsp+38h+var_18], xmm0
0x180019164  mov     rcx, [rsp+38h+arg_0]
0x180019169  call    ?max_load_factor@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBAMXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::max_load_factor(void)
0x18001916e  movss   xmm1, [rsp+38h+var_18]
0x180019174  divss   xmm1, xmm0
0x180019178  movaps  xmm0, xmm1; X
0x18001917b  call    _o_ceilf_0
0x180019180  xor     eax, eax
0x180019182  comiss  xmm0, cs:__real@5f000000
0x180019189  jb      short loc_1800191A9
0x18001918b  subss   xmm0, cs:__real@5f000000
0x180019193  comiss  xmm0, cs:__real@5f000000
0x18001919a  jnb     short loc_1800191A9
0x18001919c  mov     rcx, 8000000000000000h
0x1800191a6  add     rax, rcx
0x1800191a9  cvttss2si rcx, xmm0
0x1800191ae  add     rcx, rax
0x1800191b1  mov     rax, rcx
0x1800191b4  add     rsp, 38h
0x1800191b8  retn
```
