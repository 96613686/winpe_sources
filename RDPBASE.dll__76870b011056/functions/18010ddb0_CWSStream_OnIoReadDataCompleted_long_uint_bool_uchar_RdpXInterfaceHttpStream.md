# CWSStream::OnIoReadDataCompleted(long,uint,bool,uchar *,RdpXInterfaceHttpStream *)

- ea: `0x18010ddb0`
- end: `0x18010e2fd`
- name: `?OnIoReadDataCompleted@CWSStream@@UEAAXJI_NPEAEPEAURdpXInterfaceHttpStream@@@Z`
- size: `1357`
- prototype: `void __fastcall(CWSStream *__hidden this, int, unsigned int, bool, unsigned __int8 *, struct RdpXInterfaceHttpStream *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180002550`
- `0x180004a94`
- `0x180019a80`
- `0x180019ab0`
- `0x18001b3f8`
- `0x180040750`
- `0x180078c20`
- `0x1800888d8`
- `0x180109934`
- `0x18010c27c`
- `0x18010ddb0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010e17b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010e1e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010e17b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010e1e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010dfb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010e0d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010dfb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010e0d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010dff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010e142`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010dff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010e142`

## string_xrefs

- `0x18010de19`: `OnIoReadDataCompleted`
- `0x18010dedd`: `OnIoReadDataCompleted`
- `0x18010e23d`: `OnIoReadDataCompleted`
- `0x18010e06b`: `Trying to prepend a byte from a previous read. Unexpected payload offset.`
- `0x18010df5c`: `ReadData read 1 byte - completing listening mode`
- `0x18010e264`: `Flush of pending read data has failed.`

## pseudocode

```c
void __fastcall CWSStream::OnIoReadDataCompleted(
        CWSStream *this,
        int a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int8 *a5)
{
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rsi
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // r9d
  __int64 v15; // rcx
  unsigned int v16; // eax
  int v17; // edx
  int v18; // r8d
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 *v21; // r15
  __int64 v22; // r13
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rcx
  int Buffer; // eax
  int v28; // r8d
  int v29; // r9d
  int v30; // ebx
  unsigned int v31; // [rsp+50h] [rbp-49h] BYREF
  _BYTE *v32; // [rsp+58h] [rbp-41h] BYREF
  const char *v33; // [rsp+60h] [rbp-39h] BYREF
  const char *v34; // [rsp+68h] [rbp-31h] BYREF
  const char *v35; // [rsp+70h] [rbp-29h] BYREF
  __int64 v36; // [rsp+78h] [rbp-21h] BYREF
  __int64 v37; // [rsp+80h] [rbp-19h] BYREF
  __int64 v38; // [rsp+88h] [rbp-11h] BYREF
  const char *v39; // [rsp+90h] [rbp-9h] BYREF
  GUID ActivityId; // [rsp+98h] [rbp-1h] BYREF

  v7 = 0;
  v8 = 0;
  v38 = 0;
  v9 = 0;
  v37 = 0;
  v36 = 0;
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, (const struct _GUID *)((char *)this + 1124));
  if ( a2 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v31 = 1245;
      v39 = "OnIoReadDataCompleted";
      LODWORD(v32) = a2;
      v34 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v35 = "Receiving data has failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)byte_1801C908D,
        v12,
        v13,
        (__int64)&v35,
        (__int64)&v32,
        (__int64)&v34,
        (__int64)&v31,
        (__int64)&v39);
    }
    v14 = a2;
