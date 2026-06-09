# MFCreateAudioRenderer

- ea: `0x1801a01b0`
- end: `0x1801a0d04`
- name: `MFCreateAudioRenderer`
- size: `2900`
- prototype: `HRESULT __stdcall(IMFAttributes *pAudioAttributes, IMFMediaSink **ppSink)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1802126c0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x18007cae0`
- `0x180091eb0`
- `0x180092630`
- `0x18009302c`
- `0x18009efc4`
- `0x1800cac5c`
- `0x1800ec0e0`
- `0x18013577c`
- `0x1801a01b0`
- `0x18025839c`
- `0x1802583a8`
- `0x1802583e8`
- `0x180258480`
- `0x1802592a0`
- `0x18031794c`
- `0x180317bd0`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0c9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a0c9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0314`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a04ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a06c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0959`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0a22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0b5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0bfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0314`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a04ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a06c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0959`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0a22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0b5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801a0bfa`

## string_xrefs

- `0x1801a0287`: `MFCreateAudioRenderer`
- `0x1801a0372`: `MFCreateAudioRenderer`
- `0x1801a0548`: `MFCreateAudioRenderer`
- `0x1801a0724`: `MFCreateAudioRenderer`
- `0x1801a09b7`: `MFCreateAudioRenderer`
- `0x1801a0a80`: `MFCreateAudioRenderer`
- `0x1801a0bbb`: `MFCreateAudioRenderer`
- `0x1801a0c58`: `MFCreateAudioRenderer`
- `0x1801a0b17`: `CCreateAudioDevice::CreateAudioRenderer`

## pseudocode

```c
HRESULT __stdcall MFCreateAudioRenderer(IMFAttributes *pAudioAttributes, IMFMediaSink **ppSink)
{
  CBaseUnknown *v4; // r14
  void *v5; // r12
  const char *String; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 *v9; // rcx
  int Instance; // edi
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  int v14; // eax
  int v15; // ecx
  bool v16; // sf
  struct IMFAttributesVtbl *lpVtbl; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 *v20; // rcx
  int v21; // ebx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  int v40; // eax
  int v41; // ecx
  CCreateAudioDevice *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  struct IMFTelemetrySession *v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  _BYTE v55[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v56; // [rsp+34h] [rbp-CCh] BYREF
  int v57; // [rsp+3Ch] [rbp-C4h] BYREF
  int v58; // [rsp+40h] [rbp-C0h] BYREF
  int v59; // [rsp+44h] [rbp-BCh] BYREF
  int v60; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v61; // [rsp+4Ch] [rbp-B4h] BYREF
  int v62; // [rsp+50h] [rbp-B0h] BYREF
  int v63; // [rsp+54h] [rbp-ACh] BYREF
  int v64; // [rsp+58h] [rbp-A8h] BYREF
  int v65; // [rsp+5Ch] [rbp-A4h] BYREF
  int v66; // [rsp+60h] [rbp-A0h] BYREF
  int v67; // [rsp+64h] [rbp-9Ch] BYREF
  int v68; // [rsp+68h] [rbp-98h] BYREF
  int v69; // [rsp+6Ch] [rbp-94h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  int v71; // [rsp+78h] [rbp-88h] BYREF
  struct IMFTelemetrySession *v72; // [rsp+80h] [rbp-80h] BYREF
  __int64 v73; // [rsp+88h] [rbp-78h] BYREF
  double v74; // [rsp+90h] [rbp-70h] BYREF
  double v75; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v76[192]; // [rsp+A0h] [rbp-60h] BYREF
  GUID Buf1; // [rsp+160h] [rbp+60h] BYREF
  int v78; // [rsp+170h] [rbp+70h]
  LPVOID v79; // [rsp+178h] [rbp+78h]
  int v80; // [rsp+180h] [rbp+80h]
  int v81; // [rsp+184h] [rbp+84h]
  unsigned int v82; // [rsp+188h] [rbp+88h]
  int v83; // [rsp+18Ch] [rbp+8Ch]
  int v84; // [rsp+190h] [rbp+90h]
  __int64 v85; // [rsp+198h] [rbp+98h]
  BOOL v86; // [rsp+1A0h] [rbp+A0h]
  BOOL v87; // [rsp+1A4h] [rbp+A4h]
  BOOL v88; // [rsp+1A8h] [rbp+A8h]
  BOOL v89; // [rsp+1ACh] [rbp+ACh]
  BOOL v90; // [rsp+1B0h] [rbp+B0h]
  BOOL v91; // [rsp+1B4h] [rbp+B4h]
  BOOL v92; // [rsp+1B8h] [rbp+B8h]
  BOOL v93; // [rsp+1BCh] [rbp+BCh]
  BOOL v94; // [rsp+1C0h] [rbp+C0h]
  int v95; // [rsp+1C4h] [rbp+C4h]
  float v96; // [rsp+1C8h] [rbp+C8h]
  float v97; // [rsp+1CCh] [rbp+CCh]
  int v98; // [rsp+1D0h] [rbp+D0h]
  void *v99; // [rsp+1D8h] [rbp+D8h]
  GUID v100; // [rsp+1E0h] [rbp+E0h] BYREF

  v57 = 0;
  v100 = GUID_00000000_0000_0000_0000_000000000000;
  v75 = DOUBLE_2_0;
  v74 = 0.0;
  v4 = 0;
  v72 = 0;
  pv = 0;
  v5 = 0;
  v71 = 0;
  v61 = 0;
  v60 = 0;
  v73 = 0;
  v58 = 0;
  v59 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v56 = 0;
  memset_0(&Buf1, 0, 0x80u);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v55, "MFCreateAudioRenderer", 145);
  if ( pAudioAttributes && (unsigned __int8)byte_1803CECE9 >= 0x10u )
  {
    CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v76, pAudioAttributes);
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    {
      String = CMFAttributesTrace::GetString((CMFAttributesTrace *)v76, 0);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, &WPP_117665aa0ae6393924a62465530b37c0_Traceguids, String);
    }
    CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v76);
  }
  memset_0(&Buf1, 0, 0x80u);
  if ( !ppSink )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    Instance = -2147467261;
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFCreateAudioRenderer", 155, -2147467261);
    }
    if ( g_wppLevels )
    {
      v13 = 14;
LABEL_17:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_117665aa0ae6393924a62465530b37c0_Traceguids, 0, Instance);
      goto LABEL_137;
    }
    goto LABEL_137;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SAR_DynamicSpatialNonSpatialFormatChange>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SAR_DynamicSpatialNonSpatialFormatChange>::GetImpl'::`2'::impl) )
  {
    v94 = 1;
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_117665aa0ae6393924a62465530b37c0_Traceguids);
  }
  if ( !pAudioAttributes )
    goto LABEL_113;
  v14 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
          pAudioAttributes,
          &MF_AUDIO_RENDERER_ATTRIBUTE_FLAGS,
          &v57);
  v15 = v78;
  v16 = v14 < 0;
  lpVtbl = pAudioAttributes->lpVtbl;
  if ( !v16 )
    v15 = v57;
  v78 = v15;
  if ( ((int (__fastcall *)(IMFAttributes *, const IID *, GUID *))lpVtbl->GetGUID)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_SESSION_ID,
         &v100) >= 0 )
    Buf1 = v100;
  if ( !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) && (v78 & 1) != 0 )
    v78 ^= 1u;
  ((void (__fastcall *)(IMFAttributes *, GUID *, GUID *, struct IMFTelemetrySession **))pAudioAttributes->lpVtbl->GetUnknown)(
    pAudioAttributes,
    &GUID_627d2ca6_e1cd_4898_999d_101308f1d431,
    &GUID_627d2ca6_e1cd_4898_999d_101308f1d431,
    &v72);
  if ( ((int (__fastcall *)(IMFAttributes *, const IID *, LPVOID *, int *))pAudioAttributes->lpVtbl->GetAllocatedString)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_ENDPOINT_ID,
         &pv,
         &v71) >= 0
    && ((int (__fastcall *)(IMFAttributes *, const IID *, char *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_ENDPOINT_ROLE,
         (char *)&v56 + 4) >= 0 )
  {
    v20 = (__int64 *)CallStackTracing::s_wpInstance;
    v21 = -2147024809;
    Instance = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v23 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v23, "MFCreateAudioRenderer", 193, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_137;
    v24 = 16;
    goto LABEL_136;
  }
  if ( pv )
  {
    v79 = pv;
  }
  else if ( ((int (__fastcall *)(IMFAttributes *, const IID *, char *))pAudioAttributes->lpVtbl->GetUINT32)(
              pAudioAttributes,
              &MF_AUDIO_RENDERER_ATTRIBUTE_ENDPOINT_ROLE,
              (char *)&v56 + 4) >= 0 )
  {
    v80 = HIDWORD(v56);
    v81 = 1;
  }
  if ( ((int (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_ONLY_AUDIO,
         &v58) >= 0 )
    v86 = v58 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_DISABLE_OFFLOAD,
         &v59) >= 0 )
    v87 = v59 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_LOW_LATENCY,
         &v60) >= 0 )
  {
    if ( v60 )
    {
      v83 = 1;
      v87 = 1;
    }
    else
    {
      v83 = 0;
    }
  }
  if ( ((int (__fastcall *)(IMFAttributes *, void *, __int64 *))pAudioAttributes->lpVtbl->GetUINT64)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_BUFFER_DURATION,
         &v73) >= 0 )
  {
    v85 = v73;
    v84 = 1;
  }
  if ( ((int (__fastcall *)(IMFAttributes *, const IID *, unsigned int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_STREAM_CATEGORY,
         &v61) >= 0 )
  {
    if ( v61 >= 0xF )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      v21 = -2147024809;
      Instance = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v29, "MFCreateAudioRenderer", 245, -2147024809);
      }
      if ( !g_wppLevels )
        goto LABEL_137;
      v24 = 17;
      goto LABEL_136;
    }
    v82 = v61;
  }
  if ( ((int (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_LIVE_STREAM,
         &v62) >= 0 )
    v88 = v62 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_FILL_SILENCE_WHEN_STARVING,
         &v63) >= 0 )
    v89 = v63 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_FILL_COMPRESSED_SILENCE_WHEN_STARVING,
         &v64) >= 0 )
    v90 = v64 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_ENABLE_DYNAMIC_AUDIO_FORMAT_CHANGE,
         &v65) >= 0 )
    v91 = v65 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_ENABLE_SPATIAL_DYNAMIC_FORMAT_CHANGE,
         &v66) >= 0 )
    v94 = v66 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_DO_NOT_EXPOSE_CLOCK,
         &v67) >= 0 )
    v92 = v67 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_DROP_LATE_DATA,
         &v68) >= 0 )
    v93 = v68 != 0;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, double *))pAudioAttributes->lpVtbl->GetDouble)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_MAXIMUM_RATE_OVERRIDE,
         &v74) >= 0 )
    v96 = v74;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, double *))pAudioAttributes->lpVtbl->GetDouble)(
         pAudioAttributes,
         &MF_AUDIO_RENDERER_ATTRIBUTE_MAXIMUM_COMPRESSED_AUDIO_RATE_OVERRIDE,
         &v75) >= 0 )
    v97 = v75;
  if ( ((int (__fastcall *)(IMFAttributes *, void *, unsigned __int64 *))pAudioAttributes->lpVtbl->GetBlobSize)(
         pAudioAttributes,
         &MF_SD_AMBISONICS_SAMPLE3D_DESCRIPTION,
         &v56) < 0 )
  {
LABEL_110:
    v40 = ((__int64 (__fastcall *)(IMFAttributes *, void *, int *))pAudioAttributes->lpVtbl->GetUINT32)(
            pAudioAttributes,
            &MF_AUDIO_RENDERER_ATTRIBUTE_DISABLE_EXCLUSIVE_MODE,
            &v69);
    v41 = v95;
    if ( v40 >= 0 )
      v41 = v69;
    v95 = v41;
LABEL_113:
    v42 = (CCreateAudioDevice *)operator new(0x10u);
    if ( v42 )
    {
      v4 = CCreateAudioDevice::CCreateAudioDevice(v42);
      if ( v4 )
      {
        v45 = v72;
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)v55,
          "CCreateAudioDevice::CreateAudioRenderer",
          80);
        Instance = CAudioMediaSink::CreateInstance((const struct SARPARAMS *)&Buf1, v45, ppSink);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v55);
        if ( Instance < 0 )
        {
          v48 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47);
            CallStackTracing::s_wpInstance = v49;
            if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
            {
              v48 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v48 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v48 + 8) )
          {
            v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
            if ( *((_DWORD *)v50 + 499) != Instance )
              CallStackContext::TraceFailure(v50, "MFCreateAudioRenderer", 330, Instance);
          }
          if ( g_wppLevels )
          {
            v13 = 21;
            goto LABEL_17;
          }
        }
        goto LABEL_137;
      }
    }
    v51 = (__int64 *)CallStackTracing::s_wpInstance;
    v21 = -2147024882;
    Instance = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44);
      CallStackTracing::s_wpInstance = v52;
      if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
      {
        v51 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v51 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v51 + 8) )
    {
      v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
      if ( *((_DWORD *)v53 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v53, "MFCreateAudioRenderer", 328, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_137;
    v24 = 20;
LABEL_136:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_117665aa0ae6393924a62465530b37c0_Traceguids, 0, v21);
    goto LABEL_137;
  }
  v5 = operator new[]((unsigned int)v56);
  if ( !v5 )
  {
    v32 = (__int64 *)CallStackTracing::s_wpInstance;
    v21 = -2147024882;
    Instance = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31);
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)v34 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v34, "MFCreateAudioRenderer", 311, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_137;
    v24 = 18;
    goto LABEL_136;
  }
  Instance = ((__int64 (__fastcall *)(IMFAttributes *, void *, void *, _QWORD, unsigned __int64 *))pAudioAttributes->lpVtbl->GetBlob)(
               pAudioAttributes,
               &MF_SD_AMBISONICS_SAMPLE3D_DESCRIPTION,
               v5,
               (unsigned int)v56,
               &v56);
  if ( Instance >= 0 )
  {
    v98 = v56;
    v99 = v5;
    goto LABEL_110;
  }
  v37 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36);
    CallStackTracing::s_wpInstance = v38;
    if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
    {
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v37 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v37 + 8) )
  {
    v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
    if ( *((_DWORD *)v39 + 499) != Instance )
      CallStackContext::TraceFailure(v39, "MFCreateAudioRenderer", 314, Instance);
  }
  if ( g_wppLevels )
  {
    v13 = 19;
    goto LABEL_17;
  }
