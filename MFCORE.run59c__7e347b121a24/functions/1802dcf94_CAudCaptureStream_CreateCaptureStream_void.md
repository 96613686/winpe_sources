# CAudCaptureStream::CreateCaptureStream(void)

- ea: `0x1802dcf94`
- end: `0x1802dd652`
- name: `?CreateCaptureStream@CAudCaptureStream@@IEAAJXZ`
- size: `1726`
- prototype: `__int64 __fastcall(CAudCaptureStream *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1802de184`

## callees

- `0x18002fee0`
- `0x1800360b8`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800caaac`
- `0x1800ec0e0`
- `0x1800f21f8`
- `0x18014eaf8`
- `0x180153d20`
- `0x18015ab74`
- `0x1801859e8`
- `0x1801bb7e4`
- `0x18022b488`
- `0x180234f90`
- `0x1802dcf94`
- `0x1802de980`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802dd634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802dd634`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x1802dd0fb`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x1802dd0fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd04d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd11d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd217`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd2fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd3ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd474`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd04d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd11d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd217`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd2fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd3ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802dd474`

## string_xrefs

- `0x1802dcfde`: `CAudCaptureStream::CreateCaptureStream`

## pseudocode

```c
__int64 __fastcall CAudCaptureStream::CreateCaptureStream(CAudCaptureStream *this)
{
  HRESULT updated; // edi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  struct IAudioClient *v19; // rbx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CAecControlWrapper *v38; // rcx
  int v39; // eax
  CAudioEffectsManagerWrapper *v40; // rcx
  int v41; // eax
  WAVEFORMATEX *v42; // rax
  char v44; // [rsp+90h] [rbp+40h] BYREF
  WAVEFORMATEX *ppWF; // [rsp+98h] [rbp+48h] BYREF
  struct IUnknown *v46; // [rsp+A0h] [rbp+50h] BYREF
  struct IUnknown *v47; // [rsp+A8h] [rbp+58h] BYREF

  updated = 0;
  ppWF = 0;
  v47 = 0;
  v46 = 0;
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pp_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudCaptureStream_CreateCaptureStream_Enter,
      this,
      *((_QWORD *)this + 8));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "CAudCaptureStream::CreateCaptureStream", 579);
  if ( !*((_QWORD *)this + 8) )
  {
    if ( (unsigned __int8)byte_1803CECED >= 0x20u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 56, &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids, 0);
    updated = CAudCaptureStream::UpdateStreamingCharacteristics(this);
    if ( updated >= 0 )
    {
      updated = MFCreateWaveFormatExFromMFMediaType(*((IMFMediaType **)this + 14), &ppWF, 0, 0);
      if ( updated >= 0 )
      {
        if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
          McTemplateU0pqhqqhhh_EventWriteTransfer(
            ppWF->nChannels,
            (unsigned int)&AudCaptureStream_CreateCaptureStream_WAVEFORMAT,
            (_DWORD)this,
            ppWF->wFormatTag,
            ppWF->nChannels,
            ppWF->nSamplesPerSec,
            ppWF->nAvgBytesPerSec,
            ppWF->nBlockAlign,
            ppWF->wBitsPerSample,
            ppWF->cbSize);
        updated = CAudCaptureStream::CreateAudioClient2(this, (struct IAudioClient2 **)&v47);
        if ( updated >= 0 )
        {
          v19 = (struct IAudioClient *)v47;
          v20 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD, _QWORD, WAVEFORMATEX *, _QWORD))v47->lpVtbl[1].QueryInterface)(
                  v47,
                  0,
                  *((_DWORD *)this + 182) != 0 ? 0x40000 : 0,
                  *((_QWORD *)this + 90),
                  0,
                  ppWF,
                  0);
          updated = TranslateError_WASAPIToMFCapture(v20);
          if ( updated >= 0 )
          {
            v26 = ((__int64 (__fastcall *)(struct IAudioClient *, GUID *, struct IUnknown **))v19->lpVtbl->GetService)(
                    v19,
                    &GUID_c8adbd64_e71e_48a0_a4de_185c395cd317,
                    &v46);
            updated = TranslateError_WASAPIToMFCapture(v26);
            if ( updated >= 0 )
            {
              v32 = ((__int64 (__fastcall *)(struct IAudioClient *, char *))v19->lpVtbl->GetBufferSize)(
                      v19,
                      (char *)this + 184);
              updated = TranslateError_WASAPIToMFCapture(v32);
              if ( updated >= 0 )
              {
                v38 = (CAecControlWrapper *)*((_QWORD *)this + 11);
                if ( v38 )
                {
                  v39 = CAecControlWrapper::SetAudioClient(v38, v19);
                  if ( v39 < 0 )
                  {
                    if ( byte_1803CECED )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 27),
                        63,
                        &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids,
                        (unsigned int)v39);
                  }
                }
                v40 = (CAudioEffectsManagerWrapper *)*((_QWORD *)this + 10);
                if ( v40 )
                {
                  v41 = CAudioEffectsManagerWrapper::SetAudioClient(v40, v19);
                  if ( v41 < 0 )
                  {
                    if ( byte_1803CECED )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 27),
                        64,
                        &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids,
                        (unsigned int)v41);
                  }
                }
                v42 = ppWF;
                *((_DWORD *)this + 43) = ppWF->nBlockAlign;
                *((_DWORD *)this + 39) = v42->nSamplesPerSec;
                if ( (unsigned __int8)byte_1803CECED >= 0x10u )
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 27),
                    65,
                    &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids,
                    *((unsigned int *)this + 37),
                    *((_DWORD *)this + 46));
                if ( *((struct IAudioClient **)this + 8) != v19 )
                  ATL::AtlComPtrAssign((struct IUnknown **)this + 8, (struct IUnknown *)v19);
                if ( *((struct IUnknown **)this + 7) != v46 )
                  ATL::AtlComPtrAssign((struct IUnknown **)this + 7, v46);
              }
              else
              {
                v35 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
                  CallStackTracing::s_wpInstance = v36;
                  if ( v36
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
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
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
                    CallStackContext::TraceFailure(
                      ThreadRelativeContext,
                      "CAudCaptureStream::CreateCaptureStream",
                      628,
                      updated);
                }
                if ( g_wppLevels )
                {
                  v8 = 62;
                  goto LABEL_17;
                }
              }
            }
            else
            {
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
                CallStackTracing::s_wpInstance = v30;
                if ( v30
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
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
                if ( *((_DWORD *)v31 + 499) != updated )
                  CallStackContext::TraceFailure(v31, "CAudCaptureStream::CreateCaptureStream", 627, updated);
              }
              if ( g_wppLevels )
              {
                v8 = 61;
                goto LABEL_17;
              }
            }
          }
          else
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
              CallStackTracing::s_wpInstance = v24;
              if ( v24
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
              {
                v23 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v23 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v23 + 8) )
            {
              v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
              if ( *((_DWORD *)v25 + 499) != updated )
                CallStackContext::TraceFailure(v25, "CAudCaptureStream::CreateCaptureStream", 623, updated);
            }
            if ( g_wppLevels )
            {
              v8 = 60;
              goto LABEL_17;
            }
          }
        }
        else
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
            if ( *((_DWORD *)v18 + 499) != updated )
              CallStackContext::TraceFailure(v18, "CAudCaptureStream::CreateCaptureStream", 607, updated);
          }
          if ( g_wppLevels )
          {
            v8 = 59;
            goto LABEL_17;
          }
        }
      }
      else
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10);
          CallStackTracing::s_wpInstance = v12;
          if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
          {
            v11 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v13 + 499) != updated )
            CallStackContext::TraceFailure(v13, "CAudCaptureStream::CreateCaptureStream", 595, updated);
        }
        if ( g_wppLevels )
        {
          v8 = 58;
          goto LABEL_17;
        }
      }
    }
    else
    {
      v5 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3, v4);
        CallStackTracing::s_wpInstance = v6;
        if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
        {
          v5 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v5 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v5 + 8) )
      {
        v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
        if ( *((_DWORD *)v7 + 499) != updated )
          CallStackContext::TraceFailure(v7, "CAudCaptureStream::CreateCaptureStream", 593, updated);
      }
      if ( g_wppLevels )
      {
        v8 = 57;
LABEL_17:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids,
          this,
          updated);
      }
    }
  }
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pqqq_EventWriteTransfer(
      (unsigned int)&Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      (unsigned int)&AudCaptureStream_CreateCaptureStream_Exit,
      (_DWORD)this,
      *((_DWORD *)this + 43),
      *((_DWORD *)this + 39),
      updated);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v46);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v47);
  CoTaskMemFree(ppWF);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1802dcf94  push    rbp
