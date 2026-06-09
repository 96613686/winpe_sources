# CAudCaptureStream::GetMediaType(ulong,IMFMediaType * *)

- ea: `0x18014e544`
- end: `0x18014eaf1`
- name: `?GetMediaType@CAudCaptureStream@@QEAAJKPEAPEAUIMFMediaType@@@Z`
- size: `1453`
- prototype: `__int64 __fastcall(CAudCaptureStream *__hidden this, unsigned int, struct IMFMediaType **)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18014e250`
- `0x180200e68`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x1800360b8`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180045dbc`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18014e544`
- `0x18014eaf8`
- `0x1802de980`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014ea70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014ea70`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18014e8a7`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18014e8a7`
- `MFPlat!MFCreateMediaType` at `0x18014e7ee`
- `MFPlat!MFCreateMediaType` at `0x18014e7ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014e5a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014e646`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014e810`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014e8c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014e9d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014e5a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014e646`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014e810`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014e8c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014e9d1`

## pseudocode

```c
__int64 __fastcall CAudCaptureStream::GetMediaType(CAudCaptureStream *this, int a2, struct IMFMediaType **a3)
{
  struct IAudioClient2 *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 *v9; // rcx
  HRESULT v10; // edi
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  int v19; // eax
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  IMFMediaType *ppMFType; // [rsp+50h] [rbp-10h] BYREF
  char v39; // [rsp+90h] [rbp+30h] BYREF
  WAVEFORMATEX *pWaveFormat; // [rsp+A0h] [rbp+40h] BYREF
  struct IAudioClient2 *v41; // [rsp+A8h] [rbp+48h] BYREF

  pWaveFormat = 0;
  ppMFType = 0;
  v6 = 0;
  v41 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v39, "CAudCaptureStream::GetMediaType", 754);
  if ( a3 )
  {
    if ( a2 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      v10 = -1072875847;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875847 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CAudCaptureStream::GetMediaType", 761, -1072875847);
      }
      if ( g_wppLevels )
      {
        v13 = 72;
        goto LABEL_78;
      }
    }
    else
    {
      v6 = (struct IAudioClient2 *)*((_QWORD *)this + 8);
      if ( v6 )
      {
        ((void (__fastcall *)(_QWORD))v6->lpVtbl->AddRef)(*((_QWORD *)this + 8));
      }
      else
      {
        v10 = CAudCaptureStream::CreateAudioClient2(this, &v41);
        if ( v10 < 0 )
        {
          v17 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v17 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            v18 = CallStackTracing::GetThreadRelativeContext(v17);
            if ( *((_DWORD *)v18 + 499) != v10 )
              CallStackContext::TraceFailure(v18, "CAudCaptureStream::GetMediaType", 771, v10);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              73,
              &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids,
              this,
              v10);
          v6 = v41;
          goto LABEL_79;
        }
        v6 = v41;
      }
      v19 = ((__int64 (__fastcall *)(struct IAudioClient2 *, WAVEFORMATEX **))v6->lpVtbl->GetMixFormat)(
              v6,
              &pWaveFormat);
      v10 = TranslateError_WASAPIToMFCapture(v19);
      if ( v10 >= 0 )
      {
        v10 = MFCreateMediaType(&ppMFType);
        if ( v10 >= 0 )
        {
          v10 = MFInitMediaTypeFromWaveFormatEx(ppMFType, pWaveFormat, pWaveFormat->cbSize + 18);
          if ( v10 >= 0 )
          {
            if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
              McTemplateU0pqhqqhhh_EventWriteTransfer(
                (_DWORD)pWaveFormat,
                (unsigned int)&AudCaptureStream_GetMediaType_WAVEFORMAT,
                (_DWORD)this,
                pWaveFormat->wFormatTag,
                pWaveFormat->nChannels,
                pWaveFormat->nSamplesPerSec,
                pWaveFormat->nAvgBytesPerSec,
                pWaveFormat->nBlockAlign,
                pWaveFormat->wBitsPerSample,
                pWaveFormat->cbSize);
            v10 = ((__int64 (__fastcall *)(IMFMediaType *, GUID *, struct IMFMediaType **))ppMFType->lpVtbl->QueryInterface)(
                    ppMFType,
                    &IID_IMFMediaType,
                    a3);
            if ( v10 < 0 )
            {
              v34 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33);
                CallStackTracing::s_wpInstance = v35;
                if ( v35
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
                {
                  v34 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v34 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v34 + 8) )
              {
                v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                if ( *((_DWORD *)v36 + 499) != v10 )
                  CallStackContext::TraceFailure(v36, "CAudCaptureStream::GetMediaType", 787, v10);
              }
              if ( g_wppLevels )
              {
                v13 = 77;
                goto LABEL_78;
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
              if ( *((_DWORD *)v31 + 499) != v10 )
                CallStackContext::TraceFailure(v31, "CAudCaptureStream::GetMediaType", 776, v10);
            }
            if ( g_wppLevels )
            {
              v13 = 76;
              goto LABEL_78;
            }
          }
        }
        else
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)v26 + 499) != v10 )
              CallStackContext::TraceFailure(v26, "CAudCaptureStream::GetMediaType", 775, v10);
          }
          if ( g_wppLevels )
          {
            v13 = 75;
            goto LABEL_78;
          }
        }
      }
      else
      {
        v20 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v20 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v21 = CallStackTracing::GetThreadRelativeContext(v20);
          if ( *((_DWORD *)v21 + 499) != v10 )
            CallStackContext::TraceFailure(v21, "CAudCaptureStream::GetMediaType", 774, v10);
        }
        if ( g_wppLevels )
        {
          v13 = 74;
          goto LABEL_78;
        }
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    v10 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v12 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v12, "CAudCaptureStream::GetMediaType", 756, -2147467261);
    }
    if ( g_wppLevels )
    {
      v13 = 71;
LABEL_78:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids, this, v10);
    }
  }
LABEL_79:
  CoTaskMemFree(pWaveFormat);
  pWaveFormat = 0;
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudCaptureStream_GetMediaType,
      this,
      (unsigned int)v10);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v39);
  if ( v6 )
    ((void (__fastcall *)(struct IAudioClient2 *))v6->lpVtbl->Release)(v6);
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18014e544  mov     [rsp-28h+arg_8], rbx
0x18014e549  push    rbp
0x18014e54a  push    rsi
0x18014e54b  push    rdi
0x18014e54c  push    r12
0x18014e54e  push    r14
0x18014e550  mov     rbp, rsp
0x18014e553  sub     rsp, 60h
0x18014e557  mov     r14, r8
0x18014e55a  mov     [rbp+pWaveFormat], 0
0x18014e562  mov     edi, edx
0x18014e564  mov     [rbp+ppMFType], 0
0x18014e56c  mov     rsi, rcx
0x18014e56f  lea     r12, aCaudcapturestr_9; "CAudCaptureStream::GetMediaType"
0x18014e576  xor     ebx, ebx
0x18014e578  lea     rcx, [rbp+arg_0]; this
0x18014e57c  mov     rdx, r12; char *
0x18014e57f  mov     [rbp+arg_18], rbx
0x18014e583  mov     r8d, 2F2h; int
0x18014e589  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18014e58e  test    r14, r14
0x18014e591  jnz     loc_18014E62D
0x18014e597  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e59e  mov     edi, 80004003h
0x18014e5a3  test    rcx, rcx
0x18014e5a6  jnz     short loc_18014E5F0
0x18014e5a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014e5af  nop     dword ptr [rax+rax+00h]
0x18014e5b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e5bb  mov     rcx, rax
0x18014e5be  test    rax, rax
0x18014e5c1  jz      short loc_18014E5E2
0x18014e5c3  mov     rax, [rax]
0x18014e5c6  mov     edx, 7F0h
0x18014e5cb  mov     rax, [rax+8]
0x18014e5cf  call    cs:__guard_dispatch_icall_fptr
0x18014e5d5  test    eax, eax
0x18014e5d7  jz      short loc_18014E5E2
0x18014e5d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e5e0  jmp     short loc_18014E5F0
0x18014e5e2  lea     rcx, qword_1803CE250; this
0x18014e5e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e5f0  cmp     [rcx+8], bl
0x18014e5f3  jz      short loc_18014E616
0x18014e5f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014e5fa  cmp     [rax+7CCh], edi
0x18014e600  jz      short loc_18014E616
0x18014e602  mov     r9d, edi; int
0x18014e605  mov     r8d, 2F4h; int
0x18014e60b  mov     rdx, r12; char *
0x18014e60e  mov     rcx, rax; this
0x18014e611  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014e616  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014e61d  jb      loc_18014EA6C
0x18014e623  mov     edx, 47h ; 'G'
0x18014e628  jmp     loc_18014EA4E
0x18014e62d  test    edi, edi
0x18014e62f  jz      loc_18014E6CB
0x18014e635  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e63c  mov     edi, 0C00D36B9h
0x18014e641  test    rcx, rcx
0x18014e644  jnz     short loc_18014E68E
0x18014e646  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014e64d  nop     dword ptr [rax+rax+00h]
0x18014e652  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e659  mov     rcx, rax
0x18014e65c  test    rax, rax
0x18014e65f  jz      short loc_18014E680
0x18014e661  mov     rax, [rax]
0x18014e664  mov     edx, 7F0h
0x18014e669  mov     rax, [rax+8]
0x18014e66d  call    cs:__guard_dispatch_icall_fptr
0x18014e673  test    eax, eax
0x18014e675  jz      short loc_18014E680
0x18014e677  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e67e  jmp     short loc_18014E68E
0x18014e680  lea     rcx, qword_1803CE250; this
0x18014e687  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e68e  cmp     [rcx+8], bl
0x18014e691  jz      short loc_18014E6B4
0x18014e693  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014e698  cmp     [rax+7CCh], edi
0x18014e69e  jz      short loc_18014E6B4
0x18014e6a0  mov     r9d, edi; int
0x18014e6a3  mov     r8d, 2F9h; int
0x18014e6a9  mov     rdx, r12; char *
0x18014e6ac  mov     rcx, rax; this
0x18014e6af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014e6b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014e6bb  jb      loc_18014EA6C
0x18014e6c1  mov     edx, 48h ; 'H'
0x18014e6c6  jmp     loc_18014EA4E
0x18014e6cb  mov     rbx, [rsi+40h]
0x18014e6cf  test    rbx, rbx
0x18014e6d2  jz      short loc_18014E6E9
0x18014e6d4  mov     rax, [rbx]
0x18014e6d7  mov     rcx, rbx
0x18014e6da  mov     rax, [rax+8]
0x18014e6de  call    cs:__guard_dispatch_icall_fptr
0x18014e6e4  jmp     loc_18014E773
0x18014e6e9  lea     rdx, [rbp+arg_18]; struct IAudioClient2 **
0x18014e6ed  mov     rcx, rsi; this
0x18014e6f0  call    ?CreateAudioClient2@CAudCaptureStream@@IEAAJPEAPEAUIAudioClient2@@@Z; CAudCaptureStream::CreateAudioClient2(IAudioClient2 * *)
0x18014e6f5  mov     edi, eax
0x18014e6f7  test    eax, eax
0x18014e6f9  jns     short loc_18014E76F
0x18014e6fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e702  test    rcx, rcx
0x18014e705  jnz     short loc_18014E713
0x18014e707  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18014e70c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18014e713  cmp     byte ptr [rcx+8], 0
0x18014e717  jz      short loc_18014E73A
0x18014e719  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014e71e  cmp     [rax+7CCh], edi
0x18014e724  jz      short loc_18014E73A
0x18014e726  mov     r9d, edi; int
0x18014e729  mov     r8d, 303h; int
0x18014e72f  mov     rdx, r12; char *
0x18014e732  mov     rcx, rax; this
0x18014e735  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014e73a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014e741  jb      short loc_18014E766
0x18014e743  mov     rcx, cs:WPP_GLOBAL_Control
0x18014e74a  lea     r8, WPP_a3161aeae109384f3fa1a92793044c0c_Traceguids
0x18014e751  mov     edx, 49h ; 'I'
0x18014e756  mov     [rsp+60h+var_40], edi
0x18014e75a  mov     r9, rsi
0x18014e75d  mov     rcx, [rcx+10h]
0x18014e761  call    WPP_SF_qD
0x18014e766  mov     rbx, [rbp+arg_18]
0x18014e76a  jmp     loc_18014EA6C
0x18014e76f  mov     rbx, [rbp+arg_18]
0x18014e773  mov     rax, [rbx]
0x18014e776  lea     rdx, [rbp+pWaveFormat]
0x18014e77a  mov     rcx, rbx
0x18014e77d  mov     rax, [rax+40h]
0x18014e781  call    cs:__guard_dispatch_icall_fptr
0x18014e787  mov     ecx, eax; int
0x18014e789  call    ?TranslateError_WASAPIToMFCapture@@YAJJ@Z; TranslateError_WASAPIToMFCapture(long)
0x18014e78e  mov     edi, eax
0x18014e790  test    eax, eax
0x18014e792  jns     short loc_18014E7EA
0x18014e794  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e79b  test    rcx, rcx
0x18014e79e  jnz     short loc_18014E7AC
0x18014e7a0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18014e7a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18014e7ac  cmp     byte ptr [rcx+8], 0
0x18014e7b0  jz      short loc_18014E7D3
0x18014e7b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014e7b7  cmp     [rax+7CCh], edi
0x18014e7bd  jz      short loc_18014E7D3
0x18014e7bf  mov     r9d, edi; int
0x18014e7c2  mov     r8d, 306h; int
0x18014e7c8  mov     rdx, r12; char *
0x18014e7cb  mov     rcx, rax; this
0x18014e7ce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014e7d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014e7da  jb      loc_18014EA6C
0x18014e7e0  mov     edx, 4Ah ; 'J'
0x18014e7e5  jmp     loc_18014EA4E
0x18014e7ea  lea     rcx, [rbp+ppMFType]; ppMFType
0x18014e7ee  call    cs:__imp_MFCreateMediaType
0x18014e7f5  nop     dword ptr [rax+rax+00h]
0x18014e7fa  mov     edi, eax
0x18014e7fc  test    eax, eax
0x18014e7fe  jns     loc_18014E896
0x18014e804  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e80b  test    rcx, rcx
0x18014e80e  jnz     short loc_18014E858
0x18014e810  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014e817  nop     dword ptr [rax+rax+00h]
0x18014e81c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e823  mov     rcx, rax
0x18014e826  test    rax, rax
0x18014e829  jz      short loc_18014E84A
0x18014e82b  mov     rax, [rax]
0x18014e82e  mov     edx, 7F0h
0x18014e833  mov     rax, [rax+8]
0x18014e837  call    cs:__guard_dispatch_icall_fptr
0x18014e83d  test    eax, eax
0x18014e83f  jz      short loc_18014E84A
0x18014e841  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e848  jmp     short loc_18014E858
0x18014e84a  lea     rcx, qword_1803CE250; this
0x18014e851  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e858  cmp     byte ptr [rcx+8], 0
0x18014e85c  jz      short loc_18014E87F
0x18014e85e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014e863  cmp     [rax+7CCh], edi
0x18014e869  jz      short loc_18014E87F
0x18014e86b  mov     r9d, edi; int
0x18014e86e  mov     r8d, 307h; int
0x18014e874  mov     rdx, r12; char *
0x18014e877  mov     rcx, rax; this
0x18014e87a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014e87f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014e886  jb      loc_18014EA6C
0x18014e88c  mov     edx, 4Bh ; 'K'
0x18014e891  jmp     loc_18014EA4E
0x18014e896  mov     rdx, [rbp+pWaveFormat]; pWaveFormat
0x18014e89a  mov     rcx, [rbp+ppMFType]; pMFType
0x18014e89e  movzx   r8d, word ptr [rdx+10h]
0x18014e8a3  add     r8d, 12h; cbBufSize
0x18014e8a7  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x18014e8ae  nop     dword ptr [rax+rax+00h]
0x18014e8b3  mov     edi, eax
0x18014e8b5  test    eax, eax
0x18014e8b7  jns     loc_18014E94F
0x18014e8bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e8c4  test    rcx, rcx
0x18014e8c7  jnz     short loc_18014E911
0x18014e8c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014e8d0  nop     dword ptr [rax+rax+00h]
0x18014e8d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e8dc  mov     rcx, rax
0x18014e8df  test    rax, rax
0x18014e8e2  jz      short loc_18014E903
0x18014e8e4  mov     rax, [rax]
0x18014e8e7  mov     edx, 7F0h
0x18014e8ec  mov     rax, [rax+8]
0x18014e8f0  call    cs:__guard_dispatch_icall_fptr
0x18014e8f6  test    eax, eax
0x18014e8f8  jz      short loc_18014E903
0x18014e8fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e901  jmp     short loc_18014E911
0x18014e903  lea     rcx, qword_1803CE250; this
0x18014e90a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e911  cmp     byte ptr [rcx+8], 0
0x18014e915  jz      short loc_18014E938
0x18014e917  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014e91c  cmp     [rax+7CCh], edi
0x18014e922  jz      short loc_18014E938
0x18014e924  mov     r9d, edi; int
0x18014e927  mov     r8d, 308h; int
0x18014e92d  mov     rdx, r12; char *
0x18014e930  mov     rcx, rax; this
0x18014e933  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014e938  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014e93f  jb      loc_18014EA6C
0x18014e945  mov     edx, 4Ch ; 'L'
0x18014e94a  jmp     loc_18014EA4E
0x18014e94f  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x18014e956  jz      short loc_18014E9A1
0x18014e958  mov     rcx, [rbp+pWaveFormat]
0x18014e95c  lea     rdx, AudCaptureStream_GetMediaType_WAVEFORMAT
0x18014e963  mov     r8, rsi
0x18014e966  movzx   eax, word ptr [rcx+10h]
0x18014e96a  movzx   r9d, word ptr [rcx]
0x18014e96e  mov     [rsp+60h+var_18], ax
0x18014e973  movzx   eax, word ptr [rcx+0Eh]
0x18014e977  mov     [rsp+60h+var_20], ax
0x18014e97c  movzx   eax, word ptr [rcx+0Ch]
0x18014e980  mov     [rsp+60h+var_28], ax
0x18014e985  mov     eax, [rcx+8]
0x18014e988  mov     [rsp+60h+var_30], eax
0x18014e98c  mov     eax, [rcx+4]
0x18014e98f  mov     [rsp+60h+var_38], eax
0x18014e993  movzx   eax, word ptr [rcx+2]
0x18014e997  mov     word ptr [rsp+60h+var_40], ax
0x18014e99c  call    McTemplateU0pqhqqhhh_EventWriteTransfer
0x18014e9a1  mov     rcx, [rbp+ppMFType]
0x18014e9a5  lea     rdx, IID_IMFMediaType
0x18014e9ac  mov     r8, r14
0x18014e9af  mov     rax, [rcx]
0x18014e9b2  mov     rax, [rax]
0x18014e9b5  call    cs:__guard_dispatch_icall_fptr
0x18014e9bb  mov     edi, eax
0x18014e9bd  test    eax, eax
0x18014e9bf  jns     loc_18014EA6C
0x18014e9c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e9cc  test    rcx, rcx
0x18014e9cf  jnz     short loc_18014EA19
0x18014e9d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014e9d8  nop     dword ptr [rax+rax+00h]
0x18014e9dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014e9e4  mov     rcx, rax
0x18014e9e7  test    rax, rax
0x18014e9ea  jz      short loc_18014EA0B
0x18014e9ec  mov     rax, [rax]
0x18014e9ef  mov     edx, 7F0h
0x18014e9f4  mov     rax, [rax+8]
0x18014e9f8  call    cs:__guard_dispatch_icall_fptr
0x18014e9fe  test    eax, eax
0x18014ea00  jz      short loc_18014EA0B
0x18014ea02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ea09  jmp     short loc_18014EA19
0x18014ea0b  lea     rcx, qword_1803CE250; this
0x18014ea12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ea19  cmp     byte ptr [rcx+8], 0
0x18014ea1d  jz      short loc_18014EA40
0x18014ea1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014ea24  cmp     [rax+7CCh], edi
0x18014ea2a  jz      short loc_18014EA40
0x18014ea2c  mov     r9d, edi; int
0x18014ea2f  mov     r8d, 313h; int
0x18014ea35  mov     rdx, r12; char *
0x18014ea38  mov     rcx, rax; this
0x18014ea3b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
