# CRdpUdpTransport::OnICETransportOpened(ComPlainSmartPtr<IRdpIceAdapter> const &,int,_GUID,uint)

- ea: `0x18012b230`
- end: `0x18012bdba`
- name: `?OnICETransportOpened@CRdpUdpTransport@@UEAAJAEBV?$ComPlainSmartPtr@UIRdpIceAdapter@@@@HU_GUID@@I@Z`
- size: `2954`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001aa0`
- `0x1800080d0`
- `0x180078c20`
- `0x18007a400`
- `0x1801287b0`
- `0x1801287d0`
- `0x18012b230`
- `0x18012d7f0`
- `0x180146770`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b403`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b4be`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012ba12`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012bcb3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b403`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012b4be`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012ba12`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012bcb3`

## string_xrefs

- `0x18012b2ed`: `OnICETransportOpened`
- `0x18012b522`: `OnICETransportOpened`
- `0x18012b5d8`: `OnICETransportOpened`
- `0x18012b781`: `OnICETransportOpened`
- `0x18012b84c`: `OnICETransportOpened`
- `0x18012bb04`: `OnICETransportOpened`
- `0x18012bbba`: `OnICETransportOpened`
- `0x18012bcf9`: `OnICETransportOpened`
- `0x18012b2d1`: `CRdpUdpTransport::OnICETransportOpened:  spRdpIceAdapter is NULL`
- `0x18012b507`: `Failed to create CRdpIceLocalEndpoint instance`
- `0x18012b831`: `Failed to create CRdpIceLocalEndpoint instance`
- `0x18012bae9`: `ICE:SetPropertyBool failed for CONN_PROPERTY_SMILES_TRANSPORT_OPENED`
- `0x18012baba`: `SmilesTransportOpened`

## pseudocode

