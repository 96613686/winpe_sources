# CAudStreamSink::InvokePipelineFormatChange(int)

- ea: `0x18014d690`
- end: `0x18014dd98`
- name: `?InvokePipelineFormatChange@CAudStreamSink@@IEAAJH@Z`
- size: `1800`
- prototype: `__int64 __fastcall(CAudStreamSink *__hidden this, int)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18031941c`

## callees

- `0x18000f278`
- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180045dbc`
- `0x180050d6c`
- `0x18006b388`
- `0x180082f10`
- `0x18008352c`
- `0x18009b9e0`
- `0x1800ec0e0`
- `0x180146394`
- `0x18014d690`
- `0x180189368`
- `0x18018bbd0`
- `0x1801ad254`
- `0x180258480`
- `0x18031d290`
- `0x18031e48c`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014d8ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014d9b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014d8ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014d9b0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18014d78d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18014d78d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014d856`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014d920`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014d9ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014dab0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014db75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014dc75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014d856`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014d920`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014d9ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014dab0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014db75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014dc75`

## string_xrefs

- `0x18014d6c6`: `CAudStreamSink::InvokePipelineFormatChange`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::InvokePipelineFormatChange(CAudStreamSink *this, const unsigned __int16 *a2)
{
  int v3; // ebp
  __int64 v4; // r9
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  int ActivationFactory; // eax
  int DestinationFormat; // ebx
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  int v19; // r9d
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  int v25; // r9d
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rcx
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
  struct CallStackContext *v47; // rax
  _BYTE v49[8]; // [rsp+30h] [rbp-88h] BYREF
  __int64 v50; // [rsp+38h] [rbp-80h] BYREF
  _BYTE v51[16]; // [rsp+40h] [rbp-78h] BYREF
  HSTRING string; // [rsp+50h] [rbp-68h] BYREF

  v50 = 0;
  v3 = (int)a2;
  Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[44])a2);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v49,
    "CAudStreamSink::InvokePipelineFormatChange",
    7596);
  v5 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 825) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 825) + 296LL))(*((_QWORD *)this + 825));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 825) + 280LL))(
                      *((_QWORD *)this + 825),
                      v51);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pd_EventWriteTransfer(v5, &AudStreamSink_InvokePipelineFormatChange_Enter, this, 1);
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 0x10) != 0 )
    McTemplateU0t_EventWriteTransfer(v5, &Audio_Renderer_DynamicFormatChange, 1, v4);
  ActivationFactory = RoGetActivationFactory(string, &GUID_6a633961_dbed_464c_a09a_33412f5caa3f, &v50);
  DestinationFormat = ActivationFactory;
  if ( ActivationFactory != -2147221164 )
  {
    if ( ActivationFactory < 0 )
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v11 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext(v11);
        if ( *((_DWORD *)v12 + 499) != DestinationFormat )
          CallStackContext::TraceFailure(v12, "CAudStreamSink::InvokePipelineFormatChange", 7621, DestinationFormat);
      }
      if ( g_wppLevels )
      {
        v13 = 491;
LABEL_17:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          this,
          DestinationFormat);
        goto LABEL_100;
      }
      goto LABEL_100;
    }
    if ( *((_QWORD *)this + 815) )
    {
      DestinationFormat = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 64LL))(v50);
      if ( DestinationFormat < 0 )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != DestinationFormat )
            CallStackContext::TraceFailure(v18, "CAudStreamSink::InvokePipelineFormatChange", 7627, DestinationFormat);
        }
        if ( g_wppLevels )
        {
          v13 = 492;
          goto LABEL_17;
        }
        goto LABEL_100;
      }
      *((_QWORD *)this + 815) = 0;
    }
  }
  CoTaskMemFree(*((LPVOID *)this + 103));
  *((_QWORD *)this + 103) = 0;
  DestinationFormat = CAudStreamSink::GetDestinationFormat(this, (struct tWAVEFORMATEX **)this + 103, 0, v19);
  if ( DestinationFormat >= 0 )
  {
    CoTaskMemFree(*((LPVOID *)this + 104));
    *((_QWORD *)this + 104) = 0;
    v26 = CAudStreamSink::GetDestinationFormat(this, (struct tWAVEFORMATEX **)this + 104, 1, v25);
    DestinationFormat = 0;
    if ( v26 != -2004287454 )
      DestinationFormat = v26;
    if ( DestinationFormat >= 0 )
    {
      v32 = *((_QWORD *)this + 101);
      if ( v32 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        *((_QWORD *)this + 101) = 0;
      }
      DestinationFormat = CAudStreamSink::InitializeMediaTypeHandlerList(this);
      if ( DestinationFormat >= 0 )
      {
        if ( !v3 )
        {
          if ( *((_DWORD *)this + 87) == 1 && !*((_DWORD *)this + 1798) )
          {
            DestinationFormat = CAudStreamSink::SignalStreamPrerolled(this);
            if ( DestinationFormat < 0 )
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
                if ( *((_DWORD *)v42 + 499) != DestinationFormat )
                  CallStackContext::TraceFailure(
                    v42,
                    "CAudStreamSink::InvokePipelineFormatChange",
                    7664,
                    DestinationFormat);
              }
              if ( g_wppLevels )
              {
                v13 = 496;
                goto LABEL_17;
              }
              goto LABEL_100;
            }
          }
          if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
            McTemplateU0p_EventWriteTransfer(
              &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
              &AudStreamSink_InvokePipelineFormatChange_QueueMEStreamSinkFormatInvalidated,
              this);
          if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 497, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
          DestinationFormat = CMFMediaEventGenerator::QueueEvent(
                                (CAudStreamSink *)((char *)this + 104),
                                0x322u,
                                &GUID_00000000_0000_0000_0000_000000000000,
                                0,
                                0);
          if ( DestinationFormat < 0 )
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
              v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
              if ( *((_DWORD *)v47 + 499) != DestinationFormat )
                CallStackContext::TraceFailure(
                  v47,
                  "CAudStreamSink::InvokePipelineFormatChange",
                  7677,
                  DestinationFormat);
            }
            if ( g_wppLevels )
            {
              v13 = 498;
              goto LABEL_17;
            }
            goto LABEL_100;
          }
        }
        *((_DWORD *)this + 64) = 1;
        if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
          McTemplateU0p_EventWriteTransfer(
            &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
            &AudStreamSink_SetStreamInvalidating_On,
            this);
        *((_QWORD *)this + 635) = 0;
        CAudStreamSink::EnableSampleRequests(this, 1);
        CAudStreamSink::RequestMoreSamples(this);
        goto LABEL_100;
      }
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
        if ( *((_DWORD *)v37 + 499) != DestinationFormat )
          CallStackContext::TraceFailure(v37, "CAudStreamSink::InvokePipelineFormatChange", 7657, DestinationFormat);
      }
      if ( g_wppLevels )
      {
        v13 = 495;
        goto LABEL_17;
      }
    }
    else
    {
      v29 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != DestinationFormat )
          CallStackContext::TraceFailure(v31, "CAudStreamSink::InvokePipelineFormatChange", 7648, DestinationFormat);
      }
      if ( g_wppLevels )
      {
        v13 = 494;
        goto LABEL_17;
      }
    }
  }
  else
  {
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)v24 + 499) != DestinationFormat )
        CallStackContext::TraceFailure(v24, "CAudStreamSink::InvokePipelineFormatChange", 7636, DestinationFormat);
    }
    if ( g_wppLevels )
    {
      v13 = 493;
      goto LABEL_17;
    }
  }
