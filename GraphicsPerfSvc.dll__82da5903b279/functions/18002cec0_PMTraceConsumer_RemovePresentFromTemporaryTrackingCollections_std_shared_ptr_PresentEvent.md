# PMTraceConsumer::RemovePresentFromTemporaryTrackingCollections(std::shared_ptr<PresentEvent> &)

- ea: `0x18002cec0`
- end: `0x18002d305`
- name: `?RemovePresentFromTemporaryTrackingCollections@PMTraceConsumer@@QEAAXAEAV?$shared_ptr@UPresentEvent@@@std@@@Z`
- size: `1093`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: ``

## callers

- `0x180029254`
- `0x18002c13c`
- `0x18002cd94`

## callees

- `0x18000bcc0`
- `0x18000d67c`
- `0x18001139c`
- `0x180016b10`
- `0x18001b5cc`
- `0x180027f38`
- `0x180028630`
- `0x180028654`
- `0x18002869c`
- `0x180029018`
- `0x18002cec0`
- `0x18002df04`
- `0x18002e178`
- `0x18002e218`
- `0x18002e250`

## pseudocode

```c
__int64 __fastcall PMTraceConsumer::RemovePresentFromTemporaryTrackingCollections(_QWORD *a1, __int64 *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rax
  _DWORD *v6; // r8
  _DWORD *v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  std::_Ref_count_base **v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // r14
  __int64 result; // rax
  std::_Ref_count_base **v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // r14
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  std::_Ref_count_base *v23[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v24; // [rsp+30h] [rbp-48h]
  std::_Ref_count_base *v25; // [rsp+38h] [rbp-40h] BYREF
  __int64 v26; // [rsp+40h] [rbp-38h]
  __int64 v27; // [rsp+48h] [rbp-30h]
  _QWORD v28[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v29; // [rsp+60h] [rbp-18h]
  __int64 v30; // [rsp+B0h] [rbp+38h] BYREF

  v4 = (_QWORD *)std::map<unsigned int,std::map<unsigned __int64,std::shared_ptr<PresentEvent>>>::_Try_emplace<unsigned int,>(
                   a1 + 54,
                   v23,
                   *a2 + 8);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::erase(*v4 + 40LL);
  v5 = *a2;
  *(_OWORD *)v23 = 0;
  std::shared_ptr<PresentEvent>::operator=((_QWORD *)(a1[49] + 16LL * *(unsigned int *)(v5 + 64)), (__int64 *)v23);
  if ( v23[1] )
    std::_Ref_count_base::_Decref(v23[1]);
  std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(
    a1 + 52,
    &v30,
    *a2 + 12);
  if ( v30 != a1[52] && *(_QWORD *)(v30 + 40) == *a2 )
    std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>>,0>(
      a1 + 52,
      &v30,
      v30);
  v6 = (_DWORD *)(*a2 + 148);
  if ( *v6 )
  {
    std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(
      a1 + 52,
      &v30,
      v6);
    if ( v30 != a1[52] && *(_QWORD *)(v30 + 40) == *a2 )
      std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>>,0>(
        a1 + 52,
        &v30,
        v30);
  }
  v7 = (_DWORD *)(*a2 + 136);
  if ( *v7 )
  {
    std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(
      a1 + 56,
      &v30,
      v7);
    if ( v30 != a1[56] && *(_QWORD *)(v30 + 40) == *a2 )
      std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>>,0>(
        a1 + 56,
        &v30,
        v30);
  }
  v8 = *a2;
  v9 = *(_QWORD *)(*a2 + 128);
  if ( v9 )
  {
    v25 = *(std::_Ref_count_base **)(v8 + 88);
    v10 = *(_QWORD *)(v8 + 80);
    v27 = v9;
    v26 = v10;
    std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::find(
      a1 + 58,
      &v30,
      &v25);
    if ( v30 != a1[58] && *(_QWORD *)(v30 + 56) == *a2 )
      std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>,0>(
        a1 + 58,
        &v30,
        v30);
  }
  if ( *(_QWORD *)(*a2 + 120) )
  {
    std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(
      a1 + 60,
      &v30);
    if ( v30 != a1[60] && *(_QWORD *)(v30 + 40) == *a2 )
      std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>>,0>(
        a1 + 60,
        &v30,
        v30);
  }
  if ( *(_QWORD *)(*a2 + 72) )
  {
    std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(
      a1 + 62,
      &v30);
    if ( v30 != a1[62] && *(_QWORD *)(v30 + 40) == *a2 )
      std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>>,0>(
        a1 + 62,
        &v30,
        v30);
  }
  if ( *(_QWORD *)(*a2 + 112) )
  {
    std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(
      a1 + 64,
      &v30);
    if ( v30 != a1[64] && *(_QWORD *)(v30 + 40) == *a2 )
      std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>>,0>(
        a1 + 64,
        &v30,
        v30);
  }
  if ( *(_QWORD *)(*a2 + 112) )
  {
    std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(
      a1 + 78,
      &v30);
    if ( v30 != a1[78] && *(_QWORD *)(v30 + 40) == *a2 )
      std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>>,0>(
        a1 + 78,
        &v30,
        v30);
  }
  if ( *(_QWORD *)(*a2 + 16) )
  {
    v11 = (std::_Ref_count_base **)(a1 + 71);
    v23[1] = 0;
    v12 = a1[74];
    v13 = v12 + a1[75];
    v24 = v13;
    v23[0] = a1 == (_QWORD *)-568LL ? 0LL : *v11;
    v26 = 0;
    v27 = v12;
    v25 = a1 == (_QWORD *)-568LL ? 0LL : *v11;
    ((void (__fastcall *)(_QWORD *, std::_Ref_count_base **, std::_Ref_count_base **, __int64 *))std::find<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>,std::shared_ptr<PresentEvent>>)(
      v28,
      &v25,
      v23,
      a2);
    if ( v29 != v13 )
    {
      v27 = v29;
      v25 = (std::_Ref_count_base *)v28[0];
      v26 = 0;
      std::deque<std::shared_ptr<PresentEvent>>::erase(a1 + 71, v28, &v25);
    }
  }
  result = *a2;
  if ( *(_BYTE *)(*a2 + 256) )
  {
    v15 = (std::_Ref_count_base **)(a1 + 66);
    v26 = 0;
    v16 = a1[69];
    v17 = v16 + a1[70];
    v27 = v17;
    v25 = a1 == (_QWORD *)-528LL ? 0LL : *v15;
    v23[1] = 0;
    v24 = v16;
    v23[0] = a1 == (_QWORD *)-528LL ? 0LL : *v15;
    result = ((__int64 (__fastcall *)(_QWORD *, std::_Ref_count_base **, std::_Ref_count_base **, __int64 *))std::find<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>,std::shared_ptr<PresentEvent>>)(
               v28,
               v23,
               &v25,
               a2);
    if ( v29 != v17 )
    {
      v27 = v29;
      v25 = (std::_Ref_count_base *)v28[0];
      v26 = 0;
      std::deque<std::shared_ptr<PresentEvent>>::erase(a1 + 66, v28, &v25);
      result = *a2;
      *(_BYTE *)(*a2 + 256) = 0;
    }
  }
  if ( *(_QWORD *)(*a2 + 96) )
  {
    result = std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(
               a1 + 80,
               &v30);
    if ( v30 != a1[80] )
    {
      result = *a2;
      if ( *(_QWORD *)(v30 + 40) == *a2 )
        result = std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>>,0>(
                   a1 + 80,
                   &v30,
                   v30);
    }
  }
  v18 = *a2;
  v19 = *(_QWORD *)(*a2 + 192);
  if ( v19 )
  {
    LODWORD(v25) = *(_DWORD *)(v18 + 104);
    v20 = *(_QWORD *)(v18 + 200);
    v27 = v19;
    v26 = v20;
    result = std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned int>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned int>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned int> const,std::shared_ptr<PresentEvent>>>,0>>::find(
               a1 + 82,
               &v30,
               &v25);
    if ( v30 != a1[82] )
    {
      result = *a2;
      if ( *(_QWORD *)(v30 + 56) == *a2 )
      {
        v21 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>>::_Extract(a1 + 82);
        return std::_Tree_node<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>,void *>>>(
                 v22,
                 v21);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002cec0  push    rbp
0x18002cec2  push    rbx
0x18002cec3  push    rsi
0x18002cec4  push    rdi
0x18002cec5  push    r14
0x18002cec7  push    r15
0x18002cec9  mov     rbp, rsp
0x18002cecc  sub     rsp, 78h
0x18002ced0  mov     r8, [rdx]
0x18002ced3  mov     rbx, rdx
0x18002ced6  mov     rdi, rcx
0x18002ced9  lea     rdx, [rbp+var_58]
0x18002cedd  add     r8, 8
0x18002cee1  add     rcx, 1B0h
0x18002cee8  call    ??$_Try_emplace@I$$V@?$map@IV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@@std@@PEAX@std@@_N@1@$$QEAI@Z; std::map<uint,std::map<unsigned __int64,std::shared_ptr<PresentEvent>>>::_Try_emplace<uint,>(uint &&)
0x18002ceed  mov     rdx, [rbx]
0x18002cef0  mov     rcx, [rax]
0x18002cef3  add     rcx, 28h ; '('
0x18002cef7  call    ?erase@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::erase(unsigned __int64 const &)
0x18002cefc  mov     rax, [rbx]
0x18002ceff  lea     rdx, [rbp+var_58]
0x18002cf03  xorps   xmm0, xmm0
0x18002cf06  movdqu  xmmword ptr [rbp+var_58], xmm0
0x18002cf0b  mov     ecx, [rax+40h]
0x18002cf0e  shl     rcx, 4
0x18002cf12  add     rcx, [rdi+188h]
0x18002cf19  call    ??4?$shared_ptr@UPresentEvent@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PresentEvent>::operator=(std::shared_ptr<PresentEvent> &&)
0x18002cf1e  mov     rcx, [rbp+var_58+8]; this
0x18002cf22  xor     r15d, r15d
0x18002cf25  test    rcx, rcx
0x18002cf28  jz      short loc_18002CF2F
0x18002cf2a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002cf2f  mov     r8, [rbx]
0x18002cf32  lea     rsi, [rdi+1A0h]
0x18002cf39  add     r8, 0Ch
0x18002cf3d  lea     rdx, [rbp+arg_0]
0x18002cf41  mov     rcx, rsi
0x18002cf44  call    ?find@?$_Tree@V?$_Tmap_traits@KUProcessInfo@PresentTraceConsumerCore@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,PresentTraceConsumerCore::ProcessInfo,std::less<ulong>,std::allocator<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(ulong const &)
0x18002cf49  mov     r8, [rbp+arg_0]
0x18002cf4d  cmp     r8, [rsi]
0x18002cf50  jz      short loc_18002CF67
0x18002cf52  mov     rax, [rbx]
0x18002cf55  cmp     [r8+28h], rax
0x18002cf59  jnz     short loc_18002CF67
0x18002cf5b  lea     rdx, [rbp+arg_0]
0x18002cf5f  mov     rcx, rsi
0x18002cf62  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>)
0x18002cf67  mov     r8, [rbx]
0x18002cf6a  add     r8, 94h
0x18002cf71  cmp     [r8], r15d
0x18002cf74  jz      short loc_18002CFA0
0x18002cf76  lea     rdx, [rbp+arg_0]
0x18002cf7a  mov     rcx, rsi
0x18002cf7d  call    ?find@?$_Tree@V?$_Tmap_traits@KUProcessInfo@PresentTraceConsumerCore@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,PresentTraceConsumerCore::ProcessInfo,std::less<ulong>,std::allocator<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(ulong const &)
0x18002cf82  mov     r8, [rbp+arg_0]
0x18002cf86  cmp     r8, [rsi]
0x18002cf89  jz      short loc_18002CFA0
0x18002cf8b  mov     rax, [rbx]
0x18002cf8e  cmp     [r8+28h], rax
0x18002cf92  jnz     short loc_18002CFA0
0x18002cf94  lea     rdx, [rbp+arg_0]
0x18002cf98  mov     rcx, rsi
0x18002cf9b  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>)
0x18002cfa0  mov     r8, [rbx]
0x18002cfa3  add     r8, 88h
0x18002cfaa  cmp     [r8], r15d
0x18002cfad  jz      short loc_18002CFE0
0x18002cfaf  lea     rsi, [rdi+1C0h]
0x18002cfb6  mov     rcx, rsi
0x18002cfb9  lea     rdx, [rbp+arg_0]
0x18002cfbd  call    ?find@?$_Tree@V?$_Tmap_traits@KUProcessInfo@PresentTraceConsumerCore@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,PresentTraceConsumerCore::ProcessInfo,std::less<ulong>,std::allocator<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(ulong const &)
0x18002cfc2  mov     r8, [rbp+arg_0]
0x18002cfc6  cmp     r8, [rsi]
0x18002cfc9  jz      short loc_18002CFE0
0x18002cfcb  mov     rax, [rbx]
0x18002cfce  cmp     [r8+28h], rax
0x18002cfd2  jnz     short loc_18002CFE0
0x18002cfd4  lea     rdx, [rbp+arg_0]
0x18002cfd8  mov     rcx, rsi
0x18002cfdb  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>)
0x18002cfe0  mov     rcx, [rbx]
0x18002cfe3  mov     rdx, [rcx+80h]
0x18002cfea  test    rdx, rdx
0x18002cfed  jz      short loc_18002D038
0x18002cfef  mov     rax, [rcx+58h]
0x18002cff3  lea     rsi, [rdi+1D0h]
0x18002cffa  mov     [rbp+var_40], rax
0x18002cffe  lea     r8, [rbp+var_40]
0x18002d002  mov     rax, [rcx+50h]
0x18002d006  mov     rcx, rsi
0x18002d009  mov     [rbp+var_30], rdx
0x18002d00d  lea     rdx, [rbp+arg_0]
0x18002d011  mov     [rbp+var_38], rax
0x18002d015  call    ?find@?$_Tree@V?$_Tmap_traits@V?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@U?$less@V?$tuple@_K_K_K@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@2@AEBV?$tuple@_K_K_K@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::find(std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const &)
0x18002d01a  mov     r8, [rbp+arg_0]
0x18002d01e  cmp     r8, [rsi]
0x18002d021  jz      short loc_18002D038
0x18002d023  mov     rax, [rbx]
0x18002d026  cmp     [r8+38h], rax
0x18002d02a  jnz     short loc_18002D038
0x18002d02c  lea     rdx, [rbp+arg_0]
0x18002d030  mov     rcx, rsi
0x18002d033  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@U?$less@V?$tuple@_K_K_K@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>)
0x18002d038  mov     r8, [rbx]
0x18002d03b  add     r8, 78h ; 'x'
0x18002d03f  cmp     [r8], r15
0x18002d042  jz      short loc_18002D075
0x18002d044  lea     rsi, [rdi+1E0h]
0x18002d04b  mov     rcx, rsi
0x18002d04e  lea     rdx, [rbp+arg_0]
0x18002d052  call    ?find@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(unsigned __int64 const &)
0x18002d057  mov     r8, [rbp+arg_0]
0x18002d05b  cmp     r8, [rsi]
0x18002d05e  jz      short loc_18002D075
0x18002d060  mov     rax, [rbx]
0x18002d063  cmp     [r8+28h], rax
0x18002d067  jnz     short loc_18002D075
0x18002d069  lea     rdx, [rbp+arg_0]
0x18002d06d  mov     rcx, rsi
0x18002d070  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>)
0x18002d075  mov     r8, [rbx]
0x18002d078  add     r8, 48h ; 'H'
0x18002d07c  cmp     [r8], r15
0x18002d07f  jz      short loc_18002D0B2
0x18002d081  lea     rsi, [rdi+1F0h]
0x18002d088  mov     rcx, rsi
0x18002d08b  lea     rdx, [rbp+arg_0]
0x18002d08f  call    ?find@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(unsigned __int64 const &)
0x18002d094  mov     r8, [rbp+arg_0]
0x18002d098  cmp     r8, [rsi]
0x18002d09b  jz      short loc_18002D0B2
0x18002d09d  mov     rax, [rbx]
0x18002d0a0  cmp     [r8+28h], rax
0x18002d0a4  jnz     short loc_18002D0B2
0x18002d0a6  lea     rdx, [rbp+arg_0]
0x18002d0aa  mov     rcx, rsi
0x18002d0ad  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>)
0x18002d0b2  mov     r8, [rbx]
0x18002d0b5  add     r8, 70h ; 'p'
0x18002d0b9  cmp     [r8], r15
0x18002d0bc  jz      short loc_18002D0EF
0x18002d0be  lea     rsi, [rdi+200h]
0x18002d0c5  mov     rcx, rsi
0x18002d0c8  lea     rdx, [rbp+arg_0]
0x18002d0cc  call    ?find@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(unsigned __int64 const &)
0x18002d0d1  mov     r8, [rbp+arg_0]
0x18002d0d5  cmp     r8, [rsi]
0x18002d0d8  jz      short loc_18002D0EF
0x18002d0da  mov     rax, [rbx]
0x18002d0dd  cmp     [r8+28h], rax
0x18002d0e1  jnz     short loc_18002D0EF
0x18002d0e3  lea     rdx, [rbp+arg_0]
0x18002d0e7  mov     rcx, rsi
0x18002d0ea  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>)
0x18002d0ef  mov     r8, [rbx]
0x18002d0f2  add     r8, 70h ; 'p'
0x18002d0f6  cmp     [r8], r15
0x18002d0f9  jz      short loc_18002D12C
0x18002d0fb  lea     rsi, [rdi+270h]
0x18002d102  mov     rcx, rsi
0x18002d105  lea     rdx, [rbp+arg_0]
0x18002d109  call    ?find@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(unsigned __int64 const &)
0x18002d10e  mov     r8, [rbp+arg_0]
0x18002d112  cmp     r8, [rsi]
0x18002d115  jz      short loc_18002D12C
0x18002d117  mov     rax, [rbx]
0x18002d11a  cmp     [r8+28h], rax
0x18002d11e  jnz     short loc_18002D12C
0x18002d120  lea     rdx, [rbp+arg_0]
0x18002d124  mov     rcx, rsi
0x18002d127  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>)
0x18002d12c  mov     rax, [rbx]
0x18002d12f  cmp     [rax+10h], r15
0x18002d133  jbe     loc_18002D1BC
0x18002d139  lea     rsi, [rdi+238h]
0x18002d140  mov     [rbp+var_58+8], r15
0x18002d144  mov     rcx, [rsi+18h]
0x18002d148  mov     r14, [rsi+20h]
0x18002d14c  add     r14, rcx
0x18002d14f  mov     [rbp+var_48], r14
0x18002d153  test    rsi, rsi
0x18002d156  jz      short loc_18002D161
0x18002d158  mov     rax, [rsi]
0x18002d15b  mov     [rbp+var_58], rax
0x18002d15f  jmp     short loc_18002D165
0x18002d161  mov     [rbp+var_58], r15
0x18002d165  mov     [rbp+var_38], r15
0x18002d169  mov     [rbp+var_30], rcx
0x18002d16d  test    rsi, rsi
0x18002d170  jz      short loc_18002D17B
0x18002d172  mov     rax, [rsi]
0x18002d175  mov     [rbp+var_40], rax
0x18002d179  jmp     short loc_18002D17F
0x18002d17b  mov     [rbp+var_40], r15
0x18002d17f  mov     r9, rbx
0x18002d182  lea     r8, [rbp+var_58]
0x18002d186  lea     rdx, [rbp+var_40]
0x18002d18a  lea     rcx, [rbp+var_28]
0x18002d18e  call    ??$find@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@0@V10@V10@AEBV?$shared_ptr@UPresentEvent@@@0@@Z; std::find<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>,std::shared_ptr<PresentEvent>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>,std::shared_ptr<PresentEvent> const &)
0x18002d193  mov     rdx, [rbp+var_18]
0x18002d197  cmp     rdx, r14
0x18002d19a  jz      short loc_18002D1BC
0x18002d19c  mov     rax, [rbp+var_28]
0x18002d1a0  lea     r8, [rbp+var_40]
0x18002d1a4  mov     [rbp+var_30], rdx
0x18002d1a8  mov     rcx, rsi
0x18002d1ab  lea     rdx, [rbp+var_28]
0x18002d1af  mov     [rbp+var_40], rax
0x18002d1b3  mov     [rbp+var_38], r15
0x18002d1b7  call    ?erase@?$deque@V?$shared_ptr@UPresentEvent@@@std@@V?$allocator@V?$shared_ptr@UPresentEvent@@@std@@@2@@std@@QEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@2@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@2@@Z; std::deque<std::shared_ptr<PresentEvent>>::erase(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>)
0x18002d1bc  mov     rax, [rbx]
0x18002d1bf  cmp     [rax+100h], r15b
0x18002d1c6  jz      loc_18002D259
0x18002d1cc  lea     rsi, [rdi+210h]
0x18002d1d3  mov     [rbp+var_38], r15
0x18002d1d7  mov     rcx, [rsi+18h]
0x18002d1db  mov     r14, [rsi+20h]
0x18002d1df  add     r14, rcx
0x18002d1e2  mov     [rbp+var_30], r14
0x18002d1e6  test    rsi, rsi
0x18002d1e9  jz      short loc_18002D1F4
0x18002d1eb  mov     rax, [rsi]
0x18002d1ee  mov     [rbp+var_40], rax
0x18002d1f2  jmp     short loc_18002D1F8
0x18002d1f4  mov     [rbp+var_40], r15
0x18002d1f8  mov     [rbp+var_58+8], r15
0x18002d1fc  mov     [rbp+var_48], rcx
0x18002d200  test    rsi, rsi
0x18002d203  jz      short loc_18002D20E
0x18002d205  mov     rax, [rsi]
0x18002d208  mov     [rbp+var_58], rax
0x18002d20c  jmp     short loc_18002D212
0x18002d20e  mov     [rbp+var_58], r15
0x18002d212  mov     r9, rbx
0x18002d215  lea     r8, [rbp+var_40]
0x18002d219  lea     rdx, [rbp+var_58]
0x18002d21d  lea     rcx, [rbp+var_28]
0x18002d221  call    ??$find@V?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@YA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@0@V10@V10@AEBV?$shared_ptr@UPresentEvent@@@0@@Z; std::find<std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>,std::shared_ptr<PresentEvent>>(std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>,std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>,std::shared_ptr<PresentEvent> const &)
0x18002d226  mov     rdx, [rbp+var_18]
0x18002d22a  cmp     rdx, r14
0x18002d22d  jz      short loc_18002D259
0x18002d22f  mov     rax, [rbp+var_28]
0x18002d233  lea     r8, [rbp+var_40]
0x18002d237  mov     [rbp+var_30], rdx
0x18002d23b  mov     rcx, rsi
0x18002d23e  lea     rdx, [rbp+var_28]
0x18002d242  mov     [rbp+var_40], rax
0x18002d246  mov     [rbp+var_38], r15
0x18002d24a  call    ?erase@?$deque@V?$shared_ptr@UPresentEvent@@@std@@V?$allocator@V?$shared_ptr@UPresentEvent@@@std@@@2@@std@@QEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@2@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@2@@Z; std::deque<std::shared_ptr<PresentEvent>>::erase(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>)
0x18002d24f  mov     rax, [rbx]
0x18002d252  mov     [rax+100h], r15b
0x18002d259  mov     r8, [rbx]
0x18002d25c  add     r8, 60h ; '`'
0x18002d260  cmp     [r8], r15
0x18002d263  jz      short loc_18002D296
0x18002d265  lea     rsi, [rdi+280h]
0x18002d26c  mov     rcx, rsi
0x18002d26f  lea     rdx, [rbp+arg_0]
0x18002d273  call    ?find@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(unsigned __int64 const &)
0x18002d278  mov     r8, [rbp+arg_0]
0x18002d27c  cmp     r8, [rsi]
0x18002d27f  jz      short loc_18002D296
0x18002d281  mov     rax, [rbx]
0x18002d284  cmp     [r8+28h], rax
0x18002d288  jnz     short loc_18002D296
0x18002d28a  lea     rdx, [rbp+arg_0]
0x18002d28e  mov     rcx, rsi
0x18002d291  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>)
0x18002d296  mov     rcx, [rbx]
0x18002d299  mov     rdx, [rcx+0C0h]
0x18002d2a0  test    rdx, rdx
0x18002d2a3  jz      short loc_18002D2F8
0x18002d2a5  mov     eax, [rcx+68h]
0x18002d2a8  lea     r8, [rbp+var_40]
0x18002d2ac  mov     dword ptr [rbp+var_40], eax
0x18002d2af  mov     rax, [rcx+0C8h]
0x18002d2b6  lea     rcx, [rdi+290h]
0x18002d2bd  mov     [rbp+var_30], rdx
0x18002d2c1  lea     rdx, [rbp+arg_0]
0x18002d2c5  mov     [rbp+var_38], rax
0x18002d2c9  call    ?find@?$_Tree@V?$_Tmap_traits@V?$tuple@_K_KI@std@@V?$shared_ptr@UPresentEvent@@@2@U?$less@V?$tuple@_K_KI@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@_K_KI@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_KI@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@2@AEBV?$tuple@_K_KI@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,uint>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,uint>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,uint> const,std::shared_ptr<PresentEvent>>>,0>>::find(std::tuple<unsigned __int64,unsigned __int64,uint> const &)
0x18002d2ce  mov     rdx, [rbp+arg_0]
0x18002d2d2  cmp     rdx, [rdi+290h]
0x18002d2d9  jz      short loc_18002D2F8
0x18002d2db  mov     rax, [rbx]
0x18002d2de  cmp     [rdx+38h], rax
0x18002d2e2  jnz     short loc_18002D2F8
0x18002d2e4  lea     rcx, [rdi+290h]
0x18002d2eb  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>>,std::_Iterator_base0>)
0x18002d2f0  mov     rdx, rax
0x18002d2f3  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>,void *>> &,std::_Tree_node<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>,void *> *)
0x18002d2f8  add     rsp, 78h
0x18002d2fc  pop     r15
0x18002d2fe  pop     r14
0x18002d300  pop     rdi
0x18002d301  pop     rsi
0x18002d302  pop     rbx
0x18002d303  pop     rbp
0x18002d304  retn
```
