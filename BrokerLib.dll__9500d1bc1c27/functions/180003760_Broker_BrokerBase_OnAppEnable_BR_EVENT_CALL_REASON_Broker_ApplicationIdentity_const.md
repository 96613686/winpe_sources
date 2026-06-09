# Broker::BrokerBase::OnAppEnable(_BR_EVENT_CALL_REASON,Broker::ApplicationIdentity const &)

- ea: `0x180003760`
- end: `0x180003916`
- name: `?OnAppEnable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBUApplicationIdentity@2@@Z`
- size: `438`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007a0c`
- `0x180008554`
- `0x18000c970`
- `0x18001849c`

## callees

- `0x180002868`
- `0x180003650`
- `0x180003760`
- `0x180003cd0`
- `0x180004ae0`
- `0x180005070`
- `0x1800050d0`
- `0x180005b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Broker::BrokerBase::OnAppEnable(__int64 a1, unsigned int a2, _QWORD *a3)
{
  unsigned int v4; // esi
  __int64 v5; // rdi
  _QWORD *v6; // rcx
  std::_Ref_count_base **v7; // r9
  std::_Ref_count_base **i; // rbx
  std::_Ref_count_base *v9; // rax
  __int64 v11; // r9
  const wchar_t *v12; // rax
  char *pSid; // r8
  __int64 v14; // r9
  __int64 v15; // r9
  std::_Ref_count_base *v16; // r14
  const wchar_t *v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-88h]
  __int64 v19; // [rsp+38h] [rbp-80h]
  __int64 v20; // [rsp+40h] [rbp-78h]
  std::_Ref_count_base **v21; // [rsp+50h] [rbp-68h] BYREF
  Broker::Win32Error *v22; // [rsp+58h] [rbp-60h] BYREF
  std::_Ref_count_base *v23; // [rsp+60h] [rbp-58h] BYREF
  std::_Ref_count_base *v24; // [rsp+68h] [rbp-50h]
  __int128 v25; // [rsp+70h] [rbp-48h] BYREF
  __int64 v26; // [rsp+80h] [rbp-38h]

  v4 = a2;
  v5 = a1;
  v6 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v12 = (const wchar_t *)(a3 + 7);
    if ( a3[10] > 7u )
      v12 = *(const wchar_t **)v12;
    pSid = (char *)*a3;
    v14 = *(_QWORD *)(v5 + 8);
    if ( !v14 )
      v14 = 0;
    WPP_SF__guid__sid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x27u, (__int64)pSid, v14, pSid, v12);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 5u )
  {
    v15 = *(_QWORD *)(v5 + 8);
    if ( !v15 )
      v15 = 0;
    WPP_SF__guid_(v6[2], 41, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, v15);
  }
  v25 = 0;
  v26 = 0;
  v23 = (std::_Ref_count_base *)a3;
  v24 = (std::_Ref_count_base *)&v25;
  v7 = **(std::_Ref_count_base ****)(v5 + 208);
  v21 = v7;
  while ( v7 != *(std::_Ref_count_base ***)(v5 + 208) )
  {
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(&v21);
    lambda_fbd43cb40cbfca8789c624713de35da6_::operator()((__int64 *)&v23, v11 + 40);
    v7 = v21;
  }
  for ( i = (std::_Ref_count_base **)v25; ; i += 2 )
  {
    v21 = i;
    if ( i == *((std::_Ref_count_base ***)&v25 + 1) )
      break;
    v9 = i[1];
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
    try
    {
      v23 = *i;
      v16 = i[1];
      v24 = v16;
      Broker::BrokerBase::OnEventEnable(v5, v4, &v23);
    }
    catch ( Broker::Win32Error *v22 )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = (const wchar_t *)(a3 + 7);
        if ( a3[10] > 7u )
          v17 = *(const wchar_t **)v17;
        LODWORD(v20) = *((_DWORD *)v22 + 8);
        LODWORD(v19) = HIDWORD(*(_QWORD *)(*((_QWORD *)v23 + 2) + 16LL));
        LODWORD(v18) = *(_QWORD *)(*((_QWORD *)v23 + 2) + 16LL);
        WPP_SF__sid_S_guid_DDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_QWORD *)(*((_QWORD *)v23 + 2) + 16LL),
          (__int64)WPP_GLOBAL_Control,
          (char *)*a3,
          v17,
          *((_QWORD *)v23 + 2),
          v18,
          v19,
          v20);
      }
      v5 = a1;
      v4 = a2;
      i = v21;
      v16 = v24;
    }
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
  }
  return std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(&v25);
}

