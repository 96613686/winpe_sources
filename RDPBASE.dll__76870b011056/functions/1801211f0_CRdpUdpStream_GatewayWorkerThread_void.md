# CRdpUdpStream::GatewayWorkerThread(void)

- ea: `0x1801211f0`
- end: `0x18012149e`
- name: `?GatewayWorkerThread@CRdpUdpStream@@QEAAXXZ`
- size: `686`
- prototype: `void __fastcall(CRdpUdpStream *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180124420`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x180003158`
- `0x180018660`
- `0x180019a80`
- `0x180019ab0`
- `0x18001b3f8`
- `0x180068cb0`
- `0x180078c20`
- `0x1801211f0`
- `0x1801241a0`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180121227`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180121227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121281`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180121349`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180121349`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18012126f`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18012126f`

## string_xrefs

- `0x1801212a5`: `Failed to create gateway timer`
- `0x1801212be`: `GatewayWorkerThread`

## pseudocode

```c
void __fastcall CRdpUdpStream::GatewayWorkerThread(CRdpUdpStream *this)
{
  __int64 v2; // rcx
  __int64 v3; // rsi
  __int64 v4; // rdi
  HANDLE WaitableTimerW; // rax
  HANDLE v6; // rdi
  signed int LastError; // eax
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ecx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // [rsp+50h] [rbp-29h] BYREF
  int v15; // [rsp+54h] [rbp-25h] BYREF
  const char *v16; // [rsp+58h] [rbp-21h] BYREF
  __int64 v17; // [rsp+60h] [rbp-19h] BYREF
  const char *v18; // [rsp+68h] [rbp-11h] BYREF
  const char *v19; // [rsp+70h] [rbp-9h] BYREF
  const char *v20; // [rsp+78h] [rbp-1h] BYREF
  LARGE_INTEGER DueTime; // [rsp+80h] [rbp+7h] BYREF
  _QWORD v22[2]; // [rsp+88h] [rbp+Fh] BYREF
  GUID ActivityId; // [rsp+98h] [rbp+1Fh] BYREF

  ActivityId = *(GUID *)((char *)this + 628);
  EventActivityIdControl(4u, &ActivityId);
  v2 = *((_QWORD *)this + 13);
  v17 = 0;
  v3 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 64LL))(v2);
  if ( v4 )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v17);
    v17 = v4;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v17);
    v3 = v4;
  }
  WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
  v6 = WaitableTimerW;
  if ( WaitableTimerW )
  {
    DueTime.QuadPart = -200000;
    SetWaitableTimer(WaitableTimerW, &DueTime, 20, 0, 0, 0);
    v22[1] = *((_QWORD *)this + 56);
    v22[0] = v6;
    while ( 1 )
    {
      v14 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v3 + 80LL))(v3, 2, v22) < 0 )
        break;
      v11 = CRdpUdpStream::OnTransportTimer((CRdpUdpStream *)((char *)this + 72));
      if ( v11 )
      {
        if ( v11 < 0 )
        {
          if ( (unsigned int)CallbackContext > 4 )
          {
            v15 = -2147001850;
            v16 = "GatewayWorker: got error from OnTransportTimer...converting error code to E_PROXY_UDP_DISCONNECTED";
            LODWORD(v18) = v11;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v11,
              (unsigned int)byte_1801CD94B,
              v12,
              v13,
              (__int64)&v16,
              (__int64)&v18,
              (__int64)&v15);
          }
          CRdpUdpStream::ProcessDecoupledNetworkNotification((CRdpUdpStream *)((char *)this + 56), 1u, -2147001850, 0);
          break;
        }
      }
      else
      {
        CRdpUdpStream::ProcessDecoupledNetworkNotification((CRdpUdpStream *)((char *)this + 56), 4u, 0, 0);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v14 = 3552;
      v18 = "Failed to create gateway timer";
      v15 = v10;
      v19 = "GatewayWorkerThread";
      v20 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      v16 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v10,
        (unsigned int)&word_1801CEB86,
        v8,
        v9,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v20,
        (__int64)&v14,
        (__int64)&v19,
        (__int64)&v18);
    }
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v16 = "GatewayWorker: Exiting";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)&dword_1801CF824,
      0,
      v9,
      (__int64)&v16);
  }
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v17);
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
}

