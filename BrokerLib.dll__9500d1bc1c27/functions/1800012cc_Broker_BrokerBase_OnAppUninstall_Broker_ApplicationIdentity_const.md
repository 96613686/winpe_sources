# Broker::BrokerBase::OnAppUninstall(Broker::ApplicationIdentity const &)

- ea: `0x1800012cc`
- end: `0x1800013c5`
- name: `?OnAppUninstall@BrokerBase@Broker@@AEAAXAEBUApplicationIdentity@2@@Z`
- size: `249`
- prototype: `void(Broker::BrokerBase *__hidden this, const struct Broker::ApplicationIdentity *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180001208`

## callees

- `0x1800012cc`
- `0x18000147c`
- `0x180003650`
- `0x180003cd0`
- `0x180004500`
- `0x180004ae0`
- `0x180004fa0`
- `0x1800183bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Broker::BrokerBase::OnAppUninstall(
        Broker::BrokerBase *this,
        const struct Broker::ApplicationIdentity *a2)
{
  const struct Broker::ApplicationIdentity *v2; // rdi
  Broker::BrokerBase *v3; // rsi
  const wchar_t *v4; // rcx
  _QWORD *i; // rbx
  __int64 v6; // r9
  __int64 v7; // [rsp+30h] [rbp-48h] BYREF
  std::_Ref_count_base *v8; // [rsp+38h] [rbp-40h]
  void *v9[7]; // [rsp+40h] [rbp-38h] BYREF

  v2 = a2;
  v3 = this;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v4 = (const wchar_t *)((char *)a2 + 56);
    if ( *((_QWORD *)a2 + 10) > 7u )
      v4 = *(const wchar_t **)v4;
    WPP_SF__guid__sid_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x25u,
      (__int64)WPP_GLOBAL_Control,
      *((_QWORD *)v3 + 1),
      *(char **)a2,
      v4);
  }
  Broker::BrokerBase::SelectAppEvents(v3, v9, v2);
  for ( i = v9[0]; i != v9[1]; i += 2 )
  {
    try
    {
      std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(&v7, i);
      Broker::BrokerBase::DestroyEvent((__int64)v3, 5u, &v7, v6);
    }
    catch ( Broker::NotFound )
    {
      v3 = this;
      v2 = a2;
    }
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
  }
  try
  {
    Broker::ApplicationStateTable::DeleteApplicationState(*((Broker::ApplicationStateTable **)v3 + 34), v2);
  }
  catch ( Broker::NotFound )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids);
  }
  std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(v9);
}

```

## disassembly

```asm
0x1800012cc  mov     [rsp+arg_8], rdx
0x1800012d1  mov     [rsp+arg_0], rcx
0x1800012d6  push    rbx
0x1800012d7  push    rsi
0x1800012d8  push    rdi
0x1800012d9  sub     rsp, 60h
0x1800012dd  mov     rdi, rdx
0x1800012e0  mov     rsi, rcx
0x1800012e3  mov     r8, cs:WPP_GLOBAL_Control
0x1800012ea  test    dword ptr [r8+1Ch], 800h
0x1800012f2  jz      short loc_180001328
0x1800012f4  cmp     byte ptr [r8+19h], 5
0x1800012f9  jb      short loc_180001328
0x1800012fb  lea     rcx, [rdx+38h]
0x1800012ff  cmp     qword ptr [rcx+18h], 7
0x180001304  jbe     short loc_180001309
0x180001306  mov     rcx, [rcx]
0x180001309  mov     rax, [rdx]
0x18000130c  mov     edx, 25h ; '%'
0x180001311  mov     [rsp+78h+var_50], rcx; __int64
0x180001316  mov     [rsp+78h+pSid], rax; pSid
0x18000131b  mov     r9, [rsi+8]
0x18000131f  mov     rcx, [r8+10h]; LoggerHandle
0x180001323  call    WPP_SF__guid__sid_S
0x180001328  mov     r8, rdi
0x18000132b  lea     rdx, [rsp+78h+var_38]
0x180001330  mov     rcx, rsi
0x180001333  call    ?SelectAppEvents@BrokerBase@Broker@@AEAA?AV?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::SelectAppEvents(Broker::ApplicationIdentity const &)
0x180001338  nop
0x180001339  mov     rbx, [rsp+78h+var_38]
0x18000133e  mov     [rsp+78h+arg_10], rbx
0x180001346  cmp     rbx, [rsp+78h+var_30]
0x18000134b  jnz     short loc_180001371
0x18000134d  mov     rdx, rdi; struct Broker::ApplicationIdentity *
0x180001350  mov     rcx, [rsi+110h]; this
0x180001357  call    ?DeleteApplicationState@ApplicationStateTable@Broker@@QEAAXAEBUApplicationIdentity@2@@Z; Broker::ApplicationStateTable::DeleteApplicationState(Broker::ApplicationIdentity const &)
0x18000135c  nop
0x18000135d  jmp     short $+2
0x18000135f  lea     rcx, [rsp+78h+var_38]
0x180001364  call    ?_Tidy@?$vector@V?$shared_ptr@VBrokerEvent@Broker@@@std@@V?$allocator@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Broker::BrokerEvent>>::_Tidy(void)
0x180001369  add     rsp, 60h
0x18000136d  pop     rdi
0x18000136e  pop     rsi
0x18000136f  pop     rbx
0x180001370  retn
0x180001371  mov     rdx, rbx
0x180001374  lea     rcx, [rsp+78h+var_48]
0x180001379  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x18000137e  nop
0x18000137f  lea     r8, [rsp+78h+var_48]
0x180001384  mov     edx, 5
0x180001389  mov     rcx, rsi
0x18000138c  call    ?DestroyEvent@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::DestroyEvent(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> &)
0x180001391  nop
0x180001392  jmp     short loc_1800013AC
0x180001394  mov     rsi, [rsp+78h+arg_0]
0x18000139c  mov     rdi, [rsp+78h+arg_8]
0x1800013a4  mov     rbx, [rsp+78h+arg_10]
0x1800013ac  mov     rcx, [rsp+78h+var_40]; this
0x1800013b1  test    rcx, rcx
0x1800013b4  jz      short loc_1800013BB
0x1800013b6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800013bb  add     rbx, 10h
0x1800013bf  jmp     loc_18000133E
```
