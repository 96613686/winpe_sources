# SideTransportStream::OnConnected(uint)

- ea: `0x180153d30`
- end: `0x180154425`
- name: `?OnConnected@SideTransportStream@@UEAAXI@Z`
- size: `1781`
- prototype: `void __fastcall(SideTransportStream *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800012dc`
- `0x180001308`
- `0x18000146c`
- `0x180001f84`
- `0x18000202c`
- `0x180002d3c`
- `0x18000305c`
- `0x180044000`
- `0x18007f42c`
- `0x1800a3474`
- `0x1800d4788`
- `0x180153b70`
- `0x180153d30`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPServerStackDiagnostics_LogShortpathCheckpoint` at `0x180153fa5`
- `RDPBASE!RDPServerStackDiagnostics_LogShortpathCheckpoint` at `0x180153fa5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180153db5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180153db5`
- `OLEAUT32!__imp_VariantInit` at `0x180153e5a`
- `OLEAUT32!__imp_VariantInit` at `0x180153e5a`
- `OLEAUT32!__imp_VariantClear` at `0x1801543fb`
- `OLEAUT32!__imp_VariantClear` at `0x1801543fb`

## string_xrefs

- `0x180154077`: `SideTransportActive`
- `0x18015415c`: `StartDirectlyWithSideTransport`
- `0x180153e34`: `Setting TransportLinkType`
- `0x1801542bb`: `Failed to create Tunnel Filter Stream`
- `0x180153fdc`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x1801541b2`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x18015439e`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180153dd8`: `SideTransportStream is closed or closing. Aborting SideTransportStream::OnConnected processing.`
- `0x180153d8e`: `SideTransportStream::OnConnected`
- `0x1801540a5`: `Failed to set CONN_PROPERTY_SIDE_TRANSPORT_ACTIVE property`
- `0x180154103`: `Failed to get CONN_PROPERTY_SIDE_TRANSPORT_SECURITY_CONFIG property.`
- `0x1801540ce`: `SideTransportSecurityConfig`
- `0x180154204`: `OnSideTransportConectionCompleted call to m_spConnectorCallbacks failed`
- `0x18015424a`: `Failed to InitializeSecuritySettings`

## pseudocode

