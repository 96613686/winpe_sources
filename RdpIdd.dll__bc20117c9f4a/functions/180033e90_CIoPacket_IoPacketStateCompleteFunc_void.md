# CIoPacket::IoPacketStateCompleteFunc(void)

- ea: `0x180033e90`
- end: `0x18003403d`
- name: `?IoPacketStateCompleteFunc@CIoPacket@@AEAA?AW4IOPACKET_STATE@@XZ`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005d04`
- `0x18000d614`
- `0x180033e90`
- `0x180035e7c`
- `0x18003f010`

## string_xrefs

- `0x180033ed7`: `IoPacketStateComplete`
- `0x180033ee2`: `CIoPacket::IoPacketStateCompleteFunc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIoPacket::IoPacketStateCompleteFunc(__int64 a1)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  _QWORD *v5; // rdi
  _QWORD *v6; // r14
  _QWORD *i; // rsi
  __int64 v8; // rcx
  __int64 v9; // rcx
  const char *v11; // [rsp+60h] [rbp-20h] BYREF
  const char *v12; // [rsp+68h] [rbp-18h] BYREF
  const char *v13; // [rsp+70h] [rbp-10h] BYREF
  int v14; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v15; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v16; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v17; // [rsp+C8h] [rbp+48h] BYREF

  v2 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  v5 = (_QWORD *)(a1 + 64);
  if ( *v2 > 5u )
  {
    v15 = (__int64)(*(_QWORD *)(a1 + 72) - *(_QWORD *)(a1 + 64)) >> 5;
    v16 = *(_QWORD *)(a1 + 32);
    v17 = a1;
    v11 = "IoPacketStateComplete";
    v12 = "CIoPacket::IoPacketStateCompleteFunc";
    v14 = 1883;
    v13 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (_DWORD)v2,
      (unsigned int)&byte_18004FDE7,
      v3,
      v4,
      (__int64)&v13,
      (__int64)&v14,
      (__int64)&v12,
      (__int64)&v11,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v15);
  }
  v6 = *(_QWORD **)(a1 + 72);
  for ( i = (_QWORD *)*v5; i != v6; i += 4 )
  {
    if ( *i )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(WdfFunctions_02025 + 1312))(
        WdfDriverGlobals,
        *i,
        0,
        i[3]);
      *i = 0;
    }
  }
  *(_DWORD *)(*(_QWORD *)(a1 + 24) + 372LL) -= *(_DWORD *)(a1 + 188);
  *(_DWORD *)(a1 + 188) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  if ( *(_QWORD *)(a1 + 64) != *(_QWORD *)(a1 + 72) )
    *(_QWORD *)(a1 + 72) = *v5;
  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void _aligned_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::reset(
    a1 + 96,
    0);
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_WORD *)(a1 + 192) = 1;
  v8 = *(_QWORD *)(a1 + 56);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v8 + 24LL))(
      v8,
      a1,
      0,
      *(unsigned int *)(a1 + 40),
      *(_QWORD *)(a1 + 48));
    v9 = *(_QWORD *)(a1 + 56);
    *(_QWORD *)(a1 + 56) = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return 7;
}

