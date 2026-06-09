# Broker::BrokerBase::OnEventDeleted(_GUID const &)

- ea: `0x18001854c`
- end: `0x1800185ed`
- name: `?OnEventDeleted@BrokerBase@Broker@@AEAAXAEBU_GUID@@@Z`
- size: `161`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180019010`

## callees

- `0x180004ae0`
- `0x180005b90`
- `0x180009d9c`
- `0x1800183bc`
- `0x18001854c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BrokerBase::OnEventDeleted(Broker::BrokerBase *this, const struct _GUID *a2, int a3)
{
  __int64 v5; // r9
  Broker::Win32Error *v6; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+38h] [rbp-20h] BYREF
  std::_Ref_count_base *v8; // [rsp+40h] [rbp-18h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, a3, *((_QWORD *)this + 1), (__int64)a2);
  try
  {
    Broker::BrokeredEventTable::Find((__int64)this + 208, &v7, a2);
    if ( !*(_QWORD *)(*(_QWORD *)(v7 + 16) + 16LL) )
      Broker::BrokerBase::DestroyEvent((__int64)this, 4u, &v7, v5);
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
  }
  catch ( Broker::NotFound )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, a2);
    return;
  }
  catch ( Broker::Win32Error *v6 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF__guid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
        a2,
        *((_DWORD *)v6 + 8));
  }
}

```

## disassembly

```asm
0x18001854c  mov     [rsp+arg_0], rbx
0x180018551  mov     [rsp+arg_8], rdx
0x180018556  push    rdi
0x180018557  sub     rsp, 50h
0x18001855b  mov     rbx, rdx
0x18001855e  mov     rdi, rcx
0x180018561  mov     rcx, cs:WPP_GLOBAL_Control
0x180018568  test    dword ptr [rcx+1Ch], 800h
0x18001856f  jz      short loc_18001858F
0x180018571  cmp     byte ptr [rcx+19h], 5
0x180018575  jb      short loc_18001858F
0x180018577  mov     edx, 3Ch ; '<'
0x18001857c  mov     [rsp+58h+var_38], rbx
0x180018581  mov     r9, [rdi+8]
0x180018585  mov     rcx, [rcx+10h]
0x180018589  call    WPP_SF__guid__guid_
0x18001858e  nop
0x18001858f  lea     rcx, [rdi+0D0h]
0x180018596  mov     r8, rbx
0x180018599  lea     rdx, [rsp+58h+var_20]
0x18001859e  call    ?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokeredEventTable::Find(_GUID const &)
0x1800185a3  nop
0x1800185a4  mov     rax, [rsp+58h+var_20]
0x1800185a9  mov     rax, [rax+10h]
0x1800185ad  mov     rax, [rax+10h]
0x1800185b1  test    eax, eax
0x1800185b3  jnz     short loc_1800185CE
0x1800185b5  shr     rax, 20h
0x1800185b9  test    eax, eax
0x1800185bb  jnz     short loc_1800185CE
0x1800185bd  lea     r8, [rsp+58h+var_20]
0x1800185c2  lea     edx, [rax+4]
0x1800185c5  mov     rcx, rdi
0x1800185c8  call    ?DestroyEvent@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEAV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::DestroyEvent(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> &)
0x1800185cd  nop
0x1800185ce  mov     rcx, [rsp+58h+var_18]; this
0x1800185d3  test    rcx, rcx
0x1800185d6  jz      short loc_1800185DE
0x1800185d8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800185dd  nop
0x1800185de  jmp     short loc_1800185E2
0x1800185e0  jmp     short $+2
0x1800185e2  mov     rbx, [rsp+58h+arg_0]
0x1800185e7  add     rsp, 50h
0x1800185eb  pop     rdi
0x1800185ec  retn
```
