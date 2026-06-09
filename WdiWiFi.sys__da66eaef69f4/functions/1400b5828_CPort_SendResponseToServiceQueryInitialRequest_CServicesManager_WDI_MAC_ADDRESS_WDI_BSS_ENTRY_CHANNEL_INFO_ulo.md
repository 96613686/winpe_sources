# CPort::SendResponseToServiceQueryInitialRequest(CServicesManager *,_WDI_MAC_ADDRESS *,_WDI_BSS_ENTRY_CHANNEL_INFO *,ulong,_DOT11_ANQP_ACTION_FRAME *)

- ea: `0x1400b5828`
- end: `0x1400b5e73`
- name: `?SendResponseToServiceQueryInitialRequest@CPort@@QEAAXPEAVCServicesManager@@PEAU_WDI_MAC_ADDRESS@@PEAU_WDI_BSS_ENTRY_CHANNEL_INFO@@KPEAU_DOT11_ANQP_ACTION_FRAME@@@Z`
- size: `1611`
- prototype: `void __fastcall(CPort *this, struct CServicesManager *, struct _WDI_MAC_ADDRESS *, struct _WDI_BSS_ENTRY_CHANNEL_INFO *, unsigned int, struct _DOT11_ANQP_ACTION_FRAME *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x140060f48`

## callees

- `0x14000b43c`
- `0x1400109f8`
- `0x140012214`
- `0x140017a90`
- `0x140023ae0`
- `0x140034e04`
- `0x140034ec4`
- `0x14005a090`
- `0x1400718cc`
- `0x1400884a0`
- `0x1400b5318`
- `0x1400b5828`
- `0x1400d7e2c`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400b5ba5`
- `ntoskrnl!ExAllocatePool2` at `0x1400b5ba5`

## pseudocode

```c
void __fastcall CPort::SendResponseToServiceQueryInitialRequest(
        CPort *this,
        struct CServicesManager *a2,
        struct _WDI_MAC_ADDRESS *a3,
        struct _WDI_BSS_ENTRY_CHANNEL_INFO *a4,
        unsigned int a5,
        struct _DOT11_ANQP_ACTION_FRAME *a6)
{
  struct _DOT11_ANQP_ACTION_FRAME *v9; // rsi
  char v10; // al
  char v11; // di
  unsigned int v12; // r14d
  bool v13; // zf
  int PortIdForPortType; // eax
  int v15; // edx
  __int64 v16; // r10
  __int64 v17; // r11
  int v18; // r8d
  IPropertyCacheDirectory *v19; // rcx
  CPropertyCache *v20; // rax
  int PropertyBuffer; // eax
  int v22; // edx
  int v23; // r8d
  int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // r14d
  int v28; // r8d
  unsigned __int8 *Pool2; // r12
  int v30; // eax
  int v31; // edx
  int v32; // r8d
  int v33; // edx
  unsigned int v34; // [rsp+60h] [rbp-10h]
  unsigned __int8 *v35; // [rsp+68h] [rbp-8h] BYREF
  CServicesManager *v36; // [rsp+B8h] [rbp+48h]

