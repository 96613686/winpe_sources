# CRdpIdSwapchain::UpdateDirtyList(uint,bool *)

- ea: `0x18002cffc`
- end: `0x18002d27e`
- name: `?UpdateDirtyList@CRdpIdSwapchain@@QEAAXIPEA_N@Z`
- size: `642`
- prototype: `void __fastcall(CRdpIdSwapchain *__hidden this, unsigned int, bool *)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800299ac`
- `0x180029c18`
- `0x18002b7f0`

## callees

- `0x18001dd50`
- `0x18001ddf4`
- `0x18002971c`
- `0x180029820`
- `0x18002cffc`
- `0x18002d474`
- `0x18003f010`

## pseudocode

```c
void __fastcall CRdpIdSwapchain::UpdateDirtyList(CRdpIdSwapchain *this, unsigned int a2, bool *a3)
{
  __int64 v4; // rsi
  __int64 *v6; // rbx
  __int64 v7; // rcx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rbx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // rdi
  unsigned __int64 v21; // rdx
  __int64 v22; // rdx
  int v23; // eax
  int v24; // [rsp+20h] [rbp-20h]
  const char *v25; // [rsp+28h] [rbp-18h]
  __int128 v26; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v28; // [rsp+88h] [rbp+48h] BYREF

  v4 = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RdpIddSkippedDirtyList>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RdpIddSkippedDirtyList>::GetImpl'::`2'::impl) )
  {
    if ( (_DWORD)v4 )
    {
      v6 = (__int64 *)((char *)this + 40);
      v28 = 0;
      v7 = *((_QWORD *)this + 6);
      v8 = (v7 - *((_QWORD *)this + 5)) >> 4;
      v26 = 0;
      v9 = v4 + v8;
      if ( v4 + v8 >= v8 )
      {
        if ( v4 + v8 > v8 )
        {
          if ( v9 <= (__int64)(*((_QWORD *)this + 7) - *((_QWORD *)this + 5)) >> 4 )
            *((_QWORD *)this + 6) = std::_Uninitialized_value_construct_n<std::allocator<tagRECT>>(
                                      v7,
                                      v4,
                                      (char *)this + 40);
          else
            std::vector<tagRECT>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 40);
        }
      }
      else
      {
        *((_QWORD *)this + 6) = *v6 + 16 * v9;
      }
      v10 = *((_QWORD *)this + 4);
      v11 = 16 * v8 + *v6;
      LODWORD(v26) = v4;
      *((_QWORD *)&v26 + 1) = v11;
      v12 = ((__int64 (__fastcall *)(__int64, __int64, __int128 *, int *))qword_180057B70)(
              IddDriverGlobals,
              v10,
              &v26,
              &v28);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
        (const char *)v12,
        (int)"IddCxSwapChainGetDirtyRects failed",
        v25);
      if ( (_DWORD)v4 == 1 && **((_OWORD **)&v26 + 1) == 0 )
      {
        v13 = *v6;
        v14 = (__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 5)) >> 4;
        if ( v8 < v14 )
        {
          v15 = 16 * v8 + v13;
LABEL_17:
          *((_QWORD *)this + 6) = v15;
          goto LABEL_18;
        }
        if ( v8 > v14 )
        {
          if ( v8 <= (*((_QWORD *)this + 7) - v13) >> 4 )
          {
            v15 = std::_Uninitialized_value_construct_n<std::allocator<tagRECT>>(
                    *((_QWORD *)this + 6),
                    v8 - v14,
                    (char *)this + 40);
            goto LABEL_17;
          }
          std::vector<tagRECT>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 40);
        }
