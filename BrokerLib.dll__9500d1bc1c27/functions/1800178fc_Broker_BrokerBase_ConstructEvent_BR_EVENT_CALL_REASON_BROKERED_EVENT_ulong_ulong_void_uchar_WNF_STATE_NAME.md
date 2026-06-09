# Broker::BrokerBase::ConstructEvent(_BR_EVENT_CALL_REASON,_BROKERED_EVENT *,ulong,ulong,void *,uchar,_WNF_STATE_NAME *)

- ea: `0x1800178fc`
- end: `0x180017a96`
- name: `?ConstructEvent@BrokerBase@Broker@@AEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@W4_BR_EVENT_CALL_REASON@@PEAU_BROKERED_EVENT@@KKPEAXEPEAU_WNF_STATE_NAME@@@Z`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800186a8`

## callees

- `0x180002868`
- `0x180004500`
- `0x180004570`
- `0x180004ae0`
- `0x180004d70`
- `0x180005b50`
- `0x180006b30`
- `0x180007a0c`
- `0x180015af0`
- `0x180015b14`
- `0x1800171e4`
- `0x1800178fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *Broker::BrokerBase::ConstructEvent(__int64 a1, _QWORD *a2, unsigned int a3, __int64 a4, ...)
{
  __int64 v8; // rax
  _QWORD *v9; // rax
  _QWORD *result; // rax
  _QWORD *v11; // rax
  __int64 v12; // [rsp+50h] [rbp-E8h] BYREF
  _QWORD v13[2]; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+70h] [rbp-C8h] BYREF
  _QWORD *v16; // [rsp+78h] [rbp-C0h]
  __int64 v17; // [rsp+80h] [rbp-B8h]
  _BYTE v18[8]; // [rsp+88h] [rbp-B0h] BYREF
  std::_Ref_count_base *v19; // [rsp+90h] [rbp-A8h]
  _BYTE v20[96]; // [rsp+A0h] [rbp-98h] BYREF
  __int64 v21; // [rsp+160h] [rbp+28h] BYREF
  va_list va; // [rsp+160h] [rbp+28h]
  __int64 v23; // [rsp+168h] [rbp+30h] BYREF
  va_list va1; // [rsp+168h] [rbp+30h]
  __int64 v25; // [rsp+170h] [rbp+38h] BYREF
  va_list va2; // [rsp+170h] [rbp+38h]
  va_list va3; // [rsp+178h] [rbp+40h] BYREF

  va_start(va3, a4);
  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v21 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v23 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v25 = va_arg(va3, _QWORD);
  v17 = a1;
  v16 = a2;
  v15 = a4;
  LODWORD(v12) = 1;
  v14 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *(_QWORD *)(a1 + 8));
  Broker::ApplicationIdentity::ApplicationIdentity(
    (Broker::ApplicationIdentity *)v20,
    *(void **)(a4 + 32),
    *(const unsigned __int16 **)(a4 + 24));
  Broker::BrokerBase::ConstructApplicationState(a1, v18, v20);
  v12 = a1;
  v13[0] = operator new(0x60u);
  v8 = std::_Ref_count_obj2<Broker::BrokerEvent>::_Ref_count_obj2<Broker::BrokerEvent>(
         v13[0],
         (unsigned int)&v15,
         (unsigned int)va,
         (unsigned int)va1,
         (__int64)va2,
         (__int64)v18,
         (__int64)va3,
         (__int64)&v14,
         (__int64)&v12);
  *a2 = v8 + 16;
  a2[1] = v8;
  LODWORD(v12) = 3;
  v9 = std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(v13, a2);
  Broker::BrokeredEventTable::Insert(a1 + 208, v9);
  try
  {
    Broker::BrokerBase::OnEventEnable(a1, a3, (std::_Ref_count_base **)a2);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v20);
    result = a2;
  }
  catch ( ... )
  {
    v11 = std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(v13, v16);
    Broker::BrokeredEventTable::Remove(v17 + 208, v11);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x1800178fc  push    rbx
0x1800178fe  push    rsi
0x1800178ff  push    rdi
0x180017900  push    r14
0x180017902  sub     rsp, 118h
0x180017909  mov     rax, cs:__security_cookie
0x180017910  xor     rax, rsp
0x180017913  mov     [rsp+138h+var_38], rax
0x18001791b  mov     rsi, r9
0x18001791e  mov     r14d, r8d
0x180017921  mov     rbx, rdx
0x180017924  mov     rdi, rcx
0x180017927  mov     [rsp+138h+var_B8], rcx
0x18001792f  mov     [rsp+138h+var_C0], rdx
0x180017934  mov     [rsp+138h+var_C8], r9
0x180017939  mov     dword ptr [rsp+138h+var_E8], 1
0x180017941  mov     [rsp+138h+var_D0], 0
0x18001794a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017951  test    dword ptr [rcx+1Ch], 800h
0x180017958  jz      short loc_180017979
0x18001795a  cmp     byte ptr [rcx+19h], 5
0x18001795e  jb      short loc_180017979
0x180017960  mov     edx, 2Ch ; ','
0x180017965  mov     r9, [rdi+8]
0x180017969  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180017970  mov     rcx, [rcx+10h]
0x180017974  call    WPP_SF__guid_
0x180017979  mov     r8, [rsi+18h]; unsigned __int16 *
0x18001797d  mov     rdx, [rsi+20h]; void *
0x180017981  lea     rcx, [rsp+138h+var_98]; this
0x180017989  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x18001798e  nop
0x18001798f  lea     r8, [rsp+138h+var_98]
0x180017997  lea     rdx, [rsp+138h+var_B0]
0x18001799f  mov     rcx, rdi
0x1800179a2  call    ?ConstructApplicationState@BrokerBase@Broker@@AEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::ConstructApplicationState(Broker::ApplicationIdentity const &)
0x1800179a7  nop
0x1800179a8  mov     [rsp+138h+var_E8], rdi
0x1800179ad  mov     ecx, 60h ; '`'; Size
0x1800179b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800179b7  mov     [rsp+138h+var_E0], rax
0x1800179bc  lea     rcx, [rsp+138h+var_E8]
0x1800179c1  mov     [rsp+138h+var_F8], rcx
0x1800179c6  lea     rcx, [rsp+138h+var_D0]
0x1800179cb  mov     [rsp+138h+var_100], rcx
0x1800179d0  lea     rcx, [rsp+138h+arg_38]
0x1800179d8  mov     [rsp+138h+var_108], rcx
0x1800179dd  lea     rcx, [rsp+138h+var_B0]
0x1800179e5  mov     [rsp+138h+var_110], rcx
0x1800179ea  lea     rcx, [rsp+138h+arg_30]
0x1800179f2  mov     [rsp+138h+var_118], rcx
0x1800179f7  lea     r9, [rsp+138h+arg_28]
0x1800179ff  lea     r8, [rsp+138h+arg_20]
0x180017a07  lea     rdx, [rsp+138h+var_C8]
0x180017a0c  mov     rcx, rax
0x180017a0f  call    ??$?0AEAPEAU_BROKERED_EVENT@@AEBKAEBKAEAPEAXAEAV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEAEAEAPEAU_WNF_STATE_NAME@@PEAVBrokerBase@Broker@@@?$_Ref_count_obj2@VBrokerEvent@Broker@@@std@@QEAA@AEAPEAU_BROKERED_EVENT@@AEBK1AEAPEAXAEAV?$shared_ptr@VState@ApplicationStateTable@Broker@@@1@AEAEAEAPEAU_WNF_STATE_NAME@@$$QEAPEAVBrokerBase@Broker@@@Z; std::_Ref_count_obj2<Broker::BrokerEvent>::_Ref_count_obj2<Broker::BrokerEvent>(_BROKERED_EVENT * &,ulong const &,ulong const &,void * &,std::shared_ptr<Broker::ApplicationStateTable::State> &,uchar &,_WNF_STATE_NAME * &,Broker::BrokerBase * &&)
0x180017a14  mov     rcx, rax
0x180017a17  add     rax, 10h
0x180017a1b  mov     [rbx], rax
0x180017a1e  mov     [rbx+8], rcx
0x180017a22  mov     dword ptr [rsp+138h+var_E8], 3
0x180017a2a  mov     rdx, rbx
0x180017a2d  lea     rcx, [rsp+138h+var_E0]
0x180017a32  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x180017a37  lea     rcx, [rdi+0D0h]
0x180017a3e  mov     rdx, rax
0x180017a41  call    ?Insert@BrokeredEventTable@Broker@@QEAAXV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokeredEventTable::Insert(std::shared_ptr<Broker::BrokerEvent>)
0x180017a46  nop
0x180017a47  mov     r8, rbx
0x180017a4a  mov     edx, r14d
0x180017a4d  mov     rcx, rdi
0x180017a50  call    ?OnEventEnable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::OnEventEnable(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> const &)
0x180017a55  nop
0x180017a56  mov     rcx, [rsp+138h+var_A8]; this
0x180017a5e  test    rcx, rcx
0x180017a61  jz      short loc_180017A69
0x180017a63  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180017a68  nop
0x180017a69  lea     rcx, [rsp+138h+var_98]; this
0x180017a71  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180017a76  mov     rax, rbx
0x180017a79  mov     rcx, [rsp+138h+var_38]
0x180017a81  xor     rcx, rsp; StackCookie
0x180017a84  call    __security_check_cookie
0x180017a89  add     rsp, 118h
0x180017a90  pop     r14
0x180017a92  pop     rdi
0x180017a93  pop     rsi
0x180017a94  pop     rbx
0x180017a95  retn
```
