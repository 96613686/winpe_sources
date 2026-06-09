# HttpThreadPoolRequestQueueCallback

- ea: `0x18000a620`
- end: `0x18000afb6`
- name: `HttpThreadPoolRequestQueueCallback`
- size: `2454`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, char *Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800021f0`
- `0x180002908`
- `0x180002d40`
- `0x180002d70`
- `0x180004bc0`
- `0x180005230`
- `0x1800068e0`
- `0x180006b64`
- `0x180006e80`
- `0x18000827c`
- `0x180008360`
- `0x180009dd8`
- `0x18000a620`
- `0x18000afbc`
- `0x18000bc78`
- `0x18000bf68`
- `0x18000c788`
- `0x1800132c0`
- `0x18001bca2`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001bd80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a84e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a960`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a9c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aadc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000acfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a84e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a960`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a9c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aadc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ac6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000acfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aaec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aaec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae60`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000abd8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000abd8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000ab7e`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000ab7e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000ad96`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000ad96`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000abaf`
- `HTTPAPI!HttpReceiveHttpRequest` at `0x18000abaf`
- `prxyqry!GetSstpDestinationInfo` at `0x18000ae20`
- `prxyqry!GetSstpDestinationInfo` at `0x18000ae20`
- `prxyqry!GetSstpGroupIDFromQueryString` at `0x18000ad41`
- `prxyqry!GetSstpGroupIDFromQueryString` at `0x18000ad41`

## string_xrefs

- `0x18000a68c`: `HttpThreadPoolRequestQueueCallback`
- `0x18000af4b`: `HttpThreadPoolRequestQueueCallback`
- `0x18000adba`: `Failed to create Correlation GUID: %d`

## pseudocode

