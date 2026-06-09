# Broker::TimeBroker::Init(void)

- ea: `0x180012458`
- end: `0x180012622`
- name: `?Init@TimeBroker@Broker@@QEAAXXZ`
- size: `458`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800120f4`

## callees

- `0x180003800`
- `0x180003840`
- `0x180004488`
- `0x180010b34`
- `0x180012458`
- `0x18001396c`
- `0x180014ecc`
- `0x180015e2c`

## import_xrefs

- `BrokerLib!BrCreateBrokerInstance2` at `0x180012576`
- `BrokerLib!BrCreateBrokerInstance2` at `0x180012576`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x1800125a2`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x1800125a2`

## pseudocode

```c
void __fastcall Broker::TimeBroker::Init(Broker::TimeBroker *this)
{
  char *v2; // rdi
  unsigned __int64 v3; // rcx
  char *v4; // rax
  size_t v5; // rbx
  __int64 i; // rdx
  unsigned int BrokerInstance2; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // [rsp+30h] [rbp-48h] BYREF
  void *v11; // [rsp+38h] [rbp-40h]
  __int64 v12; // [rsp+40h] [rbp-38h]
  _QWORD v13[6]; // [rsp+48h] [rbp-30h] BYREF

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
  std::vector<_GUID>::vector<_GUID>(&v10);
  v13[0] = Broker::TimeBroker::OnCreateEvent;
  v13[1] = Broker::TimeBroker::OnDeleteEvent;
  v13[2] = &Broker::TimeBroker::OnEnableEvent;
  v13[3] = &Broker::TimeBroker::OnDisableEvent;
  v13[4] = 0;
  Broker::TimeBroker::RegisterPowerNotification(this);
  v2 = (char *)v11;
  v3 = ((__int64)v11 - v10) >> 2;
  if ( v3 > 8 )
  {
    v4 = (char *)(v10 + 32);
LABEL_10:
    v11 = v4;
    goto LABEL_11;
  }
  if ( v3 < 8 )
  {
    if ( (unsigned __int64)((v12 - v10) >> 2) >= 8 )
    {
      v5 = 4 * (8 - v3);
      memset_0(v11, 0, v5);
      v4 = &v2[v5];
      goto LABEL_10;
    }
    std::vector<unsigned long>::_Resize_reallocate<std::_Value_init_tag>(&v10);
  }
LABEL_11:
  for ( i = 0; i != 8; ++i )
    *(_DWORD *)(v10 + 4 * i) = *((_DWORD *)qword_18001F420 + i);
  BrokerInstance2 = BrCreateBrokerInstance2(v13, &Broker::TimeBroker::BrokerId, ((__int64)v11 - v10) >> 2);
  if ( BrokerInstance2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_26;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_23;
    v9 = 11;
    goto LABEL_21;
  }
  BrokerInstance2 = BrInitializeBrokerInstance2(*((_QWORD *)this + 24), 0, 0);
  if ( !BrokerInstance2 )
  {
LABEL_22:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  v8 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_26;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v9 = 12;
LABEL_21:
    WPP_SF_d(v8[2], v9, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, BrokerInstance2);
    goto LABEL_22;
  }
LABEL_23:
  if ( (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_(v8[2], 13, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
LABEL_26:
  if ( v10 )
    std::_Deallocate<16>(v10, (v12 - v10) & 0xFFFFFFFFFFFFFFFCuLL);
}

```

## disassembly

```asm
0x180012458  push    rbp
0x18001245a  push    rbx
0x18001245b  push    rsi
0x18001245c  push    rdi
0x18001245d  mov     rbp, rsp
0x180012460  sub     rsp, 78h
0x180012464  mov     rsi, rcx
0x180012467  mov     rcx, cs:WPP_GLOBAL_Control
0x18001246e  test    byte ptr [rcx+1Ch], 1
0x180012472  jz      short loc_18001248F
0x180012474  cmp     byte ptr [rcx+19h], 4
0x180012478  jb      short loc_18001248F
0x18001247a  mov     edx, 0Ah
0x18001247f  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180012486  mov     rcx, [rcx+10h]
0x18001248a  call    WPP_SF_
0x18001248f  lea     rcx, [rbp+var_48]
0x180012493  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180012498  nop
0x180012499  lea     rax, ?OnCreateEvent@TimeBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z; Broker::TimeBroker::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)
0x1800124a0  mov     [rbp+var_30], rax
0x1800124a4  lea     rax, ?OnDeleteEvent@TimeBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; Broker::TimeBroker::OnDeleteEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x1800124ab  mov     [rbp+var_28], rax
0x1800124af  lea     rax, ?OnEnableEvent@TimeBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; Broker::TimeBroker::OnEnableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x1800124b6  mov     [rbp+var_20], rax
0x1800124ba  lea     rax, ?OnDisableEvent@TimeBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; Broker::TimeBroker::OnDisableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x1800124c1  mov     [rbp+var_18], rax
0x1800124c5  xor     eax, eax
0x1800124c7  mov     [rbp+var_10], rax
0x1800124cb  mov     rcx, rsi; this
0x1800124ce  call    ?RegisterPowerNotification@TimeBroker@Broker@@AEAAXXZ; Broker::TimeBroker::RegisterPowerNotification(void)
0x1800124d3  mov     rdx, [rbp+var_48]
0x1800124d7  mov     rdi, [rbp+var_40]
0x1800124db  mov     rcx, rdi
0x1800124de  sub     rcx, rdx
0x1800124e1  sar     rcx, 2
0x1800124e5  cmp     rcx, 8
0x1800124e9  jbe     short loc_1800124F1
0x1800124eb  lea     rax, [rdx+20h]
0x1800124ef  jmp     short loc_180012530
0x1800124f1  jnb     short loc_180012534
0x1800124f3  mov     rax, [rbp+var_38]
0x1800124f7  sub     rax, rdx
0x1800124fa  sar     rax, 2
0x1800124fe  cmp     rax, 8
0x180012502  jnb     short loc_18001250F
0x180012504  lea     rcx, [rbp+var_48]
0x180012508  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ulong>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001250d  jmp     short loc_180012534
0x18001250f  mov     eax, 8
0x180012514  sub     rax, rcx
0x180012517  lea     rbx, ds:0[rax*4]
0x18001251f  mov     r8, rbx; Size
0x180012522  xor     edx, edx; Val
0x180012524  mov     rcx, rdi; void *
0x180012527  call    memset_0
0x18001252c  lea     rax, [rbx+rdi]
0x180012530  mov     [rbp+var_40], rax
0x180012534  xor     edx, edx
0x180012536  lea     rcx, qword_18001F420
0x18001253d  mov     ecx, [rcx+rdx*4]
0x180012540  mov     rax, [rbp+var_48]
0x180012544  mov     [rax+rdx*4], ecx
0x180012547  inc     rdx
0x18001254a  cmp     rdx, 8
0x18001254e  jnz     short loc_180012536
0x180012550  mov     r9, [rbp+var_48]
0x180012554  lea     rbx, [rsi+0C0h]
0x18001255b  mov     r8, [rbp+var_40]
0x18001255f  sub     r8, r9
0x180012562  sar     r8, 2
0x180012566  mov     [rsp+78h+var_58], rbx
0x18001256b  lea     rdx, ?BrokerId@TimeBroker@Broker@@0U_GUID@@B; _GUID const Broker::TimeBroker::BrokerId
0x180012572  lea     rcx, [rbp+var_30]
0x180012576  call    cs:__imp_BrCreateBrokerInstance2
0x18001257c  test    eax, eax
0x18001257e  jz      short loc_18001259A
0x180012580  mov     rcx, cs:WPP_GLOBAL_Control
0x180012587  test    byte ptr [rcx+1Ch], 1
0x18001258b  jz      short loc_180012600
0x18001258d  cmp     byte ptr [rcx+19h], 4
0x180012591  jb      short loc_1800125DE
0x180012593  mov     edx, 0Bh
0x180012598  jmp     short loc_1800125C4
0x18001259a  xor     r8d, r8d
0x18001259d  xor     edx, edx
0x18001259f  mov     rcx, [rbx]
0x1800125a2  call    cs:__imp_BrInitializeBrokerInstance2
0x1800125a8  test    eax, eax
0x1800125aa  jz      short loc_1800125D7
0x1800125ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125b3  test    byte ptr [rcx+1Ch], 1
0x1800125b7  jz      short loc_180012600
0x1800125b9  cmp     byte ptr [rcx+19h], 4
0x1800125bd  jb      short loc_1800125DE
0x1800125bf  mov     edx, 0Ch
0x1800125c4  mov     r9d, eax
0x1800125c7  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800125ce  mov     rcx, [rcx+10h]
0x1800125d2  call    WPP_SF_d
0x1800125d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125de  test    byte ptr [rcx+1Ch], 1
0x1800125e2  jz      short loc_180012600
0x1800125e4  cmp     byte ptr [rcx+19h], 4
0x1800125e8  jb      short loc_180012600
0x1800125ea  mov     edx, 0Dh
0x1800125ef  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800125f6  mov     rcx, [rcx+10h]
0x1800125fa  call    WPP_SF_
0x1800125ff  nop
0x180012600  mov     rcx, [rbp+var_48]
0x180012604  test    rcx, rcx
0x180012607  jz      short loc_180012619
0x180012609  mov     rdx, [rbp+var_38]
0x18001260d  sub     rdx, rcx
0x180012610  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180012614  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012619  add     rsp, 78h
0x18001261d  pop     rdi
0x18001261e  pop     rsi
0x18001261f  pop     rbx
0x180012620  pop     rbp
0x180012621  retn
```
