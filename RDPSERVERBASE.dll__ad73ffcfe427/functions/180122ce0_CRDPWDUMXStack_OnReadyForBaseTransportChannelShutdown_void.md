# CRDPWDUMXStack::OnReadyForBaseTransportChannelShutdown(void)

- ea: `0x180122ce0`
- end: `0x180123313`
- name: `?OnReadyForBaseTransportChannelShutdown@CRDPWDUMXStack@@IEAAXXZ`
- size: `1587`
- prototype: `void __fastcall(CRDPWDUMXStack *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180121ec4`
- `0x180123320`

## callees

- `0x180001308`
- `0x18000146c`
- `0x180001f84`
- `0x18000202c`
- `0x1800023e4`
- `0x18000ce04`
- `0x180122ce0`
- `0x1801291d0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012317b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012317b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180123162`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180123162`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012323e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012323e`

## string_xrefs

- `0x180122cf6`: `OnReadyForBaseTransportChannelShutdown`
- `0x180122dcf`: `Failed to read CONN_PROPERTY_ENABLE_TCP_TRANSPORT_SHUTDOWN property`
- `0x180122e3f`: `Failed to read CONN_PROPERTY_ENABLE_TCP_RAW_DATA_REDIRECT property`
- `0x180122eaf`: `Failed to read CONN_PROPERTY_USE_SOFT_SYNC_EXTENSIONS property`
- `0x180122e83`: `UseSoftSyncExtensions`
- `0x180122f1f`: `Failed to read CONN_PROPERTY_USER_CONFIG_TRANSPORT property`
- `0x180122ef3`: `UserConfiguredTransportMode`
- `0x180122fd3`: `TCP shutdown configuration`
- `0x180122f8a`: `Unsupported protocol configuration for TCP shutdown. Disabling the shutdown.`
- `0x18012319b`: `CreateThreadpoolTimer for SendShutdownBaseChannelRequestToClient failed`
- `0x1801232d4`: `Ready for TCP shutdown initiation. Waiting for ConnectionControl channel to be awailable.`

## pseudocode