```

## disassembly

```asm
0x1801211f0  push    rbp
0x1801211f2  push    rbx
0x1801211f3  push    rsi
0x1801211f4  push    rdi
0x1801211f5  lea     rbp, [rsp-3Fh]
0x1801211fa  sub     rsp, 0B8h
0x180121201  mov     rax, cs:__security_cookie
0x180121208  xor     rax, rsp
0x18012120b  mov     [rbp+57h+var_28], rax
0x18012120f  movups  xmm0, xmmword ptr [rcx+274h]
0x180121216  mov     rbx, rcx
0x180121219  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18012121d  mov     ecx, 4; ControlCode
0x180121222  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180121227  call    cs:__imp_EventActivityIdControl
0x18012122d  mov     rcx, [rbx+68h]
0x180121231  mov     [rbp+57h+var_70], 0
0x180121239  mov     rax, [rcx]
0x18012123c  mov     rax, [rax+40h]
0x180121240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121245  xor     esi, esi
0x180121247  mov     rdi, rax
0x18012124a  test    rax, rax
0x18012124d  jz      short loc_180121268
0x18012124f  lea     rcx, [rbp+57h+var_70]; void *
0x180121253  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180121258  lea     rcx, [rbp+57h+var_70]
0x18012125c  mov     [rbp+57h+var_70], rdi
0x180121260  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180121265  mov     rsi, rdi
0x180121268  xor     r8d, r8d; lpTimerName
0x18012126b  xor     edx, edx; bManualReset
0x18012126d  xor     ecx, ecx; lpTimerAttributes
0x18012126f  call    cs:__imp_CreateWaitableTimerW
0x180121275  mov     rdi, rax
0x180121278  test    rax, rax
0x18012127b  jnz     loc_180121322
0x180121281  call    cs:__imp_GetLastError
0x180121287  mov     ecx, eax
0x180121289  test    eax, eax
0x18012128b  jle     short loc_180121296
0x18012128d  movzx   ecx, ax
0x180121290  or      ecx, 80070000h
0x180121296  mov     eax, cs:CallbackContext
0x18012129c  cmp     eax, 2
0x18012129f  jbe     loc_180121428
0x1801212a5  lea     rax, aFailedToCreate_104; "Failed to create gateway timer"
0x1801212ac  mov     [rbp+57h+var_80], 0DE0h
0x1801212b3  mov     [rbp+57h+var_68], rax
0x1801212b7  lea     rdx, word_1801CEB86
0x1801212be  lea     rax, aGatewayworkert; "GatewayWorkerThread"
0x1801212c5  mov     [rbp+57h+var_7C], ecx
0x1801212c8  mov     [rbp+57h+var_60], rax
0x1801212cc  lea     rax, aOnecoreTermsrv_17; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801212d3  mov     [rbp+57h+var_58], rax
0x1801212d7  lea     rax, aErrorCondition; "Error condition failed"
0x1801212de  mov     [rbp+57h+var_78], rax
0x1801212e2  lea     rax, [rbp+57h+var_68]
0x1801212e6  mov     [rsp+0D0h+var_88], rax
0x1801212eb  lea     rax, [rbp+57h+var_60]
0x1801212ef  mov     [rsp+0D0h+var_90], rax
0x1801212f4  lea     rax, [rbp+57h+var_80]
0x1801212f8  mov     [rsp+0D0h+var_98], rax
0x1801212fd  lea     rax, [rbp+57h+var_58]
0x180121301  mov     [rsp+0D0h+var_A0], rax
0x180121306  lea     rax, [rbp+57h+var_7C]
0x18012130a  mov     qword ptr [rsp+0D0h+fResume], rax
0x18012130f  lea     rax, [rbp+57h+var_78]
0x180121313  mov     [rsp+0D0h+lpArgToCompletionRoutine], rax
0x180121318  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18012131d  jmp     loc_180121428
0x180121322  xor     r9d, r9d; pfnCompletionRoutine
0x180121325  mov     [rsp+0D0h+fResume], 0; fResume
0x18012132d  lea     rdx, [rbp+57h+DueTime]; lpDueTime
0x180121331  mov     qword ptr [rbp+57h+DueTime], 0FFFFFFFFFFFCF2C0h
0x180121339  mov     rcx, rdi; hTimer
0x18012133c  mov     [rsp+0D0h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x180121345  lea     r8d, [r9+14h]; lPeriod
0x180121349  call    cs:__imp_SetWaitableTimer
0x18012134f  mov     rax, [rbx+1C0h]
0x180121356  mov     [rbp+57h+var_40], rax
0x18012135a  mov     [rbp+57h+var_48], rdi
0x18012135e  mov     [rbp+57h+var_80], 0
0x180121365  lea     rcx, [rbp+57h+var_80]
0x180121369  mov     rax, [rsi]
0x18012136c  lea     r8, [rbp+57h+var_48]
0x180121370  mov     qword ptr [rsp+0D0h+fResume], rcx
0x180121375  mov     r9d, 3
0x18012137b  mov     rcx, rsi
0x18012137e  mov     dword ptr [rsp+0D0h+lpArgToCompletionRoutine], 0FFFFFFFFh
0x180121386  mov     rax, [rax+50h]
0x18012138a  lea     edx, [r9-1]
0x18012138e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121393  test    eax, eax
0x180121395  js      loc_180121428
0x18012139b  mov     eax, [rbp+57h+var_80]
0x18012139e  test    eax, eax
0x1801213a0  jnz     loc_180121487
0x1801213a6  lea     rcx, [rbx+48h]; this
0x1801213aa  call    ?OnTransportTimer@CRdpUdpStream@@UEAAJXZ; CRdpUdpStream::OnTransportTimer(void)
0x1801213af  mov     ecx, eax
0x1801213b1  test    eax, eax
0x1801213b3  jnz     short loc_1801213C9
0x1801213b5  lea     rcx, [rbx+38h]; this
0x1801213b9  xor     r9d, r9d; struct IUnknown *
0x1801213bc  xor     r8d, r8d; int
0x1801213bf  lea     edx, [rax+4]; unsigned int
0x1801213c2  call    ?ProcessDecoupledNetworkNotification@CRdpUdpStream@@UEAAXKJPEAUIUnknown@@@Z; CRdpUdpStream::ProcessDecoupledNetworkNotification(ulong,long,IUnknown *)
0x1801213c7  jmp     short loc_18012135E
0x1801213c9  test    ecx, ecx
0x1801213cb  jns     short loc_18012135E
0x1801213cd  mov     eax, cs:CallbackContext
0x1801213d3  mov     edi, 80075A06h
0x1801213d8  cmp     eax, 4
0x1801213db  jbe     short loc_180121415
0x1801213dd  lea     rax, aGatewayworkerG; "GatewayWorker: got error from OnTranspo"...
0x1801213e4  mov     [rbp+57h+var_7C], edi
0x1801213e7  mov     [rbp+57h+var_78], rax
0x1801213eb  lea     rdx, byte_1801CD94B
0x1801213f2  lea     rax, [rbp+57h+var_7C]
0x1801213f6  mov     dword ptr [rbp+57h+var_68], ecx
0x1801213f9  mov     [rsp+0D0h+var_A0], rax
0x1801213fe  lea     rax, [rbp+57h+var_68]
0x180121402  mov     qword ptr [rsp+0D0h+fResume], rax
0x180121407  lea     rax, [rbp+57h+var_78]
0x18012140b  mov     [rsp+0D0h+lpArgToCompletionRoutine], rax
0x180121410  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180121415  xor     r9d, r9d; struct IUnknown *
0x180121418  lea     rcx, [rbx+38h]; this
0x18012141c  mov     r8d, edi; int
0x18012141f  lea     edx, [r9+1]; unsigned int
0x180121423  call    ?ProcessDecoupledNetworkNotification@CRdpUdpStream@@UEAAXKJPEAUIUnknown@@@Z; CRdpUdpStream::ProcessDecoupledNetworkNotification(ulong,long,IUnknown *)
0x180121428  mov     eax, cs:CallbackContext
0x18012142e  cmp     eax, 4
0x180121431  jbe     short loc_18012145D
0x180121433  lea     rax, aGatewayworkerE; "GatewayWorker: Exiting"
0x18012143a  xor     r8d, r8d
0x18012143d  mov     [rbp+57h+var_78], rax
0x180121441  lea     rdx, dword_1801CF824
0x180121448  lea     rax, [rbp+57h+var_78]
0x18012144c  lea     rcx, CallbackContext
0x180121453  mov     [rsp+0D0h+lpArgToCompletionRoutine], rax
0x180121458  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18012145d  lea     rcx, [rbp+57h+var_70]; void *
0x180121461  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180121466  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18012146a  call    ??1CAutoSetThreadActivityId@@QEAA@XZ; CAutoSetThreadActivityId::~CAutoSetThreadActivityId(void)
0x18012146f  mov     rcx, [rbp+57h+var_28]
0x180121473  xor     rcx, rsp; StackCookie
0x180121476  call    __security_check_cookie
0x18012147b  add     rsp, 0B8h
0x180121482  pop     rdi
0x180121483  pop     rsi
0x180121484  pop     rbx
0x180121485  pop     rbp
0x180121486  retn
0x180121487  cmp     eax, 1
0x18012148a  jnz     loc_18012135E
0x180121490  lea     rcx, [rbx+38h]; this
0x180121494  call    ?ProcessNetworkEvents@CRdpUdpStream@@UEAAHXZ; CRdpUdpStream::ProcessNetworkEvents(void)
0x180121499  jmp     loc_18012135E
```
