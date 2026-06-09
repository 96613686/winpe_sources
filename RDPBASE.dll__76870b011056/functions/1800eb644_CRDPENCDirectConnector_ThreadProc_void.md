# CRDPENCDirectConnector::ThreadProc(void)

- ea: `0x1800eb644`
- end: `0x1800ebe4f`
- name: `?ThreadProc@CRDPENCDirectConnector@@IEAAXXZ`
- size: `2059`
- prototype: `void __fastcall(CRDPENCDirectConnector *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800eb450`

## callees

- `0x1800018a4`
- `0x180004a94`
- `0x180019a80`
- `0x180019ab0`
- `0x18001b3f8`
- `0x180046a84`
- `0x1800711c8`
- `0x1800721d4`
- `0x1800787d4`
- `0x180078c20`
- `0x18007969c`
- `0x18007f094`
- `0x1800e7640`
- `0x1800e7c30`
- `0x1800ea318`
- `0x1800ea6c4`
- `0x1800ea768`
- `0x1800eaccc`
- `0x1800eaf4c`
- `0x1800eb644`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800eb6a0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800eb6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb6ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb9a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eba00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ebaa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb6ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb9a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eba00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ebaa7`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800ebb2a`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800ebb2a`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800eba9d`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800eba9d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eb6ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eb991`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eb6ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eb991`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800eb9f2`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x1800eb9f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebcde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ebcde`

## string_xrefs

- `0x1800eb83b`: `ThreadProc`
- `0x1800ebb10`: `ThreadProc`
- `0x1800ebca4`: `Failed to create a new connection`
- `0x1800ebdc4`: `Failed to complete the connection`

## pseudocode

