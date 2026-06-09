# CRdpUdpLocalEndpoint::SendFromPendingQueue(void)

- ea: `0x18006b49c`
- end: `0x18006ba51`
- name: `?SendFromPendingQueue@CRdpUdpLocalEndpoint@@IEAAJXZ`
- size: `1461`
- prototype: `__int64 __fastcall(CRdpUdpLocalEndpoint *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x18006bbc4`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180002550`
- `0x180004da8`
- `0x180016ad0`
- `0x180016b00`
- `0x18001b3f8`
- `0x18001cc3c`
- `0x18003bc00`
- `0x18004298c`
- `0x1800484f0`
- `0x18006b49c`
- `0x18006bcf8`
- `0x180078c20`
- `0x180133920`
- `0x180133b80`
- `0x180133c80`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006b4cf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006b5bd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006b4cf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006b5bd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006b7cd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18006b7cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b801`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b7df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b7df`

## string_xrefs

- `0x18006b81d`: `Failed to create deffered connection release thread`
- `0x18006b739`: `Failed to allocate DeferredConnectionReleaseThreadContext`

## pseudocode

```c
__int64 __fastcall CRdpUdpLocalEndpoint::SendFromPendingQueue(CRdpUdpLocalEndpoint *this)
{
  int DataToSend; // esi
  __int64 *v3; // rbx
  int v4; // eax
  __int64 *v5; // r15
  __int64 *v6; // rdx
  __int64 *v7; // rax
  __int64 v8; // rcx
  CRdpUdpConnection *v9; // r13
  __int64 *v10; // r14
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  __int64 v14; // rax
  int v15; // ecx
  int v16; // r8d
  HANDLE Thread; // rax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  signed int LastError; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rcx
  const struct sockaddr_storage *RemoteSockAddr; // rax
  __int64 v27; // r11
  __int64 v28; // r8
  __int64 v29; // r10
  int v30; // r9d
  __int64 *v31; // rcx
  __int64 v32; // rax
  __int64 *v33; // rbx
  __int64 *v34; // rax
  __int64 **v35; // rbx
  int v37; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v38; // [rsp+54h] [rbp-65h] BYREF
  __int64 *v39; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int64 v40; // [rsp+60h] [rbp-59h] BYREF
  LPVOID lpParameter; // [rsp+68h] [rbp-51h] BYREF
  const char *v42; // [rsp+70h] [rbp-49h] BYREF
  const char *v43; // [rsp+78h] [rbp-41h] BYREF
  const char *v44; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int8 *v45; // [rsp+88h] [rbp-31h] BYREF
  DWORD ThreadId[2]; // [rsp+90h] [rbp-29h] BYREF
  const char *v47; // [rsp+98h] [rbp-21h] BYREF
  _QWORD v48[2]; // [rsp+A0h] [rbp-19h] BYREF
  int v49; // [rsp+B0h] [rbp-9h]
  int v50; // [rsp+B4h] [rbp-5h]
  GUID ActivityId; // [rsp+B8h] [rbp-1h] BYREF

  DataToSend = 0;
  EventActivityIdControl(1u, &ActivityId);
  v3 = 0;
  v39 = 0;
  TCntPtr<CRdpUdpConnection>::SafeAddRef(&v39);
  v45 = 0;
  v40 = 0;
  CTSCriticalSection::Lock((CRdpUdpLocalEndpoint *)((char *)this + 464));
  if ( *((_DWORD *)this + 120) == 1 )
  {
    CTSCriticalSection::UnLock((CRdpUdpLocalEndpoint *)((char *)this + 464));
  }
  else if ( *((CRdpUdpLocalEndpoint **)this + 66) == (CRdpUdpLocalEndpoint *)((char *)this + 528) )
  {
    CTSCriticalSection::UnLock((CRdpUdpLocalEndpoint *)((char *)this + 464));
    DataToSend = -2147483638;
  }
  else
  {
    v4 = *((_DWORD *)this + 130);
    v5 = 0;
    if ( !v4
      || (v6 = (__int64 *)*((_QWORD *)this + 66),
          *((_DWORD *)this + 130) = v4 - 1,
          v7 = (__int64 *)v6[1],
          v5 = v6 - 8,
          v8 = *v6,
          *v7 = *v6,
          *(_QWORD *)(v8 + 8) = v7,
          v6 == (__int64 *)64) )
    {
      v9 = 0;
      v10 = 0;
    }
    else
    {
      TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v39);
      v3 = v5;
      v39 = v5;
      TCntPtr<CRdpUdpConnection>::SafeAddRef(&v39);
      v9 = (CRdpUdpConnection *)v5;
      v10 = v5;
    }
    v38 = *((_DWORD *)v10 + 60);
    v40 = v10[32];
    v45 = (unsigned __int8 *)v10[31];
    CTSCriticalSection::UnLock((CRdpUdpLocalEndpoint *)((char *)this + 464));
    EventActivityIdControl(2u, (LPGUID)(v5 + 881));
    if ( !v40 )
      DataToSend = CRdpUdpConnection::GetDataToSend((CRdpUdpConnection *)v3, &v45, &v40);
    v13 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext > 5 )
    {
      *(_QWORD *)ThreadId = "UDP Send Connection";
      v37 = v40;
      lpParameter = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v40,
        (unsigned int)&word_1801D4DE6,
        v11,
        v12,
        (__int64)ThreadId,
        (__int64)&lpParameter,
        (__int64)&v37);
    }
    if ( DataToSend == 1 )
    {
      if ( (unsigned int)CRdpUdpLocalEndpoint::RemoveConnectionFromPendingList(
                           this,
                           (struct CRdpUdpConnection *)v3,
                           v38) == 1 )
      {
        TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v39);
        v3 = 0;
        v39 = 0;
        TCntPtr<CRdpUdpConnection>::SafeAddRef(&v39);
        v40 = 0;
      }
    }
    else if ( DataToSend >= 0 )
    {
      if ( v40 )
      {
        RemoteSockAddr = CRdpUdpConnection::GetRemoteSockAddr(v9);
        DataToSend = (*(__int64 (__fastcall **)(CRdpUdpLocalEndpoint *, unsigned __int8 *, __int64, const struct sockaddr_storage *, __int64))(v27 + 152))(
                       this,
                       v45,
                       v28,
                       RemoteSockAddr,
                       v29);
        if ( DataToSend == -2147483638 )
        {
          v10[32] = v40;
          v10[31] = (__int64)v45;
          if ( (unsigned int)CallbackContext > 5 )
          {
            v43 = "UDP Send Failed: returned WSAEWOULDBLOCK";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              (unsigned int)&CallbackContext,
              (unsigned int)&byte_1801D51B7,
              0,
              v30,
              (__int64)&v43);
          }
        }
        else
        {
          v10[32] = 0;
          v10[31] = 0;
        }
      }
    }
    else
    {
      ThreadId[0] = 0;
      if ( (unsigned int)CallbackContext > 2 )
      {
        lpParameter = "SendFromPendingQueue";
        v42 = "RdpUdpLocalEndpoint::SendFromPendingQueue failed to get data to send from connection. Closing the connection.";
        v38 = 1625;
        v47 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
        v37 = DataToSend;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v13,
          (unsigned int)&byte_1801D4E67,
          v11,
          v12,
          (__int64)&v42,
          (__int64)&v37,
          (__int64)&v47,
          (__int64)&v38,
          (__int64)&lpParameter);
      }
      v48[0] = v3;
      TCntPtr<CRdpUdpConnection>::SafeAddRef(v48);
      v14 = *(_QWORD *)this;
      v48[1] = this;
      (*(void (__fastcall **)(CRdpUdpLocalEndpoint *))(v14 + 8))(this);
      v49 = DataToSend;
      v50 = 0;
      utl::make_unique<DeferredConnectionReleaseThreadContext,DeferredConnectionReleaseThreadContext,0>(
        &lpParameter,
        v48);
      DeferredConnectionReleaseThreadContext::~DeferredConnectionReleaseThreadContext((DeferredConnectionReleaseThreadContext *)v48);
      if ( lpParameter )
      {
        Thread = CreateThread(
                   0,
                   0,
                   CRdpUdpLocalEndpoint::STATIC_DeferredConnectionReleaseThread,
                   lpParameter,
                   0x60u,
                   ThreadId);
        if ( Thread )
        {
          lpParameter = 0;
          CloseHandle(Thread);
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          v43 = "SendFromPendingQueue";
          v38 = 1651;
          v44 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v37 = LastError;
          v42 = "Failed to create deffered connection release thread";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v22,
            (unsigned int)&word_1801D4BF6,
            v23,
            v24,
            (__int64)&v42,
            (__int64)&v37,
            (__int64)&v44,
            (__int64)&v38,
            (__int64)&v43);
        }
        v40 = 0;
        if ( DataToSend == -2147221500 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v43 = "SendFromPendingQueue";
            v44 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
            v38 = 1663;
            v42 = "RdpUdpLocalEndpoint::SendFromPendingQueue Handshake timed out with RDPUDP_E_HANDSHAKE_TIMED_OUT_FINAL."
                  " Raising OnConnectorError!";
            v37 = -2147221500;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v18,
              (unsigned int)byte_1801D57AD,
              v19,
              v20,
              (__int64)&v42,
              (__int64)&v37,
              (__int64)&v44,
              (__int64)&v38,
              (__int64)&v43);
          }
          v25 = *((_QWORD *)this + 68);
          if ( v25 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 32LL))(v25, 2147745796LL);
        }
      }
      else
      {
        DataToSend = -2147024882;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v47 = "SendFromPendingQueue";
          v42 = "Failed to allocate DeferredConnectionReleaseThreadContext";
          v38 = 1634;
          v43 = "Error condition failed";
          v44 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
          v37 = -2147024882;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v15,
            (unsigned int)&byte_1801D471F,
            v16,
            0,
            (__int64)&v43,
            (__int64)&v37,
            (__int64)&v44,
            (__int64)&v38,
            (__int64)&v47,
            (__int64)&v42);
        }
      }
      utl::unique_ptr<DeferredConnectionReleaseThreadContext,utl::default_delete<DeferredConnectionReleaseThreadContext>>::~unique_ptr<DeferredConnectionReleaseThreadContext,utl::default_delete<DeferredConnectionReleaseThreadContext>>(&lpParameter);
    }
    if ( v3 )
    {
      CTSCriticalSection::Lock((CRdpUdpLocalEndpoint *)((char *)this + 464));
      if ( *((_DWORD *)v3 + 61) == 1 )
      {
        v31 = (__int64 *)((char *)this + 528);
        if ( v3[32] )
        {
          v32 = *v31;
          v33 = v3 + 8;
          *v33 = *v31;
          v33[1] = (__int64)v31;
          *(_QWORD *)(v32 + 8) = v33;
          *v31 = (__int64)v33;
        }
        else
        {
          v34 = (__int64 *)*((_QWORD *)this + 67);
          v35 = (__int64 **)(v3 + 8);
          *v35 = v31;
          v35[1] = v34;
          *v34 = (__int64)v35;
          *((_QWORD *)this + 67) = v35;
        }
        ++*((_DWORD *)this + 130);
      }
      CTSCriticalSection::UnLock((CRdpUdpLocalEndpoint *)((char *)this + 464));
      TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v39);
      v39 = 0;
      TCntPtr<CRdpUdpConnection>::SafeAddRef(&v39);
    }
  }
  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v39);
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  return (unsigned int)DataToSend;
}

