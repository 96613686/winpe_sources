# PMTraceConsumer::CompletePresent(std::shared_ptr<PresentEvent>)

- ea: `0x180029130`
- end: `0x18002924e`
- name: `?CompletePresent@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@@Z`
- size: `286`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `10`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002a8c8`
- `0x18002bd00`
- `0x18002bf8c`
- `0x18002c060`
- `0x18002c13c`
- `0x18002c448`
- `0x18002c5d4`
- `0x18002c6a4`
- `0x18002c7b0`
- `0x18002d470`

## callees

- `0x18000d67c`
- `0x18000e3e4`
- `0x180011430`
- `0x180015984`
- `0x180017f3c`
- `0x180018810`
- `0x180027b78`
- `0x180027eb8`
- `0x1800288d0`
- `0x180029130`
- `0x180029254`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18002921e`
- `msvcp_win!_Mtx_unlock` at `0x18002921e`

## pseudocode

```c
void __fastcall PMTraceConsumer::CompletePresent(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // r14
  struct _Mtx_internal_imp_t *v6; // rbx
  _QWORD *v7; // rdi
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  _QWORD *v10; // rcx
  std::_Ref_count_base *v11; // rcx
  __int64 *v12; // [rsp+20h] [rbp-20h] BYREF
  __int64 v13; // [rsp+28h] [rbp-18h]
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v15; // [rsp+80h] [rbp+40h] BYREF
  __int64 v16; // [rsp+88h] [rbp+48h]

  std::map<unsigned int,std::shared_ptr<PresentEvent>>::map<unsigned int,std::shared_ptr<PresentEvent>>(&v12);
  v4 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v14, a2);
  PMTraceConsumer::CompletePresentHelper(a1, v4, &v12);
  v5 = v13;
  if ( v13 )
  {
    v6 = (struct _Mtx_internal_imp_t *)(a1 + 72);
    v16 = a1 + 72;
    std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 72));
    v7 = (_QWORD *)(a1 + 152);
    v8 = v5 + ((__int64)(v7[1] - *v7) >> 4);
    v15 = v8;
    if ( v8 > (__int64)(v7[2] - *v7) >> 4 )
    {
      if ( v8 > 0xFFFFFFFFFFFFFFFLL )
        std::vector<std::pair<enum PresentTraceConsumerCore::TimeoutReason,std::shared_ptr<IPresentEventConsumer>>>::_Xlength();
      std::vector<std::shared_ptr<PresentEvent>>::_Reallocate<0>(v7, &v15);
    }
    v9 = *v12;
    v15 = *v12;
    while ( !*(_BYTE *)(v9 + 25) )
    {
      v10 = (_QWORD *)v7[1];
      if ( v10 == (_QWORD *)v7[2] )
      {
        std::vector<std::shared_ptr<PresentEvent>>::_Emplace_reallocate<std::shared_ptr<PresentEvent> const &>(
          v7,
          v7[1],
          v9 + 40);
      }
      else
      {
        std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(v10, (_QWORD *)(v9 + 40));
        v7[1] += 16LL;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++((__int64 *)&v15);
      v9 = v15;
    }
    _Mtx_unlock(v6);
  }
  std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>(&v12);
  v11 = (std::_Ref_count_base *)a2[1];
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
}

```

## disassembly

