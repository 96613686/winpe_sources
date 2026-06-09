# Broker::BrokeredEventTable::Insert(std::shared_ptr<Broker::BrokerEvent>)

- ea: `0x180004570`
- end: `0x1800046eb`
- name: `?Insert@BrokeredEventTable@Broker@@QEAAXV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800178fc`

## callees

- `0x180003000`
- `0x180003148`
- `0x180003398`
- `0x180004570`
- `0x180004ae0`
- `0x180015af0`

## import_xrefs

- `RPCRT4!UuidIsNil` at `0x180004657`
- `RPCRT4!UuidIsNil` at `0x180004657`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Broker::BrokeredEventTable::Insert(_QWORD *a1, std::_Ref_count_base **a2)
{
  std::_Ref_count_base *v4; // rax
  std::_Ref_count_base *v5; // rax
  std::_Ref_count_base *v6; // rax
  std::_Ref_count_base *v7; // rcx
  RPC_STATUS Status; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v9[16]; // [rsp+28h] [rbp-58h] BYREF
  std::_Ref_count_base **v10; // [rsp+38h] [rbp-48h]
  UUID v11; // [rsp+40h] [rbp-40h] BYREF
  std::_Ref_count_base *v12; // [rsp+50h] [rbp-30h]
  std::_Ref_count_base *v13; // [rsp+58h] [rbp-28h]
  UUID Uuid; // [rsp+60h] [rbp-20h] BYREF

  v10 = a2;
  Status = 0;
  *(_QWORD *)&v11.Data1 = *((_QWORD *)*a2 + 2);
  v4 = a2[1];
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
  *(_QWORD *)v11.Data4 = *a2;
  v12 = a2[1];
  std::_Tree<std::_Tmap_traits<_BROKERED_EVENT *,std::shared_ptr<Broker::BrokerEvent>,std::less<_BROKERED_EVENT *>,std::allocator<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_BROKERED_EVENT *,std::shared_ptr<Broker::BrokerEvent>>>(
    a1,
    (__int64)v9,
    &v11);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  if ( *(_QWORD *)(*((_QWORD *)*a2 + 2) + 16LL) )
  {
    *(_QWORD *)&v11.Data1 = *(_QWORD *)(*((_QWORD *)*a2 + 2) + 16LL);
    v5 = a2[1];
    if ( v5 )
      _InterlockedIncrement((volatile signed __int32 *)v5 + 2);
    *(_QWORD *)v11.Data4 = *a2;
    v12 = a2[1];
    std::_Tree<std::_Tmap_traits<_CBROKERED_EVENT_ID,std::shared_ptr<Broker::BrokerEvent>,std::less<_CBROKERED_EVENT_ID>,std::allocator<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_CBROKERED_EVENT_ID,std::shared_ptr<Broker::BrokerEvent>>>(
      a1 + 4,
      (__int64)v9,
      &v11);
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
  }
  Uuid = *(UUID *)*((_QWORD *)*a2 + 2);
  if ( !UuidIsNil(&Uuid, &Status) )
  {
    v11 = Uuid;
    v6 = a2[1];
    if ( v6 )
      _InterlockedIncrement((volatile signed __int32 *)v6 + 2);
    v12 = *a2;
    v13 = a2[1];
    std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerEvent>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_GUID,std::shared_ptr<Broker::BrokerEvent>>>(
      a1 + 2,
      v9,
      &v11);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
  }
  v7 = a2[1];
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
}

