# CMFMediaProcessorStream::OnSample(IMFSample *)

- ea: `0x18009b038`
- end: `0x18009b779`
- name: `?OnSample@CMFMediaProcessorStream@@QEAAJPEAUIMFSample@@@Z`
- size: `1857`
- prototype: `__int64 __fastcall(CMFMediaProcessorStream *__hidden this, struct IMFSample *)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x18009a370`

## callees

- `0x18001616c`
- `0x18001b9b0`
- `0x180039ad8`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x18006b388`
- `0x18009b038`
- `0x18009b780`
- `0x18009b9e0`
- `0x18009c830`
- `0x1800b9118`
- `0x1800de2a8`
- `0x1800ec0e0`
- `0x18014b764`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b3f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b3f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b389`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b07b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b11e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b2e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b07b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b11e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b2e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b5d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009b0a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009b14b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009b311`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009b0a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009b14b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009b311`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b08d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b130`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b2f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b08d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b130`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b2f6`
- `MFPlat!CreatePropVariant` at `0x18009b1b8`
- `MFPlat!CreatePropVariant` at `0x18009b1b8`
- `MFPlat!MFPutWorkItem` at `0x18009b2c4`
- `MFPlat!MFPutWorkItem` at `0x18009b2c4`
- `MFPlat!DestroyPropVariant` at `0x18009b286`
- `MFPlat!DestroyPropVariant` at `0x18009b286`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b625`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b6b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b625`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009b6b1`
- `MFPlat!MFCreateMediaEventResult` at `0x18009b3b3`
- `MFPlat!MFCreateMediaEventResult` at `0x18009b3b3`
- `MFPlat!MFCreateMediaEvent` at `0x18009b240`
- `MFPlat!MFCreateMediaEvent` at `0x18009b240`

## pseudocode