```c
void __fastcall HttpThreadPoolRequestQueueCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        char *Overlapped,
        ULONG IoResult,
        ULONG_PTR NumberOfBytesTransferred)
{
  const wchar_t *v7; // r8
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  __int64 v15; // rbx
  __int64 v16; // rcx
  char *v17; // rcx
  unsigned int v18; // eax
  char *v19; // rcx
  char *v20; // rbx
  int v21; // r15d
  PTP_IO *v22; // rcx
  ULONG v23; // eax
  ULONG v24; // edi
  int v25; // r15d
  __int64 SstpGroupIDFromQueryString; // rax
  HRESULT v27; // eax
  __int64 v28; // r9
  unsigned int SstpDestinationInfo; // eax
  DWORD v30; // edi
  HANDLE ProcessHeap; // rax
  unsigned int v32; // eax
  ULONG RequestBufferLength[2]; // [rsp+20h] [rbp-E0h]
  DWORD Size; // [rsp+50h] [rbp-B0h] BYREF
  int Size_4; // [rsp+54h] [rbp-ACh] BYREF
  void *Src; // [rsp+58h] [rbp-A8h] BYREF
  GUID pguid; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v38[8]; // [rsp+70h] [rbp-90h] BYREF
  DWORD v39; // [rsp+78h] [rbp-88h]
  _BYTE v40[8196]; // [rsp+7Ch] [rbp-84h] BYREF
  int v41; // [rsp+2080h] [rbp+1F80h] BYREF
  _BYTE v42[2044]; // [rsp+2084h] [rbp+1F84h] BYREF
  __int16 v43; // [rsp+2880h] [rbp+2780h] BYREF
  _BYTE v44[510]; // [rsp+2882h] [rbp+2782h] BYREF

  v41 = 0;
  memset_0(v42, 0, sizeof(v42));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v41) = 0;
    FormatRRASErrorString((wchar_t *)&v41, L"Entering %ws", L"HttpThreadPoolRequestQueueCallback");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v41);
  }
  if ( !Overlapped )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_94;
    v7 = L"NULL overlapped received";
    goto LABEL_7;
  }
  v8 = *((_DWORD *)Overlapped + 8);
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v41) = 0;
    FormatRRASErrorString((wchar_t *)&v41, L"Received overlapID %d", v8);
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v41);
  }
  v9 = v8 - 17767;
  if ( !v9 )
  {
    LOWORD(Size) = 0;
    v43 = 0;
    memset_0(v44, 0, 0x1FCu);
    v15 = *((_QWORD *)Overlapped + 7);
    if ( IoResult )
    {
      if ( IoResult == 234 )
      {
        if ( (byte_18002D803 & 0x10) != 0 )
        {
          LOWORD(v41) = 0;
          FormatRRASErrorString((wchar_t *)&v41, L"CoId=%hs:RECEIVE_REQUEST with MORE_DATA", v15 + 552);
          if ( (byte_18002D803 & 0x10) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v41);
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
        *(_DWORD *)(v15 + 252) |= 2u;
        LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
        v21 = ProcessReceivedHttpRequest(Overlapped + 96, &Size);
        if ( v21 )
        {
          if ( (byte_18002D803 & 8) != 0 )
          {
            LOWORD(v41) = 0;
            FormatRRASErrorString(
              (wchar_t *)&v41,
              L"CoId=%hs:Validation of the header fails. Initiating termination",
              v15 + 552);
            if ( (byte_18002D803 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v41);
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
          *(_DWORD *)(v15 + 268) = v21;
        }
        else
        {
          v22 = (PTP_IO *)SstpSvcGlobals;
          *(_OWORD *)Overlapped = 0;
          *((_OWORD *)Overlapped + 1) = 0;
          StartThreadpoolIo(v22[21]);
          v23 = HttpReceiveHttpRequest(
                  *((HANDLE *)SstpSvcGlobals + 8),
                  *((_QWORD *)Overlapped + 14),
                  0,
                  (PHTTP_REQUEST)(Overlapped + 96),
                  0x4000u,
                  0,
                  (LPOVERLAPPED)Overlapped);
          v24 = v23;
          if ( v23 == 997 || !v23 )
            goto LABEL_94;
          CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
          if ( (byte_18002D803 & 8) != 0 )
          {
            RequestBufferLength[0] = v24;
            LOWORD(v41) = 0;
            FormatRRASErrorString(
              (wchar_t *)&v41,
              L"CoId=%hs:Reposting HttpReceiveHttpRequest failed with %d [%d]",
              v15 + 552,
              v24,
              *(_QWORD *)RequestBufferLength);
            if ( (byte_18002D803 & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v41);
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
          *(_DWORD *)(v15 + 268) = v24;
        }
        InitiateCallContextCleanup(v15, 2);
        DereferenceRefCount(v15 + 208);
        PostNewHttpRequest();
        goto LABEL_94;
      }
      if ( IoResult != 995 )
      {
        if ( (byte_18002D803 & 8) == 0 )
          goto LABEL_94;
        LOWORD(v41) = 0;
        FormatRRASErrorString((wchar_t *)&v41, L"CoId=%hs:IOResult: %d - Unhandled", v15 + 552, IoResult);
        if ( (byte_18002D803 & 8) == 0 )
          goto LABEL_94;
        goto LABEL_49;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
      *(_DWORD *)(v15 + 268) = 995;
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
      *(_DWORD *)(v15 + 252) |= 0x202u;
      *(_QWORD *)(v15 + 280) = *((_QWORD *)Overlapped + 13);
      *(_QWORD *)(v15 + 272) = *((_QWORD *)Overlapped + 14);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
      v25 = ProcessReceivedHttpRequest(Overlapped + 96, &Size);
      if ( v25 )
      {
        if ( (byte_18002D803 & 8) != 0 )
        {
          LOWORD(v41) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v41,
            L"CoId=%hs:Validation of the header fails. Initiating termination",
            v15 + 552);
          if ( (byte_18002D803 & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v41);
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
        *(_DWORD *)(v15 + 268) = v25;
        InitiateCallContextCleanup(v15, 2);
        PostNewHttpRequest();
        goto LABEL_92;
      }
      PostNewHttpRequest();
      if ( GetSstpConfigFlag(1) )
      {
        SstpGroupIDFromQueryString = GetSstpGroupIDFromQueryString(
                                       *((_QWORD *)Overlapped + 24),
                                       *((unsigned __int16 *)Overlapped + 83));
        if ( (unsigned int)FindSstpGatewayByGroup(SstpGroupIDFromQueryString, &v43) )
        {
          Src = 0;
          Size = 0;
          memset_0(v38, 0, 0x200Cu);
          Size_4 = 0;
          pguid = 0;
          v27 = CoCreateGuid(&pguid);
          if ( v27 )
          {
            if ( (byte_18002D803 & 8) == 0 )
              goto LABEL_94;
            LOWORD(v41) = 0;
            FormatRRASErrorString((wchar_t *)&v41, L"Failed to create Correlation GUID: %d", (unsigned __int16)v27);
          }
          else
          {
            LOBYTE(v28) = 1;
            SstpDestinationInfo = GetSstpDestinationInfo(&v43, &Src, &Size, v28, &Size_4, &pguid, 0, 0, 0);
            if ( !SstpDestinationInfo )
            {
              if ( Src )
              {
                v30 = Size;
                if ( Size < 0x2000 )
                {
                  memcpy_0(v40, Src, Size);
                  v39 = v30;
                  ProcessHeap = GetProcessHeap();
                  HeapFree(ProcessHeap, 0, Src);
                  v32 = ForwardMakeCallRequest(v38, v15);
                  if ( v32 && (byte_18002D803 & 8) != 0 )
                  {
                    LOWORD(v41) = 0;
                    FormatRRASErrorString((wchar_t *)&v41, L"ForwardMakeCallRequest failed: %d", v32);
LABEL_84:
                    if ( (byte_18002D803 & 8) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasSSTPSvcTraceError,
                        &v41);
                  }
LABEL_92:
                  v19 = (char *)(v15 + 208);
                  goto LABEL_93;
                }
              }
            }
            if ( (byte_18002D803 & 8) == 0 )
              goto LABEL_94;
            LOWORD(v41) = 0;
            FormatRRASErrorString((wchar_t *)&v41, L"GetSstpDestinationInfo failed: %d", SstpDestinationInfo);
          }
          if ( (byte_18002D803 & 8) == 0 )
            goto LABEL_94;
LABEL_49:
          v7 = (const wchar_t *)&v41;
LABEL_7:
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, v7);
          goto LABEL_94;
        }
      }
      if ( GetSstpConfigFlag(2) )
      {
        ProcessNewCall(v15, Overlapped, Overlapped + 96);
        goto LABEL_92;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 288));
      *(_DWORD *)(v15 + 268) = 0;
    }
    InitiateCallContextCleanup(v15, 2);
    goto LABEL_92;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceInfo,
        L"TerminatePartialConnection returns");
    v20 = (char *)*((_QWORD *)Overlapped + 7);
    FreeBufferToPool((__int64)SstpSvcGlobals + 424, (__int64)Overlapped, 1);
    EnterCriticalSection((LPCRITICAL_SECTION)(v20 + 288));
    *((_DWORD *)v20 + 63) &= ~0x2000u;
    v17 = v20;
    goto LABEL_43;
  }
  v11 = v10 - 3;
  if ( !v11 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)Overlapped + 4);
    InitiateCallContextCleanup(Overlapped - 128, 1);
    v19 = Overlapped + 80;
LABEL_93:
    DereferenceRefCount((__int64)v19);
    goto LABEL_94;
  }
  v12 = v11 - 2;
  if ( !v12 )
  {
    v15 = *((_QWORD *)Overlapped + 7);
    if ( !IoResult )
    {
      if ( (byte_18002D803 & 0x10) != 0 )
      {
        LOWORD(v41) = 0;
        FormatRRASErrorString((wchar_t *)&v41, L"CoId=%hs:Successfully established the Layer-2", v15 + 552);
        if ( (byte_18002D803 & 0x10) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v41);
      }
      IndicateCallConnectedToTPI((LPOVERLAPPED)v15);
      goto LABEL_92;
    }
    if ( !(unsigned int)IsProxyCall(*((_QWORD *)Overlapped + 7)) )
    {
      Size = 0;
      v18 = SyncDeviceControl(*((_QWORD *)SstpSvcGlobals + 35), 1212480, (int)v15 + 240, 4, 0, 0, &Size);
      if ( v18 )
      {
        if ( (byte_18002D803 & 8) != 0 )
        {
          LOWORD(v41) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v41,
            L"CoId=%hs:SyncDevCtrl for Fast disconnect notify fails with %d",
            v15 + 552,
            v18);
          goto LABEL_84;
        }
      }
    }
    goto LABEL_92;
  }
  v13 = v12 - 2;
  if ( !v13 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)Overlapped + 3);
    *((_DWORD *)Overlapped + 21) &= ~0x2000u;
    v17 = Overlapped - 168;
LABEL_43:
    InitiateCallContextCleanup(v17, 2);
    goto LABEL_94;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v15 = *((_QWORD *)Overlapped + 7);
    if ( IoResult )
    {
      FreeBufferToPool((__int64)SstpSvcGlobals + 424, (__int64)Overlapped, 1);
    }
    else
    {
      v16 = *((_QWORD *)Overlapped + 7);
      *((_DWORD *)Overlapped + 23) = NumberOfBytesTransferred;
      *((_DWORD *)Overlapped + 22) = *(_DWORD *)(v15 + 240);
      if ( (unsigned int)IsProxyCall(v16) )
        ProxySendToRelatedCtx((LPOVERLAPPED)Overlapped);
      else
        ProcessReceivedBytes(Overlapped);
      PostReceiveOnCall(v15);
    }
    goto LABEL_92;
  }
  if ( v14 == 2 )
  {
    if ( IoResult )
    {
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v41) = 0;
        FormatRRASErrorString((wchar_t *)&v41, L"SendToHttp fails with %d", IoResult);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v41);
      }
    }
    FreeBufferToPool((__int64)SstpSvcGlobals + 424, (__int64)Overlapped, 1);
  }
LABEL_94:
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v41) = 0;
    FormatRRASErrorString((wchar_t *)&v41, L"LEaving %ws", L"HttpThreadPoolRequestQueueCallback");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v41);
  }
}

```

