# CRDPENCONTCPListener::ConfigureListeners(ulong,ulong,int,int)

- ea: `0x1800ff270`
- end: `0x1800ffcc5`
- name: `?ConfigureListeners@CRDPENCONTCPListener@@UEAAJKKHH@Z`
- size: `2645`
- prototype: `int(CRDPENCONTCPListener *__hidden this, unsigned int, unsigned int, int, int)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800018a4`
- `0x180004714`
- `0x180004970`
- `0x180005390`
- `0x180016ad0`
- `0x180019a80`
- `0x180019ab0`
- `0x18001cc3c`
- `0x180046a84`
- `0x1800506ac`
- `0x18006f440`
- `0x18006fc8c`
- `0x1800711c8`
- `0x1800721d4`
- `0x1800787d4`
- `0x180078c20`
- `0x1800923f8`
- `0x1800e8cc0`
- `0x1800e9c80`
- `0x1800e9ce0`
- `0x1800e9f30`
- `0x1800ff018`
- `0x1800ff270`
- `0x180100958`
- `0x1801074a8`
- `0x180162010`

## import_xrefs

- `WS2_32!__imp_htons` at `0x1800ff956`
- `WS2_32!__imp_htons` at `0x1800ff956`
- `OLEAUT32!__imp_VariantInit` at `0x1800ff2e2`
- `OLEAUT32!__imp_VariantInit` at `0x1800ff2ec`
- `OLEAUT32!__imp_VariantInit` at `0x1800ff2e2`
- `OLEAUT32!__imp_VariantInit` at `0x1800ff2ec`
- `OLEAUT32!__imp_VariantClear` at `0x1800ffc82`
- `OLEAUT32!__imp_VariantClear` at `0x1800ffc8c`
- `OLEAUT32!__imp_VariantClear` at `0x1800ffc82`
- `OLEAUT32!__imp_VariantClear` at `0x1800ffc8c`

## string_xrefs

- `0x1800ff4b9`: `Failed to add the port to the temp list`
- `0x1800ffb91`: `Failed to add the port to the temp list`
- `0x1800ff75a`: `ConfigureListeners`
- `0x1800ff7f9`: `ConfigureListeners`
- `0x1800ff872`: `ConfigureListeners`
- `0x1800ffa3c`: `ConfigureListeners`
- `0x1800ffab5`: `ConfigureListeners`
- `0x1800ff771`: `No interface found for protocol %d `
- `0x1800ffafd`: `Failed to create a listener on protocol type %d`

## pseudocode