LABEL_18:
        *a3 = 1;
      }
    }
  }
  else
  {
    v16 = (_QWORD *)((char *)this + 40);
    v17 = (__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 5)) >> 4;
    v18 = v17 + v4;
    if ( v17 + v4 >= v17 )
    {
      if ( v17 + v4 > v17 )
      {
        if ( v18 <= (__int64)(*((_QWORD *)this + 7) - *((_QWORD *)this + 5)) >> 4 )
          *((_QWORD *)this + 6) = std::_Uninitialized_value_construct_n<std::allocator<tagRECT>>(
                                    *((_QWORD *)this + 6),
                                    v4,
                                    (char *)this + 40);
        else
          std::vector<tagRECT>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 40);
      }
    }
    else
    {
      *((_QWORD *)this + 6) = *v16 + 16 * v18;
    }
    if ( (_DWORD)v4 )
    {
      v19 = *((_QWORD *)this + 6);
      v28 = 0;
      v20 = (v19 - *v16) >> 4;
      v26 = 0;
      v21 = v20 + v4;
      if ( v20 + v4 >= v20 )
      {
        if ( v20 + v4 > v20 )
        {
          if ( v21 <= (__int64)(*((_QWORD *)this + 7) - *((_QWORD *)this + 5)) >> 4 )
            *((_QWORD *)this + 6) = std::_Uninitialized_value_construct_n<std::allocator<tagRECT>>(
                                      v19,
                                      v4,
                                      (char *)this + 40);
          else
            std::vector<tagRECT>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 40);
        }
      }
      else
      {
        *((_QWORD *)this + 6) = *v16 + 16 * v21;
      }
      v22 = *((_QWORD *)this + 4);
      *((_QWORD *)&v26 + 1) = *v16 + 16 * v20;
      LODWORD(v26) = v4;
      v23 = ((__int64 (__fastcall *)(__int64, __int64, __int128 *, int *))qword_180057B70)(
              IddDriverGlobals,
              v22,
              &v26,
              &v28);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x190,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp",
          (const char *)(unsigned int)v23,
          v24);
    }
  }
}