```c
void __fastcall CRDPENCDirectConnector::ThreadProc(CRDPENCDirectConnector *this)
{
  GUID v2; // xmm0
  HANDLE WaitableTimer; // r13
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rdi
  HANDLE EventW; // rax
  signed int LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  int v12; // edx
  const char *v13; // rcx
  unsigned int started; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // edi
  char *v19; // rax
  char *v20; // r14
  char *v21; // r9
  unsigned int v22; // eax
  unsigned int v23; // edx
  unsigned int v24; // eax
  unsigned int v25; // r15d
  __int64 v26; // rcx
  HANDLE v27; // rax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  LONG v31; // r8d
  unsigned int v32; // edx
  __int64 v33; // rcx
  int v34; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // [rsp+50h] [rbp-59h] BYREF
  int v39; // [rsp+54h] [rbp-55h] BYREF
  unsigned int v40; // [rsp+58h] [rbp-51h]
  const char *v41; // [rsp+60h] [rbp-49h] BYREF
  __int64 v42; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int64 v43; // [rsp+70h] [rbp-39h] BYREF
  const char *v44; // [rsp+78h] [rbp-31h] BYREF
  LARGE_INTEGER DueTime; // [rsp+80h] [rbp-29h] BYREF
  const char *v46; // [rsp+88h] [rbp-21h] BYREF
  __int128 v47; // [rsp+90h] [rbp-19h] BYREF
  GUID ActivityId; // [rsp+A0h] [rbp-9h] BYREF

  v40 = 0;
  v47 = 0;
  v2 = *(GUID *)((char *)this + 244);
  DueTime.QuadPart = 0;
  WaitableTimer = 0;
  v43 = -1;
  ActivityId = v2;
  EventActivityIdControl(4u, &ActivityId);
  v4 = *((_QWORD *)this + 27);
  v5 = 0;
  v42 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
  if ( v6 )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v42);
    v5 = v6;
    v42 = v6;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v42);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 37) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 29;
LABEL_8:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      &WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
LABEL_9:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_83;
  }
  LastError = CRDPENCDirectConnector::AsyncResolveServerName(this);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 30;
    v13 = "Failed to resolve server name asynchronously";
    goto LABEL_82;
  }
  LastError = CRDPENCONResolver::SortAddresses((CRDPENCDirectConnector *)((char *)this + 56));
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 31;
    v13 = "Failed to sort the address list";
    goto LABEL_82;
  }
  started = CRDPENCONResolver::StartEnum((CRDPENCDirectConnector *)((char *)this + 56));
  v18 = started;
  if ( started )
  {
    v19 = (char *)operator new(saturated_mul(started, 8u));
    v20 = (char *)this + 304;
    v21 = v19;
    *((_QWORD *)this + 38) = v19;
    if ( v19 )
    {
      if ( v18 )
      {
        v23 = 0;
        if ( v18 < 2 || v19 <= v20 && &v19[8 * v18 - 8] >= v20 )
          goto LABEL_109;
        v24 = v18 & 0xFFFFFFFE;
        do
        {
          v23 += 2;
          v25 = v23;
        }
        while ( v23 < v24 );
        memset_0(v21, -1, 16 * ((unsigned __int64)v24 >> 1));
        v23 = v25;
        if ( v25 < v18 )
        {
LABEL_109:
          do
          {
            v26 = v23++;
            *(_QWORD *)(*(_QWORD *)v20 + 8 * v26) = -1;
          }
          while ( v23 < v18 );
        }
      }
      *((_DWORD *)this + 78) = v18;
      *((_DWORD *)this + 79) = 0;
      v27 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 36) = v27;
      if ( !v27 )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_9;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 33;
        goto LABEL_8;
      }
      WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
      if ( !WaitableTimer )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_9;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 34;
        goto LABEL_8;
      }
      if ( (unsigned int)CallbackContext > 5 )
      {
        v38 = *((_DWORD *)this + 65);
        v41 = "Trying to connection using Conn Q Interval: %d";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v28,
          (unsigned int)byte_1801BEF49,
          v29,
          v30,
          (__int64)&v41,
          (__int64)&v38);
      }
      v31 = *((_DWORD *)this + 65);
      DueTime.QuadPart = 0;
      if ( !SetWaitableTimer(WaitableTimer, &DueTime, v31, 0, 0, 0) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_9;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 35;
        goto LABEL_8;
      }
      *((_QWORD *)&v47 + 1) = *((_QWORD *)this + 36);
      *(_QWORD *)&v47 = WaitableTimer;
      LastError = CRDPENCDirectConnector::CreatePendingConnection(this);
      if ( LastError < 0 )
      {
LABEL_78:
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_83;
        }
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 36;
        v13 = "Failed to create a new connection";
LABEL_82:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          (unsigned int)&WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
          v11,
          (__int64)v13,
          LastError);
        goto LABEL_83;
      }
      while ( 1 )
      {
        if ( LastError == 1 )
        {
          CancelWaitableTimer(WaitableTimer);
          v32 = *((_DWORD *)this + 79);
          if ( !v32 )
          {
LABEL_65:
            LastError = CRDPENCDirectConnector::FireConnectionCompleted(this, 0xFFFFFFFFFFFFFFFFuLL);
            if ( LastError < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v11 = RdpWppGetCurrentThreadActivityIdPrefix();
              v12 = 37;
LABEL_70:
              v13 = "Failed to fire the event";
              goto LABEL_82;
            }
            goto LABEL_83;
          }
          v33 = 0;
          while ( *(_QWORD *)(*((_QWORD *)this + 38) + 8 * v33) == -1 )
          {
            v33 = (unsigned int)(v33 + 1);
            if ( (unsigned int)v33 >= v32 )
              goto LABEL_65;
          }
        }
        LastError = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v5 + 80LL))(v5, 2, &v47);
        if ( LastError < 0 )
          break;
        if ( v40 > 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids);
          }
          LastError = -2147418113;
          goto LABEL_83;
        }
        v34 = CRDPENCDirectConnector::CompletePendingConnection(this, &v43);
        LastError = v34;
        if ( v34 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = RdpWppGetCurrentThreadActivityIdPrefix();
            v12 = 39;
            v13 = "Failed to complete the connection";
            goto LABEL_82;
          }
          goto LABEL_83;
        }
        if ( !v34 )
        {
          LastError = CRDPENCDirectConnector::FireConnectionCompleted(this, v43);
          if ( LastError < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = RdpWppGetCurrentThreadActivityIdPrefix();
            v12 = 40;
            goto LABEL_70;
          }
          goto LABEL_83;
        }
        if ( (unsigned int)CallbackContext > 2 )
        {
          v41 = "ThreadProc";
          v46 = "Trying the next connector";
          v38 = 623;
          v44 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
          v39 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v35,
            (unsigned int)&dword_1801BEF04,
            v36,
            v37,
            (__int64)&v46,
            (__int64)&v39,
            (__int64)&v44,
            (__int64)&v38,
            (__int64)&v41);
        }
        LastError = CRDPENCDirectConnector::CreatePendingConnection(this);
        if ( LastError < 0 )
          goto LABEL_78;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 38;
        v13 = "Wait failed";
        goto LABEL_82;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          &WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
          v22,
          -2147024882);
      }
      LastError = -2147024882;
    }
  }
  else
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v39 = 523;
      v41 = "Failed to resolve any IPS";
      v43 = (unsigned __int64)"ThreadProc";
      v44 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
      v38 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v15,
        (unsigned int)byte_1801BEF7D,
        v16,
        v17,
        (__int64)&v41,
        (__int64)&v38,
        (__int64)&v44,
        (__int64)&v39,
        (__int64)&v43);
    }
    LastError = -2092621306;
  }
LABEL_83:
  CRDPENCDirectConnector::ClearPendingConnections(this);
  if ( WaitableTimer )
    CloseHandle(WaitableTimer);
  if ( (int)(LastError + 0x80000000) >= 0 && LastError != -2092629996 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 29) + 32LL))(
      *((_QWORD *)this + 29),
      (unsigned int)LastError);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v42);
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
}

```