LABEL_41:
    CWSStream::CloseInternal((CWSStream *)((char *)this - 24), 0, 0, v14);
    goto LABEL_42;
  }
  v15 = *((_QWORD *)this + 227);
  if ( v15
    && (v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD))(*(_QWORD *)v15 + 8LL))(v15, a5, a3),
        v17 = MapXResultToHR(v16),
        v17 < 0) )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v31 = v17;
      v35 = "TLSLogger detected bad input data in CWSStream.";
      LODWORD(v32) = 1253;
      v34 = "OnIoReadDataCompleted";
      v39 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
      v33 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)&byte_1801C9017,
        v18,
        v13,
        (__int64)&v33,
        (__int64)&v31,
        (__int64)&v39,
        (__int64)&v32,
        (__int64)&v34,
        (__int64)&v35);
    }
  }
  else if ( *((_DWORD *)this + 26) && a3 == 1 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v33 = "ReadData read 1 byte - completing listening mode";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)qword_1801C9068,
        0,
        v13,
        (__int64)&v33);
    }
    v19 = *((_QWORD *)this + 19);
    v20 = *((_QWORD *)this + 20);
    *((_DWORD *)this + 26) = 0;
    *((_DWORD *)this + 27) = 1;
    (*(void (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v19 + 40LL))(v19, (char *)this - 24, v20);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v21 = (__int64 *)((char *)this + 1080);
    if ( *((_QWORD *)this + 135) )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease(&v38);
      v38 = *v21;
      v7 = v38;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v38);
      v22 = v7;
    }
    else
    {
      v22 = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    if ( *((_DWORD *)this + 27) )
    {
      v31 = 0;
      v32 = 0;
      *((_DWORD *)this + 27) = 0;
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 56LL))(v22, &v31);
      if ( v31 == 1 )
      {
        v31 = 0;
        ++a3;
        (*(void (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v22 + 24LL))(v22, &v32);
        *v32 = *((_BYTE *)this + 112);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 64LL))(v22, v31);
      }
      else if ( (unsigned int)CallbackContext > 3 )
      {
        v33 = "Trying to prepend a byte from a previous read. Unexpected payload offset.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)&byte_1801C8FC7,
          0,
          v25,
          (__int64)&v33);
      }
    }
    if ( (unsigned int)CallbackContext > 5 )
    {
      LODWORD(v32) = a3;
      v33 = "Received data from server";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)&dword_1801C8FEC,
        v24,
        v25,
        (__int64)&v33,
        (__int64)&v32);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    if ( *v21 )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 1080);
      *v21 = 0;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 1080);
    }
    if ( *((_QWORD *)this + 18) )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease(&v37);
      v8 = *((_QWORD *)this + 18);
      v37 = v8;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v37);
    }
    if ( *((_QWORD *)this + 136) )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease(&v36);
      v9 = *((_QWORD *)this + 136);
      v36 = v9;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v36);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    if ( v9 )
    {
      v26 = *((_QWORD *)this + 224);
      *((_DWORD *)this + 275) += 8 * a3;
      if ( v26 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 8LL))(v26, a3);
      if ( GetTickCount() - *((_DWORD *)this + 277) > 0x64 )
      {
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v9 + 32LL))(
          v9,
          105,
          *((unsigned int *)this + 275));
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v9 + 32LL))(
          v9,
          104,
          *((unsigned int *)this + 275));
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v9 + 32LL))(v9, 124, *((_DWORD *)this + 275) >> 3);
        *((_DWORD *)this + 277) = GetTickCount();
        *((_DWORD *)this + 275) = 0;
      }
    }
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 48LL))(v7, a3);
    if ( v8 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, v7);
    Buffer = CWSStream::FlushReadBuffer((CWSStream *)((char *)this - 24));
    v30 = Buffer;
    if ( Buffer < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v32) = 1357;
        v33 = "OnIoReadDataCompleted";
        v31 = Buffer;
        v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
        v34 = "Flush of pending read data has failed.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&word_1801C8F7E,
          v28,
          v29,
          (__int64)&v34,
          (__int64)&v31,
          (__int64)&v35,
          (__int64)&v32,
          (__int64)&v33);
      }
      v14 = v30;
      goto LABEL_41;
    }
  }
LABEL_42:
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v36);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v37);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v38);
}

