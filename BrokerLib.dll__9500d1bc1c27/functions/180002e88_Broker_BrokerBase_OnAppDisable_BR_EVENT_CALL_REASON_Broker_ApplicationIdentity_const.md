# Broker::BrokerBase::OnAppDisable(_BR_EVENT_CALL_REASON,Broker::ApplicationIdentity const &)

- ea: `0x180002e88`
- end: `0x180002ff7`
- name: `?OnAppDisable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBUApplicationIdentity@2@@Z`
- size: `367`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800026b4`
- `0x180007a0c`
- `0x180008668`
- `0x1800185f4`

## callees

- `0x180001ff8`
- `0x180002e88`
- `0x180003650`
- `0x180003cd0`
- `0x180004ae0`
- `0x180005070`
- `0x1800050d0`
- `0x180005b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Broker::BrokerBase::OnAppDisable(__int64 a1, unsigned int a2, char **a3)
{
  _QWORD *v6; // rcx
  __int64 v7; // r9
  __int64 *i; // rbx
  __int64 v9; // rax
  std::_Ref_count_base *v10; // rsi
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // [rsp+30h] [rbp-30h] BYREF
  std::_Ref_count_base *v15; // [rsp+38h] [rbp-28h]
  __int128 v16; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h]
  __int64 v18; // [rsp+90h] [rbp+30h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v13 = (__int64)(a3 + 7);
    if ( *(_QWORD *)(v13 + 24) > 7u )
      v13 = *(_QWORD *)v13;
    WPP_SF__guid__sid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Bu, v13, *(_QWORD *)(a1 + 8), *a3, (const wchar_t *)v13);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF__guid_(v6[2], 41, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, *(_QWORD *)(a1 + 8));
  v16 = 0;
  v17 = 0;
  v14 = (__int64)a3;
  v15 = (std::_Ref_count_base *)&v16;
  v7 = **(_QWORD **)(a1 + 208);
  v18 = v7;
  while ( v7 != *(_QWORD *)(a1 + 208) )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(&v18);
    lambda_fbd43cb40cbfca8789c624713de35da6_::operator()(&v14, v12 + 40);
    v7 = v18;
  }
  for ( i = (__int64 *)v16; i != *((__int64 **)&v16 + 1); i += 2 )
  {
    v9 = i[1];
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
    v14 = *i;
    v15 = (std::_Ref_count_base *)i[1];
    v10 = v15;
    Broker::BrokerBase::OnEventDisable(a1, a2, &v14);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
  }
  return std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(&v16);
}

```

## disassembly

```asm
0x180002e88  mov     [rsp-18h+arg_8], rbx
0x180002e8d  mov     [rsp-18h+arg_18], rsi
0x180002e92  push    rbp
0x180002e93  push    rdi
0x180002e94  push    r14
0x180002e96  mov     rbp, rsp
0x180002e99  sub     rsp, 60h
0x180002e9d  mov     rbx, r8
0x180002ea0  mov     r14d, edx
0x180002ea3  mov     rdi, rcx
0x180002ea6  mov     [rbp+arg_0], 0
0x180002ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eb4  mov     esi, 800h
0x180002eb9  test    [rcx+1Ch], esi
0x180002ebc  jnz     loc_180002F8B
0x180002ec2  test    [rcx+1Ch], esi
0x180002ec5  jnz     loc_180002FCE
0x180002ecb  xorps   xmm0, xmm0
0x180002ece  movdqu  [rbp+var_20], xmm0
0x180002ed3  mov     [rbp+var_10], 0
0x180002edb  mov     [rbp+arg_0], 1
0x180002ee2  mov     [rbp+var_30], rbx
0x180002ee6  lea     rax, [rbp+var_20]
0x180002eea  mov     [rbp+var_28], rax
0x180002eee  mov     r9, [rdi+0D0h]
0x180002ef5  mov     r9, [r9]
0x180002ef8  mov     [rbp+arg_10], r9
0x180002efc  cmp     r9, [rdi+0D0h]
0x180002f03  jnz     short loc_180002F6C
0x180002f05  mov     rbx, qword ptr [rbp+var_20]
0x180002f09  cmp     rbx, qword ptr [rbp+var_20+8]
0x180002f0d  jz      short loc_180002F4E
0x180002f0f  mov     rax, [rbx+8]
0x180002f13  test    rax, rax
0x180002f16  jz      short loc_180002F1C
0x180002f18  lock inc dword ptr [rax+8]
0x180002f1c  mov     rax, [rbx]
0x180002f1f  mov     [rbp+var_30], rax
0x180002f23  mov     rsi, [rbx+8]
0x180002f27  mov     [rbp+var_28], rsi
0x180002f2b  lea     r8, [rbp+var_30]
0x180002f2f  mov     edx, r14d
0x180002f32  mov     rcx, rdi
0x180002f35  call    ?OnEventDisable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::OnEventDisable(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> const &)
0x180002f3a  nop
0x180002f3b  test    rsi, rsi
0x180002f3e  jz      short loc_180002F48
0x180002f40  mov     rcx, rsi; this
0x180002f43  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002f48  add     rbx, 10h
0x180002f4c  jmp     short loc_180002F09
0x180002f4e  lea     rcx, [rbp+var_20]
0x180002f52  call    ?_Tidy@?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(void)
0x180002f57  lea     r11, [rsp+60h+var_s0]
0x180002f5c  mov     rbx, [r11+28h]
0x180002f60  mov     rsi, [r11+38h]
0x180002f64  mov     rsp, r11
0x180002f67  pop     r14
0x180002f69  pop     rdi
0x180002f6a  pop     rbp
0x180002f6b  retn
0x180002f6c  lea     rcx, [rbp+arg_10]
0x180002f70  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(void)
0x180002f75  lea     rdx, [r9+28h]
0x180002f79  lea     rcx, [rbp+var_30]
0x180002f7d  call    _lambda_fbd43cb40cbfca8789c624713de35da6___operator__
0x180002f82  mov     r9, [rbp+arg_10]
0x180002f86  jmp     loc_180002EFC
0x180002f8b  cmp     byte ptr [rcx+19h], 5
0x180002f8f  jb      loc_180002EC2
0x180002f95  add     r8, 38h ; '8'
0x180002f99  cmp     qword ptr [r8+18h], 7
0x180002f9e  jbe     short loc_180002FA3
0x180002fa0  mov     r8, [r8]
0x180002fa3  mov     rax, [rbx]
0x180002fa6  mov     edx, 2Bh ; '+'
0x180002fab  mov     [rsp+60h+var_38], r8; __int64
0x180002fb0  mov     [rsp+60h+pSid], rax; pSid
0x180002fb5  mov     r9, [rdi+8]
0x180002fb9  mov     rcx, [rcx+10h]; LoggerHandle
0x180002fbd  call    WPP_SF__guid__sid_S
0x180002fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fc9  jmp     loc_180002EC2
0x180002fce  cmp     byte ptr [rcx+19h], 5
0x180002fd2  jb      loc_180002ECB
0x180002fd8  mov     edx, 29h ; ')'
0x180002fdd  mov     r9, [rdi+8]
0x180002fe1  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180002fe8  mov     rcx, [rcx+10h]
0x180002fec  call    WPP_SF__guid_
0x180002ff1  jmp     loc_180002ECB
```