```c
__int64 __fastcall CRDPENCONTCPListener::ConfigureListeners(
        CRDPENCONTCPListener *this,
        unsigned int a2,
        int a3,
        int a4,
        int a5)
{
  int v6; // r12d
  __int64 v7; // rbx
  CRDPENCONIPHelper *v10; // rax
  CRDPENCONIPHelper *v11; // rsi
  int v12; // r14d
  unsigned int v13; // eax
  unsigned int v14; // edx
  void *v15; // r8
  __int64 v16; // rcx
  unsigned int v17; // eax
  int v18; // eax
  int v19; // ebx
  __int64 v20; // rax
  unsigned int v21; // eax
  int v22; // edx
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  struct _SOCKET_ADDRESS *Next; // rcx
  int v29; // r8d
  int v30; // r9d
  struct sockaddr *lpSockaddr; // r8
  u_short v32; // ax
  int v33; // edx
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  __int64 v37; // rcx
  struct CRDPENCONPort *v38; // rbx
  CRDPENCONTCPListener *v39; // rcx
  CRDPENCNATHelper *v40; // rcx
  int v41; // eax
  int v42; // r8d
  int v43; // r9d
  struct sockaddr *v44; // rax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  struct CRDPENCONPort *v49; // [rsp+60h] [rbp-A0h] BYREF
  int v50; // [rsp+68h] [rbp-98h] BYREF
  int v51; // [rsp+6Ch] [rbp-94h] BYREF
  struct sockaddr *v52; // [rsp+70h] [rbp-90h] BYREF
  struct CRDPENCONPort *v53; // [rsp+78h] [rbp-88h] BYREF
  const char *v54; // [rsp+80h] [rbp-80h] BYREF
  const char *v55; // [rsp+88h] [rbp-78h] BYREF
  const char *v56; // [rsp+90h] [rbp-70h] BYREF
  const char *v57; // [rsp+98h] [rbp-68h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-60h] BYREF
  int v59; // [rsp+A8h] [rbp-58h]
  int v60; // [rsp+ACh] [rbp-54h] BYREF
  int v61; // [rsp+B0h] [rbp-50h] BYREF
  addrinfo v62; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v63; // [rsp+E8h] [rbp-18h] BYREF
  const char *v64; // [rsp+100h] [rbp+0h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+8h] BYREF
  int v66; // [rsp+120h] [rbp+20h] BYREF
  GUID v67; // [rsp+124h] [rbp+24h]
  __int128 v68; // [rsp+134h] [rbp+34h]

  v59 = a4;
  v51 = a3;
  v50 = a2;
  v6 = 0;
  v7 = 0;
  v58 = 0;
  memset(&v62, 0, sizeof(v62));
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v63, 0, sizeof(v63));
  VariantInit(&pvarg);
  VariantInit(&v63);
  if ( *((_QWORD *)this + 5) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        &WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147418113);
    }
    v12 = -2147418113;
  }
  else
  {
    LODWORD(v55) = *((_DWORD *)this + 19);
    v10 = (CRDPENCONIPHelper *)operator new(0x18u);
    v11 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = 0;
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = 0;
      CRDPENCONTCPListener::SetETWActivityID((CRDPENCONTCPListener *)((char *)this - 48));
      v49 = (CRDPENCONTCPListener *)((char *)this + 112);
      CTSCriticalSection::Lock((CRDPENCONTCPListener *)((char *)this + 112));
      if ( (*((_BYTE *)this - 20) & 4) != 0 )
      {
        v12 = -2147467260;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
            v13,
            (__int64)"Listener is terminated",
            4);
        }
        CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v49);
        goto LABEL_29;
      }
      if ( *((_QWORD *)this + 3) )
      {
        TCntPtr<IXMLDOMNodeList>::SafeRelease(&v58);
        v7 = *((_QWORD *)this + 3);
        v58 = v7;
        TCntPtr<ITSAsyncCallback>::SafeAddRef(&v58);
      }
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v49);
      if ( a2 == 34 )
      {
        v15 = (void *)*((_QWORD *)this + 21);
        v66 = 34;
        v62.ai_family = 34;
        v53 = 0;
        v62.ai_socktype = 1;
        v67 = HV_GUID_PARENT;
        v62.ai_protocol = 1;
        v68 = RDP_HVSOCKET_CLIENT_SERVICE_ID;
        v62.ai_canonname = 0;
        v62.ai_addrlen = 36;
        v62.ai_addr = (struct sockaddr *)&v66;
        v62.ai_next = 0;
        v12 = CRDPENCONPort::CreateInstance(&v62, a4, v15, &v53);
        if ( v12 >= 0 )
        {
          v16 = *((_QWORD *)this + 23);
          if ( v16 )
            (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v16 + 24LL))(v16, L"HVSOCKET", 0);
          v12 = (*(__int64 (__fastcall **)(char *, struct CRDPENCONPort *))(*((_QWORD *)this + 7) + 8LL))(
                  (char *)this + 56,
                  v53);
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v17 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                48,
                (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
                v17,
                (__int64)"Failed to add the port to the temp list",
                v12);
            }
            TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v53);
            goto LABEL_29;
          }
          v6 = 1;
        }
        TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v53);
        v18 = 0;
        if ( !v6 )
          v18 = v12;
        v12 = v18;
LABEL_25:
        if ( v12 < 0 )
        {
LABEL_26:
          if ( v6 )
          {
            v19 = (int)v55;
            do
            {
              v20 = *((_QWORD *)this + 7);
              v49 = 0;
              (*(void (__fastcall **)(char *, _QWORD, struct CRDPENCONPort **))(v20 + 48))(
                (char *)this + 56,
                (unsigned int)(v6 + v19 - 1),
                &v49);
              (*(void (__fastcall **)(char *, struct CRDPENCONPort *))(*((_QWORD *)this + 7) + 16LL))(
                (char *)this + 56,
                v49);
              TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v49);
              --v6;
            }
            while ( v6 );
          }
        }
        goto LABEL_29;
      }
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v7 + 24LL))(
             v7,
             L"BindAddress",
             &pvarg) >= 0 )
      {
        v12 = CRDPENCONIPHelper::Initialize(v11, a2, a5, pvarg.bstrVal);
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_29;
          }
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          v22 = 50;
          goto LABEL_41;
        }
      }
      else
      {
        v12 = CRDPENCONIPHelper::Initialize(v11, a2, a5, 0);
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_29;
          }
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          v22 = 49;
LABEL_41:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v22,
            (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
            v21,
            (__int64)"Failed to initialize the ip helper",
            v12);
LABEL_29:
          CRDPENCONIPHelper::`scalar deleting destructor'(v11, v14);
          goto LABEL_95;
        }
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 3) + 24LL))(
              *((_QWORD *)this + 3),
              L"LanAdapter",
              &v63);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v24 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids, v24);
        }
        v63.lVal = -1;
        v63.vt = 19;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          &WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
          v23,
          v63.lVal);
      }
      if ( (unsigned int)CRDPENCONIPHelper::StartEnum(v11) )
      {
        Next = CRDPENCONIPHelper::GetNext(v11);
        if ( Next )
        {
          do
          {
            lpSockaddr = Next->lpSockaddr;
            v52 = lpSockaddr;
            if ( lpSockaddr->sa_family == 2 || lpSockaddr->sa_family == 23 )
            {
              v62.ai_family = lpSockaddr->sa_family;
              v62.ai_addrlen = Next->iSockaddrLength;
              v49 = 0;
              v62.ai_socktype = 1;
              v62.ai_protocol = 6;
              v62.ai_canonname = 0;
              v62.ai_addr = lpSockaddr;
              v62.ai_next = 0;
              v32 = htons(v51);
              v33 = v59;
              *(_WORD *)v52->sa_data = v32;
              v12 = CRDPENCONPort::CreateInstance(&v62, v33, *((void **)this + 21), &v49);
              if ( v12 < 0 )
              {
                if ( (unsigned int)CallbackContext > 2 )
                {
                  v44 = v52;
                  v57 = "ConfigureListeners";
                  LODWORD(v52) = 976;
                  LODWORD(v54) = -2147467259;
                  LOWORD(v50) = v44->sa_family;
                  v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
                  v64 = "Failed to create a listener on protocol type %d";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
                    v34,
                    (unsigned int)byte_1801C5115,
                    v35,
                    v36,
                    (__int64)&v64,
                    (__int64)&v54,
                    (__int64)&v56,
                    (__int64)&v52,
                    (__int64)&v57,
                    (__int64)&v50);
                }
              }
              else
              {
                v37 = *((_QWORD *)this + 23);
                if ( v37 )
                  (*(void (__fastcall **)(__int64, const OLECHAR *, _QWORD))(*(_QWORD *)v37 + 24LL))(
                    v37,
                    L"TCP",
                    (unsigned __int16)v51);
                v38 = v49;
                v12 = (*(__int64 (__fastcall **)(char *, struct CRDPENCONPort *))(*((_QWORD *)this + 7) + 8LL))(
                        (char *)this + 56,
                        v49);
                if ( v12 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v45 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      53,
                      (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
                      v45,
                      (__int64)"Failed to add the port to the temp list",
                      v12);
                  }
                  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v49);
                  goto LABEL_26;
                }
                CRDPENCONTCPListener::RestrictListenerAdapter(
                  v39,
                  *((_QWORD *)v38 + 8),
                  v52->sa_family == 23,
                  v63.cyVal.Lo);
                if ( v52->sa_family == 2 )
                {
                  v40 = (CRDPENCNATHelper *)*((_QWORD *)this + 13);
                  if ( v40 )
                  {
                    v41 = CRDPENCNATHelper::AddPortMapping(v40, *((unsigned __int16 **)v38 + 9), *((_DWORD *)v38 + 13));
                    if ( v41 < 0 && (unsigned int)CallbackContext > 2 )
                    {
                      LODWORD(v52) = v41;
                      v60 = *((_DWORD *)v38 + 13);
                      v57 = "ConfigureListeners";
                      v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
                      v54 = "Failed to add a NAT mapping for port %d (0x%08x)";
                      v61 = 971;
                      LODWORD(v53) = -2147467259;
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                        (_DWORD)CallbackContext,
                        (unsigned int)&word_1801C50AE,
                        v42,
                        v43,
                        (__int64)&v54,
                        (__int64)&v53,
                        (__int64)&v56,
                        (__int64)&v61,
                        (__int64)&v57,
                        (__int64)&v60,
                        (__int64)&v52);
                    }
                  }
                }
                ++v6;
              }
              TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v49);
            }
            else if ( (unsigned int)CallbackContext > 2 )
            {
              LOWORD(v50) = lpSockaddr->sa_family;
              v57 = "Ignoring unknown address family %d";
              v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
              v49 = (struct CRDPENCONPort *)"ConfigureListeners";
              LODWORD(v54) = 979;
              LODWORD(v52) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
                (_DWORD)Next,
                (unsigned int)byte_1801C5053,
                (_DWORD)lpSockaddr,
                v30,
                (__int64)&v57,
                (__int64)&v52,
                (__int64)&v56,
                (__int64)&v54,
                (__int64)&v49,
                (__int64)&v50);
            }
            Next = CRDPENCONIPHelper::GetNext(v11);
          }
          while ( Next );
          if ( !v6 )
            goto LABEL_25;
          v12 = 0;
        }
        else
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v54) = 909;
            v49 = (struct CRDPENCONPort *)"ConfigureListeners";
            v51 = -2147467259;
            v55 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
            v53 = (struct CRDPENCONPort *)"Cant get a connectable IP address.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              0,
              (unsigned int)byte_1801C51C1,
              v29,
              v30,
              (__int64)&v53,
              (__int64)&v51,
              (__int64)&v55,
              (__int64)&v54,
              (__int64)&v49);
          }
          v12 = -2147014846;
        }
      }
      else
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v51 = v50;
          v49 = (struct CRDPENCONPort *)"ConfigureListeners";
          v55 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
          v53 = (struct CRDPENCONPort *)"No interface found for protocol %d ";
          v50 = 901;
          LODWORD(v54) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v25,
            (unsigned int)qword_1801C5170,
            v26,
            v27,
            (__int64)&v53,
            (__int64)&v54,
            (__int64)&v55,
            (__int64)&v50,
            (__int64)&v49,
            (__int64)&v51);
        }
        v12 = -2147014853;
      }
      goto LABEL_29;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v46 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
        v46,
        (__int64)"\"CRDPENCONIPHelper\"");
    }
    v12 = -2147024882;
  }
