# Broker::BrokerBase::OnUserLogoff(unsigned __int64,ulong,void *)

- ea: `0x1800026b4`
- end: `0x180002803`
- name: `?OnUserLogoff@BrokerBase@Broker@@AEAAX_KKPEAX@Z`
- size: `335`
- prototype: `void(Broker::BrokerBase *__hidden this, unsigned __int64, unsigned int, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001f24`

## callees

- `0x180001cbc`
- `0x180001d94`
- `0x180002614`
- `0x1800026b4`
- `0x180002e88`
- `0x180003980`
- `0x180004ae0`
- `0x180006cec`
- `0x180008340`
- `0x180008dd8`
- `0x180013a60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800026f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800026f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Broker::BrokerBase::OnUserLogoff(Broker::BrokerBase *this, __int64 a2, __int64 a3, char *pSid)
{
  unsigned int v5; // edi
  DWORD LengthSid; // eax
  Broker::ApplicationStateTable::State **i; // rbx
  Broker::ApplicationStateTable::State *v10; // rax
  Broker::ApplicationStateTable::State *v11; // rsi
  std::_Ref_count_base *v12; // rdi
  __int128 v13; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+50h] [rbp-20h]
  _QWORD v15[3]; // [rsp+58h] [rbp-18h] BYREF

  v5 = a3;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x34u, a3, *((_QWORD *)this + 1), pSid);
  v13 = 0;
  v14 = 0;
  LengthSid = GetLengthSid(pSid);
  std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(&v13, 0, pSid, LengthSid);
  if ( (unsigned __int8)Broker::UserContextTable::UserLogoff((char *)this + 256, a2, &v13, v5) )
  {
    Broker::BrokerBase::SelectUserAppStates(this, v15, &v13);
    for ( i = (Broker::ApplicationStateTable::State **)v15[0]; i != (Broker::ApplicationStateTable::State **)v15[1]; i += 2 )
    {
      v10 = i[1];
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)v10 + 2);
      v11 = *i;
      v12 = i[1];
      if ( Broker::ApplicationStateTable::State::OnUserLogoff(*i) )
        Broker::BrokerBase::OnAppDisable(this, 6, v11);
      if ( v12 )
        std::_Ref_count_base::_Decref(v12);
    }
    std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Tidy(v15);
  }
  else if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x35u, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, pSid);
  }
  std::vector<unsigned char>::_Tidy(&v13);
}

```

## disassembly

```asm
0x1800026b4  push    rbp
0x1800026b6  push    rbx
0x1800026b7  push    rsi
0x1800026b8  push    rdi
0x1800026b9  push    r14
0x1800026bb  mov     rbp, rsp
0x1800026be  sub     rsp, 70h
0x1800026c2  mov     rbx, r9
0x1800026c5  mov     edi, r8d
0x1800026c8  mov     rsi, rdx
0x1800026cb  mov     r14, rcx
0x1800026ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026d5  test    dword ptr [rcx+1Ch], 800h
0x1800026dc  jnz     loc_1800027DD
0x1800026e2  xorps   xmm0, xmm0
0x1800026e5  movdqu  [rbp+var_30], xmm0
0x1800026ea  mov     [rbp+var_20], 0
0x1800026f2  mov     rcx, rbx; pSid
0x1800026f5  call    cs:__imp_GetLengthSid
0x1800026fb  mov     r9d, eax
0x1800026fe  mov     r8, rbx
0x180002701  mov     rdx, qword ptr [rbp+var_30+8]
0x180002705  lea     rcx, [rbp+var_30]
0x180002709  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x18000270e  lea     rcx, [r14+100h]
0x180002715  mov     r9d, edi
0x180002718  lea     r8, [rbp+var_30]
0x18000271c  mov     rdx, rsi
0x18000271f  call    ?UserLogoff@UserContextTable@Broker@@QEAA_N_KAEBV?$vector@EV?$allocator@E@std@@@std@@K@Z; Broker::UserContextTable::UserLogoff(unsigned __int64,std::vector<uchar> const &,ulong)
0x180002724  test    al, al
0x180002726  jnz     short loc_180002776
0x180002728  mov     rcx, cs:WPP_GLOBAL_Control
0x18000272f  test    dword ptr [rcx+1Ch], 800h
0x180002736  jz      short loc_180002762
0x180002738  cmp     byte ptr [rcx+19h], 5
0x18000273c  jb      short loc_180002762
0x18000273e  mov     edx, 35h ; '5'
0x180002743  mov     r9, rbx
0x180002746  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000274d  mov     rcx, [rcx+10h]; LoggerHandle
0x180002751  call    WPP_SF__sid_
0x180002756  jmp     short loc_180002762
0x180002758  lea     rcx, [rbp+var_18]
0x18000275c  call    ?_Tidy@?$vector@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Tidy(void)
0x180002761  nop
0x180002762  lea     rcx, [rbp+var_30]
0x180002766  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000276b  add     rsp, 70h
0x18000276f  pop     r14
0x180002771  pop     rdi
0x180002772  pop     rsi
0x180002773  pop     rbx
0x180002774  pop     rbp
0x180002775  retn
0x180002776  lea     r8, [rbp+var_30]
0x18000277a  lea     rdx, [rbp+var_18]
0x18000277e  mov     rcx, r14
0x180002781  call    ?SelectUserAppStates@BrokerBase@Broker@@AEAA?AV?$vector@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@V?$allocator@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; Broker::BrokerBase::SelectUserAppStates(std::vector<uchar> const &)
0x180002786  nop
0x180002787  mov     rbx, [rbp+var_18]
0x18000278b  cmp     rbx, [rbp+var_10]
0x18000278f  jz      short loc_180002758
0x180002791  mov     rax, [rbx+8]
0x180002795  test    rax, rax
0x180002798  jz      short loc_18000279E
0x18000279a  lock inc dword ptr [rax+8]
0x18000279e  mov     rsi, [rbx]
0x1800027a1  mov     [rbp+var_40], rsi
0x1800027a5  mov     rdi, [rbx+8]
0x1800027a9  mov     [rbp+var_38], rdi
0x1800027ad  mov     rcx, rsi; this
0x1800027b0  call    ?OnUserLogoff@State@ApplicationStateTable@Broker@@QEAA_NXZ; Broker::ApplicationStateTable::State::OnUserLogoff(void)
0x1800027b5  test    al, al
0x1800027b7  jz      short loc_1800027CA
0x1800027b9  mov     r8, rsi
0x1800027bc  mov     edx, 6
0x1800027c1  mov     rcx, r14
0x1800027c4  call    ?OnAppDisable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::OnAppDisable(_BR_EVENT_CALL_REASON,Broker::ApplicationIdentity const &)
0x1800027c9  nop
0x1800027ca  test    rdi, rdi
0x1800027cd  jz      short loc_1800027D7
0x1800027cf  mov     rcx, rdi; this
0x1800027d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800027d7  add     rbx, 10h
0x1800027db  jmp     short loc_18000278B
0x1800027dd  cmp     byte ptr [rcx+19h], 5
0x1800027e1  jb      loc_1800026E2
0x1800027e7  mov     edx, 34h ; '4'
0x1800027ec  mov     [rsp+70h+pSid], rbx; pSid
0x1800027f1  mov     r9, [r14+8]
0x1800027f5  mov     rcx, [rcx+10h]; LoggerHandle
0x1800027f9  call    WPP_SF__guid__sid_
0x1800027fe  jmp     loc_1800026E2
```
