# Broker::BrokerBase::OnRemoveLockScreen(Broker::ApplicationIdentity const &)

- ea: `0x1800185f4`
- end: `0x1800186a1`
- name: `?OnRemoveLockScreen@BrokerBase@Broker@@AEAAXAEBUApplicationIdentity@2@@Z`
- size: `173`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this, const struct Broker::ApplicationIdentity *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017578`

## callees

- `0x180002e88`
- `0x180003650`
- `0x180004ae0`
- `0x180007a0c`
- `0x1800185f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BrokerBase::OnRemoveLockScreen(
        Broker::BrokerBase *this,
        const struct Broker::ApplicationIdentity *a2)
{
  const wchar_t *v4; // r8
  int v5; // eax
  int v6; // eax
  __int64 v7; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v8; // [rsp+38h] [rbp-10h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v4 = (const wchar_t *)((char *)a2 + 56);
    if ( *((_QWORD *)a2 + 10) > 7u )
      v4 = *(const wchar_t **)v4;
    WPP_SF__guid__sid_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x3Bu,
      (__int64)v4,
      *((_QWORD *)this + 1),
      *(char **)a2,
      v4);
  }
  try
  {
    Broker::BrokerBase::ConstructApplicationState((__int64)this, &v7, (__int64 *)a2);
    v5 = *(_DWORD *)(v7 + 140);
    if ( v5 > 0 )
    {
      v6 = v5 - 1;
      *(_DWORD *)(v7 + 140) = v6;
      if ( !v6 )
        Broker::BrokerBase::OnAppDisable((__int64)this, 5u, (char **)a2);
    }
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
  }
  catch ( std::bad_alloc )
  {
  }
}

```

## disassembly

```asm
0x1800185f4  mov     [rsp+arg_0], rbx
0x1800185f9  push    rdi
0x1800185fa  sub     rsp, 40h
0x1800185fe  mov     rbx, rdx
0x180018601  mov     rdi, rcx
0x180018604  mov     rcx, cs:WPP_GLOBAL_Control
0x18001860b  test    dword ptr [rcx+1Ch], 800h
0x180018612  jz      short loc_180018648
0x180018614  cmp     byte ptr [rcx+19h], 5
0x180018618  jb      short loc_180018648
0x18001861a  lea     r8, [rdx+38h]
0x18001861e  cmp     qword ptr [r8+18h], 7
0x180018623  jbe     short loc_180018628
0x180018625  mov     r8, [r8]
0x180018628  mov     rax, [rdx]
0x18001862b  mov     edx, 3Bh ; ';'
0x180018630  mov     [rsp+48h+var_20], r8; __int64
0x180018635  mov     [rsp+48h+pSid], rax; pSid
0x18001863a  mov     r9, [rdi+8]
0x18001863e  mov     rcx, [rcx+10h]; LoggerHandle
0x180018642  call    WPP_SF__guid__sid_S
0x180018647  nop
0x180018648  mov     r8, rbx
0x18001864b  lea     rdx, [rsp+48h+var_18]
0x180018650  mov     rcx, rdi
0x180018653  call    ?ConstructApplicationState@BrokerBase@Broker@@AEAA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::ConstructApplicationState(Broker::ApplicationIdentity const &)
0x180018658  nop
0x180018659  mov     rcx, [rsp+48h+var_18]
0x18001865e  mov     eax, [rcx+8Ch]
0x180018664  test    eax, eax
0x180018666  jle     short loc_180018684
0x180018668  sub     eax, 1
0x18001866b  mov     [rcx+8Ch], eax
0x180018671  jnz     short loc_180018684
0x180018673  mov     r8, rbx
0x180018676  mov     edx, 5
0x18001867b  mov     rcx, rdi
0x18001867e  call    ?OnAppDisable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::OnAppDisable(_BR_EVENT_CALL_REASON,Broker::ApplicationIdentity const &)
0x180018683  nop
0x180018684  mov     rcx, [rsp+48h+var_10]; this
0x180018689  test    rcx, rcx
0x18001868c  jz      short loc_180018694
0x18001868e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018693  nop
0x180018694  jmp     short $+2
0x180018696  mov     rbx, [rsp+48h+arg_0]
0x18001869b  add     rsp, 40h
0x18001869f  pop     rdi
0x1800186a0  retn
```
