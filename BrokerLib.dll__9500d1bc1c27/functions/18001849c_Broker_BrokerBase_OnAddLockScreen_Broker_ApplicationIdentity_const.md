# Broker::BrokerBase::OnAddLockScreen(Broker::ApplicationIdentity const &)

- ea: `0x18001849c`
- end: `0x180018543`
- name: `?OnAddLockScreen@BrokerBase@Broker@@AEAAXAEBUApplicationIdentity@2@@Z`
- size: `167`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this, const struct Broker::ApplicationIdentity *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001764c`

## callees

- `0x180003650`
- `0x180003760`
- `0x180004ae0`
- `0x180007a0c`
- `0x18001849c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BrokerBase::OnAddLockScreen(
        Broker::BrokerBase *this,
        const struct Broker::ApplicationIdentity *a2)
{
  const wchar_t *v4; // r8
  __int64 v5; // rax
  __int64 v6; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v7; // [rsp+38h] [rbp-10h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v4 = (const wchar_t *)((char *)a2 + 56);
    if ( *((_QWORD *)a2 + 10) > 7u )
      v4 = *(const wchar_t **)v4;
    WPP_SF__guid__sid_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x3Au,
      (__int64)v4,
      *((_QWORD *)this + 1),
      *(char **)a2,
      v4);
  }
  try
  {
    Broker::BrokerBase::ConstructApplicationState((__int64)this, &v6, (__int64 *)a2);
    v5 = v6;
    ++*(_DWORD *)(v6 + 140);
    if ( *(_DWORD *)(v5 + 140) == 1 )
      Broker::BrokerBase::OnAppEnable((__int64)this, 5u, a2);
    if ( v7 )
      std::_Ref_count_base::_Decref(v7);
  }
  catch ( std::bad_alloc )
  {
  }
}

```

## disassembly

```asm
0x18001849c  mov     [rsp+arg_0], rbx
0x1800184a1  push    rdi
0x1800184a2  sub     rsp, 40h
0x1800184a6  mov     rbx, rdx
0x1800184a9  mov     rdi, rcx
0x1800184ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184b3  test    dword ptr [rcx+1Ch], 800h
0x1800184ba  jz      short loc_1800184F0
0x1800184bc  cmp     byte ptr [rcx+19h], 5
0x1800184c0  jb      short loc_1800184F0
0x1800184c2  lea     r8, [rdx+38h]
0x1800184c6  cmp     qword ptr [r8+18h], 7
0x1800184cb  jbe     short loc_1800184D0
0x1800184cd  mov     r8, [r8]
0x1800184d0  mov     rax, [rdx]
0x1800184d3  mov     edx, 3Ah ; ':'
0x1800184d8  mov     [rsp+48h+var_20], r8; __int64
0x1800184dd  mov     [rsp+48h+pSid], rax; pSid
0x1800184e2  mov     r9, [rdi+8]
0x1800184e6  mov     rcx, [rcx+10h]; LoggerHandle
0x1800184ea  call    WPP_SF__guid__sid_S
0x1800184ef  nop
0x1800184f0  mov     r8, rbx
0x1800184f3  lea     rdx, [rsp+48h+var_18]
0x1800184f8  mov     rcx, rdi
0x1800184fb  call    ?ConstructApplicationState@BrokerBase@Broker@@AEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::ConstructApplicationState(Broker::ApplicationIdentity const &)
0x180018500  nop
0x180018501  mov     rax, [rsp+48h+var_18]
0x180018506  inc     dword ptr [rax+8Ch]
0x18001850c  cmp     dword ptr [rax+8Ch], 1
0x180018513  jnz     short loc_180018526
0x180018515  mov     r8, rbx
0x180018518  mov     edx, 5
0x18001851d  mov     rcx, rdi
0x180018520  call    ?OnAppEnable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::OnAppEnable(_BR_EVENT_CALL_REASON,Broker::ApplicationIdentity const &)
0x180018525  nop
0x180018526  mov     rcx, [rsp+48h+var_10]; this
0x18001852b  test    rcx, rcx
0x18001852e  jz      short loc_180018536
0x180018530  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018535  nop
0x180018536  jmp     short $+2
0x180018538  mov     rbx, [rsp+48h+arg_0]
0x18001853d  add     rsp, 40h
0x180018541  pop     rdi
0x180018542  retn
```
