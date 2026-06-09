# CSoapProcessor::CreateListenerOperation(InboundRequestDetails *,CListenerOperation * *)

- ea: `0x18009d670`
- end: `0x18009df01`
- name: `?CreateListenerOperation@CSoapProcessor@@MEAAXPEAVInboundRequestDetails@@PEAPEAVCListenerOperation@@@Z`
- size: `2193`
- prototype: `void __fastcall(CSoapProcessor *__hidden this, struct InboundRequestDetails *, struct CListenerOperation **)`
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180005d10`
- `0x18002b7a0`
- `0x18004a900`
- `0x1800621e0`
- `0x18008f6a0`
- `0x18009d670`
- `0x18009df08`
- `0x18009e098`
- `0x1800ea9d4`
- `0x1800ed540`
- `0x1800f9ebc`
- `0x1800fbeb4`
- `0x1801133b0`
- `0x18011349c`
- `0x18011a6d4`
- `0x18017bef0`
- `0x180182690`
- `0x180182cbc`
- `0x1801858f8`
- `0x180185adc`
- `0x180185cec`
- `0x180186b74`
- `0x180186f28`
- `0x18018731c`
- `0x180188350`
- `0x18018932c`
- `0x1801898dc`
- `0x180189df4`
- `0x18018abbc`
- `0x1801ba176`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18009de23`
- `msvcrt!_wcsnicmp` at `0x18009de94`
- `msvcrt!_wcsnicmp` at `0x18009de23`
- `msvcrt!_wcsnicmp` at `0x18009de94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009d9b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009d9b8`

## string_xrefs

- `0x18009de19`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell`
- `0x18009d76e`: `http://schemas.xmlsoap.org/ws/2004/09/transfer/Get`
- `0x18009da75`: `http://schemas.xmlsoap.org/ws/2004/08/eventing/Subscribe`
- `0x18009da29`: `http://schemas.xmlsoap.org/ws/2004/09/enumeration/Release`
- `0x18009db0d`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Command`
- `0x18009dcd5`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Connect`
- `0x18009dd4f`: `http://schemas.xmlsoap.org/ws/2004/08/eventing/GetStatus`
- `0x18009dba5`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Send`
- `0x18009dd21`: `http://schemas.xmlsoap.org/ws/2004/09/enumeration/Renew`
- `0x18009dd38`: `http://schemas.xmlsoap.org/ws/2004/09/enumeration/GetStatus`
- `0x18009dc3d`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Disconnect`
- `0x18009dc89`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Reconnect`
- `0x18009db59`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Signal`
- `0x18009dd66`: `http://schemas.xmlsoap.org/ws/2004/08/eventing/Renew`
- `0x18009dbf1`: `http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Receive`
- `0x18009d997`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18009dac1`: `http://schemas.xmlsoap.org/ws/2004/08/eventing/Unsubscribe`
- `0x18009de8a`: `http://schemas.microsoft.com/wbem/wsman/1/config`
- `0x18009d958`: `http://schemas.xmlsoap.org/ws/2004/09/enumeration/Enumerate`
- `0x18009d808`: `http://schemas.xmlsoap.org/ws/2004/09/transfer/Create`
- `0x18009d8b0`: `http://schemas.xmlsoap.org/ws/2004/09/transfer/Delete`
- `0x18009d7bc`: `http://schemas.xmlsoap.org/ws/2004/09/transfer/Put`
- `0x18009d9dd`: `http://schemas.xmlsoap.org/ws/2004/09/enumeration/Pull`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall CSoapProcessor::CreateListenerOperation(
        CSoapProcessor *this,
        struct InboundRequestDetails *a2,
        struct CListenerOperation **a3)
{
  struct IRequestContext *v4; // r13
  _DWORD *v5; // rbx
  struct CServiceCommonConfigSettings *v6; // r14
  PVOID *v7; // rsi
  const unsigned __int16 *v8; // r12
  const wchar_t *Value; // rdi
  CListenerIdentify *v10; // rax
  CListenerShell *v11; // rbx
  CListenerGet *v12; // rax
  CListenerPut *v13; // rax
  const struct Catalog::Resource *Resource; // rax
  CListenerShell *v15; // rax
  CListenerCreate *v16; // rax
  const struct Catalog::Resource *v17; // rax
  CListenerDeleteShell *v18; // rax
  CListenerDelete *v19; // rax
  CHeap *v20; // rcx
  CHeap *v21; // rcx
  CListenerEnumeration *v22; // rax
  void *Handle; // rax
  CListenerPull *v24; // rax
  CListenerRelease *v25; // rax
  CListenerSubscription *v26; // rax
  CListenerUnsubscribe *v27; // rax
  CListenerCommand *v28; // rax
  CListenerSignal *v29; // rax
  CListenerSend *v30; // rax
  CListenerReceive *v31; // rax
  CListenerDisconnectShell *v32; // rax
  CListenerReconnectShell *v33; // rax
  CListenerConnect *v34; // rax
  CListenerInvoke *v35; // rax
  CListenerGet *v36; // [rsp+38h] [rbp-39h] BYREF
  int v37; // [rsp+40h] [rbp-31h] BYREF
  int v38; // [rsp+44h] [rbp-2Dh] BYREF
  int v39; // [rsp+48h] [rbp-29h] BYREF
  int v40; // [rsp+4Ch] [rbp-25h] BYREF
  int v41; // [rsp+50h] [rbp-21h] BYREF
  int v42; // [rsp+54h] [rbp-1Dh] BYREF
  int v43; // [rsp+58h] [rbp-19h] BYREF
  int v44; // [rsp+5Ch] [rbp-15h] BYREF
  int v45; // [rsp+60h] [rbp-11h] BYREF
  int v46; // [rsp+64h] [rbp-Dh] BYREF
  int v47; // [rsp+68h] [rbp-9h] BYREF
  int v48; // [rsp+6Ch] [rbp-5h] BYREF
  int v49; // [rsp+70h] [rbp-1h] BYREF
  int v50; // [rsp+74h] [rbp+3h] BYREF
  int v51; // [rsp+78h] [rbp+7h] BYREF
  int v52; // [rsp+7Ch] [rbp+Bh] BYREF
  int v53; // [rsp+80h] [rbp+Fh] BYREF
  CListenerIdentify *v54; // [rsp+88h] [rbp+17h] BYREF
  CListenerIdentify **v57; // [rsp+F0h] [rbp+7Fh] BYREF

