# CPipeManager::CreateProcessor(PipelineProcessor,IRdpProcessor * *)

- ea: `0x18008eb60`
- end: `0x18008f852`
- name: `?CreateProcessor@CPipeManager@@IEAAJW4PipelineProcessor@@PEAPEAVIRdpProcessor@@@Z`
- size: `3314`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008f858`
- `0x180090d1c`

## callees

- `0x18000116c`
- `0x180001308`
- `0x18000202c`
- `0x18000ce04`
- `0x18000ce34`
- `0x18008eb60`
- `0x180091b5c`
- `0x1800c2ee8`
- `0x1800c38a8`
- `0x1800c51a0`
- `0x1800c6ac8`
- `0x1800c83f0`
- `0x1800c8d38`
- `0x1800c9ae8`
- `0x1800ca1f8`
- `0x1800cacd8`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x18008ebf4`: `Gfx pipe extension factory is NULL.`
- `0x18008ec0d`: `CreateProcessor`
- `0x18008ecaf`: `CreateProcessor`
- `0x18008ed71`: `CreateProcessor`
- `0x18008ee5a`: `CreateProcessor`
- `0x18008ef29`: `CreateProcessor`
- `0x18008f012`: `CreateProcessor`
- `0x18008f0d4`: `CreateProcessor`
- `0x18008f1b6`: `CreateProcessor`
- `0x18008f29f`: `CreateProcessor`
- `0x18008f35e`: `CreateProcessor`
- `0x18008f41e`: `CreateProcessor`
- `0x18008f507`: `CreateProcessor`
- `0x18008f5f0`: `CreateProcessor`
- `0x18008f6d9`: `CreateProcessor`
- `0x18008f7c9`: `CreateProcessor`
- `0x18008ec96`: `CreateVideoProcessor failed.`
- `0x18008ed30`: `PipeManagerError_CreateProcessorCreateVideoProcFail`
- `0x18008edd2`: `Frame: VideoProcessor::CreateInstance successfully completed`
- `0x18008eee8`: `PipeManagerError_CreateProcessorCreateDeltaReducerProcFail`
- `0x18008ef10`: `DeltaReducerProcessor::CreateInstance failed!`
- `0x18008ef8a`: `Frame: DeltaProcessor::CreateInstance successfully completed`
- `0x18008ee19`: `PipeManagerError_CreateProcessorCreateVideoDetectorFail`
- `0x18008ee41`: `VideoDetectorProcessor::CreateInstance failed!`
- `0x18008eebf`: `Frame: VideoDetectionProcessor::CreateInstance successfully completed`
- `0x18008f25e`: `PipeManagerError_CreateProcessorCreateMotionProcFail`
- `0x18008f286`: `MotionDetectionProcessor::CreateInstance failed!`
- `0x18008f300`: `Frame: MotionDetectionProcessor::CreateInstance successfully completed`
- `0x18008f698`: `PipeManagerError_CreateProcessorCreateCacheProcFail`
- `0x18008f6c0`: `Failed to create cache processor`
- `0x18008f73a`: `Frame: CacheProcessor::CreateInstance successfully completed`
- `0x18008f5af`: `PipeManagerError_CreateProcessorCreateClassifierProcFail`
- `0x18008f5d7`: `Classifier CreateInstance failed`
- `0x18008f651`: `Frame: ClassifierProcessor::CreateInstance successfully completed`
- `0x18008f4c6`: `PipeManagerError_CreateProcessorCreateCodecProcFail`
- `0x18008f4ee`: `Failed to create codec Processor`
- `0x18008f568`: `Frame: CodecProcessor::CreateInstance successfully completed`
- `0x18008f3dd`: `PipeManagerError_CreateProcessorCreateLegacyProcFail`
- `0x18008f405`: `Failed to create legacy processor`
- `0x18008f47f`: `Frame: LegacyProcessor_CreateInstance successfully completed`
- `0x18008f175`: `PipeManagerError_CreateProcessorCreatePrimitiveProcFail`
- `0x18008f19d`: `PrimitiveProcessor::CreateInstance failed!`
- `0x18008f217`: `Frame: PrimitiveProcessor::CreateInstance successfully completed`
- `0x18008efd1`: `PipeManagerError_CreateProcessorCreateFbrProcFail`
- `0x18008f093`: `PipeManagerError_CreateProcessorCreateFbrProcFail`
- `0x18008eff9`: `FbrProcessor::CreateInstance failed!`
- `0x18008f135`: `Frame: CFbrProcessor_CreateInstance successfully completed`

## pseudocode