LABEL_137:
  CoTaskMemFree(pv);
  pv = 0;
  if ( v4 )
    CBaseUnknown::Release(v4);
  operator delete(v5);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v55);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v72);
  return Instance;
}

```

## disassembly

```asm
0x1801a01b0  mov     [rsp-8+arg_10], rbx
0x1801a01b5  push    rbp
0x1801a01b6  push    rsi
0x1801a01b7  push    rdi
0x1801a01b8  push    r12
0x1801a01ba  push    r13
0x1801a01bc  push    r14
0x1801a01be  push    r15
0x1801a01c0  lea     rbp, [rsp-100h]
0x1801a01c8  sub     rsp, 200h
0x1801a01cf  mov     rax, cs:__security_cookie
0x1801a01d6  xor     rax, rsp
0x1801a01d9  mov     [rbp+130h+var_40], rax
0x1801a01e0  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1801a01e7  xor     r13d, r13d
0x1801a01ea  mov     r15, rdx
0x1801a01ed  mov     rbx, rcx
0x1801a01f0  mov     [rsp+230h+var_1F4], r13d
0x1801a01f5  movdqu  [rbp+130h+var_50], xmm0
0x1801a01fd  lea     rcx, [rbp+130h+Buf1]; void *
0x1801a0201  mov     edi, 80h
0x1801a0206  movsd   xmm0, cs:__real@4000000000000000
0x1801a020e  xorps   xmm1, xmm1
0x1801a0211  mov     r8d, edi; Size
0x1801a0214  movsd   [rbp+130h+var_198], xmm0
0x1801a0219  xor     edx, edx; Val
0x1801a021b  movsd   [rbp+130h+var_1A0], xmm1
0x1801a0220  mov     r14d, r13d
0x1801a0223  mov     [rbp+130h+var_1B0], r13
0x1801a0227  mov     [rsp+230h+pv], r13
0x1801a022c  mov     r12d, r13d
0x1801a022f  mov     [rsp+230h+var_1B8], r13d
0x1801a0234  mov     dword ptr [rsp+230h+var_1FC+4], r13d
0x1801a0239  mov     [rsp+230h+var_1E4], r13d
0x1801a023e  mov     [rsp+230h+var_1E8], r13d
0x1801a0243  mov     [rbp+130h+var_1A8], r13
0x1801a0247  mov     [rsp+230h+var_1F0], r13d
0x1801a024c  mov     [rsp+230h+var_1EC], r13d
0x1801a0251  mov     [rsp+230h+var_1E0], r13d
0x1801a0256  mov     [rsp+230h+var_1DC], r13d
0x1801a025b  mov     [rsp+230h+var_1D8], r13d
0x1801a0260  mov     [rsp+230h+var_1D4], r13d
0x1801a0265  mov     [rsp+230h+var_1D0], r13d
0x1801a026a  mov     [rsp+230h+var_1CC], r13d
0x1801a026f  mov     [rsp+230h+var_1C8], r13d
0x1801a0274  mov     [rsp+230h+var_1C4], r13d
0x1801a0279  mov     dword ptr [rsp+230h+var_1FC], r13d
0x1801a027e  call    memset_0
0x1801a0283  lea     r8d, [rdi+11h]; int
0x1801a0287  lea     rdx, aMfcreateaudior_1; "MFCreateAudioRenderer"
0x1801a028e  lea     rcx, [rsp+230h+var_200]; this
0x1801a0293  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801a0298  test    rbx, rbx
0x1801a029b  jz      short loc_1801A02EC
0x1801a029d  cmp     cs:byte_1803CECE9, 10h
0x1801a02a4  jb      short loc_1801A02EC
0x1801a02a6  mov     rdx, rbx; struct IMFAttributes *
0x1801a02a9  lea     rcx, [rbp+130h+var_190]; this
0x1801a02ad  call    ??0CMFAttributesTrace@@QEAA@PEAUIMFAttributes@@@Z; CMFAttributesTrace::CMFAttributesTrace(IMFAttributes *)
0x1801a02b2  cmp     cs:byte_1803CECE9, 10h
0x1801a02b9  jb      short loc_1801A02E3
0x1801a02bb  xor     edx, edx; bool
0x1801a02bd  lea     rcx, [rbp+130h+var_190]; this
0x1801a02c1  call    ?GetString@CMFAttributesTrace@@QEAAPEBD_N@Z; CMFAttributesTrace::GetString(bool)
0x1801a02c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a02cd  lea     edx, [rdi-73h]
0x1801a02d0  mov     r9, rax
0x1801a02d3  lea     r8, WPP_117665aa0ae6393924a62465530b37c0_Traceguids
0x1801a02da  mov     rcx, [rcx+38h]
0x1801a02de  call    WPP_SF_s
0x1801a02e3  lea     rcx, [rbp+130h+var_190]; this
0x1801a02e7  call    ??1CMFAttributesTrace@@QEAA@XZ; CMFAttributesTrace::~CMFAttributesTrace(void)
0x1801a02ec  mov     r8, rdi; Size
0x1801a02ef  lea     rcx, [rbp+130h+Buf1]; void *
0x1801a02f3  xor     edx, edx; Val
0x1801a02f5  call    memset_0
0x1801a02fa  test    r15, r15
0x1801a02fd  jnz     loc_1801A03A5
0x1801a0303  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a030a  mov     edi, 80004003h
0x1801a030f  test    rcx, rcx
0x1801a0312  jnz     short loc_1801A035C
0x1801a0314  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801a031b  nop     dword ptr [rax+rax+00h]
0x1801a0320  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a0327  mov     rcx, rax
0x1801a032a  test    rax, rax
0x1801a032d  jz      short loc_1801A034E
0x1801a032f  mov     rax, [rax]
0x1801a0332  mov     edx, 7F0h
0x1801a0337  mov     rax, [rax+8]
0x1801a033b  call    cs:__guard_dispatch_icall_fptr
0x1801a0341  test    eax, eax
0x1801a0343  jz      short loc_1801A034E
0x1801a0345  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a034c  jmp     short loc_1801A035C
0x1801a034e  lea     rcx, qword_1803CE250; this
0x1801a0355  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a035c  cmp     [rcx+8], r13b
0x1801a0360  jz      short loc_1801A0387
0x1801a0362  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801a0367  cmp     [rax+7CCh], edi
0x1801a036d  jz      short loc_1801A0387
0x1801a036f  mov     r9d, edi; int
0x1801a0372  lea     rdx, aMfcreateaudior_1; "MFCreateAudioRenderer"
0x1801a0379  mov     r8d, 9Bh; int
0x1801a037f  mov     rcx, rax; this
0x1801a0382  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801a0387  mov     esi, 1
0x1801a038c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1801a0393  jb      loc_1801A0C99
0x1801a0399  lea     edx, [rsi+0Dh]
0x1801a039c  mov     dword ptr [rsp+230h+var_210], edi
0x1801a03a0  jmp     loc_1801A0C7F
0x1801a03a5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SAR_DynamicSpatialNonSpatialFormatChange@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SAR_DynamicSpatialNonSpatialFormatChange@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SAR_DynamicSpatialNonSpatialFormatChange> `wil::Feature<__WilFeatureTraits_Feature_SAR_DynamicSpatialNonSpatialFormatChange>::GetImpl(void)'::`2'::impl
0x1801a03ac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SAR_DynamicSpatialNonSpatialFormatChange@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SAR_DynamicSpatialNonSpatialFormatChange>::__private_IsEnabled(void)
0x1801a03b1  mov     esi, 1
0x1801a03b6  test    al, al
0x1801a03b8  jz      short loc_1801A03E3
0x1801a03ba  mov     [rbp+130h+var_70], esi
0x1801a03c0  cmp     cs:byte_1803CECE9, 10h
0x1801a03c7  jb      short loc_1801A03E3
0x1801a03c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a03d0  lea     edx, [rsi+0Eh]
0x1801a03d3  lea     r8, WPP_117665aa0ae6393924a62465530b37c0_Traceguids
0x1801a03da  mov     rcx, [rcx+38h]
0x1801a03de  call    WPP_SF_
0x1801a03e3  test    rbx, rbx
0x1801a03e6  jz      loc_1801A0AEC
0x1801a03ec  mov     rax, [rbx]
0x1801a03ef  lea     r8, [rsp+230h+var_1F4]
0x1801a03f4  lea     rdx, MF_AUDIO_RENDERER_ATTRIBUTE_FLAGS
0x1801a03fb  mov     rcx, rbx
0x1801a03fe  mov     rax, [rax+38h]
0x1801a0402  call    cs:__guard_dispatch_icall_fptr
0x1801a0408  mov     ecx, [rbp+130h+var_C0]
0x1801a040b  lea     r8, [rbp+130h+var_50]
0x1801a0412  test    eax, eax
0x1801a0414  lea     rdx, MF_AUDIO_RENDERER_ATTRIBUTE_SESSION_ID
0x1801a041b  mov     rax, [rbx]
0x1801a041e  cmovns  ecx, [rsp+230h+var_1F4]
0x1801a0423  mov     [rbp+130h+var_C0], ecx
0x1801a0426  mov     rcx, rbx
0x1801a0429  mov     rax, [rax+50h]
0x1801a042d  call    cs:__guard_dispatch_icall_fptr
0x1801a0433  test    eax, eax
0x1801a0435  js      short loc_1801A0442
0x1801a0437  movups  xmm0, [rbp+130h+var_50]
0x1801a043e  movups  [rbp+130h+Buf1], xmm0
0x1801a0442  mov     r8d, 10h; Size
0x1801a0448  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1801a044f  lea     rcx, [rbp+130h+Buf1]; Buf1
0x1801a0453  call    memcmp_0
0x1801a0458  test    eax, eax
0x1801a045a  jnz     short loc_1801A0469
0x1801a045c  mov     eax, [rbp+130h+var_C0]
0x1801a045f  test    sil, al
0x1801a0462  jz      short loc_1801A0469
0x1801a0464  xor     eax, esi
0x1801a0466  mov     [rbp+130h+var_C0], eax
0x1801a0469  mov     rax, [rbx]
0x1801a046c  lea     rdx, _GUID_627d2ca6_e1cd_4898_999d_101308f1d431
0x1801a0473  lea     r9, [rbp+130h+var_1B0]
0x1801a0477  mov     r8, rdx
0x1801a047a  mov     rcx, rbx
0x1801a047d  mov     rax, [rax+88h]
0x1801a0484  call    cs:__guard_dispatch_icall_fptr
0x1801a048a  mov     rax, [rbx]
0x1801a048d  lea     r9, [rsp+230h+var_1B8]
0x1801a0492  lea     r8, [rsp+230h+pv]
0x1801a0497  mov     rcx, rbx
0x1801a049a  lea     rdx, MF_AUDIO_RENDERER_ATTRIBUTE_ENDPOINT_ID
0x1801a04a1  mov     rax, [rax+68h]
0x1801a04a5  call    cs:__guard_dispatch_icall_fptr
0x1801a04ab  test    eax, eax
0x1801a04ad  js      loc_1801A0574
0x1801a04b3  mov     rax, [rbx]
0x1801a04b6  lea     r8, [rsp+230h+var_1FC+4]
0x1801a04bb  lea     rdx, MF_AUDIO_RENDERER_ATTRIBUTE_ENDPOINT_ROLE
0x1801a04c2  mov     rcx, rbx
0x1801a04c5  mov     rax, [rax+38h]
0x1801a04c9  call    cs:__guard_dispatch_icall_fptr
0x1801a04cf  test    eax, eax
0x1801a04d1  js      loc_1801A0574
0x1801a04d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a04de  mov     ebx, 80070057h
0x1801a04e3  mov     edi, ebx
0x1801a04e5  test    rcx, rcx
0x1801a04e8  jnz     short loc_1801A0532
0x1801a04ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801a04f1  nop     dword ptr [rax+rax+00h]
0x1801a04f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a04fd  mov     rcx, rax
0x1801a0500  test    rax, rax
0x1801a0503  jz      short loc_1801A0524
0x1801a0505  mov     rax, [rax]
0x1801a0508  mov     edx, 7F0h
0x1801a050d  mov     rax, [rax+8]
0x1801a0511  call    cs:__guard_dispatch_icall_fptr
0x1801a0517  test    eax, eax
0x1801a0519  jz      short loc_1801A0524
0x1801a051b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a0522  jmp     short loc_1801A0532
0x1801a0524  lea     rcx, qword_1803CE250; this
0x1801a052b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a0532  cmp     [rcx+8], r13b
0x1801a0536  jz      short loc_1801A055D
0x1801a0538  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801a053d  cmp     [rax+7CCh], ebx
0x1801a0543  jz      short loc_1801A055D
0x1801a0545  mov     r9d, ebx; int
0x1801a0548  lea     rdx, aMfcreateaudior_1; "MFCreateAudioRenderer"
0x1801a054f  mov     r8d, 0C1h; int
0x1801a0555  mov     rcx, rax; this
0x1801a0558  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801a055d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1801a0564  jb      loc_1801A0C99
0x1801a056a  mov     edx, 10h
0x1801a056f  jmp     loc_1801A0C7B
0x1801a0574  mov     rax, [rsp+230h+pv]
0x1801a0579  test    rax, rax
0x1801a057c  jz      short loc_1801A0584
0x1801a057e  mov     [rbp+130h+var_B8], rax
0x1801a0582  jmp     short loc_1801A05B4
0x1801a0584  mov     rax, [rbx]
0x1801a0587  lea     r8, [rsp+230h+var_1FC+4]
0x1801a058c  lea     rdx, MF_AUDIO_RENDERER_ATTRIBUTE_ENDPOINT_ROLE
0x1801a0593  mov     rcx, rbx
0x1801a0596  mov     rax, [rax+38h]
0x1801a059a  call    cs:__guard_dispatch_icall_fptr
0x1801a05a0  test    eax, eax
0x1801a05a2  js      short loc_1801A05B4
0x1801a05a4  mov     eax, dword ptr [rsp+230h+var_1FC+4]
0x1801a05a8  mov     [rbp+130h+var_B0], eax
0x1801a05ae  mov     [rbp+130h+var_AC], esi
0x1801a05b4  mov     rax, [rbx]
0x1801a05b7  lea     r8, [rsp+230h+var_1F0]
0x1801a05bc  lea     rdx, MF_AUDIO_RENDERER_ATTRIBUTE_ONLY_AUDIO
0x1801a05c3  mov     rcx, rbx
0x1801a05c6  mov     rax, [rax+38h]
0x1801a05ca  call    cs:__guard_dispatch_icall_fptr
0x1801a05d0  test    eax, eax
0x1801a05d2  js      short loc_1801A05E5
0x1801a05d4  cmp     [rsp+230h+var_1F0], r13d
0x1801a05d9  mov     eax, r13d
0x1801a05dc  setnz   al
0x1801a05df  mov     [rbp+130h+var_90], eax
0x1801a05e5  mov     rax, [rbx]
0x1801a05e8  lea     r8, [rsp+230h+var_1EC]
0x1801a05ed  lea     rdx, MF_AUDIO_RENDERER_ATTRIBUTE_DISABLE_OFFLOAD
0x1801a05f4  mov     rcx, rbx
0x1801a05f7  mov     rax, [rax+38h]
0x1801a05fb  call    cs:__guard_dispatch_icall_fptr
0x1801a0601  test    eax, eax
0x1801a0603  js      short loc_1801A0616
0x1801a0605  cmp     [rsp+230h+var_1EC], r13d
0x1801a060a  mov     eax, r13d
0x1801a060d  setnz   al
0x1801a0610  mov     [rbp+130h+var_8C], eax
0x1801a0616  mov     rax, [rbx]
0x1801a0619  lea     r8, [rsp+230h+var_1E8]
0x1801a061e  lea     rdx, MF_LOW_LATENCY
0x1801a0625  mov     rcx, rbx
0x1801a0628  mov     rax, [rax+38h]
0x1801a062c  call    cs:__guard_dispatch_icall_fptr
0x1801a0632  test    eax, eax
0x1801a0634  js      short loc_1801A0652
0x1801a0636  cmp     [rsp+230h+var_1E8], r13d
0x1801a063b  jz      short loc_1801A064B
0x1801a063d  mov     [rbp+130h+var_A4], esi
0x1801a0643  mov     [rbp+130h+var_8C], esi
0x1801a0649  jmp     short loc_1801A0652
0x1801a064b  mov     [rbp+130h+var_A4], r13d
0x1801a0652  mov     rax, [rbx]
0x1801a0655  lea     r8, [rbp+130h+var_1A8]
0x1801a0659  lea     rdx, MF_AUDIO_RENDERER_ATTRIBUTE_BUFFER_DURATION
0x1801a0660  mov     rcx, rbx
0x1801a0663  mov     rax, [rax+40h]
0x1801a0667  call    cs:__guard_dispatch_icall_fptr
0x1801a066d  test    eax, eax
0x1801a066f  js      short loc_1801A0682
0x1801a0671  mov     rax, [rbp+130h+var_1A8]
0x1801a0675  mov     [rbp+130h+var_98], rax
0x1801a067c  mov     [rbp+130h+var_A0], esi
0x1801a0682  mov     rax, [rbx]
0x1801a0685  lea     r8, [rsp+230h+var_1E4]
0x1801a068a  lea     rdx, MF_AUDIO_RENDERER_ATTRIBUTE_STREAM_CATEGORY
0x1801a0691  mov     rcx, rbx
0x1801a0694  mov     rax, [rax+38h]
0x1801a0698  call    cs:__guard_dispatch_icall_fptr
0x1801a069e  test    eax, eax
0x1801a06a0  js      loc_1801A0756
0x1801a06a6  mov     eax, [rsp+230h+var_1E4]
0x1801a06aa  cmp     eax, 0Fh
0x1801a06ad  jb      loc_1801A0750
0x1801a06b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801a06ba  mov     ebx, 80070057h
0x1801a06bf  mov     edi, ebx
0x1801a06c1  test    rcx, rcx
0x1801a06c4  jnz     short loc_1801A070E
  ... truncated ...
```
