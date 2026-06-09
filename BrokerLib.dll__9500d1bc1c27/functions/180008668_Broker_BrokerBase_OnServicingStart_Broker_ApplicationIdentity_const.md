# Broker::BrokerBase::OnServicingStart(Broker::ApplicationIdentity const &)

- ea: `0x180008668`
- end: `0x18000871d`
- name: `?OnServicingStart@BrokerBase@Broker@@AEAAXAEBUApplicationIdentity@2@@Z`
- size: `181`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this, const struct Broker::ApplicationIdentity *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800087e8`

## callees

- `0x180002e88`
- `0x180003650`
- `0x180004ae0`
- `0x180007a0c`
- `0x180008668`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BrokerBase::OnServicingStart(
        Broker::BrokerBase *this,
        const struct Broker::ApplicationIdentity *a2)
{
  _BYTE *v4; // rcx
  const wchar_t *v5; // r8
  __int64 v6; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v7; // [rsp+38h] [rbp-10h]

  try
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v5 = (const wchar_t *)((char *)a2 + 56);
      if ( *((_QWORD *)a2 + 10) > 7u )
        v5 = *(const wchar_t **)v5;
      WPP_SF__guid__sid_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x38u,
        (__int64)v5,
        *((_QWORD *)this + 1),
        *(char **)a2,
        v5);
    }
    Broker::BrokerBase::ConstructApplicationState((__int64)this, &v6, (__int64 *)a2);
    v4 = (_BYTE *)(v6 + 137);
    if ( *(_BYTE *)(v6 + 136) && *v4 )
    {
      *v4 = 0;
      Broker::BrokerBase::OnAppDisable((__int64)this, 5u, (char **)a2);
    }
    else
    {
      *v4 = 0;
    }
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
0x180008668  mov     [rsp+arg_0], rbx
0x18000866d  push    rdi
0x18000866e  sub     rsp, 40h
0x180008672  mov     rbx, rdx
0x180008675  mov     rdi, rcx
0x180008678  mov     rcx, cs:WPP_GLOBAL_Control
0x18000867f  test    dword ptr [rcx+1Ch], 800h
0x180008686  jnz     short loc_1800086CC
0x180008688  mov     r8, rbx
0x18000868b  lea     rdx, [rsp+48h+var_18]
0x180008690  mov     rcx, rdi
0x180008693  call    ?ConstructApplicationState@BrokerBase@Broker@@AEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::ConstructApplicationState(Broker::ApplicationIdentity const &)
0x180008698  nop
0x180008699  mov     rax, [rsp+48h+var_18]
0x18000869e  lea     rcx, [rax+89h]
0x1800086a5  cmp     byte ptr [rax+88h], 0
0x1800086ac  jnz     short loc_180008701
0x1800086ae  mov     byte ptr [rcx], 0
0x1800086b1  mov     rcx, [rsp+48h+var_10]; this
0x1800086b6  test    rcx, rcx
0x1800086b9  jz      short loc_1800086C1
0x1800086bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800086c0  nop
0x1800086c1  mov     rbx, [rsp+48h+arg_0]
0x1800086c6  add     rsp, 40h
0x1800086ca  pop     rdi
0x1800086cb  retn
0x1800086cc  cmp     byte ptr [rcx+19h], 5
0x1800086d0  jb      short loc_180008688
0x1800086d2  lea     r8, [rdx+38h]
0x1800086d6  cmp     qword ptr [r8+18h], 7
0x1800086db  jbe     short loc_1800086E0
0x1800086dd  mov     r8, [r8]
0x1800086e0  mov     rax, [rdx]
0x1800086e3  mov     edx, 38h ; '8'
0x1800086e8  mov     [rsp+48h+var_20], r8; __int64
0x1800086ed  mov     [rsp+48h+pSid], rax; pSid
0x1800086f2  mov     r9, [rdi+8]
0x1800086f6  mov     rcx, [rcx+10h]; LoggerHandle
0x1800086fa  call    WPP_SF__guid__sid_S
0x1800086ff  jmp     short loc_180008688
0x180008701  cmp     byte ptr [rcx], 0
0x180008704  jz      short loc_1800086AE
0x180008706  mov     byte ptr [rcx], 0
0x180008709  mov     r8, rbx
0x18000870c  mov     edx, 5
0x180008711  mov     rcx, rdi
0x180008714  call    ?OnAppDisable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::OnAppDisable(_BR_EVENT_CALL_REASON,Broker::ApplicationIdentity const &)
0x180008719  jmp     short loc_1800086B1
0x18000871b  jmp     short loc_1800086C1
```
