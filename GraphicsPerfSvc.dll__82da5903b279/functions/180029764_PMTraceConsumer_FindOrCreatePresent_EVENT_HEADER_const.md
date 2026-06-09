# PMTraceConsumer::FindOrCreatePresent(_EVENT_HEADER const &)

- ea: `0x180029764`
- end: `0x1800298c9`
- name: `?FindOrCreatePresent@PMTraceConsumer@@QEAA?AV?$shared_ptr@UPresentEvent@@@std@@AEBU_EVENT_HEADER@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(PMTraceConsumer *this)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18002bc2c`
- `0x18002bd70`
- `0x18002c13c`
- `0x18002c7b0`

## callees

- `0x18000d67c`
- `0x18000e3e4`
- `0x18001139c`
- `0x180018810`
- `0x180027f38`
- `0x180028558`
- `0x180028714`
- `0x180029764`
- `0x18002cd20`
- `0x18002d550`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall PMTraceConsumer::FindOrCreatePresent(PMTraceConsumer *this, _QWORD *a2, __int64 a3)
{
  _QWORD *v6; // r15
  _DWORD *v7; // r14
  __int64 v8; // rax
  __int64 v9; // r12
  __int64 v10; // rdx
  __int64 v12; // [rsp+28h] [rbp-28h] BYREF
  std::_Ref_count_base *v13; // [rsp+30h] [rbp-20h]
  _BYTE v14[24]; // [rsp+38h] [rbp-18h] BYREF
  int v15; // [rsp+80h] [rbp+30h] BYREF
  __int64 v16; // [rsp+90h] [rbp+40h] BYREF

  v6 = (_QWORD *)((char *)this + 416);
  v7 = (_DWORD *)(a3 + 8);
  v15 = *(_DWORD *)(a3 + 8);
  std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(
    (char *)this + 416,
    &v16,
    &v15);
  if ( v16 == *v6 )
  {
    if ( PMTraceConsumer::IsProcessTrackedForFiltering(this, *(_DWORD *)(a3 + 12)) )
    {
      v15 = *(_DWORD *)(a3 + 12);
      v8 = std::map<unsigned int,std::map<unsigned __int64,std::shared_ptr<PresentEvent>>>::_Try_emplace<unsigned int,>(
             (char *)this + 432,
             v14,
             &v15);
      v9 = *(_QWORD *)v8;
      v10 = **(_QWORD **)(*(_QWORD *)v8 + 40LL);
      v16 = v10;
      while ( !*(_BYTE *)(v10 + 25) )
      {
        std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v12, (_QWORD *)(v10 + 40));
        if ( !*(_DWORD *)(v12 + 156) )
        {
          *(_DWORD *)(v12 + 148) = *v7;
          std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::emplace<unsigned long const &,std::shared_ptr<PresentEvent> &>(
            v6,
            v14,
            v7,
            &v12);
          *a2 = v12;
          a2[1] = v13;
          return a2;
        }
        if ( v13 )
          std::_Ref_count_base::_Decref(v13);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(&v16);
        v10 = v16;
      }
      LODWORD(v16) = 2;
      std::make_shared<PresentEvent,_EVENT_HEADER const &,enum Runtime>(&v12, a3, &v16);
      PMTraceConsumer::TrackPresent(this, &v12, v9 + 40);
      *a2 = v12;
      a2[1] = v13;
    }
    else
    {
      *a2 = 0;
      a2[1] = 0;
    }
  }
  else
  {
    std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(a2, (_QWORD *)(v16 + 40));
  }
  return a2;
}

