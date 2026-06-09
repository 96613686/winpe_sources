# PMTraceConsumer::CompletePresentHelper(std::shared_ptr<PresentEvent>,std::map<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>> *)

- ea: `0x180029254`
- end: `0x180029582`
- name: `?CompletePresentHelper@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@PEAV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@3@@Z`
- size: `814`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180029130`
- `0x180029254`

## callees

- `0x18000d67c`
- `0x18000e3e4`
- `0x18000fcec`
- `0x180018810`
- `0x18001c088`
- `0x180027f38`
- `0x18002833c`
- `0x1800284f0`
- `0x180028928`
- `0x180028e5c`
- `0x180029254`
- `0x18002cd04`
- `0x18002cd94`
- `0x18002cec0`
- `0x18002dd7c`
- `0x18002ddb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall PMTraceConsumer::CompletePresentHelper(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rcx
  int v9; // edx
  __int64 v10; // r14
  __int64 *v11; // r15
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rdx
  _QWORD *v16; // rax
  __int64 v17; // r14
  __int64 v18; // rbx
  __int64 v19; // r15
  _QWORD *v20; // rdx
  __int64 v21; // r8
  _QWORD *v22; // rax
  __int64 v23; // r8
  __int64 *v24; // rbx
  __int64 v25; // rdx
  _QWORD *v26; // rax
  std::_Ref_count_base *v27; // rcx
  __int64 v28; // [rsp+20h] [rbp-60h] BYREF
  std::_Ref_count_base *v29; // [rsp+28h] [rbp-58h]
  _QWORD v30[2]; // [rsp+30h] [rbp-50h] BYREF
  float v31[16]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v32; // [rsp+C0h] [rbp+40h] BYREF
  __int64 *v33; // [rsp+C8h] [rbp+48h]

  v33 = a2;
  v6 = *a2;
  if ( *(_BYTE *)(*a2 + 170) && *(_DWORD *)(v6 + 160) != 1 )
    *(_DWORD *)(v6 + 160) = 3;
  if ( !*(_BYTE *)(a1 + 66) || *(_BYTE *)(a1 + 67) )
  {
    if ( *(_BYTE *)(a1 + 608) )
    {
      v8 = *a2;
      v9 = *(_DWORD *)(*a2 + 156);
      if ( ((unsigned int)(v9 - 4) <= 1 || (unsigned int)(v9 - 11) <= 1) && !*(_QWORD *)(v8 + 16) )
        *(_DWORD *)(v8 + 160) = 2;
    }
    std::unordered_set<unsigned __int64>::unordered_set<unsigned __int64>(v31);
    v10 = *(_QWORD *)(*a2 + 240) + *(_QWORD *)(*a2 + 248);
    if ( *a2 == -216 )
      v11 = 0;
    else
      v11 = *(__int64 **)(*a2 + 216);
    while ( v10 != *(_QWORD *)(*a2 + 240) )
    {
      --v10;
      if ( v11 )
        v12 = *v11;
      else
        v12 = 0;
      std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(
        &v28,
        *(_QWORD **)(*(_QWORD *)(v12 + 8) + 8 * (v10 & (*(_QWORD *)(v12 + 16) - 1LL))));
      v14 = v28;
      if ( !*(_BYTE *)(v28 + 171)
        && (unsigned __int8)PMTraceConsumer::IsComposedFlipMode(v13, *(unsigned int *)(v28 + 156))
        && !*(_BYTE *)(std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::emplace<unsigned __int64 &>(
                         v31,
                         (__int64)v30,
                         (unsigned __int8 *)(v14 + 112))
                     + 8) )
      {
        *(_DWORD *)(v14 + 160) = 2;
      }
      if ( v29 )
        std::_Ref_count_base::_Decref(v29);
    }
    std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::clear(v31);
    if ( *(_DWORD *)(*a2 + 160)
      || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_UnknownFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GPM_UnknownFix>::GetImpl'::`2'::impl) )
    {
      v17 = *a2;
      v18 = *(_QWORD *)(*a2 + 240);
      v19 = v18 + *(_QWORD *)(*a2 + 248);
      while ( v18 != v19 )
      {
        v20 = *(_QWORD **)(*(_QWORD *)(v17 + 224) + 8 * (v18 & (*(_QWORD *)(v17 + 232) - 1LL)));
        v21 = *v20;
        if ( !*(_BYTE *)(*v20 + 171LL) && *(_DWORD *)(v21 + 160) != 2 )
        {
          *(_QWORD *)(v21 + 40) = *(_QWORD *)(*a2 + 40);
          *(_DWORD *)(*v20 + 160LL) = *(_DWORD *)(*a2 + 160);
        }
        v22 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v28, v20);
        PMTraceConsumer::CompletePresentHelper(a1, v22, a3);
        ++v18;
      }
      std::deque<std::shared_ptr<PresentEvent>>::_Tidy(*a2 + 216);
      PMTraceConsumer::RemovePresentFromTemporaryTrackingCollections((_QWORD *)a1, a2);
      v23 = *a2;
      if ( *(_DWORD *)(*a2 + 160) == 1 && !*(_BYTE *)(v23 + 170) )
      {
        v24 = *(__int64 **)(*(_QWORD *)std::map<unsigned int,std::map<unsigned __int64,std::shared_ptr<PresentEvent>>>::_Try_emplace<unsigned int,>(
                                         a1 + 432,
                                         v30,
                                         v23 + 8)
                          + 40LL);
        v25 = *v24;
        v32 = *v24;
        while ( (__int64 *)v25 != v24 )
        {
          std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v28, (_QWORD *)(v25 + 40));
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(&v32);
          if ( *(_QWORD *)(v28 + 48) == *(_QWORD *)(*a2 + 48) )
          {
            if ( *(_QWORD *)v28 >= *(_QWORD *)*a2 )
            {
              if ( v29 )
                std::_Ref_count_base::_Decref(v29);
              break;
            }
            v26 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(v30, &v28);
            PMTraceConsumer::CompletePresentHelper(a1, v26, a3);
          }
          if ( v29 )
            std::_Ref_count_base::_Decref(v29);
          v25 = v32;
        }
      }
      *(_BYTE *)(*a2 + 170) = 1;
      std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::emplace<unsigned __int64 &,std::shared_ptr<PresentEvent> &>(
        a3,
        v30,
        *a2,
        a2);
    }
    else
    {
      LOBYTE(v15) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl'::`2'::impl,
        v15);
      v16 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v28, a2);
      PMTraceConsumer::RemoveLostPresent(a1, v16);
    }
    std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>((__int64)v31);
  }
  else
  {
    v7 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v28, a2);
    PMTraceConsumer::RemoveLostPresent(a1, v7);
  }
  v27 = (std::_Ref_count_base *)a2[1];
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
}