  v36 = a2;
  v35 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      296,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  v9 = a6;
  if ( a6->InitialRequest.AdvertisementProtocolElement.AdvertisementProtocol[0].AdvertisementProtocolID )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        297,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        a6->InitialRequest.AdvertisementProtocolElement.ElementID,
        a6->InitialRequest.AdvertisementProtocolElement.AdvertisementProtocol[0].AdvertisementProtocolID);
    }
    v10 = CPort::SendANQPQueryResponse(
            this,
            DOT11_PUBLIC_ACTION_FRAME_TYPE_GAS_INITIAL_RESPONSE,
            v9->DialogToken,
            v9->InitialRequest.AdvertisementProtocolElement.AdvertisementProtocol[0].AdvertisementProtocolID,
            0x3Bu,
            0,
            0,
            a3,
            a4->BandId,
            a4->ChannelNumber,
            0,
            0);
    goto LABEL_9;
  }
  v12 = a6->InitialResponse.AdvertisementProtocolElement.ElementID
      + (a6->InitialResponse.AdvertisementProtocolElement.Length << 8);
  v34 = v12;
  if ( a5 < v12 + 9 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        298,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        a5,
        a6->InitialResponse.AdvertisementProtocolElement.ElementID + 9);
    }
    v11 = 21;
    goto LABEL_47;
  }
  v13 = this->m_WfcPortType == WfcPortTypeWFDRole;
  LOWORD(a6) = this->m_WfcPortId;
  if ( v13 )
  {
    PortIdForPortType = CAdapter::GetPortIdForPortType(this->m_pAdapter, WfcPortTypeWFDDevice, (unsigned __int16 *)&a6);
    v11 = PortIdForPortType;
    if ( PortIdForPortType )
    {
      if ( *(_QWORD *)&WPP_RECORDER_INITIALIZED == v16 )
        return;
      v18 = v15 - 3;
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_D(WPP_GLOBAL_Control->DeviceExtension, v15, v18, 299, v17, PortIdForPortType);
      goto LABEL_47;
    }
  }
  v19 = &this->m_pAdapter->IPropertyCacheDirectory;
  LODWORD(a6) = 0;
  v20 = (CPropertyCache *)((__int64 (__fastcall *)(IPropertyCacheDirectory *))v19->GetPortPropertyCache)(v19);
  PropertyBuffer = CPropertyCache::GetPropertyBuffer(v20, 0x3Au, (unsigned int *)&a6, &v35);
  v11 = PropertyBuffer;
  if ( PropertyBuffer )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return;
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      1,
      300,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      PropertyBuffer);
    goto LABEL_47;
  }
  if ( (unsigned int)a6 >= 0x28 )
  {
    v22 = (int)v35;
    if ( (unsigned int)a6 >= *((unsigned int *)v35 + 4)
                           + 40LL
                           + *((unsigned int *)v35 + 7)
                           + (unsigned __int64)*((unsigned int *)v35 + 9) )
    {
      LODWORD(a6) = 0;
      v24 = WFDSvcEncodeANQPResponse(v12, (__int64)&a6, 0);
      v27 = (int)a6;
      v11 = v24;
      if ( v24 != -1073741789 || !(_DWORD)a6 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return;
        LOBYTE(v25) = 2;
        WPP_RECORDER_SF_Dd(
          WPP_GLOBAL_Control->DeviceExtension,
          v25,
          v26,
          302,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          v24,
          (char)a6);
        goto LABEL_47;
      }
      if ( (unsigned int)a6 > 0xFFFF )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v25) = 2;
          WPP_RECORDER_SF_Ld(
            WPP_GLOBAL_Control->DeviceExtension,
            v25,
            v26,
            303,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            (char)a6,
            255);
        }
        v11 = CPort::SendANQPQueryResponse(
                this,
                DOT11_PUBLIC_ACTION_FRAME_TYPE_GAS_INITIAL_RESPONSE,
                v9->DialogToken,
                v9->InitialRequest.AdvertisementProtocolElement.AdvertisementProtocol[0].AdvertisementProtocolID,
                0x3Fu,
                0,
                0,
                a3,
                a4->BandId,
                a4->ChannelNumber,
                0,
                0);
        goto LABEL_47;
      }
      Pool2 = (unsigned __int8 *)ExAllocatePool2(64, (unsigned int)a6, 1198089303);
      if ( !Pool2 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)a2,
            v28,
            304,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            v27);
        }
        v11 = -102;
        goto LABEL_47;
      }
      LODWORD(a6) = v27;
      v30 = WFDSvcEncodeANQPResponse(v34, (__int64)&a6, Pool2);
      v11 = v30;
      if ( v30 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v31) = 2;
          WPP_RECORDER_SF_dDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v31,
            v32,
            305,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            v30,
            v27,
            (char)a6);
        }
      }
      else if ( (unsigned int)a6 >= v36->m_MaxResponseFragmentSize )
      {
        if ( CServicesManager::AddComebackResponseContext(
               v36,
               a3,
               v9->DialogToken,
               (struct _DOT11_AVERTISEMENT_PROTOCOL_ELEMENT *)&v9->InitialRequest,
               (unsigned __int16)a6,
               Pool2) )
        {
          v10 = CPort::SendANQPQueryResponse(
                  this,
                  DOT11_PUBLIC_ACTION_FRAME_TYPE_GAS_INITIAL_RESPONSE,
                  v9->DialogToken,
                  v9->InitialRequest.AdvertisementProtocolElement.AdvertisementProtocol[0].AdvertisementProtocolID,
                  0,
                  0,
                  1u,
                  a3,
                  a4->BandId,
                  a4->ChannelNumber,
                  0,
                  0);
LABEL_9:
          v11 = v10;
          goto LABEL_47;
        }
        v11 = -102;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v33) = 2;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v33,
            1,
            306,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            154);
        }
      }
      else
      {
        v11 = CPort::SendANQPQueryResponse(
                this,
                DOT11_PUBLIC_ACTION_FRAME_TYPE_GAS_INITIAL_RESPONSE,
                v9->DialogToken,
                v9->InitialRequest.AdvertisementProtocolElement.AdvertisementProtocol[0].AdvertisementProtocolID,
                0,
                0,
                0,
                a3,
                a4->BandId,
                a4->ChannelNumber,
                (unsigned __int16)a6,
                Pool2);
      }
      operator delete(Pool2);
      goto LABEL_47;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return;
  LOBYTE(v22) = 2;
  v11 = 21;
  WPP_RECORDER_SF_d(
    WPP_GLOBAL_Control->DeviceExtension,
    v22,
    v23,
    301,
    (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
    (char)a6);
LABEL_47:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      307,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v11);
  }
}

