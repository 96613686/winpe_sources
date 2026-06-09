# RpcSrvSBCompleteRetrieveSocket

- ea: `0x180018a40`
- end: `0x180018bc6`
- name: `RpcSrvSBCompleteRetrieveSocket`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001ebc`
- `0x18000264c`
- `0x180003ed0`
- `0x180004a30`
- `0x18000a0a0`
- `0x180014780`
- `0x180014d30`
- `0x180018a40`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180018b75`
- `RPCRT4!RpcRevertToSelf` at `0x180018b75`

## string_xrefs

- `0x180018bab`: `RpcSrvSBCompleteRetrieveSocket: invalid parameter`
- `0x180018ade`: `RpcSrvSBCompleteRetrieveSocket: RpcHelperRetriveSbContext failed`
- `0x180018b02`: `RpcSrvSBCompleteRetrieveSocket: RetrieveContext failed`
- `0x180018b5a`: `RpcSrvSBCompleteRetrieveSocket: completed`

## pseudocode

```c
__int64 __fastcall RpcSrvSBCompleteRetrieveSocket(__int64 a1, unsigned __int16 *a2, __int64 *a3, __int64 *a4)
{
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // ebx
  unsigned int Socket; // eax
  __int64 *v15; // [rsp+40h] [rbp-38h] BYREF
  SocketBrokerContext *v16; // [rsp+48h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-28h] BYREF
  __int64 *v18; // [rsp+58h] [rbp-20h] BYREF
  __int64 *v19; // [rsp+60h] [rbp-18h] BYREF
  bool v20; // [rsp+B0h] [rbp+38h] BYREF

  v16 = 0;
  lpMem = 0;
  v20 = 0;
  if ( a3 && a4 )
  {
    if ( (unsigned int)dword_18004D068 > 5 )
    {
      v15 = a4;
      v18 = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
        a1,
        (unsigned __int8 *)word_18004551A,
        (__int64)a3,
        (__int64)a4,
        (__int64 *)&v18,
        &v15);
    }
    v7 = RpcHelperRetriveSbContext(a2, (struct _GUID *)a2, &v20, (unsigned __int16 **)&lpMem, &v16, 0);
    v12 = v7;
    if ( v7 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v9,
          v8,
          L"RpcSrvSBCompleteRetrieveSocket: RpcHelperRetriveSbContext failed",
          v7);
    }
    else
    {
      Socket = SocketBrokerContext::CompleteRetrieveSocket(v16, (const unsigned __int16 *)a4);
      v12 = Socket;
      if ( Socket && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v9, v8, L"RpcSrvSBCompleteRetrieveSocket: RetrieveContext failed", Socket);
    }
    if ( (unsigned int)dword_18004D068 > 5 )
    {
      LODWORD(v15) = v12;
      v18 = a4;
      v19 = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned __int8 *)byte_18004540D,
        v10,
        v11,
        (__int64 *)&v19,
        &v18,
        (__int64)&v15);
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v9, v8, L"RpcSrvSBCompleteRetrieveSocket: completed", (unsigned int)v12);
    VpnFree(lpMem);
    if ( v20 )
      RpcRevertToSelf();
    if ( v16 )
      SocketBrokerContext::ReleaseRef(v16);
    if ( v12 > 0 )
      return (unsigned __int16)v12 | 0x80070000;
    return (unsigned int)v12;
  }
  else
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(a1, a2, L"RpcSrvSBCompleteRetrieveSocket: invalid parameter", 87);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180018a40  push    rbp
0x180018a42  push    rbx
0x180018a43  push    rdi
0x180018a44  push    r14
0x180018a46  mov     rbp, rsp
0x180018a49  sub     rsp, 78h
0x180018a4d  mov     [rbp+var_30], 0
0x180018a55  mov     rdi, r9
0x180018a58  mov     [rbp+lpMem], 0
0x180018a60  mov     r14, r8
0x180018a63  mov     [rbp+arg_10], 0
0x180018a67  mov     rbx, rdx
0x180018a6a  test    r8, r8
0x180018a6d  jz      loc_180018B9C
0x180018a73  test    r9, r9
0x180018a76  jz      loc_180018B9C
0x180018a7c  mov     eax, cs:dword_18004D068
0x180018a82  cmp     eax, 5
0x180018a85  jbe     short loc_180018AAD
0x180018a87  lea     rax, [rbp+var_38]
0x180018a8b  mov     [rbp+var_38], r9
0x180018a8f  mov     [rsp+78h+var_50], rax
0x180018a94  lea     rdx, word_18004551A
0x180018a9b  lea     rax, [rbp+var_20]
0x180018a9f  mov     [rbp+var_20], r8
0x180018aa3  mov     [rsp+78h+var_58], rax
0x180018aa8  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x180018aad  lea     rax, [rbp+var_30]
0x180018ab1  mov     [rsp+78h+var_50], 0; void **
0x180018aba  lea     r9, [rbp+lpMem]; unsigned __int16 **
0x180018abe  mov     [rsp+78h+var_58], rax; struct SocketBrokerContext **
0x180018ac3  lea     r8, [rbp+arg_10]; bool *
0x180018ac7  mov     rcx, rbx; unsigned __int16 *
0x180018aca  call    ?RpcHelperRetriveSbContext@@YAKPEBGPEAU_GUID@@PEA_NPEAPEAGPEAPEAVSocketBrokerContext@@PEAPEAX@Z; RpcHelperRetriveSbContext(ushort const *,_GUID *,bool *,ushort * *,SocketBrokerContext * *,void * *)
0x180018acf  mov     ebx, eax
0x180018ad1  test    eax, eax
0x180018ad3  jz      short loc_180018AE7
0x180018ad5  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180018adc  jz      short loc_180018B11
0x180018ade  lea     r8, aRpcsrvsbcomple_0; "RpcSrvSBCompleteRetrieveSocket: RpcHelp"...
0x180018ae5  jmp     short loc_180018B09
0x180018ae7  mov     rcx, [rbp+var_30]; this
0x180018aeb  mov     rdx, rdi; unsigned __int16 *
0x180018aee  call    ?CompleteRetrieveSocket@SocketBrokerContext@@QEAAKPEBG@Z; SocketBrokerContext::CompleteRetrieveSocket(ushort const *)
0x180018af3  mov     ebx, eax
0x180018af5  test    eax, eax
0x180018af7  jz      short loc_180018B11
0x180018af9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180018b00  jz      short loc_180018B11
0x180018b02  lea     r8, aRpcsrvsbcomple; "RpcSrvSBCompleteRetrieveSocket: Retriev"...
0x180018b09  mov     r9d, eax
0x180018b0c  call    McTemplateU0zq_EventWriteTransfer
0x180018b11  mov     eax, cs:dword_18004D068
0x180018b17  cmp     eax, 5
0x180018b1a  jbe     short loc_180018B4E
0x180018b1c  lea     rax, [rbp+var_38]
0x180018b20  mov     dword ptr [rbp+var_38], ebx
0x180018b23  mov     [rsp+78h+var_48], rax
0x180018b28  lea     rdx, byte_18004540D
0x180018b2f  lea     rax, [rbp+var_20]
0x180018b33  mov     [rbp+var_20], rdi
0x180018b37  mov     [rsp+78h+var_50], rax
0x180018b3c  lea     rax, [rbp+var_18]
0x180018b40  mov     [rsp+78h+var_58], rax
0x180018b45  mov     [rbp+var_18], r14
0x180018b49  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180018b4e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180018b55  jz      short loc_180018B66
0x180018b57  mov     r9d, ebx
0x180018b5a  lea     r8, aRpcsrvsbcomple_1; "RpcSrvSBCompleteRetrieveSocket: complet"...
0x180018b61  call    McTemplateU0zq_EventWriteTransfer
0x180018b66  mov     rcx, [rbp+lpMem]; lpMem
0x180018b6a  call    VpnFree
0x180018b6f  cmp     [rbp+arg_10], 0
0x180018b73  jz      short loc_180018B7B
0x180018b75  call    cs:__imp_RpcRevertToSelf
0x180018b7b  cmp     [rbp+var_30], 0
0x180018b80  jz      short loc_180018B8B
0x180018b82  mov     rcx, [rbp+var_30]; this
0x180018b86  call    ?ReleaseRef@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::ReleaseRef(void)
0x180018b8b  test    ebx, ebx
0x180018b8d  jle     short loc_180018B98
0x180018b8f  movzx   ebx, bx
0x180018b92  or      ebx, 80070000h
0x180018b98  mov     eax, ebx
0x180018b9a  jmp     short loc_180018BBC
0x180018b9c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180018ba3  jz      short loc_180018BB7
0x180018ba5  mov     r9d, 57h ; 'W'
0x180018bab  lea     r8, aRpcsrvsbcomple_2; "RpcSrvSBCompleteRetrieveSocket: invalid"...
0x180018bb2  call    McTemplateU0zq_EventWriteTransfer
0x180018bb7  mov     eax, 80070057h
0x180018bbc  add     rsp, 78h
0x180018bc0  pop     r14
0x180018bc2  pop     rdi
0x180018bc3  pop     rbx
0x180018bc4  pop     rbp
0x180018bc5  retn
```