```

## disassembly

```asm
0x18006b49c  push    rbp
0x18006b49e  push    rbx
0x18006b49f  push    rsi
0x18006b4a0  push    rdi
0x18006b4a1  push    r12
0x18006b4a3  push    r13
0x18006b4a5  push    r14
0x18006b4a7  push    r15
0x18006b4a9  lea     rbp, [rsp-1Fh]
0x18006b4ae  sub     rsp, 0D8h
0x18006b4b5  mov     rax, cs:__security_cookie
0x18006b4bc  xor     rax, rsp
0x18006b4bf  mov     [rbp+57h+var_48], rax
0x18006b4c3  mov     rdi, rcx
0x18006b4c6  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18006b4ca  xor     esi, esi
0x18006b4cc  lea     ecx, [rsi+1]; ControlCode
0x18006b4cf  call    cs:__imp_EventActivityIdControl
0x18006b4d5  xor     ebx, ebx
0x18006b4d7  lea     rcx, [rbp+57h+var_B8]
0x18006b4db  mov     [rbp+57h+var_B8], rbx
0x18006b4df  call    ?SafeAddRef@?$TCntPtr@VCRdpUdpConnection@@@@AEAAXXZ; TCntPtr<CRdpUdpConnection>::SafeAddRef(void)
0x18006b4e4  lea     r12, [rdi+1D0h]
0x18006b4eb  mov     [rbp+57h+var_88], rbx
0x18006b4ef  mov     rcx, r12; this
0x18006b4f2  mov     [rbp+57h+var_B0], rbx
0x18006b4f6  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18006b4fb  cmp     dword ptr [rdi+1E0h], 1
0x18006b502  jnz     short loc_18006B511
0x18006b504  mov     rcx, r12; this
0x18006b507  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18006b50c  jmp     loc_18006BA1D
0x18006b511  lea     rax, [rdi+210h]
0x18006b518  cmp     [rax], rax
0x18006b51b  jnz     short loc_18006B52F
0x18006b51d  mov     rcx, r12; this
0x18006b520  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18006b525  mov     esi, 8000000Ah
0x18006b52a  jmp     loc_18006BA1D
0x18006b52f  mov     eax, [rdi+208h]
0x18006b535  xor     r15d, r15d
0x18006b538  test    eax, eax
0x18006b53a  jz      short loc_18006B583
0x18006b53c  mov     rdx, [rdi+210h]
0x18006b543  dec     eax
0x18006b545  mov     [rdi+208h], eax
0x18006b54b  mov     rax, [rdx+8]
0x18006b54f  lea     r15, [rdx-40h]
0x18006b553  mov     rcx, [rdx]
0x18006b556  mov     [rax], rcx
0x18006b559  mov     [rcx+8], rax
0x18006b55d  test    r15, r15
0x18006b560  jz      short loc_18006B583
0x18006b562  lea     rcx, [rbp+57h+var_B8]
0x18006b566  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x18006b56b  mov     rbx, r15
0x18006b56e  lea     rcx, [rbp+57h+var_B8]
0x18006b572  mov     [rbp+57h+var_B8], rbx
0x18006b576  call    ?SafeAddRef@?$TCntPtr@VCRdpUdpConnection@@@@AEAAXXZ; TCntPtr<CRdpUdpConnection>::SafeAddRef(void)
0x18006b57b  mov     r13, r15
0x18006b57e  mov     r14, r15
0x18006b581  jmp     short loc_18006B589
0x18006b583  xor     r13d, r13d
0x18006b586  xor     r14d, r14d
0x18006b589  mov     eax, [r14+0F0h]
0x18006b590  mov     rcx, r12; this
0x18006b593  mov     [rbp+57h+var_BC], eax
0x18006b596  mov     rax, [r14+100h]
0x18006b59d  mov     [rbp+57h+var_B0], rax
0x18006b5a1  mov     rax, [r14+0F8h]
0x18006b5a8  mov     [rbp+57h+var_88], rax
0x18006b5ac  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18006b5b1  lea     rdx, [r15+1B88h]; ActivityId
0x18006b5b8  mov     ecx, 2; ControlCode
0x18006b5bd  call    cs:__imp_EventActivityIdControl
0x18006b5c3  xor     r15d, r15d
0x18006b5c6  cmp     [rbp+57h+var_B0], r15
0x18006b5ca  jnz     short loc_18006B5DE
0x18006b5cc  lea     r8, [rbp+57h+var_B0]; unsigned __int64 *
0x18006b5d0  mov     rcx, rbx; this
0x18006b5d3  lea     rdx, [rbp+57h+var_88]; unsigned __int8 **
0x18006b5d7  call    ?GetDataToSend@CRdpUdpConnection@@QEAAJPEAPEAEPEA_K@Z; CRdpUdpConnection::GetDataToSend(uchar * *,unsigned __int64 *)
0x18006b5dc  mov     esi, eax
0x18006b5de  mov     ecx, cs:CallbackContext
0x18006b5e4  cmp     ecx, 5
0x18006b5e7  jbe     short loc_18006B625
0x18006b5e9  mov     ecx, dword ptr [rbp+57h+var_B0]
0x18006b5ec  lea     rax, aUdpSendConnect; "UDP Send Connection"
0x18006b5f3  mov     qword ptr [rbp+57h+ThreadId], rax
0x18006b5f7  lea     rdx, word_1801D4DE6
0x18006b5fe  lea     rax, [rbp+57h+var_C0]
0x18006b602  mov     [rbp+57h+var_C0], ecx
0x18006b605  mov     [rsp+110h+var_E0], rax
0x18006b60a  lea     rax, [rbp+57h+lpParameter]
0x18006b60e  mov     [rsp+110h+lpThreadId], rax
0x18006b613  lea     rax, [rbp+57h+ThreadId]
0x18006b617  mov     qword ptr [rsp+110h+dwCreationFlags], rax
0x18006b61c  mov     [rbp+57h+lpParameter], rbx
0x18006b620  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18006b625  cmp     esi, 1
0x18006b628  jnz     short loc_18006B663
0x18006b62a  mov     r8d, [rbp+57h+var_BC]; unsigned int
0x18006b62e  mov     rdx, rbx; struct CRdpUdpConnection *
0x18006b631  mov     rcx, rdi; this
0x18006b634  call    ?RemoveConnectionFromPendingList@CRdpUdpLocalEndpoint@@IEAAHPEAVCRdpUdpConnection@@I@Z; CRdpUdpLocalEndpoint::RemoveConnectionFromPendingList(CRdpUdpConnection *,uint)
0x18006b639  cmp     eax, esi
0x18006b63b  jnz     loc_18006B9A6
0x18006b641  lea     rcx, [rbp+57h+var_B8]
0x18006b645  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x18006b64a  mov     rbx, r15
0x18006b64d  lea     rcx, [rbp+57h+var_B8]
0x18006b651  mov     [rbp+57h+var_B8], rbx
0x18006b655  call    ?SafeAddRef@?$TCntPtr@VCRdpUdpConnection@@@@AEAAXXZ; TCntPtr<CRdpUdpConnection>::SafeAddRef(void)
0x18006b65a  mov     [rbp+57h+var_B0], r15
0x18006b65e  jmp     loc_18006B9A6
0x18006b663  test    esi, esi
0x18006b665  jns     loc_18006B8FA
0x18006b66b  mov     eax, cs:CallbackContext
0x18006b671  lea     r13, aSendfrompendin; "SendFromPendingQueue"
0x18006b678  mov     [rbp+57h+ThreadId], r15d
0x18006b67c  lea     r14, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006b683  cmp     eax, 2
0x18006b686  jbe     short loc_18006B6DE
0x18006b688  lea     rax, aRdpudplocalend; "RdpUdpLocalEndpoint::SendFromPendingQue"...
0x18006b68f  mov     [rbp+57h+lpParameter], r13
0x18006b693  mov     [rbp+57h+var_A0], rax
0x18006b697  lea     rdx, byte_1801D4E67
0x18006b69e  lea     rax, [rbp+57h+lpParameter]
0x18006b6a2  mov     [rbp+57h+var_BC], 659h
0x18006b6a9  mov     [rsp+110h+var_D0], rax
0x18006b6ae  lea     rax, [rbp+57h+var_BC]
0x18006b6b2  mov     [rsp+110h+var_D8], rax
0x18006b6b7  lea     rax, [rbp+57h+var_78]
0x18006b6bb  mov     [rsp+110h+var_E0], rax
0x18006b6c0  lea     rax, [rbp+57h+var_C0]
0x18006b6c4  mov     [rsp+110h+lpThreadId], rax
0x18006b6c9  lea     rax, [rbp+57h+var_A0]
0x18006b6cd  mov     qword ptr [rsp+110h+dwCreationFlags], rax
0x18006b6d2  mov     [rbp+57h+var_78], r14
0x18006b6d6  mov     [rbp+57h+var_C0], esi
0x18006b6d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006b6de  lea     rcx, [rbp+57h+var_70]
0x18006b6e2  mov     [rbp+57h+var_70], rbx
0x18006b6e6  call    ?SafeAddRef@?$TCntPtr@VCRdpUdpConnection@@@@AEAAXXZ; TCntPtr<CRdpUdpConnection>::SafeAddRef(void)
0x18006b6eb  mov     rax, [rdi]
0x18006b6ee  mov     rcx, rdi
0x18006b6f1  mov     [rbp+57h+var_68], rdi
0x18006b6f5  mov     rax, [rax+8]
0x18006b6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6fe  xor     eax, eax
0x18006b700  mov     [rbp+57h+var_60], esi
0x18006b703  lea     rdx, [rbp+57h+var_70]
0x18006b707  mov     [rbp+57h+var_5C], eax
0x18006b70a  lea     rcx, [rbp+57h+lpParameter]
0x18006b70e  call    ??$make_unique@UDeferredConnectionReleaseThreadContext@@U1@$0A@@utl@@YA?AV?$unique_ptr@UDeferredConnectionReleaseThreadContext@@U?$default_delete@UDeferredConnectionReleaseThreadContext@@@utl@@@0@$$QEAUDeferredConnectionReleaseThreadContext@@@Z; utl::make_unique<DeferredConnectionReleaseThreadContext,DeferredConnectionReleaseThreadContext,0>(DeferredConnectionReleaseThreadContext &&)
0x18006b713  lea     rcx, [rbp+57h+var_70]; this
0x18006b717  call    ??1DeferredConnectionReleaseThreadContext@@QEAA@XZ; DeferredConnectionReleaseThreadContext::~DeferredConnectionReleaseThreadContext(void)
0x18006b71c  mov     r9, [rbp+57h+lpParameter]; lpParameter
0x18006b720  test    r9, r9
0x18006b723  jnz     loc_18006B7B1
0x18006b729  mov     eax, cs:CallbackContext
0x18006b72f  mov     esi, 8007000Eh
0x18006b734  cmp     eax, 2
0x18006b737  jbe     short loc_18006B7A3
0x18006b739  lea     rax, aFailedToAlloca_21; "Failed to allocate DeferredConnectionRe"...
0x18006b740  mov     [rbp+57h+var_78], r13
0x18006b744  mov     [rbp+57h+var_A0], rax
0x18006b748  lea     rdx, byte_1801D471F
0x18006b74f  lea     rax, aErrorCondition; "Error condition failed"
0x18006b756  mov     [rbp+57h+var_BC], 662h
0x18006b75d  mov     [rbp+57h+var_98], rax
0x18006b761  lea     rax, [rbp+57h+var_A0]
0x18006b765  mov     [rsp+110h+var_C8], rax
0x18006b76a  lea     rax, [rbp+57h+var_78]
0x18006b76e  mov     [rsp+110h+var_D0], rax
0x18006b773  lea     rax, [rbp+57h+var_BC]
0x18006b777  mov     [rsp+110h+var_D8], rax
0x18006b77c  lea     rax, [rbp+57h+var_90]
0x18006b780  mov     [rsp+110h+var_E0], rax
0x18006b785  lea     rax, [rbp+57h+var_C0]
0x18006b789  mov     [rsp+110h+lpThreadId], rax
0x18006b78e  lea     rax, [rbp+57h+var_98]
0x18006b792  mov     qword ptr [rsp+110h+dwCreationFlags], rax
0x18006b797  mov     [rbp+57h+var_90], r14
0x18006b79b  mov     [rbp+57h+var_C0], esi
0x18006b79e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18006b7a3  lea     rcx, [rbp+57h+lpParameter]
0x18006b7a7  call    ??1?$unique_ptr@UDeferredConnectionReleaseThreadContext@@U?$default_delete@UDeferredConnectionReleaseThreadContext@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<DeferredConnectionReleaseThreadContext,utl::default_delete<DeferredConnectionReleaseThreadContext>>::~unique_ptr<DeferredConnectionReleaseThreadContext,utl::default_delete<DeferredConnectionReleaseThreadContext>>(void)
0x18006b7ac  jmp     loc_18006B9A6
0x18006b7b1  lea     rax, [rbp+57h+ThreadId]
0x18006b7b5  xor     edx, edx; dwStackSize
0x18006b7b7  mov     [rsp+110h+lpThreadId], rax; lpThreadId
0x18006b7bc  lea     r8, ?STATIC_DeferredConnectionReleaseThread@CRdpUdpLocalEndpoint@@KAKPEAX@Z; lpStartAddress
0x18006b7c3  xor     ecx, ecx; lpThreadAttributes
0x18006b7c5  mov     [rsp+110h+dwCreationFlags], 60h ; '`'; dwCreationFlags
0x18006b7cd  call    cs:__imp_CreateThread
0x18006b7d3  test    rax, rax
0x18006b7d6  jz      short loc_18006B7E7
0x18006b7d8  mov     rcx, rax; hObject
0x18006b7db  mov     [rbp+57h+lpParameter], r15
0x18006b7df  call    cs:__imp_CloseHandle
0x18006b7e5  jmp     short loc_18006B85A
0x18006b7e7  mov     eax, cs:CallbackContext
0x18006b7ed  cmp     eax, 2
0x18006b7f0  jbe     short loc_18006B85A
0x18006b7f2  mov     [rbp+57h+var_98], r13
0x18006b7f6  mov     [rbp+57h+var_BC], 673h
0x18006b7fd  mov     [rbp+57h+var_90], r14
0x18006b801  call    cs:__imp_GetLastError
0x18006b807  test    eax, eax
0x18006b809  jle     short loc_18006B813
0x18006b80b  movzx   eax, ax
0x18006b80e  or      eax, 80070000h
0x18006b813  mov     [rbp+57h+var_C0], eax
0x18006b816  lea     rdx, word_1801D4BF6
0x18006b81d  lea     rax, aFailedToCreate_99; "Failed to create deffered connection re"...
0x18006b824  mov     [rbp+57h+var_A0], rax
0x18006b828  lea     rax, [rbp+57h+var_98]
0x18006b82c  mov     [rsp+110h+var_D0], rax
0x18006b831  lea     rax, [rbp+57h+var_BC]
0x18006b835  mov     [rsp+110h+var_D8], rax
0x18006b83a  lea     rax, [rbp+57h+var_90]
0x18006b83e  mov     [rsp+110h+var_E0], rax
0x18006b843  lea     rax, [rbp+57h+var_C0]
0x18006b847  mov     [rsp+110h+lpThreadId], rax
0x18006b84c  lea     rax, [rbp+57h+var_A0]
0x18006b850  mov     qword ptr [rsp+110h+dwCreationFlags], rax
0x18006b855  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006b85a  mov     r14d, 80040004h
0x18006b860  mov     [rbp+57h+var_B0], r15
0x18006b864  cmp     esi, r14d
0x18006b867  jnz     loc_18006B7A3
0x18006b86d  mov     eax, cs:CallbackContext
0x18006b873  cmp     eax, 2
0x18006b876  jbe     short loc_18006B8D6
0x18006b878  lea     rax, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006b87f  mov     [rbp+57h+var_98], r13
0x18006b883  mov     [rbp+57h+var_90], rax
0x18006b887  lea     rdx, byte_1801D57AD
0x18006b88e  lea     rax, aRdpudplocalend_0; "RdpUdpLocalEndpoint::SendFromPendingQue"...
0x18006b895  mov     [rbp+57h+var_BC], 67Fh
0x18006b89c  mov     [rbp+57h+var_A0], rax
0x18006b8a0  lea     rax, [rbp+57h+var_98]
0x18006b8a4  mov     [rsp+110h+var_D0], rax
0x18006b8a9  lea     rax, [rbp+57h+var_BC]
0x18006b8ad  mov     [rsp+110h+var_D8], rax
0x18006b8b2  lea     rax, [rbp+57h+var_90]
0x18006b8b6  mov     [rsp+110h+var_E0], rax
0x18006b8bb  lea     rax, [rbp+57h+var_C0]
0x18006b8bf  mov     [rsp+110h+lpThreadId], rax
0x18006b8c4  lea     rax, [rbp+57h+var_A0]
0x18006b8c8  mov     qword ptr [rsp+110h+dwCreationFlags], rax
0x18006b8cd  mov     [rbp+57h+var_C0], r14d
0x18006b8d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006b8d6  mov     rcx, [rdi+220h]
0x18006b8dd  test    rcx, rcx
0x18006b8e0  jz      loc_18006B7A3
0x18006b8e6  mov     rax, [rcx]
0x18006b8e9  mov     edx, r14d
0x18006b8ec  mov     rax, [rax+20h]
0x18006b8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b8f5  jmp     loc_18006B7A3
0x18006b8fa  mov     r8, [rbp+57h+var_B0]
0x18006b8fe  test    r8, r8
0x18006b901  jz      loc_18006B9A6
0x18006b907  cmp     [r14+10Ch], r15d
0x18006b90e  lea     rax, [r13+0D0h]
0x18006b915  mov     r11, [rdi]
0x18006b918  mov     r10, r15
0x18006b91b  mov     rcx, r13; this
0x18006b91e  cmovz   r10, rax
0x18006b922  call    ?GetRemoteSockAddr@CRdpUdpConnection@@QEBAPEBUsockaddr_storage@@XZ; CRdpUdpConnection::GetRemoteSockAddr(void)
0x18006b927  mov     rdx, [rbp+57h+var_88]
0x18006b92b  mov     r9, rax
0x18006b92e  mov     rax, [r11+98h]
0x18006b935  mov     rcx, rdi
0x18006b938  mov     qword ptr [rsp+110h+dwCreationFlags], r10
0x18006b93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b942  mov     esi, eax
0x18006b944  cmp     eax, 8000000Ah
0x18006b949  jnz     short loc_18006B998
0x18006b94b  mov     rax, [rbp+57h+var_B0]
0x18006b94f  mov     [r14+100h], rax
0x18006b956  mov     rax, [rbp+57h+var_88]
0x18006b95a  mov     [r14+0F8h], rax
0x18006b961  mov     eax, cs:CallbackContext
0x18006b967  cmp     eax, 5
0x18006b96a  jbe     short loc_18006B9A6
0x18006b96c  lea     rax, aUdpSendFailedR; "UDP Send Failed: returned WSAEWOULDBLOC"...
0x18006b973  xor     r8d, r8d
0x18006b976  mov     [rbp+57h+var_98], rax
0x18006b97a  lea     rdx, byte_1801D51B7
0x18006b981  lea     rax, [rbp+57h+var_98]
0x18006b985  lea     rcx, CallbackContext
0x18006b98c  mov     qword ptr [rsp+110h+dwCreationFlags], rax
0x18006b991  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006b996  jmp     short loc_18006B9A6
0x18006b998  mov     [r14+100h], r15
0x18006b99f  mov     [r14+0F8h], r15
0x18006b9a6  test    rbx, rbx
  ... truncated ...
```
