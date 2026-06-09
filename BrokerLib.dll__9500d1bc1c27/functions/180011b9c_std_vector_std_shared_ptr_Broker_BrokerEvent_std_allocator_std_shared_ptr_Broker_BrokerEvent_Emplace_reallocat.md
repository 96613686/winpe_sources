# std::vector<std::shared_ptr<Broker::BrokerEvent>,std::allocator<std::shared_ptr<Broker::BrokerEvent>>>::_Emplace_reallocate<std::shared_ptr<Broker::BrokerEvent> const &>(std::shared_ptr<Broker::BrokerEvent> * const,std::shared_ptr<Broker::BrokerEvent> const &)

- ea: `0x180011b9c`
- end: `0x180011c78`
- name: `??$_Emplace_reallocate@AEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VBrokerEvent@Broker@@@1@QEAV21@AEBV21@@Z`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800050d0`

## callees

- `0x180004500`
- `0x180004530`
- `0x180004be0`
- `0x180004c3c`
- `0x180004e78`
- `0x180011b9c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011bd3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011bd3`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Emplace_reallocate<std::shared_ptr<Broker::BrokerEvent> const &>(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rax
  unsigned __int64 v8; // rbp
  __int64 v9; // rsi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 size_of; // rax
  _QWORD *v13; // rsi
  _QWORD *v14; // r10
  __int64 v15; // rdx
  _QWORD *v16; // r8
  __int64 v17; // rcx
  __int64 v18; // r10

  v3 = 0xFFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 4;
  if ( v5 == 0xFFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v5 + 1;
  v9 = a2 - *a1;
  v10 = (a1[2] - *a1) >> 4;
  v11 = v10 >> 1;
  if ( v10 <= 0xFFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v11 + v10;
    if ( v11 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<16>(v3);
  v13 = (_QWORD *)(std::_Allocate<16,std::_Default_allocate_traits>(size_of) + (v9 & 0xFFFFFFFFFFFFFFF0uLL));
  std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(v13, a3);
  v15 = a1[1];
  v16 = v14;
  v17 = *a1;
  if ( a2 != v15 )
  {
    std::_Uninitialized_move<std::shared_ptr<Broker::BrokerEvent> *,std::allocator<std::shared_ptr<Broker::BrokerEvent>>>(
      v17,
      a2,
      v14);
    v15 = a1[1];
    v16 = v13 + 2;
    v17 = a2;
  }
  std::_Uninitialized_move<std::shared_ptr<Broker::BrokerEvent> *,std::allocator<std::shared_ptr<Broker::BrokerEvent>>>(
    v17,
    v15,
    v16);
  std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Change_array(a1, v18, v8, v3);
  return v13;
}

```

## disassembly

```asm
0x180011b9c  push    rbx
0x180011b9e  push    rbp
0x180011b9f  push    rsi
0x180011ba0  push    rdi
0x180011ba1  push    r14
0x180011ba3  push    r15
0x180011ba5  sub     rsp, 28h
0x180011ba9  mov     rax, [rcx+8]
0x180011bad  mov     rbx, 0FFFFFFFFFFFFFFFh
0x180011bb7  sub     rax, [rcx]
0x180011bba  mov     r15, r8
0x180011bbd  sar     rax, 4
0x180011bc1  mov     r14, rdx
0x180011bc4  mov     rdi, rcx
0x180011bc7  cmp     rax, rbx
0x180011bca  jnz     short loc_180011BDA
0x180011bcc  lea     rcx, aVectorTooLong; "vector too long"
0x180011bd3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180011bda  lea     rbp, [rax+1]
0x180011bde  mov     rsi, r14
0x180011be1  sub     rsi, [rcx]
0x180011be4  mov     rax, rbx
0x180011be7  mov     rcx, [rcx+10h]
0x180011beb  sub     rcx, [rdi]
0x180011bee  sar     rcx, 4
0x180011bf2  mov     rdx, rcx
0x180011bf5  shr     rdx, 1
0x180011bf8  sub     rax, rdx
0x180011bfb  cmp     rcx, rax
0x180011bfe  ja      short loc_180011C0B
0x180011c00  lea     rbx, [rdx+rcx]
0x180011c04  cmp     rbx, rbp
0x180011c07  cmovb   rbx, rbp
0x180011c0b  mov     rcx, rbx
0x180011c0e  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x180011c13  mov     rcx, rax
0x180011c16  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180011c1b  and     rsi, 0FFFFFFFFFFFFFFF0h
0x180011c1f  mov     rdx, r15
0x180011c22  add     rsi, rax
0x180011c25  mov     r10, rax
0x180011c28  mov     rcx, rsi
0x180011c2b  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x180011c30  mov     rdx, [rdi+8]
0x180011c34  mov     r8, r10
0x180011c37  mov     rcx, [rdi]
0x180011c3a  cmp     r14, rdx
0x180011c3d  jz      short loc_180011C52
0x180011c3f  mov     rdx, r14
0x180011c42  call    ??$_Uninitialized_move@PEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@YAPEAV?$shared_ptr@VBrokerEvent@Broker@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<Broker::BrokerEvent> *,std::allocator<std::shared_ptr<Broker::BrokerEvent>>>(std::shared_ptr<Broker::BrokerEvent> * const,std::shared_ptr<Broker::BrokerEvent> * const,std::shared_ptr<Broker::BrokerEvent> *,std::allocator<std::shared_ptr<Broker::BrokerEvent>> &)
0x180011c47  mov     rdx, [rdi+8]
0x180011c4b  lea     r8, [rsi+10h]
0x180011c4f  mov     rcx, r14
0x180011c52  call    ??$_Uninitialized_move@PEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@YAPEAV?$shared_ptr@VBrokerEvent@Broker@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@0@@Z; std::_Uninitialized_move<std::shared_ptr<Broker::BrokerEvent> *,std::allocator<std::shared_ptr<Broker::BrokerEvent>>>(std::shared_ptr<Broker::BrokerEvent> * const,std::shared_ptr<Broker::BrokerEvent> * const,std::shared_ptr<Broker::BrokerEvent> *,std::allocator<std::shared_ptr<Broker::BrokerEvent>> &)
0x180011c57  mov     r9, rbx
0x180011c5a  mov     r8, rbp
0x180011c5d  mov     rcx, rdi
0x180011c60  mov     rdx, r10
0x180011c63  call    ?_Change_array@?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEAAXQEAV?$shared_ptr@VBrokerEvent@Broker@@@2@_K1@Z; std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Change_array(std::shared_ptr<Broker::BrokerEvent> * const,unsigned __int64,unsigned __int64)
0x180011c68  mov     rax, rsi
0x180011c6b  add     rsp, 28h
0x180011c6f  pop     r15
0x180011c71  pop     r14
0x180011c73  pop     rdi
0x180011c74  pop     rsi
0x180011c75  pop     rbp
0x180011c76  pop     rbx
0x180011c77  retn
```
