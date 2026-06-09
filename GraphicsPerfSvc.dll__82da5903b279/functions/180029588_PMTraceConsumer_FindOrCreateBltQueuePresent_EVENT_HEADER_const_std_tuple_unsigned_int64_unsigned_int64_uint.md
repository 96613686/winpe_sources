# PMTraceConsumer::FindOrCreateBltQueuePresent(_EVENT_HEADER const &,std::tuple<unsigned __int64,unsigned __int64,uint>)

- ea: `0x180029588`
- end: `0x18002975c`
- name: `?FindOrCreateBltQueuePresent@PMTraceConsumer@@QEAA?AV?$shared_ptr@UPresentEvent@@@std@@AEBU_EVENT_HEADER@@V?$tuple@_K_KI@3@@Z`
- size: `468`
- prototype: `__int64 __fastcall(PMTraceConsumer *this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18002a8c8`

## callees

- `0x18000d67c`
- `0x18001139c`
- `0x180018810`
- `0x180027f38`
- `0x180028558`
- `0x180028630`
- `0x180028714`
- `0x180029018`
- `0x18002905c`
- `0x180029588`
- `0x18002cd20`
- `0x18002d550`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall PMTraceConsumer::FindOrCreateBltQueuePresent(PMTraceConsumer *this, _QWORD *a2, __int64 a3, int *a4)
{
  _QWORD *v6; // rsi
  _QWORD *v8; // r12
  __int64 v9; // rax
  __int64 v10; // r13
  int v11; // r10d
  __int64 v12; // r11
  __int64 v13; // rsi
  __int64 *v14; // r9
  __int64 v15; // rbx
  bool v16; // zf
  __int64 v17; // rax
  _DWORD *v18; // r15
  __int64 v19; // rdi
  __int64 v20; // rcx
  __int64 *v21; // rax
  _DWORD *v23; // [rsp+28h] [rbp-38h] BYREF
  std::_Ref_count_base *v24; // [rsp+30h] [rbp-30h]
  __int128 v25; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v26[24]; // [rsp+48h] [rbp-18h] BYREF
  int v27; // [rsp+A0h] [rbp+40h] BYREF
  _QWORD *v28; // [rsp+A8h] [rbp+48h]
  __int64 i; // [rsp+B0h] [rbp+50h] BYREF

  v28 = a2;
  v6 = a2;
  v25 = 0;
  v23 = (_DWORD *)(a3 + 8);
  v27 = *(_DWORD *)(a3 + 8);
  v8 = (_QWORD *)((char *)this + 416);
  std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(
    (char *)this + 416,
    &i,
    &v27);
  if ( i != *v8 )
  {
    std::shared_ptr<PresentEvent>::operator=(&v25, i + 40);
    goto LABEL_17;
  }
  if ( PMTraceConsumer::IsProcessTrackedForFiltering(this, *(_DWORD *)(a3 + 12)) )
  {
    v27 = *(_DWORD *)(a3 + 12);
    v9 = std::map<unsigned int,std::map<unsigned __int64,std::shared_ptr<PresentEvent>>>::_Try_emplace<unsigned int,>(
           (char *)this + 432,
           v26,
           &v27);
    v10 = *(_QWORD *)v9;
    v11 = *a4;
    v12 = *((_QWORD *)a4 + 1);
    v13 = *((_QWORD *)a4 + 2);
    v14 = *(__int64 **)(*(_QWORD *)v9 + 40LL);
    v15 = *v14;
    for ( i = *v14; ; v15 = i )
    {
      v16 = v15 == (_QWORD)v14;
      if ( (__int64 *)v15 == v14 )
        break;
      v17 = *(_QWORD *)(v15 + 40);
      if ( v13 == *(_QWORD *)(v17 + 192) && v12 == *(_QWORD *)(v17 + 200) && v11 == *(_DWORD *)(v17 + 104) )
      {
        v16 = v15 == (_QWORD)v14;
        break;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(&i);
    }
    v6 = v28;
    if ( !v16 )
    {
      v18 = v23;
      v19 = *(_QWORD *)std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::emplace<unsigned long const &,std::shared_ptr<PresentEvent> &>(
                         v8,
                         &v23,
                         v23,
                         v15 + 40);
      std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>>,0>(
        v10 + 40,
        &i,
        v15);
      std::shared_ptr<PresentEvent>::operator=(&v25, v19 + 40);
      v20 = v25;
      *(_DWORD *)(v25 + 148) = *v18;
LABEL_18:
      *(_QWORD *)(v20 + 192) = *((_QWORD *)a4 + 2);
      *(_QWORD *)(v20 + 200) = *((_QWORD *)a4 + 1);
      *(_DWORD *)(v20 + 104) = *a4;
      *v6 = v20;
      v6[1] = *((_QWORD *)&v25 + 1);
      return v6;
    }
    LODWORD(i) = 2;
    v21 = (__int64 *)std::make_shared<PresentEvent,_EVENT_HEADER const &,enum Runtime>(&v23, a3, &i);
    std::shared_ptr<PresentEvent>::operator=(&v25, v21);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    PMTraceConsumer::TrackPresent(this, &v25, v10 + 40);
LABEL_17:
    v20 = v25;
    goto LABEL_18;
  }
  *v6 = 0;
  v6[1] = 0;
  return v6;
}

```

## disassembly

```asm
0x180029588  mov     [rsp-38h+arg_18], rbx
0x18002958d  mov     [rsp-38h+arg_8], rdx
0x180029592  push    rbp
0x180029593  push    rsi
0x180029594  push    rdi
0x180029595  push    r12
0x180029597  push    r13
0x180029599  push    r14
0x18002959b  push    r15
0x18002959d  mov     rbp, rsp
0x1800295a0  sub     rsp, 60h
0x1800295a4  mov     r14, r9
0x1800295a7  mov     rdi, r8
0x1800295aa  mov     rsi, rdx
0x1800295ad  mov     r15, rcx
0x1800295b0  xor     ebx, ebx
0x1800295b2  xorps   xmm0, xmm0
0x1800295b5  movdqu  [rbp+var_28], xmm0
0x1800295ba  lea     rax, [r8+8]
0x1800295be  mov     [rbp+var_38], rax
0x1800295c2  mov     eax, [rax]
0x1800295c4  mov     [rbp+arg_0], eax
0x1800295c7  lea     r12, [rcx+1A0h]
0x1800295ce  lea     r8, [rbp+arg_0]
0x1800295d2  lea     rdx, [rbp+arg_10]
0x1800295d6  mov     rcx, r12
0x1800295d9  call    ?find@?$_Tree@V?$_Tmap_traits@KUProcessInfo@PresentTraceConsumerCore@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,PresentTraceConsumerCore::ProcessInfo,std::less<ulong>,std::allocator<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(ulong const &)
0x1800295de  mov     rdx, [rbp+arg_10]
0x1800295e2  cmp     rdx, [r12]
0x1800295e6  jz      short loc_1800295FA
0x1800295e8  add     rdx, 28h ; '('
0x1800295ec  lea     rcx, [rbp+var_28]
0x1800295f0  call    ??4?$shared_ptr@UPresentEvent@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<PresentEvent>::operator=(std::shared_ptr<PresentEvent> const &)
0x1800295f5  jmp     loc_180029708
0x1800295fa  mov     edx, [rdi+0Ch]; unsigned int
0x1800295fd  mov     rcx, r15; this
0x180029600  call    ?IsProcessTrackedForFiltering@PMTraceConsumer@@QEAA_NI@Z; PMTraceConsumer::IsProcessTrackedForFiltering(uint)
0x180029605  test    al, al
0x180029607  jnz     short loc_180029615
0x180029609  mov     [rsi], rbx
0x18002960c  mov     [rsi+8], rbx
0x180029610  jmp     loc_180029741
0x180029615  mov     eax, [rdi+0Ch]
0x180029618  mov     [rbp+arg_0], eax
0x18002961b  lea     rcx, [r15+1B0h]
0x180029622  lea     r8, [rbp+arg_0]
0x180029626  lea     rdx, [rbp+var_18]
0x18002962a  call    ??$_Try_emplace@I$$V@?$map@IV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@@std@@PEAX@std@@_N@1@$$QEAI@Z; std::map<uint,std::map<unsigned __int64,std::shared_ptr<PresentEvent>>>::_Try_emplace<uint,>(uint &&)
0x18002962f  mov     r13, [rax]
0x180029632  mov     r10d, [r14]
0x180029635  mov     r11, [r14+8]
0x180029639  mov     rsi, [r14+10h]
0x18002963d  mov     r9, [r13+28h]
0x180029641  mov     rbx, [r9]
0x180029644  mov     [rbp+arg_10], rbx
0x180029648  cmp     rbx, r9
0x18002964b  jz      short loc_18002967B
0x18002964d  mov     rax, [rbx+28h]
0x180029651  cmp     rsi, [rax+0C0h]
0x180029658  jnz     short loc_180029669
0x18002965a  cmp     r11, [rax+0C8h]
0x180029661  jnz     short loc_180029669
0x180029663  cmp     r10d, [rax+68h]
0x180029667  jz      short loc_180029678
0x180029669  lea     rcx, [rbp+arg_10]
0x18002966d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(void)
0x180029672  mov     rbx, [rbp+arg_10]
0x180029676  jmp     short loc_180029648
0x180029678  cmp     rbx, r9
0x18002967b  mov     rsi, [rbp+arg_8]
0x18002967f  jz      short loc_1800296C7
0x180029681  lea     r9, [rbx+28h]
0x180029685  mov     r15, [rbp+var_38]
0x180029689  mov     r8, r15
0x18002968c  lea     rdx, [rbp+var_38]
0x180029690  mov     rcx, r12
0x180029693  call    ??$emplace@AEBKAEAV?$shared_ptr@UPresentEvent@@@std@@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@_N@1@AEBKAEAV?$shared_ptr@UPresentEvent@@@1@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::emplace<ulong const &,std::shared_ptr<PresentEvent> &>(ulong const &,std::shared_ptr<PresentEvent> &)
0x180029698  mov     rdi, [rax]
0x18002969b  mov     r8, rbx
0x18002969e  lea     rdx, [rbp+arg_10]
0x1800296a2  lea     rcx, [r13+28h]
0x1800296a6  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<uint const,std::shared_ptr<PresentEvent>>>>>)
0x1800296ab  lea     rdx, [rdi+28h]
0x1800296af  lea     rcx, [rbp+var_28]
0x1800296b3  call    ??4?$shared_ptr@UPresentEvent@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<PresentEvent>::operator=(std::shared_ptr<PresentEvent> const &)
0x1800296b8  mov     eax, [r15]
0x1800296bb  mov     rcx, qword ptr [rbp+var_28]
0x1800296bf  mov     [rcx+94h], eax
0x1800296c5  jmp     short loc_18002970C
0x1800296c7  mov     dword ptr [rbp+arg_10], 2
0x1800296ce  lea     r8, [rbp+arg_10]
0x1800296d2  mov     rdx, rdi
0x1800296d5  lea     rcx, [rbp+var_38]
0x1800296d9  call    ??$make_shared@UPresentEvent@@AEBU_EVENT_HEADER@@W4Runtime@@@std@@YA?AV?$shared_ptr@UPresentEvent@@@0@AEBU_EVENT_HEADER@@$$QEAW4Runtime@@@Z; std::make_shared<PresentEvent,_EVENT_HEADER const &,Runtime>(_EVENT_HEADER const &,Runtime &&)
0x1800296de  mov     rdx, rax
0x1800296e1  lea     rcx, [rbp+var_28]
0x1800296e5  call    ??4?$shared_ptr@UPresentEvent@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PresentEvent>::operator=(std::shared_ptr<PresentEvent> &&)
0x1800296ea  mov     rcx, [rbp+var_30]; this
0x1800296ee  test    rcx, rcx
0x1800296f1  jz      short loc_1800296F8
0x1800296f3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800296f8  lea     r8, [r13+28h]
0x1800296fc  lea     rdx, [rbp+var_28]
0x180029700  mov     rcx, r15
0x180029703  call    ?TrackPresent@PMTraceConsumer@@QEAAXAEAV?$shared_ptr@UPresentEvent@@@std@@PEAV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@3@@Z; PMTraceConsumer::TrackPresent(std::shared_ptr<PresentEvent> &,std::map<unsigned __int64,std::shared_ptr<PresentEvent>> *)
0x180029708  mov     rcx, qword ptr [rbp+var_28]
0x18002970c  mov     r8, r14
0x18002970f  mov     edx, 8
0x180029714  mov     r9, r14
0x180029717  lea     eax, [rdx+8]
0x18002971a  mov     rax, [r14+rax]
0x18002971e  mov     [rcx+0C0h], rax
0x180029725  mov     rax, [rdx+r14]
0x180029729  mov     [rcx+0C8h], rax
0x180029730  mov     eax, [r14]
0x180029733  mov     [rcx+68h], eax
0x180029736  mov     [rsi], rcx
0x180029739  mov     rax, qword ptr [rbp+var_28+8]
0x18002973d  mov     [rsi+8], rax
0x180029741  mov     rax, rsi
0x180029744  mov     rbx, [rsp+60h+arg_18]
0x18002974c  add     rsp, 60h
0x180029750  pop     r15
0x180029752  pop     r14
0x180029754  pop     r13
0x180029756  pop     r12
0x180029758  pop     rdi
0x180029759  pop     rsi
0x18002975a  pop     rbp
0x18002975b  retn
```