```c
__int64 __fastcall CRdpUdpTransport::OnICETransportOpened(
        __int64 a1,
        __int64 *a2,
        int a3,
        const char *a4,
        unsigned int a5)
{
  struct IUnknown *v7; // rdi
  int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int16 *v17; // rdx
  void *p_EventDescriptor; // rax
  unsigned int i; // ebx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  struct IUnknownVtbl *lpVtbl; // rax
  const char *v24; // rcx
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rcx
  int v32; // eax
  struct SessionStartupCtl *v33; // rbx
  struct IUnknown *v34; // rcx
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-D8h]
  const char **v37; // [rsp+38h] [rbp-D0h]
  const char **v38; // [rsp+48h] [rbp-C0h]
  EVENT_DESCRIPTOR *v39; // [rsp+50h] [rbp-B8h]
  unsigned int v40; // [rsp+58h] [rbp-B0h] BYREF
  int v41; // [rsp+5Ch] [rbp-ACh] BYREF
  const char *v42; // [rsp+60h] [rbp-A8h] BYREF
  struct IUnknown *v43; // [rsp+68h] [rbp-A0h] BYREF
  struct SessionStartupCtl *v44; // [rsp+70h] [rbp-98h] BYREF
  const char *v45; // [rsp+78h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v47[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v48; // [rsp+98h] [rbp-70h] BYREF
  int v49; // [rsp+A8h] [rbp-60h]
  _OWORD v50[2]; // [rsp+ACh] [rbp-5Ch] BYREF
  struct _EVENT_DATA_DESCRIPTOR v51[8]; // [rsp+D8h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+158h] [rbp+50h] BYREF
  __int16 *v53; // [rsp+168h] [rbp+60h]
  int v54; // [rsp+170h] [rbp+68h]
  int v55; // [rsp+174h] [rbp+6Ch]
  const char *v56; // [rsp+178h] [rbp+70h]
  __int64 v57; // [rsp+180h] [rbp+78h]
  struct _EVENT_DATA_DESCRIPTOR v58; // [rsp+188h] [rbp+80h] BYREF
  __int16 *v59; // [rsp+198h] [rbp+90h]
  int v60; // [rsp+1A0h] [rbp+98h]
  int v61; // [rsp+1A4h] [rbp+9Ch]
  const char *v62; // [rsp+1A8h] [rbp+A0h]
  __int64 v63; // [rsp+1B0h] [rbp+A8h]
  const char **v64; // [rsp+1B8h] [rbp+B0h]
  __int64 v65; // [rsp+1C0h] [rbp+B8h]
  const char *v66; // [rsp+1C8h] [rbp+C0h]
  __int64 v67; // [rsp+1D0h] [rbp+C8h]
  unsigned int *v68; // [rsp+1D8h] [rbp+D0h]
  __int64 v69; // [rsp+1E0h] [rbp+D8h]
  const char *v70; // [rsp+1E8h] [rbp+E0h]
  __int64 v71; // [rsp+1F0h] [rbp+E8h]
  const char *v72; // [rsp+1F8h] [rbp+F0h]
  __int64 v73; // [rsp+200h] [rbp+F8h]
  wchar_t Buffer[264]; // [rsp+208h] [rbp+100h] BYREF

  v7 = 0;
  v49 = 0;
  memset(v50, 0, sizeof(v50));
  v43 = 0;
  v48 = 0;
  memset(v51, 0, sizeof(v51));
  if ( !*a2 )
  {
    v9 = -2147467261;
    if ( (unsigned int)CallbackContext > 2 )
    {
      EventDescriptor.Keyword = 0;
      v72 = "CRdpUdpTransport::OnICETransportOpened:  spRdpIceAdapter is NULL";
      v47[0] = 476;
      v70 = "OnICETransportOpened";
      v41 = -2147467261;
      v68 = v47;
      v73 = 65;
      v66 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
      v71 = 21;
      v64 = (const char **)&v41;
      v69 = 4;
      v62 = "Error condition failed";
      *(_DWORD *)&EventDescriptor.Level = 2;
      v58.Ptr = (ULONGLONG)off_1801E7010;
      v67 = 79;
      v65 = 4;
      v63 = 23;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      v58.Size = *(unsigned __int16 *)off_1801E7010;
      v59 = &word_1801CFF36;
      v58.Reserved = 2;
      v60 = 59;
      v61 = 1;
      v40 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &v58);
    }
    goto LABEL_57;
  }
  if ( a3 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      EventDescriptor.Keyword = 0;
      v56 = "Creating Ice local endpoint";
      *(_DWORD *)&EventDescriptor.Level = 4;
      v52.Ptr = (ULONGLONG)off_1801E7010;
      v57 = 28;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      v52.Size = *(unsigned __int16 *)off_1801E7010;
      v53 = &word_1801D25A6;
      v52.Reserved = 2;
      v54 = 19;
      v55 = 1;
      v40 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v52);
    }
    v10 = a1 - 8;
    if ( a1 == 80 )
      v10 = 0;
    v11 = CRdpUdpIceLocalEndpoint_CreateInstance(v10, 0, a2, *(_QWORD *)(a1 + 88), &v43);
    v9 = v11;
    if ( v11 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v40 = 483;
        v44 = (struct SessionStartupCtl *)"Failed to create CRdpIceLocalEndpoint instance";
        v41 = v11;
        *(_QWORD *)v47 = "OnICETransportOpened";
        v45 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
        v42 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)qword_1801D0BC0,
          v12,
          v13,
          (__int64)&v42,
          (__int64)&v41,
          (__int64)&v45,
          (__int64)&v40,
          (__int64)v47,
          (__int64)&v44);
      }
      goto LABEL_12;
    }
    v7 = v43;
    v9 = CRdpUdpTransport::RegisterReverseConnectEndpoint((CRdpUdpTransport *)(a1 - 32), v43);
    if ( v9 >= 0 )
    {
      for ( i = 0; i < 8; ++i )
      {
        LODWORD(UserData) = i;
        snwprintf_s(Buffer, 0x104u, 0x103u, L"%s%d", L"MultiTransportCookieHash", UserData);
        (*(void (__fastcall **)(_QWORD, wchar_t *, char *))(**(_QWORD **)(a1 + 40) + 40LL))(
          *(_QWORD *)(a1 + 40),
          Buffer,
          (char *)v50 + 4 * (int)i);
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        *(_QWORD *)&EventDescriptor.Id = v50;
        LOWORD(EventDescriptor.Keyword) = 32;
        v42 = "UDP set cookie hash to the localEndPoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperArray<1>>(
          v20,
          (unsigned int)byte_1801D1D35,
          v21,
          v22,
          (__int64)&v42,
          (__int64)&EventDescriptor);
      }
      lpVtbl = v7->lpVtbl;
      v24 = *(const char **)(a1 + 376);
      v42 = v24;
      AddRef = lpVtbl[1].AddRef;
      if ( v24 )
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v24 + 8LL))(v24);
      v9 = ((__int64 (__fastcall *)(struct IUnknown *, struct _EVENT_DATA_DESCRIPTOR *, _QWORD, __int64, const char **, int, __int128 *, __int64))AddRef)(
             v7,
             v51,
             0,
             a1 + 392,
             &v42,
             257,
             &v48,
             a1 + 232);
      if ( v9 >= 0 )
      {
        CRdpUdpTransport::EnableTransportTimer((CRdpUdpTransport *)(a1 - 8));
        goto LABEL_57;
      }
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_57;
      v40 = 508;
      v42 = "Outgoing connection request failed.";
      v17 = (__int16 *)qword_1801CFEE0;
      v45 = "OnICETransportOpened";
      v44 = (struct SessionStartupCtl *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
      v43 = (struct IUnknown *)"Error HResult failed";
      v39 = (EVENT_DESCRIPTOR *)&v42;
      v38 = &v45;
      v37 = (const char **)&v44;
      p_EventDescriptor = &v43;
    }
    else
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_57;
      v40 = 486;
      v42 = "Failed to RegisterReverseConnectEndpoint";
      v17 = (__int16 *)&dword_1801D26AC;
      v45 = "OnICETransportOpened";
      v44 = (struct SessionStartupCtl *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
      v43 = (struct IUnknown *)"Error HResult failed";
      v39 = (EVENT_DESCRIPTOR *)&v42;
      v38 = &v45;
      v37 = (const char **)&v44;
      p_EventDescriptor = &v43;
    }
LABEL_56:
    v41 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v14,
      (_DWORD)v17,
      v15,
      v16,
      (__int64)p_EventDescriptor,
      (__int64)&v41,
      (__int64)v37,
      (__int64)&v40,
      (__int64)v38,
      (__int64)v39);
    goto LABEL_57;
  }
  v26 = a1 - 80;
  v27 = a1 - 8;
  if ( !v26 )
    v27 = 0;
  v9 = CRdpUdpIceLocalEndpoint_CreateInstance(v27, 1, a2, 0, &v43);
  if ( v9 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v40 = 515;
      v42 = "Failed to create CRdpIceLocalEndpoint instance";
      v41 = v9;
      v45 = "OnICETransportOpened";
      v44 = (struct SessionStartupCtl *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
      *(_QWORD *)v47 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v28,
        (unsigned int)&dword_1801D239C,
        v29,
        v30,
        (__int64)v47,
        (__int64)&v41,
        (__int64)&v44,
        (__int64)&v40,
        (__int64)&v45,
        (__int64)&v42);
      v7 = v43;
      goto LABEL_57;
    }
LABEL_12:
    v7 = v43;
    goto LABEL_57;
  }
  if ( (unsigned int)CallbackContext > 4
    && (qword_1801E7018 & 0x470000000000LL) != 0
    && (qword_1801E7020 & 0x470000000000LL) == qword_1801E7020 )
  {
    v70 = a4;
    v68 = (unsigned int *)"Udp";
    EventDescriptor.Keyword = 0x470000000000LL;
    v66 = "Stack";
    v42 = (const char *)0x1000000;
    v64 = &v42;
    v71 = 16;
    v62 = "Checkpoint";
    *(_DWORD *)&EventDescriptor.Level = 11268;
    v58.Ptr = (ULONGLONG)off_1801E7010;
    v69 = 4;
    v67 = 6;
    v65 = 8;
    v63 = 11;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    v58.Size = *(unsigned __int16 *)off_1801E7010;
    v59 = (__int16 *)byte_1801D2F5D;
    v58.Reserved = 2;
    v60 = 81;
    v61 = 1;
    v40 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &v58);
  }
  v31 = *a2;
  v44 = 0;
  v47[0] = 0;
  v32 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 24LL))(v31, v47);
  v7 = v43;
  if ( v32 >= 0 && (int)SessionCtlBlkManager::Find((SessionCtlBlkManager *)(a1 + 416), v47[0], &v44) >= 0 )
  {
    v33 = v44;
    if ( v44 )
    {
      v34 = (struct IUnknown *)*((_QWORD *)v44 + 2);
      if ( v7 != v34 )
      {
        if ( v34 )
        {
          *((_QWORD *)v44 + 2) = 0;
          ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
        }
        *((_QWORD *)v33 + 2) = v7;
        if ( v7 )
          ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->AddRef)(v7);
        v33 = v44;
      }
      if ( *(_QWORD *)v33 )
      {
        v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)v33 + 64LL))(
               *(_QWORD *)v33,
               L"SmilesTransportOpened",
               1);
        if ( v9 < 0 )
        {
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_57;
          v40 = 536;
          v42 = "ICE:SetPropertyBool failed for CONN_PROPERTY_SMILES_TRANSPORT_OPENED";
          v17 = &word_1801CFDDE;
          v45 = "OnICETransportOpened";
          v43 = (struct IUnknown *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
          *(_QWORD *)&EventDescriptor.Id = "Error HResult failed";
          v39 = (EVENT_DESCRIPTOR *)&v42;
          v38 = &v45;
          v37 = (const char **)&v43;
          p_EventDescriptor = &EventDescriptor;
          goto LABEL_56;
        }
        v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**(_QWORD **)v44 + 72LL))(
               *(_QWORD *)v44,
               L"SmilesInitialTransportType",
               a5);
        if ( v9 < 0 )
        {
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_57;
          v40 = 539;
          *(_QWORD *)&EventDescriptor.Id = "ICE:SetPropertyUnsignedLong failed for CONN_PROPERTY_SMILES_INITIAL_TRANSPORT_TYPE";
          v17 = (__int16 *)byte_1801D0B79;
          v42 = "OnICETransportOpened";
          v45 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
          v43 = (struct IUnknown *)"Error HResult failed";
          v39 = &EventDescriptor;
          v38 = &v42;
          v37 = &v45;
          p_EventDescriptor = &v43;
          goto LABEL_56;
        }
      }
    }
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v57 = 37;
    v56 = "Registering reverse connect endpoint";
    *(_DWORD *)&EventDescriptor.Level = 4;
    v52.Ptr = (ULONGLONG)off_1801E7010;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v52.Size = *(unsigned __int16 *)off_1801E7010;
    v53 = (__int16 *)&byte_1801D05FF;
    v52.Reserved = 2;
    v54 = 19;
    v55 = 1;
    v40 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v52);
  }
  v9 = CRdpUdpTransport::RegisterReverseConnectEndpoint((CRdpUdpTransport *)(a1 - 32), v7);
  if ( v9 < 0 && (unsigned int)CallbackContext > 2 )
  {
    v40 = 546;
    *(_QWORD *)&EventDescriptor.Id = "Failed to register reverse connect endpoint";
    v17 = word_1801D2CDA;
    v42 = "OnICETransportOpened";
    v45 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
    v44 = (struct SessionStartupCtl *)"Error HResult failed";
    v39 = &EventDescriptor;
    v38 = &v42;
    v37 = &v45;
    p_EventDescriptor = &v44;
    goto LABEL_56;
  }
LABEL_57:
  if ( v7 )
    ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18012b230  mov     r11, rsp
0x18012b233  push    rbp
0x18012b234  push    rbx
0x18012b235  push    rdi
0x18012b236  lea     rbp, [r11-358h]
0x18012b23d  sub     rsp, 440h
0x18012b244  mov     rax, cs:__security_cookie
0x18012b24b  xor     rax, rsp
0x18012b24e  mov     [rbp+350h+var_40], rax
0x18012b255  xorps   xmm0, xmm0
0x18012b258  mov     [r11+18h], rsi
0x18012b25c  mov     [r11-20h], r12
0x18012b260  mov     rsi, rcx
0x18012b263  mov     [r11-28h], r13
0x18012b267  mov     r13, r9
0x18012b26a  mov     [r11-30h], r14
0x18012b26e  xor     r14d, r14d
0x18012b271  mov     edi, r14d
0x18012b274  mov     [r11-38h], r15
0x18012b278  mov     r15, rdx
0x18012b27b  mov     [rbp+350h+var_3B0], r14d
0x18012b27f  movups  [rbp+350h+var_3AC], xmm0
0x18012b283  mov     [rsp+450h+var_3F0], r14
0x18012b288  movups  [rbp+350h+var_39C], xmm0
0x18012b28c  movups  [rbp+350h+var_3C0], xmm0
0x18012b290  movups  [rbp+350h+var_380], xmm0
0x18012b294  movups  [rbp+350h+var_370], xmm0
0x18012b298  movups  [rbp+350h+var_360], xmm0
0x18012b29c  movups  [rbp+350h+var_350], xmm0
0x18012b2a0  movups  [rbp+350h+var_340], xmm0
0x18012b2a4  movups  [rbp+350h+var_330], xmm0
0x18012b2a8  movups  [rbp+350h+var_320], xmm0
0x18012b2ac  movups  [rbp+350h+var_310], xmm0
0x18012b2b0  cmp     [rdx], r14
0x18012b2b3  jnz     loc_18012B40E
0x18012b2b9  mov     eax, cs:CallbackContext
0x18012b2bf  mov     ebx, 80004003h
0x18012b2c4  cmp     eax, 2
0x18012b2c7  jbe     loc_18012BD62
0x18012b2cd  mov     [rbp+350h+EventDescriptor.Keyword], r14
0x18012b2d1  lea     rax, aCrdpudptranspo_3; "CRdpUdpTransport::OnICETransportOpened:"...
0x18012b2d8  mov     [rbp+350h+var_260], rax
0x18012b2df  lea     r14, _TraceLoggingMetadataEnd
0x18012b2e6  mov     [rbp+350h+var_3C8], 1DCh
0x18012b2ed  lea     rax, aOnicetransport_1; "OnICETransportOpened"
0x18012b2f4  mov     [rbp+350h+var_270], rax
0x18012b2fb  lea     r12, _TraceLoggingMetadata
0x18012b302  mov     dword ptr [rsp+450h+var_400+4], ebx
0x18012b306  lea     rax, [rbp+350h+var_3C8]
0x18012b30a  mov     [rbp+350h+var_280], rax
0x18012b311  lea     rdx, [rsp+450h+EventDescriptor]; EventDescriptor
0x18012b316  mov     [rbp+350h+var_258], 41h ; 'A'
0x18012b321  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18012b328  mov     [rbp+350h+var_290], rax
0x18012b32f  sub     r14d, r12d
0x18012b332  mov     [rbp+350h+var_268], 15h
0x18012b33d  lea     rax, [rsp+450h+var_400+4]
0x18012b342  mov     [rbp+350h+var_2A0], rax
0x18012b349  xor     r9d, r9d; RelatedActivityId
0x18012b34c  lea     rax, aErrorCondition; "Error condition failed"
0x18012b353  mov     [rbp+350h+var_278], 4
0x18012b35e  mov     [rbp+350h+var_2B0], rax
0x18012b365  xor     r8d, r8d; ActivityId
0x18012b368  movzx   eax, cs:word_1801CFF2C
0x18012b36f  mov     dword ptr [rsp+450h+EventDescriptor.Level], eax
0x18012b373  mov     rax, cs:off_1801E7010
0x18012b37a  mov     [rbp+350h+var_2D0.Ptr], rax
0x18012b381  mov     [rbp+350h+var_288], 4Fh ; 'O'
0x18012b38c  mov     [rbp+350h+var_298], 4
0x18012b397  mov     [rbp+350h+var_2A8], 17h
0x18012b3a2  mov     dword ptr [rsp+450h+EventDescriptor.Id], 0B000000h
0x18012b3aa  movzx   eax, word ptr [rax]
0x18012b3ad  mov     [rbp+350h+var_2D0.Size], eax
0x18012b3b3  lea     rax, word_1801CFF36
0x18012b3ba  mov     [rbp+350h+var_2C0], rax
0x18012b3c1  mov     dword ptr [rbp+350h+var_2D0.0Ch], 2
0x18012b3cb  mov     [rbp+350h+var_2B8], 3Bh ; ';'
0x18012b3d5  mov     [rbp+350h+var_2B4], 1
0x18012b3df  mov     dword ptr [rsp+450h+var_400], r14d
0x18012b3e4  mov     eax, dword ptr [rsp+450h+var_400]
0x18012b3e8  mov     rcx, cs:RegHandle; RegHandle
0x18012b3ef  lea     rax, [rbp+350h+var_2D0]
0x18012b3f6  mov     [rsp+450h+UserData], rax; UserData
0x18012b3fb  mov     [rsp+450h+UserDataCount], 8; UserDataCount
0x18012b403  call    cs:__imp_EventWriteTransfer
0x18012b409  jmp     loc_18012BD62
0x18012b40e  test    r8d, r8d
0x18012b411  jz      loc_18012B7EF
0x18012b417  mov     eax, cs:CallbackContext
0x18012b41d  cmp     eax, 4
0x18012b420  jbe     loc_18012B4C7
0x18012b426  mov     [rbp+350h+EventDescriptor.Keyword], r14
0x18012b42a  lea     rax, aCreatingIceLoc; "Creating Ice local endpoint"
0x18012b431  mov     [rbp+350h+var_2E0], rax
0x18012b435  lea     r14, _TraceLoggingMetadataEnd
0x18012b43c  movzx   eax, cs:word_1801D259C
0x18012b443  lea     r12, _TraceLoggingMetadata
0x18012b44a  mov     dword ptr [rsp+450h+EventDescriptor.Level], eax
0x18012b44e  lea     rdx, [rsp+450h+EventDescriptor]; EventDescriptor
0x18012b453  mov     rax, cs:off_1801E7010
0x18012b45a  sub     r14d, r12d
0x18012b45d  mov     [rbp+350h+var_300.Ptr], rax
0x18012b461  xor     r9d, r9d; RelatedActivityId
0x18012b464  mov     [rbp+350h+var_2D8], 1Ch
0x18012b46c  xor     r8d, r8d; ActivityId
0x18012b46f  mov     dword ptr [rsp+450h+EventDescriptor.Id], 0B000000h
0x18012b477  movzx   eax, word ptr [rax]
0x18012b47a  mov     [rbp+350h+var_300.Size], eax
0x18012b47d  lea     rax, word_1801D25A6
0x18012b484  mov     [rbp+350h+var_2F0], rax
0x18012b488  mov     dword ptr [rbp+350h+var_300.0Ch], 2
0x18012b48f  mov     [rbp+350h+var_2E8], 13h
0x18012b496  mov     [rbp+350h+var_2E4], 1
0x18012b49d  mov     dword ptr [rsp+450h+var_400], r14d
0x18012b4a2  mov     eax, dword ptr [rsp+450h+var_400]
0x18012b4a6  mov     rcx, cs:RegHandle; RegHandle
0x18012b4ad  lea     rax, [rbp+350h+var_300]
0x18012b4b1  mov     [rsp+450h+UserData], rax; UserData
0x18012b4b6  mov     [rsp+450h+UserDataCount], 3; UserDataCount
0x18012b4be  call    cs:__imp_EventWriteTransfer
0x18012b4c4  xor     r14d, r14d
0x18012b4c7  mov     r9, [rsi+58h]
0x18012b4cb  lea     rdx, [rsi-50h]
0x18012b4cf  test    rdx, rdx
0x18012b4d2  lea     rax, [rsp+450h+var_3F0]
0x18012b4d7  lea     rcx, [rsi-8]
0x18012b4db  mov     qword ptr [rsp+450h+UserDataCount], rax
0x18012b4e0  cmovz   rcx, r14
0x18012b4e4  mov     r8, r15
0x18012b4e7  xor     edx, edx
0x18012b4e9  call    ?CRdpUdpIceLocalEndpoint_CreateInstance@@YAJPEAUIRdpUdpLocalEndpointCallback@@HAEBV?$ComPlainSmartPtr@UIRdpIceAdapter@@@@PEAUIRDPENCConnectorCallbacks@@PEAPEAUIRdpUdpLocalEndpoint@@@Z; CRdpUdpIceLocalEndpoint_CreateInstance(IRdpUdpLocalEndpointCallback *,int,ComPlainSmartPtr<IRdpIceAdapter> const &,IRDPENCConnectorCallbacks *,IRdpUdpLocalEndpoint * *)
0x18012b4ee  mov     ebx, eax
0x18012b4f0  test    eax, eax
0x18012b4f2  jns     loc_18012B593
0x18012b4f8  mov     ecx, cs:CallbackContext
0x18012b4fe  cmp     ecx, 2
0x18012b501  jbe     loc_18012B589
0x18012b507  lea     rax, aFailedToCreate_82; "Failed to create CRdpIceLocalEndpoint i"...
0x18012b50e  mov     dword ptr [rsp+450h+var_400], 1E3h
0x18012b516  mov     [rsp+450h+var_3E8], rax
0x18012b51b  lea     rdx, qword_1801D0BC0
0x18012b522  lea     rax, aOnicetransport_1; "OnICETransportOpened"
0x18012b529  mov     dword ptr [rsp+450h+var_400+4], ebx
0x18012b52d  mov     qword ptr [rbp+350h+var_3C8], rax
0x18012b531  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18012b538  mov     [rsp+450h+var_3E0], rax
0x18012b53d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18012b544  mov     [rsp+450h+var_3F8], rax
0x18012b549  lea     rax, [rsp+450h+var_3E8]
0x18012b54e  mov     qword ptr [rsp+450h+var_408], rax
0x18012b553  lea     rax, [rbp+350h+var_3C8]
0x18012b557  mov     [rsp+450h+var_410], rax
0x18012b55c  lea     rax, [rsp+450h+var_400]
0x18012b561  mov     [rsp+450h+var_418], rax
0x18012b566  lea     rax, [rsp+450h+var_3E0]
0x18012b56b  mov     [rsp+450h+var_420], rax
0x18012b570  lea     rax, [rsp+450h+var_400+4]
0x18012b575  mov     [rsp+450h+UserData], rax
0x18012b57a  lea     rax, [rsp+450h+var_3F8]
0x18012b57f  mov     qword ptr [rsp+450h+UserDataCount], rax
0x18012b584  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18012b589  mov     rdi, [rsp+450h+var_3F0]
0x18012b58e  jmp     loc_18012BD62
0x18012b593  mov     rdi, [rsp+450h+var_3F0]
0x18012b598  lea     rcx, [rsi-20h]; this
0x18012b59c  mov     rdx, rdi; struct IUnknown *
0x18012b59f  call    ?RegisterReverseConnectEndpoint@CRdpUdpTransport@@UEAAJPEAUIUnknown@@@Z; CRdpUdpTransport::RegisterReverseConnectEndpoint(IUnknown *)
0x18012b5a4  mov     ebx, eax
0x18012b5a6  test    eax, eax
0x18012b5a8  jns     loc_18012B638
0x18012b5ae  mov     eax, cs:CallbackContext
0x18012b5b4  cmp     eax, 2
0x18012b5b7  jbe     loc_18012BD62
0x18012b5bd  lea     rax, aFailedToRegist_2; "Failed to RegisterReverseConnectEndpoin"...
0x18012b5c4  mov     dword ptr [rsp+450h+var_400], 1E6h
0x18012b5cc  mov     [rsp+450h+var_3F8], rax
0x18012b5d1  lea     rdx, dword_1801D26AC
0x18012b5d8  lea     rax, aOnicetransport_1; "OnICETransportOpened"
0x18012b5df  mov     [rsp+450h+var_3E0], rax
0x18012b5e4  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18012b5eb  mov     [rsp+450h+var_3E8], rax
0x18012b5f0  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18012b5f7  mov     [rsp+450h+var_3F0], rax
0x18012b5fc  lea     rax, [rsp+450h+var_3F8]
0x18012b601  mov     qword ptr [rsp+450h+var_408], rax
0x18012b606  lea     rax, [rsp+450h+var_3E0]
0x18012b60b  mov     [rsp+450h+var_410], rax
0x18012b610  lea     rax, [rsp+450h+var_400]
0x18012b615  mov     [rsp+450h+var_418], rax
0x18012b61a  lea     rax, [rsp+450h+var_3E8]
0x18012b61f  mov     [rsp+450h+var_420], rax
0x18012b624  lea     rax, [rsp+450h+var_400+4]
0x18012b629  mov     [rsp+450h+UserData], rax
0x18012b62e  lea     rax, [rsp+450h+var_3F0]
0x18012b633  jmp     loc_18012BD54
0x18012b638  mov     ebx, r14d
0x18012b63b  lea     r14, aMultitransport; "MultiTransportCookieHash"
0x18012b642  nop     dword ptr [rax+00h]
0x18012b646  nop     word ptr [rax+rax+00000000h]
0x18012b650  mov     dword ptr [rsp+450h+UserData], ebx
0x18012b654  lea     r9, aSD; "%s%d"
0x18012b65b  mov     edx, 104h; BufferCount
0x18012b660  mov     qword ptr [rsp+450h+UserDataCount], r14
0x18012b665  mov     r8d, 103h; MaxCount
0x18012b66b  lea     rcx, [rbp+350h+Buffer]; Buffer
0x18012b672  call    _snwprintf_s
0x18012b677  mov     rcx, [rsi+28h]
0x18012b67b  lea     r8, [rbp+350h+var_3AC]
0x18012b67f  movsxd  rax, ebx
0x18012b682  mov     rdx, [rcx]
0x18012b685  lea     r8, [r8+rax*4]
0x18012b689  mov     rax, [rdx+28h]
0x18012b68d  lea     rdx, [rbp+350h+Buffer]
0x18012b694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b699  inc     ebx
0x18012b69b  cmp     ebx, 8
0x18012b69e  jb      short loc_18012B650
0x18012b6a0  mov     eax, cs:CallbackContext
0x18012b6a6  cmp     eax, 4
0x18012b6a9  jbe     short loc_18012B6E9
0x18012b6ab  lea     rax, [rbp+350h+var_3AC]
0x18012b6af  mov     qword ptr [rsp+450h+EventDescriptor.Id], rax
0x18012b6b4  lea     rdx, byte_1801D1D35
0x18012b6bb  mov     eax, 20h ; ' '
0x18012b6c0  mov     word ptr [rbp+350h+EventDescriptor.Keyword], ax
0x18012b6c4  lea     rax, aUdpSetCookieHa; "UDP set cookie hash to the localEndPoin"...
0x18012b6cb  mov     [rsp+450h+var_3F8], rax
0x18012b6d0  lea     rax, [rsp+450h+EventDescriptor]
0x18012b6d5  mov     [rsp+450h+UserData], rax
0x18012b6da  lea     rax, [rsp+450h+var_3F8]
0x18012b6df  mov     qword ptr [rsp+450h+UserDataCount], rax
0x18012b6e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperArray<1> const &)
0x18012b6e9  mov     rax, [rdi]
0x18012b6ec  mov     rcx, [rsi+178h]
0x18012b6f3  mov     [rsp+450h+var_3F8], rcx
0x18012b6f8  mov     rbx, [rax+20h]
0x18012b6fc  test    rcx, rcx
0x18012b6ff  jz      short loc_18012B70D
0x18012b701  mov     rax, [rcx]
0x18012b704  mov     rax, [rax+8]
0x18012b708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b70d  lea     rcx, [rsi+0E8h]
0x18012b714  xor     r8d, r8d
0x18012b717  mov     [rsp+450h+var_418], rcx
0x18012b71c  lea     rax, [rbp+350h+var_3C0]
0x18012b720  mov     [rsp+450h+var_420], rax
0x18012b725  lea     r9, [rsi+188h]
0x18012b72c  lea     rax, [rsp+450h+var_3F8]
0x18012b731  mov     dword ptr [rsp+450h+UserData], 101h
0x18012b739  mov     qword ptr [rsp+450h+UserDataCount], rax
0x18012b73e  lea     rdx, [rbp+350h+var_380]
0x18012b742  mov     rax, rbx
0x18012b745  mov     rcx, rdi
0x18012b748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b74d  mov     ebx, eax
0x18012b74f  test    eax, eax
0x18012b751  jns     loc_18012B7E1
0x18012b757  mov     eax, cs:CallbackContext
0x18012b75d  cmp     eax, 2
0x18012b760  jbe     loc_18012BD62
0x18012b766  lea     rax, aOutgoingConnec_0; "Outgoing connection request failed."
0x18012b76d  mov     dword ptr [rsp+450h+var_400], 1FCh
0x18012b775  mov     [rsp+450h+var_3F8], rax
0x18012b77a  lea     rdx, qword_1801CFEE0
0x18012b781  lea     rax, aOnicetransport_1; "OnICETransportOpened"
0x18012b788  mov     [rsp+450h+var_3E0], rax
0x18012b78d  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18012b794  mov     [rsp+450h+var_3E8], rax
0x18012b799  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18012b7a0  mov     [rsp+450h+var_3F0], rax
0x18012b7a5  lea     rax, [rsp+450h+var_3F8]
0x18012b7aa  mov     qword ptr [rsp+450h+var_408], rax
0x18012b7af  lea     rax, [rsp+450h+var_3E0]
0x18012b7b4  mov     [rsp+450h+var_410], rax
0x18012b7b9  lea     rax, [rsp+450h+var_400]
0x18012b7be  mov     [rsp+450h+var_418], rax
0x18012b7c3  lea     rax, [rsp+450h+var_3E8]
0x18012b7c8  mov     [rsp+450h+var_420], rax
0x18012b7cd  lea     rax, [rsp+450h+var_400+4]
0x18012b7d2  mov     [rsp+450h+UserData], rax
0x18012b7d7  lea     rax, [rsp+450h+var_3F0]
0x18012b7dc  jmp     loc_18012BD54
0x18012b7e1  lea     rcx, [rsi-8]; this
0x18012b7e5  call    ?EnableTransportTimer@CRdpUdpTransport@@UEAAXXZ; CRdpUdpTransport::EnableTransportTimer(void)
0x18012b7ea  jmp     loc_18012BD62
0x18012b7ef  lea     rdx, [rcx-50h]
0x18012b7f3  mov     r8, r15
0x18012b7f6  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18012b7fa  lea     rax, [rsp+450h+var_3F0]
0x18012b7ff  test    rdx, rdx
0x18012b802  mov     qword ptr [rsp+450h+UserDataCount], rax
0x18012b807  mov     edx, 1
0x18012b80c  cmovz   rcx, r14
0x18012b810  xor     r9d, r9d
0x18012b813  call    ?CRdpUdpIceLocalEndpoint_CreateInstance@@YAJPEAUIRdpUdpLocalEndpointCallback@@HAEBV?$ComPlainSmartPtr@UIRdpIceAdapter@@@@PEAUIRDPENCConnectorCallbacks@@PEAPEAUIRdpUdpLocalEndpoint@@@Z; CRdpUdpIceLocalEndpoint_CreateInstance(IRdpUdpLocalEndpointCallback *,int,ComPlainSmartPtr<IRdpIceAdapter> const &,IRDPENCConnectorCallbacks *,IRdpUdpLocalEndpoint * *)
0x18012b818  mov     ebx, eax
0x18012b81a  test    eax, eax
0x18012b81c  mov     eax, cs:CallbackContext
0x18012b822  jns     loc_18012B8BD
0x18012b828  cmp     eax, 2
  ... truncated ...
```
