# PMTraceConsumer::HandleDWMCompositionEvent(std::shared_ptr<PresentEvent> &,uint,unsigned __int64)

- ea: `0x180029c00`
- end: `0x180029dd8`
- name: `?HandleDWMCompositionEvent@PMTraceConsumer@@QEAAXAEAV?$shared_ptr@UPresentEvent@@@std@@I_K@Z`
- size: `472`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002c5d4`
- `0x18002c6a4`

## callees

- `0x18000b5ec`
- `0x18000d67c`
- `0x18000e3e4`
- `0x18000fcec`
- `0x180014a64`
- `0x180029c00`
- `0x18002e178`
- `0x18002e2c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PMTraceConsumer::HandleDWMCompositionEvent(__int64 a1, __int64 *a2, int a3)
{
  __int64 *v6; // rdi
  __int64 v7; // rdx
  unsigned __int64 v8; // r10
  __int64 v9; // rbx
  __int64 result; // rax
  unsigned __int64 v11; // r12
  __int64 v12; // rdi
  __int64 *v13; // rbx
  __int64 v14; // rdx
  _QWORD *v15; // rdx
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // [rsp+20h] [rbp-60h] BYREF
  std::_Ref_count_base *v19; // [rsp+28h] [rbp-58h]
  _QWORD v20[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+40h] [rbp-40h]
  _QWORD v22[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v23; // [rsp+58h] [rbp-28h]
  _BYTE v24[32]; // [rsp+60h] [rbp-20h] BYREF

  v6 = (__int64 *)(a1 + 720);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::_Find_lower_bound<unsigned __int64>(
    a1 + 720,
    v22);
  v9 = v23;
  if ( *(_BYTE *)(v23 + 25) || v8 < *(_QWORD *)(v23 + 32) )
    v9 = *v6;
  result = *a2;
  if ( *(_BYTE *)(*a2 + 257) )
  {
    if ( *(_BYTE *)(a1 + 608) )
    {
      LOBYTE(v7) = 1;
      result = wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(
                 `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl'::`2'::impl,
                 v7);
      if ( v9 != *v6 )
      {
        *(_DWORD *)(*a2 + 184) = a3;
        *(_QWORD *)(*a2 + 192) = *(_QWORD *)(v9 + 40);
        v11 = *(_QWORD *)*a2;
        v20[1] = 0;
        v12 = *(_QWORD *)(a1 + 592);
        v21 = v12;
        if ( a1 == -568 )
          v13 = 0;
        else
          v13 = *(__int64 **)(a1 + 568);
        v20[0] = v13;
        while ( 1 )
        {
          result = *(_QWORD *)(a1 + 592) + *(_QWORD *)(a1 + 600);
          if ( v12 == result )
            break;
          if ( v13 )
            v14 = *v13;
          else
            v14 = 0;
          std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(
            &v18,
            *(_QWORD **)(*(_QWORD *)(v14 + 8) + 8 * (v12 & (*(_QWORD *)(v14 + 16) - 1LL))));
          if ( *(_QWORD *)(v18 + 16) >= v11
            || (v15 = (_QWORD *)*a2, *(_DWORD *)(v18 + 184) != *(_DWORD *)(*a2 + 184))
            || *(_QWORD *)(v18 + 192) != v15[24]
            || (v16 = *(_DWORD *)(v18 + 156), v16 == 3)
            || v16 == 8 )
          {
            ++v12;
          }
          else
          {
            std::deque<std::shared_ptr<PresentEvent>>::push_back(v15 + 27, &v18);
            *(_BYTE *)(*(_QWORD *)std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(v20)
                     + 256LL) = 0;
            v22[1] = 0;
            v22[0] = v13;
            v23 = v12;
            v17 = std::deque<std::shared_ptr<PresentEvent>>::erase(a1 + 568, v24, v22);
            v13 = *(__int64 **)v17;
            v20[0] = *(_QWORD *)v17;
            v12 = *(_QWORD *)(v17 + 16);
          }
          v21 = v12;
          if ( v19 )
            std::_Ref_count_base::_Decref(v19);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029c00  mov     [rsp-28h+arg_0], rbx
0x180029c05  mov     [rsp-28h+arg_8], rsi
0x180029c0a  mov     [rsp-28h+arg_18], r9
0x180029c0f  push    rbp
0x180029c10  push    rdi
0x180029c11  push    r12
0x180029c13  push    r14
0x180029c15  push    r15
0x180029c17  mov     rbp, rsp
0x180029c1a  sub     rsp, 80h
0x180029c21  mov     r10, r9
0x180029c24  mov     r15d, r8d
0x180029c27  mov     r14, rdx
0x180029c2a  mov     rsi, rcx
0x180029c2d  lea     rdi, [rcx+2D0h]
0x180029c34  lea     r8, [rbp+arg_18]
0x180029c38  lea     rdx, [rbp+var_38]
0x180029c3c  mov     rcx, rdi
0x180029c3f  call    ??$_Find_lower_bound@_K@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@PEAX@std@@@1@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::_Find_lower_bound<unsigned __int64>(unsigned __int64 const &)
0x180029c44  mov     rbx, [rbp+var_28]
0x180029c48  cmp     byte ptr [rbx+19h], 0
0x180029c4c  jnz     short loc_180029C54
0x180029c4e  cmp     r10, [rbx+20h]
0x180029c52  jnb     short loc_180029C57
0x180029c54  mov     rbx, [rdi]
0x180029c57  mov     rax, [r14]
0x180029c5a  cmp     byte ptr [rax+101h], 0
0x180029c61  jz      loc_180029DBC
0x180029c67  cmp     byte ptr [rsi+260h], 0
0x180029c6e  jz      loc_180029DBC
0x180029c74  mov     dl, 1
0x180029c76  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_MultiMon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon> `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl(void)'::`2'::impl
0x180029c7d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029c82  cmp     rbx, [rdi]
0x180029c85  jz      loc_180029DBC
0x180029c8b  mov     rax, [r14]
0x180029c8e  mov     [rax+0B8h], r15d
0x180029c95  mov     rcx, [r14]
0x180029c98  mov     rax, [rbx+28h]
0x180029c9c  mov     [rcx+0C0h], rax
0x180029ca3  mov     rax, [r14]
0x180029ca6  mov     r12, [rax]
0x180029ca9  lea     r15, [rsi+238h]
0x180029cb0  mov     [rbp+var_48], 0
0x180029cb8  mov     rdi, [r15+18h]
0x180029cbc  mov     [rbp+var_40], rdi
0x180029cc0  test    r15, r15
0x180029cc3  jz      short loc_180029CCA
0x180029cc5  mov     rbx, [r15]
0x180029cc8  jmp     short loc_180029CCC
0x180029cca  xor     ebx, ebx
0x180029ccc  mov     [rbp+var_50], rbx
0x180029cd0  mov     rax, [rsi+258h]
0x180029cd7  add     rax, [rsi+250h]
0x180029cde  cmp     rdi, rax
0x180029ce1  jz      loc_180029DBC
0x180029ce7  test    rbx, rbx
0x180029cea  jz      short loc_180029CF1
0x180029cec  mov     rdx, [rbx]
0x180029cef  jmp     short loc_180029CF3
0x180029cf1  xor     edx, edx
0x180029cf3  mov     rax, [rdx+10h]
0x180029cf7  dec     rax
0x180029cfa  and     rax, rdi
0x180029cfd  mov     rdx, [rdx+8]
0x180029d01  mov     rdx, [rdx+rax*8]
0x180029d05  lea     rcx, [rbp+var_60]
0x180029d09  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x180029d0e  nop
0x180029d0f  mov     rcx, [rbp+var_60]
0x180029d13  cmp     [rcx+10h], r12
0x180029d17  jnb     loc_180029D9E
0x180029d1d  mov     rdx, [r14]
0x180029d20  mov     eax, [rdx+0B8h]
0x180029d26  cmp     [rcx+0B8h], eax
0x180029d2c  jnz     short loc_180029D9E
0x180029d2e  mov     rax, [rdx+0C0h]
0x180029d35  cmp     [rcx+0C0h], rax
0x180029d3c  jnz     short loc_180029D9E
0x180029d3e  mov     eax, [rcx+9Ch]
0x180029d44  cmp     eax, 3
0x180029d47  jz      short loc_180029D9E
0x180029d49  cmp     eax, 8
0x180029d4c  jz      short loc_180029D9E
0x180029d4e  lea     rcx, [rdx+0D8h]
0x180029d55  lea     rdx, [rbp+var_60]
0x180029d59  call    ?push_back@?$deque@V?$shared_ptr@UPresentEvent@@@std@@V?$allocator@V?$shared_ptr@UPresentEvent@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@UPresentEvent@@@2@@Z; std::deque<std::shared_ptr<PresentEvent>>::push_back(std::shared_ptr<PresentEvent> const &)
0x180029d5e  lea     rcx, [rbp+var_50]
0x180029d62  call    ??C?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@QEBAPEAV?$shared_ptr@UPresentEvent@@@1@XZ; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(void)
0x180029d67  mov     rcx, [rax]
0x180029d6a  mov     byte ptr [rcx+100h], 0
0x180029d71  mov     [rbp+var_30], 0
0x180029d79  mov     [rbp+var_38], rbx
0x180029d7d  mov     [rbp+var_28], rdi
0x180029d81  lea     r8, [rbp+var_38]
0x180029d85  lea     rdx, [rbp+var_20]
0x180029d89  mov     rcx, r15
0x180029d8c  call    ?erase@?$deque@V?$shared_ptr@UPresentEvent@@@std@@V?$allocator@V?$shared_ptr@UPresentEvent@@@std@@@2@@std@@QEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@2@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@2@@Z; std::deque<std::shared_ptr<PresentEvent>>::erase(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>)
0x180029d91  mov     rbx, [rax]
0x180029d94  mov     [rbp+var_50], rbx
0x180029d98  mov     rdi, [rax+10h]
0x180029d9c  jmp     short loc_180029DA1
0x180029d9e  inc     rdi
0x180029da1  mov     [rbp+var_40], rdi
0x180029da5  mov     rcx, [rbp+var_58]; this
0x180029da9  test    rcx, rcx
0x180029dac  jz      loc_180029CD0
0x180029db2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029db7  jmp     loc_180029CD0
0x180029dbc  lea     r11, [rsp+80h+var_s0]
0x180029dc4  mov     rbx, [r11+30h]
0x180029dc8  mov     rsi, [r11+38h]
0x180029dcc  mov     rsp, r11
0x180029dcf  pop     r15
0x180029dd1  pop     r14
0x180029dd3  pop     r12
0x180029dd5  pop     rdi
0x180029dd6  pop     rbp
0x180029dd7  retn
```