```c
void __fastcall CRDPWDUMXStack::OnReadyForBaseTransportChannelShutdown(
        CRDPWDUMXStack *this,
        __int64 a2,
        int a3,
        int a4)
{
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  int v6; // eax
  int v7; // eax
  int v8; // r8d
  int v9; // r9d
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  int v14; // r8d
  int v15; // r9d
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // rcx
  int v20; // eax
  int v21; // r8d
  int v22; // r9d
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  int v28; // r8d
  int v29; // r9d
  unsigned int v30; // ecx
  int v31; // eax
  int v32; // r8d
  int v33; // r9d
  const char *v34; // [rsp+50h] [rbp-9h] BYREF
  const char *v35; // [rsp+58h] [rbp-1h] BYREF
  __int64 v36; // [rsp+60h] [rbp+7h] BYREF
  struct _FILETIME pftDueTime; // [rsp+68h] [rbp+Fh] BYREF
  const char *v38; // [rsp+70h] [rbp+17h] BYREF
  __int64 v39; // [rsp+78h] [rbp+1Fh] BYREF
  const char *v40; // [rsp+80h] [rbp+27h] BYREF
  _QWORD v41[5]; // [rsp+88h] [rbp+2Fh] BYREF
  int v42; // [rsp+C0h] [rbp+67h] BYREF
  int v43; // [rsp+C8h] [rbp+6Fh] BYREF
  const char *v44; // [rsp+D0h] [rbp+77h] BYREF
  const char *v45; // [rsp+D8h] [rbp+7Fh] BYREF

  v39 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 78);
  v42 = 0;
  v43 = 0;
  if ( v5 )
  {
    v6 = (**v5)(v5, &IID_IRDPCollection, &v39);
    if ( v6 < 0 && (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v44) = v6;
      v45 = "OnReadyForBaseTransportChannelShutdown";
      pftDueTime = (struct _FILETIME)"Failed to QI for RDP Collection from Platfornm Context";
      v34 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_18028BB55,
        a3,
        a4,
        (__int64)&v34,
        (__int64)&pftDueTime,
        (__int64)&v44,
        (__int64)&v45);
    }
    LODWORD(v5) = v39;
    if ( v39 )
    {
      LODWORD(v45) = 0;
      LODWORD(v44) = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v39 + 32LL))(
             v39,
             L"EnableTcpTransportShutdown",
             &v42);
      if ( v7 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v36) = v7;
        pftDueTime = (struct _FILETIME)"OnReadyForBaseTransportChannelShutdown";
        v34 = "Failed to read CONN_PROPERTY_ENABLE_TCP_TRANSPORT_SHUTDOWN property";
        v35 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)word_18028E1A2,
          v8,
          v9,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)&v36,
          (__int64)&pftDueTime);
      }
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v39 + 32LL))(
              v39,
              L"EnableTcpRawDataRedirect",
              &v43);
      if ( v10 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v36) = v10;
        v35 = "OnReadyForBaseTransportChannelShutdown";
        pftDueTime = (struct _FILETIME)"Failed to read CONN_PROPERTY_ENABLE_TCP_RAW_DATA_REDIRECT property";
        v34 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)word_18028CB7A,
          v11,
          v12,
          (__int64)&v34,
          (__int64)&pftDueTime,
          (__int64)&v36,
          (__int64)&v35);
      }
      v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const char **))(*(_QWORD *)v39 + 40LL))(
              v39,
              L"UseSoftSyncExtensions",
              &v44);
      if ( v13 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v36) = v13;
        v35 = "OnReadyForBaseTransportChannelShutdown";
        pftDueTime = (struct _FILETIME)"Failed to read CONN_PROPERTY_USE_SOFT_SYNC_EXTENSIONS property";
        v34 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_18028DC41,
          v14,
          v15,
          (__int64)&v34,
          (__int64)&pftDueTime,
          (__int64)&v36,
          (__int64)&v35);
      }
      v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const char **))(*(_QWORD *)v39 + 40LL))(
              v39,
              L"UserConfiguredTransportMode",
              &v45);
      if ( v16 < 0 )
      {
        LODWORD(v5) = (_DWORD)CallbackContext;
        if ( (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v36) = v16;
          v35 = "OnReadyForBaseTransportChannelShutdown";
          pftDueTime = (struct _FILETIME)"Failed to read CONN_PROPERTY_USER_CONFIG_TRANSPORT property";
          v34 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)byte_18028A91B,
            a3,
            a4,
            (__int64)&v34,
            (__int64)&pftDueTime,
            (__int64)&v36,
            (__int64)&v35);
        }
      }
      if ( (_DWORD)v45 != 2 || !(_DWORD)v44 )
      {
        v42 = 0;
        v43 = 0;
        if ( (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v36) = (_DWORD)v44;
          LODWORD(v34) = (_DWORD)v45;
          v35 = "Unsupported protocol configuration for TCP shutdown. Disabling the shutdown.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v5,
            (unsigned int)byte_180291189,
            a3,
            a4,
            (__int64)&v35,
            (__int64)&v34,
            (__int64)&v36);
        }
      }
    }
  }
  if ( (unsigned int)CallbackContext > 3 )
  {
    LODWORD(v44) = v43;
    LODWORD(v45) = v42;
    v35 = "TCP shutdown configuration";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v5,
      (unsigned int)&byte_18029034F,
      a3,
      a4,
      (__int64)&v35,
      (__int64)&v45,
      (__int64)&v44);
  }
  v17 = *((_QWORD *)this + 67);
  v18 = 0;
  *((_DWORD *)this + 138) = 0;
  if ( v17 )
  {
    *((_DWORD *)this + 138) = 1;
    v18 = 1;
  }
  if ( v42 )
  {
    v18 = 3 - (v43 != 0);
    *((_DWORD *)this + 138) = v18;
  }
  if ( (unsigned int)(v18 - 2) <= 1 )
  {
    if ( v17 )
    {
      v19 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 78);
      v36 = 0;
      LODWORD(v44) = 10;
      v20 = (**v19)(v19, &IID_IRDPENCPlatformContext, &v36);
      if ( v20 >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, const wchar_t *, const char **))(*(_QWORD *)v36 + 40LL))(
               v36,
               L"WVD::TcpTransportShutdownDelay",
               &v44) >= 0
          && (unsigned int)CallbackContext > 4 )
        {
          LODWORD(v45) = (_DWORD)v44;
          v38 = "TCP shutdown delay specified.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)byte_180290A9B,
            v24,
            v25,
            (__int64)&v38,
            (__int64)&v45);
        }
        if ( (_DWORD)v44 )
        {
          ThreadpoolTimer = CreateThreadpoolTimer(
                              lambda_304e468b43775d113758e471a7faea74_::_lambda_invoker_cdecl_,
                              this,
                              0);
          *((_QWORD *)this + 76) = ThreadpoolTimer;
          if ( ThreadpoolTimer )
          {
            pftDueTime = (struct _FILETIME)(-10000000LL * (unsigned int)v44);
            SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
          }
          else
          {
            LastError = GetLastError();
            v30 = LastError;
            if ( LastError > 0 )
              v30 = (unsigned __int16)LastError | 0x80070000;
            if ( (unsigned int)CallbackContext > 2 )
            {
              v40 = "OnReadyForBaseTransportChannelShutdown";
              v38 = "CreateThreadpoolTimer for SendShutdownBaseChannelRequestToClient failed";
              v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
              v41[0] = "Error condition failed";
              LODWORD(v45) = 1756;
              LODWORD(v34) = v30;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v30,
                (unsigned int)&word_18028EF2E,
                v28,
                v29,
                (__int64)v41,
                (__int64)&v34,
                (__int64)&v35,
                (__int64)&v45,
                (__int64)&v40,
                (__int64)&v38);
            }
          }
        }
        else
        {
          v31 = CRDPWDUMXStack::SendShutdownBaseChannelRequestToClient(this);
          if ( v31 < 0 && (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v34) = v31;
            v40 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
            v35 = "Error HResult failed";
            v41[0] = "Send shutdown base channel request PDU to client failed";
            v38 = "OnReadyForBaseTransportChannelShutdown";
            LODWORD(v45) = 1771;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              (unsigned int)"Send shutdown base channel request PDU to client failed",
              (unsigned int)&byte_180290257,
              v32,
              v33,
              (__int64)&v35,
              (__int64)&v34,
              (__int64)&v40,
              (__int64)&v45,
              (__int64)&v38,
              (__int64)v41);
          }
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v34) = v20;
        v40 = "onecore\\termsrv\\rdpplatform\\rdpenc\\encwdumx\\rdpwdumximpl.cpp";
        v38 = "Error HResult failed";
        v35 = "m_spPlatformContext->QueryInterface(IID_IRDPENCPlatformContext) faled";
        pftDueTime = (struct _FILETIME)"OnReadyForBaseTransportChannelShutdown";
        LODWORD(v45) = 1741;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)"m_spPlatformContext->QueryInterface(IID_IRDPENCPlatformContext) faled",
          (unsigned int)&dword_180291FFC,
          v21,
          v22,
          (__int64)&v38,
          (__int64)&v34,
          (__int64)&v40,
          (__int64)&v45,
          (__int64)&pftDueTime,
          (__int64)&v35);
      }
      TCntPtr<IRdpVCMgr>::SafeRelease(&v36);
    }
    else
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v44 = "Ready for TCP shutdown initiation. Waiting for ConnectionControl channel to be awailable.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          0,
          (unsigned int)&unk_180291F88,
          a3,
          a4,
          (__int64)&v44);
      }
      *((_DWORD *)this + 140) = 1;
    }
  }
  TCntPtr<IRdpVCMgr>::SafeRelease(&v39);
}

```