```

## disassembly

```asm
0x18010ddb0  mov     [rsp-8+arg_18], rbx
0x18010ddb5  push    rbp
0x18010ddb6  push    rsi
0x18010ddb7  push    rdi
0x18010ddb8  push    r12
0x18010ddba  push    r13
0x18010ddbc  push    r14
0x18010ddbe  push    r15
0x18010ddc0  lea     rbp, [rsp-17h]
0x18010ddc5  sub     rsp, 0B0h
0x18010ddcc  mov     rax, cs:__security_cookie
0x18010ddd3  xor     rax, rsp
0x18010ddd6  mov     [rbp+47h+var_38], rax
0x18010ddda  mov     r13, [rbp+47h+arg_20]
0x18010ddde  mov     r15d, edx
0x18010dde1  lea     rdx, [rcx+464h]; struct _GUID *
0x18010dde8  mov     r14, rcx
0x18010ddeb  xor     ebx, ebx
0x18010dded  lea     rcx, [rbp+47h+ActivityId]; ActivityId
0x18010ddf1  xor     edi, edi
0x18010ddf3  mov     [rbp+47h+var_58], rbx
0x18010ddf7  xor     esi, esi
0x18010ddf9  mov     [rbp+47h+var_60], rdi
0x18010ddfd  mov     r12d, r8d
0x18010de00  mov     [rbp+47h+var_68], rsi
0x18010de04  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18010de09  test    r15d, r15d
0x18010de0c  jz      short loc_18010DE86
0x18010de0e  mov     eax, cs:CallbackContext
0x18010de14  cmp     eax, 2
0x18010de17  jbe     short loc_18010DE7E
0x18010de19  lea     rax, aOnioreaddataco; "OnIoReadDataCompleted"
0x18010de20  mov     [rbp+47h+var_90], 4DDh
0x18010de27  mov     [rbp+47h+var_50], rax
0x18010de2b  lea     rdx, byte_1801C908D
0x18010de32  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010de39  mov     dword ptr [rbp+47h+var_88], r15d
0x18010de3d  mov     [rbp+47h+var_78], rax
0x18010de41  lea     rax, aReceivingDataH; "Receiving data has failed."
0x18010de48  mov     [rbp+47h+var_70], rax
0x18010de4c  lea     rax, [rbp+47h+var_50]
0x18010de50  mov     [rsp+0E0h+var_A0], rax
0x18010de55  lea     rax, [rbp+47h+var_90]
0x18010de59  mov     [rsp+0E0h+var_A8], rax
0x18010de5e  lea     rax, [rbp+47h+var_78]
0x18010de62  mov     [rsp+0E0h+var_B0], rax
0x18010de67  lea     rax, [rbp+47h+var_88]
0x18010de6b  mov     [rsp+0E0h+var_B8], rax
0x18010de70  lea     rax, [rbp+47h+var_70]
0x18010de74  mov     [rsp+0E0h+var_C0], rax
0x18010de79  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010de7e  mov     r9d, r15d
0x18010de81  jmp     loc_18010E2A4
0x18010de86  mov     rcx, [r14+718h]
0x18010de8d  test    rcx, rcx
0x18010de90  jz      loc_18010DF45
0x18010de96  mov     rax, [rcx]
0x18010de99  mov     r8d, r12d
0x18010de9c  mov     rdx, r13
0x18010de9f  mov     rax, [rax+8]
0x18010dea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dea8  mov     ecx, eax
0x18010deaa  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18010deaf  mov     edx, eax
0x18010deb1  test    eax, eax
0x18010deb3  jns     loc_18010DF45
0x18010deb9  mov     ecx, cs:CallbackContext
0x18010debf  cmp     ecx, 2
0x18010dec2  jbe     loc_18010E2B2
0x18010dec8  lea     rax, aTlsloggerDetec; "TLSLogger detected bad input data in CW"...
0x18010decf  mov     [rbp+47h+var_90], edx
0x18010ded2  mov     [rbp+47h+var_70], rax
0x18010ded6  lea     rdx, byte_1801C9017
0x18010dedd  lea     rax, aOnioreaddataco; "OnIoReadDataCompleted"
0x18010dee4  mov     dword ptr [rbp+47h+var_88], 4E5h
0x18010deeb  mov     [rbp+47h+var_78], rax
0x18010deef  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010def6  mov     [rbp+47h+var_50], rax
0x18010defa  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18010df01  mov     [rbp+47h+var_80], rax
0x18010df05  lea     rax, [rbp+47h+var_70]
0x18010df09  mov     [rsp+0E0h+var_98], rax
0x18010df0e  lea     rax, [rbp+47h+var_78]
0x18010df12  mov     [rsp+0E0h+var_A0], rax
0x18010df17  lea     rax, [rbp+47h+var_88]
0x18010df1b  mov     [rsp+0E0h+var_A8], rax
0x18010df20  lea     rax, [rbp+47h+var_50]
0x18010df24  mov     [rsp+0E0h+var_B0], rax
0x18010df29  lea     rax, [rbp+47h+var_90]
0x18010df2d  mov     [rsp+0E0h+var_B8], rax
0x18010df32  lea     rax, [rbp+47h+var_80]
0x18010df36  mov     [rsp+0E0h+var_C0], rax
0x18010df3b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18010df40  jmp     loc_18010E2B2
0x18010df45  cmp     [r14+68h], ebx
0x18010df49  jz      short loc_18010DFB5
0x18010df4b  cmp     r12d, 1
0x18010df4f  jnz     short loc_18010DFB5
0x18010df51  mov     eax, cs:CallbackContext
0x18010df57  cmp     eax, 4
0x18010df5a  jbe     short loc_18010DF86
0x18010df5c  lea     rax, aReaddataRead1B; "ReadData read 1 byte - completing liste"...
0x18010df63  xor     r8d, r8d
0x18010df66  mov     [rbp+47h+var_80], rax
0x18010df6a  lea     rdx, qword_1801C9068
0x18010df71  lea     rax, [rbp+47h+var_80]
0x18010df75  lea     rcx, CallbackContext
0x18010df7c  mov     [rsp+0E0h+var_C0], rax
0x18010df81  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18010df86  mov     rcx, [r14+98h]
0x18010df8d  lea     rdx, [r14-18h]
0x18010df91  mov     r8, [r14+0A0h]
0x18010df98  mov     [r14+68h], ebx
0x18010df9c  mov     dword ptr [r14+6Ch], 1
0x18010dfa4  mov     rax, [rcx]
0x18010dfa7  mov     rax, [rax+28h]
0x18010dfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dfb0  jmp     loc_18010E2B2
0x18010dfb5  lea     rcx, [r14+38h]; lpCriticalSection
0x18010dfb9  call    cs:__imp_EnterCriticalSection
0x18010dfbf  lea     r15, [r14+438h]
0x18010dfc6  cmp     [r15], rbx
0x18010dfc9  jnz     short loc_18010DFD0
0x18010dfcb  xor     r13d, r13d
0x18010dfce  jmp     short loc_18010DFEC
0x18010dfd0  lea     rcx, [rbp+47h+var_58]; void *
0x18010dfd4  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010dfd9  mov     rbx, [r15]
0x18010dfdc  lea     rcx, [rbp+47h+var_58]
0x18010dfe0  mov     [rbp+47h+var_58], rbx
0x18010dfe4  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010dfe9  mov     r13, rbx
0x18010dfec  lea     rcx, [r14+38h]; lpCriticalSection
0x18010dff0  call    cs:__imp_LeaveCriticalSection
0x18010dff6  xor     eax, eax
0x18010dff8  cmp     [r14+6Ch], eax
0x18010dffc  jz      loc_18010E095
0x18010e002  mov     [rbp+47h+var_90], eax
0x18010e005  lea     rdx, [rbp+47h+var_90]
0x18010e009  mov     [rbp+47h+var_88], rax
0x18010e00d  mov     rcx, r13
0x18010e010  mov     [r14+6Ch], eax
0x18010e014  mov     rax, [r13+0]
0x18010e018  mov     rax, [rax+38h]
0x18010e01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e021  cmp     [rbp+47h+var_90], 1
0x18010e025  jnz     short loc_18010E060
0x18010e027  mov     [rbp+47h+var_90], esi
0x18010e02a  lea     rdx, [rbp+47h+var_88]
0x18010e02e  mov     rax, [r13+0]
0x18010e032  mov     rcx, r13
0x18010e035  inc     r12d
0x18010e038  mov     rax, [rax+18h]
0x18010e03c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e041  mov     rax, [rbp+47h+var_88]
0x18010e045  mov     cl, [r14+70h]
0x18010e049  mov     [rax], cl
0x18010e04b  mov     rcx, r13
0x18010e04e  mov     rax, [r13+0]
0x18010e052  mov     edx, [rbp+47h+var_90]
0x18010e055  mov     rax, [rax+40h]
0x18010e059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e05e  jmp     short loc_18010E095
0x18010e060  mov     eax, cs:CallbackContext
0x18010e066  cmp     eax, 3
0x18010e069  jbe     short loc_18010E095
0x18010e06b  lea     rax, aTryingToPrepen; "Trying to prepend a byte from a previou"...
0x18010e072  xor     r8d, r8d
0x18010e075  mov     [rbp+47h+var_80], rax
0x18010e079  lea     rdx, byte_1801C8FC7
0x18010e080  lea     rax, [rbp+47h+var_80]
0x18010e084  lea     rcx, CallbackContext
0x18010e08b  mov     [rsp+0E0h+var_C0], rax
0x18010e090  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18010e095  mov     eax, cs:CallbackContext
0x18010e09b  cmp     eax, 5
0x18010e09e  jbe     short loc_18010E0CD
0x18010e0a0  lea     rax, aReceivedDataFr; "Received data from server"
0x18010e0a7  mov     dword ptr [rbp+47h+var_88], r12d
0x18010e0ab  mov     [rbp+47h+var_80], rax
0x18010e0af  lea     rdx, dword_1801C8FEC
0x18010e0b6  lea     rax, [rbp+47h+var_88]
0x18010e0ba  mov     [rsp+0E0h+var_B8], rax
0x18010e0bf  lea     rax, [rbp+47h+var_80]
0x18010e0c3  mov     [rsp+0E0h+var_C0], rax
0x18010e0c8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18010e0cd  lea     rcx, [r14+38h]; lpCriticalSection
0x18010e0d1  call    cs:__imp_EnterCriticalSection
0x18010e0d7  cmp     [r15], rsi
0x18010e0da  jz      short loc_18010E0EF
0x18010e0dc  mov     rcx, r15; void *
0x18010e0df  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010e0e4  mov     rcx, r15
0x18010e0e7  mov     [r15], rsi
0x18010e0ea  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010e0ef  xor     r15d, r15d
0x18010e0f2  cmp     [r14+90h], r15
0x18010e0f9  jz      short loc_18010E118
0x18010e0fb  lea     rcx, [rbp+47h+var_60]; void *
0x18010e0ff  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010e104  mov     rdi, [r14+90h]
0x18010e10b  lea     rcx, [rbp+47h+var_60]
0x18010e10f  mov     [rbp+47h+var_60], rdi
0x18010e113  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010e118  cmp     [r14+440h], r15
0x18010e11f  jz      short loc_18010E13E
0x18010e121  lea     rcx, [rbp+47h+var_68]; void *
0x18010e125  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18010e12a  mov     rsi, [r14+440h]
0x18010e131  lea     rcx, [rbp+47h+var_68]
0x18010e135  mov     [rbp+47h+var_68], rsi
0x18010e139  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18010e13e  lea     rcx, [r14+38h]; lpCriticalSection
0x18010e142  call    cs:__imp_LeaveCriticalSection
0x18010e148  test    rsi, rsi
0x18010e14b  jz      loc_18010E1F6
0x18010e151  mov     rcx, [r14+700h]
0x18010e158  lea     eax, ds:0[r12*8]
0x18010e160  add     [r14+44Ch], eax
0x18010e167  test    rcx, rcx
0x18010e16a  jz      short loc_18010E17B
0x18010e16c  mov     rax, [rcx]
0x18010e16f  mov     edx, r12d
0x18010e172  mov     rax, [rax+8]
0x18010e176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e17b  call    cs:__imp_GetTickCount
0x18010e181  sub     eax, [r14+454h]
0x18010e188  cmp     eax, 64h ; 'd'
0x18010e18b  jbe     short loc_18010E1F6
0x18010e18d  mov     rax, [rsi]
0x18010e190  mov     edx, 69h ; 'i'
0x18010e195  mov     r8d, [r14+44Ch]
0x18010e19c  mov     rcx, rsi
0x18010e19f  mov     rax, [rax+20h]
0x18010e1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e1a8  mov     rax, [rsi]
0x18010e1ab  mov     edx, 68h ; 'h'
0x18010e1b0  mov     r8d, [r14+44Ch]
0x18010e1b7  mov     rcx, rsi
0x18010e1ba  mov     rax, [rax+20h]
0x18010e1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e1c3  mov     rax, [rsi]
0x18010e1c6  mov     edx, 7Ch ; '|'
0x18010e1cb  mov     r8d, [r14+44Ch]
0x18010e1d2  mov     rcx, rsi
0x18010e1d5  shr     r8d, 3
0x18010e1d9  mov     rax, [rax+20h]
0x18010e1dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e1e2  call    cs:__imp_GetTickCount
0x18010e1e8  mov     [r14+454h], eax
0x18010e1ef  mov     [r14+44Ch], r15d
0x18010e1f6  mov     rax, [rbx]
0x18010e1f9  mov     edx, r12d
0x18010e1fc  mov     rcx, rbx
0x18010e1ff  mov     rax, [rax+30h]
0x18010e203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e208  test    rdi, rdi
0x18010e20b  jz      short loc_18010E21F
0x18010e20d  mov     rax, [rdi]
0x18010e210  mov     rdx, rbx
0x18010e213  mov     rcx, rdi
0x18010e216  mov     rax, [rax+20h]
0x18010e21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e21f  lea     rcx, [r14-18h]; this
0x18010e223  call    ?FlushReadBuffer@CWSStream@@AEAAJXZ; CWSStream::FlushReadBuffer(void)
0x18010e228  mov     ebx, eax
0x18010e22a  test    eax, eax
0x18010e22c  jns     loc_18010E2B2
0x18010e232  mov     ecx, cs:CallbackContext
0x18010e238  cmp     ecx, 2
0x18010e23b  jbe     short loc_18010E2A1
0x18010e23d  lea     rax, aOnioreaddataco; "OnIoReadDataCompleted"
0x18010e244  mov     dword ptr [rbp+47h+var_88], 54Dh
0x18010e24b  mov     [rbp+47h+var_80], rax
0x18010e24f  lea     rdx, word_1801C8F7E
0x18010e256  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010e25d  mov     [rbp+47h+var_90], ebx
0x18010e260  mov     [rbp+47h+var_70], rax
0x18010e264  lea     rax, aFlushOfPending_0; "Flush of pending read data has failed."
0x18010e26b  mov     [rbp+47h+var_78], rax
0x18010e26f  lea     rax, [rbp+47h+var_80]
0x18010e273  mov     [rsp+0E0h+var_A0], rax
0x18010e278  lea     rax, [rbp+47h+var_88]
0x18010e27c  mov     [rsp+0E0h+var_A8], rax
0x18010e281  lea     rax, [rbp+47h+var_70]
0x18010e285  mov     [rsp+0E0h+var_B0], rax
0x18010e28a  lea     rax, [rbp+47h+var_90]
0x18010e28e  mov     [rsp+0E0h+var_B8], rax
0x18010e293  lea     rax, [rbp+47h+var_78]
0x18010e297  mov     [rsp+0E0h+var_C0], rax
0x18010e29c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010e2a1  mov     r9d, ebx; int
0x18010e2a4  xor     r8d, r8d; unsigned int
0x18010e2a7  lea     rcx, [r14-18h]; this
0x18010e2ab  xor     edx, edx; int
0x18010e2ad  call    ?CloseInternal@CWSStream@@AEAAJHKJ@Z; CWSStream::CloseInternal(int,ulong,long)
0x18010e2b2  lea     rcx, [rbp+47h+ActivityId]; ActivityId
0x18010e2b6  call    ??1CAutoSetThreadActivityId@@QEAA@XZ; CAutoSetThreadActivityId::~CAutoSetThreadActivityId(void)
0x18010e2bb  lea     rcx, [rbp+47h+var_68]; void *
0x18010e2bf  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
  ... truncated ...
```