LABEL_95:
  VariantClear(&pvarg);
  VariantClear(&v63);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v58);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800ff270  mov     [rsp-8+arg_18], rbx
0x1800ff275  push    rbp
0x1800ff276  push    rsi
0x1800ff277  push    rdi
0x1800ff278  push    r12
0x1800ff27a  push    r13
0x1800ff27c  push    r14
0x1800ff27e  push    r15
0x1800ff280  lea     rbp, [rsp-50h]
0x1800ff285  sub     rsp, 150h
0x1800ff28c  mov     rax, cs:__security_cookie
0x1800ff293  xor     rax, rsp
0x1800ff296  mov     [rbp+80h+var_38], rax
0x1800ff29a  xorps   xmm0, xmm0
0x1800ff29d  mov     [rbp+80h+var_D8], r9d
0x1800ff2a1  xor     eax, eax
0x1800ff2a3  mov     [rsp+180h+var_114], r8d
0x1800ff2a8  mov     r13, rcx
0x1800ff2ab  mov     [rsp+180h+var_118], edx
0x1800ff2af  xorps   xmm1, xmm1
0x1800ff2b2  mov     qword ptr [rbp+80h+pvarg+10h], rax
0x1800ff2b6  xor     r12d, r12d
0x1800ff2b9  mov     qword ptr [rbp+80h+var_98+10h], rax
0x1800ff2bd  mov     ebx, r12d
0x1800ff2c0  lea     rcx, [rbp+80h+pvarg]; pvarg
0x1800ff2c4  mov     [rbp+80h+var_E0], rbx
0x1800ff2c8  mov     r15d, r9d
0x1800ff2cb  mov     r14d, edx
0x1800ff2ce  movups  xmmword ptr [rbp+80h+var_C8.ai_flags], xmm0
0x1800ff2d2  movups  xmmword ptr [rbp+80h+var_C8.ai_addrlen], xmm0
0x1800ff2d6  movups  xmmword ptr [rbp+80h+var_C8.ai_addr], xmm0
0x1800ff2da  movups  xmmword ptr [rbp+80h+pvarg], xmm0
0x1800ff2de  movups  xmmword ptr [rbp+80h+var_98], xmm1
0x1800ff2e2  call    cs:__imp_VariantInit
0x1800ff2e8  lea     rcx, [rbp+80h+var_98]; pvarg
0x1800ff2ec  call    cs:__imp_VariantInit
0x1800ff2f2  cmp     [r13+28h], r12
0x1800ff2f6  jnz     loc_1800FFC2A
0x1800ff2fc  mov     eax, [r13+4Ch]
0x1800ff300  lea     ecx, [r12+18h]; Size
0x1800ff305  mov     dword ptr [rbp+80h+var_F8], eax
0x1800ff308  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ff30d  mov     rsi, rax
0x1800ff310  test    rax, rax
0x1800ff313  jz      loc_1800FFBD0
0x1800ff319  lea     rcx, [r13-30h]; this
0x1800ff31d  mov     [rax], r12
0x1800ff320  mov     [rax+8], r12
0x1800ff324  mov     [rax+10h], r12
0x1800ff328  call    ?SetETWActivityID@CRDPENCONTCPListener@@IEAAJXZ; CRDPENCONTCPListener::SetETWActivityID(void)
0x1800ff32d  lea     rcx, [r13+70h]; this
0x1800ff331  mov     [rsp+180h+var_120], rcx
0x1800ff336  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800ff33b  mov     dil, 4
0x1800ff33e  test    [r13-14h], dil
0x1800ff342  jz      short loc_1800FF3B3
0x1800ff344  mov     r14d, 80004004h
0x1800ff34a  mov     rax, cs:WPP_GLOBAL_Control
0x1800ff351  lea     r15, WPP_GLOBAL_Control
0x1800ff358  cmp     rax, r15
0x1800ff35b  jz      short loc_1800FF3A4
0x1800ff35d  test    byte ptr [rax+1Ch], 8
0x1800ff361  jz      short loc_1800FF3A4
0x1800ff363  lea     edi, [r12+2]
0x1800ff368  cmp     [rax+19h], dil
0x1800ff36c  jb      short loc_1800FF3A4
0x1800ff36e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ff373  lea     rcx, aListenerIsTerm; "Listener is terminated"
0x1800ff37a  mov     dword ptr [rsp+180h+var_158], 80004004h
0x1800ff382  mov     [rsp+180h+var_160], rcx
0x1800ff387  lea     edx, [rdi+2Dh]
0x1800ff38a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ff391  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x1800ff398  mov     r9d, eax
0x1800ff39b  mov     rcx, [rcx+10h]
0x1800ff39f  call    WPP_SF_DsD
0x1800ff3a4  lea     rcx, [rsp+180h+var_120]; this
0x1800ff3a9  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800ff3ae  jmp     loc_1800FF564
0x1800ff3b3  cmp     [r13+18h], rbx
0x1800ff3b7  jz      short loc_1800FF3D3
0x1800ff3b9  lea     rcx, [rbp+80h+var_E0]; void *
0x1800ff3bd  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800ff3c2  mov     rbx, [r13+18h]
0x1800ff3c6  lea     rcx, [rbp+80h+var_E0]
0x1800ff3ca  mov     [rbp+80h+var_E0], rbx
0x1800ff3ce  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800ff3d3  lea     rcx, [rsp+180h+var_120]; this
0x1800ff3d8  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800ff3dd  mov     ecx, 22h ; '"'
0x1800ff3e2  cmp     r14d, ecx
0x1800ff3e5  jnz     loc_1800FF571
0x1800ff3eb  movups  xmm0, xmmword ptr cs:HV_GUID_PARENT.Data1
0x1800ff3f2  mov     r8, [r13+0A8h]; void *
0x1800ff3f9  lea     ebx, [rcx-21h]
0x1800ff3fc  movups  xmm1, cs:RDP_HVSOCKET_CLIENT_SERVICE_ID
0x1800ff403  mov     [rbp+80h+var_60], ecx
0x1800ff406  lea     rax, [rbp+80h+var_60]
0x1800ff40a  mov     [rbp+80h+var_C8.ai_family], ecx
0x1800ff40d  lea     r9, [rsp+180h+var_108]; struct CRDPENCONPort **
0x1800ff412  mov     edx, r15d; int
0x1800ff415  mov     [rsp+180h+var_108], r12
0x1800ff41a  lea     rcx, [rbp+80h+var_C8]; struct addrinfo *
0x1800ff41e  mov     [rbp+80h+var_C8.ai_socktype], ebx
0x1800ff421  movdqu  [rbp+80h+var_5C], xmm0
0x1800ff426  mov     [rbp+80h+var_C8.ai_protocol], ebx
0x1800ff429  movdqu  [rbp+80h+var_4C], xmm1
0x1800ff42e  mov     [rbp+80h+var_C8.ai_canonname], r12
0x1800ff432  mov     [rbp+80h+var_C8.ai_addrlen], 24h ; '$'
0x1800ff43a  mov     [rbp+80h+var_C8.ai_addr], rax
0x1800ff43e  mov     [rbp+80h+var_C8.ai_next], r12
0x1800ff442  call    ?CreateInstance@CRDPENCONPort@@SAJPEAUaddrinfo@@HPEAXPEAPEAV1@@Z; CRDPENCONPort::CreateInstance(addrinfo *,int,void *,CRDPENCONPort * *)
0x1800ff447  mov     r14d, eax
0x1800ff44a  test    eax, eax
0x1800ff44c  js      loc_1800FF4F6
0x1800ff452  mov     rcx, [r13+0B8h]
0x1800ff459  test    rcx, rcx
0x1800ff45c  jz      short loc_1800FF474
0x1800ff45e  mov     rax, [rcx]
0x1800ff461  lea     rdx, aHvsocket; "HVSOCKET"
0x1800ff468  xor     r8d, r8d
0x1800ff46b  mov     rax, [rax+18h]
0x1800ff46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff474  mov     rdx, [rsp+180h+var_108]
0x1800ff479  lea     rcx, [r13+38h]
0x1800ff47d  mov     rax, [rcx]
0x1800ff480  mov     rax, [rax+8]
0x1800ff484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff489  mov     r14d, eax
0x1800ff48c  test    eax, eax
0x1800ff48e  jns     short loc_1800FF4F3
0x1800ff490  mov     rax, cs:WPP_GLOBAL_Control
0x1800ff497  lea     r15, WPP_GLOBAL_Control
0x1800ff49e  cmp     rax, r15
0x1800ff4a1  jz      short loc_1800FF4E7
0x1800ff4a3  test    byte ptr [rax+1Ch], 8
0x1800ff4a7  jz      short loc_1800FF4E7
0x1800ff4a9  mov     edi, 2
0x1800ff4ae  cmp     [rax+19h], dil
0x1800ff4b2  jb      short loc_1800FF4E7
0x1800ff4b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ff4b9  lea     rcx, aFailedToAddThe_2; "Failed to add the port to the temp list"
0x1800ff4c0  mov     dword ptr [rsp+180h+var_158], r14d
0x1800ff4c5  mov     [rsp+180h+var_160], rcx
0x1800ff4ca  lea     edx, [rdi+2Eh]
0x1800ff4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ff4d4  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x1800ff4db  mov     r9d, eax
0x1800ff4de  mov     rcx, [rcx+10h]
0x1800ff4e2  call    WPP_SF_DsD
0x1800ff4e7  lea     rcx, [rsp+180h+var_108]
0x1800ff4ec  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x1800ff4f1  jmp     short loc_1800FF564
0x1800ff4f3  mov     r12d, ebx
0x1800ff4f6  lea     rcx, [rsp+180h+var_108]
0x1800ff4fb  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x1800ff500  xor     eax, eax
0x1800ff502  test    r12d, r12d
0x1800ff505  cmovz   eax, r14d
0x1800ff509  mov     r14d, eax
0x1800ff50c  test    r14d, r14d
0x1800ff50f  jns     short loc_1800FF564
0x1800ff511  test    r12d, r12d
0x1800ff514  jz      short loc_1800FF564
0x1800ff516  mov     ebx, dword ptr [rbp+80h+var_F8]
0x1800ff519  mov     rax, [r13+38h]
0x1800ff51d  lea     edx, [rbx-1]
0x1800ff520  add     edx, r12d
0x1800ff523  mov     [rsp+180h+var_120], 0
0x1800ff52c  lea     r8, [rsp+180h+var_120]
0x1800ff531  lea     rcx, [r13+38h]
0x1800ff535  mov     rax, [rax+30h]
0x1800ff539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff53e  mov     rax, [r13+38h]
0x1800ff542  lea     rcx, [r13+38h]
0x1800ff546  mov     rdx, [rsp+180h+var_120]
0x1800ff54b  mov     rax, [rax+10h]
0x1800ff54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff554  lea     rcx, [rsp+180h+var_120]
0x1800ff559  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x1800ff55e  add     r12d, 0FFFFFFFFh
0x1800ff562  jnz     short loc_1800FF519
0x1800ff564  mov     rcx, rsi; this
0x1800ff567  call    ??_GCRDPENCONIPHelper@@QEAAPEAXI@Z; CRDPENCONIPHelper::`scalar deleting destructor'(uint)
0x1800ff56c  jmp     loc_1800FFC7E
0x1800ff571  mov     rax, [rbx]
0x1800ff574  lea     r8, [rbp+80h+pvarg]
0x1800ff578  lea     rdx, aBindaddress; "BindAddress"
0x1800ff57f  mov     rcx, rbx
0x1800ff582  mov     rax, [rax+18h]
0x1800ff586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff58b  mov     r8d, [rbp+80h+arg_20]; int
0x1800ff592  mov     edx, r14d; unsigned int
0x1800ff595  mov     rcx, rsi; this
0x1800ff598  test    eax, eax
0x1800ff59a  jns     short loc_1800FF5DD
0x1800ff59c  xor     r9d, r9d; unsigned __int16 *
0x1800ff59f  call    ?Initialize@CRDPENCONIPHelper@@QEAAJKHPEAG@Z; CRDPENCONIPHelper::Initialize(ulong,int,ushort *)
0x1800ff5a4  mov     r14d, eax
0x1800ff5a7  test    eax, eax
0x1800ff5a9  jns     loc_1800FF655
0x1800ff5af  mov     rax, cs:WPP_GLOBAL_Control
0x1800ff5b6  lea     r15, WPP_GLOBAL_Control
0x1800ff5bd  cmp     rax, r15
0x1800ff5c0  jz      short loc_1800FF564
0x1800ff5c2  test    byte ptr [rax+1Ch], 8
0x1800ff5c6  jz      short loc_1800FF564
0x1800ff5c8  mov     edi, 2
0x1800ff5cd  cmp     [rax+19h], dil
0x1800ff5d1  jb      short loc_1800FF564
0x1800ff5d3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ff5d8  lea     edx, [rdi+2Fh]
0x1800ff5db  jmp     short loc_1800FF625
0x1800ff5dd  mov     r9, qword ptr [rbp+80h+pvarg+8]; unsigned __int16 *
0x1800ff5e1  call    ?Initialize@CRDPENCONIPHelper@@QEAAJKHPEAG@Z; CRDPENCONIPHelper::Initialize(ulong,int,ushort *)
0x1800ff5e6  mov     r14d, eax
0x1800ff5e9  test    eax, eax
0x1800ff5eb  jns     short loc_1800FF655
0x1800ff5ed  mov     rax, cs:WPP_GLOBAL_Control
0x1800ff5f4  lea     r15, WPP_GLOBAL_Control
0x1800ff5fb  cmp     rax, r15
0x1800ff5fe  jz      loc_1800FF564
0x1800ff604  test    byte ptr [rax+1Ch], 8
0x1800ff608  jz      loc_1800FF564
0x1800ff60e  mov     edi, 2
0x1800ff613  cmp     [rax+19h], dil
0x1800ff617  jb      loc_1800FF564
0x1800ff61d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ff622  lea     edx, [rdi+30h]
0x1800ff625  lea     rcx, aFailedToInitia_24; "Failed to initialize the ip helper"
0x1800ff62c  mov     dword ptr [rsp+180h+var_158], r14d
0x1800ff631  mov     [rsp+180h+var_160], rcx
0x1800ff636  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x1800ff63d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ff644  mov     r9d, eax
0x1800ff647  mov     rcx, [rcx+10h]
0x1800ff64b  call    WPP_SF_DsD
0x1800ff650  jmp     loc_1800FF564
0x1800ff655  mov     rcx, [r13+18h]
0x1800ff659  lea     r8, [rbp+80h+var_98]
0x1800ff65d  lea     rdx, aLanadapter; "LanAdapter"
0x1800ff664  mov     rax, [rcx]
0x1800ff667  mov     rax, [rax+18h]
0x1800ff66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff670  mov     r14d, eax
0x1800ff673  test    eax, eax
0x1800ff675  js      short loc_1800FF6D2
0x1800ff677  mov     rax, cs:WPP_GLOBAL_Control
0x1800ff67e  lea     r15, WPP_GLOBAL_Control
0x1800ff685  cmp     rax, r15
0x1800ff688  jz      loc_1800FF728
0x1800ff68e  test    dword ptr [rax+1Ch], 800h
0x1800ff695  jz      loc_1800FF728
0x1800ff69b  cmp     [rax+19h], dil
0x1800ff69f  jb      loc_1800FF728
0x1800ff6a5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ff6aa  mov     ecx, dword ptr [rbp+80h+var_98+8]
0x1800ff6ad  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x1800ff6b4  mov     dword ptr [rsp+180h+var_160], ecx
0x1800ff6b8  mov     edx, 33h ; '3'
0x1800ff6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ff6c4  mov     r9d, eax
0x1800ff6c7  mov     rcx, [rcx+10h]
0x1800ff6cb  call    WPP_SF_Dd
0x1800ff6d0  jmp     short loc_1800FF728
0x1800ff6d2  mov     rax, cs:WPP_GLOBAL_Control
0x1800ff6d9  lea     r15, WPP_GLOBAL_Control
0x1800ff6e0  cmp     rax, r15
0x1800ff6e3  jz      short loc_1800FF718
0x1800ff6e5  test    dword ptr [rax+1Ch], 800h
0x1800ff6ec  jz      short loc_1800FF718
0x1800ff6ee  cmp     [rax+19h], dil
0x1800ff6f2  jb      short loc_1800FF718
0x1800ff6f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ff6f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ff700  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x1800ff707  mov     edx, 34h ; '4'
0x1800ff70c  mov     r9d, eax
0x1800ff70f  mov     rcx, [rcx+10h]
0x1800ff713  call    WPP_SF_d
0x1800ff718  mov     eax, 13h
0x1800ff71d  mov     dword ptr [rbp+80h+var_98+8], 0FFFFFFFFh
0x1800ff724  mov     word ptr [rbp+80h+var_98], ax
0x1800ff728  mov     rcx, rsi; this
0x1800ff72b  call    ?StartEnum@CRDPENCONIPHelper@@QEAAHXZ; CRDPENCONIPHelper::StartEnum(void)
0x1800ff730  test    eax, eax
0x1800ff732  jnz     loc_1800FF7D6
0x1800ff738  mov     eax, cs:CallbackContext
0x1800ff73e  mov     edi, 2
0x1800ff743  cmp     eax, edi
0x1800ff745  jbe     loc_1800FF7CB
0x1800ff74b  mov     eax, [rsp+180h+var_118]
0x1800ff74f  lea     rdx, qword_1801C5170
0x1800ff756  mov     [rsp+180h+var_114], eax
0x1800ff75a  lea     rax, aConfigureliste; "ConfigureListeners"
0x1800ff761  mov     [rsp+180h+var_120], rax
0x1800ff766  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800ff76d  mov     [rbp+80h+var_F8], rax
0x1800ff771  lea     rax, aNoInterfaceFou; "No interface found for protocol %d "
0x1800ff778  mov     [rsp+180h+var_108], rax
  ... truncated ...
```