0x1802dcf96  push    rbx
0x1802dcf97  push    rsi
0x1802dcf98  push    rdi
0x1802dcf99  push    r12
0x1802dcf9b  push    r13
0x1802dcf9d  push    r14
0x1802dcf9f  mov     rbp, rsp
0x1802dcfa2  sub     rsp, 50h
0x1802dcfa6  xor     r14d, r14d
0x1802dcfa9  mov     rsi, rcx
0x1802dcfac  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x1802dcfb3  mov     edi, r14d
0x1802dcfb6  mov     [rbp+ppWF], r14
0x1802dcfba  mov     [rbp+arg_18], r14
0x1802dcfbe  mov     [rbp+arg_10], r14
0x1802dcfc2  jz      short loc_1802DCFDE
0x1802dcfc4  mov     r9, [rcx+40h]
0x1802dcfc8  lea     rdx, AudCaptureStream_CreateCaptureStream_Enter
0x1802dcfcf  mov     r8, rcx
0x1802dcfd2  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Core_Context
0x1802dcfd9  call    McTemplateU0pp_EventWriteTransfer
0x1802dcfde  lea     r13, aCaudcapturestr_34; "CAudCaptureStream::CreateCaptureStream"
0x1802dcfe5  mov     r8d, 243h; int
0x1802dcfeb  mov     rdx, r13; char *
0x1802dcfee  lea     rcx, [rbp+arg_0]; this
0x1802dcff2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802dcff7  cmp     [rsi+40h], r14
0x1802dcffb  jnz     loc_1802DD5E1
0x1802dd001  cmp     cs:byte_1803CECED, 20h ; ' '
0x1802dd008  lea     r12, WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids
0x1802dd00f  jb      short loc_1802DD02F
0x1802dd011  mov     rcx, cs:WPP_GLOBAL_Control
0x1802dd018  mov     edx, 38h ; '8'
0x1802dd01d  xor     r9d, r9d
0x1802dd020  mov     r8, r12
0x1802dd023  mov     rcx, [rcx+0D8h]
0x1802dd02a  call    WPP_SF_d
0x1802dd02f  mov     rcx, rsi; this
0x1802dd032  call    ?UpdateStreamingCharacteristics@CAudCaptureStream@@IEAAJXZ; CAudCaptureStream::UpdateStreamingCharacteristics(void)
0x1802dd037  mov     edi, eax
0x1802dd039  test    eax, eax
0x1802dd03b  jns     loc_1802DD0ED
0x1802dd041  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd048  test    rcx, rcx
0x1802dd04b  jnz     short loc_1802DD095
0x1802dd04d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802dd054  nop     dword ptr [rax+rax+00h]
0x1802dd059  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd060  mov     rcx, rax
0x1802dd063  test    rax, rax
0x1802dd066  jz      short loc_1802DD087
0x1802dd068  mov     rax, [rax]
0x1802dd06b  mov     edx, 7F0h
0x1802dd070  mov     rax, [rax+8]
0x1802dd074  call    cs:__guard_dispatch_icall_fptr
0x1802dd07a  test    eax, eax
0x1802dd07c  jz      short loc_1802DD087
0x1802dd07e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd085  jmp     short loc_1802DD095
0x1802dd087  lea     rcx, qword_1803CE250; this
0x1802dd08e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd095  cmp     [rcx+8], r14b
0x1802dd099  jz      short loc_1802DD0BC
0x1802dd09b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802dd0a0  cmp     [rax+7CCh], edi
0x1802dd0a6  jz      short loc_1802DD0BC
0x1802dd0a8  mov     r9d, edi; int
0x1802dd0ab  mov     r8d, 251h; int
0x1802dd0b1  mov     rdx, r13; char *
0x1802dd0b4  mov     rcx, rax; this
0x1802dd0b7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802dd0bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802dd0c3  jb      loc_1802DD5E1
0x1802dd0c9  mov     edx, 39h ; '9'
0x1802dd0ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1802dd0d5  mov     r9, rsi
0x1802dd0d8  mov     r8, r12
0x1802dd0db  mov     dword ptr [rsp+50h+var_30], edi
0x1802dd0df  mov     rcx, [rcx+10h]
0x1802dd0e3  call    WPP_SF_qD
0x1802dd0e8  jmp     loc_1802DD5E1
0x1802dd0ed  mov     rcx, [rsi+70h]; pMFType
0x1802dd0f1  lea     rdx, [rbp+ppWF]; ppWF
0x1802dd0f5  xor     r9d, r9d; Flags
0x1802dd0f8  xor     r8d, r8d; pcbSize
0x1802dd0fb  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x1802dd102  nop     dword ptr [rax+rax+00h]
0x1802dd107  mov     edi, eax
0x1802dd109  test    eax, eax
0x1802dd10b  jns     loc_1802DD1A3
0x1802dd111  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd118  test    rcx, rcx
0x1802dd11b  jnz     short loc_1802DD165
0x1802dd11d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802dd124  nop     dword ptr [rax+rax+00h]
0x1802dd129  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd130  mov     rcx, rax
0x1802dd133  test    rax, rax
0x1802dd136  jz      short loc_1802DD157
0x1802dd138  mov     rax, [rax]
0x1802dd13b  mov     edx, 7F0h
0x1802dd140  mov     rax, [rax+8]
0x1802dd144  call    cs:__guard_dispatch_icall_fptr
0x1802dd14a  test    eax, eax
0x1802dd14c  jz      short loc_1802DD157
0x1802dd14e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd155  jmp     short loc_1802DD165
0x1802dd157  lea     rcx, qword_1803CE250; this
0x1802dd15e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd165  cmp     [rcx+8], r14b
0x1802dd169  jz      short loc_1802DD18C
0x1802dd16b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802dd170  cmp     [rax+7CCh], edi
0x1802dd176  jz      short loc_1802DD18C
0x1802dd178  mov     r9d, edi; int
0x1802dd17b  mov     r8d, 253h; int
0x1802dd181  mov     rdx, r13; char *
0x1802dd184  mov     rcx, rax; this
0x1802dd187  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802dd18c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802dd193  jb      loc_1802DD5E1
0x1802dd199  mov     edx, 3Ah ; ':'
0x1802dd19e  jmp     loc_1802DD0CE
0x1802dd1a3  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x1802dd1aa  jz      short loc_1802DD1F5
0x1802dd1ac  mov     rax, [rbp+ppWF]
0x1802dd1b0  lea     rdx, AudCaptureStream_CreateCaptureStream_WAVEFORMAT
0x1802dd1b7  mov     r8, rsi
0x1802dd1ba  movzx   ecx, word ptr [rax+10h]
0x1802dd1be  movzx   r9d, word ptr [rax]
0x1802dd1c2  mov     [rsp+50h+var_8], cx
0x1802dd1c7  movzx   ecx, word ptr [rax+0Eh]
0x1802dd1cb  mov     [rsp+50h+var_10], cx
0x1802dd1d0  movzx   ecx, word ptr [rax+0Ch]
0x1802dd1d4  mov     [rsp+50h+var_18], cx
0x1802dd1d9  mov     ecx, [rax+8]
0x1802dd1dc  mov     dword ptr [rsp+50h+var_20], ecx
0x1802dd1e0  mov     ecx, [rax+4]
0x1802dd1e3  mov     dword ptr [rsp+50h+var_28], ecx
0x1802dd1e7  movzx   ecx, word ptr [rax+2]
0x1802dd1eb  mov     word ptr [rsp+50h+var_30], cx
0x1802dd1f0  call    McTemplateU0pqhqqhhh_EventWriteTransfer
0x1802dd1f5  lea     rdx, [rbp+arg_18]; struct IAudioClient2 **
0x1802dd1f9  mov     rcx, rsi; this
0x1802dd1fc  call    ?CreateAudioClient2@CAudCaptureStream@@IEAAJPEAPEAUIAudioClient2@@@Z; CAudCaptureStream::CreateAudioClient2(IAudioClient2 * *)
0x1802dd201  mov     edi, eax
0x1802dd203  test    eax, eax
0x1802dd205  jns     loc_1802DD29D
0x1802dd20b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd212  test    rcx, rcx
0x1802dd215  jnz     short loc_1802DD25F
0x1802dd217  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802dd21e  nop     dword ptr [rax+rax+00h]
0x1802dd223  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd22a  mov     rcx, rax
0x1802dd22d  test    rax, rax
0x1802dd230  jz      short loc_1802DD251
0x1802dd232  mov     rax, [rax]
0x1802dd235  mov     edx, 7F0h
0x1802dd23a  mov     rax, [rax+8]
0x1802dd23e  call    cs:__guard_dispatch_icall_fptr
0x1802dd244  test    eax, eax
0x1802dd246  jz      short loc_1802DD251
0x1802dd248  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd24f  jmp     short loc_1802DD25F
0x1802dd251  lea     rcx, qword_1803CE250; this
0x1802dd258  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd25f  cmp     [rcx+8], r14b
0x1802dd263  jz      short loc_1802DD286
0x1802dd265  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802dd26a  cmp     [rax+7CCh], edi
0x1802dd270  jz      short loc_1802DD286
0x1802dd272  mov     r9d, edi; int
0x1802dd275  mov     r8d, 25Fh; int
0x1802dd27b  mov     rdx, r13; char *
0x1802dd27e  mov     rcx, rax; this
0x1802dd281  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802dd286  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802dd28d  jb      loc_1802DD5E1
0x1802dd293  mov     edx, 3Bh ; ';'
0x1802dd298  jmp     loc_1802DD0CE
0x1802dd29d  mov     eax, [rsi+2D8h]
0x1802dd2a3  mov     rdx, [rbp+ppWF]
0x1802dd2a7  neg     eax
0x1802dd2a9  mov     rbx, [rbp+arg_18]
0x1802dd2ad  mov     r9, [rsi+2D0h]
0x1802dd2b4  sbb     r8d, r8d
0x1802dd2b7  mov     [rsp+50h+var_20], r14
0x1802dd2bc  and     r8d, 40000h
0x1802dd2c3  mov     [rsp+50h+var_28], rdx
0x1802dd2c8  xor     edx, edx
0x1802dd2ca  mov     rcx, [rbx]
0x1802dd2cd  mov     [rsp+50h+var_30], r14
0x1802dd2d2  mov     rax, [rcx+18h]
0x1802dd2d6  mov     rcx, rbx
0x1802dd2d9  call    cs:__guard_dispatch_icall_fptr
0x1802dd2df  mov     ecx, eax; int
0x1802dd2e1  call    ?TranslateError_WASAPIToMFCapture@@YAJJ@Z; TranslateError_WASAPIToMFCapture(long)
0x1802dd2e6  mov     edi, eax
0x1802dd2e8  test    eax, eax
0x1802dd2ea  jns     loc_1802DD382
0x1802dd2f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd2f7  test    rcx, rcx
0x1802dd2fa  jnz     short loc_1802DD344
0x1802dd2fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802dd303  nop     dword ptr [rax+rax+00h]
0x1802dd308  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd30f  mov     rcx, rax
0x1802dd312  test    rax, rax
0x1802dd315  jz      short loc_1802DD336
0x1802dd317  mov     rax, [rax]
0x1802dd31a  mov     edx, 7F0h
0x1802dd31f  mov     rax, [rax+8]
0x1802dd323  call    cs:__guard_dispatch_icall_fptr
0x1802dd329  test    eax, eax
0x1802dd32b  jz      short loc_1802DD336
0x1802dd32d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd334  jmp     short loc_1802DD344
0x1802dd336  lea     rcx, qword_1803CE250; this
0x1802dd33d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd344  cmp     [rcx+8], r14b
0x1802dd348  jz      short loc_1802DD36B
0x1802dd34a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802dd34f  cmp     [rax+7CCh], edi
0x1802dd355  jz      short loc_1802DD36B
0x1802dd357  mov     r9d, edi; int
0x1802dd35a  mov     r8d, 26Fh; int
0x1802dd360  mov     rdx, r13; char *
0x1802dd363  mov     rcx, rax; this
0x1802dd366  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802dd36b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802dd372  jb      loc_1802DD5E1
0x1802dd378  mov     edx, 3Ch ; '<'
0x1802dd37d  jmp     loc_1802DD0CE
0x1802dd382  mov     rax, [rbx]
0x1802dd385  lea     r8, [rbp+arg_10]
0x1802dd389  lea     rdx, _GUID_c8adbd64_e71e_48a0_a4de_185c395cd317
0x1802dd390  mov     rcx, rbx
0x1802dd393  mov     rax, [rax+70h]
0x1802dd397  call    cs:__guard_dispatch_icall_fptr
0x1802dd39d  mov     ecx, eax; int
0x1802dd39f  call    ?TranslateError_WASAPIToMFCapture@@YAJJ@Z; TranslateError_WASAPIToMFCapture(long)
0x1802dd3a4  mov     edi, eax
0x1802dd3a6  test    eax, eax
0x1802dd3a8  jns     loc_1802DD440
0x1802dd3ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd3b5  test    rcx, rcx
0x1802dd3b8  jnz     short loc_1802DD402
0x1802dd3ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802dd3c1  nop     dword ptr [rax+rax+00h]
0x1802dd3c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd3cd  mov     rcx, rax
0x1802dd3d0  test    rax, rax
0x1802dd3d3  jz      short loc_1802DD3F4
0x1802dd3d5  mov     rax, [rax]
0x1802dd3d8  mov     edx, 7F0h
0x1802dd3dd  mov     rax, [rax+8]
0x1802dd3e1  call    cs:__guard_dispatch_icall_fptr
0x1802dd3e7  test    eax, eax
0x1802dd3e9  jz      short loc_1802DD3F4
0x1802dd3eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd3f2  jmp     short loc_1802DD402
0x1802dd3f4  lea     rcx, qword_1803CE250; this
0x1802dd3fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd402  cmp     [rcx+8], r14b
0x1802dd406  jz      short loc_1802DD429
0x1802dd408  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802dd40d  cmp     [rax+7CCh], edi
0x1802dd413  jz      short loc_1802DD429
0x1802dd415  mov     r9d, edi; int
0x1802dd418  mov     r8d, 273h; int
0x1802dd41e  mov     rdx, r13; char *
0x1802dd421  mov     rcx, rax; this
0x1802dd424  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802dd429  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802dd430  jb      loc_1802DD5E1
0x1802dd436  mov     edx, 3Dh ; '='
0x1802dd43b  jmp     loc_1802DD0CE
0x1802dd440  mov     rax, [rbx]
0x1802dd443  lea     rdx, [rsi+0B8h]
0x1802dd44a  mov     rcx, rbx
0x1802dd44d  mov     rax, [rax+20h]
0x1802dd451  call    cs:__guard_dispatch_icall_fptr
0x1802dd457  mov     ecx, eax; int
0x1802dd459  call    ?TranslateError_WASAPIToMFCapture@@YAJJ@Z; TranslateError_WASAPIToMFCapture(long)
0x1802dd45e  mov     edi, eax
0x1802dd460  test    eax, eax
0x1802dd462  jns     loc_1802DD4FA
0x1802dd468  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd46f  test    rcx, rcx
0x1802dd472  jnz     short loc_1802DD4BC
0x1802dd474  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802dd47b  nop     dword ptr [rax+rax+00h]
0x1802dd480  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802dd487  mov     rcx, rax
0x1802dd48a  test    rax, rax
0x1802dd48d  jz      short loc_1802DD4AE
0x1802dd48f  mov     rax, [rax]
0x1802dd492  mov     edx, 7F0h
  ... truncated ...
```