```asm
0x180029130  mov     [rsp-28h+arg_8], rdx
0x180029135  push    rbp
0x180029136  push    rbx
0x180029137  push    rsi
0x180029138  push    rdi
0x180029139  push    r14
0x18002913b  mov     rbp, rsp
0x18002913e  sub     rsp, 40h
0x180029142  mov     rsi, rdx
0x180029145  mov     rdi, rcx
0x180029148  lea     rcx, [rbp+var_20]
0x18002914c  call    ??0?$map@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@std@@QEAA@XZ; std::map<uint,std::shared_ptr<PresentEvent>>::map<uint,std::shared_ptr<PresentEvent>>(void)
0x180029151  nop
0x180029152  mov     rdx, rsi
0x180029155  lea     rcx, [rbp+var_10]
0x180029159  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002915e  lea     r8, [rbp+var_20]
0x180029162  mov     rdx, rax
0x180029165  mov     rcx, rdi
0x180029168  call    ?CompletePresentHelper@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@PEAV?$map@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@@3@@Z; PMTraceConsumer::CompletePresentHelper(std::shared_ptr<PresentEvent>,std::map<unsigned __int64,std::shared_ptr<PresentEvent>> *)
0x18002916d  mov     r14, [rbp+var_18]
0x180029171  test    r14, r14
0x180029174  jz      loc_180029225
0x18002917a  lea     rbx, [rdi+48h]
0x18002917e  mov     [rbp+arg_18], rbx
0x180029182  mov     rcx, rbx; this
0x180029185  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002918a  nop
0x18002918b  add     rdi, 98h
0x180029192  mov     rcx, [rdi+8]
0x180029196  sub     rcx, [rdi]
0x180029199  sar     rcx, 4
0x18002919d  add     rcx, r14
0x1800291a0  mov     [rbp+arg_10], rcx
0x1800291a4  mov     rax, [rdi+10h]
0x1800291a8  sub     rax, [rdi]
0x1800291ab  sar     rax, 4
0x1800291af  cmp     rcx, rax
0x1800291b2  jbe     short loc_1800291D3
0x1800291b4  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800291be  cmp     rcx, rax
0x1800291c1  ja      loc_180029248
0x1800291c7  lea     rdx, [rbp+arg_10]
0x1800291cb  mov     rcx, rdi
0x1800291ce  call    ??$_Reallocate@$0A@@?$vector@V?$shared_ptr@UPresentEvent@@@std@@V?$allocator@V?$shared_ptr@UPresentEvent@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::shared_ptr<PresentEvent>>::_Reallocate<0>(unsigned __int64 &)
0x1800291d3  mov     rax, [rbp+var_20]
0x1800291d7  mov     rax, [rax]
0x1800291da  mov     [rbp+arg_10], rax
0x1800291de  cmp     byte ptr [rax+19h], 0
0x1800291e2  jnz     short loc_18002921B
0x1800291e4  lea     rdx, [rax+28h]
0x1800291e8  mov     rcx, [rdi+8]
0x1800291ec  cmp     rcx, [rdi+10h]
0x1800291f0  jz      short loc_1800291FE
0x1800291f2  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x1800291f7  add     qword ptr [rdi+8], 10h
0x1800291fc  jmp     short loc_18002920C
0x1800291fe  mov     r8, rdx
0x180029201  mov     rdx, rcx
0x180029204  mov     rcx, rdi
0x180029207  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UPresentEvent@@@std@@@?$vector@V?$shared_ptr@UPresentEvent@@@std@@V?$allocator@V?$shared_ptr@UPresentEvent@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UPresentEvent@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PresentEvent>>::_Emplace_reallocate<std::shared_ptr<PresentEvent> const &>(std::shared_ptr<PresentEvent> * const,std::shared_ptr<PresentEvent> const &)
0x18002920c  lea     rcx, [rbp+arg_10]
0x180029210  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>>,std::_Iterator_base0>::operator++(void)
0x180029215  mov     rax, [rbp+arg_10]
0x180029219  jmp     short loc_1800291DE
0x18002921b  mov     rcx, rbx; _Mtx_t
0x18002921e  call    cs:__imp__Mtx_unlock
0x180029224  nop
0x180029225  lea     rcx, [rbp+var_20]
0x180029229  call    ??1?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::~_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>(void)
0x18002922e  nop
0x18002922f  mov     rcx, [rsi+8]; this
0x180029233  test    rcx, rcx
0x180029236  jz      short loc_18002923D
0x180029238  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002923d  add     rsp, 40h
0x180029241  pop     r14
0x180029243  pop     rdi
0x180029244  pop     rsi
0x180029245  pop     rbx
0x180029246  pop     rbp
0x180029247  retn
0x180029248  call    ?_Xlength@?$vector@U?$pair@W4TimeoutReason@PresentTraceConsumerCore@@V?$shared_ptr@UIPresentEventConsumer@@@std@@@std@@V?$allocator@U?$pair@W4TimeoutReason@PresentTraceConsumerCore@@V?$shared_ptr@UIPresentEventConsumer@@@std@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<PresentTraceConsumerCore::TimeoutReason,std::shared_ptr<IPresentEventConsumer>>>::_Xlength(void)
```
