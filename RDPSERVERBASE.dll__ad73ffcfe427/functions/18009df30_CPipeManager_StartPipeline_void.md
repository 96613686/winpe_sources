# CPipeManager::StartPipeline(void)

- ea: `0x18009df30`
- end: `0x18009eb88`
- name: `?StartPipeline@CPipeManager@@IEAAJXZ`
- size: `3160`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180056260`

## callees

- `0x18000116c`
- `0x1800012dc`
- `0x180001308`
- `0x18000202c`
- `0x1800023e4`
- `0x180002d3c`
- `0x18000ce04`
- `0x18000ce34`
- `0x18002aafc`
- `0x18004f5bc`
- `0x18004fc5c`
- `0x18005306c`
- `0x180076090`
- `0x180076bf8`
- `0x180076cc8`
- `0x180079770`
- `0x18007e9e0`
- `0x18008b9e8`
- `0x18008d5a4`
- `0x180090b20`
- `0x1800996a0`
- `0x18009cf80`
- `0x18009df30`
- `0x180158180`
- `0x18019b280`
- `0x18019c010`

## import_xrefs

- `RDPBASE!?GetTickCount@PipelineClock@@QEAAIXZ` at `0x18009e98c`
- `RDPBASE!?GetTickCount@PipelineClock@@QEAAIXZ` at `0x18009e98c`
- `RDPBASE!CRDPCacVideoCodecForHardwareClient_CreateInstance` at `0x18009e1dd`
- `RDPBASE!CRDPCacVideoCodecForHardwareClient_CreateInstance` at `0x18009e1dd`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18009e983`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18009e983`

## string_xrefs

- `0x18009e893`: `PipeManagerError_StartPipelineConfigProfileFail`
- `0x18009e8bb`: `ConfigureProfile failed`
- `0x18009e044`: `Failed to start update tracker`
- `0x18009e1f2`: `CRDPCacVideoCodecForHardwareClient_CreateInstance failed.`
- `0x18009e22a`: `spImageCompressor is null, so call DisableCodec.`
- `0x18009e3a1`: `Unable to GetProtocolSettings`
- `0x18009e519`: `spImageCompressor->SetDecompressionSettings failed`
- `0x18009e5ee`: `AddCompressorInstance failed`
- `0x18009e8fe`: `m_spProcessorList.Remove failed`

## pseudocode

```c
__int64 __fastcall CPipeManager::StartPipeline(CPipeManager *this)
{
  CTSCriticalSection *v1; // rdi
  __int64 v3; // rbx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  signed int v7; // eax
  int v8; // esi
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rbx
  int v12; // eax
  char v13; // si
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rdx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  signed int v23; // eax
  int v24; // ecx
  int v25; // r9d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  char *v29; // rdx
  const char **v30; // rax
  unsigned int v31; // ebx
  unsigned int v32; // esi
  unsigned int i; // edx
  unsigned int v34; // eax
  unsigned int v35; // eax
  signed int v36; // eax
  __int64 v37; // r8
  __int64 *v38; // rcx
  __int64 v39; // rax
  signed int v40; // eax
  const char *v41; // r8
  const char *v42; // r9
  int v43; // ecx
  __int64 v44; // rdx
  int v45; // r8d
  int v46; // r9d
  unsigned int v47; // r12d
  int v48; // eax
  __int64 v49; // rbx
  signed int v50; // eax
  __int64 v51; // r15
  void (__fastcall *v52)(__int64, _QWORD, _QWORD); // rsi
  unsigned int v53; // ebx
  unsigned int v54; // eax
  signed int v55; // eax
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  const char *v59; // rax
  char *v60; // rdx
  PipelineClock *Instance; // rax
  __int64 v62; // r8
  __int64 v63; // r9
  int v64; // ecx
  int v65; // r8d
  int v66; // r9d
  int v67; // ecx
  int v68; // r8d
  int v69; // r9d
  unsigned int v70; // edi
  int v71; // ecx
  int v72; // r8d
  int v73; // r9d
  int v74; // ebx
  int v75; // r8d
  int v77; // [rsp+20h] [rbp-E0h]
  int *v78; // [rsp+30h] [rbp-D0h]
  int *v79; // [rsp+38h] [rbp-C8h]
  int *v80; // [rsp+40h] [rbp-C0h]
  struct _GUID *v81; // [rsp+48h] [rbp-B8h]
  int v82[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v83[2]; // [rsp+68h] [rbp-98h] BYREF
  int v84[2]; // [rsp+70h] [rbp-90h] BYREF
  const char *v85; // [rsp+78h] [rbp-88h] BYREF
  const char *v86; // [rsp+80h] [rbp-80h] BYREF
  const char *v87; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v88[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v89; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v90; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v91; // [rsp+B8h] [rbp-48h] BYREF
  int v92[80]; // [rsp+C0h] [rbp-40h] BYREF
  int v93; // [rsp+200h] [rbp+100h] BYREF

  v1 = (CPipeManager *)((char *)this + 48896);
  v88[0] = 0;
  LODWORD(v87) = 0;
  v91 = 0;
  *(_QWORD *)v82 = (char *)this + 48896;
  CTSCriticalSection::Lock((CPipeManager *)((char *)this + 48896));
  v3 = 0;
  if ( *((_QWORD *)this + 1625) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v91);
    v3 = *((_QWORD *)this + 1625);
    v91 = v3;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v91);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)v82);
  if ( (unsigned int)CallbackContext > 5 )
  {
    *(_QWORD *)v82 = "ENTERFN CPipeManager::StartPipeline";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v4,
      (unsigned int)&dword_1802790B4,
      v5,
      v6,
      (__int64)v82);
  }
  if ( v3 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 72LL))(v3);
    v8 = v7;
    if ( v7 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_StartPipelineStartUTFail",
        (char *)0x12D0,
        v7,
        v77);
      if ( (unsigned int)CallbackContext > 2 )
      {
        *(_QWORD *)v84 = "StartPipeline";
        *(_QWORD *)v82 = "Failed to start update tracker";
        v90 = 4817;
        *(_QWORD *)v83 = "Error HResult failed";
        v85 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        LODWORD(v87) = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&word_180279066,
          v9,
          v10,
          (__int64)v83,
          (__int64)&v87,
          (__int64)&v85,
          (__int64)&v90,
          (__int64)v84,
          (__int64)v82);
      }
      goto LABEL_81;
    }
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 6118) + 64LL))((char *)this + 48944);
  while ( (unsigned int)CTSSimpleKeyComPtrArray<enum PipelineProcessor,IRdpProcessor>::GetNext(
                          (char *)this + 48944,
                          &v87,
                          v88) )
  {
    v11 = v88[0];
    v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v88[0] + 64LL))(v88[0]);
    v13 = v12;
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"OnStarted failed",
          v13);
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1631) + 104LL))(
        *((_QWORD *)this + 1631),
        (unsigned int)v87);
    }
    if ( v11 )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease(v88);
      v88[0] = 0;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(v88);
    }
  }
  if ( *((_DWORD *)this + 13256)
    && (*((_BYTE *)this + 13272) & 1) != 0
    && (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1631) + 80LL))(
         *((_QWORD *)this + 1631),
         3) )
  {
    *(_QWORD *)v82 = 0;
    if ( (int)CRDPCacVideoCodecForHardwareClient_CreateInstance(0, &IID_IRdpImageCompressor, v82) < 0
      && (unsigned int)CallbackContext > 3 )
    {
      *(_QWORD *)v83 = "CRDPCacVideoCodecForHardwareClient_CreateInstance failed.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v15,
        (unsigned int)&dword_180279044,
        v16,
        v17,
        (__int64)v83);
    }
    if ( !*(_QWORD *)v82 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        *(_QWORD *)v83 = "spImageCompressor is null, so call DisableCodec.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v15,
          (unsigned int)word_180279022,
          v16,
          v17,
          (__int64)v83);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1631) + 88LL))(*((_QWORD *)this + 1631), 3);
      goto LABEL_29;
    }
    v22 = *((_QWORD *)this + 1624);
    v90 = 16;
    v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, int *))(*(_QWORD *)v22 + 152LL))(v22, 0, 0, v92);
    v8 = v23;
    if ( v23 >= 0 )
    {
      v31 = 0;
      v32 = 0;
      for ( i = 0; i < v90; v32 = v35 )
      {
        v24 = 5 * i;
        v34 = v92[5 * i + 2] - v92[5 * i] + 1;
        if ( v34 <= v31 )
          v34 = v31;
        v31 = v34;
        v35 = v92[5 * i + 3] - v92[5 * i + 1] + 1;
        if ( v35 <= v32 )
          v35 = v32;
        ++i;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v85) = v32;
        *(_QWORD *)&v89.Data1 = "Capability: Calista video encoder for hardware client will be initialized";
        v84[0] = v31;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)byte_180278F9D,
          v90,
          v25,
          (__int64)&v89,
          (__int64)v84,
          (__int64)&v85);
      }
      v77 = 0;
      v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)v82 + 40LL))(
              *(_QWORD *)v82,
              v31,
              v32,
              0);
      v8 = v36;
      if ( v36 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_StartPipelineStartCaVideoCodecFail",
          (char *)0x1334,
          v36,
          0);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_37;
        v84[0] = 4917;
        *(_QWORD *)&v89.Data1 = "spImageCompressor->SetDecompressionSettings failed";
        v86 = "StartPipeline";
        v87 = "Error HResult failed";
        *(_QWORD *)v83 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v81 = &v89;
        v29 = &byte_180278F4F;
        v80 = (int *)&v86;
        v79 = v84;
        v78 = v83;
        v30 = &v87;
        goto LABEL_36;
      }
      v38 = (__int64 *)*((_QWORD *)this + 6127);
      LOBYTE(v37) = 3;
      v39 = *v38;
      v89 = CODEC_GUID_CACODEC;
      v40 = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *, __int64, _QWORD))(v39 + 24))(
              v38,
              &v89,
              v37,
              *(_QWORD *)v82);
      v8 = v40;
      if ( v40 >= 0 )
      {
LABEL_29:
        TCntPtr<IRdpImageCompressor>::operator=(v82, 0);
        TCntPtr<IRdpVCMgr>::SafeRelease(v82);
        goto LABEL_30;
      }
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_StartPipelineStartCaVideoCodecFail",
        (char *)0x133C,
        v40,
        0);
      if ( (unsigned int)CallbackContext > 2 )
      {
        v84[0] = 4925;
        *(_QWORD *)&v89.Data1 = "AddCompressorInstance failed";
        v86 = "StartPipeline";
        v87 = "Error HResult failed";
        *(_QWORD *)v83 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v81 = &v89;
        v29 = byte_180278F01;
        v80 = (int *)&v86;
        v79 = v84;
        v78 = v83;
        v30 = &v87;
        goto LABEL_36;
      }
    }
    else
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_StartPipelineStartCaVideoCodecFail",
        (char *)0x1319,
        v23,
        (int)&v93);
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v87) = 4890;
        *(_QWORD *)v83 = "Unable to GetProtocolSettings";
        *(_QWORD *)v84 = "StartPipeline";
        *(_QWORD *)&v89.Data1 = "Error HResult failed";
        v86 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v81 = (struct _GUID *)v83;
        v29 = (char *)&dword_180278FD4;
        v80 = v84;
        v79 = (int *)&v87;
        v78 = (int *)&v86;
        v30 = (const char **)&v89;
