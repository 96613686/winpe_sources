# CMFTWrapperAsync::CMFTWrapperAsync(ulong,IMFTransform *,long *)

- ea: `0x1800a9778`
- end: `0x1800aa09b`
- name: `??0CMFTWrapperAsync@@QEAA@KPEAUIMFTransform@@PEAJ@Z`
- size: `2339`
- prototype: `CMFTWrapperAsync *__fastcall(CMFTWrapperAsync *__hidden this, unsigned int, struct IMFTransform *, int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a8260`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004714c`
- `0x18004d118`
- `0x180050d6c`
- `0x1800a9778`
- `0x1800aa468`
- `0x1800aa49c`
- `0x1800aa508`
- `0x1800cf200`
- `0x1800ec0e0`
- `0x18015ab74`
- `0x1802583a8`
- `0x1802592a0`
- `0x180271b28`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a9d7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a9d7e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a980b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a9932`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a9945`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a980b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a9932`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a9945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9d96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9b46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9e3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9ee6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9f8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9b46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9e3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9ee6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9f8e`
- `MFPlat!MFCreateEventQueue` at `0x1800a9e19`
- `MFPlat!MFCreateEventQueue` at `0x1800a9e19`

## pseudocode

```c
CMFTWrapperAsync *__fastcall CMFTWrapperAsync::CMFTWrapperAsync(
        CMFTWrapperAsync *this,
        int a2,
        struct IMFTransform *a3,
        int *a4)
{
  struct IMFTransform **v7; // r14
  int *v8; // rbx
  int Streams; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CPassthroughMFT *v48; // rax
  CPassthroughMFT *v49; // rax
  char v51; // [rsp+78h] [rbp+10h] BYREF
  int *v52; // [rsp+88h] [rbp+20h]

  v52 = a4;
  _InterlockedIncrement((_DWORD *)&qword_1803CE158 + 1);
  *(_QWORD *)this = &CMFTWrapperAsync::`vftable'{for `IMFTransform'};
  *((_QWORD *)this + 1) = &CMFTWrapperAsync::`vftable'{for `IMFTransformWrapper'};
  *((_QWORD *)this + 2) = &CMFTWrapperAsync::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 3) = &CMFTWrapperAsync::`vftable'{for `IMFMediaEventGenerator'};
  *((_QWORD *)this + 4) = &CMFTWrapperAsync::`vftable'{for `IMFShutdown'};
  *((_QWORD *)this + 5) = &CMFTWrapperAsync::`vftable'{for `IMFRealTimeClient'};
  *((_QWORD *)this + 6) = &CMFTWrapperAsync::`vftable'{for `IMFRealTimeClientEx'};
  *((_QWORD *)this + 7) = &CMFTWrapperAsync::`vftable'{for `IMFRateControl'};
  CMFTWrapperAsync::ProcessingLoopAsyncCallback::ProcessingLoopAsyncCallback((CMFTWrapperAsync *)((char *)this + 64));
  *((_DWORD *)this + 18) = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 2);
  v7 = (struct IMFTransform **)((char *)this + 128);
  *((_DWORD *)this + 30) = a2;
  ComSmartPtr<IUnknown>::ComSmartPtr<IUnknown>((char *)this + 128, a3);
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_BYTE *)this + 152) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_WORD *)this + 108) = 0;
  *((_BYTE *)this + 218) = 0;
  memset_0((char *)this + 224, 0, 0xA0u);
  *((_DWORD *)this + 51) |= 1u;
  *((_QWORD *)this + 24) = &CTPtrArray<IMFTransform,20>::`vftable';
  *((_QWORD *)this + 48) = 0;
  *((_DWORD *)this + 98) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_WORD *)this + 212) = 0;
  *((_BYTE *)this + 426) = 0;
  memset_0((char *)this + 432, 0, 0xA0u);
  *((_DWORD *)this + 103) |= 1u;
  *((_QWORD *)this + 50) = &CTPtrArray<IMFTransform,20>::`vftable';
  *((_QWORD *)this + 74) = 0;
  *((_DWORD *)this + 150) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 5;
  *((_DWORD *)this + 156) = -1;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 16);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1704));
  *((_DWORD *)this + 436) = 0;
  *((_DWORD *)this + 437) = 1;
  *((_DWORD *)this + 438) = 2;
  *((_QWORD *)this + 220) = 0;
  *((_QWORD *)this + 221) = 0;
  *((_DWORD *)this + 444) = 0;
  *((_DWORD *)this + 550) = 0;
  *((_QWORD *)this + 274) = 0;
  *((_QWORD *)this + 273) = 0;
  *((_QWORD *)this + 272) = 0;
  *((_QWORD *)this + 276) = 0;
  *((_QWORD *)this + 277) = 0;
  *((_DWORD *)this + 556) = 0;
  v8 = v52;
  *((_DWORD *)this + 662) = 0;
  *((_QWORD *)this + 330) = 0;
  *((_QWORD *)this + 329) = 0;
  Streams = *v8;
  *((_QWORD *)this + 328) = 0;
  *((_QWORD *)this + 332) = 0;
  *((_QWORD *)this + 333) = 0;
  *((_QWORD *)this + 334) = 0;
  *((_DWORD *)this + 670) = 0;
  *((_DWORD *)this + 776) = 0;
  *((_QWORD *)this + 387) = 0;
  *((_QWORD *)this + 386) = 0;
  *((_QWORD *)this + 385) = 0;
  *((_DWORD *)this + 778) = 0;
  *((_DWORD *)this + 779) = 1;
  *((_QWORD *)this + 393) = 0;
  *((_QWORD *)this + 394) = 0;
  *((_DWORD *)this + 790) = 0;
  *((_QWORD *)this + 390) = 0;
  *((_QWORD *)this + 391) = 0;
  *((_QWORD *)this + 413) = 0;
  *((_DWORD *)this + 828) = 0;
  *((_QWORD *)this + 415) = 0;
  *((_QWORD *)this + 416) = 1065353216;
  *((_QWORD *)this + 417) = 0;
  *((_QWORD *)this + 418) = 0;
  *((_QWORD *)this + 419) = 0;
  *((_QWORD *)this + 420) = 0;
  *((_QWORD *)this + 421) = 0;
  *((_DWORD *)this + 844) = 0;
  *(_QWORD *)((char *)this + 3380) = 1;
  *(_QWORD *)((char *)this + 3388) = 0;
  *(_QWORD *)((char *)this + 3396) = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v51, "CMFTWrapperAsync::CMFTWrapperAsync", 126);
  if ( Streams >= 0 )
  {
    if ( *v7 )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 0x20u )
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_054355ff8c893728e226c9db837ca8ed_Traceguids, this, *v7);
      ((void (__fastcall *)(struct IMFTransform *, GUID *, char *))(*v7)->lpVtbl->QueryInterface)(
        *v7,
        &GUID_fa993888_4383_415a_a930_dd472a8cf6f7,
        (char *)this + 160);
      ((void (__fastcall *)(struct IMFTransform *, GUID *, char *))(*v7)->lpVtbl->QueryInterface)(
        *v7,
        &GUID_03910848_ab16_4611_b100_17b88ae2f248,
        (char *)this + 168);
      if ( !*((_QWORD *)this + 21) )
        ((void (__fastcall *)(struct IMFTransform *, GUID *, char *))(*v7)->lpVtbl->QueryInterface)(
          *v7,
          &GUID_2347d60b_3fb5_480c_8803_8df3adcd3ef0,
          (char *)this + 176);
      v18 = *((_DWORD *)this + 438);
      *((_QWORD *)this + 328) = 0;
      if ( !*((_QWORD *)this + 277) )
      {
        *((_DWORD *)this + 556) = v18;
        v19 = 0;
        *((_QWORD *)this + 277) = (char *)this + 2232;
        *((_QWORD *)this + 279) = 0;
        do
        {
          v20 = v19 + 2 * v19 + 1;
          ++v19;
          v21 = *((_QWORD *)this + 277) + 8 * v20;
          *(_QWORD *)(v21 + 8) = *((_QWORD *)this + 276);
          *((_QWORD *)this + 276) = v21;
        }
        while ( v19 != 16 );
      }
      v22 = *((_DWORD *)this + 438);
      *((_QWORD *)this + 385) = 0;
      if ( !*((_QWORD *)this + 334) )
      {
        *((_DWORD *)this + 670) = v22;
        v23 = 0;
        *((_QWORD *)this + 334) = (char *)this + 2688;
        *((_QWORD *)this + 336) = 0;
        do
        {
          v24 = v23 + 2 * v23 + 1;
          ++v23;
          v25 = *((_QWORD *)this + 334) + 8 * v24;
          *(_QWORD *)(v25 + 8) = *((_QWORD *)this + 333);
          *((_QWORD *)this + 333) = v25;
        }
        while ( v23 != 16 );
      }
      *((_QWORD *)this + 272) = 0;
      if ( !*((_QWORD *)this + 221) )
      {
        *((_DWORD *)this + 444) = 1;
        *((_QWORD *)this + 221) = (char *)this + 1784;
        v26 = 0;
        *((_QWORD *)this + 223) = 0;
        do
        {
          v27 = v26 + 2 * v26 + 1;
          ++v26;
          v28 = *((_QWORD *)this + 221) + 8 * v27;
          *(_QWORD *)(v28 + 8) = *((_QWORD *)this + 220);
          *((_QWORD *)this + 220) = v28;
        }
        while ( v26 != 16 );
      }
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 79) = EventW;
      if ( EventW )
      {
        Streams = MFCreateEventQueue((IMFMediaEventQueue **)this + 76);
        if ( Streams >= 0 )
        {
          Streams = CMFTSampleAttributeHandler::Init((CMFTWrapperAsync *)((char *)this + 3112), *v7);
          if ( Streams >= 0 )
          {
            Streams = CMFTWrapperAsync::CreateStreams(this);
            if ( Streams >= 0 )
            {
              if ( (Microsoft_Windows_MFEnableBits & 0x40) != 0 )
                McTemplateU0pp_EventWriteTransfer(&Microsoft_Windows_MF_Context, &AsyncWrapper_Start, this, *v7);
              if ( (*((_BYTE *)this + 120) & 0x20) != 0 )
              {
                ComSmartPtr<IKsControl>::operator=((char *)this + 136, (char *)this + 128);
                v48 = (CPassthroughMFT *)operator new(0x50u);
                if ( v48 )
                  v49 = CPassthroughMFT::CPassthroughMFT(v48);
                else
                  v49 = 0;
                *((_QWORD *)this + 18) = v49;
              }
            }
            else
            {
              v45 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44);
                CallStackTracing::s_wpInstance = v46;
                if ( v46
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
                {
                  v45 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v45 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v45 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != Streams )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CMFTWrapperAsync::CMFTWrapperAsync",
                    163,
                    Streams);
              }
              if ( g_wppLevels )
              {
                v14 = 25;
                goto LABEL_9;
              }
            }
          }
          else
          {
            v40 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39);
              CallStackTracing::s_wpInstance = v41;
              if ( v41
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
              {
                v40 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v40 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v40 + 8) )
            {
              v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
              if ( *((_DWORD *)v42 + 499) != Streams )
                CallStackContext::TraceFailure(v42, "CMFTWrapperAsync::CMFTWrapperAsync", 158, Streams);
            }
            if ( g_wppLevels )
            {
              v14 = 24;
              goto LABEL_9;
            }
          }
        }
        else
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != Streams )
              CallStackContext::TraceFailure(v37, "CMFTWrapperAsync::CMFTWrapperAsync", 153, Streams);
          }
          if ( g_wppLevels )
          {
            v14 = 23;
            goto LABEL_9;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        Streams = LastError;
        if ( LastError > 0 )
          Streams = (unsigned __int16)LastError | 0x80070000;
        v31 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v31 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v31 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext(v31);
          if ( Streams < 0 && *((_DWORD *)v32 + 499) != Streams )
            CallStackContext::TraceFailure(v32, "CMFTWrapperAsync::CMFTWrapperAsync", 148, Streams);
        }
        if ( g_wppLevels )
        {
          v14 = 22;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      Streams = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v17, "CMFTWrapperAsync::CMFTWrapperAsync", 129, -2147024809);
      }
      if ( g_wppLevels )
      {
        v14 = 17;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v12 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v12 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(v12);
      if ( *((_DWORD *)v13 + 499) != Streams )
        CallStackContext::TraceFailure(v13, "CMFTWrapperAsync::CMFTWrapperAsync", 128, Streams);
    }
    if ( g_wppLevels )
    {
      v14 = 16;
LABEL_9:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_054355ff8c893728e226c9db837ca8ed_Traceguids,
        this,
        Streams);
    }
  }
  *v52 = Streams;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v51);
  return this;
}

