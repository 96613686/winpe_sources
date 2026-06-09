# BrInitializeBrokerInstance2

- ea: `0x1800109f0`
- end: `0x180010aa2`
- name: `BrInitializeBrokerInstance2`
- size: `178`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, int (*)(void *, void *))`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004ae0`
- `0x1800058e0`
- `0x180009e94`
- `0x1800109f0`
- `0x180010aa8`
- `0x180010b84`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrInitializeBrokerInstance2(const void *a1, const unsigned __int16 *a2, int (*a3)(void *, void *))
{
  unsigned int v5; // ebx
  Broker::BILayer::Failure *v7; // [rsp+20h] [rbp-28h] BYREF
  Broker::Win32Error *v8; // [rsp+28h] [rbp-20h] BYREF
  Broker::BrokerBase *v9; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v10; // [rsp+38h] [rbp-10h]
  ULONG v11; // [rsp+50h] [rbp+8h]

  v5 = 0;
  if ( !a1 )
  {
    v5 = 87;
LABEL_6:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, v5);
    return v5;
  }
  try
  {
    Broker::BrokerBase::GetInstance(&v9, a1);
    Broker::BrokerBase::InitializeBroker(v9);
    Broker::BrokerBase::StartRpcServer(v9, a2, a3);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
  }
  catch ( std::bad_alloc )
  {
    v5 = 14;
    goto LABEL_6;
  }
  catch ( Broker::InvalidParameter )
  {
    v5 = 87;
    goto LABEL_6;
  }
  catch ( Broker::AccessDenied )
  {
    v5 = 5;
    goto LABEL_6;
  }
  catch ( Broker::BILayer::Failure *v7 )
  {
    v11 = RtlNtStatusToDosError(*((_DWORD *)v7 + 8));
    goto LABEL_5;
  }
  catch ( Broker::Win32Error *v8 )
  {
    v11 = *((_DWORD *)v8 + 8);
LABEL_5:
    v5 = v11;
    if ( !v11 )
      return v5;
    goto LABEL_6;
  }
  catch ( ... )
  {
    v5 = 1287;
    goto LABEL_6;
  }
  return v5;
}

```

## disassembly

```asm
0x1800109f0  mov     [rsp+arg_8], rbx
0x1800109f5  mov     [rsp+arg_10], rsi
0x1800109fa  push    rdi
0x1800109fb  sub     rsp, 40h
0x1800109ff  mov     rdi, r8
0x180010a02  mov     rsi, rdx
0x180010a05  xor     ebx, ebx
0x180010a07  test    rcx, rcx
0x180010a0a  jnz     short loc_180010A11
0x180010a0c  lea     ebx, [rcx+57h]
0x180010a0f  jmp     short loc_180010A62
0x180010a11  mov     rdx, rcx
0x180010a14  lea     rcx, [rsp+48h+var_18]
0x180010a19  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x180010a1e  nop
0x180010a1f  mov     rcx, [rsp+48h+var_18]; this
0x180010a24  call    ?InitializeBroker@BrokerBase@Broker@@QEAAXXZ; Broker::BrokerBase::InitializeBroker(void)
0x180010a29  mov     r8, rdi; int (*)(void *, void *)
0x180010a2c  mov     rdx, rsi; unsigned __int16 *
0x180010a2f  mov     rcx, [rsp+48h+var_18]; this
0x180010a34  call    ?StartRpcServer@BrokerBase@Broker@@QEAAXPEBGP6AJPEAX1@Z@Z; Broker::BrokerBase::StartRpcServer(ushort const *,long (*)(void *,void *))
0x180010a39  nop
0x180010a3a  mov     rcx, [rsp+48h+var_10]; this
0x180010a3f  test    rcx, rcx
0x180010a42  jz      short loc_180010A4A
0x180010a44  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010a49  nop
0x180010a4a  jmp     short loc_180010A90
0x180010a4c  jmp     short loc_180010A5E
0x180010a4e  jmp     short loc_180010A5E
0x180010a50  jmp     short loc_180010A5E
0x180010a52  jmp     short $+2
0x180010a54  mov     ebx, [rsp+48h+arg_0]
0x180010a58  test    ebx, ebx
0x180010a5a  jnz     short loc_180010A62
0x180010a5c  jmp     short loc_180010A90
0x180010a5e  mov     ebx, [rsp+48h+arg_0]
0x180010a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a69  test    dword ptr [rcx+1Ch], 800h
0x180010a70  jz      short loc_180010A90
0x180010a72  cmp     byte ptr [rcx+19h], 2
0x180010a76  jb      short loc_180010A90
0x180010a78  mov     edx, 0Dh
0x180010a7d  mov     r9d, ebx
0x180010a80  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x180010a87  mov     rcx, [rcx+10h]
0x180010a8b  call    WPP_SF_d
0x180010a90  mov     eax, ebx
0x180010a92  mov     rbx, [rsp+48h+arg_8]
0x180010a97  mov     rsi, [rsp+48h+arg_10]
0x180010a9c  add     rsp, 40h
0x180010aa0  pop     rdi
0x180010aa1  retn
```