```

## disassembly

```asm
0x180033e90  push    rbp
0x180033e92  push    rbx
0x180033e93  push    rsi
0x180033e94  push    rdi
0x180033e95  push    r14
0x180033e97  mov     rbp, rsp
0x180033e9a  sub     rsp, 80h
0x180033ea1  mov     rbx, rcx
0x180033ea4  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180033ea9  mov     rcx, [rax+8]
0x180033ead  mov     eax, [rcx]
0x180033eaf  lea     rdi, [rbx+40h]
0x180033eb3  cmp     eax, 5
0x180033eb6  jbe     loc_180033F4A
0x180033ebc  mov     rax, [rdi+8]
0x180033ec0  sub     rax, [rdi]
0x180033ec3  sar     rax, 5
0x180033ec7  mov     [rbp+arg_8], rax
0x180033ecb  mov     rax, [rbx+20h]
0x180033ecf  mov     [rbp+arg_10], rax
0x180033ed3  mov     [rbp+arg_18], rbx
0x180033ed7  lea     rax, aIopacketstatec_3; "IoPacketStateComplete"
0x180033ede  mov     [rbp+var_20], rax
0x180033ee2  lea     rax, aCiopacketIopac_0; "CIoPacket::IoPacketStateCompleteFunc"
0x180033ee9  mov     [rbp+var_18], rax
0x180033eed  mov     [rbp+arg_0], 75Bh
0x180033ef4  lea     rax, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180033efb  mov     [rbp+var_10], rax
0x180033eff  lea     rax, [rbp+arg_8]
0x180033f03  mov     [rsp+80h+var_30], rax
0x180033f08  lea     rax, [rbp+arg_10]
0x180033f0c  mov     [rsp+80h+var_38], rax
0x180033f11  lea     rax, [rbp+arg_18]
0x180033f15  mov     [rsp+80h+var_40], rax
0x180033f1a  lea     rax, [rbp+var_20]
0x180033f1e  mov     [rsp+80h+var_48], rax
0x180033f23  lea     rax, [rbp+var_18]
0x180033f27  mov     [rsp+80h+var_50], rax
0x180033f2c  lea     rax, [rbp+arg_0]
0x180033f30  mov     [rsp+80h+var_58], rax
0x180033f35  lea     rax, [rbp+var_10]
0x180033f39  mov     [rsp+80h+var_60], rax
0x180033f3e  lea     rdx, byte_18004FDE7
0x180033f45  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180033f4a  mov     r14, [rdi+8]
0x180033f4e  mov     rsi, [rdi]
0x180033f51  jmp     short loc_180033F87
0x180033f53  mov     rdx, [rsi]
0x180033f56  test    rdx, rdx
0x180033f59  jz      short loc_180033F83
0x180033f5b  mov     rax, cs:WdfFunctions_02025
0x180033f62  mov     r9, [rsi+18h]
0x180033f66  xor     r8d, r8d
0x180033f69  mov     rcx, cs:WdfDriverGlobals
0x180033f70  mov     rax, [rax+520h]
0x180033f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f7c  mov     qword ptr [rsi], 0
0x180033f83  add     rsi, 20h ; ' '
0x180033f87  cmp     rsi, r14
0x180033f8a  jnz     short loc_180033F53
0x180033f8c  mov     rcx, [rbx+18h]
0x180033f90  mov     eax, [rbx+0BCh]
0x180033f96  sub     [rcx+174h], eax
0x180033f9c  mov     dword ptr [rbx+0BCh], 0
0x180033fa6  mov     qword ptr [rbx+88h], 0
0x180033fb1  mov     rax, [rdi]
0x180033fb4  cmp     rax, [rdi+8]
0x180033fb8  jz      short loc_180033FBE
0x180033fba  mov     [rdi+8], rax
0x180033fbe  lea     rcx, [rbx+60h]
0x180033fc2  xor     edx, edx
0x180033fc4  call    ?reset@?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?_aligned_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAAXPEAE@Z; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&_aligned_free(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::reset(uchar *)
0x180033fc9  mov     qword ptr [rbx+78h], 0
0x180033fd1  mov     qword ptr [rbx+70h], 0
0x180033fd9  mov     word ptr [rbx+0C0h], 1
0x180033fe2  mov     rcx, [rbx+38h]
0x180033fe6  test    rcx, rcx
0x180033fe9  jz      short loc_180034029
0x180033feb  mov     rax, [rcx]
0x180033fee  mov     rdx, [rbx+30h]
0x180033ff2  mov     [rsp+80h+var_60], rdx
0x180033ff7  mov     r9d, [rbx+28h]
0x180033ffb  xor     r8d, r8d
0x180033ffe  mov     rdx, rbx
0x180034001  mov     rax, [rax+18h]
0x180034005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003400a  nop
0x18003400b  mov     rcx, [rbx+38h]
0x18003400f  mov     qword ptr [rbx+38h], 0
0x180034017  test    rcx, rcx
0x18003401a  jz      short loc_180034029
0x18003401c  mov     rax, [rcx]
0x18003401f  mov     rax, [rax+10h]
0x180034023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034028  nop
0x180034029  mov     eax, 7
0x18003402e  add     rsp, 80h
0x180034035  pop     r14
0x180034037  pop     rdi
0x180034038  pop     rsi
0x180034039  pop     rbx
0x18003403a  pop     rbp
0x18003403b  retn
```
