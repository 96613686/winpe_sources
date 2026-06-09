# CIoPacket::IoPacketStateCommitPendingIrpFunc(void)

- ea: `0x180033b70`
- end: `0x180033d24`
- name: `?IoPacketStateCommitPendingIrpFunc@CIoPacket@@AEAA?AW4IOPACKET_STATE@@XZ`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180005d04`
- `0x180007b20`
- `0x18000d614`
- `0x180031e74`
- `0x180033498`
- `0x180033b70`

## string_xrefs

- `0x180033c63`: `IoPacketStateCommitPendingIrp`
- `0x180033c6e`: `CIoPacket::IoPacketStateCommitPendingIrpFunc`

## pseudocode

```c
__int64 __fastcall CIoPacket::IoPacketStateCommitPendingIrpFunc(_QWORD *a1)
{
  __int64 v1; // rbx
  unsigned __int64 v3; // rax
  _QWORD *v4; // rbx
  CFileIoChannel *v5; // rcx
  __int64 result; // rax
  struct WDFREQUEST__ **v7; // rdx
  struct WDFREQUEST__ *v8; // rcx
  unsigned __int64 v9; // r8
  size_t v10; // rsi
  size_t v11; // r14
  void *v12; // r15
  _DWORD *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  const void *v16; // rdx
  __int64 v17; // [rsp+60h] [rbp-29h] BYREF
  _QWORD *v18; // [rsp+68h] [rbp-21h] BYREF
  const char *v19; // [rsp+70h] [rbp-19h] BYREF
  const char *v20; // [rsp+78h] [rbp-11h] BYREF
  const char *v21; // [rsp+80h] [rbp-9h] BYREF
  _QWORD v22[11]; // [rsp+88h] [rbp-1h] BYREF
  struct WDFREQUEST__ *v23; // [rsp+F0h] [rbp+67h] BYREF
  void *v24; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned __int64 v25; // [rsp+100h] [rbp+77h] BYREF
  size_t v26; // [rsp+108h] [rbp+7Fh] BYREF

  v1 = a1[9];
  if ( a1[8] == v1 || (v3 = *(_QWORD *)(v1 - 16), v4 = (_QWORD *)(v1 - 32), v4[3] >= v3) )
  {
    v5 = (CFileIoChannel *)a1[3];
    v23 = 0;
    v24 = 0;
    v25 = 0;
    if ( !CFileIoChannel::DequeuePendingIrp(v5, &v23, &v24, &v25) )
      return 4;
    v7 = (struct WDFREQUEST__ **)a1[9];
    v8 = (struct WDFREQUEST__ *)v24;
    v9 = v25;
    v22[0] = v23;
    v22[1] = v24;
    v22[2] = v25;
    v22[3] = 0;
    if ( v7 == (struct WDFREQUEST__ **)a1[10] )
    {
      std::vector<CIoPacket::IrpBufferEntry>::_Emplace_reallocate<CIoPacket::IrpBufferEntry const &>(a1 + 8, v7, v22);
    }
    else
    {
      *v7 = v23;
      v7[1] = v8;
      v7[2] = (struct WDFREQUEST__ *)v9;
      v7[3] = 0;
      a1[9] += 32LL;
    }
    v4 = (_QWORD *)(a1[9] - 32LL);
  }
  v10 = a1[12] + a1[14] - a1[15];
  v11 = v4[2] - v4[3];
  v12 = (void *)(v4[3] + v4[1]);
  v13 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v13 > 5u )
  {
    v17 = v4[2];
    v19 = "IoPacketStateCommitPendingIrp";
    v20 = "CIoPacket::IoPacketStateCommitPendingIrpFunc";
    v21 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp";
    v26 = v10;
    v18 = a1;
    LODWORD(v23) = 1721;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      (_DWORD)v13,
      (unsigned int)qword_18004FEE8,
      v14,
      v15,
      (__int64)&v21,
      (__int64)&v23,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v26);
  }
  v16 = (const void *)a1[15];
  if ( v11 >= v10 )
  {
    memcpy_0(v12, v16, v10);
    a1[15] += v10;
    result = 5;
    v4[3] += v10;
  }
  else
  {
    memcpy_0(v12, v16, v11);
    a1[15] += v11;
    v4[3] = v4[2];
    return 3;
  }
  return result;
}