```

## disassembly

```asm
0x180029764  mov     [rsp-28h+arg_8], rbx
0x180029769  mov     [rsp-28h+arg_18], rsi
0x18002976e  push    rbp
0x18002976f  push    rdi
0x180029770  push    r12
0x180029772  push    r14
0x180029774  push    r15
0x180029776  mov     rbp, rsp
0x180029779  sub     rsp, 50h
0x18002977d  mov     rdi, r8
0x180029780  mov     rbx, rdx
0x180029783  mov     rsi, rcx
0x180029786  lea     r15, [rcx+1A0h]
0x18002978d  lea     r14, [r8+8]
0x180029791  mov     eax, [r14]
0x180029794  mov     [rbp+arg_0], eax
0x180029797  lea     r8, [rbp+arg_0]
0x18002979b  lea     rdx, [rbp+arg_10]
0x18002979f  mov     rcx, r15
0x1800297a2  call    ?find@?$_Tree@V?$_Tmap_traits@KUProcessInfo@PresentTraceConsumerCore@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,PresentTraceConsumerCore::ProcessInfo,std::less<ulong>,std::allocator<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(ulong const &)
0x1800297a7  mov     rdx, [rbp+arg_10]
0x1800297ab  cmp     rdx, [r15]
0x1800297ae  jnz     loc_1800298A1
0x1800297b4  mov     edx, [rdi+0Ch]; unsigned int
0x1800297b7  mov     rcx, rsi; this
0x1800297ba  call    ?IsProcessTrackedForFiltering@PMTraceConsumer@@QEAA_NI@Z; PMTraceConsumer::IsProcessTrackedForFiltering(uint)
0x1800297bf  test    al, al
0x1800297c1  jnz     short loc_1800297D7
0x1800297c3  mov     qword ptr [rbx], 0
0x1800297ca  mov     qword ptr [rbx+8], 0
0x1800297d2  jmp     loc_1800298AD
0x1800297d7  mov     eax, [rdi+0Ch]
0x1800297da  mov     [rbp+arg_0], eax
0x1800297dd  lea     rcx, [rsi+1B0h]
0x1800297e4  lea     r8, [rbp+arg_0]
0x1800297e8  lea     rdx, [rbp+var_18]
0x1800297ec  call    ??$_Try_emplace@I$$V@?$map@IV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@@std@@PEAX@std@@_N@1@$$QEAI@Z; std::map<uint,std::map<unsigned __int64,std::shared_ptr<PresentEvent>>>::_Try_emplace<uint,>(uint &&)
0x1800297f1  mov     r12, [rax]
0x1800297f4  mov     rdx, [r12+28h]
0x1800297f9  mov     rdx, [rdx]
0x1800297fc  mov     [rbp+arg_10], rdx
0x180029800  lea     rcx, [rbp+var_28]
0x180029804  cmp     byte ptr [rdx+19h], 0
0x180029808  jnz     short loc_18002986B
0x18002980a  add     rdx, 28h ; '('
0x18002980e  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x180029813  nop
0x180029814  mov     rcx, [rbp+var_28]
0x180029818  cmp     dword ptr [rcx+9Ch], 0
0x18002981f  jz      short loc_18002983E
0x180029821  mov     rcx, [rbp+var_20]; this
0x180029825  test    rcx, rcx
0x180029828  jz      short loc_18002982F
0x18002982a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002982f  lea     rcx, [rbp+arg_10]
0x180029833  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(void)
0x180029838  mov     rdx, [rbp+arg_10]
0x18002983c  jmp     short loc_180029800
0x18002983e  mov     eax, [r14]
0x180029841  mov     [rcx+94h], eax
0x180029847  lea     r9, [rbp+var_28]
0x18002984b  mov     r8, r14
0x18002984e  lea     rdx, [rbp+var_18]
0x180029852  mov     rcx, r15
0x180029855  call    ??$emplace@AEBKAEAV?$shared_ptr@UPresentEvent@@@std@@@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@_N@1@AEBKAEAV?$shared_ptr@UPresentEvent@@@1@@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::emplace<ulong const &,std::shared_ptr<PresentEvent> &>(ulong const &,std::shared_ptr<PresentEvent> &)
0x18002985a  mov     rax, [rbp+var_28]
0x18002985e  mov     [rbx], rax
0x180029861  mov     rax, [rbp+var_20]
0x180029865  mov     [rbx+8], rax
0x180029869  jmp     short loc_1800298AD
0x18002986b  mov     dword ptr [rbp+arg_10], 2
0x180029872  lea     r8, [rbp+arg_10]
0x180029876  mov     rdx, rdi
0x180029879  call    ??$make_shared@UPresentEvent@@AEBU_EVENT_HEADER@@W4Runtime@@@std@@YA?AV?$shared_ptr@UPresentEvent@@@0@AEBU_EVENT_HEADER@@$$QEAW4Runtime@@@Z; std::make_shared<PresentEvent,_EVENT_HEADER const &,Runtime>(_EVENT_HEADER const &,Runtime &&)
0x18002987e  nop
0x18002987f  lea     r8, [r12+28h]
0x180029884  lea     rdx, [rbp+var_28]
0x180029888  mov     rcx, rsi
0x18002988b  call    ?TrackPresent@PMTraceConsumer@@QEAAXAEAV?$shared_ptr@UPresentEvent@@@std@@PEAV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@3@@Z; PMTraceConsumer::TrackPresent(std::shared_ptr<PresentEvent> &,std::map<unsigned __int64,std::shared_ptr<PresentEvent>> *)
0x180029890  mov     rax, [rbp+var_28]
0x180029894  mov     [rbx], rax
0x180029897  mov     rax, [rbp+var_20]
0x18002989b  mov     [rbx+8], rax
0x18002989f  jmp     short loc_1800298AD
0x1800298a1  add     rdx, 28h ; '('
0x1800298a5  mov     rcx, rbx
0x1800298a8  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x1800298ad  mov     rax, rbx
0x1800298b0  lea     r11, [rsp+50h+var_s0]
0x1800298b5  mov     rbx, [r11+38h]
0x1800298b9  mov     rsi, [r11+48h]
0x1800298bd  mov     rsp, r11
0x1800298c0  pop     r15
0x1800298c2  pop     r14
0x1800298c4  pop     r12
0x1800298c6  pop     rdi
0x1800298c7  pop     rbp
0x1800298c8  retn
```
