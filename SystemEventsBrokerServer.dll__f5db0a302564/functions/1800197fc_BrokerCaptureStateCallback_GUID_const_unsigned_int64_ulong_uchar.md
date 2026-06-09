# BrokerCaptureStateCallback(_GUID const *,unsigned __int64,ulong,uchar)

- ea: `0x1800197fc`
- end: `0x1800198d7`
- name: `?BrokerCaptureStateCallback@@YAXPEBU_GUID@@_KKE@Z`
- size: `219`
- prototype: `void __fastcall(const struct _GUID *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800159d0`

## callees

- `0x180002680`
- `0x1800076a0`
- `0x180012a80`
- `0x180017120`
- `0x1800197fc`
- `0x1800198e0`
- `0x180019b60`

## pseudocode

```c
void __fastcall BrokerCaptureStateCallback(const struct _GUID *a1, unsigned __int64 a2)
{
  __int64 v4; // r9
  __int64 v5; // rax
  __int64 *Instance; // rax
  __int64 v7; // rax
  std::_Ref_count_base *v8[2]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v9[8]; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v10; // [rsp+38h] [rbp-10h]

  v4 = WPP_ThisDir_CTLGUID_BrokerCommon;
  v5 = *(_QWORD *)&a1->Data1 - WPP_ThisDir_CTLGUID_BrokerCommon;
  if ( *(_QWORD *)&a1->Data1 == WPP_ThisDir_CTLGUID_BrokerCommon )
    v5 = *(_QWORD *)a1->Data4 + 0x5752B75E582E7C56LL;
  if ( !v5 )
  {
    *(_OWORD *)v8 = 0;
    Instance = (__int64 *)Broker::SebBroker::GetInstance(v9, a2, 0xA8AD48A1A7D183AAuLL);
    std::shared_ptr<CBroker::SebBroker>::operator=(v8, Instance);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
    if ( v8[0] )
      Broker::SebBroker::Dump(v8[0], a2);
    if ( v8[1] )
      std::_Ref_count_base::_Decref(v8[1]);
    v4 = WPP_ThisDir_CTLGUID_BrokerCommon;
  }
  v7 = *(_QWORD *)&a1->Data1 - v4;
  if ( *(_QWORD *)&a1->Data1 == v4 )
    v7 = *(_QWORD *)a1->Data4 + 0x5752B75E582E7C56LL;
  if ( !v7 )
  {
    CBroker::SebBroker::GetInstance(v8);
    if ( v8[0] )
      CBroker::SebBroker::Dump(v8[0], a2);
    if ( v8[1] )
      std::_Ref_count_base::_Decref(v8[1]);
  }
}

```

## disassembly

```asm
0x1800197fc  mov     [rsp+arg_0], rbx
0x180019801  push    rdi
0x180019802  sub     rsp, 40h
0x180019806  mov     rdi, rdx
0x180019809  mov     rbx, rcx
0x18001980c  mov     rax, [rcx]
0x18001980f  mov     r9, cs:WPP_ThisDir_CTLGUID_BrokerCommon
0x180019816  mov     r8, cs:qword_18002A930
0x18001981d  sub     rax, r9
0x180019820  jnz     short loc_180019829
0x180019822  mov     rax, [rcx+8]
0x180019826  sub     rax, r8
0x180019829  test    rax, rax
0x18001982c  jnz     short loc_18001988D
0x18001982e  xorps   xmm0, xmm0
0x180019831  movdqu  xmmword ptr [rsp+48h+var_28], xmm0
0x180019837  lea     rcx, [rsp+48h+var_18]
0x18001983c  call    ?GetInstance@SebBroker@Broker@@SA?AV?$shared_ptr@VSebBroker@Broker@@@std@@XZ; Broker::SebBroker::GetInstance(void)
0x180019841  mov     rdx, rax
0x180019844  lea     rcx, [rsp+48h+var_28]
0x180019849  call    ??4?$shared_ptr@VSebBroker@CBroker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CBroker::SebBroker>::operator=(std::shared_ptr<CBroker::SebBroker> &&)
0x18001984e  mov     rcx, [rsp+48h+var_10]; this
0x180019853  test    rcx, rcx
0x180019856  jz      short loc_18001985D
0x180019858  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001985d  mov     rcx, [rsp+48h+var_28]; this
0x180019862  test    rcx, rcx
0x180019865  jz      short loc_180019870
0x180019867  mov     rdx, rdi; unsigned __int64
0x18001986a  call    ?Dump@SebBroker@Broker@@QEAAX_K@Z; Broker::SebBroker::Dump(unsigned __int64)
0x18001986f  nop
0x180019870  mov     rcx, [rsp+48h+var_28+8]; this
0x180019875  test    rcx, rcx
0x180019878  jz      short loc_18001987F
0x18001987a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001987f  mov     r8, cs:qword_18002A930
0x180019886  mov     r9, cs:WPP_ThisDir_CTLGUID_BrokerCommon
0x18001988d  mov     rax, [rbx]
0x180019890  sub     rax, r9
0x180019893  jnz     short loc_18001989C
0x180019895  mov     rax, [rbx+8]
0x180019899  sub     rax, r8
0x18001989c  test    rax, rax
0x18001989f  jnz     short loc_1800198CC
0x1800198a1  lea     rcx, [rsp+48h+var_28]
0x1800198a6  call    ?GetInstance@SebBroker@CBroker@@SA?AV?$shared_ptr@VSebBroker@CBroker@@@std@@XZ; CBroker::SebBroker::GetInstance(void)
0x1800198ab  mov     rcx, [rsp+48h+var_28]; this
0x1800198b0  test    rcx, rcx
0x1800198b3  jz      short loc_1800198BD
0x1800198b5  mov     rdx, rdi; unsigned __int64
0x1800198b8  call    ?Dump@SebBroker@CBroker@@QEAAX_K@Z; CBroker::SebBroker::Dump(unsigned __int64)
0x1800198bd  mov     rcx, [rsp+48h+var_28+8]; this
0x1800198c2  test    rcx, rcx
0x1800198c5  jz      short loc_1800198CC
0x1800198c7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800198cc  mov     rbx, [rsp+48h+arg_0]
0x1800198d1  add     rsp, 40h
0x1800198d5  pop     rdi
0x1800198d6  retn
```