```

## disassembly

```asm
0x180033b70  push    rbp
0x180033b72  push    rbx
0x180033b73  push    rsi
0x180033b74  push    rdi
0x180033b75  push    r14
0x180033b77  push    r15
0x180033b79  lea     rbp, [rsp-2Fh]
0x180033b7e  sub     rsp, 0B8h
0x180033b85  mov     rbx, [rcx+48h]
0x180033b89  mov     rdi, rcx
0x180033b8c  cmp     [rcx+40h], rbx
0x180033b90  jz      short loc_180033BA4
0x180033b92  mov     rax, [rbx-10h]
0x180033b96  add     rbx, 0FFFFFFFFFFFFFFE0h
0x180033b9a  cmp     [rbx+18h], rax
0x180033b9e  jb      loc_180033C24
0x180033ba4  mov     rcx, [rcx+18h]; this
0x180033ba8  lea     r9, [rbp+57h+arg_10]; unsigned __int64 *
0x180033bac  xor     ebx, ebx
0x180033bae  lea     r8, [rbp+57h+arg_8]; void **
0x180033bb2  lea     rdx, [rbp+57h+arg_0]; struct WDFREQUEST__ **
0x180033bb6  mov     [rbp+57h+arg_0], rbx
0x180033bba  mov     [rbp+57h+arg_8], rbx
0x180033bbe  mov     [rbp+57h+arg_10], rbx
0x180033bc2  call    ?DequeuePendingIrp@CFileIoChannel@@QEAA_NPEAPEAUWDFREQUEST__@@PEAPEAXPEA_K@Z; CFileIoChannel::DequeuePendingIrp(WDFREQUEST__ * *,void * *,unsigned __int64 *)
0x180033bc7  test    al, al
0x180033bc9  jnz     short loc_180033BD3
0x180033bcb  lea     eax, [rbx+4]
0x180033bce  jmp     loc_180033D13
0x180033bd3  mov     rdx, [rdi+48h]
0x180033bd7  mov     rax, [rbp+57h+arg_0]
0x180033bdb  mov     rcx, [rbp+57h+arg_8]
0x180033bdf  mov     r8, [rbp+57h+arg_10]
0x180033be3  mov     [rbp+57h+var_58], rax
0x180033be7  mov     [rbp+57h+var_50], rcx
0x180033beb  mov     [rbp+57h+var_48], r8
0x180033bef  mov     [rbp+57h+var_40], rbx
0x180033bf3  cmp     rdx, [rdi+50h]
0x180033bf7  jz      short loc_180033C0F
0x180033bf9  mov     [rdx], rax
0x180033bfc  mov     [rdx+8], rcx
0x180033c00  mov     [rdx+10h], r8
0x180033c04  mov     [rdx+18h], rbx
0x180033c08  add     qword ptr [rdi+48h], 20h ; ' '
0x180033c0d  jmp     short loc_180033C1C
0x180033c0f  lea     r8, [rbp+57h+var_58]
0x180033c13  lea     rcx, [rdi+40h]
0x180033c17  call    ??$_Emplace_reallocate@AEBUIrpBufferEntry@CIoPacket@@@?$vector@UIrpBufferEntry@CIoPacket@@V?$allocator@UIrpBufferEntry@CIoPacket@@@std@@@std@@AEAAPEAUIrpBufferEntry@CIoPacket@@QEAU23@AEBU23@@Z; std::vector<CIoPacket::IrpBufferEntry>::_Emplace_reallocate<CIoPacket::IrpBufferEntry const &>(CIoPacket::IrpBufferEntry * const,CIoPacket::IrpBufferEntry const &)
0x180033c1c  mov     rbx, [rdi+48h]
0x180033c20  sub     rbx, 20h ; ' '
0x180033c24  mov     rsi, [rdi+70h]
0x180033c28  add     rsi, [rdi+60h]
0x180033c2c  mov     r14, [rbx+10h]
0x180033c30  mov     r15, [rbx+8]
0x180033c34  sub     rsi, [rdi+78h]
0x180033c38  sub     r14, [rbx+18h]
0x180033c3c  add     r15, [rbx+18h]
0x180033c40  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180033c45  mov     rcx, [rax+8]
0x180033c49  mov     eax, [rcx]
0x180033c4b  cmp     eax, 5
0x180033c4e  jbe     loc_180033CD7
0x180033c54  mov     rax, [rbx+10h]
0x180033c58  lea     rdx, qword_18004FEE8
0x180033c5f  mov     [rbp+57h+var_80], rax
0x180033c63  lea     rax, aIopacketstatec; "IoPacketStateCommitPendingIrp"
0x180033c6a  mov     [rbp+57h+var_70], rax
0x180033c6e  lea     rax, aCiopacketIopac_2; "CIoPacket::IoPacketStateCommitPendingIr"...
0x180033c75  mov     [rbp+57h+var_68], rax
0x180033c79  lea     rax, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180033c80  mov     [rbp+57h+var_60], rax
0x180033c84  lea     rax, [rbp+57h+arg_18]
0x180033c88  mov     [rsp+0E0h+var_90], rax
0x180033c8d  lea     rax, [rbp+57h+var_80]
0x180033c91  mov     [rsp+0E0h+var_98], rax
0x180033c96  lea     rax, [rbp+57h+var_78]
0x180033c9a  mov     [rsp+0E0h+var_A0], rax
0x180033c9f  lea     rax, [rbp+57h+var_70]
0x180033ca3  mov     [rsp+0E0h+var_A8], rax
0x180033ca8  lea     rax, [rbp+57h+var_68]
0x180033cac  mov     [rsp+0E0h+var_B0], rax
0x180033cb1  lea     rax, [rbp+57h+arg_0]
0x180033cb5  mov     [rsp+0E0h+var_B8], rax
0x180033cba  lea     rax, [rbp+57h+var_60]
0x180033cbe  mov     [rsp+0E0h+var_C0], rax
0x180033cc3  mov     [rbp+57h+arg_18], rsi
0x180033cc7  mov     [rbp+57h+var_78], rdi
0x180033ccb  mov     dword ptr [rbp+57h+arg_0], 6B9h
0x180033cd2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180033cd7  mov     rdx, [rdi+78h]; Src
0x180033cdb  mov     rcx, r15; void *
0x180033cde  cmp     r14, rsi
0x180033ce1  jnb     short loc_180033CFE
0x180033ce3  mov     r8, r14; Size
0x180033ce6  call    memcpy_0
0x180033ceb  add     [rdi+78h], r14
0x180033cef  mov     rax, [rbx+10h]
0x180033cf3  mov     [rbx+18h], rax
0x180033cf7  mov     eax, 3
0x180033cfc  jmp     short loc_180033D13
0x180033cfe  mov     r8, rsi; Size
0x180033d01  call    memcpy_0
0x180033d06  add     [rdi+78h], rsi
0x180033d0a  mov     eax, 5
0x180033d0f  add     [rbx+18h], rsi
0x180033d13  add     rsp, 0B8h
0x180033d1a  pop     r15
0x180033d1c  pop     r14
0x180033d1e  pop     rdi
0x180033d1f  pop     rsi
0x180033d20  pop     rbx
0x180033d21  pop     rbp
0x180033d22  retn
```