```c
__int64 __fastcall CMFMediaProcessorStream::OnSample(CMFMediaProcessorStream *this, struct IMFSample *a2)
{
  CallStackTracing *v4; // rbx
  char *v5; // rdi
  DWORD LastError; // r14d
  char *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  CallStackTracing *v10; // rbx
  char *v11; // rdi
  DWORD v12; // r15d
  char *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  HRESULT v20; // edi
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  CallStackTracing *v24; // rbx
  CallStackContext *v25; // rsi
  DWORD v26; // r14d
  CallStackContext *v27; // rax
  int v28; // edx
  int v29; // edx
  struct IMFMediaEvent *v31; // rdi
  unsigned int v32; // edx
  _QWORD *v33; // rax
  __int64 v34; // rdx
  const char *v35; // rax
  int v36; // edx
  int v37; // r8d
  CallStackTracing *v38; // rcx
  __int64 v39; // rax
  CallStackTracing *v40; // rcx
  __int64 v41; // rax
  CallStackTracing *v42; // rcx
  __int64 v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  struct IMFSample *v51; // [rsp+40h] [rbp-30h] BYREF
  __int64 v52; // [rsp+48h] [rbp-28h] BYREF
  PROPVARIANT pvValue[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v54; // [rsp+60h] [rbp-10h]
  int v55; // [rsp+B0h] [rbp+40h] BYREF
  int v56; // [rsp+C0h] [rbp+50h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+C8h] [rbp+58h] BYREF

  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v4 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v5 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v38 = CallStackTracing::s_wpInstance;
      }
      v39 = (**(__int64 (__fastcall ***)(CallStackTracing *))v38)(v38);
      if ( v39 )
        v5 = (char *)v39;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[8 * v9] = "CMFMediaProcessorStream::OnSample";
      *(_DWORD *)&v5[8 * v9 + 8] = 644;
    }
    ++*((_DWORD *)v5 + 497);
  }
  if ( *((_DWORD *)this + 4) )
  {
    v20 = 0;
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 39, &WPP_1b82ed3199523340553770a2714a1031_Traceguids, this);
  }
  else
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_qdqd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        40,
        &WPP_1b82ed3199523340553770a2714a1031_Traceguids,
        this,
        *((_DWORD *)this + 54),
        a2,
        0);
    v51 = a2;
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    v10 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v11 = (char *)CallStackTracing::s_wpInstance + 208;
      v12 = GetLastError();
      v13 = (char *)TlsGetValue(*((_DWORD *)v10 + 3));
      if ( v13 )
      {
        v11 = v13;
      }
      else if ( !GetLastError() )
      {
        v40 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v40 = CallStackTracing::s_wpInstance;
        }
        v41 = (**(__int64 (__fastcall ***)(CallStackTracing *))v40)(v40);
        if ( v41 )
          v11 = (char *)v41;
      }
      SetLastError(v12);
      v14 = *((unsigned int *)v11 + 497);
      if ( (unsigned int)v14 < *((_DWORD *)v11 + 498) )
      {
        v15 = 2 * v14;
        *(_QWORD *)&v11[8 * v15] = "CMFMediaEventGenerator::QueueEventWithIUnknown";
        *(_DWORD *)&v11[8 * v15 + 8] = 509;
      }
      ++*((_DWORD *)v11 + 497);
    }
    if ( *((_DWORD *)this + 34) )
    {
      v20 = -1072873851;
    }
    else if ( v51 )
    {
      v54 = 0;
      *(_OWORD *)pvValue = 0;
      CreatePropVariant(pvValue, 13, &v51, 8);
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v16 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v16);
        v18 = *((unsigned int *)ThreadRelativeContext + 497);
        if ( (unsigned int)v18 < *((_DWORD *)ThreadRelativeContext + 498) )
        {
          v19 = 2 * v18;
          *((_QWORD *)ThreadRelativeContext + v19) = "CMFMediaEventGenerator::QueueEvent";
          *((_DWORD *)ThreadRelativeContext + 2 * v19 + 2) = 366;
        }
        ++*((_DWORD *)ThreadRelativeContext + 497);
      }
      if ( (unsigned __int8)byte_1803CECEB >= 0x10u )
      {
        v35 = MFTRACE_STRING_FROM_MET(0xD5u);
        WPP_SF_qsL(*((_QWORD *)WPP_GLOBAL_Control + 17), v36, v37, (_DWORD)this + 88, (__int64)v35, 0);
      }
      if ( *((_DWORD *)this + 34) )
      {
        v20 = -1072873851;
      }
      else
      {
        ppEvent = 0;
        v20 = MFCreateMediaEvent(0xD5u, &GUID_00000000_0000_0000_0000_000000000000, 0, pvValue, &ppEvent);
        if ( v20 >= 0 )
        {
          v31 = ppEvent;
          v52 = 0;
          v55 = 0;
          v56 = 0;
          if ( ppEvent
            && ((int (__fastcall *)(IMFMediaEvent *, int *))ppEvent->lpVtbl->GetType)(ppEvent, &v55) >= 0
            && v55 == 1
            && ((int (__fastcall *)(struct IMFMediaEvent *, int *))v31->lpVtbl->GetStatus)(v31, &v56) >= 0 )
          {
            v44 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50);
              CallStackTracing::s_wpInstance = v45;
              if ( v45
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
              {
                v44 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v44 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v44 + 8) )
            {
              v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
              if ( v56 < 0 && *((_DWORD *)v46 + 499) != v56 )
                CallStackContext::TraceFailure(v46, "CMFMediaEventGenerator::QueueEvent", 458, v56);
            }
          }
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
          if ( *((_DWORD *)this + 34) )
          {
            v20 = -1072873851;
          }
          else
          {
            if ( (unsigned __int8)byte_1803CECEB >= 0x10u )
              MFTRACE_MEDIA_EVENT_IMPL(0x30001u, v32, v31);
            v20 = MFCreateMediaEventResult(v31, &v52);
            if ( v20 >= 0 )
            {
              v33 = (_QWORD *)*((_QWORD *)this + 20);
              v34 = v52 + 128;
              *(_QWORD *)(v52 + 128) = (char *)this + 152;
              *(_QWORD *)(v34 + 8) = v33;
              *v33 = v34;
              ++*((_DWORD *)this + 36);
              *((_QWORD *)this + 20) = v34;
              v20 = CMFMediaEventGenerator::CheckDispatchEvent((CMFMediaProcessorStream *)((char *)this + 88));
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
        }
        if ( ppEvent )
          ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
      }
      if ( (unsigned __int8)byte_1803CECEB >= 0x20u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          20,
          &WPP_5850d8474d1a3657fe88c51c9f643822_Traceguids,
          (char *)this + 88,
          v20);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v55);
      DestroyPropVariant(pvValue);
    }
    else
    {
      v20 = CMFMediaEventGenerator::QueueEvent(
              (CMFMediaProcessorStream *)((char *)this + 88),
              0xD5u,
              &GUID_00000000_0000_0000_0000_000000000000,
              0,
              0);
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v55);
    if ( v20 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v22, v21, v23);
        CallStackTracing::s_wpInstance = v47;
        if ( !v47 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v48 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v48 + 499) != v20 )
          CallStackContext::TraceFailure(v48, "CMFMediaProcessorStream::OnSample", 664, v20);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_1b82ed3199523340553770a2714a1031_Traceguids, this, v20);
    }
    else
    {
      CMFMediaProcessorStream::ResetProcessSamplePending(this);
      if ( *((_DWORD *)this + 166) )
        MFPutWorkItem(*((_DWORD *)this + 169), (IMFAsyncCallback *)this + 85, 0);
    }
  }
  v24 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v25 = (CallStackTracing *)((char *)CallStackTracing::s_wpInstance + 208);
    v26 = GetLastError();
    v27 = (CallStackContext *)TlsGetValue(*((_DWORD *)v24 + 3));
    if ( v27 )
    {
      v25 = v27;
    }
    else if ( !GetLastError() )
    {
      v42 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v42 = CallStackTracing::s_wpInstance;
      }
      v43 = (**(__int64 (__fastcall ***)(CallStackTracing *))v42)(v42);
      if ( v43 )
        v25 = (CallStackContext *)v43;
    }
    SetLastError(v26);
    v28 = *((_DWORD *)v25 + 497);
    if ( v28 )
    {
      v29 = v28 - 1;
      *((_DWORD *)v25 + 497) = v29;
      if ( !v29 )
        CallStackContext::ClearState(v25);
    }
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18009b038  push    rbp
0x18009b03a  push    rbx
0x18009b03b  push    rsi
0x18009b03c  push    rdi
0x18009b03d  push    r12
0x18009b03f  push    r14
0x18009b041  push    r15
0x18009b043  mov     rbp, rsp
0x18009b046  sub     rsp, 70h
0x18009b04a  xor     r12d, r12d
0x18009b04d  mov     r15, rdx
0x18009b050  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b057  mov     rsi, rcx
0x18009b05a  jz      loc_18009B528
0x18009b060  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b067  lea     rcx, aCmfmediaproces_43; "CMFMediaProcessorStream::OnSample"
0x18009b06e  cmp     [rbx+8], r12b
0x18009b072  jz      short loc_18009B0DE
0x18009b074  lea     rdi, [rbx+0D0h]
0x18009b07b  call    cs:__imp_GetLastError
0x18009b082  nop     dword ptr [rax+rax+00h]
0x18009b087  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18009b08a  mov     r14d, eax
0x18009b08d  call    cs:__imp_TlsGetValue
0x18009b094  nop     dword ptr [rax+rax+00h]
0x18009b099  test    rax, rax
0x18009b09c  jz      loc_18009B54D
0x18009b0a2  mov     rdi, rax
0x18009b0a5  mov     ecx, r14d; dwErrCode
0x18009b0a8  call    cs:__imp_SetLastError
0x18009b0af  nop     dword ptr [rax+rax+00h]
0x18009b0b4  mov     eax, [rdi+7C4h]
0x18009b0ba  lea     rcx, aCmfmediaproces_43; "CMFMediaProcessorStream::OnSample"
0x18009b0c1  cmp     eax, [rdi+7C8h]
0x18009b0c7  jnb     short loc_18009B0D8
0x18009b0c9  add     rax, rax
0x18009b0cc  mov     [rdi+rax*8], rcx
0x18009b0d0  mov     dword ptr [rdi+rax*8+8], 284h
0x18009b0d8  inc     dword ptr [rdi+7C4h]
0x18009b0de  cmp     [rsi+10h], r12d
0x18009b0e2  jnz     loc_18009B405
0x18009b0e8  cmp     cs:byte_1803CECE9, 10h
0x18009b0ef  jnb     loc_18009B4D4
0x18009b0f5  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b0fc  lea     r14, [rsi+58h]
0x18009b100  mov     [rbp+var_30], r15
0x18009b104  jz      loc_18009B532
0x18009b10a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b111  cmp     [rbx+8], r12b
0x18009b115  jz      short loc_18009B181
0x18009b117  lea     rdi, [rbx+0D0h]
0x18009b11e  call    cs:__imp_GetLastError
0x18009b125  nop     dword ptr [rax+rax+00h]
0x18009b12a  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18009b12d  mov     r15d, eax
0x18009b130  call    cs:__imp_TlsGetValue
0x18009b137  nop     dword ptr [rax+rax+00h]
0x18009b13c  test    rax, rax
0x18009b13f  jz      loc_18009B591
0x18009b145  mov     rdi, rax
0x18009b148  mov     ecx, r15d; dwErrCode
0x18009b14b  call    cs:__imp_SetLastError
0x18009b152  nop     dword ptr [rax+rax+00h]
0x18009b157  mov     eax, [rdi+7C4h]
0x18009b15d  cmp     eax, [rdi+7C8h]
0x18009b163  jnb     short loc_18009B17B
0x18009b165  add     rax, rax
0x18009b168  lea     rcx, aCmfmediaeventg_3; "CMFMediaEventGenerator::QueueEventWithI"...
0x18009b16f  mov     [rdi+rax*8], rcx
0x18009b173  mov     dword ptr [rdi+rax*8+8], 1FDh
0x18009b17b  inc     dword ptr [rdi+7C4h]
0x18009b181  lea     r15, qword_1803CE250
0x18009b188  cmp     [r14+30h], r12d
0x18009b18c  jnz     loc_18009B439
0x18009b192  cmp     [rbp+var_30], r12
0x18009b196  jz      loc_18009B44A
0x18009b19c  xor     eax, eax
0x18009b19e  lea     r8, [rbp+var_30]
0x18009b1a2  xorps   xmm0, xmm0
0x18009b1a5  mov     [rbp+var_10], rax
0x18009b1a9  lea     rcx, [rbp+pvValue]
0x18009b1ad  movups  xmmword ptr [rbp+pvValue], xmm0
0x18009b1b1  lea     edx, [rax+0Dh]
0x18009b1b4  lea     r9d, [rax+8]
0x18009b1b8  call    cs:__imp_CreatePropVariant
0x18009b1bf  nop     dword ptr [rax+rax+00h]
0x18009b1c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009b1cb  test    rcx, rcx
0x18009b1ce  jz      loc_18009B53C
0x18009b1d4  lea     rbx, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x18009b1db  cmp     [rcx+8], r12b
0x18009b1df  jz      short loc_18009B209
0x18009b1e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009b1e6  mov     ecx, [rax+7C4h]
0x18009b1ec  cmp     ecx, [rax+7C8h]
0x18009b1f2  jnb     short loc_18009B203
0x18009b1f4  add     rcx, rcx
0x18009b1f7  mov     [rax+rcx*8], rbx
0x18009b1fb  mov     dword ptr [rax+rcx*8+8], 16Eh
0x18009b203  inc     dword ptr [rax+7C4h]
0x18009b209  cmp     cs:byte_1803CECEB, 10h
0x18009b210  jnb     loc_18009B47A
0x18009b216  cmp     [r14+30h], r12d
0x18009b21a  jnz     loc_18009B50C
0x18009b220  lea     rax, [rbp+arg_18]
0x18009b224  mov     [rbp+arg_18], r12
0x18009b228  lea     r9, [rbp+pvValue]; pvValue
0x18009b22c  mov     [rsp+70h+ppEvent], rax; ppEvent
0x18009b231  xor     r8d, r8d; hrStatus
0x18009b234  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x18009b23b  mov     ecx, 0D5h; met
0x18009b240  call    cs:__imp_MFCreateMediaEvent
0x18009b247  nop     dword ptr [rax+rax+00h]
0x18009b24c  mov     edi, eax
0x18009b24e  test    eax, eax
0x18009b250  jns     loc_18009B348
0x18009b256  mov     rcx, [rbp+arg_18]
0x18009b25a  test    rcx, rcx
0x18009b25d  jz      short loc_18009B26C
0x18009b25f  mov     rax, [rcx]
0x18009b262  mov     rax, [rax+10h]
0x18009b266  call    cs:__guard_dispatch_icall_fptr
0x18009b26c  cmp     cs:byte_1803CECEB, 20h ; ' '
0x18009b273  jnb     loc_18009B4A9
0x18009b279  lea     rcx, [rbp+arg_0]; this
0x18009b27d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009b282  lea     rcx, [rbp+pvValue]
0x18009b286  call    cs:__imp_DestroyPropVariant
0x18009b28d  nop     dword ptr [rax+rax+00h]
0x18009b292  lea     rcx, [rbp+arg_0]; this
0x18009b296  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009b29b  test    edi, edi
0x18009b29d  js      loc_18009B6A8
0x18009b2a3  mov     rcx, rsi; this
0x18009b2a6  call    ?ResetProcessSamplePending@CMFMediaProcessorStream@@AEAAXXZ; CMFMediaProcessorStream::ResetProcessSamplePending(void)
0x18009b2ab  cmp     [rsi+298h], r12d
0x18009b2b2  jz      short loc_18009B2D0
0x18009b2b4  mov     ecx, [rsi+2A4h]; dwQueue
0x18009b2ba  lea     rdx, [rsi+2A8h]; pCallback
0x18009b2c1  xor     r8d, r8d; pState
0x18009b2c4  call    cs:__imp_MFPutWorkItem
0x18009b2cb  nop     dword ptr [rax+rax+00h]
0x18009b2d0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b2d7  cmp     [rbx+8], r12b
0x18009b2db  jz      short loc_18009B336
0x18009b2dd  lea     rsi, [rbx+0D0h]
0x18009b2e4  call    cs:__imp_GetLastError
0x18009b2eb  nop     dword ptr [rax+rax+00h]
0x18009b2f0  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18009b2f3  mov     r14d, eax
0x18009b2f6  call    cs:__imp_TlsGetValue
0x18009b2fd  nop     dword ptr [rax+rax+00h]
0x18009b302  test    rax, rax
0x18009b305  jz      loc_18009B5D5
0x18009b30b  mov     rsi, rax
0x18009b30e  mov     ecx, r14d; dwErrCode
0x18009b311  call    cs:__imp_SetLastError
0x18009b318  nop     dword ptr [rax+rax+00h]
0x18009b31d  mov     edx, [rsi+7C4h]
0x18009b323  test    edx, edx
0x18009b325  jz      short loc_18009B336
0x18009b327  sub     edx, 1
0x18009b32a  mov     [rsi+7C4h], edx
0x18009b330  jz      loc_18009B46D
0x18009b336  mov     eax, edi
0x18009b338  add     rsp, 70h
0x18009b33c  pop     r15
0x18009b33e  pop     r14
0x18009b340  pop     r12
0x18009b342  pop     rdi
0x18009b343  pop     rsi
0x18009b344  pop     rbx
0x18009b345  pop     rbp
0x18009b346  retn
0x18009b348  mov     rdi, [rbp+arg_18]
0x18009b34c  mov     [rbp+var_28], r12
0x18009b350  mov     [rbp+arg_0], r12d
0x18009b354  mov     [rbp+arg_10], r12d
0x18009b358  test    rdi, rdi
0x18009b35b  jz      short loc_18009B382
0x18009b35d  mov     rax, [rdi]
0x18009b360  lea     rdx, [rbp+arg_0]
0x18009b364  mov     rcx, rdi
0x18009b367  mov     rax, [rax+108h]
0x18009b36e  call    cs:__guard_dispatch_icall_fptr
0x18009b374  test    eax, eax
0x18009b376  js      short loc_18009B382
0x18009b378  cmp     [rbp+arg_0], 1
0x18009b37c  jz      loc_18009B755
0x18009b382  lea     rbx, [r14+8]
0x18009b386  mov     rcx, rbx; lpCriticalSection
0x18009b389  call    cs:__imp_EnterCriticalSection
0x18009b390  nop     dword ptr [rax+rax+00h]
0x18009b395  cmp     [r14+30h], r12d
0x18009b399  jnz     loc_18009B443
0x18009b39f  cmp     cs:byte_1803CECEB, 10h
0x18009b3a6  jnb     loc_18009B516
0x18009b3ac  lea     rdx, [rbp+var_28]
0x18009b3b0  mov     rcx, rdi
0x18009b3b3  call    cs:__imp_MFCreateMediaEventResult
0x18009b3ba  nop     dword ptr [rax+rax+00h]
0x18009b3bf  mov     edi, eax
0x18009b3c1  test    eax, eax
0x18009b3c3  js      short loc_18009B3F1
0x18009b3c5  mov     rdx, [rbp+var_28]
0x18009b3c9  lea     rcx, [r14+40h]
0x18009b3cd  mov     rax, [rcx+8]
0x18009b3d1  sub     rdx, 0FFFFFFFFFFFFFF80h
0x18009b3d5  mov     [rdx], rcx
0x18009b3d8  mov     [rdx+8], rax
0x18009b3dc  mov     [rax], rdx
0x18009b3df  inc     dword ptr [r14+38h]
0x18009b3e3  mov     [rcx+8], rdx
0x18009b3e7  mov     rcx, r14; this
0x18009b3ea  call    ?CheckDispatchEvent@CMFMediaEventGenerator@@IEAAJXZ; CMFMediaEventGenerator::CheckDispatchEvent(void)
0x18009b3ef  mov     edi, eax
0x18009b3f1  mov     rcx, rbx; lpCriticalSection
0x18009b3f4  call    cs:__imp_LeaveCriticalSection
0x18009b3fb  nop     dword ptr [rax+rax+00h]
0x18009b400  jmp     loc_18009B256
0x18009b405  mov     edi, r12d
0x18009b408  cmp     cs:byte_1803CECE9, 8
0x18009b40f  jb      loc_18009B2D0
0x18009b415  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b41c  lea     r8, WPP_1b82ed3199523340553770a2714a1031_Traceguids
0x18009b423  mov     edx, 27h ; '''
0x18009b428  mov     r9, rsi
0x18009b42b  mov     rcx, [rcx+38h]
0x18009b42f  call    WPP_SF_q
0x18009b434  jmp     loc_18009B2D0
0x18009b439  mov     edi, 0C00D3E85h
0x18009b43e  jmp     loc_18009B292
0x18009b443  mov     edi, 0C00D3E85h
0x18009b448  jmp     short loc_18009B3F1
0x18009b44a  xor     r9d, r9d; hrStatus
0x18009b44d  mov     [rsp+70h+ppEvent], r12; pvValue
0x18009b452  lea     r8, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x18009b459  mov     edx, 0D5h; unsigned int
0x18009b45e  mov     rcx, r14; this
0x18009b461  call    ?QueueEvent@CMFMediaEventGenerator@@QEAAJKAEBU_GUID@@JPEBUtagPROPVARIANT@@@Z; CMFMediaEventGenerator::QueueEvent(ulong,_GUID const &,long,tagPROPVARIANT const *)
0x18009b466  mov     edi, eax
0x18009b468  jmp     loc_18009B292
0x18009b46d  mov     rcx, rsi; this
0x18009b470  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x18009b475  jmp     loc_18009B336
0x18009b47a  mov     ecx, 0D5h; unsigned int
0x18009b47f  call    ?MFTRACE_STRING_FROM_MET@@YAPEBDK@Z; MFTRACE_STRING_FROM_MET(ulong)
0x18009b484  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b48b  mov     r9, r14
0x18009b48e  mov     dword ptr [rsp+70h+var_48], r12d
0x18009b493  mov     [rsp+70h+ppEvent], rax
0x18009b498  mov     rcx, [rcx+88h]
0x18009b49f  call    WPP_SF_qsL
0x18009b4a4  jmp     loc_18009B216
0x18009b4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b4b0  lea     r8, WPP_5850d8474d1a3657fe88c51c9f643822_Traceguids
0x18009b4b7  mov     edx, 14h
0x18009b4bc  mov     dword ptr [rsp+70h+ppEvent], edi
0x18009b4c0  mov     r9, r14
0x18009b4c3  mov     rcx, [rcx+88h]
0x18009b4ca  call    WPP_SF_qD
0x18009b4cf  jmp     loc_18009B279
0x18009b4d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b4db  lea     r8, WPP_1b82ed3199523340553770a2714a1031_Traceguids
0x18009b4e2  mov     eax, [rsi+0D8h]
0x18009b4e8  mov     edx, 28h ; '('
0x18009b4ed  mov     [rsp+70h+var_40], r12d
0x18009b4f2  mov     r9, rsi
0x18009b4f5  mov     [rsp+70h+var_48], r15
0x18009b4fa  mov     rcx, [rcx+38h]
0x18009b4fe  mov     dword ptr [rsp+70h+ppEvent], eax
0x18009b502  call    WPP_SF_qdqd
0x18009b507  jmp     loc_18009B0F5
0x18009b50c  mov     edi, 0C00D3E85h
0x18009b511  jmp     loc_18009B26C
0x18009b516  mov     r8, rdi; struct IMFMediaEvent *
0x18009b519  mov     ecx, 30001h; unsigned int
0x18009b51e  call    ?MFTRACE_MEDIA_EVENT_IMPL@@YAXKKPEAUIMFMediaEvent@@@Z; MFTRACE_MEDIA_EVENT_IMPL(ulong,ulong,IMFMediaEvent *)
0x18009b523  jmp     loc_18009B3AC
0x18009b528  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18009b52d  jmp     loc_18009B060
0x18009b532  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18009b537  jmp     loc_18009B10A
0x18009b53c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18009b541  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b548  jmp     loc_18009B1D4
0x18009b54d  call    cs:__imp_GetLastError
0x18009b554  nop     dword ptr [rax+rax+00h]
0x18009b559  test    eax, eax
0x18009b55b  jnz     loc_18009B0A5
0x18009b561  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b568  test    rcx, rcx
0x18009b56b  jnz     short loc_18009B579
0x18009b56d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18009b572  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009b579  mov     rax, [rcx]
0x18009b57c  mov     rax, [rax]
0x18009b57f  call    cs:__guard_dispatch_icall_fptr
0x18009b585  test    rax, rax
0x18009b588  cmovnz  rdi, rax
  ... truncated ...
```