```

## disassembly

```asm
0x180029254  mov     [rsp-38h+arg_8], rdx
0x180029259  push    rbp
0x18002925a  push    rbx
0x18002925b  push    rsi
0x18002925c  push    rdi
0x18002925d  push    r12
0x18002925f  push    r14
0x180029261  push    r15
0x180029263  mov     rbp, rsp
0x180029266  sub     rsp, 80h
0x18002926d  mov     r12, r8
0x180029270  mov     rdi, rdx
0x180029273  mov     rsi, rcx
0x180029276  mov     rax, [rdx]
0x180029279  cmp     byte ptr [rax+0AAh], 0
0x180029280  jz      short loc_180029295
0x180029282  cmp     dword ptr [rax+0A0h], 1
0x180029289  jz      short loc_180029295
0x18002928b  mov     dword ptr [rax+0A0h], 3
0x180029295  cmp     byte ptr [rcx+42h], 0
0x180029299  jz      short loc_1800292BA
0x18002929b  cmp     byte ptr [rcx+43h], 0
0x18002929f  jnz     short loc_1800292BA
0x1800292a1  lea     rcx, [rbp+var_60]
0x1800292a5  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x1800292aa  mov     rdx, rax
0x1800292ad  mov     rcx, rsi
0x1800292b0  call    ?RemoveLostPresent@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@@Z; PMTraceConsumer::RemoveLostPresent(std::shared_ptr<PresentEvent>)
0x1800292b5  jmp     loc_180029562
0x1800292ba  cmp     byte ptr [rcx+260h], 0
0x1800292c1  jz      short loc_1800292ED
0x1800292c3  mov     rcx, [rdx]
0x1800292c6  mov     edx, [rcx+9Ch]
0x1800292cc  lea     eax, [rdx-4]
0x1800292cf  cmp     eax, 1
0x1800292d2  jbe     short loc_1800292DC
0x1800292d4  lea     eax, [rdx-0Bh]
0x1800292d7  cmp     eax, 1
0x1800292da  ja      short loc_1800292ED
0x1800292dc  cmp     qword ptr [rcx+10h], 0
0x1800292e1  jnz     short loc_1800292ED
0x1800292e3  mov     dword ptr [rcx+0A0h], 2
0x1800292ed  lea     rcx, [rbp+var_40]
0x1800292f1  call    ??0?$unordered_set@_KU?$hash@_K@std@@U?$equal_to@_K@2@V?$allocator@_K@2@@std@@QEAA@XZ; std::unordered_set<unsigned __int64>::unordered_set<unsigned __int64>(void)
0x1800292f6  nop
0x1800292f7  mov     rdx, [rdi]
0x1800292fa  add     rdx, 0D8h
0x180029301  mov     r14, [rdx+20h]
0x180029305  add     r14, [rdx+18h]
0x180029309  test    rdx, rdx
0x18002930c  jz      short loc_180029313
0x18002930e  mov     r15, [rdx]
0x180029311  jmp     short loc_180029316
0x180029313  xor     r15d, r15d
0x180029316  mov     rax, [rdi]
0x180029319  cmp     r14, [rax+0F0h]
0x180029320  jz      short loc_18002939D
0x180029322  dec     r14
0x180029325  test    r15, r15
0x180029328  jz      short loc_18002932F
0x18002932a  mov     rdx, [r15]
0x18002932d  jmp     short loc_180029331
0x18002932f  xor     edx, edx
0x180029331  mov     rax, [rdx+10h]
0x180029335  dec     rax
0x180029338  and     rax, r14
0x18002933b  mov     rdx, [rdx+8]
0x18002933f  mov     rdx, [rdx+rax*8]
0x180029343  lea     rcx, [rbp+var_60]
0x180029347  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002934c  nop
0x18002934d  mov     rbx, [rbp+var_60]
0x180029351  cmp     byte ptr [rbx+0ABh], 0
0x180029358  jnz     short loc_18002938A
0x18002935a  mov     edx, [rbx+9Ch]
0x180029360  call    ?IsComposedFlipMode@PMTraceConsumer@@QEAA_NW4PresentMode@@@Z; PMTraceConsumer::IsComposedFlipMode(PresentMode)
0x180029365  test    al, al
0x180029367  jz      short loc_18002938A
0x180029369  lea     r8, [rbx+70h]
0x18002936d  lea     rdx, [rbp+var_50]
0x180029371  lea     rcx, [rbp+var_40]
0x180029375  call    ??$emplace@AEA_K@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@std@@_N@1@AEA_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::emplace<unsigned __int64 &>(unsigned __int64 &)
0x18002937a  cmp     byte ptr [rax+8], 0
0x18002937e  jnz     short loc_18002938A
0x180029380  mov     dword ptr [rbx+0A0h], 2
0x18002938a  mov     rcx, [rbp+var_58]; this
0x18002938e  test    rcx, rcx
0x180029391  jz      short loc_180029316
0x180029393  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029398  jmp     loc_180029316
0x18002939d  lea     rcx, [rbp+var_40]
0x1800293a1  call    ?clear@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::clear(void)
0x1800293a6  mov     rax, [rdi]
0x1800293a9  cmp     dword ptr [rax+0A0h], 0
0x1800293b0  jnz     short loc_1800293EC
0x1800293b2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_UnknownFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_UnknownFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_UnknownFix> `wil::Feature<__WilFeatureTraits_Feature_GPM_UnknownFix>::GetImpl(void)'::`2'::impl
0x1800293b9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_UnknownFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_UnknownFix>::__private_IsEnabled(void)
0x1800293be  test    al, al
0x1800293c0  jz      short loc_1800293EC
0x1800293c2  mov     dl, 1
0x1800293c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_MultiMon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon> `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl(void)'::`2'::impl
0x1800293cb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800293d0  mov     rdx, rdi
0x1800293d3  lea     rcx, [rbp+var_60]
0x1800293d7  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x1800293dc  mov     rdx, rax
0x1800293df  mov     rcx, rsi
0x1800293e2  call    ?RemoveLostPresent@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@@Z; PMTraceConsumer::RemoveLostPresent(std::shared_ptr<PresentEvent>)
0x1800293e7  jmp     loc_180029558
0x1800293ec  mov     r14, [rdi]
0x1800293ef  mov     rbx, [r14+0F0h]
0x1800293f6  mov     r15, [r14+0F8h]
0x1800293fd  add     r15, rbx
0x180029400  cmp     rbx, r15
0x180029403  jz      short loc_18002946D
0x180029405  mov     rcx, [r14+0E8h]
0x18002940c  dec     rcx
0x18002940f  and     rcx, rbx
0x180029412  mov     rax, [r14+0E0h]
0x180029419  mov     rdx, [rax+rcx*8]
0x18002941d  mov     r8, [rdx]
0x180029420  cmp     byte ptr [r8+0ABh], 0
0x180029428  jnz     short loc_180029451
0x18002942a  cmp     dword ptr [r8+0A0h], 2
0x180029432  jz      short loc_180029451
0x180029434  mov     rax, [rdi]
0x180029437  mov     rcx, [rax+28h]
0x18002943b  mov     [r8+28h], rcx
0x18002943f  mov     rax, [rdi]
0x180029442  mov     rcx, [rdx]
0x180029445  mov     eax, [rax+0A0h]
0x18002944b  mov     [rcx+0A0h], eax
0x180029451  lea     rcx, [rbp+var_60]
0x180029455  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002945a  mov     r8, r12
0x18002945d  mov     rdx, rax
0x180029460  mov     rcx, rsi
0x180029463  call    ?CompletePresentHelper@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@PEAV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@3@@Z; PMTraceConsumer::CompletePresentHelper(std::shared_ptr<PresentEvent>,std::map<unsigned __int64,std::shared_ptr<PresentEvent>> *)
0x180029468  inc     rbx
0x18002946b  jmp     short loc_180029400
0x18002946d  mov     rcx, [rdi]
0x180029470  add     rcx, 0D8h
0x180029477  call    ?_Tidy@?$deque@V?$shared_ptr@UPresentEvent@@@std@@V?$allocator@V?$shared_ptr@UPresentEvent@@@std@@@2@@std@@AEAAXXZ; std::deque<std::shared_ptr<PresentEvent>>::_Tidy(void)
0x18002947c  mov     rdx, rdi
0x18002947f  mov     rcx, rsi
0x180029482  call    ?RemovePresentFromTemporaryTrackingCollections@PMTraceConsumer@@QEAAXAEAV?$shared_ptr@UPresentEvent@@@std@@@Z; PMTraceConsumer::RemovePresentFromTemporaryTrackingCollections(std::shared_ptr<PresentEvent> &)
0x180029487  mov     r8, [rdi]
0x18002948a  cmp     dword ptr [r8+0A0h], 1
0x180029492  jnz     loc_18002953B
0x180029498  cmp     byte ptr [r8+0AAh], 0
0x1800294a0  jnz     loc_18002953B
0x1800294a6  add     r8, 8
0x1800294aa  lea     rcx, [rsi+1B0h]
0x1800294b1  lea     rdx, [rbp+var_50]
0x1800294b5  call    ??$_Try_emplace@I$$V@?$map@IV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@@std@@PEAX@std@@_N@1@$$QEAI@Z; std::map<uint,std::map<unsigned __int64,std::shared_ptr<PresentEvent>>>::_Try_emplace<uint,>(uint &&)
0x1800294ba  mov     rbx, [rax]
0x1800294bd  mov     rbx, [rbx+28h]
0x1800294c1  mov     rdx, [rbx]
0x1800294c4  mov     [rbp+arg_0], rdx
0x1800294c8  cmp     rdx, rbx
0x1800294cb  jz      short loc_18002953B
0x1800294cd  add     rdx, 28h ; '('
0x1800294d1  lea     rcx, [rbp+var_60]
0x1800294d5  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x1800294da  nop
0x1800294db  lea     rcx, [rbp+arg_0]
0x1800294df  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(void)
0x1800294e4  mov     r9, [rdi]
0x1800294e7  mov     rax, [r9+30h]
0x1800294eb  mov     rcx, [rbp+var_60]
0x1800294ef  cmp     [rcx+30h], rax
0x1800294f3  jnz     short loc_180029519
0x1800294f5  mov     rax, [r9]
0x1800294f8  cmp     [rcx], rax
0x1800294fb  jnb     short loc_18002952D
0x1800294fd  lea     rdx, [rbp+var_60]
0x180029501  lea     rcx, [rbp+var_50]
0x180029505  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002950a  mov     r8, r12
0x18002950d  mov     rdx, rax
0x180029510  mov     rcx, rsi
0x180029513  call    ?CompletePresentHelper@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@PEAV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@3@@Z; PMTraceConsumer::CompletePresentHelper(std::shared_ptr<PresentEvent>,std::map<unsigned __int64,std::shared_ptr<PresentEvent>> *)
0x180029518  nop
0x180029519  mov     rcx, [rbp+var_58]; this
0x18002951d  test    rcx, rcx
0x180029520  jz      short loc_180029527
0x180029522  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029527  mov     rdx, [rbp+arg_0]
0x18002952b  jmp     short loc_1800294C8
0x18002952d  mov     rcx, [rbp+var_58]; this
0x180029531  test    rcx, rcx
0x180029534  jz      short loc_18002953B
0x180029536  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002953b  mov     rax, [rdi]
0x18002953e  mov     byte ptr [rax+0AAh], 1
0x180029545  mov     r9, rdi
0x180029548  mov     r8, [rdi]
0x18002954b  lea     rdx, [rbp+var_50]
0x18002954f  mov     rcx, r12
0x180029552  call    ??$emplace@AEA_KAEAV?$shared_ptr@UPresentEvent@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@_N@1@AEA_KAEAV?$shared_ptr@UPresentEvent@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::emplace<unsigned __int64 &,std::shared_ptr<PresentEvent> &>(unsigned __int64 &,std::shared_ptr<PresentEvent> &)
0x180029557  nop
0x180029558  lea     rcx, [rbp+var_40]
0x18002955c  call    ??1?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>(void)
0x180029561  nop
0x180029562  mov     rcx, [rdi+8]; this
0x180029566  test    rcx, rcx
0x180029569  jz      short loc_180029570
0x18002956b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029570  add     rsp, 80h
0x180029577  pop     r15
0x180029579  pop     r14
0x18002957b  pop     r12
0x18002957d  pop     rdi
0x18002957e  pop     rsi
0x18002957f  pop     rbx
0x180029580  pop     rbp
0x180029581  retn
```