```

## disassembly

```asm
0x1400b5828  mov     rax, rsp
0x1400b582b  mov     [rax+8], rbx
0x1400b582f  mov     [rax+20h], r9
0x1400b5833  mov     [rax+18h], r8
0x1400b5837  mov     [rax+10h], rdx
0x1400b583b  push    rbp
0x1400b583c  push    rsi
0x1400b583d  push    rdi
0x1400b583e  push    r12
0x1400b5840  push    r13
0x1400b5842  push    r14
0x1400b5844  push    r15
0x1400b5846  mov     rbp, rsp
0x1400b5849  sub     rsp, 70h
0x1400b584d  xor     r15d, r15d
0x1400b5850  mov     r12, r9
0x1400b5853  mov     [rbp+var_8], r15
0x1400b5857  mov     bl, r15b
0x1400b585a  mov     rdi, r8
0x1400b585d  mov     r13, rcx
0x1400b5860  lea     r10, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b5867  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400b586e  lea     r11, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b5875  jz      short loc_1400B58B5
0x1400b5877  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b587e  cmp     byte ptr [rcx+29h], 5
0x1400b5882  jnb     short loc_1400B588B
0x1400b5884  cmp     [rcx+48h], r15w
0x1400b5889  jz      short loc_1400B58B5
0x1400b588b  mov     rcx, [rcx+40h]
0x1400b588f  mov     r9d, 128h
0x1400b5895  mov     r8d, 1
0x1400b589b  mov     qword ptr [rsp+70h+var_50], r11
0x1400b58a0  mov     dl, 5
0x1400b58a2  call    WPP_RECORDER_SF_
0x1400b58a7  lea     r10, WPP_RECORDER_INITIALIZED
0x1400b58ae  lea     r11, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b58b5  mov     rsi, [rbp+arg_28]
0x1400b58b9  movzx   eax, byte ptr [rsi+6]
0x1400b58bd  test    al, al
0x1400b58bf  jz      loc_1400B594C
0x1400b58c5  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x1400b58cc  jz      short loc_1400B58F7
0x1400b58ce  movzx   ecx, byte ptr [rsi+3]
0x1400b58d2  mov     r9d, 129h
0x1400b58d8  mov     dword ptr [rsp+70h+var_40], eax
0x1400b58dc  mov     dl, 2
0x1400b58de  mov     dword ptr [rsp+70h+var_48], ecx
0x1400b58e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b58e9  mov     qword ptr [rsp+70h+var_50], r11
0x1400b58ee  mov     rcx, [rcx+40h]
0x1400b58f2  call    WPP_RECORDER_SF_Ld
0x1400b58f7  mov     eax, [r12]
0x1400b58fb  mov     [rsp+70h+var_18], r15; unsigned __int8 *
0x1400b5900  mov     [rsp+70h+var_20], r15w; unsigned __int16
0x1400b5906  mov     [rsp+70h+var_28], eax; unsigned int
0x1400b590a  mov     eax, [r12+4]
0x1400b590f  mov     [rsp+70h+var_30], eax; enum _WDI_BAND_ID
0x1400b5913  mov     [rsp+70h+var_38], rdi; struct _WDI_MAC_ADDRESS *
0x1400b5918  mov     [rsp+70h+var_40], r15w; unsigned __int16
0x1400b591e  mov     byte ptr [rsp+70h+var_48], bl; union DOT11_ANQP_FRAGMENT_ID
0x1400b5922  mov     [rsp+70h+var_50], 3Bh ; ';'; unsigned __int16
0x1400b5929  mov     r9b, [rsi+6]; unsigned __int8
0x1400b592d  mov     edx, 0Bh; enum _DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE
0x1400b5932  mov     r8b, [rsi+2]; unsigned __int8
0x1400b5936  mov     rcx, r13; this
0x1400b5939  call    ?SendANQPQueryResponse@CPort@@QEAAHW4_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE@@EEGTDOT11_ANQP_FRAGMENT_ID@@GPEAU_WDI_MAC_ADDRESS@@W4_WDI_BAND_ID@@IGPEAE@Z; CPort::SendANQPQueryResponse(_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE,uchar,uchar,ushort,DOT11_ANQP_FRAGMENT_ID,ushort,_WDI_MAC_ADDRESS *,_WDI_BAND_ID,uint,ushort,uchar *)
0x1400b593e  mov     edi, eax
0x1400b5940  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b5947  jmp     loc_1400B5E16
0x1400b594c  movzx   eax, byte ptr [rsi+7]
0x1400b5950  movzx   r14d, byte ptr [rsi+8]
0x1400b5955  mov     ecx, [rbp+arg_20]
0x1400b5958  shl     r14d, 8
0x1400b595c  add     r14d, eax
0x1400b595f  mov     [rbp+var_10], r14d
0x1400b5963  lea     eax, [r14+9]
0x1400b5967  cmp     ecx, eax
0x1400b5969  jnb     short loc_1400B59A0
0x1400b596b  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x1400b5972  jz      short loc_1400B5999
0x1400b5974  mov     dword ptr [rsp+70h+var_40], eax
0x1400b5978  mov     r9d, 12Ah
0x1400b597e  mov     dword ptr [rsp+70h+var_48], ecx
0x1400b5982  mov     dl, 2
0x1400b5984  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b598b  mov     qword ptr [rsp+70h+var_50], r11
0x1400b5990  mov     rcx, [rcx+40h]
0x1400b5994  call    WPP_RECORDER_SF_Ld
0x1400b5999  mov     edi, 0C0010015h
0x1400b599e  jmp     short loc_1400B5940
0x1400b59a0  cmp     dword ptr [r13+68h], 8
0x1400b59a5  movzx   edx, word ptr [r13+64h]
0x1400b59aa  mov     word ptr [rbp+arg_28], dx
0x1400b59ae  jnz     short loc_1400B5A03
0x1400b59b0  mov     rcx, [r13+58h]; this
0x1400b59b4  lea     r8, [rbp+arg_28]; unsigned __int16 *
0x1400b59b8  mov     edx, 4; enum _WFC_PORT_TYPE
0x1400b59bd  call    ?GetPortIdForPortType@CAdapter@@QEAAHW4_WFC_PORT_TYPE@@PEAG@Z; CAdapter::GetPortIdForPortType(_WFC_PORT_TYPE,ushort *)
0x1400b59c2  mov     edi, eax
0x1400b59c4  test    eax, eax
0x1400b59c6  jz      short loc_1400B59FF
0x1400b59c8  cmp     cs:WPP_RECORDER_INITIALIZED, r10; __annotation("TMF:",
0x1400b59cf  jz      loc_1400B5E5A
0x1400b59d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b59dc  lea     r8d, [rdx-3]
0x1400b59e0  mov     dword ptr [rsp+70h+var_48], eax
0x1400b59e4  mov     r9d, 12Bh
0x1400b59ea  mov     dl, 2
0x1400b59ec  mov     qword ptr [rsp+70h+var_50], r11
0x1400b59f1  mov     rcx, [rcx+40h]
0x1400b59f5  call    WPP_RECORDER_SF_D
0x1400b59fa  jmp     loc_1400B5940
0x1400b59ff  movzx   edx, word ptr [rbp+arg_28]
0x1400b5a03  mov     rcx, [r13+58h]
0x1400b5a07  add     rcx, 8
0x1400b5a0b  mov     dword ptr [rbp+arg_28], r15d
0x1400b5a0f  mov     rax, [rcx]
0x1400b5a12  mov     rax, [rax]
0x1400b5a15  call    _guard_dispatch_icall
0x1400b5a1a  lea     r9, [rbp+var_8]; unsigned __int8 **
0x1400b5a1e  mov     edx, 3Ah ; ':'; unsigned int
0x1400b5a23  lea     r8, [rbp+arg_28]; unsigned int *
0x1400b5a27  mov     rcx, rax; this
0x1400b5a2a  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400b5a2f  mov     edi, eax
0x1400b5a31  test    eax, eax
0x1400b5a33  jz      short loc_1400B5A7C
0x1400b5a35  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b5a3c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b5a43  jz      loc_1400B5E5A
0x1400b5a49  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5a50  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b5a57  mov     r9d, 12Ch
0x1400b5a5d  mov     dword ptr [rsp+70h+var_48], edi
0x1400b5a61  mov     r8d, 1
0x1400b5a67  mov     qword ptr [rsp+70h+var_50], r14
0x1400b5a6c  mov     dl, 2
0x1400b5a6e  mov     rcx, [rcx+40h]
0x1400b5a72  call    WPP_RECORDER_SF_D
0x1400b5a77  jmp     loc_1400B5E16
0x1400b5a7c  mov     r15d, dword ptr [rbp+arg_28]
0x1400b5a80  cmp     r15d, 28h ; '('
0x1400b5a84  jb      loc_1400B5DD5
0x1400b5a8a  mov     rdx, [rbp+var_8]
0x1400b5a8e  mov     eax, [rdx+1Ch]
0x1400b5a91  mov     ecx, [rdx+24h]
0x1400b5a94  add     rcx, rax
0x1400b5a97  mov     eax, [rdx+10h]
0x1400b5a9a  add     rax, 28h ; '('
0x1400b5a9e  add     rcx, rax
0x1400b5aa1  cmp     r15, rcx
0x1400b5aa4  jb      loc_1400B5DD5
0x1400b5aaa  lea     rcx, [rbp+arg_28]
0x1400b5aae  mov     qword ptr [rsp+70h+var_48], 0; unsigned __int8 *
0x1400b5ab7  mov     qword ptr [rsp+70h+var_50], rcx; __int64
0x1400b5abc  mov     r9, rdx
0x1400b5abf  mov     ecx, r14d; unsigned int
0x1400b5ac2  mov     dword ptr [rbp+arg_28], 0
0x1400b5ac9  mov     r8d, r15d
0x1400b5acc  lea     rdx, [rsi+9]
0x1400b5ad0  call    WFDSvcEncodeANQPResponse
0x1400b5ad5  mov     r14d, dword ptr [rbp+arg_28]
0x1400b5ad9  mov     edi, eax
0x1400b5adb  cmp     eax, 0C0000023h
0x1400b5ae0  jnz     loc_1400B5D92
0x1400b5ae6  test    r14d, r14d
0x1400b5ae9  jz      loc_1400B5D92
0x1400b5aef  mov     ecx, 0FFFFh
0x1400b5af4  cmp     r14d, ecx
0x1400b5af7  jbe     loc_1400B5B97
0x1400b5afd  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b5b04  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b5b0b  jz      short loc_1400B5B3C
0x1400b5b0d  mov     dword ptr [rsp+70h+var_40], ecx
0x1400b5b11  mov     r9d, 12Fh
0x1400b5b17  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5b1e  mov     dl, 2
0x1400b5b20  mov     dword ptr [rsp+70h+var_48], r14d
0x1400b5b25  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b5b2c  mov     qword ptr [rsp+70h+var_50], r14
0x1400b5b31  mov     rcx, [rcx+40h]
0x1400b5b35  call    WPP_RECORDER_SF_Ld
0x1400b5b3a  jmp     short loc_1400B5B43
0x1400b5b3c  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b5b43  mov     eax, [r12]
0x1400b5b47  xor     r15d, r15d
0x1400b5b4a  mov     rdi, [rbp+arg_10]
0x1400b5b4e  mov     rcx, r13; this
0x1400b5b51  mov     r9b, [rsi+6]; unsigned __int8
0x1400b5b55  mov     r8b, [rsi+2]; unsigned __int8
0x1400b5b59  mov     [rsp+70h+var_18], r15; unsigned __int8 *
0x1400b5b5e  lea     edx, [r15+0Bh]; enum _DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE
0x1400b5b62  mov     [rsp+70h+var_20], r15w; unsigned __int16
0x1400b5b68  mov     [rsp+70h+var_28], eax; unsigned int
0x1400b5b6c  mov     eax, [r12+4]
0x1400b5b71  mov     [rsp+70h+var_30], eax; enum _WDI_BAND_ID
0x1400b5b75  mov     [rsp+70h+var_38], rdi; struct _WDI_MAC_ADDRESS *
0x1400b5b7a  mov     [rsp+70h+var_40], r15w; unsigned __int16
0x1400b5b80  mov     byte ptr [rsp+70h+var_48], bl; union DOT11_ANQP_FRAGMENT_ID
0x1400b5b84  mov     [rsp+70h+var_50], 3Fh ; '?'; unsigned __int16
0x1400b5b8b  call    ?SendANQPQueryResponse@CPort@@QEAAHW4_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE@@EEGTDOT11_ANQP_FRAGMENT_ID@@GPEAU_WDI_MAC_ADDRESS@@W4_WDI_BAND_ID@@IGPEAE@Z; CPort::SendANQPQueryResponse(_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE,uchar,uchar,ushort,DOT11_ANQP_FRAGMENT_ID,ushort,_WDI_MAC_ADDRESS *,_WDI_BAND_ID,uint,ushort,uchar *)
0x1400b5b90  mov     edi, eax
0x1400b5b92  jmp     loc_1400B5E16
0x1400b5b97  mov     rdx, r14
0x1400b5b9a  mov     ecx, 40h ; '@'
0x1400b5b9f  mov     r8d, 47696457h
0x1400b5ba5  call    cs:__imp_ExAllocatePool2
0x1400b5bac  nop     dword ptr [rax+rax+00h]
0x1400b5bb1  mov     r12, rax
0x1400b5bb4  test    rax, rax
0x1400b5bb7  jnz     short loc_1400B5C05
0x1400b5bb9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b5bc0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b5bc7  jz      short loc_1400B5BF4
0x1400b5bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5bd0  mov     r9d, 130h
0x1400b5bd6  mov     dword ptr [rsp+70h+var_48], r14d
0x1400b5bdb  mov     dl, 2
0x1400b5bdd  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b5be4  mov     qword ptr [rsp+70h+var_50], r14
0x1400b5be9  mov     rcx, [rcx+40h]
0x1400b5bed  call    WPP_RECORDER_SF_d
0x1400b5bf2  jmp     short loc_1400B5BFB
0x1400b5bf4  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b5bfb  mov     edi, 0C000009Ah
0x1400b5c00  jmp     loc_1400B5E13
0x1400b5c05  mov     r9, [rbp+var_8]
0x1400b5c09  lea     rax, [rbp+arg_28]
0x1400b5c0d  mov     ecx, [rbp+var_10]; unsigned int
0x1400b5c10  lea     rdx, [rsi+9]
0x1400b5c14  mov     qword ptr [rsp+70h+var_48], r12; unsigned __int8 *
0x1400b5c19  mov     r8d, r15d
0x1400b5c1c  mov     qword ptr [rsp+70h+var_50], rax; __int64
0x1400b5c21  mov     dword ptr [rbp+arg_28], r14d
0x1400b5c25  call    WFDSvcEncodeANQPResponse
0x1400b5c2a  xor     r15d, r15d
0x1400b5c2d  mov     edi, eax
0x1400b5c2f  test    eax, eax
0x1400b5c31  jz      short loc_1400B5C7D
0x1400b5c33  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b5c3a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b5c41  jz      loc_1400B5CDC
0x1400b5c47  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5c4e  mov     r9d, 131h
0x1400b5c54  mov     eax, dword ptr [rbp+arg_28]
0x1400b5c57  mov     dl, 2
0x1400b5c59  mov     dword ptr [rsp+70h+var_38], eax
0x1400b5c5d  mov     dword ptr [rsp+70h+var_40], r14d
0x1400b5c62  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b5c69  mov     rcx, [rcx+40h]
0x1400b5c6d  mov     dword ptr [rsp+70h+var_48], edi
0x1400b5c71  mov     qword ptr [rsp+70h+var_50], r14
0x1400b5c76  call    WPP_RECORDER_SF_dDD
0x1400b5c7b  jmp     short loc_1400B5CE3
0x1400b5c7d  mov     rcx, [rbp+arg_8]; this
0x1400b5c81  mov     r8d, dword ptr [rbp+arg_28]
0x1400b5c85  mov     rdi, [rbp+arg_10]
0x1400b5c89  movzx   eax, word ptr [rcx+1Ch]
0x1400b5c8d  cmp     r8d, eax
0x1400b5c90  jnb     short loc_1400B5CF0
0x1400b5c92  mov     r9b, [rsi+6]; unsigned __int8
0x1400b5c96  mov     edx, 0Bh; enum _DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE
0x1400b5c9b  mov     [rsp+70h+var_18], r12; unsigned __int8 *
0x1400b5ca0  mov     rcx, r13; this
0x1400b5ca3  mov     [rsp+70h+var_20], r8w; unsigned __int16
0x1400b5ca9  mov     r8, [rbp+arg_18]
0x1400b5cad  mov     eax, [r8]
0x1400b5cb0  mov     [rsp+70h+var_28], eax; unsigned int
0x1400b5cb4  mov     eax, [r8+4]
0x1400b5cb8  mov     r8b, [rsi+2]; unsigned __int8
0x1400b5cbc  mov     [rsp+70h+var_30], eax; enum _WDI_BAND_ID
0x1400b5cc0  mov     [rsp+70h+var_38], rdi; struct _WDI_MAC_ADDRESS *
0x1400b5cc5  mov     [rsp+70h+var_40], r15w; unsigned __int16
0x1400b5ccb  mov     byte ptr [rsp+70h+var_48], bl; union DOT11_ANQP_FRAGMENT_ID
0x1400b5ccf  mov     [rsp+70h+var_50], r15w; unsigned __int16
0x1400b5cd5  call    ?SendANQPQueryResponse@CPort@@QEAAHW4_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE@@EEGTDOT11_ANQP_FRAGMENT_ID@@GPEAU_WDI_MAC_ADDRESS@@W4_WDI_BAND_ID@@IGPEAE@Z; CPort::SendANQPQueryResponse(_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE,uchar,uchar,ushort,DOT11_ANQP_FRAGMENT_ID,ushort,_WDI_MAC_ADDRESS *,_WDI_BAND_ID,uint,ushort,uchar *)
0x1400b5cda  mov     edi, eax
0x1400b5cdc  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b5ce3  mov     rcx, r12; void *
0x1400b5ce6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b5ceb  jmp     loc_1400B5E16
0x1400b5cf0  mov     qword ptr [rsp+70h+var_48], r12; unsigned __int8 *
0x1400b5cf5  lea     r9, [rsi+3]; struct _DOT11_AVERTISEMENT_PROTOCOL_ELEMENT *
0x1400b5cf9  mov     [rsp+70h+var_50], r8w; unsigned __int16
0x1400b5cff  mov     rdx, rdi; struct _WDI_MAC_ADDRESS *
0x1400b5d02  mov     r8b, [rsi+2]; unsigned __int8
0x1400b5d06  call    ?AddComebackResponseContext@CServicesManager@@QEAAPEAVCServiceComebackResponseContext@@PEAU_WDI_MAC_ADDRESS@@EPEAU_DOT11_AVERTISEMENT_PROTOCOL_ELEMENT@@GPEAE@Z; CServicesManager::AddComebackResponseContext(_WDI_MAC_ADDRESS *,uchar,_DOT11_AVERTISEMENT_PROTOCOL_ELEMENT *,ushort,uchar *)
0x1400b5d0b  test    rax, rax
0x1400b5d0e  jnz     short loc_1400B5D59
0x1400b5d10  mov     edi, 0C000009Ah
0x1400b5d15  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400b5d1c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b5d23  lea     r14, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x1400b5d2a  jz      short loc_1400B5CE3
0x1400b5d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5d33  mov     r9d, 132h
0x1400b5d39  mov     dword ptr [rsp+70h+var_48], 0C000009Ah
0x1400b5d41  mov     r8d, 1
0x1400b5d47  mov     dl, 2
  ... truncated ...
```