LABEL_36:
        LODWORD(v85) = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v26,
          (_DWORD)v29,
          v27,
          v28,
          (__int64)v30,
          (__int64)&v85,
          (__int64)v78,
          (__int64)v79,
          (__int64)v80,
          (__int64)v81);
      }
    }
LABEL_37:
    TCntPtr<IRdpVCMgr>::SafeRelease(v82);
    goto LABEL_81;
  }
LABEL_30:
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1631) + 64LL))(*((_QWORD *)this + 1631)) )
  {
    v8 = -2147467259;
    if ( (unsigned int)CallbackContext > 2 )
    {
      *(_QWORD *)&v89.Data1 = "StartPipeline";
      *(_QWORD *)v83 = "Capability: No profile available for the pipeline";
      v84[0] = 4936;
      v86 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      LODWORD(v85) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v19,
        (unsigned int)byte_180278EBB,
        v20,
        v21,
        (__int64)v83,
        (__int64)&v85,
        (__int64)&v86,
        (__int64)v84,
        (__int64)&v89);
    }
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_StartPipelineNoProfileAvailable",
      (char *)0x1349,
      0x80004005,
      v77);
    goto LABEL_81;
  }
  v41 = "Stack";
  v42 = "Checkpoint";
  if ( (unsigned int)CallbackContext > 4
    && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, "Stack", "Checkpoint") )
  {
    v86 = "PipeMgr";
    *(_QWORD *)&v89.Data1 = (char *)this + 13552;
    *(_QWORD *)v83 = v41;
    *(_QWORD *)v82 = 0x1000000;
    *(_QWORD *)v84 = v42;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
      v43,
      (unsigned int)&byte_180278E57,
      (_DWORD)v41,
      (_DWORD)v42,
      (__int64)v84,
      (__int64)v82,
      (__int64)v83,
      (__int64)&v86,
      (__int64)&v89);
  }
  (*(void (__fastcall **)(char *, __int64, const char *, const char *))(*((_QWORD *)this + 6118) + 64LL))(
    (char *)this + 48944,
    v18,
    v41,
    v42);
  if ( (unsigned int)CTSSimpleKeyComPtrArray<enum PipelineProcessor,IRdpProcessor>::GetNext(
                       (char *)this + 48944,
                       &v87,
                       v88) )
  {
    while ( 1 )
    {
      v47 = (unsigned int)v87;
      v48 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1631) + 96LL))(
              *((_QWORD *)this + 1631),
              (unsigned int)v87);
      v49 = v88[0];
      if ( !v48 )
      {
        if ( v47 == 4 )
        {
          if ( *((_QWORD *)this + 1634) )
          {
            TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 13072);
            *((_QWORD *)this + 1634) = 0;
            TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 13072);
          }
        }
        else if ( v47 == 1 && *((_QWORD *)this + 1636) )
        {
          TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 13088);
          *((_QWORD *)this + 1636) = 0;
          TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 13088);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 32LL))(v49);
        v50 = CTSSimpleKeyComPtrArray<enum PipelineProcessor,IRdpProcessor>::Remove((char *)this + 48944, v47);
        v8 = v50;
        if ( v50 < 0 )
          break;
      }
      if ( v49 )
      {
        TCntPtr<IRdpVCMgr>::SafeRelease(v88);
        v88[0] = 0;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(v88);
      }
      if ( !(unsigned int)CTSSimpleKeyComPtrArray<enum PipelineProcessor,IRdpProcessor>::GetNext(
                            (char *)this + 48944,
                            &v87,
                            v88) )
        goto LABEL_68;
    }
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "PipeManagerError_StartPipelineTerminateProcsFail",
      (char *)0x1361,
      v50,
      v77);
    if ( (unsigned int)CallbackContext > 2 )
    {
      v59 = "m_spProcessorList.Remove failed";
      v84[0] = 4962;
      v60 = byte_180278E09;
LABEL_77:
      *(_QWORD *)&v89.Data1 = v59;
      LODWORD(v85) = v8;
      *(_QWORD *)v82 = "Error HResult failed";
      *(_QWORD *)v83 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v86 = "StartPipeline";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v56,
        (_DWORD)v60,
        v57,
        v58,
        (__int64)v82,
        (__int64)&v85,
        (__int64)v83,
        (__int64)v84,
        (__int64)&v86,
        (__int64)&v89);
    }
  }
  else
  {
LABEL_68:
    if ( *((_DWORD *)this + 13256) )
      CPipeManager::OnFrameCaps((CPipeManager *)((char *)this + 24), 0x63u);
    v51 = *((_QWORD *)this + 1624);
    if ( v51 )
    {
      v52 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v51 + 232LL);
      v53 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1631) + 168LL))(*((_QWORD *)this + 1631));
      v54 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1631) + 160LL))(*((_QWORD *)this + 1631));
      v52(v51, v54, v53);
    }
    v55 = CPipeManager::ConfigureProfile(this, v44, v45, v46);
    v8 = v55;
    if ( v55 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "PipeManagerError_StartPipelineConfigProfileFail",
        (char *)0x137A,
        v55,
        v77);
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_81;
      v59 = "ConfigureProfile failed";
      v84[0] = 4987;
      v60 = byte_180278DBB;
      goto LABEL_77;
    }
    Instance = (PipelineClock *)PipelineClock::GetInstance();
    *((_DWORD *)this + 13380) = PipelineClock::GetTickCount(Instance);
    if ( (unsigned int)CallbackContext > 4
      && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v62, v63) )
    {
      v86 = "PipeMgr";
      *(_QWORD *)&v89.Data1 = (char *)this + 13552;
      *(_QWORD *)v82 = 0x1000000;
      *(_QWORD *)v83 = "Stack";
      *(_QWORD *)v84 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v64,
        (unsigned int)byte_180278D59,
        v65,
        v66,
        (__int64)v84,
        (__int64)v82,
        (__int64)v83,
        (__int64)&v86,
        (__int64)&v89);
    }
  }