## disassembly

```asm
0x1800eb644  push    rbp
0x1800eb646  push    rbx
0x1800eb647  push    rsi
0x1800eb648  push    rdi
0x1800eb649  push    r12
0x1800eb64b  push    r13
0x1800eb64d  push    r14
0x1800eb64f  push    r15
0x1800eb651  lea     rbp, [rsp-1Fh]
0x1800eb656  sub     rsp, 0C8h
0x1800eb65d  mov     rax, cs:__security_cookie
0x1800eb664  xor     rax, rsp
0x1800eb667  mov     [rbp+57h+var_50], rax
0x1800eb66b  xor     r12d, r12d
0x1800eb66e  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1800eb672  xorps   xmm0, xmm0
0x1800eb675  mov     [rbp+57h+var_A8], r12d
0x1800eb679  movups  [rbp+57h+var_70], xmm0
0x1800eb67d  mov     rsi, rcx
0x1800eb680  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800eb684  movups  xmm0, xmmword ptr [rcx+0F4h]
0x1800eb68b  lea     ecx, [r12+4]; ControlCode
0x1800eb690  mov     qword ptr [rbp+57h+DueTime], r12
0x1800eb694  mov     r13d, r12d
0x1800eb697  mov     [rbp+57h+var_90], r15
0x1800eb69b  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1800eb6a0  call    cs:__imp_EventActivityIdControl
0x1800eb6a6  mov     rcx, [rsi+0D8h]
0x1800eb6ad  mov     ebx, r12d
0x1800eb6b0  mov     [rbp+57h+var_98], rbx
0x1800eb6b4  mov     rax, [rcx]
0x1800eb6b7  mov     rax, [rax+40h]
0x1800eb6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb6c0  mov     rdi, rax
0x1800eb6c3  test    rax, rax
0x1800eb6c6  jz      short loc_1800EB6E1
0x1800eb6c8  lea     rcx, [rbp+57h+var_98]; void *
0x1800eb6cc  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800eb6d1  mov     rbx, rdi
0x1800eb6d4  lea     rcx, [rbp+57h+var_98]
0x1800eb6d8  mov     [rbp+57h+var_98], rbx
0x1800eb6dc  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800eb6e1  xor     r9d, r9d; lpName
0x1800eb6e4  xor     r8d, r8d; bInitialState
0x1800eb6e7  xor     ecx, ecx; lpEventAttributes
0x1800eb6e9  lea     edx, [r9+1]; bManualReset
0x1800eb6ed  call    cs:__imp_CreateEventW
0x1800eb6f3  mov     [rsi+128h], rax
0x1800eb6fa  test    rax, rax
0x1800eb6fd  jnz     short loc_1800EB76C
0x1800eb6ff  call    cs:__imp_GetLastError
0x1800eb705  mov     edi, eax
0x1800eb707  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb70e  lea     rax, WPP_GLOBAL_Control
0x1800eb715  cmp     rcx, rax
0x1800eb718  jz      short loc_1800EB74E
0x1800eb71a  test    byte ptr [rcx+1Ch], 8
0x1800eb71e  jz      short loc_1800EB74E
0x1800eb720  cmp     byte ptr [rcx+19h], 2
0x1800eb724  jb      short loc_1800EB74E
0x1800eb726  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800eb72b  mov     edx, 1Dh
0x1800eb730  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb737  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1800eb73e  mov     r9d, eax
0x1800eb741  mov     dword ptr [rsp+100h+lpArgToCompletionRoutine], edi
0x1800eb745  mov     rcx, [rcx+10h]
0x1800eb749  call    WPP_SF_Dd
0x1800eb74e  test    edi, edi
0x1800eb750  jle     short loc_1800EB75B
0x1800eb752  movzx   edi, di
0x1800eb755  or      edi, 80070000h
0x1800eb75b  test    edi, edi
0x1800eb75d  mov     r14d, 80004005h
0x1800eb763  cmovns  edi, r14d
0x1800eb767  jmp     loc_1800EBCCE
0x1800eb76c  mov     rcx, rsi; this
0x1800eb76f  call    ?AsyncResolveServerName@CRDPENCDirectConnector@@IEAAJXZ; CRDPENCDirectConnector::AsyncResolveServerName(void)
0x1800eb774  mov     edi, eax
0x1800eb776  test    eax, eax
0x1800eb778  jns     short loc_1800EB7BB
0x1800eb77a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb781  lea     rax, WPP_GLOBAL_Control
0x1800eb788  cmp     rcx, rax
0x1800eb78b  jz      loc_1800EBCCE
0x1800eb791  test    byte ptr [rcx+1Ch], 8
0x1800eb795  jz      loc_1800EBCCE
0x1800eb79b  cmp     byte ptr [rcx+19h], 2
0x1800eb79f  jb      loc_1800EBCCE
0x1800eb7a5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800eb7aa  mov     edx, 1Eh
0x1800eb7af  lea     rcx, aFailedToResolv; "Failed to resolve server name asynchron"...
0x1800eb7b6  jmp     loc_1800EBCAB
0x1800eb7bb  lea     rcx, [rsi+38h]; this
0x1800eb7bf  call    ?SortAddresses@CRDPENCONResolver@@QEAAJXZ; CRDPENCONResolver::SortAddresses(void)
0x1800eb7c4  mov     edi, eax
0x1800eb7c6  test    eax, eax
0x1800eb7c8  jns     short loc_1800EB80B
0x1800eb7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb7d1  lea     rax, WPP_GLOBAL_Control
0x1800eb7d8  cmp     rcx, rax
0x1800eb7db  jz      loc_1800EBCCE
0x1800eb7e1  test    byte ptr [rcx+1Ch], 8
0x1800eb7e5  jz      loc_1800EBCCE
0x1800eb7eb  cmp     byte ptr [rcx+19h], 2
0x1800eb7ef  jb      loc_1800EBCCE
0x1800eb7f5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800eb7fa  mov     edx, 1Fh
0x1800eb7ff  lea     rcx, aFailedToSortTh; "Failed to sort the address list"
0x1800eb806  jmp     loc_1800EBCAB
0x1800eb80b  lea     rcx, [rsi+38h]; this
0x1800eb80f  call    ?StartEnum@CRDPENCONResolver@@QEAAIXZ; CRDPENCONResolver::StartEnum(void)
0x1800eb814  mov     edi, eax
0x1800eb816  test    eax, eax
0x1800eb818  jnz     loc_1800EB89E
0x1800eb81e  mov     eax, cs:CallbackContext
0x1800eb824  cmp     eax, 2
0x1800eb827  jbe     short loc_1800EB894
0x1800eb829  lea     rax, aFailedToResolv_0; "Failed to resolve any IPS"
0x1800eb830  mov     [rbp+57h+var_AC], 20Bh
0x1800eb837  mov     [rbp+57h+var_A0], rax
0x1800eb83b  lea     r15, aThreadproc; "ThreadProc"
0x1800eb842  lea     rax, [rbp+57h+var_90]
0x1800eb846  mov     [rbp+57h+var_90], r15
0x1800eb84a  mov     [rsp+100h+var_C0], rax
0x1800eb84f  lea     r12, aOnecoreTermsrv_46; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800eb856  lea     rax, [rbp+57h+var_AC]
0x1800eb85a  mov     [rbp+57h+var_88], r12
0x1800eb85e  mov     [rsp+100h+var_C8], rax
0x1800eb863  lea     rdx, byte_1801BEF7D
0x1800eb86a  lea     rax, [rbp+57h+var_88]
0x1800eb86e  mov     r14d, 80004005h
0x1800eb874  mov     [rsp+100h+var_D0], rax
0x1800eb879  lea     rax, [rbp+57h+var_B0]
0x1800eb87d  mov     qword ptr [rsp+100h+fResume], rax
0x1800eb882  lea     rax, [rbp+57h+var_A0]
0x1800eb886  mov     [rsp+100h+lpArgToCompletionRoutine], rax
0x1800eb88b  mov     [rbp+57h+var_B0], r14d
0x1800eb88f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800eb894  mov     edi, 83452206h
0x1800eb899  jmp     loc_1800EBCCE
0x1800eb89e  mov     eax, 8
0x1800eb8a3  mul     rdi
0x1800eb8a6  cmovb   rax, r15
0x1800eb8aa  mov     rcx, rax; Size
0x1800eb8ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eb8b2  lea     r14, [rsi+130h]
0x1800eb8b9  mov     r9, rax
0x1800eb8bc  mov     [r14], rax
0x1800eb8bf  test    rax, rax
0x1800eb8c2  jnz     short loc_1800EB919
0x1800eb8c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb8cb  lea     rax, WPP_GLOBAL_Control
0x1800eb8d2  cmp     rcx, rax
0x1800eb8d5  jz      short loc_1800EB90F
0x1800eb8d7  test    byte ptr [rcx+1Ch], 8
0x1800eb8db  jz      short loc_1800EB90F
0x1800eb8dd  cmp     byte ptr [rcx+19h], 2
0x1800eb8e1  jb      short loc_1800EB90F
0x1800eb8e3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800eb8e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb8ef  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1800eb8f6  mov     edx, 20h ; ' '
0x1800eb8fb  mov     dword ptr [rsp+100h+lpArgToCompletionRoutine], 8007000Eh
0x1800eb903  mov     r9d, eax
0x1800eb906  mov     rcx, [rcx+10h]
0x1800eb90a  call    WPP_SF_Dd
0x1800eb90f  mov     edi, 8007000Eh
0x1800eb914  jmp     loc_1800EBCCE
0x1800eb919  test    edi, edi
0x1800eb91b  jz      short loc_1800EB97A
0x1800eb91d  mov     edx, r12d
0x1800eb920  cmp     edi, 2
0x1800eb923  jb      short loc_1800EB96B
0x1800eb925  cmp     r9, r14
0x1800eb928  ja      short loc_1800EB936
0x1800eb92a  lea     eax, [rdi-1]
0x1800eb92d  lea     rax, [r9+rax*8]
0x1800eb931  cmp     rax, r14
0x1800eb934  jnb     short loc_1800EB96B
0x1800eb936  mov     eax, edi
0x1800eb938  and     eax, 0FFFFFFFEh
0x1800eb93b  add     edx, 2
0x1800eb93e  mov     r15d, edx
0x1800eb941  cmp     edx, eax
0x1800eb943  jb      short loc_1800EB93B
0x1800eb945  mov     r8d, eax
0x1800eb948  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x1800eb94c  shr     r8, 1
0x1800eb94f  mov     rcx, r9; void *
0x1800eb952  shl     r8, 4
0x1800eb956  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x1800eb95a  call    memset_0
0x1800eb95f  mov     edx, r15d
0x1800eb962  cmp     r15d, edi
0x1800eb965  jnb     short loc_1800EB97A
0x1800eb967  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800eb96b  mov     rax, [r14]
0x1800eb96e  mov     ecx, edx
0x1800eb970  inc     edx
0x1800eb972  mov     [rax+rcx*8], r15
0x1800eb976  cmp     edx, edi
0x1800eb978  jb      short loc_1800EB96B
0x1800eb97a  xor     r9d, r9d; lpName
0x1800eb97d  mov     [rsi+138h], edi
0x1800eb983  xor     r8d, r8d; bInitialState
0x1800eb986  mov     [rsi+13Ch], r12d
0x1800eb98d  xor     edx, edx; bManualReset
0x1800eb98f  xor     ecx, ecx; lpEventAttributes
0x1800eb991  call    cs:__imp_CreateEventW
0x1800eb997  mov     [rsi+120h], rax
0x1800eb99e  test    rax, rax
0x1800eb9a1  jnz     short loc_1800EB9E5
0x1800eb9a3  call    cs:__imp_GetLastError
0x1800eb9a9  mov     edi, eax
0x1800eb9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eb9b2  lea     rax, WPP_GLOBAL_Control
0x1800eb9b9  cmp     rcx, rax
0x1800eb9bc  jz      loc_1800EB74E
0x1800eb9c2  test    byte ptr [rcx+1Ch], 8
0x1800eb9c6  jz      loc_1800EB74E
0x1800eb9cc  cmp     byte ptr [rcx+19h], 2
0x1800eb9d0  jb      loc_1800EB74E
0x1800eb9d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800eb9db  mov     edx, 21h ; '!'
0x1800eb9e0  jmp     loc_1800EB730
0x1800eb9e5  mov     r9d, 1F0003h; dwDesiredAccess
0x1800eb9eb  xor     r8d, r8d; dwFlags
0x1800eb9ee  xor     edx, edx; lpTimerName
0x1800eb9f0  xor     ecx, ecx; lpTimerAttributes
0x1800eb9f2  call    cs:__imp_CreateWaitableTimerExW
0x1800eb9f8  mov     r13, rax
0x1800eb9fb  test    rax, rax
0x1800eb9fe  jnz     short loc_1800EBA41
0x1800eba00  call    cs:__imp_GetLastError
0x1800eba06  mov     edi, eax
0x1800eba08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eba0f  lea     rax, WPP_GLOBAL_Control
0x1800eba16  cmp     rcx, rax
0x1800eba19  jz      loc_1800EB74E
0x1800eba1f  test    byte ptr [rcx+1Ch], 8
0x1800eba23  jz      loc_1800EB74E
0x1800eba29  cmp     byte ptr [rcx+19h], 2
0x1800eba2d  jb      loc_1800EB74E
0x1800eba33  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800eba38  lea     edx, [r13+22h]
0x1800eba3c  jmp     loc_1800EB730
0x1800eba41  mov     eax, cs:CallbackContext
0x1800eba47  cmp     eax, 5
0x1800eba4a  jbe     short loc_1800EBA7E
0x1800eba4c  mov     eax, [rsi+104h]
0x1800eba52  lea     rdx, byte_1801BEF49
0x1800eba59  mov     [rbp+57h+var_B0], eax
0x1800eba5c  lea     rax, aTryingToConnec; "Trying to connection using Conn Q Inter"...
0x1800eba63  mov     [rbp+57h+var_A0], rax
0x1800eba67  lea     rax, [rbp+57h+var_B0]
0x1800eba6b  mov     qword ptr [rsp+100h+fResume], rax
0x1800eba70  lea     rax, [rbp+57h+var_A0]
0x1800eba74  mov     [rsp+100h+lpArgToCompletionRoutine], rax
0x1800eba79  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800eba7e  mov     r8d, [rsi+104h]; lPeriod
0x1800eba85  lea     rdx, [rbp+57h+DueTime]; lpDueTime
0x1800eba89  mov     [rsp+100h+fResume], r12d; fResume
0x1800eba8e  xor     r9d, r9d; pfnCompletionRoutine
0x1800eba91  mov     rcx, r13; hTimer
0x1800eba94  mov     [rsp+100h+lpArgToCompletionRoutine], r12; lpArgToCompletionRoutine
0x1800eba99  mov     qword ptr [rbp+57h+DueTime], r12
0x1800eba9d  call    cs:__imp_SetWaitableTimer
0x1800ebaa3  test    eax, eax
0x1800ebaa5  jnz     short loc_1800EBAE9
0x1800ebaa7  call    cs:__imp_GetLastError
0x1800ebaad  mov     edi, eax
0x1800ebaaf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ebab6  lea     rax, WPP_GLOBAL_Control
0x1800ebabd  cmp     rcx, rax
0x1800ebac0  jz      loc_1800EB74E
0x1800ebac6  test    byte ptr [rcx+1Ch], 8
0x1800ebaca  jz      loc_1800EB74E
0x1800ebad0  cmp     byte ptr [rcx+19h], 2
0x1800ebad4  jb      loc_1800EB74E
0x1800ebada  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ebadf  mov     edx, 23h ; '#'
0x1800ebae4  jmp     loc_1800EB730
0x1800ebae9  mov     rax, [rsi+120h]
0x1800ebaf0  mov     rcx, rsi; this
0x1800ebaf3  mov     qword ptr [rbp+57h+var_70+8], rax
0x1800ebaf7  mov     qword ptr [rbp+57h+var_70], r13
0x1800ebafb  call    ?CreatePendingConnection@CRDPENCDirectConnector@@IEAAJXZ; CRDPENCDirectConnector::CreatePendingConnection(void)
0x1800ebb00  mov     edi, eax
0x1800ebb02  test    eax, eax
0x1800ebb04  js      loc_1800EBC7B
0x1800ebb0a  mov     r14d, 80004005h
0x1800ebb10  lea     r15, aThreadproc; "ThreadProc"
0x1800ebb17  lea     r12, aOnecoreTermsrv_46; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800ebb1e  cmp     edi, 1
0x1800ebb21  jnz     loc_1800EBBA7
0x1800ebb27  mov     rcx, r13; hTimer
0x1800ebb2a  call    cs:__imp_CancelWaitableTimer
0x1800ebb30  mov     edx, [rsi+13Ch]
0x1800ebb36  test    edx, edx
  ... truncated ...
```