  v4 = (struct IRequestContext *)*((_QWORD *)a2 + 9);
  v5 = (_DWORD *)*((_QWORD *)a2 + 33);
  v6 = (struct CServiceCommonConfigSettings *)*((_QWORD *)a2 + 10);
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, this);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = &Class;
  if ( v5[774] )
  {
    Value = (const wchar_t *)PacketParser::PacketElement<unsigned short const *>::GetValue(v5 + 774);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    Value = &Class;
  }
  if ( v5[756] )
  {
    v8 = (const unsigned __int16 *)PacketParser::PacketElement<unsigned short const *>::GetValue(v5 + 756);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5[1074] )
  {
    LODWORD(v57) = 0;
    v36 = (CListenerGet *)&v57;
    v10 = (CListenerIdentify *)WSManMemory::Alloc(2144, 0, 0);
    v54 = v10;
    if ( v10 )
      v11 = CListenerIdentify::CListenerIdentify(v10, this, v6);
    else
      v11 = 0;
    goto LABEL_103;
  }
  v11 = 0;
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/transfer/Get") )
  {
    v37 = 0;
    v57 = (CListenerIdentify **)&v37;
    v12 = (CListenerGet *)WSManMemory::Alloc(2200, 0, 0);
    v36 = v12;
    if ( v12 )
      v11 = CListenerGet::CListenerGet(v12, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/transfer/Put") )
  {
    v38 = 0;
    v57 = (CListenerIdentify **)&v38;
    v13 = (CListenerPut *)WSManMemory::Alloc(2200, 0, 0);
    v36 = v13;
    if ( v13 )
      v11 = CListenerPut::CListenerPut(v13, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/transfer/Create") )
  {
    if ( v8
      && (Resource = Catalog::GetResource((CSoapProcessor *)((char *)this + 32), v8, v4)) != 0
      && (*((_BYTE *)Resource + 68) & 1) != 0 )
    {
      v39 = 0;
      v57 = (CListenerIdentify **)&v39;
      v15 = (CListenerShell *)WSManMemory::Alloc(10784, 0, 0);
      v36 = v15;
      if ( v15 )
        v11 = CListenerShell::CListenerShell(v15, this, v6);
    }
    else
    {
      v40 = 0;
      v57 = (CListenerIdentify **)&v40;
      v16 = (CListenerCreate *)WSManMemory::Alloc(2200, 0, 0);
      v36 = v16;
      if ( v16 )
        v11 = CListenerCreate::CListenerCreate(v16, this, v6);
    }
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/transfer/Delete") )
  {
    if ( v8
      && (v17 = Catalog::GetResource((CSoapProcessor *)((char *)this + 32), v8, v4)) != 0
      && (*((_BYTE *)v17 + 68) & 1) != 0 )
    {
      v41 = 0;
      v57 = (CListenerIdentify **)&v41;
      v18 = (CListenerDeleteShell *)WSManMemory::Alloc(2232, 0, 0);
      v36 = v18;
      if ( v18 )
        v11 = CListenerDeleteShell::CListenerDeleteShell(v18, this, v6);
    }
    else
    {
      v42 = 0;
      v57 = (CListenerIdentify **)&v42;
      v19 = (CListenerDelete *)WSManMemory::Alloc(2200, 0, 0);
      v36 = v19;
      if ( v19 )
        v11 = CListenerDelete::CListenerDelete(v19, this, v6);
    }
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/enumeration/Enumerate") )
  {
    v43 = 0;
    v57 = (CListenerIdentify **)&v43;
    if ( CHeap::GetHandle(v20) )
    {
      Handle = CHeap::GetHandle(v21);
      v22 = (CListenerEnumeration *)HeapAlloc(Handle, 0, 0xAB0u);
    }
    else
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
      v22 = 0;
    }
    v36 = v22;
    if ( v22 )
      v11 = CListenerEnumeration::CListenerEnumeration(v22, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/enumeration/Pull") )
  {
    v44 = 0;
    v57 = (CListenerIdentify **)&v44;
    v24 = (CListenerPull *)WSManMemory::Alloc(2184, 0, 0);
    v36 = v24;
    if ( v24 )
      v11 = CListenerPull::CListenerPull(v24, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/enumeration/Release") )
  {
    v45 = 0;
    v57 = (CListenerIdentify **)&v45;
    v25 = (CListenerRelease *)WSManMemory::Alloc(2176, 0, 0);
    v36 = v25;
    if ( v25 )
      v11 = CListenerRelease::CListenerRelease(v25, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/08/eventing/Subscribe") )
  {
    v46 = 0;
    v57 = (CListenerIdentify **)&v46;
    v26 = (CListenerSubscription *)WSManMemory::Alloc(3240, 0, 0);
    v36 = v26;
    if ( v26 )
      v11 = CListenerSubscription::CListenerSubscription(v26, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/08/eventing/Unsubscribe") )
  {
    v47 = 0;
    v57 = (CListenerIdentify **)&v47;
    v27 = (CListenerUnsubscribe *)WSManMemory::Alloc(2176, 0, 0);
    v36 = v27;
    if ( v27 )
      v11 = CListenerUnsubscribe::CListenerUnsubscribe(v27, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Command") )
  {
    v48 = 0;
    v57 = (CListenerIdentify **)&v48;
    v28 = (CListenerCommand *)WSManMemory::Alloc(7008, 0, 0);
    v36 = v28;
    if ( v28 )
      v11 = CListenerCommand::CListenerCommand(v28, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Signal") )
  {
    v49 = 0;
    v57 = (CListenerIdentify **)&v49;
    v29 = (CListenerSignal *)WSManMemory::Alloc(2256, 0, 0);
    v36 = v29;
    if ( v29 )
      v11 = CListenerSignal::CListenerSignal(v29, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Send") )
  {
    v50 = 0;
    v57 = (CListenerIdentify **)&v50;
    v30 = (CListenerSend *)WSManMemory::Alloc(2320, 0, 0);
    v36 = v30;
    if ( v30 )
      v11 = CListenerSend::CListenerSend(v30, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Receive") )
  {
    v51 = 0;
    v57 = (CListenerIdentify **)&v51;
    v31 = (CListenerReceive *)WSManMemory::Alloc(2312, 0, 0);
    v36 = v31;
    if ( v31 )
      v11 = CListenerReceive::CListenerReceive(v31, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Disconnect") )
  {
    v52 = 0;
    v57 = (CListenerIdentify **)&v52;
    v32 = (CListenerDisconnectShell *)WSManMemory::Alloc(2248, 0, 0);
    v36 = v32;
    if ( v32 )
      v11 = CListenerDisconnectShell::CListenerDisconnectShell(v32, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Reconnect") )
  {
    v53 = 0;
    v57 = (CListenerIdentify **)&v53;
    v33 = (CListenerReconnectShell *)WSManMemory::Alloc(2240, 0, 0);
    v36 = v33;
    if ( v33 )
      v11 = CListenerReconnectShell::CListenerReconnectShell(v33, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell/Connect") )
  {
    LODWORD(v54) = 0;
    v57 = &v54;
    v34 = (CListenerConnect *)WSManMemory::Alloc(2392, 0, 0);
    v36 = v34;
    if ( v34 )
      v11 = CListenerConnect::CListenerConnect(v34, this, v6);
    goto LABEL_103;
  }
  if ( !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/enumeration/Renew")
    || !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/09/enumeration/GetStatus")
    || !wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/08/eventing/GetStatus") )
  {
    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *))(*(_QWORD *)v4 + 64LL))(
      v4,
      2150858771LL,
      1077134280,
      Value);
  }
  else
  {
    if ( wcscmp_0(Value, L"http://schemas.xmlsoap.org/ws/2004/08/eventing/Renew") )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400) != 0 )
        WPP_SF_S(v7[2], 50, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, Value);
      LODWORD(v36) = 0;
      v57 = &v36;
      v35 = (CListenerInvoke *)WSManMemory::Alloc(2208, 0, 0);
      v54 = v35;
      if ( v35 )
        v11 = CListenerInvoke::CListenerInvoke(v35, this, v6);
      else
        v11 = 0;
LABEL_103:
      *a3 = v11;
      if ( v11 )
        goto LABEL_104;
      goto LABEL_109;
    }
    (*(void (__fastcall **)(struct IRequestContext *, __int64, _QWORD, _QWORD))(*(_QWORD *)v4 + 64LL))(
      v4,
      2150858788LL,
      0,
      0);
  }
  *a3 = 0;
LABEL_109:
  if ( (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)v4 + 144LL))(v4) )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)v4 + 24LL))(v4);
    goto LABEL_113;
  }
LABEL_104:
  if ( v8 )
  {
    if ( _wcsnicmp(v8, L"http://schemas.microsoft.com/wbem/wsman/1/windows/shell", 0x37u) )
    {
      if ( !_wcsnicmp(v8, L"http://schemas.microsoft.com/wbem/wsman/1/config", 0x30u) )
        *((_QWORD *)v11 + 138) = *((_QWORD *)a2 + 10);
    }
    else
    {
      *((_QWORD *)v11 + 138) = v11;
    }
  }
LABEL_113:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids, this, v11);
}

```

## disassembly

```asm
0x18009d670  mov     rax, rsp
0x18009d673  mov     [rax+8], rbx
0x18009d677  mov     [rax+18h], r8
0x18009d67b  mov     [rax+10h], rdx
0x18009d67f  push    rbp
0x18009d680  push    rsi
0x18009d681  push    rdi
0x18009d682  push    r12
0x18009d684  push    r13
0x18009d686  push    r14
0x18009d688  push    r15
0x18009d68a  lea     rbp, [rax-5Fh]
0x18009d68e  sub     rsp, 90h
0x18009d695  mov     r15, rcx
0x18009d698  mov     r13, [rdx+48h]
0x18009d69c  mov     rbx, [rdx+108h]
0x18009d6a3  mov     r14, [rdx+50h]
0x18009d6a7  lea     rax, WPP_GLOBAL_Control
0x18009d6ae  mov     rsi, cs:WPP_GLOBAL_Control
0x18009d6b5  cmp     rsi, rax
0x18009d6b8  jz      short loc_18009D6E2
0x18009d6ba  test    dword ptr [rsi+1Ch], 400h
0x18009d6c1  jz      short loc_18009D6E2
0x18009d6c3  mov     edx, 31h ; '1'
0x18009d6c8  mov     r9, rcx
0x18009d6cb  lea     r8, WPP_a482115d032f30ae1a22b7eb05ad85d2_Traceguids
0x18009d6d2  mov     rcx, [rsi+10h]
0x18009d6d6  call    WPP_SF_q
0x18009d6db  mov     rsi, cs:WPP_GLOBAL_Control
0x18009d6e2  lea     rcx, [rbx+0C18h]
0x18009d6e9  lea     r12, Class
0x18009d6f0  cmp     dword ptr [rcx], 0
0x18009d6f3  jz      short loc_18009D706
0x18009d6f5  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x18009d6fa  mov     rdi, rax
0x18009d6fd  mov     rsi, cs:WPP_GLOBAL_Control
0x18009d704  jmp     short loc_18009D709
0x18009d706  mov     rdi, r12
0x18009d709  lea     rcx, [rbx+0BD0h]
0x18009d710  cmp     dword ptr [rcx], 0
0x18009d713  jz      short loc_18009D724
0x18009d715  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x18009d71a  mov     r12, rax
0x18009d71d  mov     rsi, cs:WPP_GLOBAL_Control
0x18009d724  cmp     dword ptr [rbx+10C8h], 0
0x18009d72b  jz      short loc_18009D76E
0x18009d72d  mov     dword ptr [rbp+57h+arg_18], 0
0x18009d734  lea     rax, [rbp+57h+arg_18]
0x18009d738  mov     [rbp+57h+var_90], rax
0x18009d73c  xor     r8d, r8d
0x18009d73f  xor     edx, edx
0x18009d741  mov     ecx, 860h
0x18009d746  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009d74b  mov     [rbp+57h+var_40], rax
0x18009d74f  test    rax, rax
0x18009d752  jz      short loc_18009D767
0x18009d754  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009d757  mov     rdx, r15; struct CSoapProcessor *
0x18009d75a  mov     rcx, rax; this
0x18009d75d  call    ??0CListenerIdentify@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerIdentify::CListenerIdentify(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009d762  mov     rbx, rax
0x18009d765  jmp     short loc_18009D769
0x18009d767  xor     ebx, ebx
0x18009d769  jmp     loc_18009DDFE
0x18009d76e  lea     rdx, aHttpSchemasXml_27; "http://schemas.xmlsoap.org/ws/2004/09/t"...
0x18009d775  mov     rcx, rdi; String1
0x18009d778  call    wcscmp_0
0x18009d77d  xor     ebx, ebx
0x18009d77f  test    eax, eax
0x18009d781  jnz     short loc_18009D7BC
0x18009d783  mov     [rbp+57h+var_88], ebx
0x18009d786  lea     rax, [rbp+57h+var_88]
0x18009d78a  mov     [rbp+57h+arg_18], rax
0x18009d78e  xor     r8d, r8d
0x18009d791  xor     edx, edx
0x18009d793  mov     ecx, 898h
0x18009d798  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009d79d  mov     [rbp+57h+var_90], rax
0x18009d7a1  test    rax, rax
0x18009d7a4  jz      short loc_18009D7B7
0x18009d7a6  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009d7a9  mov     rdx, r15; struct CSoapProcessor *
0x18009d7ac  mov     rcx, rax; this
0x18009d7af  call    ??0CListenerGet@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerGet::CListenerGet(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009d7b4  mov     rbx, rax
0x18009d7b7  jmp     loc_18009DDFE
0x18009d7bc  lea     rdx, aHttpSchemasXml_2; "http://schemas.xmlsoap.org/ws/2004/09/t"...
0x18009d7c3  mov     rcx, rdi; String1
0x18009d7c6  call    wcscmp_0
0x18009d7cb  test    eax, eax
0x18009d7cd  jnz     short loc_18009D808
0x18009d7cf  mov     [rbp+57h+var_84], ebx
0x18009d7d2  lea     rax, [rbp+57h+var_84]
0x18009d7d6  mov     [rbp+57h+arg_18], rax
0x18009d7da  xor     r8d, r8d
0x18009d7dd  xor     edx, edx
0x18009d7df  mov     ecx, 898h
0x18009d7e4  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009d7e9  mov     [rbp+57h+var_90], rax
0x18009d7ed  test    rax, rax
0x18009d7f0  jz      short loc_18009D803
0x18009d7f2  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009d7f5  mov     rdx, r15; struct CSoapProcessor *
0x18009d7f8  mov     rcx, rax; this
0x18009d7fb  call    ??0CListenerPut@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerPut::CListenerPut(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009d800  mov     rbx, rax
0x18009d803  jmp     loc_18009DDFE
0x18009d808  lea     rdx, aHttpSchemasXml_30; "http://schemas.xmlsoap.org/ws/2004/09/t"...
0x18009d80f  mov     rcx, rdi; String1
0x18009d812  call    wcscmp_0
0x18009d817  test    eax, eax
0x18009d819  jnz     loc_18009D8B0
0x18009d81f  test    r12, r12
0x18009d822  jz      short loc_18009D877
0x18009d824  lea     rcx, [r15+20h]; this
0x18009d828  mov     r8, r13; struct IRequestContext *
0x18009d82b  mov     rdx, r12; unsigned __int16 *
0x18009d82e  call    ?GetResource@Catalog@@QEBAPEBVResource@1@PEBGAEAVIRequestContext@@@Z; Catalog::GetResource(ushort const *,IRequestContext &)
0x18009d833  test    rax, rax
0x18009d836  jz      short loc_18009D877
0x18009d838  test    byte ptr [rax+44h], 1
0x18009d83c  jz      short loc_18009D877
0x18009d83e  mov     [rbp+57h+var_80], ebx
0x18009d841  lea     rax, [rbp+57h+var_80]
0x18009d845  mov     [rbp+57h+arg_18], rax
0x18009d849  xor     r8d, r8d
0x18009d84c  xor     edx, edx
0x18009d84e  mov     ecx, 2A20h
0x18009d853  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009d858  mov     [rbp+57h+var_90], rax
0x18009d85c  test    rax, rax
0x18009d85f  jz      short loc_18009D872
0x18009d861  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009d864  mov     rdx, r15; struct CSoapProcessor *
0x18009d867  mov     rcx, rax; this
0x18009d86a  call    ??0CListenerShell@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerShell::CListenerShell(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009d86f  mov     rbx, rax
0x18009d872  jmp     loc_18009DDFE
0x18009d877  mov     [rbp+57h+var_7C], ebx
0x18009d87a  lea     rax, [rbp+57h+var_7C]
0x18009d87e  mov     [rbp+57h+arg_18], rax
0x18009d882  xor     r8d, r8d
0x18009d885  xor     edx, edx
0x18009d887  mov     ecx, 898h
0x18009d88c  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009d891  mov     [rbp+57h+var_90], rax
0x18009d895  test    rax, rax
0x18009d898  jz      short loc_18009D8AB
0x18009d89a  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009d89d  mov     rdx, r15; struct CSoapProcessor *
0x18009d8a0  mov     rcx, rax; this
0x18009d8a3  call    ??0CListenerCreate@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerCreate::CListenerCreate(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009d8a8  mov     rbx, rax
0x18009d8ab  jmp     loc_18009DDFE
0x18009d8b0  lea     rdx, aHttpSchemasXml_18; "http://schemas.xmlsoap.org/ws/2004/09/t"...
0x18009d8b7  mov     rcx, rdi; String1
0x18009d8ba  call    wcscmp_0
0x18009d8bf  test    eax, eax
0x18009d8c1  jnz     loc_18009D958
0x18009d8c7  test    r12, r12
0x18009d8ca  jz      short loc_18009D91F
0x18009d8cc  lea     rcx, [r15+20h]; this
0x18009d8d0  mov     r8, r13; struct IRequestContext *
0x18009d8d3  mov     rdx, r12; unsigned __int16 *
0x18009d8d6  call    ?GetResource@Catalog@@QEBAPEBVResource@1@PEBGAEAVIRequestContext@@@Z; Catalog::GetResource(ushort const *,IRequestContext &)
0x18009d8db  test    rax, rax
0x18009d8de  jz      short loc_18009D91F
0x18009d8e0  test    byte ptr [rax+44h], 1
0x18009d8e4  jz      short loc_18009D91F
0x18009d8e6  mov     [rbp+57h+var_78], ebx
0x18009d8e9  lea     rax, [rbp+57h+var_78]
0x18009d8ed  mov     [rbp+57h+arg_18], rax
0x18009d8f1  xor     r8d, r8d
0x18009d8f4  xor     edx, edx
0x18009d8f6  mov     ecx, 8B8h
0x18009d8fb  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009d900  mov     [rbp+57h+var_90], rax
0x18009d904  test    rax, rax
0x18009d907  jz      short loc_18009D91A
0x18009d909  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009d90c  mov     rdx, r15; struct CSoapProcessor *
0x18009d90f  mov     rcx, rax; this
0x18009d912  call    ??0CListenerDeleteShell@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerDeleteShell::CListenerDeleteShell(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009d917  mov     rbx, rax
0x18009d91a  jmp     loc_18009DDFE
0x18009d91f  mov     [rbp+57h+var_74], ebx
0x18009d922  lea     rax, [rbp+57h+var_74]
0x18009d926  mov     [rbp+57h+arg_18], rax
0x18009d92a  xor     r8d, r8d
0x18009d92d  xor     edx, edx
0x18009d92f  mov     ecx, 898h
0x18009d934  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009d939  mov     [rbp+57h+var_90], rax
0x18009d93d  test    rax, rax
0x18009d940  jz      short loc_18009D953
0x18009d942  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009d945  mov     rdx, r15; struct CSoapProcessor *
0x18009d948  mov     rcx, rax; this
0x18009d94b  call    ??0CListenerDelete@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerDelete::CListenerDelete(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009d950  mov     rbx, rax
0x18009d953  jmp     loc_18009DDFE
0x18009d958  lea     rdx, aHttpSchemasXml_1; "http://schemas.xmlsoap.org/ws/2004/09/e"...
0x18009d95f  mov     rcx, rdi; String1
0x18009d962  call    wcscmp_0
0x18009d967  test    eax, eax
0x18009d969  jnz     short loc_18009D9DD
0x18009d96b  mov     [rbp+57h+var_70], ebx
0x18009d96e  lea     rax, [rbp+57h+var_70]
0x18009d972  mov     [rbp+57h+arg_18], rax
0x18009d976  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18009d97b  test    rax, rax
0x18009d97e  jnz     short loc_18009D9A8
0x18009d980  mov     [rsp+20h], rbx; struct IRequestContext *
0x18009d985  mov     r9d, 54Fh; unsigned int
0x18009d98b  lea     r8, a170; "170"
0x18009d992  mov     edx, 0AAh; unsigned int
0x18009d997  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18009d99e  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18009d9a3  mov     rax, rbx
0x18009d9a6  jmp     short loc_18009D9BE
0x18009d9a8  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18009d9ad  xor     edx, edx; dwFlags
0x18009d9af  mov     r8d, 0AB0h; dwBytes
0x18009d9b5  mov     rcx, rax; hHeap
0x18009d9b8  call    cs:__imp_HeapAlloc
0x18009d9be  mov     [rbp+57h+var_90], rax
0x18009d9c2  test    rax, rax
0x18009d9c5  jz      short loc_18009D9D8
0x18009d9c7  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009d9ca  mov     rdx, r15; struct CSoapProcessor *
0x18009d9cd  mov     rcx, rax; this
0x18009d9d0  call    ??0CListenerEnumeration@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerEnumeration::CListenerEnumeration(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009d9d5  mov     rbx, rax
0x18009d9d8  jmp     loc_18009DDFE
0x18009d9dd  lea     rdx, aHttpSchemasXml_31; "http://schemas.xmlsoap.org/ws/2004/09/e"...
0x18009d9e4  mov     rcx, rdi; String1
0x18009d9e7  call    wcscmp_0
0x18009d9ec  test    eax, eax
0x18009d9ee  jnz     short loc_18009DA29
0x18009d9f0  mov     [rbp+57h+var_6C], ebx
0x18009d9f3  lea     rax, [rbp+57h+var_6C]
0x18009d9f7  mov     [rbp+57h+arg_18], rax
0x18009d9fb  xor     r8d, r8d
0x18009d9fe  xor     edx, edx
0x18009da00  mov     ecx, 888h
0x18009da05  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009da0a  mov     [rbp+57h+var_90], rax
0x18009da0e  test    rax, rax
0x18009da11  jz      short loc_18009DA24
0x18009da13  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009da16  mov     rdx, r15; struct CSoapProcessor *
0x18009da19  mov     rcx, rax; this
0x18009da1c  call    ??0CListenerPull@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerPull::CListenerPull(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009da21  mov     rbx, rax
0x18009da24  jmp     loc_18009DDFE
0x18009da29  lea     rdx, aHttpSchemasXml_19; "http://schemas.xmlsoap.org/ws/2004/09/e"...
0x18009da30  mov     rcx, rdi; String1
0x18009da33  call    wcscmp_0
0x18009da38  test    eax, eax
0x18009da3a  jnz     short loc_18009DA75
0x18009da3c  mov     [rbp+57h+var_68], ebx
0x18009da3f  lea     rax, [rbp+57h+var_68]
0x18009da43  mov     [rbp+57h+arg_18], rax
0x18009da47  xor     r8d, r8d
0x18009da4a  xor     edx, edx
0x18009da4c  mov     ecx, 880h
0x18009da51  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009da56  mov     [rbp+57h+var_90], rax
0x18009da5a  test    rax, rax
0x18009da5d  jz      short loc_18009DA70
0x18009da5f  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009da62  mov     rdx, r15; struct CSoapProcessor *
0x18009da65  mov     rcx, rax; this
0x18009da68  call    ??0CListenerRelease@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerRelease::CListenerRelease(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009da6d  mov     rbx, rax
0x18009da70  jmp     loc_18009DDFE
0x18009da75  lea     rdx, aHttpSchemasXml_28; "http://schemas.xmlsoap.org/ws/2004/08/e"...
0x18009da7c  mov     rcx, rdi; String1
0x18009da7f  call    wcscmp_0
0x18009da84  test    eax, eax
0x18009da86  jnz     short loc_18009DAC1
0x18009da88  mov     [rbp+57h+var_64], ebx
0x18009da8b  lea     rax, [rbp+57h+var_64]
0x18009da8f  mov     [rbp+57h+arg_18], rax
0x18009da93  xor     r8d, r8d
0x18009da96  xor     edx, edx
0x18009da98  mov     ecx, 0CA8h
0x18009da9d  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18009daa2  mov     [rbp+57h+var_90], rax
0x18009daa6  test    rax, rax
0x18009daa9  jz      short loc_18009DABC
0x18009daab  mov     r8, r14; struct CServiceCommonConfigSettings *
0x18009daae  mov     rdx, r15; struct CSoapProcessor *
0x18009dab1  mov     rcx, rax; this
0x18009dab4  call    ??0CListenerSubscription@@QEAA@PEAVCSoapProcessor@@PEAVCServiceCommonConfigSettings@@@Z; CListenerSubscription::CListenerSubscription(CSoapProcessor *,CServiceCommonConfigSettings *)
0x18009dab9  mov     rbx, rax
0x18009dabc  jmp     loc_18009DDFE
0x18009dac1  lea     rdx, aHttpSchemasXml_11; "http://schemas.xmlsoap.org/ws/2004/08/e"...
0x18009dac8  mov     rcx, rdi; String1
0x18009dacb  call    wcscmp_0
  ... truncated ...
```