```

## disassembly

```asm
0x180004570  mov     [rsp-8+arg_10], rbx
0x180004575  mov     [rsp-8+arg_18], rdi
0x18000457a  push    rbp
0x18000457b  mov     rbp, rsp
0x18000457e  sub     rsp, 80h
0x180004585  mov     rax, cs:__security_cookie
0x18000458c  xor     rax, rsp
0x18000458f  mov     [rbp+var_10], rax
0x180004593  mov     rbx, rdx
0x180004596  mov     rdi, rcx
0x180004599  mov     [rbp+var_48], rdx
0x18000459d  mov     [rbp+Status], 0
0x1800045a4  mov     rax, [rdx]
0x1800045a7  mov     rdx, [rax+10h]
0x1800045ab  mov     qword ptr [rbp+var_40], rdx
0x1800045af  mov     rax, [rbx+8]
0x1800045b3  test    rax, rax
0x1800045b6  jz      short loc_1800045BC
0x1800045b8  lock inc dword ptr [rax+8]
0x1800045bc  mov     rax, [rbx]
0x1800045bf  mov     qword ptr [rbp+var_40+8], rax
0x1800045c3  mov     rax, [rbx+8]
0x1800045c7  mov     [rbp+var_30], rax
0x1800045cb  lea     r8, [rbp+var_40]
0x1800045cf  lea     rdx, [rbp+var_58]
0x1800045d3  call    ??$_Emplace@U?$pair@PEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@PEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@U?$less@PEAU_BROKERED_EVENT@@@3@V?$allocator@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@PEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<_BROKERED_EVENT *,std::shared_ptr<Broker::BrokerEvent>,std::less<_BROKERED_EVENT *>,std::allocator<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_BROKERED_EVENT *,std::shared_ptr<Broker::BrokerEvent>>>(std::pair<_BROKERED_EVENT *,std::shared_ptr<Broker::BrokerEvent>> &&)
0x1800045d8  nop
0x1800045d9  mov     rcx, [rbp+var_30]; this
0x1800045dd  test    rcx, rcx
0x1800045e0  jz      short loc_1800045E7
0x1800045e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800045e7  mov     rax, [rbx]
0x1800045ea  mov     rax, [rax+10h]
0x1800045ee  mov     rax, [rax+10h]
0x1800045f2  test    eax, eax
0x1800045f4  jz      loc_1800046D6
0x1800045fa  mov     dword ptr [rbp+var_40], eax
0x1800045fd  shr     rax, 20h
0x180004601  mov     dword ptr [rbp+var_40+4], eax
0x180004604  mov     rax, [rbx+8]
0x180004608  test    rax, rax
0x18000460b  jz      short loc_180004611
0x18000460d  lock inc dword ptr [rax+8]
0x180004611  mov     rax, [rbx]
0x180004614  mov     qword ptr [rbp+var_40+8], rax
0x180004618  mov     rax, [rbx+8]
0x18000461c  mov     [rbp+var_30], rax
0x180004620  lea     rcx, [rdi+20h]
0x180004624  lea     r8, [rbp+var_40]
0x180004628  lea     rdx, [rbp+var_58]
0x18000462c  call    ??$_Emplace@U?$pair@U_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@U?$less@U_CBROKERED_EVENT_ID@@@3@V?$allocator@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_CBROKERED_EVENT_ID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<_CBROKERED_EVENT_ID,std::shared_ptr<Broker::BrokerEvent>,std::less<_CBROKERED_EVENT_ID>,std::allocator<std::pair<_CBROKERED_EVENT_ID const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_CBROKERED_EVENT_ID,std::shared_ptr<Broker::BrokerEvent>>>(std::pair<_CBROKERED_EVENT_ID,std::shared_ptr<Broker::BrokerEvent>> &&)
0x180004631  nop
0x180004632  mov     rcx, [rbp+var_30]; this
0x180004636  test    rcx, rcx
0x180004639  jz      short loc_180004640
0x18000463b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004640  mov     rax, [rbx]
0x180004643  mov     rcx, [rax+10h]
0x180004647  movups  xmm0, xmmword ptr [rcx]
0x18000464a  movdqu  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18000464f  lea     rdx, [rbp+Status]; Status
0x180004653  lea     rcx, [rbp+Uuid]; Uuid
0x180004657  call    cs:__imp_UuidIsNil
0x18000465d  test    eax, eax
0x18000465f  jnz     short loc_1800046A7
0x180004661  movups  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180004665  movdqu  [rbp+var_40], xmm0
0x18000466a  mov     rax, [rbx+8]
0x18000466e  test    rax, rax
0x180004671  jz      short loc_180004677
0x180004673  lock inc dword ptr [rax+8]
0x180004677  mov     rax, [rbx]
0x18000467a  mov     [rbp+var_30], rax
0x18000467e  mov     rax, [rbx+8]
0x180004682  mov     [rbp+var_28], rax
0x180004686  lea     rcx, [rdi+10h]
0x18000468a  lea     r8, [rbp+var_40]
0x18000468e  lea     rdx, [rbp+var_58]
0x180004692  call    ??$_Emplace@U?$pair@U_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerEvent>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_GUID,std::shared_ptr<Broker::BrokerEvent>>>(std::pair<_GUID,std::shared_ptr<Broker::BrokerEvent>> &&)
0x180004697  nop
0x180004698  mov     rcx, [rbp+var_28]; this
0x18000469c  test    rcx, rcx
0x18000469f  jz      short loc_1800046A7
0x1800046a1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800046a6  nop
0x1800046a7  mov     rcx, [rbx+8]; this
0x1800046ab  test    rcx, rcx
0x1800046ae  jz      short loc_1800046B5
0x1800046b0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800046b5  mov     rcx, [rbp+var_10]
0x1800046b9  xor     rcx, rsp; StackCookie
0x1800046bc  call    __security_check_cookie
0x1800046c1  lea     r11, [rsp+80h+var_s0]
0x1800046c9  mov     rbx, [r11+20h]
0x1800046cd  mov     rdi, [r11+28h]
0x1800046d1  mov     rsp, r11
0x1800046d4  pop     rbp
0x1800046d5  retn
0x1800046d6  mov     rcx, rax
0x1800046d9  shr     rcx, 20h
0x1800046dd  test    ecx, ecx
0x1800046df  jz      loc_180004640
0x1800046e5  jmp     loc_1800045FA
```
