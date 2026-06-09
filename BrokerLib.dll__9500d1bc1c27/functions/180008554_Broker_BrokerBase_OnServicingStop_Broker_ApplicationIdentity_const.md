# Broker::BrokerBase::OnServicingStop(Broker::ApplicationIdentity const &)

- ea: `0x180008554`
- end: `0x1800085fc`
- name: `?OnServicingStop@BrokerBase@Broker@@AEAAXAEBUApplicationIdentity@2@@Z`
- size: `168`
- prototype: `void(Broker::BrokerBase *__hidden this, const struct Broker::ApplicationIdentity *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180008724`

## callees

- `0x180003650`
- `0x180003760`
- `0x180004ae0`
- `0x180007a0c`
- `0x180008554`
- `0x180013500`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BrokerBase::OnServicingStop(
        Broker::BrokerBase *this,
        const struct Broker::ApplicationIdentity *a2)
{
  const wchar_t *v4; // r8
  Broker::ApplicationStateTable::State *v5; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v6; // [rsp+38h] [rbp-10h]

  try
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v4 = (const wchar_t *)((char *)a2 + 56);
      if ( *((_QWORD *)a2 + 10) > 7u )
        v4 = *(const wchar_t **)v4;
      WPP_SF__guid__sid_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x39u,
        (__int64)v4,
        *((_QWORD *)this + 1),
        *(char **)a2,
        v4);
    }
    Broker::BrokerBase::ConstructApplicationState((__int64)this, (__int64 *)&v5, (__int64 *)a2);
    if ( Broker::ApplicationStateTable::State::OnServicingStop(v5, a2) )
      Broker::BrokerBase::OnAppEnable((__int64)this, 5u, a2);
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
  }
  catch ( std::bad_alloc )
  {
  }
}

```

## disassembly

```asm
0x180008554  mov     [rsp+arg_0], rbx
0x180008559  push    rdi
0x18000855a  sub     rsp, 40h
0x18000855e  mov     rbx, rdx
0x180008561  mov     rdi, rcx
0x180008564  mov     rcx, cs:WPP_GLOBAL_Control
0x18000856b  test    dword ptr [rcx+1Ch], 800h
0x180008572  jnz     short loc_1800085C2
0x180008574  mov     r8, rbx
0x180008577  lea     rdx, [rsp+48h+var_18]
0x18000857c  mov     rcx, rdi
0x18000857f  call    ?ConstructApplicationState@BrokerBase@Broker@@AEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::ConstructApplicationState(Broker::ApplicationIdentity const &)
0x180008584  nop
0x180008585  mov     rdx, rbx; struct Broker::ApplicationIdentity *
0x180008588  mov     rcx, [rsp+48h+var_18]; this
0x18000858d  call    ?OnServicingStop@State@ApplicationStateTable@Broker@@QEAA_NPEBUApplicationIdentity@3@@Z; Broker::ApplicationStateTable::State::OnServicingStop(Broker::ApplicationIdentity const *)
0x180008592  test    al, al
0x180008594  jz      short loc_1800085A7
0x180008596  mov     r8, rbx
0x180008599  mov     edx, 5
0x18000859e  mov     rcx, rdi
0x1800085a1  call    ?OnAppEnable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::OnAppEnable(_BR_EVENT_CALL_REASON,Broker::ApplicationIdentity const &)
0x1800085a6  nop
0x1800085a7  mov     rcx, [rsp+48h+var_10]; this
0x1800085ac  test    rcx, rcx
0x1800085af  jz      short loc_1800085B7
0x1800085b1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800085b6  nop
0x1800085b7  mov     rbx, [rsp+48h+arg_0]
0x1800085bc  add     rsp, 40h
0x1800085c0  pop     rdi
0x1800085c1  retn
0x1800085c2  cmp     byte ptr [rcx+19h], 5
0x1800085c6  jb      short loc_180008574
0x1800085c8  lea     r8, [rdx+38h]
0x1800085cc  cmp     qword ptr [r8+18h], 7
0x1800085d1  jbe     short loc_1800085D6
0x1800085d3  mov     r8, [r8]
0x1800085d6  mov     rax, [rdx]
0x1800085d9  mov     edx, 39h ; '9'
0x1800085de  mov     [rsp+48h+var_20], r8; __int64
0x1800085e3  mov     [rsp+48h+pSid], rax; pSid
0x1800085e8  mov     r9, [rdi+8]
0x1800085ec  mov     rcx, [rcx+10h]; LoggerHandle
0x1800085f0  call    WPP_SF__guid__sid_S
0x1800085f5  jmp     loc_180008574
0x1800085fa  jmp     short loc_1800085B7
```