```c
__int64 __fastcall CPipeManager::CreateProcessor(__int64 a1, int a2, struct IRdpProcessor **a3)
{
  const struct _GUID *v6; // rdx
  struct IUnknown *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  __int64 v13; // rcx
  signed int v14; // ebx
  __int16 *v15; // rdx
  const char **v16; // rax
  signed int v17; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  unsigned int v21; // edi
  signed int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  const char *v26; // rax
  int *v27; // rdx
  signed int v28; // eax
  signed int v29; // eax
  signed int v30; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  signed int v34; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  signed int v38; // eax
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  int v42; // ebx
  int v43; // ebx
  int v44; // ebx
  signed int v45; // eax
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  signed int v49; // eax
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  signed int v53; // eax
  int v54; // ecx
  int v55; // r8d
  int v56; // r9d
  signed int Instance; // eax
  int v58; // ecx
  int v59; // r8d
  int v60; // r9d
  char *ProcessorInitErrorName; // rax
  int v63; // [rsp+20h] [rbp-60h]
  const char **v64; // [rsp+30h] [rbp-50h]
  const char **v65; // [rsp+40h] [rbp-40h]
  const char **v66; // [rsp+48h] [rbp-38h]
  struct IRdpProcessor *v67; // [rsp+50h] [rbp-30h] BYREF
  const char *v68; // [rsp+58h] [rbp-28h] BYREF
  const char *v69; // [rsp+60h] [rbp-20h] BYREF
  const char *v70; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v71[2]; // [rsp+70h] [rbp-10h] BYREF
  int v72; // [rsp+A8h] [rbp+28h] BYREF
  const char *v73; // [rsp+B8h] [rbp+38h] BYREF

  v67 = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v67);
  if ( a2 > 5 )
  {
    v42 = a2 - 6;
    if ( !v42 )
    {
      Instance = RdpCacheMan::CreateInstance(*(struct IUnknown **)(a1 + 13016), v6, (void **)&v67);
      v14 = Instance;
      if ( Instance < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_CreateProcessorCreateCacheProcFail",
          (char *)0x20CF,
          Instance,
          v63);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_88;
        v72 = 8400;
        v71[0] = "Failed to create cache processor";
        v15 = &word_1802762D6;
        v70 = "CreateProcessor";
        v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v68 = "Error HResult failed";
        v66 = (const char **)v71;
        v65 = &v70;
        v64 = &v69;
        v16 = &v68;
        goto LABEL_11;
      }
      if ( (unsigned int)CallbackContext > 5 )
      {
        v73 = "Frame: CacheProcessor::CreateInstance successfully completed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v58,
          (unsigned int)&dword_1802762B4,
          v59,
          v60,
          (__int64)&v73);
      }
      v21 = 264;
      goto LABEL_84;
    }
    v43 = v42 - 1;
    if ( !v43 )
    {
      v53 = CImageClassifierProcessor::CreateInstance(*(struct IRDPENCPlatformContext **)(a1 + 13016), &v67);
      v14 = v53;
      if ( v53 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_CreateProcessorCreateClassifierProcFail",
          (char *)0x20DE,
          v53,
          v63);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_88;
        v72 = 8415;
        v71[0] = "Classifier CreateInstance failed";
        v15 = &word_180276266;
        v70 = "CreateProcessor";
        v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v68 = "Error HResult failed";
        v66 = (const char **)v71;
        v65 = &v70;
        v64 = &v69;
        v16 = &v68;
        goto LABEL_11;
      }
      if ( (unsigned int)CallbackContext > 5 )
      {
        v73 = "Frame: ClassifierProcessor::CreateInstance successfully completed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v54,
          (unsigned int)&dword_180276244,
          v55,
          v56,
          (__int64)&v73);
      }
      v21 = 265;
      goto LABEL_84;
    }
    v44 = v43 - 1;
    if ( !v44 )
    {
      v49 = CRdpCodecProcessor_CreateInstance(*(struct IUnknown **)(a1 + 13016), v6, (void **)&v67);
      v14 = v49;
      if ( v49 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_CreateProcessorCreateCodecProcFail",
          (char *)0x20EE,
          v49,
          v63);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_88;
        v72 = 8431;
        v71[0] = "Failed to create codec Processor";
        v15 = &word_1802761F6;
        v70 = "CreateProcessor";
        v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v68 = "Error HResult failed";
        v66 = (const char **)v71;
        v65 = &v70;
        v64 = &v69;
        v16 = &v68;
        goto LABEL_11;
      }
      if ( (unsigned int)CallbackContext > 5 )
      {
        v73 = "Frame: CodecProcessor::CreateInstance successfully completed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v50,
          (unsigned int)&dword_1802761D4,
          v51,
          v52,
          (__int64)&v73);
      }
      v21 = 266;
      goto LABEL_84;
    }
    if ( v44 == 1 )
    {
      v45 = LegacyProcessor::CreateInstance(v7, v6, (void **)&v67);
      v14 = v45;
      if ( v45 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_CreateProcessorCreateLegacyProcFail",
          (char *)0x20FE,
          v45,
          v63);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_88;
        v72 = 8447;
        v71[0] = "Failed to create legacy processor";
        v15 = &word_180276186;
        v70 = "CreateProcessor";
        v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v68 = "Error HResult failed";
        v66 = (const char **)v71;
        v65 = &v70;
        v64 = &v69;
        v16 = &v68;
        goto LABEL_11;
      }
      if ( (unsigned int)CallbackContext > 5 )
      {
        v73 = "Frame: LegacyProcessor_CreateInstance successfully completed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v46,
          (unsigned int)&dword_180276164,
          v47,
          v48,
          (__int64)&v73);
      }
      v21 = 267;
      goto LABEL_84;
    }
LABEL_58:
    v14 = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v72 = 8490;
      v71[0] = "CreateProcessor";
      LODWORD(v73) = -2147024809;
      v70 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v69 = "Unknown processor";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)qword_180275FF0,
        v8,
        v9,
        (__int64)&v69,
        (__int64)&v73,
        (__int64)&v70,
        (__int64)&v72,
        (__int64)v71);
    }
    goto LABEL_88;
  }
  if ( a2 == 5 )
  {
    v38 = MotionDetectionProcessor::CreateInstance(*(struct IRDPENCPlatformContext **)(a1 + 13016), &v67);
    v14 = v38;
    if ( v38 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_CreateProcessorCreateMotionProcFail",
        (char *)0x20BF,
        v38,
        v63);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_88;
      v72 = 8384;
      v71[0] = "MotionDetectionProcessor::CreateInstance failed!";
      v15 = &word_180276346;
      v70 = "CreateProcessor";
      v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v68 = "Error HResult failed";
      v66 = (const char **)v71;
      v65 = &v70;
      v64 = &v69;
      v16 = &v68;
      goto LABEL_11;
    }
    if ( (unsigned int)CallbackContext > 5 )
    {
      v73 = "Frame: MotionDetectionProcessor::CreateInstance successfully completed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v39,
        (unsigned int)&dword_180276324,
        v40,
        v41,
        (__int64)&v73);
    }
    v21 = 263;
    goto LABEL_84;
  }
  if ( !a2 )
  {
    v34 = PrimitiveProcessor::CreateInstance(&v67);
    v14 = v34;
    if ( v34 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_CreateProcessorCreatePrimitiveProcFail",
        (char *)0x210A,
        v34,
        v63);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_88;
      v72 = 8459;
      v71[0] = "PrimitiveProcessor::CreateInstance failed!";
      v15 = &word_180276116;
      v70 = "CreateProcessor";
      v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v68 = "Error HResult failed";
      v66 = (const char **)v71;
      v65 = &v70;
      v64 = &v69;
      v16 = &v68;
      goto LABEL_11;
    }
    if ( (unsigned int)CallbackContext > 5 )
    {
      v73 = "Frame: PrimitiveProcessor::CreateInstance successfully completed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v35,
        (unsigned int)&dword_1802760F4,
        v36,
        v37,
        (__int64)&v73);
    }
    v21 = 268;
    goto LABEL_84;
  }
  v10 = a2 - 1;
  if ( !v10 )
  {
    v29 = CFbrProcessor_CreateInstance(*(struct IUnknown **)(a1 + 13016), v6, (void **)&v67);
    v14 = v29;
    if ( v29 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_CreateProcessorCreateFbrProcFail",
        (char *)0x211A,
        v29,
        v63);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_88;
      v72 = 8475;
      v71[0] = "FbrProcessor::CreateInstance failed!";
      v15 = &word_1802760A6;
      v70 = "CreateProcessor";
      v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v68 = "Error HResult failed";
      v66 = (const char **)v71;
      v65 = &v70;
      v64 = &v69;
      v16 = &v68;
      goto LABEL_11;
    }
    v30 = (**(__int64 (__fastcall ***)(struct IRdpProcessor *, GUID *, __int64))v67)(
            v67,
            &IID_IRdpFbrProcessor,
            a1 + 13088);
    v14 = v30;
    if ( v30 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_CreateProcessorCreateFbrProcFail",
        (char *)0x211E,
        v30,
        v63);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_88;
      v72 = 8479;
      v71[0] = "pProcessor->QueryInterface( IID_IRdpFbrProcessor ) failed.";
      v15 = (__int16 *)qword_180276058;
      v70 = "CreateProcessor";
      v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v68 = "Error HResult failed";
      v66 = (const char **)v71;
      v65 = &v70;
      v64 = &v69;
      v16 = &v68;
      goto LABEL_11;
    }
    if ( (unsigned int)CallbackContext > 5 )
    {
      v73 = "Frame: CFbrProcessor_CreateInstance successfully completed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v31,
        (unsigned int)&word_180276036,
        v32,
        v33,
        (__int64)&v73);
    }
    v21 = 269;
    goto LABEL_84;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v28 = DeltaReducerProcessor::CreateInstance(&v67);
    v14 = v28;
    if ( v28 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_CreateProcessorCreateDeltaReducerProcFail",
        (char *)0x20A7,
        v28,
        v63);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_88;
      v72 = 8360;
      v71[0] = "DeltaReducerProcessor::CreateInstance failed!";
      v15 = &word_180276426;
      v70 = "CreateProcessor";
      v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v68 = "Error HResult failed";
      v66 = (const char **)v71;
      v65 = &v70;
      v64 = &v69;
      v16 = &v68;
      goto LABEL_11;
    }
    if ( (unsigned int)CallbackContext <= 5 )
      goto LABEL_32;
    v26 = "Frame: DeltaProcessor::CreateInstance successfully completed";
    v27 = &dword_180276404;
    goto LABEL_31;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    v22 = VideoDetectorProcessor::CreateInstance(*(struct IUnknown **)(a1 + 13016), &v67);
    v14 = v22;
    if ( v22 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_CreateProcessorCreateVideoDetectorFail",
        (char *)0x20B3,
        v22,
        v63);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_88;
      v72 = 8372;
      v71[0] = "VideoDetectorProcessor::CreateInstance failed!";
      v15 = &word_1802763B6;
      v70 = "CreateProcessor";
      v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v68 = "Error HResult failed";
      v66 = (const char **)v71;
      v65 = &v70;
      v64 = &v69;
      v16 = &v68;
      goto LABEL_11;
    }
    if ( (unsigned int)CallbackContext <= 5 )
      goto LABEL_32;
    v26 = "Frame: VideoDetectionProcessor::CreateInstance successfully completed";
    v27 = &dword_180276394;
LABEL_31:
    v73 = v26;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v23,
      (_DWORD)v27,
      v24,
      v25,
      (__int64)&v73);
LABEL_32:
    v21 = 261;
    goto LABEL_84;
  }
  if ( v12 != 1 )
    goto LABEL_58;
  v13 = *(_QWORD *)(a1 + 13128);
  if ( !v13 )
  {
    v14 = -2147418113;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v72 = 8340;
      v68 = "Gfx pipe extension factory is NULL.";
      v15 = word_180276532;
      v69 = "CreateProcessor";
      v70 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v71[0] = "Error condition failed";
      v66 = &v68;
      v65 = &v69;
      v64 = &v70;
      v16 = (const char **)v71;
LABEL_11:
      LODWORD(v73) = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (_DWORD)v15,
        v8,
        v9,
        (__int64)v16,
        (__int64)&v73,
        (__int64)v64,
        (__int64)&v72,
        (__int64)v65,
        (__int64)v66);
      goto LABEL_88;
    }
    goto LABEL_88;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, struct IRdpProcessor **))(*(_QWORD *)v13 + 32LL))(v13, &v67);
  if ( v14 < 0 )
  {
    LODWORD(v13) = (_DWORD)CallbackContext;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_88;
    v72 = 8344;
    v71[0] = "CreateVideoProcessor failed.";
    v15 = (__int16 *)&dword_1802764E4;
    v70 = "CreateProcessor";
    v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v68 = "Error HResult failed";
    v66 = (const char **)v71;
    v65 = &v70;
    v64 = &v69;
    v16 = &v68;
    goto LABEL_11;
  }
  v17 = (**(__int64 (__fastcall ***)(struct IRdpProcessor *, GUID *, __int64))v67)(
          v67,
          &IID_IRdpVideoProcessor,
          a1 + 13072);
  v14 = v17;
  if ( v17 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_CreateProcessorCreateVideoProcFail",
      (char *)0x209B,
      v17,
      v63);
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_88;
    v72 = 8348;
    v71[0] = "pProcessor->QueryInterface( IID_IRdpVideoProcessor ) failed.";
    v15 = &word_180276496;
    v70 = "CreateProcessor";
    v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v68 = "Error HResult failed";
    v66 = (const char **)v71;
    v65 = &v70;
    v64 = &v69;
    v16 = &v68;
    goto LABEL_11;
  }
  if ( (unsigned int)CallbackContext > 5 )
  {
    v73 = "Frame: VideoProcessor::CreateInstance successfully completed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v18,
      (unsigned int)&dword_180276474,
      v19,
      v20,
      (__int64)&v73);
  }
  v21 = 260;
LABEL_84:
  v14 = (*(__int64 (__fastcall **)(struct IRdpProcessor *, __int64))(*(_QWORD *)v67 + 24LL))(
          v67,
          (a1 + 8) & -(__int64)(a1 != 0));
  if ( v14 >= 0 )
  {
    *a3 = v67;
    v67 = 0;
    goto LABEL_88;
  }
  ProcessorInitErrorName = GetCreateProcessorInitErrorName(v21);
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
    ProcessorInitErrorName,
    (char *)0x2130,
    v14,
    v63);
  if ( (unsigned int)CallbackContext > 2 )
  {
    v72 = 8497;
    v71[0] = "InitializeInstance failed";
    v15 = word_180275FA2;
    v70 = "CreateProcessor";
    v69 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v68 = "Error HResult failed";
    v66 = (const char **)v71;
    v65 = &v70;
    v64 = &v69;
    v16 = &v68;
    goto LABEL_11;
  }
LABEL_88:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v67);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18008eb60  mov     [rsp-18h+arg_0], rbx
0x18008eb65  mov     [rsp-18h+arg_10], rsi
0x18008eb6a  push    rbp
0x18008eb6b  push    rdi
0x18008eb6c  push    r14
0x18008eb6e  mov     rbp, rsp
0x18008eb71  sub     rsp, 80h
0x18008eb78  mov     rsi, rcx
0x18008eb7b  mov     [rbp+var_30], 0
0x18008eb83  lea     rcx, [rbp+var_30]
0x18008eb87  mov     r14, r8
0x18008eb8a  mov     ebx, edx
0x18008eb8c  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18008eb91  mov     edi, 5
0x18008eb96  cmp     ebx, edi
0x18008eb98  jg      loc_18008F32A
0x18008eb9e  jz      loc_18008F241
0x18008eba4  test    ebx, ebx
0x18008eba6  jz      loc_18008F15F
0x18008ebac  sub     ebx, 1
0x18008ebaf  jz      loc_18008EFB4
0x18008ebb5  sub     ebx, 1
0x18008ebb8  jz      loc_18008EED2
0x18008ebbe  sub     ebx, 1
0x18008ebc1  jz      loc_18008EDFC
0x18008ebc7  cmp     ebx, 1
0x18008ebca  jnz     loc_18008F34A
0x18008ebd0  mov     rcx, [rsi+3348h]
0x18008ebd7  test    rcx, rcx
0x18008ebda  jnz     loc_18008EC71
0x18008ebe0  mov     eax, cs:CallbackContext
0x18008ebe6  mov     ebx, 8000FFFFh
0x18008ebeb  cmp     eax, 2
0x18008ebee  jbe     loc_18008F82F
0x18008ebf4  lea     rax, aGfxPipeExtensi; "Gfx pipe extension factory is NULL."
0x18008ebfb  mov     [rbp+arg_8], 2094h
0x18008ec02  mov     [rbp+var_28], rax
0x18008ec06  lea     rdx, word_180276532
0x18008ec0d  lea     rax, aCreateprocesso_0; "CreateProcessor"
0x18008ec14  mov     [rbp+var_20], rax
0x18008ec18  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008ec1f  mov     [rbp+var_18], rax
0x18008ec23  lea     rax, aErrorCondition; "Error condition failed"
0x18008ec2a  mov     [rbp+var_10], rax
0x18008ec2e  lea     rax, [rbp+var_28]
0x18008ec32  mov     [rsp+80h+var_38], rax
0x18008ec37  lea     rax, [rbp+var_20]
0x18008ec3b  mov     [rsp+80h+var_40], rax
0x18008ec40  lea     rax, [rbp+arg_8]
0x18008ec44  mov     [rsp+80h+var_48], rax
0x18008ec49  lea     rax, [rbp+var_18]
0x18008ec4d  mov     [rsp+80h+var_50], rax
0x18008ec52  lea     rax, [rbp+arg_18]
0x18008ec56  mov     [rsp+80h+var_58], rax
0x18008ec5b  lea     rax, [rbp+var_10]
0x18008ec5f  mov     qword ptr [rsp+80h+var_60], rax
0x18008ec64  mov     dword ptr [rbp+arg_18], ebx
0x18008ec67  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008ec6c  jmp     loc_18008F82F
0x18008ec71  mov     rax, [rcx]
0x18008ec74  lea     rdx, [rbp+var_30]
0x18008ec78  mov     rax, [rax+20h]
0x18008ec7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ec81  mov     ebx, eax
0x18008ec83  test    eax, eax
0x18008ec85  jns     short loc_18008ED06
0x18008ec87  mov     ecx, cs:CallbackContext
0x18008ec8d  cmp     ecx, 2
0x18008ec90  jbe     loc_18008F82F
0x18008ec96  lea     rax, aCreatevideopro; "CreateVideoProcessor failed."
0x18008ec9d  mov     [rbp+arg_8], 2098h
0x18008eca4  mov     [rbp+var_10], rax
0x18008eca8  lea     rdx, dword_1802764E4
0x18008ecaf  lea     rax, aCreateprocesso_0; "CreateProcessor"
0x18008ecb6  mov     [rbp+var_18], rax
0x18008ecba  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008ecc1  mov     [rbp+var_20], rax
0x18008ecc5  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008eccc  mov     [rbp+var_28], rax
0x18008ecd0  lea     rax, [rbp+var_10]
0x18008ecd4  mov     [rsp+80h+var_38], rax
0x18008ecd9  lea     rax, [rbp+var_18]
0x18008ecdd  mov     [rsp+80h+var_40], rax
0x18008ece2  lea     rax, [rbp+arg_8]
0x18008ece6  mov     [rsp+80h+var_48], rax
0x18008eceb  lea     rax, [rbp+var_20]
0x18008ecef  mov     [rsp+80h+var_50], rax
0x18008ecf4  lea     rax, [rbp+arg_18]
0x18008ecf8  mov     [rsp+80h+var_58], rax
0x18008ecfd  lea     rax, [rbp+var_28]
0x18008ed01  jmp     loc_18008EC5F
0x18008ed06  mov     rcx, [rbp+var_30]
0x18008ed0a  lea     r8, [rsi+3310h]
0x18008ed11  lea     rdx, IID_IRdpVideoProcessor
0x18008ed18  mov     rax, [rcx]
0x18008ed1b  mov     rax, [rax]
0x18008ed1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ed23  mov     ebx, eax
0x18008ed25  test    eax, eax
0x18008ed27  jns     loc_18008EDC8
0x18008ed2d  mov     r9d, eax; unsigned int
0x18008ed30  lea     rdx, aPipemanagererr_29; "PipeManagerError_CreateProcessorCreateV"...
0x18008ed37  mov     r8d, 209Bh; char *
0x18008ed3d  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008ed44  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008ed49  mov     eax, cs:CallbackContext
0x18008ed4f  cmp     eax, 2
0x18008ed52  jbe     loc_18008F82F
0x18008ed58  lea     rax, aPprocessorQuer_1; "pProcessor->QueryInterface( IID_IRdpVid"...
0x18008ed5f  mov     [rbp+arg_8], 209Ch
0x18008ed66  mov     [rbp+var_10], rax
0x18008ed6a  lea     rdx, word_180276496
0x18008ed71  lea     rax, aCreateprocesso_0; "CreateProcessor"
0x18008ed78  mov     [rbp+var_18], rax
0x18008ed7c  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008ed83  mov     [rbp+var_20], rax
0x18008ed87  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008ed8e  mov     [rbp+var_28], rax
0x18008ed92  lea     rax, [rbp+var_10]
0x18008ed96  mov     [rsp+80h+var_38], rax
0x18008ed9b  lea     rax, [rbp+var_18]
0x18008ed9f  mov     [rsp+80h+var_40], rax
0x18008eda4  lea     rax, [rbp+arg_8]
0x18008eda8  mov     [rsp+80h+var_48], rax
0x18008edad  lea     rax, [rbp+var_20]
0x18008edb1  mov     [rsp+80h+var_50], rax
0x18008edb6  lea     rax, [rbp+arg_18]
0x18008edba  mov     [rsp+80h+var_58], rax
0x18008edbf  lea     rax, [rbp+var_28]
0x18008edc3  jmp     loc_18008EC5F
0x18008edc8  mov     eax, cs:CallbackContext
0x18008edce  cmp     eax, edi
0x18008edd0  jbe     short loc_18008EDF2
0x18008edd2  lea     rax, aFrameVideoproc; "Frame: VideoProcessor::CreateInstance s"...
0x18008edd9  mov     [rbp+arg_18], rax
0x18008eddd  lea     rdx, dword_180276474
0x18008ede4  lea     rax, [rbp+arg_18]
0x18008ede8  mov     qword ptr [rsp+80h+var_60], rax
0x18008eded  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008edf2  mov     edi, 104h
0x18008edf7  jmp     loc_18008F75F
0x18008edfc  mov     rcx, [rsi+32D8h]; struct IUnknown *
0x18008ee03  lea     rdx, [rbp+var_30]; struct IRdpProcessor **
0x18008ee07  call    ?CreateInstance@VideoDetectorProcessor@@SAJPEAUIRDPCollection@@PEAPEAVIRdpProcessor@@@Z; VideoDetectorProcessor::CreateInstance(IRDPCollection *,IRdpProcessor * *)
0x18008ee0c  mov     ebx, eax
0x18008ee0e  test    eax, eax
0x18008ee10  jns     loc_18008EEB1
0x18008ee16  mov     r9d, eax; unsigned int
0x18008ee19  lea     rdx, aPipemanagererr_97; "PipeManagerError_CreateProcessorCreateV"...
0x18008ee20  mov     r8d, 20B3h; char *
0x18008ee26  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008ee2d  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008ee32  mov     eax, cs:CallbackContext
0x18008ee38  cmp     eax, 2
0x18008ee3b  jbe     loc_18008F82F
0x18008ee41  lea     rax, aVideodetectorp_2; "VideoDetectorProcessor::CreateInstance "...
0x18008ee48  mov     [rbp+arg_8], 20B4h
0x18008ee4f  mov     [rbp+var_10], rax
0x18008ee53  lea     rdx, word_1802763B6
0x18008ee5a  lea     rax, aCreateprocesso_0; "CreateProcessor"
0x18008ee61  mov     [rbp+var_18], rax
0x18008ee65  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008ee6c  mov     [rbp+var_20], rax
0x18008ee70  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008ee77  mov     [rbp+var_28], rax
0x18008ee7b  lea     rax, [rbp+var_10]
0x18008ee7f  mov     [rsp+80h+var_38], rax
0x18008ee84  lea     rax, [rbp+var_18]
0x18008ee88  mov     [rsp+80h+var_40], rax
0x18008ee8d  lea     rax, [rbp+arg_8]
0x18008ee91  mov     [rsp+80h+var_48], rax
0x18008ee96  lea     rax, [rbp+var_20]
0x18008ee9a  mov     [rsp+80h+var_50], rax
0x18008ee9f  lea     rax, [rbp+arg_18]
0x18008eea3  mov     [rsp+80h+var_58], rax
0x18008eea8  lea     rax, [rbp+var_28]
0x18008eeac  jmp     loc_18008EC5F
0x18008eeb1  mov     eax, cs:CallbackContext
0x18008eeb7  cmp     eax, edi
0x18008eeb9  jbe     loc_18008EFAA
0x18008eebf  lea     rax, aFrameVideodete; "Frame: VideoDetectionProcessor::CreateI"...
0x18008eec6  lea     rdx, dword_180276394
0x18008eecd  jmp     loc_18008EF98
0x18008eed2  lea     rcx, [rbp+var_30]; struct IRdpProcessor **
0x18008eed6  call    ?CreateInstance@DeltaReducerProcessor@@SAJPEAPEAVIRdpProcessor@@@Z; DeltaReducerProcessor::CreateInstance(IRdpProcessor * *)
0x18008eedb  mov     ebx, eax
0x18008eedd  test    eax, eax
0x18008eedf  jns     loc_18008EF80
0x18008eee5  mov     r9d, eax; unsigned int
0x18008eee8  lea     rdx, aPipemanagererr_108; "PipeManagerError_CreateProcessorCreateD"...
0x18008eeef  mov     r8d, 20A7h; char *
0x18008eef5  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008eefc  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008ef01  mov     eax, cs:CallbackContext
0x18008ef07  cmp     eax, 2
0x18008ef0a  jbe     loc_18008F82F
0x18008ef10  lea     rax, aDeltareducerpr_3; "DeltaReducerProcessor::CreateInstance f"...
0x18008ef17  mov     [rbp+arg_8], 20A8h
0x18008ef1e  mov     [rbp+var_10], rax
0x18008ef22  lea     rdx, word_180276426
0x18008ef29  lea     rax, aCreateprocesso_0; "CreateProcessor"
0x18008ef30  mov     [rbp+var_18], rax
0x18008ef34  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008ef3b  mov     [rbp+var_20], rax
0x18008ef3f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008ef46  mov     [rbp+var_28], rax
0x18008ef4a  lea     rax, [rbp+var_10]
0x18008ef4e  mov     [rsp+80h+var_38], rax
0x18008ef53  lea     rax, [rbp+var_18]
0x18008ef57  mov     [rsp+80h+var_40], rax
0x18008ef5c  lea     rax, [rbp+arg_8]
0x18008ef60  mov     [rsp+80h+var_48], rax
0x18008ef65  lea     rax, [rbp+var_20]
0x18008ef69  mov     [rsp+80h+var_50], rax
0x18008ef6e  lea     rax, [rbp+arg_18]
0x18008ef72  mov     [rsp+80h+var_58], rax
0x18008ef77  lea     rax, [rbp+var_28]
0x18008ef7b  jmp     loc_18008EC5F
0x18008ef80  mov     eax, cs:CallbackContext
0x18008ef86  cmp     eax, edi
0x18008ef88  jbe     short loc_18008EFAA
0x18008ef8a  lea     rax, aFrameDeltaproc; "Frame: DeltaProcessor::CreateInstance s"...
0x18008ef91  lea     rdx, dword_180276404
0x18008ef98  mov     [rbp+arg_18], rax
0x18008ef9c  lea     rax, [rbp+arg_18]
0x18008efa0  mov     qword ptr [rsp+80h+var_60], rax
0x18008efa5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008efaa  mov     edi, 105h
0x18008efaf  jmp     loc_18008F75F
0x18008efb4  mov     rcx, [rsi+32D8h]; struct IUnknown *
0x18008efbb  lea     r8, [rbp+var_30]; void **
0x18008efbf  call    ?CFbrProcessor_CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CFbrProcessor_CreateInstance(IUnknown *,_GUID const &,void * *)
0x18008efc4  mov     ebx, eax
0x18008efc6  test    eax, eax
0x18008efc8  jns     loc_18008F069
0x18008efce  mov     r9d, eax; unsigned int
0x18008efd1  lea     rdx, aPipemanagererr_89; "PipeManagerError_CreateProcessorCreateF"...
0x18008efd8  mov     r8d, 211Ah; char *
0x18008efde  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008efe5  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008efea  mov     eax, cs:CallbackContext
0x18008eff0  cmp     eax, 2
0x18008eff3  jbe     loc_18008F82F
0x18008eff9  lea     rax, aFbrprocessorCr; "FbrProcessor::CreateInstance failed!"
0x18008f000  mov     [rbp+arg_8], 211Bh
0x18008f007  mov     [rbp+var_10], rax
0x18008f00b  lea     rdx, word_1802760A6
0x18008f012  lea     rax, aCreateprocesso_0; "CreateProcessor"
0x18008f019  mov     [rbp+var_18], rax
0x18008f01d  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008f024  mov     [rbp+var_20], rax
0x18008f028  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008f02f  mov     [rbp+var_28], rax
0x18008f033  lea     rax, [rbp+var_10]
0x18008f037  mov     [rsp+80h+var_38], rax
0x18008f03c  lea     rax, [rbp+var_18]
0x18008f040  mov     [rsp+80h+var_40], rax
0x18008f045  lea     rax, [rbp+arg_8]
0x18008f049  mov     [rsp+80h+var_48], rax
0x18008f04e  lea     rax, [rbp+var_20]
0x18008f052  mov     [rsp+80h+var_50], rax
0x18008f057  lea     rax, [rbp+arg_18]
0x18008f05b  mov     [rsp+80h+var_58], rax
0x18008f060  lea     rax, [rbp+var_28]
0x18008f064  jmp     loc_18008EC5F
0x18008f069  mov     rcx, [rbp+var_30]
0x18008f06d  lea     r8, [rsi+3320h]
0x18008f074  lea     rdx, IID_IRdpFbrProcessor
0x18008f07b  mov     rax, [rcx]
0x18008f07e  mov     rax, [rax]
0x18008f081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f086  mov     ebx, eax
0x18008f088  test    eax, eax
0x18008f08a  jns     loc_18008F12B
0x18008f090  mov     r9d, eax; unsigned int
0x18008f093  lea     rdx, aPipemanagererr_89; "PipeManagerError_CreateProcessorCreateF"...
0x18008f09a  mov     r8d, 211Eh; char *
0x18008f0a0  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008f0a7  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008f0ac  mov     eax, cs:CallbackContext
0x18008f0b2  cmp     eax, 2
0x18008f0b5  jbe     loc_18008F82F
0x18008f0bb  lea     rax, aPprocessorQuer; "pProcessor->QueryInterface( IID_IRdpFbr"...
0x18008f0c2  mov     [rbp+arg_8], 211Fh
0x18008f0c9  mov     [rbp+var_10], rax
0x18008f0cd  lea     rdx, qword_180276058
0x18008f0d4  lea     rax, aCreateprocesso_0; "CreateProcessor"
0x18008f0db  mov     [rbp+var_18], rax
0x18008f0df  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008f0e6  mov     [rbp+var_20], rax
0x18008f0ea  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008f0f1  mov     [rbp+var_28], rax
0x18008f0f5  lea     rax, [rbp+var_10]
0x18008f0f9  mov     [rsp+80h+var_38], rax
0x18008f0fe  lea     rax, [rbp+var_18]
0x18008f102  mov     [rsp+80h+var_40], rax
0x18008f107  lea     rax, [rbp+arg_8]
0x18008f10b  mov     [rsp+80h+var_48], rax
0x18008f110  lea     rax, [rbp+var_20]
0x18008f114  mov     [rsp+80h+var_50], rax
  ... truncated ...
```
