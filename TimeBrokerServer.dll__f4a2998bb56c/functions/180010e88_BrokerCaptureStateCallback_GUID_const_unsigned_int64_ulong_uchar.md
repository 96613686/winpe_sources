# BrokerCaptureStateCallback(_GUID const *,unsigned __int64,ulong,uchar)

- ea: `0x180010e88`
- end: `0x180010f04`
- name: `?BrokerCaptureStateCallback@@YAXPEBU_GUID@@_KKE@Z`
- size: `124`
- prototype: `void __fastcall(const struct _GUID *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e650`

## callees

- `0x180004e18`
- `0x180005b30`
- `0x18000bd30`
- `0x180010e88`
- `0x180010f0c`

## pseudocode

```c
void __fastcall BrokerCaptureStateCallback(const struct _GUID *a1, unsigned __int64 a2)
{
  __int64 v3; // rax
  __int64 *Instance; // rax
  std::_Ref_count_base *v5[2]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v6[8]; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v7; // [rsp+38h] [rbp-10h]

  v3 = *(_QWORD *)&a1->Data1 - WPP_ThisDir_CTLGUID_BrokerCommon;
  if ( *(_QWORD *)&a1->Data1 == WPP_ThisDir_CTLGUID_BrokerCommon )
    v3 = *(_QWORD *)a1->Data4 + 0x5752B75E582E7C56LL;
  if ( !v3 )
  {
    *(_OWORD *)v5 = 0;
    Instance = (__int64 *)Broker::TimeBroker::GetInstance(v6);
    std::shared_ptr<Broker::SystemTimer>::operator=(v5, Instance);
    if ( v7 )
      std::_Ref_count_base::_Decref(v7);
    if ( v5[0] )
      Broker::TimeBroker::Dump(v5[0], a2);
    if ( v5[1] )
      std::_Ref_count_base::_Decref(v5[1]);
  }
}

```

## disassembly

```asm
0x180010e88  push    rbx
0x180010e8a  sub     rsp, 40h
0x180010e8e  mov     rbx, rdx
0x180010e91  mov     rax, [rcx]
0x180010e94  sub     rax, cs:WPP_ThisDir_CTLGUID_BrokerCommon
0x180010e9b  jnz     short loc_180010EA8
0x180010e9d  mov     rax, [rcx+8]
0x180010ea1  sub     rax, cs:qword_18001F018
0x180010ea8  test    rax, rax
0x180010eab  jnz     short loc_180010EFE
0x180010ead  xorps   xmm0, xmm0
0x180010eb0  movdqu  xmmword ptr [rsp+48h+var_28], xmm0
0x180010eb6  lea     rcx, [rsp+48h+var_18]
0x180010ebb  call    ?GetInstance@TimeBroker@Broker@@SA?AV?$shared_ptr@VTimeBroker@Broker@@@std@@XZ; Broker::TimeBroker::GetInstance(void)
0x180010ec0  mov     rdx, rax
0x180010ec3  lea     rcx, [rsp+48h+var_28]
0x180010ec8  call    ??4?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::SystemTimer>::operator=(std::shared_ptr<Broker::SystemTimer> &&)
0x180010ecd  mov     rcx, [rsp+48h+var_10]; this
0x180010ed2  test    rcx, rcx
0x180010ed5  jz      short loc_180010EDC
0x180010ed7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010edc  mov     rcx, [rsp+48h+var_28]; this
0x180010ee1  test    rcx, rcx
0x180010ee4  jz      short loc_180010EEF
0x180010ee6  mov     rdx, rbx; unsigned __int64
0x180010ee9  call    ?Dump@TimeBroker@Broker@@QEAAX_K@Z; Broker::TimeBroker::Dump(unsigned __int64)
0x180010eee  nop
0x180010eef  mov     rcx, [rsp+48h+var_28+8]; this
0x180010ef4  test    rcx, rcx
0x180010ef7  jz      short loc_180010EFE
0x180010ef9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010efe  add     rsp, 40h
0x180010f02  pop     rbx
0x180010f03  retn
```