```

## disassembly

```asm
0x1800a9778  mov     [rsp+arg_0], rbx
0x1800a977d  mov     [rsp+arg_18], r9
0x1800a9782  push    rbp
0x1800a9783  push    rsi
0x1800a9784  push    rdi
0x1800a9785  push    r12
0x1800a9787  push    r13
0x1800a9789  push    r14
0x1800a978b  push    r15
0x1800a978d  sub     rsp, 30h
0x1800a9791  mov     rdi, r8
0x1800a9794  mov     ebx, edx
0x1800a9796  mov     rsi, rcx
0x1800a9799  lock inc dword ptr cs:qword_1803CE158+4
0x1800a97a0  lea     rax, ??_7CMFTWrapperAsync@@6BIMFTransform@@@; const CMFTWrapperAsync::`vftable'{for `IMFTransform'}
0x1800a97a7  mov     [rcx], rax
0x1800a97aa  lea     rax, ??_7CMFTWrapperAsync@@6BIMFTransformWrapper@@@; const CMFTWrapperAsync::`vftable'{for `IMFTransformWrapper'}
0x1800a97b1  mov     [rcx+8], rax
0x1800a97b5  lea     rax, ??_7CMFTWrapperAsync@@6BIMFGetService@@@; const CMFTWrapperAsync::`vftable'{for `IMFGetService'}
0x1800a97bc  mov     [rcx+10h], rax
0x1800a97c0  lea     rax, ??_7CMFTWrapperAsync@@6BIMFMediaEventGenerator@@@; const CMFTWrapperAsync::`vftable'{for `IMFMediaEventGenerator'}
0x1800a97c7  mov     [rcx+18h], rax
0x1800a97cb  lea     rax, ??_7CMFTWrapperAsync@@6BIMFShutdown@@@; const CMFTWrapperAsync::`vftable'{for `IMFShutdown'}
0x1800a97d2  mov     [rcx+20h], rax
0x1800a97d6  lea     rax, ??_7CMFTWrapperAsync@@6BIMFRealTimeClient@@@; const CMFTWrapperAsync::`vftable'{for `IMFRealTimeClient'}
0x1800a97dd  mov     [rcx+28h], rax
0x1800a97e1  lea     rax, ??_7CMFTWrapperAsync@@6BIMFRealTimeClientEx@@@; const CMFTWrapperAsync::`vftable'{for `IMFRealTimeClientEx'}
0x1800a97e8  mov     [rcx+30h], rax
0x1800a97ec  lea     rax, ??_7CMFTWrapperAsync@@6BIMFRateControl@@@; const CMFTWrapperAsync::`vftable'{for `IMFRateControl'}
0x1800a97f3  mov     [rcx+38h], rax
0x1800a97f7  add     rcx, 40h ; '@'; this
0x1800a97fb  call    ??0ProcessingLoopAsyncCallback@CMFTWrapperAsync@@QEAA@XZ; CMFTWrapperAsync::ProcessingLoopAsyncCallback::ProcessingLoopAsyncCallback(void)
0x1800a9800  lea     rcx, [rsi+50h]; lpCriticalSection
0x1800a9804  mov     dword ptr [rsi+48h], 1
0x1800a980b  call    cs:__imp_InitializeCriticalSection
0x1800a9812  nop     dword ptr [rax+rax+00h]
0x1800a9817  lea     r14, [rsi+80h]
0x1800a981e  mov     [rsi+78h], ebx
0x1800a9821  mov     rcx, r14
0x1800a9824  mov     rdx, rdi
0x1800a9827  call    ??0?$ComSmartPtr@UIUnknown@@@@QEAA@PEAUIUnknown@@@Z; ComSmartPtr<IUnknown>::ComSmartPtr<IUnknown>(IUnknown *)
0x1800a982c  xor     edi, edi
0x1800a982e  lea     r13, [rsi+0A0h]
0x1800a9835  mov     [rsi+88h], rdi
0x1800a983c  lea     r15, [rsi+0A8h]
0x1800a9843  mov     [rsi+90h], rdi
0x1800a984a  lea     rbp, [rsi+0B0h]
0x1800a9851  mov     [rsi+98h], dil
0x1800a9858  lea     rcx, [rsi+0E0h]; void *
0x1800a985f  mov     [r13+0], rdi
0x1800a9863  xor     eax, eax
0x1800a9865  mov     [r15], rdi
0x1800a9868  mov     ebx, 0A0h
0x1800a986d  mov     [rbp+0], rdi
0x1800a9871  mov     r8d, ebx; Size
0x1800a9874  mov     [rsi+0B8h], rdi
0x1800a987b  xor     edx, edx; Val
0x1800a987d  mov     [rsi+0C8h], rdi
0x1800a9884  mov     [rsi+0D8h], ax
0x1800a988b  mov     [rsi+0DAh], al
0x1800a9891  call    memset_0
0x1800a9896  or      dword ptr [rsi+0CCh], 1
0x1800a989d  lea     rax, ??_7?$CTPtrArray@UIMFTransform@@$0BE@@@6B@; const CTPtrArray<IMFTransform,20>::`vftable'
0x1800a98a4  mov     [rsi+0C0h], rax
0x1800a98ab  lea     rcx, [rsi+1B0h]; void *
0x1800a98b2  mov     [rsi+180h], rdi
0x1800a98b9  xor     eax, eax
0x1800a98bb  mov     [rsi+188h], edi
0x1800a98c1  mov     r8d, ebx; Size
0x1800a98c4  mov     [rsi+0D0h], rdi
0x1800a98cb  xor     edx, edx; Val
0x1800a98cd  mov     [rsi+198h], rdi
0x1800a98d4  mov     [rsi+1A8h], ax
0x1800a98db  mov     [rsi+1AAh], al
0x1800a98e1  call    memset_0
0x1800a98e6  or      dword ptr [rsi+19Ch], 1
0x1800a98ed  lea     rax, ??_7?$CTPtrArray@UIMFTransform@@$0BE@@@6B@; const CTPtrArray<IMFTransform,20>::`vftable'
0x1800a98f4  mov     [rsi+190h], rax
0x1800a98fb  lea     rcx, [rsi+280h]; lpCriticalSection
0x1800a9902  mov     [rsi+250h], rdi
0x1800a9909  mov     [rsi+258h], edi
0x1800a990f  mov     [rsi+1A0h], rdi
0x1800a9916  mov     [rsi+260h], rdi
0x1800a991d  mov     qword ptr [rsi+268h], 5
0x1800a9928  mov     dword ptr [rsi+270h], 0FFFFFFFFh
0x1800a9932  call    cs:__imp_InitializeCriticalSection
0x1800a9939  nop     dword ptr [rax+rax+00h]
0x1800a993e  lea     rcx, [rsi+6A8h]; lpCriticalSection
0x1800a9945  call    cs:__imp_InitializeCriticalSection
0x1800a994c  nop     dword ptr [rax+rax+00h]
0x1800a9951  mov     [rsi+6D0h], edi
0x1800a9957  mov     dword ptr [rsi+6D4h], 1
0x1800a9961  mov     dword ptr [rsi+6D8h], 2
0x1800a996b  mov     [rsi+6E0h], rdi
0x1800a9972  mov     [rsi+6E8h], rdi
0x1800a9979  mov     [rsi+6F0h], edi
0x1800a997f  mov     [rsi+898h], edi
0x1800a9985  mov     [rsi+890h], rdi
0x1800a998c  mov     [rsi+888h], rdi
0x1800a9993  lea     r12, [rsi+0C28h]
0x1800a999a  mov     [rsi+880h], rdi
0x1800a99a1  lea     r8d, [rdi+7Eh]; int
0x1800a99a5  mov     [rsi+8A0h], rdi
0x1800a99ac  lea     rdx, aCmftwrapperasy_43; "CMFTWrapperAsync::CMFTWrapperAsync"
0x1800a99b3  mov     [rsi+8A8h], rdi
0x1800a99ba  lea     rcx, [rsp+68h+arg_8]; this
0x1800a99bf  mov     [rsi+8B0h], edi
0x1800a99c5  mov     rbx, [rsp+68h+arg_18]
0x1800a99cd  mov     [rsi+0A58h], edi
0x1800a99d3  mov     [rsi+0A50h], rdi
0x1800a99da  mov     [rsi+0A48h], rdi
0x1800a99e1  mov     ebx, [rbx]
0x1800a99e3  mov     [rsi+0A40h], rdi
0x1800a99ea  mov     [rsi+0A60h], rdi
0x1800a99f1  mov     [rsi+0A68h], rdi
0x1800a99f8  mov     [rsi+0A70h], rdi
0x1800a99ff  mov     [rsi+0A78h], edi
0x1800a9a05  mov     [rsi+0C20h], edi
0x1800a9a0b  mov     [rsi+0C18h], rdi
0x1800a9a12  mov     [rsi+0C10h], rdi
0x1800a9a19  mov     [rsi+0C08h], rdi
0x1800a9a20  mov     [r12], edi
0x1800a9a24  mov     dword ptr [r12+4], 1
0x1800a9a2d  mov     [r12+20h], rdi
0x1800a9a32  mov     [r12+28h], rdi
0x1800a9a37  mov     [r12+30h], edi
0x1800a9a3c  mov     [r12+8], rdi
0x1800a9a41  mov     [r12+10h], rdi
0x1800a9a46  mov     [r12+0C0h], rdi
0x1800a9a4e  mov     [rsi+0CF0h], edi
0x1800a9a54  mov     [rsi+0CF8h], rdi
0x1800a9a5b  mov     qword ptr [rsi+0D00h], 3F800000h
0x1800a9a66  mov     [rsi+0D08h], rdi
0x1800a9a6d  mov     [rsi+0D10h], rdi
0x1800a9a74  mov     [rsi+0D18h], rdi
0x1800a9a7b  mov     [rsi+0D20h], rdi
0x1800a9a82  mov     [rsi+0D28h], rdi
0x1800a9a89  mov     [rsi+0D30h], edi
0x1800a9a8f  mov     qword ptr [rsi+0D34h], 1
0x1800a9a9a  mov     [rsi+0D3Ch], rdi
0x1800a9aa1  mov     [rsi+0D44h], rdi
0x1800a9aa8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a9aad  test    ebx, ebx
0x1800a9aaf  jns     short loc_1800A9B29
0x1800a9ab1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9ab8  test    rcx, rcx
0x1800a9abb  jnz     short loc_1800A9AC9
0x1800a9abd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a9ac2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a9ac9  cmp     [rcx+8], dil
0x1800a9acd  jz      short loc_1800A9AF4
0x1800a9acf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9ad4  cmp     [rax+7CCh], ebx
0x1800a9ada  jz      short loc_1800A9AF4
0x1800a9adc  mov     r9d, ebx; int
0x1800a9adf  lea     rdx, aCmftwrapperasy_43; "CMFTWrapperAsync::CMFTWrapperAsync"
0x1800a9ae6  mov     r8d, 80h; int
0x1800a9aec  mov     rcx, rax; this
0x1800a9aef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9af4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9afb  jb      loc_1800AA06E
0x1800a9b01  mov     edx, 10h
0x1800a9b06  lea     r8, WPP_054355ff8c893728e226c9db837ca8ed_Traceguids
0x1800a9b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9b14  mov     r9, rsi
0x1800a9b17  mov     dword ptr [rsp+68h+var_48], ebx
0x1800a9b1b  mov     rcx, [rcx+10h]
0x1800a9b1f  call    WPP_SF_qD
0x1800a9b24  jmp     loc_1800AA06E
0x1800a9b29  mov     rax, [r14]
0x1800a9b2c  test    rax, rax
0x1800a9b2f  jnz     loc_1800A9BD0
0x1800a9b35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b3c  mov     ebx, 80070057h
0x1800a9b41  test    rcx, rcx
0x1800a9b44  jnz     short loc_1800A9B8E
0x1800a9b46  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9b4d  nop     dword ptr [rax+rax+00h]
0x1800a9b52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b59  mov     rcx, rax
0x1800a9b5c  test    rax, rax
0x1800a9b5f  jz      short loc_1800A9B80
0x1800a9b61  mov     rax, [rax]
0x1800a9b64  mov     edx, 7F0h
0x1800a9b69  mov     rax, [rax+8]
0x1800a9b6d  call    cs:__guard_dispatch_icall_fptr
0x1800a9b73  test    eax, eax
0x1800a9b75  jz      short loc_1800A9B80
0x1800a9b77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b7e  jmp     short loc_1800A9B8E
0x1800a9b80  lea     rcx, qword_1803CE250; this
0x1800a9b87  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b8e  cmp     [rcx+8], dil
0x1800a9b92  jz      short loc_1800A9BB9
0x1800a9b94  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9b99  cmp     [rax+7CCh], ebx
0x1800a9b9f  jz      short loc_1800A9BB9
0x1800a9ba1  mov     r9d, ebx; int
0x1800a9ba4  lea     rdx, aCmftwrapperasy_43; "CMFTWrapperAsync::CMFTWrapperAsync"
0x1800a9bab  mov     r8d, 81h; int
0x1800a9bb1  mov     rcx, rax; this
0x1800a9bb4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9bb9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9bc0  jb      loc_1800AA06E
0x1800a9bc6  mov     edx, 11h
0x1800a9bcb  jmp     loc_1800A9B06
0x1800a9bd0  cmp     cs:byte_1803CECE9, 20h ; ' '
0x1800a9bd7  lea     rdi, WPP_054355ff8c893728e226c9db837ca8ed_Traceguids
0x1800a9bde  jb      short loc_1800A9C00
0x1800a9be0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9be7  mov     edx, 12h
0x1800a9bec  mov     r9, rsi
0x1800a9bef  mov     [rsp+68h+var_48], rax
0x1800a9bf4  mov     r8, rdi
0x1800a9bf7  mov     rcx, [rcx+38h]
0x1800a9bfb  call    WPP_SF_qq
0x1800a9c00  mov     rcx, [r14]
0x1800a9c03  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x1800a9c0a  mov     r8, r13
0x1800a9c0d  mov     rax, [rcx]
0x1800a9c10  mov     rax, [rax]
0x1800a9c13  call    cs:__guard_dispatch_icall_fptr
0x1800a9c19  mov     rcx, [r14]
0x1800a9c1c  lea     rdx, _GUID_03910848_ab16_4611_b100_17b88ae2f248
0x1800a9c23  mov     r8, r15
0x1800a9c26  mov     rax, [rcx]
0x1800a9c29  mov     rax, [rax]
0x1800a9c2c  call    cs:__guard_dispatch_icall_fptr
0x1800a9c32  xor     r13d, r13d
0x1800a9c35  cmp     [r15], r13
0x1800a9c38  jnz     short loc_1800A9C53
0x1800a9c3a  mov     rcx, [r14]
0x1800a9c3d  lea     rdx, _GUID_2347d60b_3fb5_480c_8803_8df3adcd3ef0
0x1800a9c44  mov     r8, rbp
0x1800a9c47  mov     rax, [rcx]
0x1800a9c4a  mov     rax, [rax]
0x1800a9c4d  call    cs:__guard_dispatch_icall_fptr
0x1800a9c53  mov     eax, [rsi+6D8h]
0x1800a9c59  mov     [rsi+0A40h], r13
0x1800a9c60  cmp     [rsi+8A8h], r13
0x1800a9c67  jnz     short loc_1800A9CB4
0x1800a9c69  mov     [rsi+8B0h], eax
0x1800a9c6f  mov     r8, r13
0x1800a9c72  lea     rax, [rsi+8B8h]
0x1800a9c79  mov     [rsi+8A8h], rax
0x1800a9c80  mov     [rax], r13
0x1800a9c83  mov     rax, [rsi+8A8h]
0x1800a9c8a  lea     rdx, ds:1[r8*2]
0x1800a9c92  add     rdx, r8
0x1800a9c95  inc     r8
0x1800a9c98  lea     rdx, [rax+rdx*8]
0x1800a9c9c  mov     rax, [rsi+8A0h]
0x1800a9ca3  mov     [rdx+8], rax
0x1800a9ca7  mov     [rsi+8A0h], rdx
0x1800a9cae  cmp     r8, 10h
0x1800a9cb2  jnz     short loc_1800A9C83
0x1800a9cb4  mov     eax, [rsi+6D8h]
0x1800a9cba  mov     [rsi+0C08h], r13
0x1800a9cc1  cmp     [rsi+0A70h], r13
0x1800a9cc8  jnz     short loc_1800A9D15
0x1800a9cca  mov     [rsi+0A78h], eax
0x1800a9cd0  mov     r8, r13
0x1800a9cd3  lea     rax, [rsi+0A80h]
0x1800a9cda  mov     [rsi+0A70h], rax
0x1800a9ce1  mov     [rax], r13
0x1800a9ce4  mov     rax, [rsi+0A70h]
0x1800a9ceb  lea     rdx, ds:1[r8*2]
0x1800a9cf3  add     rdx, r8
0x1800a9cf6  inc     r8
0x1800a9cf9  lea     rdx, [rax+rdx*8]
0x1800a9cfd  mov     rax, [rsi+0A68h]
0x1800a9d04  mov     [rdx+8], rax
0x1800a9d08  mov     [rsi+0A68h], rdx
0x1800a9d0f  cmp     r8, 10h
0x1800a9d13  jnz     short loc_1800A9CE4
0x1800a9d15  mov     [rsi+880h], r13
0x1800a9d1c  cmp     [rsi+6E8h], r13
0x1800a9d23  jnz     short loc_1800A9D74
0x1800a9d25  lea     rax, [rsi+6F8h]
0x1800a9d2c  mov     dword ptr [rsi+6F0h], 1
0x1800a9d36  mov     [rsi+6E8h], rax
0x1800a9d3d  mov     r8, r13
0x1800a9d40  mov     [rax], r13
0x1800a9d43  mov     rax, [rsi+6E8h]
0x1800a9d4a  lea     rdx, ds:1[r8*2]
0x1800a9d52  add     rdx, r8
0x1800a9d55  inc     r8
0x1800a9d58  lea     rdx, [rax+rdx*8]
0x1800a9d5c  mov     rax, [rsi+6E0h]
0x1800a9d63  mov     [rdx+8], rax
0x1800a9d67  mov     [rsi+6E0h], rdx
0x1800a9d6e  cmp     r8, 10h
0x1800a9d72  jnz     short loc_1800A9D43
0x1800a9d74  xor     r9d, r9d; lpName
0x1800a9d77  xor     r8d, r8d; bInitialState
0x1800a9d7a  xor     edx, edx; bManualReset
0x1800a9d7c  xor     ecx, ecx; lpEventAttributes
0x1800a9d7e  call    cs:__imp_CreateEventW
0x1800a9d85  nop     dword ptr [rax+rax+00h]
0x1800a9d8a  mov     [rsi+278h], rax
  ... truncated ...
```
