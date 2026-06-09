# CIoPacket::IoPacketStateCompleteCommittedIrpFunc(void)

- ea: `0x180033d30`
- end: `0x180033e83`
- name: `?IoPacketStateCompleteCommittedIrpFunc@CIoPacket@@AEAA?AW4IOPACKET_STATE@@XZ`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005d04`
- `0x18000d614`
- `0x180033d30`
- `0x18003f010`

## string_xrefs

- `0x180033d7a`: `IoPacketStateCompleteCommittedIrp`
- `0x180033d85`: `CIoPacket::IoPacketStateCompleteCommittedIrpFunc`

## pseudocode

```c
__int64 __fastcall CIoPacket::IoPacketStateCompleteCommittedIrpFunc(__int64 a1)
{
  _QWORD *v2; // rbx
  _DWORD *v3; // rcx
  int v4; // r8d
  int v5; // r9d
  _QWORD *v6; // r14
  _QWORD *v7; // rdi
  __int64 v8; // r8
  const char *v10; // [rsp+60h] [rbp-20h] BYREF
  const char *v11; // [rsp+68h] [rbp-18h] BYREF
  const char *v12; // [rsp+70h] [rbp-10h] BYREF
  int v13; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v14; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v15; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v16; // [rsp+C8h] [rbp+48h] BYREF

  v2 = (_QWORD *)(a1 + 64);
  v3 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v3 > 5u )
  {
    v14 = *(_QWORD *)(a1 + 32);
    v15 = (__int64)(*(_QWORD *)(a1 + 72) - *(_QWORD *)(a1 + 64)) >> 5;
    v10 = "IoPacketStateCompleteCommittedIrp";
    v11 = "CIoPacket::IoPacketStateCompleteCommittedIrpFunc";
    v12 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp";
    v16 = a1;
    v13 = 1817;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (_DWORD)v3,
      (unsigned int)qword_18004FE40,
      v4,
      v5,
      (__int64)&v12,
      (__int64)&v13,
      (__int64)&v11,
      (__int64)&v10,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v14);
  }
  v6 = *(_QWORD **)(a1 + 72);
  v7 = (_QWORD *)*v2;
  if ( (_QWORD *)*v2 != v6 )
  {
    do
    {
      if ( *v7 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 24) + 376LL) == 2 )
          v8 = 261;
        else
          v8 = 0;
        (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(WdfFunctions_02025 + 1312))(
          WdfDriverGlobals,
          *v7,
          v8,
          v7[3]);
        *v7 = 0;
      }
      v7 += 4;
    }
    while ( v7 != v6 );
    v2 = (_QWORD *)(a1 + 64);
  }
  *(_DWORD *)(*(_QWORD *)(a1 + 24) + 372LL) -= *(_DWORD *)(a1 + 188);
  *(_DWORD *)(a1 + 188) = 0;
  if ( *v2 != v2[1] )
    v2[1] = *v2;
  return 2;
}

```

## disassembly

```asm
0x180033d30  push    rbp
0x180033d32  push    rbx
0x180033d33  push    rsi
0x180033d34  push    rdi
0x180033d35  push    r14
0x180033d37  mov     rbp, rsp
0x180033d3a  sub     rsp, 80h
0x180033d41  mov     rsi, rcx
0x180033d44  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180033d49  lea     rbx, [rsi+40h]
0x180033d4d  mov     rcx, [rax+8]
0x180033d51  mov     eax, [rcx]
0x180033d53  cmp     eax, 5
0x180033d56  jbe     loc_180033DEA
0x180033d5c  mov     rax, [rsi+20h]
0x180033d60  lea     rdx, qword_18004FE40
0x180033d67  mov     [rbp+arg_8], rax
0x180033d6b  mov     rax, [rbx+8]
0x180033d6f  sub     rax, [rbx]
0x180033d72  sar     rax, 5
0x180033d76  mov     [rbp+arg_10], rax
0x180033d7a  lea     rax, aIopacketstatec_0; "IoPacketStateCompleteCommittedIrp"
0x180033d81  mov     [rbp+var_20], rax
0x180033d85  lea     rax, aCiopacketIopac_1; "CIoPacket::IoPacketStateCompleteCommitt"...
0x180033d8c  mov     [rbp+var_18], rax
0x180033d90  lea     rax, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180033d97  mov     [rbp+var_10], rax
0x180033d9b  lea     rax, [rbp+arg_8]
0x180033d9f  mov     [rsp+80h+var_30], rax
0x180033da4  lea     rax, [rbp+arg_10]
0x180033da8  mov     [rsp+80h+var_38], rax
0x180033dad  lea     rax, [rbp+arg_18]
0x180033db1  mov     [rsp+80h+var_40], rax
0x180033db6  lea     rax, [rbp+var_20]
0x180033dba  mov     [rsp+80h+var_48], rax
0x180033dbf  lea     rax, [rbp+var_18]
0x180033dc3  mov     [rsp+80h+var_50], rax
0x180033dc8  lea     rax, [rbp+arg_0]
0x180033dcc  mov     [rsp+80h+var_58], rax
0x180033dd1  lea     rax, [rbp+var_10]
0x180033dd5  mov     [rsp+80h+var_60], rax
0x180033dda  mov     [rbp+arg_18], rsi
0x180033dde  mov     [rbp+arg_0], 719h
0x180033de5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180033dea  mov     r14, [rbx+8]
0x180033dee  mov     rdi, [rbx]
0x180033df1  cmp     rdi, r14
0x180033df4  jz      short loc_180033E48
0x180033df6  mov     rdx, [rdi]
0x180033df9  test    rdx, rdx
0x180033dfc  jz      short loc_180033E3B
0x180033dfe  mov     rax, [rsi+18h]
0x180033e02  mov     r9, [rdi+18h]
0x180033e06  mov     rcx, cs:WdfDriverGlobals
0x180033e0d  cmp     dword ptr [rax+178h], 2
0x180033e14  mov     rax, cs:WdfFunctions_02025
0x180033e1b  mov     rax, [rax+520h]
0x180033e22  jnz     short loc_180033E2C
0x180033e24  mov     r8d, 105h
0x180033e2a  jmp     short loc_180033E2F
0x180033e2c  xor     r8d, r8d
0x180033e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e34  mov     qword ptr [rdi], 0
0x180033e3b  add     rdi, 20h ; ' '
0x180033e3f  cmp     rdi, r14
0x180033e42  jnz     short loc_180033DF6
0x180033e44  lea     rbx, [rsi+40h]
0x180033e48  mov     ecx, [rsi+0BCh]
0x180033e4e  mov     rdx, [rsi+18h]
0x180033e52  sub     [rdx+174h], ecx
0x180033e58  mov     dword ptr [rsi+0BCh], 0
0x180033e62  mov     rcx, [rbx]
0x180033e65  cmp     rcx, [rbx+8]
0x180033e69  jz      short loc_180033E6F
0x180033e6b  mov     [rbx+8], rcx
0x180033e6f  mov     eax, 2
0x180033e74  add     rsp, 80h
0x180033e7b  pop     r14
0x180033e7d  pop     rdi
0x180033e7e  pop     rsi
0x180033e7f  pop     rbx
0x180033e80  pop     rbp
0x180033e81  retn
```
