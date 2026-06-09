# CRdpUdpTransport::Initialize(int)

- ea: `0x1800698e4`
- end: `0x180069f5e`
- name: `?Initialize@CRdpUdpTransport@@QEAAJH@Z`
- size: `1658`
- prototype: `__int64 __fastcall(CRdpUdpTransport *__hidden this, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18012fc68`
- `0x18012ff2c`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x180005090`
- `0x1800698e4`
- `0x1800787d4`
- `0x180078c20`
- `0x18007969c`
- `0x1800e57b0`
- `0x180121580`
- `0x1801216a0`
- `0x180127af0`
- `0x1801281e0`
- `0x18012d71c`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069a2f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180069af2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180069bbc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180069af2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180069bbc`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180069a16`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180069a16`
- `WS2_32!__imp_WSAStartup` at `0x180069939`
- `WS2_32!__imp_WSAStartup` at `0x180069939`

## string_xrefs

- `0x180069b1a`: `Failed to create event`
- `0x180069cb8`: `Failed to create event`
- `0x180069bf1`: `Failed to create event in CRdpUdpTransport::Initialize`
- `0x180069a53`: `Failed to create transport timer`
- `0x180069e91`: `UDP InitializeConnector failed to create client state transition logger.`

## pseudocode

```c
__int64 __fastcall CRdpUdpTransport::Initialize(CRdpUdpTransport *this, int a2)
{
  CRDPENCONResolver *v4; // rax
  int v5; // r8d
  int v6; // r9d
  signed int ClientEventLogCallback; // edi
  HANDLE WaitableTimerW; // rax
  signed int LastError; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  HANDLE EventW; // rax
  int v14; // r8d
  int v15; // r9d
  HANDLE v16; // rsi
  HANDLE v17; // rax
  int v18; // r8d
  int v19; // r9d
  CRdpUdpTransport *v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  int v23; // r8d
  int v24; // r9d
  int v25; // eax
  int v26; // r8d
  int v27; // r9d
  int v28; // r9d
  __int64 v29; // rsi
  __int64 v30; // rbx
  __int64 RdpClientStateName; // rax
  __int64 v32; // r11
  __int64 v33; // r8
  __int64 v34; // r10
  int v36; // [rsp+50h] [rbp-B0h] BYREF
  struct ISharedHandle *v37; // [rsp+58h] [rbp-A8h] BYREF
  const char *v38; // [rsp+60h] [rbp-A0h] BYREF
  const char *v39; // [rsp+68h] [rbp-98h] BYREF
  const char *v40; // [rsp+70h] [rbp-90h] BYREF
  const char *v41; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v42[4]; // [rsp+80h] [rbp-80h] BYREF
  struct WSAData WSAData; // [rsp+90h] [rbp-70h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  *((_DWORD *)this + 108) = a2;
  WSAStartup(2u, &WSAData);
  *((_DWORD *)this + 117) = 1;
  v4 = (CRDPENCONResolver *)operator new(0xA0u);
  if ( v4 )
    v4 = CRDPENCONResolver::CRDPENCONResolver(v4);
  *((_QWORD *)this + 53) = v4;
  if ( v4 )
  {
    WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
    *((_QWORD *)this + 35) = WaitableTimerW;
    if ( WaitableTimerW )
    {
      (*(void (__fastcall **)(char *, HANDLE))(*((_QWORD *)this + 41) + 8LL))((char *)this + 328, WaitableTimerW);
      EventW = CreateEventW(0, 0, 0, 0);
      v16 = EventW;
      if ( EventW )
      {
        (*(void (__fastcall **)(char *, HANDLE))(*((_QWORD *)this + 41) + 8LL))((char *)this + 328, EventW);
        *((_QWORD *)this + 37) = v16;
        v17 = CreateEventW(0, 0, 0, 0);
        v37 = 0;
        ClientEventLogCallback = SharedHandle::CreateInstance(v17, &v37);
        if ( ClientEventLogCallback >= 0 )
        {
          v20 = (CRdpUdpTransport *)*((_QWORD *)this + 50);
          *((_QWORD *)this + 50) = v37;
          if ( v20 )
            (*(void (__fastcall **)(CRdpUdpTransport *))(*(_QWORD *)v20 + 16LL))(v20);
          if ( *((_QWORD *)this + 50) )
          {
            v42[0] = 4;
            *((_DWORD *)this + 28) = 0;
            CRdpUdpTransport::ReadRegistryValue(v20, L"UdpDebugFlags", (unsigned __int8 *)this + 112, v42);
            *((_DWORD *)this + 7) |= 2u;
            v21 = *((_QWORD *)this + 15);
            if ( v21 )
            {
              v22 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, GUID *, char *))(*(_QWORD *)v21 + 48LL))(
                      v21,
                      L"RDP::EventLog::Session",
                      &IID_IRdpTransportEventLogCallbacks,
                      (char *)this + 440);
              if ( v22 < 0 && (unsigned int)CallbackContext > 3 )
              {
                LODWORD(v37) = v22;
                v38 = "Initialize";
                v40 = "Failed to get event log instance, but it is OK.";
                v39 = "HResult failed but continue";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  (_DWORD)CallbackContext,
                  (unsigned int)byte_1801D03FD,
                  v23,
                  v24,
                  (__int64)&v39,
                  (__int64)&v40,
                  (__int64)&v37,
                  (__int64)&v38);
              }
              v25 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, GUID *, char *))(**((_QWORD **)this + 15) + 48LL))(
                      *((_QWORD *)this + 15),
                      L"RDP::EventLog::Session",
                      &IID_IRdpStateTransitionEventLogCallbacks,
                      (char *)this + 448);
              if ( v25 < 0 && (unsigned int)CallbackContext > 3 )
              {
                LODWORD(v37) = v25;
                v38 = "Initialize";
                v40 = "Failed to get state transtition event log instance, but it is OK.";
                v39 = "HResult failed but continue";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  (_DWORD)CallbackContext,
                  (unsigned int)&dword_1801D2A64,
                  v26,
                  v27,
                  (__int64)&v39,
                  (__int64)&v40,
                  (__int64)&v37,
                  (__int64)&v38);
              }
            }
            ClientEventLogCallback = CRdpUdpTransport::CreateClientEventLogCallback(this);
            if ( ClientEventLogCallback < 0 )
            {
              if ( (unsigned int)CallbackContext > 3 )
              {
                v38 = "UDP InitializeConnector failed to create client state transition logger.";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (unsigned int)&CallbackContext,
                  (unsigned int)&word_1801D1CF6,
                  0,
                  v28,
                  (__int64)&v38);
              }
              ClientEventLogCallback = 0;
            }
            v29 = *((_QWORD *)this + 57);
            if ( v29 )
            {
              v30 = (unsigned int)(a2 != 0) + 2;
              GetRdpClientEventName(v30, 0);
              GetRdpClientStateName((unsigned int)v30, 1);
              RdpClientStateName = GetRdpClientStateName((unsigned int)v30, 0);
              (*(void (__fastcall **)(__int64, const unsigned __int16 * near *, _QWORD, __int64, int, __int64, _DWORD, __int64))(v32 + 24))(
                v29,
                (&RDPClientStateTransitionNameTable)[v30],
                0,
                RdpClientStateName,
                1,
                v33,
                0,
                v34);
            }
          }
          else
          {
            ClientEventLogCallback = -2147024882;
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(v37) = 275;
              v38 = "Failed to create event";
              v40 = "Initialize";
              v39 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
              v36 = -2147024882;
              v41 = "Error condition failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                -2147024882,
                (unsigned int)byte_1801D2A19,
                v18,
                v19,
                (__int64)&v41,
                (__int64)&v36,
                (__int64)&v39,
                (__int64)&v37,
                (__int64)&v40,
                (__int64)&v38);
            }
          }
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v37) = 270;
          v38 = "Failed to create event in CRdpUdpTransport::Initialize";
          v40 = "Initialize";
          v39 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
          v36 = ClientEventLogCallback;
          v41 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)byte_1801D247D,
            v18,
            v19,
            (__int64)&v41,
            (__int64)&v36,
            (__int64)&v39,
            (__int64)&v37,
            (__int64)&v40,
            (__int64)&v38);
        }
      }
      else
      {
        ClientEventLogCallback = -2147024882;
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v37) = 262;
          v38 = "Failed to create event";
          v40 = "Initialize";
          v39 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
          v36 = -2147024882;
          v41 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147024882,
            (unsigned int)byte_1801D0C75,
            v14,
            v15,
            (__int64)&v41,
            (__int64)&v36,
            (__int64)&v39,
            (__int64)&v37,
            (__int64)&v40,
            (__int64)&v38);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      ClientEventLogCallback = LastError;
      if ( LastError > 0 )
        ClientEventLogCallback = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v37) = 258;
        v38 = "Failed to create transport timer";
        v40 = "Initialize";
        v39 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
        v36 = ClientEventLogCallback;
        v41 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v10,
          (unsigned int)&word_1801D24F6,
          v11,
          v12,
          (__int64)&v41,
          (__int64)&v36,
          (__int64)&v39,
          (__int64)&v37,
          (__int64)&v40,
          (__int64)&v38);
      }
    }
  }
  else
  {
    ClientEventLogCallback = -2147024882;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v36 = 255;
      v41 = "CRDPENCONResolver allocation failed";
      v39 = "Initialize";
      v40 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
      LODWORD(v37) = -2147024882;
      v38 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024882,
        (unsigned int)&dword_1801D0E5C,
        v5,
        v6,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v40,
        (__int64)&v36,
        (__int64)&v39,
        (__int64)&v41);
    }
  }
  return (unsigned int)ClientEventLogCallback;
}

```