LABEL_81:
  *(_QWORD *)v82 = v1;
  CTSCriticalSection::Lock(v1);
  v70 = *((_DWORD *)this + 12220);
  if ( v8 >= 0 )
  {
    if ( v70 != 8 )
      *((_DWORD *)this + 12220) = 9;
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&v89.Data1 = "Frame: CPipeManager::StartPipeline: PipeStateEncodingFirstFrame: can encode now";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v67,
        (unsigned int)byte_180278CF1,
        v68,
        v69,
        (__int64)&v89);
    }
  }
  else
  {
    CPipeManager::DisconnectClient(this, 0x12Du);
    if ( (unsigned int)CallbackContext > 2 )
    {
      *(_QWORD *)&v89.Data1 = "StartPipeline";
      *(_QWORD *)v83 = "PIPE_ERROR: cannot encode";
      v84[0] = 5001;
      v86 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      LODWORD(v85) = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v71,
        (unsigned int)byte_180278D13,
        v72,
        v73,
        (__int64)v83,
        (__int64)&v85,
        (__int64)&v86,
        (__int64)v84,
        (__int64)&v89);
    }
  }
  v74 = *((_DWORD *)this + 12220);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)v82);
  if ( v74 == 9 )
  {
    CPipeManager::LogPipelineTransition(this, v70, 9, 8);
  }
  else if ( v8 < 0 )
  {
    CPipeManager::SetPipelineErrorState(this, (unsigned int)v8, 9);
  }
  CPipeManager::ScheduleTask(this, 0, v75);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v91);
  TCntPtr<IRdpVCMgr>::SafeRelease(v88);
  return 0;
}

