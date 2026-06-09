# Broker::SebBroker::CreateInstance(ushort *)

- ea: `0x18001c100`
- end: `0x18001c173`
- name: `?CreateInstance@SebBroker@Broker@@SAXPEAG@Z`
- size: `115`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001df48`

## callees

- `0x180005a50`
- `0x1800076a0`
- `0x180017120`
- `0x18001c100`
- `0x18001c17c`
- `0x18001c228`
- `0x18001c8e4`

## pseudocode

```c
void __fastcall Broker::SebBroker::CreateInstance(unsigned __int16 *a1)
{
  __int64 *v1; // rax
  unsigned __int16 *v2; // rdx
  __int64 v3; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v4; // [rsp+28h] [rbp-10h]

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  TlgRegisterAggregateProviderEx(&dword_180035050);
  v1 = std::make_shared<Broker::SebBroker,>(&v3);
  std::shared_ptr<CBroker::SebBroker>::operator=(&Broker::SebBroker::Instance, v1);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  try
  {
    Broker::SebBroker::Initialize(Broker::SebBroker::Instance, v2);
  }
  catch ( ... )
  {
    std::shared_ptr<Broker::SebBroker>::reset();
    throw;
  }
}

```

## disassembly

```asm
0x18001c100  sub     rsp, 38h
0x18001c104  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c10b  test    byte ptr [rcx+1Ch], 1
0x18001c10f  jz      short loc_18001C12C
0x18001c111  cmp     byte ptr [rcx+19h], 4
0x18001c115  jb      short loc_18001C12C
0x18001c117  mov     edx, 0Bh
0x18001c11c  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001c123  mov     rcx, [rcx+10h]
0x18001c127  call    WPP_SF_
0x18001c12c  lea     rcx, dword_180035050; CallbackContext
0x18001c133  call    TlgRegisterAggregateProviderEx
0x18001c138  lea     rcx, [rsp+38h+var_18]
0x18001c13d  call    ??$make_shared@VSebBroker@Broker@@$$V@std@@YA?AV?$shared_ptr@VSebBroker@Broker@@@0@XZ; std::make_shared<Broker::SebBroker,>(void)
0x18001c142  mov     rdx, rax
0x18001c145  lea     rcx, ?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; std::shared_ptr<Broker::SebBroker> Broker::SebBroker::Instance
0x18001c14c  call    ??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)
0x18001c151  mov     rcx, [rsp+38h+var_10]; this
0x18001c156  test    rcx, rcx
0x18001c159  jz      short loc_18001C161
0x18001c15b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c160  nop
0x18001c161  mov     rcx, qword ptr cs:?Instance@SebBroker@Broker@@0V?$shared_ptr@VSebBroker@Broker@@@std@@A; this
0x18001c168  call    ?Initialize@SebBroker@Broker@@QEAAXPEAG@Z; Broker::SebBroker::Initialize(ushort *)
0x18001c16d  nop
0x18001c16e  add     rsp, 38h
0x18001c172  retn
```