## disassembly

```asm
0x1800698e4  mov     [rsp-8+arg_8], rbx
0x1800698e9  mov     [rsp-8+arg_10], rsi
0x1800698ee  push    rbp
0x1800698ef  push    rdi
0x1800698f0  push    r14
0x1800698f2  lea     rbp, [rsp-140h]
0x1800698fa  sub     rsp, 240h
0x180069901  mov     rax, cs:__security_cookie
0x180069908  xor     rax, rsp
0x18006990b  mov     [rbp+150h+var_20], rax
0x180069912  mov     r14d, edx
0x180069915  mov     rbx, rcx
0x180069918  xor     edx, edx; Val
0x18006991a  lea     rcx, [rbp+150h+WSAData]; void *
0x18006991e  mov     r8d, 198h; Size
0x180069924  call    memset_0
0x180069929  mov     ecx, 2; wVersionRequested
0x18006992e  mov     [rbx+1B0h], r14d
0x180069935  lea     rdx, [rbp+150h+WSAData]; lpWSAData
0x180069939  call    cs:__imp_WSAStartup
0x18006993f  mov     ecx, 0A0h; Size
0x180069944  mov     dword ptr [rbx+1D4h], 1
0x18006994e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069953  test    rax, rax
0x180069956  jz      short loc_180069960
0x180069958  mov     rcx, rax; this
0x18006995b  call    ??0CRDPENCONResolver@@QEAA@XZ; CRDPENCONResolver::CRDPENCONResolver(void)
0x180069960  mov     [rbx+1A8h], rax
0x180069967  test    rax, rax
0x18006996a  jnz     loc_180069A0F
0x180069970  mov     eax, cs:CallbackContext
0x180069976  mov     ecx, 8007000Eh
0x18006997b  mov     edi, ecx
0x18006997d  cmp     eax, 2
0x180069980  jbe     loc_180069F35
0x180069986  lea     rax, aCrdpenconresol; "CRDPENCONResolver allocation failed"
0x18006998d  mov     [rsp+250h+var_200], 0FFh
0x180069995  mov     [rsp+250h+var_1D8], rax
0x18006999a  lea     rsi, aInitialize; "Initialize"
0x1800699a1  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800699a8  mov     [rsp+250h+var_1E8], rsi
0x1800699ad  mov     [rsp+250h+var_1E0], rax
0x1800699b2  lea     rdx, dword_1801D0E5C
0x1800699b9  lea     rax, aErrorCondition; "Error condition failed"
0x1800699c0  mov     dword ptr [rsp+250h+var_1F8], ecx
0x1800699c4  mov     [rsp+250h+var_1F0], rax
0x1800699c9  lea     rax, [rsp+250h+var_1D8]
0x1800699ce  mov     [rsp+250h+var_208], rax
0x1800699d3  lea     rax, [rsp+250h+var_1E8]
0x1800699d8  mov     [rsp+250h+var_210], rax
0x1800699dd  lea     rax, [rsp+250h+var_200]
0x1800699e2  mov     [rsp+250h+var_218], rax
0x1800699e7  lea     rax, [rsp+250h+var_1E0]
0x1800699ec  mov     [rsp+250h+var_220], rax
0x1800699f1  lea     rax, [rsp+250h+var_1F8]
0x1800699f6  mov     [rsp+250h+var_228], rax
0x1800699fb  lea     rax, [rsp+250h+var_1F0]
0x180069a00  mov     [rsp+250h+var_230], rax
0x180069a05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180069a0a  jmp     loc_180069F35
0x180069a0f  xor     r8d, r8d; lpTimerName
0x180069a12  xor     edx, edx; bManualReset
0x180069a14  xor     ecx, ecx; lpTimerAttributes
0x180069a16  call    cs:__imp_CreateWaitableTimerW
0x180069a1c  mov     [rbx+118h], rax
0x180069a23  mov     rdx, rax
0x180069a26  test    rax, rax
0x180069a29  jnz     loc_180069AD2
0x180069a2f  call    cs:__imp_GetLastError
0x180069a35  mov     edi, eax
0x180069a37  test    eax, eax
0x180069a39  jle     short loc_180069A44
0x180069a3b  movzx   edi, ax
0x180069a3e  or      edi, 80070000h
0x180069a44  mov     eax, cs:CallbackContext
0x180069a4a  cmp     eax, 2
0x180069a4d  jbe     loc_180069F35
0x180069a53  lea     rax, aFailedToCreate_67; "Failed to create transport timer"
0x180069a5a  mov     dword ptr [rsp+250h+var_1F8], 102h
0x180069a62  mov     [rsp+250h+var_1F0], rax
0x180069a67  lea     rsi, aInitialize; "Initialize"
0x180069a6e  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180069a75  mov     [rsp+250h+var_1E0], rsi
0x180069a7a  mov     [rsp+250h+var_1E8], rax
0x180069a7f  lea     rdx, word_1801D24F6
0x180069a86  lea     rax, aErrorCondition; "Error condition failed"
0x180069a8d  mov     [rsp+250h+var_200], edi
0x180069a91  mov     [rsp+250h+var_1D8], rax
0x180069a96  lea     rax, [rsp+250h+var_1F0]
0x180069a9b  mov     [rsp+250h+var_208], rax
0x180069aa0  lea     rax, [rsp+250h+var_1E0]
0x180069aa5  mov     [rsp+250h+var_210], rax
0x180069aaa  lea     rax, [rsp+250h+var_1F8]
0x180069aaf  mov     [rsp+250h+var_218], rax
0x180069ab4  lea     rax, [rsp+250h+var_1E8]
0x180069ab9  mov     [rsp+250h+var_220], rax
0x180069abe  lea     rax, [rsp+250h+var_200]
0x180069ac3  mov     [rsp+250h+var_228], rax
0x180069ac8  lea     rax, [rsp+250h+var_1D8]
0x180069acd  jmp     loc_180069A00
0x180069ad2  lea     rdi, [rbx+148h]
0x180069ad9  mov     rax, [rdi]
0x180069adc  mov     rcx, rdi
0x180069adf  mov     rax, [rax+8]
0x180069ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ae8  xor     r9d, r9d; lpName
0x180069aeb  xor     r8d, r8d; bInitialState
0x180069aee  xor     edx, edx; bManualReset
0x180069af0  xor     ecx, ecx; lpEventAttributes
0x180069af2  call    cs:__imp_CreateEventW
0x180069af8  mov     rsi, rax
0x180069afb  test    rax, rax
0x180069afe  jnz     loc_180069B99
0x180069b04  mov     eax, cs:CallbackContext
0x180069b0a  mov     ecx, 8007000Eh
0x180069b0f  mov     edi, ecx
0x180069b11  cmp     eax, 2
0x180069b14  jbe     loc_180069F35
0x180069b1a  lea     rax, aFailedToCreate_73; "Failed to create event"
0x180069b21  mov     dword ptr [rsp+250h+var_1F8], 106h
0x180069b29  mov     [rsp+250h+var_1F0], rax
0x180069b2e  lea     rsi, aInitialize; "Initialize"
0x180069b35  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180069b3c  mov     [rsp+250h+var_1E0], rsi
0x180069b41  mov     [rsp+250h+var_1E8], rax
0x180069b46  lea     rdx, byte_1801D0C75
0x180069b4d  lea     rax, aErrorCondition; "Error condition failed"
0x180069b54  mov     [rsp+250h+var_200], ecx
0x180069b58  mov     [rsp+250h+var_1D8], rax
0x180069b5d  lea     rax, [rsp+250h+var_1F0]
0x180069b62  mov     [rsp+250h+var_208], rax
0x180069b67  lea     rax, [rsp+250h+var_1E0]
0x180069b6c  mov     [rsp+250h+var_210], rax
0x180069b71  lea     rax, [rsp+250h+var_1F8]
0x180069b76  mov     [rsp+250h+var_218], rax
0x180069b7b  lea     rax, [rsp+250h+var_1E8]
0x180069b80  mov     [rsp+250h+var_220], rax
0x180069b85  lea     rax, [rsp+250h+var_200]
0x180069b8a  mov     [rsp+250h+var_228], rax
0x180069b8f  lea     rax, [rsp+250h+var_1D8]
0x180069b94  jmp     loc_180069A00
0x180069b99  mov     rax, [rdi]
0x180069b9c  mov     rdx, rsi
0x180069b9f  mov     rcx, rdi
0x180069ba2  mov     rax, [rax+8]
0x180069ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069bab  xor     r9d, r9d; lpName
0x180069bae  mov     [rbx+128h], rsi
0x180069bb5  xor     r8d, r8d; bInitialState
0x180069bb8  xor     edx, edx; bManualReset
0x180069bba  xor     ecx, ecx; lpEventAttributes
0x180069bbc  call    cs:__imp_CreateEventW
0x180069bc2  lea     rdx, [rsp+250h+var_1F8]; struct ISharedHandle **
0x180069bc7  mov     [rsp+250h+var_1F8], 0
0x180069bd0  mov     rcx, rax; void *
0x180069bd3  call    ?CreateInstance@SharedHandle@@SAJPEAXPEAPEAUISharedHandle@@@Z; SharedHandle::CreateInstance(void *,ISharedHandle * *)
0x180069bd8  mov     edi, eax
0x180069bda  test    eax, eax
0x180069bdc  jns     loc_180069C70
0x180069be2  mov     ecx, cs:CallbackContext
0x180069be8  cmp     ecx, 2
0x180069beb  jbe     loc_180069F35
0x180069bf1  lea     rax, aFailedToCreate_58; "Failed to create event in CRdpUdpTransp"...
0x180069bf8  mov     dword ptr [rsp+250h+var_1F8], 10Eh
0x180069c00  mov     [rsp+250h+var_1F0], rax
0x180069c05  lea     rsi, aInitialize; "Initialize"
0x180069c0c  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180069c13  mov     [rsp+250h+var_1E0], rsi
0x180069c18  mov     [rsp+250h+var_1E8], rax
0x180069c1d  lea     rdx, byte_1801D247D
0x180069c24  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180069c2b  mov     [rsp+250h+var_200], edi
0x180069c2f  mov     [rsp+250h+var_1D8], rax
0x180069c34  lea     rax, [rsp+250h+var_1F0]
0x180069c39  mov     [rsp+250h+var_208], rax
0x180069c3e  lea     rax, [rsp+250h+var_1E0]
0x180069c43  mov     [rsp+250h+var_210], rax
0x180069c48  lea     rax, [rsp+250h+var_1F8]
0x180069c4d  mov     [rsp+250h+var_218], rax
0x180069c52  lea     rax, [rsp+250h+var_1E8]
0x180069c57  mov     [rsp+250h+var_220], rax
0x180069c5c  lea     rax, [rsp+250h+var_200]
0x180069c61  mov     [rsp+250h+var_228], rax
0x180069c66  lea     rax, [rsp+250h+var_1D8]
0x180069c6b  jmp     loc_180069A00
0x180069c70  mov     rcx, [rbx+190h]
0x180069c77  mov     rax, [rsp+250h+var_1F8]
0x180069c7c  mov     [rbx+190h], rax
0x180069c83  test    rcx, rcx
0x180069c86  jz      short loc_180069C94
0x180069c88  mov     rax, [rcx]
0x180069c8b  mov     rax, [rax+10h]
0x180069c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069c94  cmp     qword ptr [rbx+190h], 0
0x180069c9c  jnz     loc_180069D37
0x180069ca2  mov     eax, cs:CallbackContext
0x180069ca8  mov     ecx, 8007000Eh
0x180069cad  mov     edi, ecx
0x180069caf  cmp     eax, 2
0x180069cb2  jbe     loc_180069F35
0x180069cb8  lea     rax, aFailedToCreate_73; "Failed to create event"
0x180069cbf  mov     dword ptr [rsp+250h+var_1F8], 113h
0x180069cc7  mov     [rsp+250h+var_1F0], rax
0x180069ccc  lea     rsi, aInitialize; "Initialize"
0x180069cd3  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180069cda  mov     [rsp+250h+var_1E0], rsi
0x180069cdf  mov     [rsp+250h+var_1E8], rax
0x180069ce4  lea     rdx, byte_1801D2A19
0x180069ceb  lea     rax, aErrorCondition; "Error condition failed"
0x180069cf2  mov     [rsp+250h+var_200], ecx
0x180069cf6  mov     [rsp+250h+var_1D8], rax
0x180069cfb  lea     rax, [rsp+250h+var_1F0]
0x180069d00  mov     [rsp+250h+var_208], rax
0x180069d05  lea     rax, [rsp+250h+var_1E0]
0x180069d0a  mov     [rsp+250h+var_210], rax
0x180069d0f  lea     rax, [rsp+250h+var_1F8]
0x180069d14  mov     [rsp+250h+var_218], rax
0x180069d19  lea     rax, [rsp+250h+var_1E8]
0x180069d1e  mov     [rsp+250h+var_220], rax
0x180069d23  lea     rax, [rsp+250h+var_200]
0x180069d28  mov     [rsp+250h+var_228], rax
0x180069d2d  lea     rax, [rsp+250h+var_1D8]
0x180069d32  jmp     loc_180069A00
0x180069d37  lea     r8, [rbx+70h]; unsigned __int8 *
0x180069d3b  mov     [rbp+150h+var_1D0], 4
0x180069d42  lea     r9, [rbp+150h+var_1D0]; unsigned int *
0x180069d46  mov     dword ptr [r8], 0
0x180069d4d  lea     rdx, aUdpdebugflags; "UdpDebugFlags"
0x180069d54  call    ?ReadRegistryValue@CRdpUdpTransport@@IEAAHPEAGPEAEPEAK@Z; CRdpUdpTransport::ReadRegistryValue(ushort *,uchar *,ulong *)
0x180069d59  or      dword ptr [rbx+1Ch], 2
0x180069d5d  mov     rcx, [rbx+78h]
0x180069d61  test    rcx, rcx
0x180069d64  jz      loc_180069E78
0x180069d6a  mov     rax, [rcx]
0x180069d6d  lea     r9, [rbx+1B8h]
0x180069d74  lea     r8, IID_IRdpTransportEventLogCallbacks
0x180069d7b  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x180069d82  mov     rax, [rax+30h]
0x180069d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d8b  lea     rsi, aInitialize; "Initialize"
0x180069d92  lea     rdi, aHresultFailedB; "HResult failed but continue"
0x180069d99  test    eax, eax
0x180069d9b  jns     short loc_180069DF6
0x180069d9d  mov     ecx, cs:CallbackContext
0x180069da3  cmp     ecx, 3
0x180069da6  jbe     short loc_180069DF6
0x180069da8  mov     dword ptr [rsp+250h+var_1F8], eax
0x180069dac  lea     rdx, byte_1801D03FD
0x180069db3  lea     rax, aFailedToGetEve; "Failed to get event log instance, but i"...
0x180069dba  mov     [rsp+250h+var_1F0], rsi
0x180069dbf  mov     [rsp+250h+var_1E0], rax
0x180069dc4  lea     rax, [rsp+250h+var_1F0]
0x180069dc9  mov     [rsp+250h+var_218], rax
0x180069dce  lea     rax, [rsp+250h+var_1F8]
0x180069dd3  mov     [rsp+250h+var_220], rax
0x180069dd8  lea     rax, [rsp+250h+var_1E0]
0x180069ddd  mov     [rsp+250h+var_228], rax
0x180069de2  lea     rax, [rsp+250h+var_1E8]
0x180069de7  mov     [rsp+250h+var_230], rax
0x180069dec  mov     [rsp+250h+var_1E8], rdi
0x180069df1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180069df6  mov     rcx, [rbx+78h]
0x180069dfa  lea     r9, [rbx+1C0h]
0x180069e01  lea     r8, IID_IRdpStateTransitionEventLogCallbacks
0x180069e08  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x180069e0f  mov     rax, [rcx]
0x180069e12  mov     rax, [rax+30h]
0x180069e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069e1b  test    eax, eax
0x180069e1d  jns     short loc_180069E78
0x180069e1f  mov     ecx, cs:CallbackContext
0x180069e25  cmp     ecx, 3
0x180069e28  jbe     short loc_180069E78
0x180069e2a  mov     dword ptr [rsp+250h+var_1F8], eax
0x180069e2e  lea     rdx, dword_1801D2A64
0x180069e35  lea     rax, aFailedToGetSta; "Failed to get state transtition event l"...
0x180069e3c  mov     [rsp+250h+var_1F0], rsi
0x180069e41  mov     [rsp+250h+var_1E0], rax
0x180069e46  lea     rax, [rsp+250h+var_1F0]
0x180069e4b  mov     [rsp+250h+var_218], rax
0x180069e50  lea     rax, [rsp+250h+var_1F8]
0x180069e55  mov     [rsp+250h+var_220], rax
0x180069e5a  lea     rax, [rsp+250h+var_1E0]
0x180069e5f  mov     [rsp+250h+var_228], rax
0x180069e64  lea     rax, [rsp+250h+var_1E8]
0x180069e69  mov     [rsp+250h+var_230], rax
0x180069e6e  mov     [rsp+250h+var_1E8], rdi
0x180069e73  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180069e78  mov     rcx, rbx; this
0x180069e7b  call    ?CreateClientEventLogCallback@CRdpUdpTransport@@IEAAJXZ; CRdpUdpTransport::CreateClientEventLogCallback(void)
0x180069e80  mov     edi, eax
0x180069e82  test    eax, eax
0x180069e84  jns     short loc_180069EBF
0x180069e86  mov     eax, cs:CallbackContext
0x180069e8c  cmp     eax, 3
0x180069e8f  jbe     short loc_180069EBD
0x180069e91  lea     rax, aUdpInitializec_0; "UDP InitializeConnector failed to creat"...
0x180069e98  xor     r8d, r8d
0x180069e9b  mov     [rsp+250h+var_1F0], rax
0x180069ea0  lea     rdx, word_1801D1CF6
  ... truncated ...
```