```c
void __fastcall SideTransportStream::OnConnected(SideTransportStream *this, int a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // r9
  const char *v14; // r8
  int v15; // ecx
  int v16; // ecx
  const char *v17; // r8
  int v18; // r9d
  __int64 v19; // rcx
  int v20; // r8d
  int v21; // r9d
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // rbx
  __int16 *v23; // rdx
  const char *v24; // rax
  __int64 (__fastcall **v25)(_QWORD, GUID *, __int64 *); // rax
  __int64 v26; // rcx
  __int64 (__fastcall *v27)(_QWORD, GUID *, __int64 *); // rsi
  int v28; // edx
  const char *v29; // rax
  int v30; // edx
  struct _SSLINFO *llVal; // rsi
  int v32; // eax
  int v33; // r8d
  int v34; // r9d
  SideTransportStream *v35; // rcx
  int v36; // edx
  int v37; // eax
  void *v38; // rcx
  int v39; // edx
  int v40; // eax
  __int64 v41; // rdx
  void *v42; // rcx
  __int64 v43; // rsi
  int v44; // edx
  const char *v45; // [rsp+50h] [rbp-89h] BYREF
  __int64 v46; // [rsp+58h] [rbp-81h] BYREF
  const char *v47; // [rsp+60h] [rbp-79h] BYREF
  const char *v48; // [rsp+68h] [rbp-71h] BYREF
  __int64 v49; // [rsp+70h] [rbp-69h] BYREF
  void *v50; // [rsp+78h] [rbp-61h] BYREF
  __int64 v51; // [rsp+80h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v53[80]; // [rsp+A0h] [rbp-39h] BYREF
  int v54; // [rsp+F0h] [rbp+17h]
  int v55; // [rsp+140h] [rbp+67h] BYREF
  const char *v56; // [rsp+150h] [rbp+77h] BYREF
  const char *v57; // [rsp+158h] [rbp+7Fh] BYREF

  v50 = 0;
  v49 = 0;
  v51 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(v53, 0, 0x60u);
  v55 = 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v56 = "SideTransportStream::OnConnected";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v4,
      (unsigned int)&word_18029BA7E,
      v5,
      v6,
      (__int64)&v56);
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 11);
  v56 = (char *)this + 88;
  if ( !*((_BYTE *)this + 97) )
  {
    *((_DWORD *)this + 25) = a2;
    *((_BYTE *)this + 96) = 1;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v56);
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v56) = *((_DWORD *)this + 25);
      v57 = "Setting TransportLinkType";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&dword_18029CF04,
        v11,
        v12,
        (__int64)&v57,
        (__int64)&v56);
    }
    VariantInit(&pvarg);
    v14 = "Checkpoint";
    if ( (unsigned int)CallbackContext > 4
      && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, "Checkpoint", v13) )
    {
      v57 = "Udp";
      v56 = (char *)this + 104;
      v46 = (__int64)"Stack";
      v47 = (const char *)0x1000000;
      v45 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v15,
        (unsigned int)byte_18029B6D5,
        (_DWORD)v14,
        v13,
        (__int64)&v45,
        (__int64)&v47,
        (__int64)&v46,
        (__int64)&v57,
        (__int64)&v56);
      v14 = "Checkpoint";
    }
    if ( (unsigned int)CallbackContext > 4
      && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v14, v13) )
    {
      LODWORD(v56) = a2;
      v57 = (char *)this + 104;
      v45 = "Udp";
      v47 = "Stack";
      v46 = 0x1000000;
      v48 = v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)&word_18029C4A6,
        (_DWORD)v17,
        v18,
        (__int64)&v48,
        (__int64)&v46,
        (__int64)&v47,
        (__int64)&v45,
        (__int64)&v57,
        (__int64)&v56);
    }
    RDPServerStackDiagnostics_LogShortpathCheckpoint((char *)this + 104, 713, 1, 1, a2 + 0x10000000, 0);
    v22 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 6);
    if ( !v22 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v56) = 391;
        v48 = "Platform context pointer is null.";
        LODWORD(v57) = -2147467261;
        v47 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        v23 = (__int16 *)byte_18029CFD9;
        v24 = "Error condition failed";
LABEL_58:
        v46 = (__int64)v24;
        v45 = "OnConnected";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v19,
          (_DWORD)v23,
          v20,
          v21,
          (__int64)&v46,
          (__int64)&v57,
          (__int64)&v47,
          (__int64)&v56,
          (__int64)&v45,
          (__int64)&v48);
        goto LABEL_59;
      }
      goto LABEL_59;
    }
    v25 = *v22;
    v26 = v49;
    v49 = 0;
    v27 = *v25;
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v28 = v27(v22, &IID_IRDPENCPlatformContext, &v49);
    if ( v28 >= 0 )
    {
      v30 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v49 + 64LL))(
              v49,
              L"SideTransportActive",
              1);
      if ( v30 >= 0 )
      {
        llVal = 0;
        v32 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v49 + 24LL))(
                v49,
                L"SideTransportSecurityConfig",
                &pvarg);
        if ( v32 >= 0 )
        {
          if ( pvarg.vt == 8 )
            llVal = (struct _SSLINFO *)pvarg.llVal;
        }
        else if ( (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v56) = v32;
          v57 = "OnConnected";
          v48 = "Failed to get CONN_PROPERTY_SIDE_TRANSPORT_SECURITY_CONFIG property.";
          v45 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)&dword_18029D024,
            v33,
            v34,
            (__int64)&v45,
            (__int64)&v48,
            (__int64)&v56,
            (__int64)&v57);
        }
        if ( (*(int (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v49 + 32LL))(
               v49,
               L"StartDirectlyWithSideTransport",
               &v55) >= 0
          && v55 )
        {
          v19 = *((_QWORD *)this + 3);
          if ( !v19 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(v56) = 414;
              v48 = "Invalid m_spConnectorCallbacks pointer";
              v23 = (__int16 *)&byte_18029B657;
              LODWORD(v57) = -2147418113;
              v47 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
              v24 = "Error condition failed";
              goto LABEL_58;
            }
LABEL_59:
            VariantClear(&pvarg);
            goto LABEL_60;
          }
          v36 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *))(*(_QWORD *)v19 + 24LL))(
                  v19,
                  SideTransportStream::m_requestId,
                  0,
                  (char *)this - 40);
          if ( v36 >= 0 )
            goto LABEL_59;
          LODWORD(v19) = (_DWORD)CallbackContext;
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_59;
          LODWORD(v57) = v36;
          v29 = "OnSideTransportConectionCompleted call to m_spConnectorCallbacks failed";
          v23 = (__int16 *)&byte_18029CD5F;
          LODWORD(v56) = 421;
        }
        else
        {
          v51 = 0x100000001LL;
          v37 = SideTransportStream::InitializeSecuritySettings(v35, llVal, (struct RDPENC_SECFILTER_SETTINGS *)v53);
          if ( v37 >= 0 )
          {
            v38 = v50;
            v54 = 0;
            v50 = 0;
            if ( v38 )
              (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v38 + 16LL))(v38, (unsigned int)v37);
            v39 = RDPSERVERBASE_CreateInstance(
                    *((struct IUnknown **)this + 6),
                    &CLSID_IRdpTunnelFilterStream,
                    &IID_IRDPTunnelFilterStream,
                    &v50);
            if ( v39 >= 0 )
            {
              v40 = (*(__int64 (__fastcall **)(void *, char *, __int64 *, _BYTE *))(*(_QWORD *)v50 + 24LL))(
                      v50,
                      (char *)this - 40,
                      &v51,
                      v53);
              v41 = (unsigned int)v40;
              if ( v40 >= 0 )
              {
                v42 = v50;
                v43 = *((_QWORD *)this + 7);
                *((_QWORD *)this + 7) = v50;
                if ( v42 )
                  (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v42 + 8LL))(v42, (unsigned int)v40);
                if ( v43 )
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 16LL))(v43, v41);
                v44 = (*(__int64 (__fastcall **)(void *, unsigned __int64))(*(_QWORD *)v50 + 32LL))(
                        v50,
                        ((unsigned __int64)this - 32) & -(__int64)(this != (SideTransportStream *)40));
                if ( v44 >= 0 )
                  goto LABEL_59;
                LODWORD(v19) = (_DWORD)CallbackContext;
                if ( (unsigned int)CallbackContext <= 2 )
                  goto LABEL_59;
                LODWORD(v57) = v44;
                v29 = "Tunnel Filter Do Handshake failed";
                v23 = (__int16 *)&byte_18029C65F;
                LODWORD(v56) = 455;
              }
              else
              {
                LODWORD(v19) = (_DWORD)CallbackContext;
                if ( (unsigned int)CallbackContext <= 2 )
                  goto LABEL_59;
                LODWORD(v57) = v40;
                v29 = "Failed to initialize instance tunnel stream filter object";
                v23 = word_18029CDAA;
                LODWORD(v56) = 446;
              }
            }
            else
            {
              LODWORD(v19) = (_DWORD)CallbackContext;
              if ( (unsigned int)CallbackContext <= 2 )
                goto LABEL_59;
              LODWORD(v57) = v39;
              v29 = "Failed to create Tunnel Filter Stream";
              v23 = (__int16 *)qword_18029C2B8;
              LODWORD(v56) = 440;
            }
          }
          else
          {
            LODWORD(v19) = (_DWORD)CallbackContext;
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_59;
            LODWORD(v57) = v37;
            v29 = "Failed to InitializeSecuritySettings";
            v23 = &word_18029C34E;
            LODWORD(v56) = 432;
          }
        }
      }
      else
      {
        LODWORD(v19) = (_DWORD)CallbackContext;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_59;
        LODWORD(v57) = v30;
        v29 = "Failed to set CONN_PROPERTY_SIDE_TRANSPORT_ACTIVE property";
        v23 = word_18029BFAA;
        LODWORD(v56) = 400;
      }
    }
    else
    {
      LODWORD(v19) = (_DWORD)CallbackContext;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_59;
      LODWORD(v57) = v28;
      v29 = "pPlatformContext->QueryInterface(IID_IRDPENCPlatformContext) failed";
      v23 = word_18029C6AA;
      LODWORD(v56) = 394;
    }
    v48 = v29;
    v47 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v24 = "Error HResult failed";
    goto LABEL_58;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v57 = "SideTransportStream is closed or closing. Aborting SideTransportStream::OnConnected processing.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v7,
      (unsigned int)byte_18029B5C5,
      v8,
      v9,
      (__int64)&v57);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v56);
LABEL_60:
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v49);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v50);
}

```