```

## disassembly

```asm
0x180003760  mov     rax, rsp
0x180003763  mov     [rax+18h], r8
0x180003767  mov     [rax+10h], edx
0x18000376a  mov     [rax+8], rcx
0x18000376e  push    rbx
0x18000376f  push    rsi
0x180003770  push    rdi
0x180003771  push    r14
0x180003773  sub     rsp, 98h
0x18000377a  mov     rbx, r8
0x18000377d  mov     esi, edx
0x18000377f  mov     rdi, rcx
0x180003782  xor     r14d, r14d
0x180003785  mov     [rax+20h], r14d
0x180003789  mov     rcx, cs:WPP_GLOBAL_Control
0x180003790  test    dword ptr [rcx+1Ch], 800h
0x180003797  jnz     loc_180003878
0x18000379d  test    dword ptr [rcx+1Ch], 800h
0x1800037a4  jnz     loc_1800038C0
0x1800037aa  xorps   xmm0, xmm0
0x1800037ad  movdqu  [rsp+0B8h+var_48], xmm0
0x1800037b3  mov     [rsp+0B8h+var_38], r14
0x1800037bb  mov     [rsp+0B8h+arg_18], 1
0x1800037c6  mov     [rsp+0B8h+var_58], rbx
0x1800037cb  lea     rax, [rsp+0B8h+var_48]
0x1800037d0  mov     [rsp+0B8h+var_50], rax
0x1800037d5  mov     r9, [rdi+0D0h]
0x1800037dc  mov     r9, [r9]
0x1800037df  mov     [rsp+0B8h+var_68], r9
0x1800037e4  cmp     r9, [rdi+0D0h]
0x1800037eb  jnz     short loc_180003856
0x1800037ed  mov     rbx, qword ptr [rsp+0B8h+var_48]
0x1800037f2  mov     [rsp+0B8h+var_68], rbx
0x1800037f7  cmp     rbx, qword ptr [rsp+0B8h+var_48+8]
0x1800037fc  jz      short loc_18000383F
0x1800037fe  mov     rax, [rbx+8]
0x180003802  test    rax, rax
0x180003805  jz      short loc_18000380B
0x180003807  lock inc dword ptr [rax+8]
0x18000380b  mov     rax, [rbx]
0x18000380e  mov     [rsp+0B8h+var_58], rax
0x180003813  mov     r14, [rbx+8]
0x180003817  mov     [rsp+0B8h+var_50], r14
0x18000381c  lea     r8, [rsp+0B8h+var_58]
0x180003821  mov     edx, esi
0x180003823  mov     rcx, rdi
0x180003826  call    ?OnEventEnable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::OnEventEnable(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> const &)
0x18000382b  nop
0x18000382c  test    r14, r14
0x18000382f  jz      short loc_180003839
0x180003831  mov     rcx, r14; this
0x180003834  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003839  add     rbx, 10h
0x18000383d  jmp     short loc_1800037F2
0x18000383f  lea     rcx, [rsp+0B8h+var_48]
0x180003844  call    ?_Tidy@?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(void)
0x180003849  add     rsp, 98h
0x180003850  pop     r14
0x180003852  pop     rdi
0x180003853  pop     rsi
0x180003854  pop     rbx
0x180003855  retn
0x180003856  lea     rcx, [rsp+0B8h+var_68]
0x18000385b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(void)
0x180003860  lea     rdx, [r9+28h]
0x180003864  lea     rcx, [rsp+0B8h+var_58]
0x180003869  call    _lambda_fbd43cb40cbfca8789c624713de35da6___operator__
0x18000386e  mov     r9, [rsp+0B8h+var_68]
0x180003873  jmp     loc_1800037E4
0x180003878  cmp     byte ptr [rcx+19h], 5
0x18000387c  jb      loc_18000379D
0x180003882  lea     rax, [r8+38h]
0x180003886  cmp     qword ptr [rax+18h], 7
0x18000388b  jbe     short loc_180003890
0x18000388d  mov     rax, [rax]
0x180003890  mov     r8, [r8]
0x180003893  mov     r9, [rdi+8]
0x180003897  test    r9, r9
0x18000389a  jz      short loc_1800038ED
0x18000389c  mov     edx, 27h ; '''
0x1800038a1  mov     [rsp+0B8h+var_90], rax; __int64
0x1800038a6  mov     [rsp+0B8h+pSid], r8; pSid
0x1800038ab  mov     rcx, [rcx+10h]; LoggerHandle
0x1800038af  call    WPP_SF__guid__sid_S
0x1800038b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038bb  jmp     loc_18000379D
0x1800038c0  cmp     byte ptr [rcx+19h], 5
0x1800038c4  jb      loc_1800037AA
0x1800038ca  mov     r9, [rdi+8]
0x1800038ce  test    r9, r9
0x1800038d1  jz      short loc_1800038F2
0x1800038d3  mov     edx, 29h ; ')'
0x1800038d8  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x1800038df  mov     rcx, [rcx+10h]
0x1800038e3  call    WPP_SF__guid_
0x1800038e8  jmp     loc_1800037AA
0x1800038ed  mov     r9, r14
0x1800038f0  jmp     short loc_18000389C
0x1800038f2  mov     r9, r14
0x1800038f5  jmp     short loc_1800038D3
0x1800038f7  mov     rdi, [rsp+0B8h+arg_0]
0x1800038ff  mov     esi, [rsp+0B8h+arg_8]
0x180003906  mov     rbx, [rsp+0B8h+var_68]
0x18000390b  mov     r14, [rsp+0B8h+var_50]
0x180003910  jmp     loc_18000382C
```