```

## disassembly

```asm
0x18009df30  push    rbp
0x18009df32  push    rbx
0x18009df33  push    rsi
0x18009df34  push    rdi
0x18009df35  push    r12
0x18009df37  push    r13
0x18009df39  push    r14
0x18009df3b  push    r15
0x18009df3d  lea     rbp, [rsp-2418h]
0x18009df45  mov     eax, 2518h
0x18009df4a  call    _alloca_probe
0x18009df4f  sub     rsp, rax
0x18009df52  mov     rax, cs:__security_cookie
0x18009df59  xor     rax, rsp
0x18009df5c  mov     [rbp+2450h+var_50], rax
0x18009df63  lea     rdi, [rcx+0BF00h]
0x18009df6a  xor     r13d, r13d
0x18009df6d  mov     r14, rcx
0x18009df70  mov     [rbp+2450h+var_24C0], r13
0x18009df74  mov     rcx, rdi; this
0x18009df77  mov     dword ptr [rbp+2450h+var_24C8], r13d
0x18009df7b  mov     [rbp+2450h+var_2498], r13
0x18009df7f  mov     qword ptr [rsp+2550h+var_24F0], rdi
0x18009df84  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18009df89  mov     ebx, r13d
0x18009df8c  cmp     [r14+32C8h], r13
0x18009df93  jz      short loc_18009DFB2
0x18009df95  lea     rcx, [rbp+2450h+var_2498]
0x18009df99  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009df9e  mov     rbx, [r14+32C8h]
0x18009dfa5  lea     rcx, [rbp+2450h+var_2498]
0x18009dfa9  mov     [rbp+2450h+var_2498], rbx
0x18009dfad  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18009dfb2  lea     rcx, [rsp+2550h+var_24F0]; this
0x18009dfb7  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18009dfbc  mov     eax, cs:CallbackContext
0x18009dfc2  cmp     eax, 5
0x18009dfc5  jbe     short loc_18009DFE9
0x18009dfc7  lea     rax, aEnterfnCpipema; "ENTERFN CPipeManager::StartPipeline"
0x18009dfce  mov     qword ptr [rsp+2550h+var_24F0], rax
0x18009dfd3  lea     rdx, dword_1802790B4
0x18009dfda  lea     rax, [rsp+2550h+var_24F0]
0x18009dfdf  mov     qword ptr [rsp+2550h+var_2530], rax; int
0x18009dfe4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009dfe9  lea     r12, aStartpipeline; "StartPipeline"
0x18009dff0  lea     r15, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009dff7  test    rbx, rbx
0x18009dffa  jz      loc_18009E0BB
0x18009e000  mov     rax, [rbx]
0x18009e003  mov     rcx, rbx
0x18009e006  mov     rax, [rax+48h]
0x18009e00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e00f  mov     esi, eax
0x18009e011  test    eax, eax
0x18009e013  jns     loc_18009E0BB
0x18009e019  mov     r9d, eax; unsigned int
0x18009e01c  lea     rdx, aPipemanagererr_90; "PipeManagerError_StartPipelineStartUTFa"...
0x18009e023  mov     r8d, 12D0h; char *
0x18009e029  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18009e030  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009e035  mov     ecx, cs:CallbackContext
0x18009e03b  cmp     ecx, 2
0x18009e03e  jbe     loc_18009EA2E
0x18009e044  lea     rax, aFailedToStartU; "Failed to start update tracker"
0x18009e04b  mov     qword ptr [rsp+2550h+var_24E0], r12
0x18009e050  mov     qword ptr [rsp+2550h+var_24F0], rax
0x18009e055  lea     rdx, word_180279066
0x18009e05c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009e063  mov     [rbp+2450h+var_24A0], 12D1h
0x18009e06a  mov     qword ptr [rsp+2550h+var_24E8], rax
0x18009e06f  lea     rax, [rsp+2550h+var_24F0]
0x18009e074  mov     [rsp+2550h+var_2508], rax
0x18009e079  lea     rax, [rsp+2550h+var_24E0]
0x18009e07e  mov     [rsp+2550h+var_2510], rax
0x18009e083  lea     rax, [rbp+2450h+var_24A0]
0x18009e087  mov     [rsp+2550h+var_2518], rax
0x18009e08c  lea     rax, [rsp+2550h+var_24D8]
0x18009e091  mov     [rsp+2550h+var_2520], rax
0x18009e096  lea     rax, [rbp+2450h+var_24C8]
0x18009e09a  mov     [rsp+2550h+var_2528], rax
0x18009e09f  lea     rax, [rsp+2550h+var_24E8]
0x18009e0a4  mov     qword ptr [rsp+2550h+var_2530], rax
0x18009e0a9  mov     [rsp+2550h+var_24D8], r15
0x18009e0ae  mov     dword ptr [rbp+2450h+var_24C8], esi
0x18009e0b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009e0b6  jmp     loc_18009EA2E
0x18009e0bb  lea     r15, [r14+0BF30h]
0x18009e0c2  mov     rax, [r15]
0x18009e0c5  mov     rcx, r15
0x18009e0c8  mov     rax, [rax+40h]
0x18009e0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e0d1  jmp     loc_18009E173
0x18009e0d6  mov     rbx, [rbp+2450h+var_24C0]
0x18009e0da  mov     rcx, rbx
0x18009e0dd  mov     rax, [rbx]
0x18009e0e0  mov     rax, [rax+40h]
0x18009e0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e0e9  mov     esi, eax
0x18009e0eb  test    eax, eax
0x18009e0ed  jns     short loc_18009E158
0x18009e0ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e0f6  lea     rax, WPP_GLOBAL_Control
0x18009e0fd  cmp     rcx, rax
0x18009e100  jz      short loc_18009E142
0x18009e102  test    byte ptr [rcx+1Ch], 8
0x18009e106  jz      short loc_18009E142
0x18009e108  cmp     byte ptr [rcx+19h], 2
0x18009e10c  jb      short loc_18009E142
0x18009e10e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009e113  lea     rcx, aOnstartedFaile; "OnStarted failed"
0x18009e11a  mov     dword ptr [rsp+2550h+var_2528], esi
0x18009e11e  mov     qword ptr [rsp+2550h+var_2530], rcx
0x18009e123  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x18009e12a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e131  mov     edx, 6Bh ; 'k'
0x18009e136  mov     r9d, eax
0x18009e139  mov     rcx, [rcx+10h]
0x18009e13d  call    WPP_SF_DsD
0x18009e142  mov     rcx, [r14+32F8h]
0x18009e149  mov     edx, dword ptr [rbp+2450h+var_24C8]
0x18009e14c  mov     rax, [rcx]
0x18009e14f  mov     rax, [rax+68h]
0x18009e153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e158  test    rbx, rbx
0x18009e15b  jz      short loc_18009E173
0x18009e15d  lea     rcx, [rbp+2450h+var_24C0]
0x18009e161  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009e166  lea     rcx, [rbp+2450h+var_24C0]
0x18009e16a  mov     [rbp+2450h+var_24C0], r13
0x18009e16e  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18009e173  lea     r8, [rbp+2450h+var_24C0]
0x18009e177  mov     rcx, r15
0x18009e17a  lea     rdx, [rbp+2450h+var_24C8]
0x18009e17e  call    ?GetNext@?$CTSSimpleKeyComPtrArray@W4PipelineProcessor@@VIRdpProcessor@@@@QEAAHPEAW4PipelineProcessor@@PEAPEAVIRdpProcessor@@@Z; CTSSimpleKeyComPtrArray<PipelineProcessor,IRdpProcessor>::GetNext(PipelineProcessor *,IRdpProcessor * *)
0x18009e183  test    eax, eax
0x18009e185  jnz     loc_18009E0D6
0x18009e18b  cmp     [r14+0CF20h], r13d
0x18009e192  jz      loc_18009E27F
0x18009e198  test    byte ptr [r14+33D8h], 1
0x18009e1a0  jz      loc_18009E27F
0x18009e1a6  mov     rcx, [r14+32F8h]
0x18009e1ad  mov     r12d, 3
0x18009e1b3  mov     edx, r12d
0x18009e1b6  mov     rax, [rcx]
0x18009e1b9  mov     rax, [rax+50h]
0x18009e1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e1c2  test    eax, eax
0x18009e1c4  jz      loc_18009E278
0x18009e1ca  lea     r8, [rsp+2550h+var_24F0]
0x18009e1cf  mov     qword ptr [rsp+2550h+var_24F0], r13
0x18009e1d4  lea     rdx, IID_IRdpImageCompressor
0x18009e1db  xor     ecx, ecx
0x18009e1dd  call    cs:__imp_CRDPCacVideoCodecForHardwareClient_CreateInstance
0x18009e1e3  test    eax, eax
0x18009e1e5  jns     short loc_18009E214
0x18009e1e7  mov     eax, cs:CallbackContext
0x18009e1ed  cmp     eax, r12d
0x18009e1f0  jbe     short loc_18009E214
0x18009e1f2  lea     rax, aCrdpcacvideoco; "CRDPCacVideoCodecForHardwareClient_Crea"...
0x18009e1f9  mov     qword ptr [rsp+2550h+var_24E8], rax
0x18009e1fe  lea     rdx, dword_180279044
0x18009e205  lea     rax, [rsp+2550h+var_24E8]
0x18009e20a  mov     qword ptr [rsp+2550h+var_2530], rax
0x18009e20f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009e214  cmp     qword ptr [rsp+2550h+var_24F0], r13
0x18009e219  jnz     loc_18009E316
0x18009e21f  mov     eax, cs:CallbackContext
0x18009e225  cmp     eax, r12d
0x18009e228  jbe     short loc_18009E24C
0x18009e22a  lea     rax, aSpimagecompres; "spImageCompressor is null, so call Disa"...
0x18009e231  mov     qword ptr [rsp+2550h+var_24E8], rax
0x18009e236  lea     rdx, word_180279022
0x18009e23d  lea     rax, [rsp+2550h+var_24E8]
0x18009e242  mov     qword ptr [rsp+2550h+var_2530], rax; int
0x18009e247  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009e24c  mov     rcx, [r14+32F8h]
0x18009e253  mov     edx, r12d
0x18009e256  mov     rax, [rcx]
0x18009e259  mov     rax, [rax+58h]
0x18009e25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e262  xor     edx, edx
0x18009e264  lea     rcx, [rsp+2550h+var_24F0]
0x18009e269  call    ??4?$TCntPtr@UIRdpImageCompressor@@@@QEAAPEAUIRdpImageCompressor@@PEAU1@@Z; TCntPtr<IRdpImageCompressor>::operator=(IRdpImageCompressor *)
0x18009e26e  lea     rcx, [rsp+2550h+var_24F0]
0x18009e273  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009e278  lea     r12, aStartpipeline; "StartPipeline"
0x18009e27f  mov     rcx, [r14+32F8h]
0x18009e286  mov     rax, [rcx]
0x18009e289  mov     rax, [rax+40h]
0x18009e28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e292  test    eax, eax
0x18009e294  mov     eax, cs:CallbackContext
0x18009e29a  jnz     loc_18009E68B
0x18009e2a0  mov     esi, 80004005h
0x18009e2a5  cmp     eax, 2
0x18009e2a8  jbe     loc_18009E663
0x18009e2ae  lea     rax, aCapabilityNoPr; "Capability: No profile available for th"...
0x18009e2b5  mov     qword ptr [rbp+2450h+var_24B0], r12
0x18009e2b9  mov     qword ptr [rsp+2550h+var_24E8], rax
0x18009e2be  lea     r12, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009e2c5  lea     rax, [rbp+2450h+var_24B0]
0x18009e2c9  mov     [rsp+2550h+var_24E0], 1348h
0x18009e2d1  mov     [rsp+2550h+var_2510], rax
0x18009e2d6  lea     rdx, byte_180278EBB
0x18009e2dd  lea     rax, [rsp+2550h+var_24E0]
0x18009e2e2  mov     [rbp+2450h+var_24D0], r12
0x18009e2e6  mov     [rsp+2550h+var_2518], rax
0x18009e2eb  lea     rax, [rbp+2450h+var_24D0]
0x18009e2ef  mov     [rsp+2550h+var_2520], rax
0x18009e2f4  lea     rax, [rsp+2550h+var_24D8]
0x18009e2f9  mov     [rsp+2550h+var_2528], rax
0x18009e2fe  lea     rax, [rsp+2550h+var_24E8]
0x18009e303  mov     qword ptr [rsp+2550h+var_2530], rax
0x18009e308  mov     dword ptr [rsp+2550h+var_24D8], esi
0x18009e30c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009e311  jmp     loc_18009E66A
0x18009e316  mov     rcx, [r14+32C0h]
0x18009e31d  lea     rdx, [rbp+2450h+var_24A0]
0x18009e321  mov     [rsp+2550h+var_2508], r13
0x18009e326  lea     r9, [rbp+2450h+var_2490]
0x18009e32a  mov     [rsp+2550h+var_2510], r13
0x18009e32f  xor     r8d, r8d
0x18009e332  mov     [rsp+2550h+var_2518], r13
0x18009e337  mov     [rsp+2550h+var_2520], rdx
0x18009e33c  lea     rdx, [rbp+2450h+var_2210]
0x18009e343  mov     [rsp+2550h+var_2528], rdx
0x18009e348  lea     rdx, [rbp+2450h+var_2350]
0x18009e34f  mov     [rbp+2450h+var_24A0], 10h
0x18009e356  mov     rax, [rcx]
0x18009e359  mov     qword ptr [rsp+2550h+var_2530], rdx; int
0x18009e35e  xor     edx, edx
0x18009e360  mov     rax, [rax+98h]
0x18009e367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e36c  mov     esi, eax
0x18009e36e  test    eax, eax
0x18009e370  jns     loc_18009E43E
0x18009e376  mov     r9d, eax; unsigned int
0x18009e379  lea     rdx, aPipemanagererr_69; "PipeManagerError_StartPipelineStartCaVi"...
0x18009e380  mov     r8d, 1319h; char *
0x18009e386  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18009e38d  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009e392  mov     eax, cs:CallbackContext
0x18009e398  cmp     eax, 2
0x18009e39b  jbe     loc_18009E421
0x18009e3a1  lea     rax, aUnableToGetpro; "Unable to GetProtocolSettings"
0x18009e3a8  mov     dword ptr [rbp+2450h+var_24C8], 131Ah
0x18009e3af  mov     qword ptr [rsp+2550h+var_24E8], rax
0x18009e3b4  lea     rbx, aStartpipeline; "StartPipeline"
0x18009e3bb  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009e3c2  mov     qword ptr [rsp+2550h+var_24E0], rbx
0x18009e3c7  mov     qword ptr [rbp+2450h+var_24B0], rax
0x18009e3cb  lea     r12, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009e3d2  lea     rax, [rsp+2550h+var_24E8]
0x18009e3d7  mov     [rbp+2450h+var_24D0], r12
0x18009e3db  mov     [rsp+2550h+var_2508], rax
0x18009e3e0  lea     rdx, dword_180278FD4
0x18009e3e7  lea     rax, [rsp+2550h+var_24E0]
0x18009e3ec  mov     [rsp+2550h+var_2510], rax
0x18009e3f1  lea     rax, [rbp+2450h+var_24C8]
0x18009e3f5  mov     [rsp+2550h+var_2518], rax
0x18009e3fa  lea     rax, [rbp+2450h+var_24D0]
0x18009e3fe  mov     [rsp+2550h+var_2520], rax
0x18009e403  lea     rax, [rsp+2550h+var_24D8]
0x18009e408  mov     [rsp+2550h+var_2528], rax
0x18009e40d  lea     rax, [rbp+2450h+var_24B0]
0x18009e411  mov     dword ptr [rsp+2550h+var_24D8], esi
0x18009e415  mov     qword ptr [rsp+2550h+var_2530], rax
0x18009e41a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009e41f  jmp     short loc_18009E42F
0x18009e421  lea     rbx, aStartpipeline; "StartPipeline"
0x18009e428  lea     r12, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009e42f  lea     rcx, [rsp+2550h+var_24F0]
0x18009e434  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009e439  jmp     loc_18009EA3C
0x18009e43e  mov     r8d, [rbp+2450h+var_24A0]
0x18009e442  mov     ebx, r13d
0x18009e445  mov     esi, r13d
0x18009e448  mov     edx, r13d
0x18009e44b  test    r8d, r8d
0x18009e44e  jz      short loc_18009E47F
0x18009e450  mov     eax, edx
0x18009e452  lea     rcx, [rax+rax*4]
0x18009e456  mov     eax, [rbp+rcx*4+2450h+var_2488]
0x18009e45a  sub     eax, [rbp+rcx*4+2450h+var_2490]
0x18009e45e  inc     eax
0x18009e460  cmp     eax, ebx
0x18009e462  cmovbe  eax, ebx
0x18009e465  mov     ebx, eax
0x18009e467  mov     eax, [rbp+rcx*4+2450h+var_2484]
0x18009e46b  sub     eax, [rbp+rcx*4+2450h+var_248C]
0x18009e46f  inc     eax
0x18009e471  cmp     eax, esi
0x18009e473  cmovbe  eax, esi
0x18009e476  inc     edx
0x18009e478  mov     esi, eax
0x18009e47a  cmp     edx, r8d
0x18009e47d  jb      short loc_18009E450
0x18009e47f  mov     eax, cs:CallbackContext
0x18009e485  cmp     eax, 4
0x18009e488  jbe     short loc_18009E4C6
  ... truncated ...
```