```

## disassembly

```asm
0x18002cffc  mov     [rsp-28h+arg_0], rbx
0x18002d001  mov     [rsp-28h+arg_8], rsi
0x18002d006  push    rbp
0x18002d007  push    rdi
0x18002d008  push    r12
0x18002d00a  push    r14
0x18002d00c  push    r15
0x18002d00e  mov     rbp, rsp
0x18002d011  sub     rsp, 40h
0x18002d015  mov     r12, r8
0x18002d018  mov     esi, edx
0x18002d01a  mov     r15, rcx
0x18002d01d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RdpIddSkippedDirtyList@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RdpIddSkippedDirtyList@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RdpIddSkippedDirtyList> `wil::Feature<__WilFeatureTraits_Feature_RdpIddSkippedDirtyList>::GetImpl(void)'::`2'::impl
0x18002d024  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RdpIddSkippedDirtyList@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RdpIddSkippedDirtyList>::__private_IsEnabled(void)
0x18002d029  test    al, al
0x18002d02b  jz      loc_18002D17C
0x18002d031  test    esi, esi
0x18002d033  jz      loc_18002D164
0x18002d039  lea     rbx, [r15+28h]
0x18002d03d  mov     [rbp+arg_18], 0
0x18002d044  mov     rcx, [rbx+8]
0x18002d048  xorps   xmm0, xmm0
0x18002d04b  mov     rdi, rcx
0x18002d04e  sub     rdi, [rbx]
0x18002d051  sar     rdi, 4
0x18002d055  movups  [rbp+var_10], xmm0
0x18002d059  lea     rdx, [rsi+rdi]
0x18002d05d  cmp     rdx, rdi
0x18002d060  jnb     short loc_18002D06F
0x18002d062  shl     rdx, 4
0x18002d066  add     rdx, [rbx]
0x18002d069  mov     [rbx+8], rdx
0x18002d06d  jmp     short loc_18002D09A
0x18002d06f  jbe     short loc_18002D09A
0x18002d071  mov     rax, [rbx+10h]
0x18002d075  sub     rax, [rbx]
0x18002d078  sar     rax, 4
0x18002d07c  cmp     rdx, rax
0x18002d07f  jbe     short loc_18002D08B
0x18002d081  mov     rcx, rbx
0x18002d084  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<tagRECT>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002d089  jmp     short loc_18002D09A
0x18002d08b  mov     r8, rbx
0x18002d08e  mov     rdx, rsi
0x18002d091  call    ??$_Uninitialized_value_construct_n@V?$allocator@UtagRECT@@@std@@@std@@YAPEAUtagRECT@@PEAU1@_KAEAV?$allocator@UtagRECT@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<tagRECT>>(tagRECT *,unsigned __int64,std::allocator<tagRECT> &)
0x18002d096  mov     [rbx+8], rax
0x18002d09a  mov     rcx, [rbx]
0x18002d09d  lea     r9, [rbp+arg_18]
0x18002d0a1  mov     rdx, [r15+20h]
0x18002d0a5  lea     r8, [rbp+var_10]
0x18002d0a9  mov     rax, cs:qword_180057B70
0x18002d0b0  mov     r14, rdi
0x18002d0b3  shl     r14, 4
0x18002d0b7  add     rcx, r14
0x18002d0ba  mov     dword ptr [rbp+var_10], esi
0x18002d0bd  mov     qword ptr [rbp+var_10+8], rcx
0x18002d0c1  mov     rcx, cs:IddDriverGlobals
0x18002d0c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0cd  mov     rcx, [rbp+28h]; this
0x18002d0d1  lea     rdx, aIddcxswapchain_3; "IddCxSwapChainGetDirtyRects failed"
0x18002d0d8  mov     qword ptr [rsp+40h+var_20], rdx; int
0x18002d0dd  lea     r8, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002d0e4  mov     edx, 15Eh; void *
0x18002d0e9  mov     r9d, eax; char *
0x18002d0ec  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002d0f1  cmp     esi, 1
0x18002d0f4  jnz     short loc_18002D164
0x18002d0f6  mov     rax, qword ptr [rbp+var_10+8]
0x18002d0fa  cmp     dword ptr [rax], 0
0x18002d0fd  jnz     short loc_18002D164
0x18002d0ff  cmp     dword ptr [rax+4], 0
0x18002d103  jnz     short loc_18002D164
0x18002d105  cmp     dword ptr [rax+8], 0
0x18002d109  jnz     short loc_18002D164
0x18002d10b  cmp     dword ptr [rax+0Ch], 0
0x18002d10f  jnz     short loc_18002D164
0x18002d111  mov     rdx, [rbx]
0x18002d114  mov     rcx, [rbx+8]
0x18002d118  sub     rcx, rdx
0x18002d11b  sar     rcx, 4
0x18002d11f  cmp     rdi, rcx
0x18002d122  jnb     short loc_18002D12A
0x18002d124  lea     rax, [r14+rdx]
0x18002d128  jmp     short loc_18002D15B
0x18002d12a  jbe     short loc_18002D15F
0x18002d12c  mov     rax, [rbx+10h]
0x18002d130  sub     rax, rdx
0x18002d133  sar     rax, 4
0x18002d137  cmp     rdi, rax
0x18002d13a  jbe     short loc_18002D149
0x18002d13c  mov     rdx, rdi
0x18002d13f  mov     rcx, rbx
0x18002d142  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<tagRECT>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002d147  jmp     short loc_18002D15F
0x18002d149  sub     rdi, rcx
0x18002d14c  mov     r8, rbx
0x18002d14f  mov     rcx, [rbx+8]
0x18002d153  mov     rdx, rdi
0x18002d156  call    ??$_Uninitialized_value_construct_n@V?$allocator@UtagRECT@@@std@@@std@@YAPEAUtagRECT@@PEAU1@_KAEAV?$allocator@UtagRECT@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<tagRECT>>(tagRECT *,unsigned __int64,std::allocator<tagRECT> &)
0x18002d15b  mov     [rbx+8], rax
0x18002d15f  mov     byte ptr [r12], 1
0x18002d164  mov     rbx, [rsp+40h+arg_0]
0x18002d169  mov     rsi, [rsp+40h+arg_8]
0x18002d16e  add     rsp, 40h
0x18002d172  pop     r15
0x18002d174  pop     r14
0x18002d176  pop     r12
0x18002d178  pop     rdi
0x18002d179  pop     rbp
0x18002d17a  retn
0x18002d17c  lea     rbx, [r15+28h]
0x18002d180  mov     rcx, [rbx+8]
0x18002d184  mov     rax, rcx
0x18002d187  sub     rax, [rbx]
0x18002d18a  sar     rax, 4
0x18002d18e  lea     rdx, [rax+rsi]
0x18002d192  cmp     rdx, rax
0x18002d195  jnb     short loc_18002D1A4
0x18002d197  shl     rdx, 4
0x18002d19b  add     rdx, [rbx]
0x18002d19e  mov     [rbx+8], rdx
0x18002d1a2  jmp     short loc_18002D1CF
0x18002d1a4  jbe     short loc_18002D1CF
0x18002d1a6  mov     rax, [rbx+10h]
0x18002d1aa  sub     rax, [rbx]
0x18002d1ad  sar     rax, 4
0x18002d1b1  cmp     rdx, rax
0x18002d1b4  jbe     short loc_18002D1C0
0x18002d1b6  mov     rcx, rbx
0x18002d1b9  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<tagRECT>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002d1be  jmp     short loc_18002D1CF
0x18002d1c0  mov     r8, rbx
0x18002d1c3  mov     rdx, rsi
0x18002d1c6  call    ??$_Uninitialized_value_construct_n@V?$allocator@UtagRECT@@@std@@@std@@YAPEAUtagRECT@@PEAU1@_KAEAV?$allocator@UtagRECT@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<tagRECT>>(tagRECT *,unsigned __int64,std::allocator<tagRECT> &)
0x18002d1cb  mov     [rbx+8], rax
0x18002d1cf  test    esi, esi
0x18002d1d1  jz      short loc_18002D164
0x18002d1d3  mov     rcx, [rbx+8]
0x18002d1d7  xorps   xmm0, xmm0
0x18002d1da  mov     rdi, rcx
0x18002d1dd  mov     [rbp+arg_18], 0
0x18002d1e4  sub     rdi, [rbx]
0x18002d1e7  sar     rdi, 4
0x18002d1eb  movups  [rbp+var_10], xmm0
0x18002d1ef  lea     rdx, [rdi+rsi]
0x18002d1f3  cmp     rdx, rdi
0x18002d1f6  jnb     short loc_18002D205
0x18002d1f8  shl     rdx, 4
0x18002d1fc  add     rdx, [rbx]
0x18002d1ff  mov     [rbx+8], rdx
0x18002d203  jmp     short loc_18002D230
0x18002d205  jbe     short loc_18002D230
0x18002d207  mov     rax, [rbx+10h]
0x18002d20b  sub     rax, [rbx]
0x18002d20e  sar     rax, 4
0x18002d212  cmp     rdx, rax
0x18002d215  jbe     short loc_18002D221
0x18002d217  mov     rcx, rbx
0x18002d21a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<tagRECT>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002d21f  jmp     short loc_18002D230
0x18002d221  mov     r8, rbx
0x18002d224  mov     rdx, rsi
0x18002d227  call    ??$_Uninitialized_value_construct_n@V?$allocator@UtagRECT@@@std@@@std@@YAPEAUtagRECT@@PEAU1@_KAEAV?$allocator@UtagRECT@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<tagRECT>>(tagRECT *,unsigned __int64,std::allocator<tagRECT> &)
0x18002d22c  mov     [rbx+8], rax
0x18002d230  mov     rdx, [r15+20h]
0x18002d234  lea     r9, [rbp+arg_18]
0x18002d238  mov     rcx, cs:IddDriverGlobals
0x18002d23f  lea     r8, [rbp+var_10]
0x18002d243  mov     rax, cs:qword_180057B70
0x18002d24a  shl     rdi, 4
0x18002d24e  add     rdi, [rbx]
0x18002d251  mov     qword ptr [rbp+var_10+8], rdi
0x18002d255  mov     dword ptr [rbp+var_10], esi
0x18002d258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d25d  test    eax, eax
0x18002d25f  jns     loc_18002D164
0x18002d265  mov     rcx, [rbp+28h]; this
0x18002d269  lea     r8, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002d270  mov     r9d, eax; char *
0x18002d273  mov     edx, 190h; void *
0x18002d278  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