## disassembly

```asm
0x18000a620  mov     [rsp-8+arg_0], rbx
0x18000a625  mov     [rsp-8+arg_8], rsi
0x18000a62a  push    rbp
0x18000a62b  push    rdi
0x18000a62c  push    r13
0x18000a62e  push    r14
0x18000a630  push    r15
0x18000a632  lea     rbp, [rsp-2990h]
0x18000a63a  mov     eax, 2A90h
0x18000a63f  call    _alloca_probe
0x18000a644  sub     rsp, rax
0x18000a647  mov     rax, cs:__security_cookie
0x18000a64e  xor     rax, rsp
0x18000a651  mov     [rbp+29B0h+var_30], rax
0x18000a658  mov     rdi, r8
0x18000a65b  lea     rcx, [rbp+29B0h+var_A2C]; void *
0x18000a662  xor     eax, eax
0x18000a664  mov     r8d, 7FCh; Size
0x18000a66a  xor     edx, edx; Val
0x18000a66c  mov     [rbp+29B0h+var_A30], eax
0x18000a672  mov     esi, r9d
0x18000a675  call    memset_0
0x18000a67a  test    cs:byte_18002D803, 10h
0x18000a681  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a688  jz      short loc_18000A6CC
0x18000a68a  xor     eax, eax
0x18000a68c  lea     r8, aHttpthreadpool; "HttpThreadPoolRequestQueueCallback"
0x18000a693  lea     rdx, aEnteringWs; "Entering %ws"
0x18000a69a  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000a6a1  lea     rcx, [rbp+29B0h+var_A30]
0x18000a6a8  call    FormatRRASErrorString
0x18000a6ad  test    cs:byte_18002D803, 10h
0x18000a6b4  jz      short loc_18000A6CC
0x18000a6b6  lea     r8, [rbp+29B0h+var_A30]
0x18000a6bd  mov     rcx, r13
0x18000a6c0  lea     rdx, RasSSTPSvcTraceInfo
0x18000a6c7  call    McTemplateU0z_EventWriteTransfer
0x18000a6cc  test    rdi, rdi
0x18000a6cf  jnz     short loc_18000A6F9
0x18000a6d1  test    cs:byte_18002D803, 8
0x18000a6d8  jz      loc_18000AF40
0x18000a6de  lea     r8, aNullOverlapped; "NULL overlapped received"
0x18000a6e5  lea     rdx, RasSSTPSvcTraceError
0x18000a6ec  mov     rcx, r13
0x18000a6ef  call    McTemplateU0z_EventWriteTransfer
0x18000a6f4  jmp     loc_18000AF40
0x18000a6f9  test    cs:byte_18002D803, 10h
0x18000a700  mov     ebx, [rdi+20h]
0x18000a703  jz      short loc_18000A743
0x18000a705  xor     eax, eax
0x18000a707  lea     rdx, aReceivedOverla; "Received overlapID %d"
0x18000a70e  mov     r8d, ebx
0x18000a711  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000a718  lea     rcx, [rbp+29B0h+var_A30]
0x18000a71f  call    FormatRRASErrorString
0x18000a724  test    cs:byte_18002D803, 10h
0x18000a72b  jz      short loc_18000A743
0x18000a72d  lea     r8, [rbp+29B0h+var_A30]
0x18000a734  mov     rcx, r13
0x18000a737  lea     rdx, RasSSTPSvcTraceInfo
0x18000a73e  call    McTemplateU0z_EventWriteTransfer
0x18000a743  sub     ebx, 4567h
0x18000a749  jz      loc_18000A9E0
0x18000a74f  sub     ebx, 1
0x18000a752  jz      loc_18000A97D
0x18000a758  sub     ebx, 3
0x18000a75b  jz      loc_18000A959
0x18000a761  sub     ebx, 2
0x18000a764  jz      loc_18000A865
0x18000a76a  sub     ebx, 2
0x18000a76d  jz      loc_18000A84A
0x18000a773  sub     ebx, 1
0x18000a776  jz      short loc_18000A7EA
0x18000a778  cmp     ebx, 2
0x18000a77b  jnz     loc_18000AF40
0x18000a781  test    esi, esi
0x18000a783  jz      short loc_18000A7CC
0x18000a785  test    cs:byte_18002D803, 8
0x18000a78c  jz      short loc_18000A7CC
0x18000a78e  xor     eax, eax
0x18000a790  lea     rdx, aSendtohttpFail; "SendToHttp fails with %d"
0x18000a797  mov     r8d, esi
0x18000a79a  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000a7a1  lea     rcx, [rbp+29B0h+var_A30]
0x18000a7a8  call    FormatRRASErrorString
0x18000a7ad  test    cs:byte_18002D803, 8
0x18000a7b4  jz      short loc_18000A7CC
0x18000a7b6  lea     r8, [rbp+29B0h+var_A30]
0x18000a7bd  mov     rcx, r13
0x18000a7c0  lea     rdx, RasSSTPSvcTraceError
0x18000a7c7  call    McTemplateU0z_EventWriteTransfer
0x18000a7cc  mov     rcx, cs:SstpSvcGlobals
0x18000a7d3  mov     r8b, 1
0x18000a7d6  add     rcx, 1A8h
0x18000a7dd  mov     rdx, rdi
0x18000a7e0  call    FreeBufferToPool
0x18000a7e5  jmp     loc_18000AF40
0x18000a7ea  mov     rbx, [rdi+38h]
0x18000a7ee  test    esi, esi
0x18000a7f0  jnz     short loc_18000A82C
0x18000a7f2  mov     eax, dword ptr [rbp+29B0h+NumberOfBytesTransferred]
0x18000a7f8  mov     rcx, rbx
0x18000a7fb  mov     [rdi+5Ch], eax
0x18000a7fe  mov     eax, [rbx+0F0h]
0x18000a804  mov     [rdi+58h], eax
0x18000a807  call    IsProxyCall
0x18000a80c  mov     rcx, rdi; Overlapped
0x18000a80f  test    eax, eax
0x18000a811  jz      short loc_18000A81A
0x18000a813  call    ProxySendToRelatedCtx
0x18000a818  jmp     short loc_18000A81F
0x18000a81a  call    ProcessReceivedBytes
0x18000a81f  mov     rcx, rbx
0x18000a822  call    PostReceiveOnCall
0x18000a827  jmp     loc_18000AF34
0x18000a82c  mov     rcx, cs:SstpSvcGlobals
0x18000a833  mov     r8b, 1
0x18000a836  add     rcx, 1A8h
0x18000a83d  mov     rdx, rdi
0x18000a840  call    FreeBufferToPool
0x18000a845  jmp     loc_18000AF34
0x18000a84a  lea     rcx, [rdi+78h]; lpCriticalSection
0x18000a84e  call    cs:__imp_EnterCriticalSection
0x18000a854  btr     dword ptr [rdi+54h], 0Dh
0x18000a859  lea     rcx, [rdi-0A8h]
0x18000a860  jmp     loc_18000A9D1
0x18000a865  mov     rbx, [rdi+38h]
0x18000a869  test    esi, esi
0x18000a86b  jnz     short loc_18000A8C5
0x18000a86d  test    cs:byte_18002D803, 10h
0x18000a874  jz      short loc_18000A8B8
0x18000a876  xor     eax, eax
0x18000a878  lea     r8, [rbx+228h]
0x18000a87f  lea     rdx, aCoidHsSuccessf; "CoId=%hs:Successfully established the L"...
0x18000a886  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000a88d  lea     rcx, [rbp+29B0h+var_A30]
0x18000a894  call    FormatRRASErrorString
0x18000a899  test    cs:byte_18002D803, 10h
0x18000a8a0  jz      short loc_18000A8B8
0x18000a8a2  lea     r8, [rbp+29B0h+var_A30]
0x18000a8a9  mov     rcx, r13
0x18000a8ac  lea     rdx, RasSSTPSvcTraceInfo
0x18000a8b3  call    McTemplateU0z_EventWriteTransfer
0x18000a8b8  mov     rcx, rbx; LPOVERLAPPED
0x18000a8bb  call    IndicateCallConnectedToTPI
0x18000a8c0  jmp     loc_18000AF34
0x18000a8c5  mov     rcx, rbx
0x18000a8c8  call    IsProxyCall
0x18000a8cd  test    eax, eax
0x18000a8cf  jnz     loc_18000AF34
0x18000a8d5  mov     rcx, cs:SstpSvcGlobals
0x18000a8dc  lea     r8, [rbx+0F0h]; int
0x18000a8e3  mov     dword ptr [rsp+2AB0h+Size], eax
0x18000a8e7  mov     edx, 128040h; int
0x18000a8ec  lea     rax, [rsp+2AB0h+Size]
0x18000a8f1  mov     r9d, 4; int
0x18000a8f7  mov     [rsp+2AB0h+Overlapped], rax; LPDWORD
0x18000a8fc  mov     rcx, [rcx+118h]; int
0x18000a903  mov     dword ptr [rsp+2AB0h+BytesReturned], 0; DWORD
0x18000a90b  mov     qword ptr [rsp+2AB0h+RequestBufferLength], 0; LPVOID
0x18000a914  call    SyncDeviceControl
0x18000a919  test    eax, eax
0x18000a91b  jz      loc_18000AF34
0x18000a921  test    cs:byte_18002D803, 8
0x18000a928  jz      loc_18000AF34
0x18000a92e  xor     ecx, ecx
0x18000a930  lea     r8, [rbx+228h]
0x18000a937  mov     word ptr [rbp+29B0h+var_A30], cx
0x18000a93e  lea     rdx, aCoidHsSyncdevc; "CoId=%hs:SyncDevCtrl for Fast disconnec"...
0x18000a945  lea     rcx, [rbp+29B0h+var_A30]
0x18000a94c  mov     r9d, eax
0x18000a94f  call    FormatRRASErrorString
0x18000a954  jmp     loc_18000AEB7
0x18000a959  lea     rcx, [rdi+0A0h]; lpCriticalSection
0x18000a960  call    cs:__imp_EnterCriticalSection
0x18000a966  mov     edx, 1
0x18000a96b  lea     rcx, [rdi-80h]
0x18000a96f  call    InitiateCallContextCleanup
0x18000a974  lea     rcx, [rdi+50h]
0x18000a978  jmp     loc_18000AF3B
0x18000a97d  test    cs:byte_18002D803, 10h
0x18000a984  jz      short loc_18000A99C
0x18000a986  lea     r8, aTerminateparti; "TerminatePartialConnection returns"
0x18000a98d  mov     rcx, r13
0x18000a990  lea     rdx, RasSSTPSvcTraceInfo
0x18000a997  call    McTemplateU0z_EventWriteTransfer
0x18000a99c  mov     rcx, cs:SstpSvcGlobals
0x18000a9a3  mov     r8b, 1
0x18000a9a6  mov     rbx, [rdi+38h]
0x18000a9aa  add     rcx, 1A8h
0x18000a9b1  mov     rdx, rdi
0x18000a9b4  call    FreeBufferToPool
0x18000a9b9  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000a9c0  call    cs:__imp_EnterCriticalSection
0x18000a9c6  btr     dword ptr [rbx+0FCh], 0Dh
0x18000a9ce  mov     rcx, rbx
0x18000a9d1  mov     edx, 2
0x18000a9d6  call    InitiateCallContextCleanup
0x18000a9db  jmp     loc_18000AF40
0x18000a9e0  xor     eax, eax
0x18000a9e2  lea     rcx, [rbp+29B0h+var_22E]; void *
0x18000a9e9  xor     edx, edx; Val
0x18000a9eb  mov     word ptr [rsp+2AB0h+Size], ax
0x18000a9f0  mov     r8d, 1FCh; Size
0x18000a9f6  mov     [rbp+29B0h+var_230], ax
0x18000a9fd  call    memset_0
0x18000aa02  mov     rbx, [rdi+38h]
0x18000aa06  lea     r14, [rdi+60h]
0x18000aa0a  test    esi, esi
0x18000aa0c  jz      loc_18000AC62
0x18000aa12  cmp     esi, 0EAh
0x18000aa18  jz      short loc_18000AA87
0x18000aa1a  mov     edi, 3E3h
0x18000aa1f  cmp     esi, edi
0x18000aa21  jz      short loc_18000AA6F
0x18000aa23  test    cs:byte_18002D803, 8
0x18000aa2a  jz      loc_18000AF40
0x18000aa30  xor     eax, eax
0x18000aa32  lea     r8, [rbx+228h]
0x18000aa39  mov     r9d, esi
0x18000aa3c  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000aa43  lea     rdx, aCoidHsIoresult; "CoId=%hs:IOResult: %d - Unhandled"
0x18000aa4a  lea     rcx, [rbp+29B0h+var_A30]
0x18000aa51  call    FormatRRASErrorString
0x18000aa56  test    cs:byte_18002D803, 8
0x18000aa5d  jz      loc_18000AF40
0x18000aa63  lea     r8, [rbp+29B0h+var_A30]
0x18000aa6a  jmp     loc_18000A6E5
0x18000aa6f  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000aa76  call    cs:__imp_EnterCriticalSection
0x18000aa7c  mov     [rbx+10Ch], edi
0x18000aa82  jmp     loc_18000AF27
0x18000aa87  test    cs:byte_18002D803, 10h
0x18000aa8e  jz      short loc_18000AAD2
0x18000aa90  xor     eax, eax
0x18000aa92  lea     r8, [rbx+228h]
0x18000aa99  lea     rdx, aCoidHsReceiveR; "CoId=%hs:RECEIVE_REQUEST with MORE_DATA"
0x18000aaa0  mov     word ptr [rbp+29B0h+var_A30], ax
0x18000aaa7  lea     rcx, [rbp+29B0h+var_A30]
0x18000aaae  call    FormatRRASErrorString
0x18000aab3  test    cs:byte_18002D803, 10h
0x18000aaba  jz      short loc_18000AAD2
0x18000aabc  lea     r8, [rbp+29B0h+var_A30]
0x18000aac3  mov     rcx, r13
0x18000aac6  lea     rdx, RasSSTPSvcTraceInfo
0x18000aacd  call    McTemplateU0z_EventWriteTransfer
0x18000aad2  lea     rsi, [rbx+120h]
0x18000aad9  mov     rcx, rsi; lpCriticalSection
0x18000aadc  call    cs:__imp_EnterCriticalSection
0x18000aae2  or      dword ptr [rbx+0FCh], 2
0x18000aae9  mov     rcx, rsi; lpCriticalSection
0x18000aaec  call    cs:__imp_LeaveCriticalSection
0x18000aaf2  lea     rdx, [rsp+2AB0h+Size]
0x18000aaf7  mov     rcx, r14
0x18000aafa  call    ProcessReceivedHttpRequest
0x18000aaff  mov     r15d, eax
0x18000ab02  test    eax, eax
0x18000ab04  jz      short loc_18000AB66
0x18000ab06  test    cs:byte_18002D803, 8
0x18000ab0d  jz      short loc_18000AB51
0x18000ab0f  xor     ecx, ecx
0x18000ab11  lea     r8, [rbx+228h]
0x18000ab18  mov     word ptr [rbp+29B0h+var_A30], cx
0x18000ab1f  lea     rdx, aCoidHsValidati; "CoId=%hs:Validation of the header fails"...
0x18000ab26  lea     rcx, [rbp+29B0h+var_A30]
0x18000ab2d  call    FormatRRASErrorString
0x18000ab32  test    cs:byte_18002D803, 8
0x18000ab39  jz      short loc_18000AB51
0x18000ab3b  lea     r8, [rbp+29B0h+var_A30]
0x18000ab42  mov     rcx, r13
0x18000ab45  lea     rdx, RasSSTPSvcTraceError
0x18000ab4c  call    McTemplateU0z_EventWriteTransfer
0x18000ab51  mov     rcx, rsi; lpCriticalSection
0x18000ab54  call    cs:__imp_EnterCriticalSection
0x18000ab5a  mov     [rbx+10Ch], r15d
0x18000ab61  jmp     loc_18000AC3F
0x18000ab66  mov     rcx, cs:SstpSvcGlobals
0x18000ab6d  xorps   xmm0, xmm0
0x18000ab70  movups  xmmword ptr [rdi], xmm0
0x18000ab73  movups  xmmword ptr [rdi+10h], xmm0
0x18000ab77  mov     rcx, [rcx+0A8h]; pio
0x18000ab7e  call    cs:__imp_StartThreadpoolIo
0x18000ab84  mov     rcx, cs:SstpSvcGlobals
0x18000ab8b  mov     r9, r14; RequestBuffer
0x18000ab8e  mov     rdx, [r14+10h]; RequestId
0x18000ab92  xor     r8d, r8d; Flags
0x18000ab95  mov     [rsp+2AB0h+Overlapped], rdi; Overlapped
0x18000ab9a  mov     [rsp+2AB0h+BytesReturned], 0; BytesReturned
0x18000aba3  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000aba7  mov     [rsp+2AB0h+RequestBufferLength], 4000h; RequestBufferLength
0x18000abaf  call    cs:__imp_HttpReceiveHttpRequest
0x18000abb5  mov     edi, eax
0x18000abb7  cmp     eax, 3E5h
0x18000abbc  jz      loc_18000AF40
0x18000abc2  test    eax, eax
0x18000abc4  jz      loc_18000AF40
0x18000abca  mov     rcx, cs:SstpSvcGlobals
0x18000abd1  mov     rcx, [rcx+0A8h]; pio
0x18000abd8  call    cs:__imp_CancelThreadpoolIo
0x18000abde  test    cs:byte_18002D803, 8
  ... truncated ...
```