## disassembly

```asm
0x180122ce0  push    rbp
0x180122ce2  push    rbx
0x180122ce3  push    rdi
0x180122ce4  push    r14
0x180122ce6  push    r15
0x180122ce8  lea     rbp, [rsp-37h]
0x180122ced  sub     rsp, 90h
0x180122cf4  xor     edi, edi
0x180122cf6  lea     r15, aOnreadyforbase; "OnReadyForBaseTransportChannelShutdown"
0x180122cfd  mov     rbx, rcx
0x180122d00  mov     [rbp+57h+var_38], rdi
0x180122d04  mov     rcx, [rcx+270h]
0x180122d0b  mov     [rbp+57h+arg_0], edi
0x180122d0e  mov     [rbp+57h+arg_8], edi
0x180122d11  test    rcx, rcx
0x180122d14  jz      loc_180122FB5
0x180122d1a  mov     rax, [rcx]
0x180122d1d  lea     r8, [rbp+57h+var_38]
0x180122d21  lea     rdx, IID_IRDPCollection
0x180122d28  mov     rax, [rax]
0x180122d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122d30  lea     r14, aHresultFailedB; "HResult failed but continue"
0x180122d37  test    eax, eax
0x180122d39  jns     short loc_180122D8C
0x180122d3b  mov     ecx, cs:CallbackContext
0x180122d41  cmp     ecx, 3
0x180122d44  jbe     short loc_180122D8C
0x180122d46  mov     dword ptr [rbp+57h+arg_10], eax
0x180122d49  lea     rdx, byte_18028BB55
0x180122d50  lea     rax, aFailedToQiForR_0; "Failed to QI for RDP Collection from Pl"...
0x180122d57  mov     [rbp+57h+arg_18], r15
0x180122d5b  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rax
0x180122d5f  lea     rax, [rbp+57h+arg_18]
0x180122d63  mov     [rsp+0B0h+var_78], rax
0x180122d68  lea     rax, [rbp+57h+arg_10]
0x180122d6c  mov     [rsp+0B0h+var_80], rax
0x180122d71  lea     rax, [rbp+57h+pftDueTime]
0x180122d75  mov     [rsp+0B0h+var_88], rax
0x180122d7a  lea     rax, [rbp+57h+var_60]
0x180122d7e  mov     [rsp+0B0h+var_90], rax
0x180122d83  mov     [rbp+57h+var_60], r14
0x180122d87  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180122d8c  mov     rcx, [rbp+57h+var_38]
0x180122d90  test    rcx, rcx
0x180122d93  jz      loc_180122FB5
0x180122d99  mov     dword ptr [rbp+57h+arg_18], edi
0x180122d9c  lea     r8, [rbp+57h+arg_0]
0x180122da0  mov     dword ptr [rbp+57h+arg_10], edi
0x180122da3  lea     rdx, aEnabletcptrans; "EnableTcpTransportShutdown"
0x180122daa  mov     rax, [rcx]
0x180122dad  mov     rax, [rax+20h]
0x180122db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122db6  test    eax, eax
0x180122db8  jns     short loc_180122E0B
0x180122dba  mov     ecx, cs:CallbackContext
0x180122dc0  cmp     ecx, 3
0x180122dc3  jbe     short loc_180122E0B
0x180122dc5  mov     dword ptr [rbp+57h+var_50], eax
0x180122dc8  lea     rdx, word_18028E1A2
0x180122dcf  lea     rax, aFailedToReadCo_1; "Failed to read CONN_PROPERTY_ENABLE_TCP"...
0x180122dd6  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], r15
0x180122dda  mov     [rbp+57h+var_60], rax
0x180122dde  lea     rax, [rbp+57h+pftDueTime]
0x180122de2  mov     [rsp+0B0h+var_78], rax
0x180122de7  lea     rax, [rbp+57h+var_50]
0x180122deb  mov     [rsp+0B0h+var_80], rax
0x180122df0  lea     rax, [rbp+57h+var_60]
0x180122df4  mov     [rsp+0B0h+var_88], rax
0x180122df9  lea     rax, [rbp+57h+var_58]
0x180122dfd  mov     [rsp+0B0h+var_90], rax
0x180122e02  mov     [rbp+57h+var_58], r14
0x180122e06  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180122e0b  mov     rcx, [rbp+57h+var_38]
0x180122e0f  lea     r8, [rbp+57h+arg_8]
0x180122e13  lea     rdx, aEnabletcprawda; "EnableTcpRawDataRedirect"
0x180122e1a  mov     rax, [rcx]
0x180122e1d  mov     rax, [rax+20h]
0x180122e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122e26  test    eax, eax
0x180122e28  jns     short loc_180122E7B
0x180122e2a  mov     ecx, cs:CallbackContext
0x180122e30  cmp     ecx, 3
0x180122e33  jbe     short loc_180122E7B
0x180122e35  mov     dword ptr [rbp+57h+var_50], eax
0x180122e38  lea     rdx, word_18028CB7A
0x180122e3f  lea     rax, aFailedToReadCo_0; "Failed to read CONN_PROPERTY_ENABLE_TCP"...
0x180122e46  mov     [rbp+57h+var_58], r15
0x180122e4a  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rax
0x180122e4e  lea     rax, [rbp+57h+var_58]
0x180122e52  mov     [rsp+0B0h+var_78], rax
0x180122e57  lea     rax, [rbp+57h+var_50]
0x180122e5b  mov     [rsp+0B0h+var_80], rax
0x180122e60  lea     rax, [rbp+57h+pftDueTime]
0x180122e64  mov     [rsp+0B0h+var_88], rax
0x180122e69  lea     rax, [rbp+57h+var_60]
0x180122e6d  mov     [rsp+0B0h+var_90], rax
0x180122e72  mov     [rbp+57h+var_60], r14
0x180122e76  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180122e7b  mov     rcx, [rbp+57h+var_38]
0x180122e7f  lea     r8, [rbp+57h+arg_10]
0x180122e83  lea     rdx, aUsesoftsyncext; "UseSoftSyncExtensions"
0x180122e8a  mov     rax, [rcx]
0x180122e8d  mov     rax, [rax+28h]
0x180122e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122e96  test    eax, eax
0x180122e98  jns     short loc_180122EEB
0x180122e9a  mov     ecx, cs:CallbackContext
0x180122ea0  cmp     ecx, 3
0x180122ea3  jbe     short loc_180122EEB
0x180122ea5  mov     dword ptr [rbp+57h+var_50], eax
0x180122ea8  lea     rdx, byte_18028DC41
0x180122eaf  lea     rax, aFailedToReadCo; "Failed to read CONN_PROPERTY_USE_SOFT_S"...
0x180122eb6  mov     [rbp+57h+var_58], r15
0x180122eba  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rax
0x180122ebe  lea     rax, [rbp+57h+var_58]
0x180122ec2  mov     [rsp+0B0h+var_78], rax
0x180122ec7  lea     rax, [rbp+57h+var_50]
0x180122ecb  mov     [rsp+0B0h+var_80], rax
0x180122ed0  lea     rax, [rbp+57h+pftDueTime]
0x180122ed4  mov     [rsp+0B0h+var_88], rax
0x180122ed9  lea     rax, [rbp+57h+var_60]
0x180122edd  mov     [rsp+0B0h+var_90], rax
0x180122ee2  mov     [rbp+57h+var_60], r14
0x180122ee6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180122eeb  mov     rcx, [rbp+57h+var_38]
0x180122eef  lea     r8, [rbp+57h+arg_18]
0x180122ef3  lea     rdx, aUserconfigured; "UserConfiguredTransportMode"
0x180122efa  mov     rax, [rcx]
0x180122efd  mov     rax, [rax+28h]
0x180122f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122f06  test    eax, eax
0x180122f08  jns     short loc_180122F5B
0x180122f0a  mov     ecx, cs:CallbackContext
0x180122f10  cmp     ecx, 3
0x180122f13  jbe     short loc_180122F5B
0x180122f15  mov     dword ptr [rbp+57h+var_50], eax
0x180122f18  lea     rdx, byte_18028A91B
0x180122f1f  lea     rax, aFailedToReadCo_2; "Failed to read CONN_PROPERTY_USER_CONFI"...
0x180122f26  mov     [rbp+57h+var_58], r15
0x180122f2a  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rax
0x180122f2e  lea     rax, [rbp+57h+var_58]
0x180122f32  mov     [rsp+0B0h+var_78], rax
0x180122f37  lea     rax, [rbp+57h+var_50]
0x180122f3b  mov     [rsp+0B0h+var_80], rax
0x180122f40  lea     rax, [rbp+57h+pftDueTime]
0x180122f44  mov     [rsp+0B0h+var_88], rax
0x180122f49  lea     rax, [rbp+57h+var_60]
0x180122f4d  mov     [rsp+0B0h+var_90], rax
0x180122f52  mov     [rbp+57h+var_60], r14
0x180122f56  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180122f5b  cmp     dword ptr [rbp+57h+arg_18], 2
0x180122f5f  jnz     short loc_180122F66
0x180122f61  cmp     dword ptr [rbp+57h+arg_10], edi
0x180122f64  jnz     short loc_180122FB5
0x180122f66  mov     eax, cs:CallbackContext
0x180122f6c  mov     [rbp+57h+arg_0], edi
0x180122f6f  mov     [rbp+57h+arg_8], edi
0x180122f72  cmp     eax, 3
0x180122f75  jbe     short loc_180122FB5
0x180122f77  mov     eax, dword ptr [rbp+57h+arg_10]
0x180122f7a  lea     rdx, byte_180291189
0x180122f81  mov     dword ptr [rbp+57h+var_50], eax
0x180122f84  mov     eax, dword ptr [rbp+57h+arg_18]
0x180122f87  mov     dword ptr [rbp+57h+var_60], eax
0x180122f8a  lea     rax, aUnsupportedPro; "Unsupported protocol configuration for "...
0x180122f91  mov     [rbp+57h+var_58], rax
0x180122f95  lea     rax, [rbp+57h+var_50]
0x180122f99  mov     [rsp+0B0h+var_80], rax
0x180122f9e  lea     rax, [rbp+57h+var_60]
0x180122fa2  mov     [rsp+0B0h+var_88], rax
0x180122fa7  lea     rax, [rbp+57h+var_58]
0x180122fab  mov     [rsp+0B0h+var_90], rax
0x180122fb0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180122fb5  mov     eax, cs:CallbackContext
0x180122fbb  cmp     eax, 3
0x180122fbe  jbe     short loc_180122FFE
0x180122fc0  mov     eax, [rbp+57h+arg_8]
0x180122fc3  lea     rdx, byte_18029034F
0x180122fca  mov     dword ptr [rbp+57h+arg_10], eax
0x180122fcd  mov     eax, [rbp+57h+arg_0]
0x180122fd0  mov     dword ptr [rbp+57h+arg_18], eax
0x180122fd3  lea     rax, aTcpShutdownCon; "TCP shutdown configuration"
0x180122fda  mov     [rbp+57h+var_58], rax
0x180122fde  lea     rax, [rbp+57h+arg_10]
0x180122fe2  mov     [rsp+0B0h+var_80], rax
0x180122fe7  lea     rax, [rbp+57h+arg_18]
0x180122feb  mov     [rsp+0B0h+var_88], rax
0x180122ff0  lea     rax, [rbp+57h+var_58]
0x180122ff4  mov     [rsp+0B0h+var_90], rax
0x180122ff9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180122ffe  mov     rcx, [rbx+218h]
0x180123005  mov     eax, edi
0x180123007  mov     [rbx+228h], edi
0x18012300d  mov     r14d, 1
0x180123013  test    rcx, rcx
0x180123016  jz      short loc_180123022
0x180123018  mov     [rbx+228h], r14d
0x18012301f  mov     eax, r14d
0x180123022  cmp     [rbp+57h+arg_0], edi
0x180123025  jz      short loc_180123037
0x180123027  mov     eax, [rbp+57h+arg_8]
0x18012302a  neg     eax
0x18012302c  sbb     eax, eax
0x18012302e  add     eax, 3
0x180123031  mov     [rbx+228h], eax
0x180123037  add     eax, 0FFFFFFFEh
0x18012303a  cmp     eax, r14d
0x18012303d  ja      loc_1801232FB
0x180123043  test    rcx, rcx
0x180123046  jz      loc_1801232C9
0x18012304c  mov     rcx, [rbx+270h]
0x180123053  lea     r8, [rbp+57h+var_50]
0x180123057  mov     [rbp+57h+var_50], rdi
0x18012305b  lea     rdx, IID_IRDPENCPlatformContext
0x180123062  mov     dword ptr [rbp+57h+arg_10], 0Ah
0x180123069  mov     rax, [rcx]
0x18012306c  mov     rax, [rax]
0x18012306f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123074  test    eax, eax
0x180123076  jns     short loc_1801230F3
0x180123078  mov     ecx, cs:CallbackContext
0x18012307e  cmp     ecx, 2
0x180123081  jbe     loc_18012320C
0x180123087  mov     dword ptr [rbp+57h+var_60], eax
0x18012308a  lea     rdx, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180123091  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180123098  mov     [rbp+57h+var_30], rdx
0x18012309c  mov     [rbp+57h+var_40], rax
0x1801230a0  lea     rcx, aMSpplatformcon; "m_spPlatformContext->QueryInterface(IID"...
0x1801230a7  lea     rax, [rbp+57h+var_58]
0x1801230ab  mov     [rbp+57h+var_58], rcx
0x1801230af  mov     [rsp+0B0h+var_68], rax
0x1801230b4  lea     rdx, dword_180291FFC
0x1801230bb  lea     rax, [rbp+57h+pftDueTime]
0x1801230bf  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], r15
0x1801230c3  mov     [rsp+0B0h+var_70], rax
0x1801230c8  lea     rax, [rbp+57h+arg_18]
0x1801230cc  mov     [rsp+0B0h+var_78], rax
0x1801230d1  lea     rax, [rbp+57h+var_30]
0x1801230d5  mov     [rsp+0B0h+var_80], rax
0x1801230da  lea     rax, [rbp+57h+var_60]
0x1801230de  mov     [rsp+0B0h+var_88], rax
0x1801230e3  lea     rax, [rbp+57h+var_40]
0x1801230e7  mov     dword ptr [rbp+57h+arg_18], 6CDh
0x1801230ee  jmp     loc_180123202
0x1801230f3  mov     rcx, [rbp+57h+var_50]
0x1801230f7  lea     r8, [rbp+57h+arg_10]
0x1801230fb  lea     rdx, aWvdTcptranspor; "WVD::TcpTransportShutdownDelay"
0x180123102  mov     rax, [rcx]
0x180123105  mov     rax, [rax+28h]
0x180123109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012310e  test    eax, eax
0x180123110  js      short loc_18012314C
0x180123112  mov     eax, cs:CallbackContext
0x180123118  cmp     eax, 4
0x18012311b  jbe     short loc_18012314C
0x18012311d  mov     eax, dword ptr [rbp+57h+arg_10]
0x180123120  lea     rdx, byte_180290A9B
0x180123127  mov     dword ptr [rbp+57h+arg_18], eax
0x18012312a  lea     rax, aTcpShutdownDel; "TCP shutdown delay specified."
0x180123131  mov     [rbp+57h+var_40], rax
0x180123135  lea     rax, [rbp+57h+arg_18]
0x180123139  mov     [rsp+0B0h+var_88], rax
0x18012313e  lea     rax, [rbp+57h+var_40]
0x180123142  mov     [rsp+0B0h+var_90], rax
0x180123147  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18012314c  cmp     dword ptr [rbp+57h+arg_10], edi
0x18012314f  jbe     loc_180123246
0x180123155  xor     r8d, r8d; pcbe
0x180123158  lea     rcx, _lambda_304e468b43775d113758e471a7faea74____lambda_invoker_cdecl_; pfnti
0x18012315f  mov     rdx, rbx; pv
0x180123162  call    cs:__imp_CreateThreadpoolTimer
0x180123168  mov     [rbx+260h], rax
0x18012316f  mov     r10, rax
0x180123172  test    rax, rax
0x180123175  jnz     loc_18012321A
0x18012317b  call    cs:__imp_GetLastError
0x180123181  mov     ecx, eax
0x180123183  test    eax, eax
0x180123185  jle     short loc_180123190
0x180123187  movzx   ecx, ax
0x18012318a  or      ecx, 80070000h
0x180123190  mov     eax, cs:CallbackContext
0x180123196  cmp     eax, 2
0x180123199  jbe     short loc_18012320C
0x18012319b  lea     rax, aCreatethreadpo; "CreateThreadpoolTimer for SendShutdownB"...
0x1801231a2  mov     [rbp+57h+var_30], r15
0x1801231a6  mov     [rbp+57h+var_40], rax
0x1801231aa  lea     rdx, aOnecoreTermsrv_67; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801231b1  lea     rax, aErrorCondition; "Error condition failed"
0x1801231b8  mov     [rbp+57h+var_58], rdx
0x1801231bc  mov     [rbp+57h+var_28], rax
0x1801231c0  lea     rdx, word_18028EF2E
0x1801231c7  lea     rax, [rbp+57h+var_40]
0x1801231cb  mov     dword ptr [rbp+57h+arg_18], 6DCh
0x1801231d2  mov     [rsp+0B0h+var_68], rax
0x1801231d7  lea     rax, [rbp+57h+var_30]
0x1801231db  mov     [rsp+0B0h+var_70], rax
0x1801231e0  lea     rax, [rbp+57h+arg_18]
0x1801231e4  mov     [rsp+0B0h+var_78], rax
  ... truncated ...
```