## disassembly

```asm
0x180153d30  push    rbp
0x180153d32  push    rbx
0x180153d33  push    rsi
0x180153d34  push    rdi
0x180153d35  push    r12
0x180153d37  push    r13
0x180153d39  push    r14
0x180153d3b  lea     rbp, [rsp-27h]
0x180153d40  sub     rsp, 100h
0x180153d47  xor     eax, eax
0x180153d49  mov     [rbp+57h+var_B8], 0
0x180153d51  mov     esi, edx
0x180153d53  mov     [rbp+57h+var_C0], 0
0x180153d5b  mov     rdi, rcx
0x180153d5e  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180153d62  xorps   xmm0, xmm0
0x180153d65  mov     [rbp+57h+var_B0], rax
0x180153d69  lea     r8d, [rax+60h]; Size
0x180153d6d  xor     edx, edx; Val
0x180153d6f  lea     rcx, [rbp+57h+var_90]; void *
0x180153d73  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180153d77  call    memset_0
0x180153d7c  mov     eax, cs:CallbackContext
0x180153d82  mov     [rbp+57h+arg_0], 0
0x180153d89  cmp     eax, 4
0x180153d8c  jbe     short loc_180153DAE
0x180153d8e  lea     rax, aSidetransports_4; "SideTransportStream::OnConnected"
0x180153d95  mov     [rbp+57h+arg_10], rax
0x180153d99  lea     rdx, word_18029BA7E
0x180153da0  lea     rax, [rbp+57h+arg_10]
0x180153da4  mov     [rsp+130h+var_110], rax
0x180153da9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180153dae  lea     rbx, [rdi+58h]
0x180153db2  mov     rcx, rbx; SRWLock
0x180153db5  call    cs:__imp_AcquireSRWLockExclusive
0x180153dbb  lea     r14, [rdi-28h]
0x180153dbf  mov     [rbp+57h+arg_10], rbx
0x180153dc3  cmp     byte ptr [r14+89h], 0
0x180153dcb  jz      short loc_180153E06
0x180153dcd  mov     eax, cs:CallbackContext
0x180153dd3  cmp     eax, 4
0x180153dd6  jbe     short loc_180153DF8
0x180153dd8  lea     rax, aSidetransports_2; "SideTransportStream is closed or closin"...
0x180153ddf  mov     [rbp+57h+arg_18], rax
0x180153de3  lea     rdx, byte_18029B5C5
0x180153dea  lea     rax, [rbp+57h+arg_18]
0x180153dee  mov     [rsp+130h+var_110], rax
0x180153df3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180153df8  lea     rcx, [rbp+57h+arg_10]
0x180153dfc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180153e01  jmp     loc_180154401
0x180153e06  mov     r12d, 1
0x180153e0c  mov     [rdi+64h], esi
0x180153e0f  lea     rcx, [rbp+57h+arg_10]
0x180153e13  mov     [rdi+60h], r12b
0x180153e17  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180153e1c  mov     eax, cs:CallbackContext
0x180153e22  cmp     eax, 4
0x180153e25  jbe     short loc_180153E56
0x180153e27  mov     eax, [rdi+64h]
0x180153e2a  lea     rdx, dword_18029CF04
0x180153e31  mov     dword ptr [rbp+57h+arg_10], eax
0x180153e34  lea     rax, aSettingTranspo; "Setting TransportLinkType"
0x180153e3b  mov     [rbp+57h+arg_18], rax
0x180153e3f  lea     rax, [rbp+57h+arg_10]
0x180153e43  mov     [rsp+130h+var_108], rax
0x180153e48  lea     rax, [rbp+57h+arg_18]
0x180153e4c  mov     [rsp+130h+var_110], rax
0x180153e51  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180153e56  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180153e5a  call    cs:__imp_VariantInit
0x180153e60  mov     eax, cs:CallbackContext
0x180153e66  lea     rbx, aUdp; "Udp"
0x180153e6d  lea     r13, aStack; "Stack"
0x180153e74  lea     r8, aCheckpoint; "Checkpoint"
0x180153e7b  cmp     eax, 4
0x180153e7e  jbe     short loc_180153EFA
0x180153e80  mov     rdx, 470000000000h
0x180153e8a  lea     rcx, CallbackContext
0x180153e91  call    _tlgKeywordOn
0x180153e96  test    al, al
0x180153e98  jz      short loc_180153EFA
0x180153e9a  lea     rax, [rdi+68h]
0x180153e9e  mov     [rbp+57h+arg_18], rbx
0x180153ea2  mov     [rbp+57h+arg_10], rax
0x180153ea6  lea     rdx, byte_18029B6D5
0x180153ead  lea     rax, [rbp+57h+arg_10]
0x180153eb1  mov     [rsp+130h+var_D8], r13
0x180153eb6  mov     [rsp+130h+var_F0], rax
0x180153ebb  lea     rax, [rbp+57h+arg_18]
0x180153ebf  mov     [rsp+130h+var_F8], rax
0x180153ec4  lea     rax, [rsp+130h+var_D8]
0x180153ec9  mov     [rsp+130h+var_100], rax
0x180153ece  lea     rax, [rbp+57h+var_D0]
0x180153ed2  mov     [rsp+130h+var_108], rax
0x180153ed7  lea     rax, [rsp+130h+var_E0]
0x180153edc  mov     [rsp+130h+var_110], rax
0x180153ee1  mov     [rbp+57h+var_D0], 1000000h
0x180153ee9  mov     [rsp+130h+var_E0], r8
0x180153eee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x180153ef3  lea     r8, aCheckpoint; "Checkpoint"
0x180153efa  mov     eax, cs:CallbackContext
0x180153f00  cmp     eax, 4
0x180153f03  jbe     short loc_180153F84
0x180153f05  mov     rdx, 470000000000h
0x180153f0f  lea     rcx, CallbackContext
0x180153f16  call    _tlgKeywordOn
0x180153f1b  test    al, al
0x180153f1d  jz      short loc_180153F84
0x180153f1f  lea     rax, [rdi+68h]
0x180153f23  mov     dword ptr [rbp+57h+arg_10], esi
0x180153f26  mov     [rbp+57h+arg_18], rax
0x180153f2a  lea     rdx, word_18029C4A6
0x180153f31  lea     rax, [rbp+57h+arg_10]
0x180153f35  mov     [rsp+130h+var_E0], rbx
0x180153f3a  mov     [rsp+130h+var_E8], rax
0x180153f3f  lea     rax, [rbp+57h+arg_18]
0x180153f43  mov     [rsp+130h+var_F0], rax
0x180153f48  lea     rax, [rsp+130h+var_E0]
0x180153f4d  mov     [rsp+130h+var_F8], rax
0x180153f52  lea     rax, [rbp+57h+var_D0]
0x180153f56  mov     [rsp+130h+var_100], rax
0x180153f5b  lea     rax, [rsp+130h+var_D8]
0x180153f60  mov     [rsp+130h+var_108], rax
0x180153f65  lea     rax, [rbp+57h+var_C8]
0x180153f69  mov     [rsp+130h+var_110], rax
0x180153f6e  mov     [rbp+57h+var_D0], r13
0x180153f72  mov     [rsp+130h+var_D8], 1000000h
0x180153f7b  mov     [rbp+57h+var_C8], r8
0x180153f7f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180153f84  lea     eax, [rsi+10000000h]
0x180153f8a  mov     dword ptr [rsp+130h+var_108], 0
0x180153f92  lea     rcx, [rdi+68h]
0x180153f96  mov     dword ptr [rsp+130h+var_110], eax
0x180153f9a  mov     r9d, r12d
0x180153f9d  mov     r8d, r12d
0x180153fa0  mov     edx, 2C9h
0x180153fa5  call    cs:__imp_RDPServerStackDiagnostics_LogShortpathCheckpoint
0x180153fab  mov     rbx, [rdi+30h]
0x180153faf  test    rbx, rbx
0x180153fb2  jnz     short loc_180154001
0x180153fb4  mov     eax, cs:CallbackContext
0x180153fba  cmp     eax, 2
0x180153fbd  jbe     loc_1801543F7
0x180153fc3  lea     rax, aPlatformContex; "Platform context pointer is null."
0x180153fca  mov     dword ptr [rbp+57h+arg_10], 187h
0x180153fd1  mov     [rbp+57h+var_C8], rax
0x180153fd5  lea     rbx, aOnconnected; "OnConnected"
0x180153fdc  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180153fe3  mov     dword ptr [rbp+57h+arg_18], 80004003h
0x180153fea  mov     [rbp+57h+var_D0], rax
0x180153fee  lea     rdx, byte_18029CFD9
0x180153ff5  lea     rax, aErrorCondition; "Error condition failed"
0x180153ffc  jmp     loc_1801543B0
0x180154001  mov     rax, [rbx]
0x180154004  mov     rcx, [rbp+57h+var_C0]
0x180154008  mov     [rbp+57h+var_C0], 0
0x180154010  mov     rsi, [rax]
0x180154013  test    rcx, rcx
0x180154016  jz      short loc_180154024
0x180154018  mov     rdx, [rcx]
0x18015401b  mov     rax, [rdx+10h]
0x18015401f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154024  lea     r8, [rbp+57h+var_C0]
0x180154028  mov     rcx, rbx
0x18015402b  lea     rdx, IID_IRDPENCPlatformContext
0x180154032  mov     rax, rsi
0x180154035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015403a  mov     edx, eax
0x18015403c  test    eax, eax
0x18015403e  jns     short loc_180154073
0x180154040  mov     ecx, cs:CallbackContext
0x180154046  cmp     ecx, 2
0x180154049  jbe     loc_1801543F7
0x18015404f  mov     dword ptr [rbp+57h+arg_18], edx
0x180154052  lea     rax, aPplatformconte_1; "pPlatformContext->QueryInterface(IID_IR"...
0x180154059  lea     rdx, word_18029C6AA
0x180154060  mov     dword ptr [rbp+57h+arg_10], 18Ah
0x180154067  lea     rbx, aOnconnected; "OnConnected"
0x18015406e  jmp     loc_18015439A
0x180154073  mov     rcx, [rbp+57h+var_C0]
0x180154077  lea     rdx, aSidetransporta; "SideTransportActive"
0x18015407e  mov     r8d, r12d
0x180154081  mov     rax, [rcx]
0x180154084  mov     rax, [rax+40h]
0x180154088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015408d  mov     edx, eax
0x18015408f  test    eax, eax
0x180154091  jns     short loc_1801540C6
0x180154093  mov     ecx, cs:CallbackContext
0x180154099  cmp     ecx, 2
0x18015409c  jbe     loc_1801543F7
0x1801540a2  mov     dword ptr [rbp+57h+arg_18], edx
0x1801540a5  lea     rax, aFailedToSetCon; "Failed to set CONN_PROPERTY_SIDE_TRANSP"...
0x1801540ac  lea     rdx, word_18029BFAA
0x1801540b3  mov     dword ptr [rbp+57h+arg_10], 190h
0x1801540ba  lea     rbx, aOnconnected; "OnConnected"
0x1801540c1  jmp     loc_18015439A
0x1801540c6  mov     rcx, [rbp+57h+var_C0]
0x1801540ca  lea     r8, [rbp+57h+pvarg]
0x1801540ce  lea     rdx, aSidetransports_5; "SideTransportSecurityConfig"
0x1801540d5  xor     esi, esi
0x1801540d7  mov     rax, [rcx]
0x1801540da  mov     rax, [rax+18h]
0x1801540de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801540e3  lea     rbx, aOnconnected; "OnConnected"
0x1801540ea  test    eax, eax
0x1801540ec  jns     short loc_18015414A
0x1801540ee  mov     ecx, cs:CallbackContext
0x1801540f4  cmp     ecx, 3
0x1801540f7  jbe     short loc_180154154
0x1801540f9  mov     dword ptr [rbp+57h+arg_10], eax
0x1801540fc  lea     rdx, dword_18029D024
0x180154103  lea     rax, aFailedToGetCon_1; "Failed to get CONN_PROPERTY_SIDE_TRANSP"...
0x18015410a  mov     [rbp+57h+arg_18], rbx
0x18015410e  mov     [rbp+57h+var_C8], rax
0x180154112  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180154119  mov     [rsp+130h+var_E0], rax
0x18015411e  lea     rax, [rbp+57h+arg_18]
0x180154122  mov     [rsp+130h+var_F8], rax
0x180154127  lea     rax, [rbp+57h+arg_10]
0x18015412b  mov     [rsp+130h+var_100], rax
0x180154130  lea     rax, [rbp+57h+var_C8]
0x180154134  mov     [rsp+130h+var_108], rax
0x180154139  lea     rax, [rsp+130h+var_E0]
0x18015413e  mov     [rsp+130h+var_110], rax
0x180154143  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180154148  jmp     short loc_180154154
0x18015414a  cmp     word ptr [rbp+57h+pvarg], 8
0x18015414f  cmovz   rsi, qword ptr [rbp+57h+pvarg+8]
0x180154154  mov     rcx, [rbp+57h+var_C0]
0x180154158  lea     r8, [rbp+57h+arg_0]
0x18015415c  lea     rdx, aStartdirectlyw; "StartDirectlyWithSideTransport"
0x180154163  mov     rax, [rcx]
0x180154166  mov     rax, [rax+20h]
0x18015416a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015416f  test    eax, eax
0x180154171  js      loc_18015421E
0x180154177  cmp     [rbp+57h+arg_0], 0
0x18015417b  jz      loc_18015421E
0x180154181  mov     rcx, [rdi+18h]
0x180154185  test    rcx, rcx
0x180154188  jnz     short loc_1801541D0
0x18015418a  mov     eax, cs:CallbackContext
0x180154190  cmp     eax, 2
0x180154193  jbe     loc_1801543F7
0x180154199  lea     rax, aInvalidMSpconn; "Invalid m_spConnectorCallbacks pointer"
0x1801541a0  mov     dword ptr [rbp+57h+arg_10], 19Eh
0x1801541a7  mov     [rbp+57h+var_C8], rax
0x1801541ab  lea     rdx, byte_18029B657
0x1801541b2  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801541b9  mov     dword ptr [rbp+57h+arg_18], 8000FFFFh
0x1801541c0  mov     [rbp+57h+var_D0], rax
0x1801541c4  lea     rax, aErrorCondition; "Error condition failed"
0x1801541cb  jmp     loc_1801543B0
0x1801541d0  mov     rax, [rcx]
0x1801541d3  mov     r9, r14
0x1801541d6  mov     edx, cs:?m_requestId@SideTransportStream@@0IA; uint SideTransportStream::m_requestId
0x1801541dc  xor     r8d, r8d
0x1801541df  mov     rax, [rax+18h]
0x1801541e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801541e8  mov     edx, eax
0x1801541ea  test    eax, eax
0x1801541ec  jns     loc_1801543F7
0x1801541f2  mov     ecx, cs:CallbackContext
0x1801541f8  cmp     ecx, 2
0x1801541fb  jbe     loc_1801543F7
0x180154201  mov     dword ptr [rbp+57h+arg_18], edx
0x180154204  lea     rax, aOnsidetranspor_1; "OnSideTransportConectionCompleted call "...
0x18015420b  lea     rdx, byte_18029CD5F
0x180154212  mov     dword ptr [rbp+57h+arg_10], 1A5h
0x180154219  jmp     loc_18015439A
0x18015421e  lea     r8, [rbp+57h+var_90]; struct RDPENC_SECFILTER_SETTINGS *
0x180154222  mov     dword ptr [rbp+57h+var_B0], r12d
0x180154226  mov     rdx, rsi; struct _SSLINFO *
0x180154229  mov     dword ptr [rbp+57h+var_B0+4], r12d
0x18015422d  call    ?InitializeSecuritySettings@SideTransportStream@@IEAAJPEAU_SSLINFO@@PEAURDPENC_SECFILTER_SETTINGS@@@Z; SideTransportStream::InitializeSecuritySettings(_SSLINFO *,RDPENC_SECFILTER_SETTINGS *)
0x180154232  mov     edx, eax
0x180154234  test    eax, eax
0x180154236  jns     short loc_180154264
0x180154238  mov     ecx, cs:CallbackContext
0x18015423e  cmp     ecx, 2
0x180154241  jbe     loc_1801543F7
0x180154247  mov     dword ptr [rbp+57h+arg_18], edx
0x18015424a  lea     rax, aFailedToInitia_68; "Failed to InitializeSecuritySettings"
0x180154251  lea     rdx, word_18029C34E
0x180154258  mov     dword ptr [rbp+57h+arg_10], 1B0h
0x18015425f  jmp     loc_18015439A
0x180154264  mov     rcx, [rbp+57h+var_B8]
0x180154268  mov     [rbp+57h+var_40], 0
0x18015426f  mov     [rbp+57h+var_B8], 0
0x180154277  test    rcx, rcx
0x18015427a  jz      short loc_180154288
0x18015427c  mov     rax, [rcx]
0x18015427f  mov     rax, [rax+10h]
0x180154283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154288  mov     rcx, [rdi+30h]
0x18015428c  lea     r9, [rbp+57h+var_B8]
0x180154290  lea     r8, IID_IRDPTunnelFilterStream
0x180154297  lea     rdx, CLSID_IRdpTunnelFilterStream
  ... truncated ...
```
