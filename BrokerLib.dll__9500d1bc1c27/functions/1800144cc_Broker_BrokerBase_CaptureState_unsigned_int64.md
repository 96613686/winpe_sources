# Broker::BrokerBase::CaptureState(unsigned __int64)

- ea: `0x1800144cc`
- end: `0x180014552`
- name: `?CaptureState@BrokerBase@Broker@@SAX_K@Z`
- size: `134`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f590`

## callees

- `0x180005070`
- `0x18000b3a4`
- `0x1800144cc`
- `0x180014558`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18001454b`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800144ed`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800144ed`

## pseudocode

```c
void __fastcall Broker::BrokerBase::CaptureState(unsigned __int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  WPP_SF_(a1, 12, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids);
  RtlAcquireSRWLockShared(&Broker::g_BrokersLock);
  v2 = Broker::g_Brokers;
  v3 = *(_QWORD *)Broker::g_Brokers;
  v4 = *(_QWORD *)Broker::g_Brokers;
  while ( v3 != v2 )
  {
    Broker::BrokerBase::Dump(*(struct _RTL_SRWLOCK **)(v3 + 48), a1);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(&v4);
    v2 = Broker::g_Brokers;
    v3 = v4;
  }
  WPP_SF_(a1, 13, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids);
  RtlReleaseSRWLockShared(&Broker::g_BrokersLock);
}

```

## disassembly

```asm
0x1800144cc  push    rbx
0x1800144ce  sub     rsp, 20h
0x1800144d2  mov     rbx, rcx
0x1800144d5  mov     edx, 0Ch
0x1800144da  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x1800144e1  call    WPP_SF_
0x1800144e6  lea     rcx, ?g_BrokersLock@Broker@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Broker::g_BrokersLock
0x1800144ed  call    cs:__imp_RtlAcquireSRWLockShared
0x1800144f3  mov     rax, cs:?g_Brokers@Broker@@3V?$map@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@@std@@A; std::map<_GUID,std::shared_ptr<Broker::BrokerBase>> Broker::g_Brokers
0x1800144fa  mov     rcx, [rax]
0x1800144fd  mov     [rsp+28h+arg_8], rcx
0x180014502  cmp     rcx, rax
0x180014505  jz      short loc_18001452B
0x180014507  mov     rcx, [rcx+30h]; this
0x18001450b  mov     rdx, rbx; unsigned __int64
0x18001450e  call    ?Dump@BrokerBase@Broker@@QEAAX_K@Z; Broker::BrokerBase::Dump(unsigned __int64)
0x180014513  lea     rcx, [rsp+28h+arg_8]
0x180014518  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAU_BROKERED_EVENT@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_BROKERED_EVENT * const,std::shared_ptr<Broker::BrokerEvent>>>>,std::_Iterator_base0>::operator++(void)
0x18001451d  mov     rax, cs:?g_Brokers@Broker@@3V?$map@U_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerBase@Broker@@@std@@@std@@@3@@std@@A; std::map<_GUID,std::shared_ptr<Broker::BrokerBase>> Broker::g_Brokers
0x180014524  mov     rcx, [rsp+28h+arg_8]
0x180014529  jmp     short loc_180014502
0x18001452b  mov     edx, 0Dh
0x180014530  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180014537  mov     rcx, rbx
0x18001453a  call    WPP_SF_
0x18001453f  lea     rcx, ?g_BrokersLock@Broker@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Broker::g_BrokersLock
0x180014546  add     rsp, 20h
0x18001454a  pop     rbx
0x18001454b  jmp     cs:__imp_RtlReleaseSRWLockShared
```