LABEL_100:
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudStreamSink_InvokePipelineFormatChange_Exit,
      this,
      (unsigned int)DestinationFormat);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v49);
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  return (unsigned int)DestinationFormat;
}

```

## disassembly

```asm
0x18014d690  push    rbx
0x18014d692  push    rbp
0x18014d693  push    rsi
0x18014d694  push    rdi
0x18014d695  push    r14
0x18014d697  push    r15
0x18014d699  sub     rsp, 88h
0x18014d6a0  mov     rax, cs:__security_cookie
0x18014d6a7  xor     rax, rsp
0x18014d6aa  mov     [rsp+0B8h+var_48], rax
0x18014d6af  mov     rsi, rcx
0x18014d6b2  xor     r14d, r14d
0x18014d6b5  lea     rcx, [rsp+0B8h+string]; string
0x18014d6ba  mov     [rsp+0B8h+var_80], r14
0x18014d6bf  mov     ebp, edx
0x18014d6c1  call    ??$?0$0CM@@StringReference@Internal@Windows@@QEAA@AEAY0CM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[44])
0x18014d6c6  lea     r15, aCaudstreamsink_72; "CAudStreamSink::InvokePipelineFormatCha"...
0x18014d6cd  mov     r8d, 1DACh; int
0x18014d6d3  mov     rdx, r15; char *
0x18014d6d6  lea     rcx, [rsp+0B8h+var_88]; this
0x18014d6db  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18014d6e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18014d6e7  cmp     [rcx+8], r14b
0x18014d6eb  jz      short loc_18014D744
0x18014d6ed  cmp     [rsi+19C8h], r14
0x18014d6f4  jz      short loc_18014D744
0x18014d6f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014d6fb  mov     rcx, [rsi+19C8h]
0x18014d702  mov     rdi, rax
0x18014d705  mov     rdx, [rcx]
0x18014d708  mov     rax, [rdx+128h]
0x18014d70f  call    cs:__guard_dispatch_icall_fptr
0x18014d715  mov     rcx, [rsi+19C8h]
0x18014d71c  mov     ebx, eax
0x18014d71e  mov     rdx, [rcx]
0x18014d721  mov     rax, [rdx+118h]
0x18014d728  lea     rdx, [rsp+0B8h+var_78]
0x18014d72d  call    cs:__guard_dispatch_icall_fptr
0x18014d733  movups  xmm0, xmmword ptr [rax]
0x18014d736  mov     [rdi+7E0h], ebx
0x18014d73c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18014d744  mov     edi, 1
0x18014d749  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, dil
0x18014d750  jz      short loc_18014D764
0x18014d752  mov     r9d, edi
0x18014d755  lea     rdx, AudStreamSink_InvokePipelineFormatChange_Enter
0x18014d75c  mov     r8, rsi
0x18014d75f  call    McTemplateU0pd_EventWriteTransfer
0x18014d764  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 10h
0x18014d76b  jz      short loc_18014D77C
0x18014d76d  mov     r8d, edi
0x18014d770  lea     rdx, Audio_Renderer_DynamicFormatChange
0x18014d777  call    McTemplateU0t_EventWriteTransfer
0x18014d77c  mov     rcx, [rsp+0B8h+string]
0x18014d781  lea     r8, [rsp+0B8h+var_80]
0x18014d786  lea     rdx, _GUID_6a633961_dbed_464c_a09a_33412f5caa3f
0x18014d78d  call    cs:__imp_RoGetActivationFactory
0x18014d794  nop     dword ptr [rax+rax+00h]
0x18014d799  mov     ebx, eax
0x18014d79b  cmp     eax, 80040154h
0x18014d7a0  jz      loc_18014D8E3
0x18014d7a6  test    eax, eax
0x18014d7a8  jns     short loc_18014D81E
0x18014d7aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d7b1  test    rcx, rcx
0x18014d7b4  jnz     short loc_18014D7C2
0x18014d7b6  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18014d7bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18014d7c2  cmp     [rcx+8], r14b
0x18014d7c6  jz      short loc_18014D7E9
0x18014d7c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014d7cd  cmp     [rax+7CCh], ebx
0x18014d7d3  jz      short loc_18014D7E9
0x18014d7d5  mov     r9d, ebx; int
0x18014d7d8  mov     r8d, 1DC5h; int
0x18014d7de  mov     rdx, r15; char *
0x18014d7e1  mov     rcx, rax; this
0x18014d7e4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014d7e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18014d7f0  jb      loc_18014DD35
0x18014d7f6  mov     edx, 1EBh
0x18014d7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18014d802  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x18014d809  mov     r9, rsi
0x18014d80c  mov     dword ptr [rsp+0B8h+pvValue], ebx
0x18014d810  mov     rcx, [rcx+10h]
0x18014d814  call    WPP_SF_qD
0x18014d819  jmp     loc_18014DD35
0x18014d81e  mov     rdx, [rsi+1978h]
0x18014d825  test    rdx, rdx
0x18014d828  jz      loc_18014D8E3
0x18014d82e  mov     rcx, [rsp+0B8h+var_80]
0x18014d833  mov     rax, [rcx]
0x18014d836  mov     rax, [rax+40h]
0x18014d83a  call    cs:__guard_dispatch_icall_fptr
0x18014d840  mov     ebx, eax
0x18014d842  test    eax, eax
0x18014d844  jns     loc_18014D8DC
0x18014d84a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d851  test    rcx, rcx
0x18014d854  jnz     short loc_18014D89E
0x18014d856  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014d85d  nop     dword ptr [rax+rax+00h]
0x18014d862  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d869  mov     rcx, rax
0x18014d86c  test    rax, rax
0x18014d86f  jz      short loc_18014D890
0x18014d871  mov     rax, [rax]
0x18014d874  mov     edx, 7F0h
0x18014d879  mov     rax, [rax+8]
0x18014d87d  call    cs:__guard_dispatch_icall_fptr
0x18014d883  test    eax, eax
0x18014d885  jz      short loc_18014D890
0x18014d887  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d88e  jmp     short loc_18014D89E
0x18014d890  lea     rcx, qword_1803CE250; this
0x18014d897  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d89e  cmp     [rcx+8], r14b
0x18014d8a2  jz      short loc_18014D8C5
0x18014d8a4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014d8a9  cmp     [rax+7CCh], ebx
0x18014d8af  jz      short loc_18014D8C5
0x18014d8b1  mov     r9d, ebx; int
0x18014d8b4  mov     r8d, 1DCBh; int
0x18014d8ba  mov     rdx, r15; char *
0x18014d8bd  mov     rcx, rax; this
0x18014d8c0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014d8c5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18014d8cc  jb      loc_18014DD35
0x18014d8d2  mov     edx, 1ECh
0x18014d8d7  jmp     loc_18014D7FB
0x18014d8dc  mov     [rsi+1978h], r14
0x18014d8e3  lea     rbx, [rsi+338h]
0x18014d8ea  mov     rcx, [rbx]; pv
0x18014d8ed  call    cs:__imp_CoTaskMemFree
0x18014d8f4  nop     dword ptr [rax+rax+00h]
0x18014d8f9  xor     r8d, r8d; int
0x18014d8fc  mov     [rbx], r14
0x18014d8ff  mov     rdx, rbx; struct tWAVEFORMATEX **
0x18014d902  mov     rcx, rsi; this
0x18014d905  call    ?GetDestinationFormat@CAudStreamSink@@IEAAJPEAPEAUtWAVEFORMATEX@@HH@Z; CAudStreamSink::GetDestinationFormat(tWAVEFORMATEX * *,int,int)
0x18014d90a  mov     ebx, eax
0x18014d90c  test    eax, eax
0x18014d90e  jns     loc_18014D9A6
0x18014d914  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d91b  test    rcx, rcx
0x18014d91e  jnz     short loc_18014D968
0x18014d920  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014d927  nop     dword ptr [rax+rax+00h]
0x18014d92c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d933  mov     rcx, rax
0x18014d936  test    rax, rax
0x18014d939  jz      short loc_18014D95A
0x18014d93b  mov     rax, [rax]
0x18014d93e  mov     edx, 7F0h
0x18014d943  mov     rax, [rax+8]
0x18014d947  call    cs:__guard_dispatch_icall_fptr
0x18014d94d  test    eax, eax
0x18014d94f  jz      short loc_18014D95A
0x18014d951  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d958  jmp     short loc_18014D968
0x18014d95a  lea     rcx, qword_1803CE250; this
0x18014d961  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d968  cmp     [rcx+8], r14b
0x18014d96c  jz      short loc_18014D98F
0x18014d96e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014d973  cmp     [rax+7CCh], ebx
0x18014d979  jz      short loc_18014D98F
0x18014d97b  mov     r9d, ebx; int
0x18014d97e  mov     r8d, 1DD4h; int
0x18014d984  mov     rdx, r15; char *
0x18014d987  mov     rcx, rax; this
0x18014d98a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014d98f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18014d996  jb      loc_18014DD35
0x18014d99c  mov     edx, 1EDh
0x18014d9a1  jmp     loc_18014D7FB
0x18014d9a6  lea     rbx, [rsi+340h]
0x18014d9ad  mov     rcx, [rbx]; pv
0x18014d9b0  call    cs:__imp_CoTaskMemFree
0x18014d9b7  nop     dword ptr [rax+rax+00h]
0x18014d9bc  mov     r8d, edi; int
0x18014d9bf  mov     [rbx], r14
0x18014d9c2  mov     rdx, rbx; struct tWAVEFORMATEX **
0x18014d9c5  mov     rcx, rsi; this
0x18014d9c8  call    ?GetDestinationFormat@CAudStreamSink@@IEAAJPEAPEAUtWAVEFORMATEX@@HH@Z; CAudStreamSink::GetDestinationFormat(tWAVEFORMATEX * *,int,int)
0x18014d9cd  cmp     eax, 88890022h
0x18014d9d2  mov     ebx, r14d
0x18014d9d5  cmovnz  ebx, eax
0x18014d9d8  test    ebx, ebx
0x18014d9da  jns     loc_18014DA72
0x18014d9e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d9e7  test    rcx, rcx
0x18014d9ea  jnz     short loc_18014DA34
0x18014d9ec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014d9f3  nop     dword ptr [rax+rax+00h]
0x18014d9f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d9ff  mov     rcx, rax
0x18014da02  test    rax, rax
0x18014da05  jz      short loc_18014DA26
0x18014da07  mov     rax, [rax]
0x18014da0a  mov     edx, 7F0h
0x18014da0f  mov     rax, [rax+8]
0x18014da13  call    cs:__guard_dispatch_icall_fptr
0x18014da19  test    eax, eax
0x18014da1b  jz      short loc_18014DA26
0x18014da1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014da24  jmp     short loc_18014DA34
0x18014da26  lea     rcx, qword_1803CE250; this
0x18014da2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014da34  cmp     [rcx+8], r14b
0x18014da38  jz      short loc_18014DA5B
0x18014da3a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014da3f  cmp     [rax+7CCh], ebx
0x18014da45  jz      short loc_18014DA5B
0x18014da47  mov     r9d, ebx; int
0x18014da4a  mov     r8d, 1DE0h; int
0x18014da50  mov     rdx, r15; char *
0x18014da53  mov     rcx, rax; this
0x18014da56  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014da5b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18014da62  jb      loc_18014DD35
0x18014da68  mov     edx, 1EEh
0x18014da6d  jmp     loc_18014D7FB
0x18014da72  mov     rcx, [rsi+328h]
0x18014da79  test    rcx, rcx
0x18014da7c  jz      short loc_18014DA92
0x18014da7e  mov     rax, [rcx]
0x18014da81  mov     rax, [rax+10h]
0x18014da85  call    cs:__guard_dispatch_icall_fptr
0x18014da8b  mov     [rsi+328h], r14
0x18014da92  mov     rcx, rsi; this
0x18014da95  call    ?InitializeMediaTypeHandlerList@CAudStreamSink@@IEAAJXZ; CAudStreamSink::InitializeMediaTypeHandlerList(void)
0x18014da9a  mov     ebx, eax
0x18014da9c  test    eax, eax
0x18014da9e  jns     loc_18014DB36
0x18014daa4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014daab  test    rcx, rcx
0x18014daae  jnz     short loc_18014DAF8
0x18014dab0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014dab7  nop     dword ptr [rax+rax+00h]
0x18014dabc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014dac3  mov     rcx, rax
0x18014dac6  test    rax, rax
0x18014dac9  jz      short loc_18014DAEA
0x18014dacb  mov     rax, [rax]
0x18014dace  mov     edx, 7F0h
0x18014dad3  mov     rax, [rax+8]
0x18014dad7  call    cs:__guard_dispatch_icall_fptr
0x18014dadd  test    eax, eax
0x18014dadf  jz      short loc_18014DAEA
0x18014dae1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014dae8  jmp     short loc_18014DAF8
0x18014daea  lea     rcx, qword_1803CE250; this
0x18014daf1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014daf8  cmp     [rcx+8], r14b
0x18014dafc  jz      short loc_18014DB1F
0x18014dafe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014db03  cmp     [rax+7CCh], ebx
0x18014db09  jz      short loc_18014DB1F
0x18014db0b  mov     r9d, ebx; int
0x18014db0e  mov     r8d, 1DE9h; int
0x18014db14  mov     rdx, r15; char *
0x18014db17  mov     rcx, rax; this
0x18014db1a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014db1f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18014db26  jb      loc_18014DD35
0x18014db2c  mov     edx, 1EFh
0x18014db31  jmp     loc_18014D7FB
0x18014db36  test    ebp, ebp
0x18014db38  jnz     loc_18014DCF7
0x18014db3e  cmp     [rsi+15Ch], edi
0x18014db44  jnz     loc_18014DBFB
0x18014db4a  cmp     [rsi+1C18h], r14d
0x18014db51  jnz     loc_18014DBFB
0x18014db57  mov     rcx, rsi; this
0x18014db5a  call    ?SignalStreamPrerolled@CAudStreamSink@@UEAAJXZ; CAudStreamSink::SignalStreamPrerolled(void)
0x18014db5f  mov     ebx, eax
0x18014db61  test    eax, eax
0x18014db63  jns     loc_18014DBFB
0x18014db69  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014db70  test    rcx, rcx
0x18014db73  jnz     short loc_18014DBBD
0x18014db75  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014db7c  nop     dword ptr [rax+rax+00h]
0x18014db81  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014db88  mov     rcx, rax
0x18014db8b  test    rax, rax
0x18014db8e  jz      short loc_18014DBAF
0x18014db90  mov     rax, [rax]
0x18014db93  mov     edx, 7F0h
0x18014db98  mov     rax, [rax+8]
0x18014db9c  call    cs:__guard_dispatch_icall_fptr
0x18014dba2  test    eax, eax
0x18014dba4  jz      short loc_18014DBAF
0x18014dba6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014dbad  jmp     short loc_18014DBBD
0x18014dbaf  lea     rcx, qword_1803CE250; this
0x18014dbb6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014dbbd  cmp     [rcx+8], r14b
  ... truncated ...
```
