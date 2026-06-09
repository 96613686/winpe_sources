# AvcProgressiveWorkItem::Initialize(IUnknown *,uchar,_RDP_ENCODER_POLICY_ *,PipelineCodec,RdpSurface *,ulong,IRdpPipeEvents *,CapsDataAvc &,_RDPX_QUALITY,AvcEncodeSettings::MftSetting,float,IRdpPipeExtensionFactory *)

- ea: `0x1800ce948`
- end: `0x1800cf482`
- name: `?Initialize@AvcProgressiveWorkItem@@QEAAJPEAUIUnknown@@EPEAU_RDP_ENCODER_POLICY_@@W4PipelineCodec@@PEAVRdpSurface@@KPEAVIRdpPipeEvents@@AEAVCapsDataAvc@@T_RDPX_QUALITY@@W4MftSetting@AvcEncodeSettings@@MPEAVIRdpPipeExtensionFactory@@@Z`
- size: `2874`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b3810`

## callees

- `0x18000ce04`
- `0x18000e4ec`
- `0x180010d6c`
- `0x180076090`
- `0x1800772e0`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x18007a404`
- `0x18007cf90`
- `0x180088e24`
- `0x1800cc1c0`
- `0x1800cc8d0`
- `0x1800ce1fc`
- `0x1800ce948`
- `0x180157934`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800cf43a`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800cf462`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800cf43a`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800cf462`

## string_xrefs

- `0x1800cea96`: `pExtensionFactory`
- `0x1800cef31`: `OnGpuUsageStateUpdate failed`
- `0x1800cedb6`: `AvcProgressiveWorkItemError_InitializeCreateCompresserFail`
- `0x1800cf03f`: `AvcProgressiveWorkItemError_InitializeCreateCompresserFail`
- `0x1800cee04`: `Failed to create encoder`
- `0x1800cf27a`: `AvcCompressor initialization failed ...`
- `0x1800cf308`: `failed to create Dirty BA`
- `0x1800cf378`: `failed to create target BA`

## pseudocode

```c
__int64 __fastcall AvcProgressiveWorkItem::Initialize(
        __int64 a1,
        __int64 a2,
        char a3,
        _DWORD *a4,
        int a5,
        RdpSurface *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int16 a10,
        int a11,
        int a12,
        __int64 a13)
{
  RDPGraphicsTraceLogging *CodecName; // rax
  int Compressor; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v20; // edx
  const char *v21; // rcx
  RDPGraphicsTraceLogging *v22; // rax
  unsigned int v23; // eax
  _QWORD *v24; // r15
  RDPGraphicsTraceLogging *v25; // rax
  unsigned int v26; // eax
  int v27; // edx
  const char *v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  RDPGraphicsTraceLogging *v32; // rax
  RDPGraphicsTraceLogging *v33; // rax
  __int128 v34; // xmm0
  int v35; // eax
  __int128 v36; // xmm0
  int v37; // eax
  int v38; // eax
  RDPGraphicsTraceLogging *v39; // rax
  unsigned int v40; // eax
  int v41; // edx
  int v42; // ecx
  char v43; // r8
  __int64 v44; // r9
  int v45; // edx
  unsigned int v46; // eax
  int v47; // edx
  unsigned int v48; // eax
  RDPGraphicsTraceLogging *v49; // rax
  int v50; // ebx
  unsigned int v51; // eax
  RDPGraphicsTraceLogging *v52; // rax
  int v53; // edx
  unsigned int v54; // eax
  int v55; // eax
  char *v56; // rdx
  RDPGraphicsTraceLogging *v57; // rcx
  unsigned int v58; // r9d
  unsigned int v59; // eax
  RDPGraphicsTraceLogging *v60; // rax
  unsigned int v61; // eax
  RDPGraphicsTraceLogging *v62; // rax
  unsigned int v63; // eax
  int v64; // edx
  RDPGraphicsTraceLogging *v65; // rax
  int v67; // [rsp+20h] [rbp-98h]
  int v68; // [rsp+20h] [rbp-98h]
  int v69; // [rsp+20h] [rbp-98h]
  char *v70; // [rsp+38h] [rbp-80h]
  char v71; // [rsp+E8h] [rbp+30h]

  if ( !a6 )
  {
    CodecName = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
    Compressor = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      CodecName,
      "AvcProgressiveWorkItemError_InitializeNullPointer",
      (char *)0x6F,
      0x80004003,
      v67);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 10;
      v21 = "pSurface";
LABEL_6:
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        (unsigned int)WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v21);
      return (unsigned int)Compressor;
    }
    return (unsigned int)Compressor;
  }
  if ( a4 )
  {
    if ( !a13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
          v23,
          (__int64)"pExtensionFactory");
      }
      return (unsigned int)-2147467261;
    }
    v24 = (_QWORD *)(a1 + 56);
    if ( *(_QWORD *)(a1 + 56) )
    {
      v25 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
      Compressor = -2147467259;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        v25,
        "AvcProgressiveWorkItemError_InitializeReinitializeFail",
        (char *)0x78,
        0x80004005,
        v67);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Compressor;
      }
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      v27 = 13;
      v28 = "Initialize called again??";
      goto LABEL_23;
    }
    TCntPtr<IRDPCoreVirtualChannel>::operator=(a1 + 144, a2);
    *(_DWORD *)(a1 + 76) = a5;
    *(_DWORD *)(a1 + 80) = *((_DWORD *)a6 + 18);
    *(_DWORD *)(a1 + 84) = *((_DWORD *)a6 + 19);
    *(_DWORD *)(a1 + 88) = a11;
    if ( a13 != *(_QWORD *)(a1 + 256) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease(a1 + 256);
      *(_QWORD *)(a1 + 256) = a13;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a13 + 8LL))(a13);
    }
    v29 = a4[2];
    *(_DWORD *)(a1 + 208) = v29;
    if ( v29 )
    {
      if ( v29 == 1 )
      {
        v32 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
        Compressor = -2147467259;
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          v32,
          "AvcProgressiveWorkItemError_InitializeLosslessMode",
          (char *)0x8C,
          0x80004005,
          v67);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)Compressor;
        }
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        v27 = 14;
        v28 = "Lossless image quality mode is not supported for AVC";
        goto LABEL_23;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 208) = 3;
    }
    v30 = *(unsigned int *)(a1 + 76);
    if ( (_DWORD)v30 == 7 )
    {
      v36 = CODEC_GUID_AVC420_CODEC;
    }
    else
    {
      if ( (_DWORD)v30 != 12 )
      {
        if ( (unsigned int)(v30 - 8) > 1 )
        {
          if ( (_DWORD)v30 == 10 )
          {
            *(_OWORD *)(a1 + 124) = CODEC_GUID_HEVC_CODEC;
            v31 = a4[7];
            if ( v31 )
              *(_DWORD *)(a1 + 224) = v31;
            *(_DWORD *)(a1 + 244) = 0;
LABEL_62:
            Compressor = AvcProgressiveWorkItem::CreateCompressor((AvcProgressiveWorkItem *)a1);
            if ( Compressor < 0 )
            {
              v39 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                v39,
                "AvcProgressiveWorkItemError_InitializeCreateCompresserFail",
                (char *)0xFA,
                Compressor,
                v67);
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                return (unsigned int)Compressor;
              }
              v40 = RdpWppGetCurrentThreadActivityIdPrefix();
              v41 = 17;
              goto LABEL_67;
            }
            v42 = *(_DWORD *)(a1 + 224);
            v43 = 18;
            v44 = *(unsigned int *)(a1 + 208);
            *(_DWORD *)(a1 + 240) = a12;
            if ( !v42 )
              v43 = a3;
            v71 = v43;
            v70 = (char *)(a1 + 88);
            v68 = *(_DWORD *)(a1 + 196);
            Compressor = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)*v24 + 88LL))(
                           *v24,
                           *(unsigned int *)(a1 + 80),
                           *(unsigned int *)(a1 + 84),
                           v44);
            if ( Compressor >= 0 )
            {
              if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 56) + 48LL))(*(_QWORD *)(a1 + 56)) )
              {
                Compressor = RdpSurface::OnGpuUsageStateUpdate(a6, v45);
                if ( Compressor < 0 )
                {
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    return (unsigned int)Compressor;
                  }
                  v46 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v47 = 18;
                  goto LABEL_77;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  v48 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    19,
                    WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
                    v48);
                }
              }
              Compressor = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 56) + 112LL))(
                             *(_QWORD *)(a1 + 56),
                             a8);
              if ( Compressor >= 0 )
                goto LABEL_110;
            }
            if ( *(_DWORD *)(a1 + 244) )
            {
              if ( *(_DWORD *)(a1 + 88) != 1 )
                goto LABEL_105;
              v49 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                v49,
                "AvcProgressiveWorkItemError_InitializeSoftwareFallback",
                (char *)0x130,
                0,
                v68);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v50 = *(_DWORD *)(a1 + 88);
                v51 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  20,
                  WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
                  v51,
                  v50);
              }
              TCntPtr<IRdpAvcEncoder>::operator=(v24);
              *(_DWORD *)(a1 + 88) = AvcEncodeSettings::GetDefaultOrFallbackAvcEncoderInfo();
              Compressor = AvcProgressiveWorkItem::CreateCompressor((AvcProgressiveWorkItem *)a1);
              if ( Compressor < 0 )
              {
                v52 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  v52,
                  "AvcProgressiveWorkItemError_InitializeCreateCompresserFail",
                  (char *)0x13D,
                  Compressor,
                  v69);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  return (unsigned int)Compressor;
                }
                v40 = RdpWppGetCurrentThreadActivityIdPrefix();
                v41 = 21;
LABEL_67:
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v41,
                  (unsigned int)WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
                  v40,
                  (__int64)"Failed to create encoder",
                  Compressor);
                return (unsigned int)Compressor;
              }
              v70 = (char *)(a1 + 88);
              v68 = *(_DWORD *)(a1 + 196);
              Compressor = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 56) + 88LL))(
                             *(_QWORD *)(a1 + 56),
                             *(unsigned int *)(a1 + 80),
                             *(unsigned int *)(a1 + 84),
                             *(unsigned int *)(a1 + 208));
              if ( Compressor >= 0 )
              {
                *(_DWORD *)(a1 + 248) = 1;
                Compressor = RdpSurface::OnGpuUsageStateUpdate(a6, v53);
                if ( Compressor < 0 )
                {
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    return (unsigned int)Compressor;
                  }
                  v46 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v47 = 22;
LABEL_77:
                  WPP_SF_DsD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v47,
                    (unsigned int)WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
                    v46,
                    (__int64)"OnGpuUsageStateUpdate failed",
                    Compressor);
                  return (unsigned int)Compressor;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  v54 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    23,
                    WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
                    v54);
                }
                Compressor = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 56) + 112LL))(
                               *(_QWORD *)(a1 + 56),
                               a8);
LABEL_105:
                if ( Compressor < 0 )
                  goto LABEL_106;
LABEL_110:
                if ( (unsigned int)(a11 - 1) <= 1 && *(_DWORD *)(a1 + 88) == 3 )
                  *(_DWORD *)(a1 + 248) = 1;
                Compressor = RgnlibBA_CreateInstance(a1 + 152);
                if ( Compressor < 0 )
                {
                  v60 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
                  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                    v60,
                    "AvcProgressiveWorkItemError_InitializeInitializeFail",
                    (char *)0x167,
                    Compressor,
                    v68);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v61 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      25,
                      (unsigned int)WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
                      v61,
                      (__int64)"failed to create Dirty BA",
                      Compressor);
                  }
                  return (unsigned int)Compressor;
                }
                Compressor = RgnlibBA_CreateInstance(a1 + 160);
                if ( Compressor >= 0 )
                {
                  Compressor = RgnlibBA_CreateInstance(a1 + 168);
                  if ( Compressor >= 0 )
                  {
                    *(_BYTE *)(a1 + 120) = v71;
                    *(_QWORD *)(a1 + 176) = 0;
                    *(_QWORD *)(a1 + 184) = 0;
                    *(_QWORD *)(a1 + 64) = a6;
                    TCntPtr<IRdpPipeEvents>::operator=(a1 + 112, a8);
                    Compressor = RDPAPI_GetGenericCounter(
                                   L"RDV::RDP::GraphicsPipeline::WorkItemCodecStart",
                                   0xFFFFFFFFLL,
                                   0xFFFFFFFFLL,
                                   0xFFFFFFFFLL,
                                   4,
                                   a1 + 96);
                    if ( Compressor >= 0 )
                      return (unsigned int)RDPAPI_GetGenericCounter(
                                             L"RDV::RDP::GraphicsPipeline::WorkItemCodecEnd",
                                             0xFFFFFFFFLL,
                                             0xFFFFFFFFLL,
                                             0xFFFFFFFFLL,
                                             4,
                                             a1 + 104);
                    return (unsigned int)Compressor;
                  }
                  v65 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
                  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                    v65,
                    "AvcProgressiveWorkItemError_InitializeInitializeFail",
                    (char *)0x16F,
                    Compressor,
                    v68);
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    return (unsigned int)Compressor;
                  }
                  v63 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v64 = 27;
                }
                else
                {
                  v62 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
                  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                    v62,
                    "AvcProgressiveWorkItemError_InitializeInitializeFail",
                    (char *)0x16B,
                    Compressor,
                    v68);
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                  {
                    return (unsigned int)Compressor;
                  }
                  v63 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v64 = 26;
                }
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v64,
                  (unsigned int)WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
                  v63,
                  (__int64)"failed to create target BA",
                  Compressor);
                return (unsigned int)Compressor;
              }
            }
LABEL_106:
            v55 = GetCodecName(*(unsigned int *)(a1 + 76));
            RDPGraphicsTraceLogging::LogRDPGraphicInitializeCompressorFailure(
              v57,
              Compressor,
              v55,
              (char *)*(unsigned int *)(a1 + 80),
              *(_DWORD *)(a1 + 84),
              v58,
              v56,
              v70);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v59 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                (unsigned int)WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
                v59,
                (__int64)"AvcCompressor initialization failed ...",
                Compressor);
            }
            return (unsigned int)Compressor;
          }
          *(_OWORD *)(a1 + 124) = 0;
          v33 = (RDPGraphicsTraceLogging *)GetCodecName(v30);
          Compressor = -2147467259;
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            v33,
            "AvcProgressiveWorkItemError_InitializeBadCodec",
            (char *)0xE3,
            0x80004005,
            v67);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return (unsigned int)Compressor;
          }
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          v27 = 15;
          v28 = "AVC Workitem called with a non AVC codec";
LABEL_23:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v27,
            (unsigned int)WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids,
            v26,
            (__int64)v28,
            5);
          return (unsigned int)Compressor;
        }
        if ( (_DWORD)v30 == 8 )
          v34 = CODEC_GUID_AVC444V1_CODEC;
        else
          v34 = CODEC_GUID_AVC444V2_CODEC;
        *(_OWORD *)(a1 + 124) = v34;
        if ( (_BYTE)a10 != 0xFF )
          *(_DWORD *)(a1 + 196) = (unsigned __int8)a10;
        if ( HIBYTE(a10) != 0xFF )
          *(_DWORD *)(a1 + 200) = HIBYTE(a10);
        v35 = a4[5];
        if ( v35 )
          *(_DWORD *)(a1 + 204) = v35;
LABEL_57:
        v37 = a4[6];
        if ( v37 )
          *(_DWORD *)(a1 + 220) = v37;
        v38 = a4[8];
        if ( v38 )
          *(_DWORD *)(a1 + 228) = v38;
        *(_DWORD *)(a1 + 244) = 1;
        goto LABEL_62;
      }
      v36 = CODEC_GUID_AVC420_DRM_CODEC;
    }
    *(_OWORD *)(a1 + 124) = v36;
    if ( (_BYTE)a10 != 0xFF )
      *(_DWORD *)(a1 + 196) = (unsigned __int8)a10;
    goto LABEL_57;
  }
  v22 = (RDPGraphicsTraceLogging *)GetCodecName(*(unsigned int *)(a1 + 76));
  Compressor = -2147467261;
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    v22,
    "AvcProgressiveWorkItemError_InitializeNullPointer",
    (char *)0x71,
    0x80004003,
    v67);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 11;
    v21 = "policy";
    goto LABEL_6;
  }
  return (unsigned int)Compressor;
}

```

## disassembly

```asm
0x1800ce948  push    rbx
0x1800ce94a  push    rbp
0x1800ce94b  push    rsi
0x1800ce94c  push    rdi
0x1800ce94d  push    r12
0x1800ce94f  push    r13
0x1800ce951  push    r14
0x1800ce953  push    r15
0x1800ce955  sub     rsp, 78h
0x1800ce959  mov     rbp, [rsp+0B8h+arg_28]
0x1800ce961  mov     rbx, r9
0x1800ce964  movaps  [rsp+0B8h+var_58], xmm6
0x1800ce969  mov     rdi, rcx
0x1800ce96c  movzx   r13d, r8b
0x1800ce970  test    rbp, rbp
0x1800ce973  jnz     loc_1800CE9FA
0x1800ce979  mov     ecx, [rcx+4Ch]
0x1800ce97c  call    ?GetCodecName@@YAPEADW4PipelineCodec@@@Z; GetCodecName(PipelineCodec)
0x1800ce981  mov     ebx, 80004003h
0x1800ce986  lea     r8d, [rbp+6Fh]; char *
0x1800ce98a  mov     r9d, ebx; unsigned int
0x1800ce98d  lea     rdx, aAvcprogressive_19; "AvcProgressiveWorkItemError_InitializeN"...
0x1800ce994  mov     rcx, rax; this
0x1800ce997  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800ce99c  mov     rax, cs:WPP_GLOBAL_Control
0x1800ce9a3  lea     rsi, WPP_GLOBAL_Control
0x1800ce9aa  cmp     rax, rsi
0x1800ce9ad  jz      loc_1800CF46A
0x1800ce9b3  test    byte ptr [rax+1Ch], 8
0x1800ce9b7  jz      loc_1800CF46A
0x1800ce9bd  cmp     byte ptr [rax+19h], 2
0x1800ce9c1  jb      loc_1800CF46A
0x1800ce9c7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ce9cc  lea     edx, [rbp+0Ah]
0x1800ce9cf  lea     rcx, aPsurface; "pSurface"
0x1800ce9d6  mov     qword ptr [rsp+0B8h+var_98], rcx
0x1800ce9db  lea     r8, WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids
0x1800ce9e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce9e9  mov     r9d, eax
0x1800ce9ec  mov     rcx, [rcx+10h]
0x1800ce9f0  call    WPP_SF_Ds
0x1800ce9f5  jmp     loc_1800CF46A
0x1800ce9fa  test    rbx, rbx
0x1800ce9fd  jnz     short loc_1800CEA65
0x1800ce9ff  mov     ecx, [rcx+4Ch]
0x1800cea02  call    ?GetCodecName@@YAPEADW4PipelineCodec@@@Z; GetCodecName(PipelineCodec)
0x1800cea07  mov     ebx, 80004003h
0x1800cea0c  lea     rdx, aAvcprogressive_19; "AvcProgressiveWorkItemError_InitializeN"...
0x1800cea13  mov     r9d, ebx; unsigned int
0x1800cea16  mov     rcx, rax; this
0x1800cea19  mov     r8d, 71h ; 'q'; char *
0x1800cea1f  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800cea24  mov     rax, cs:WPP_GLOBAL_Control
0x1800cea2b  lea     rsi, WPP_GLOBAL_Control
0x1800cea32  cmp     rax, rsi
0x1800cea35  jz      loc_1800CF46A
0x1800cea3b  test    byte ptr [rax+1Ch], 8
0x1800cea3f  jz      loc_1800CF46A
0x1800cea45  cmp     byte ptr [rax+19h], 2
0x1800cea49  jb      loc_1800CF46A
0x1800cea4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cea54  mov     edx, 0Bh
0x1800cea59  lea     rcx, aPolicy; "policy"
0x1800cea60  jmp     loc_1800CE9D6
0x1800cea65  mov     rsi, [rsp+0B8h+arg_60]
0x1800cea6d  test    rsi, rsi
0x1800cea70  jnz     short loc_1800CEACB
0x1800cea72  mov     rax, cs:WPP_GLOBAL_Control
0x1800cea79  lea     rsi, WPP_GLOBAL_Control
0x1800cea80  cmp     rax, rsi
0x1800cea83  jz      short loc_1800CEAC1
0x1800cea85  test    byte ptr [rax+1Ch], 8
0x1800cea89  jz      short loc_1800CEAC1
0x1800cea8b  cmp     byte ptr [rax+19h], 2
0x1800cea8f  jb      short loc_1800CEAC1
0x1800cea91  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cea96  lea     rcx, aPextensionfact; "pExtensionFactory"
0x1800cea9d  mov     edx, 0Ch
0x1800ceaa2  mov     qword ptr [rsp+0B8h+var_98], rcx
0x1800ceaa7  lea     r8, WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids
0x1800ceaae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceab5  mov     r9d, eax
0x1800ceab8  mov     rcx, [rcx+10h]
0x1800ceabc  call    WPP_SF_Ds
0x1800ceac1  mov     ebx, 80004003h
0x1800ceac6  jmp     loc_1800CF46A
0x1800ceacb  lea     r15, [rcx+38h]
0x1800ceacf  cmp     qword ptr [r15], 0
0x1800cead3  jz      loc_1800CEB66
0x1800cead9  mov     ecx, [rcx+4Ch]
0x1800ceadc  call    ?GetCodecName@@YAPEADW4PipelineCodec@@@Z; GetCodecName(PipelineCodec)
0x1800ceae1  mov     ebx, 80004005h
0x1800ceae6  lea     rdx, aAvcprogressive_10; "AvcProgressiveWorkItemError_InitializeR"...
0x1800ceaed  mov     r9d, ebx; unsigned int
0x1800ceaf0  mov     rcx, rax; this
0x1800ceaf3  mov     r8d, 78h ; 'x'; char *
0x1800ceaf9  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800ceafe  mov     rax, cs:WPP_GLOBAL_Control
0x1800ceb05  lea     rsi, WPP_GLOBAL_Control
0x1800ceb0c  cmp     rax, rsi
0x1800ceb0f  jz      loc_1800CF46A
0x1800ceb15  test    byte ptr [rax+1Ch], 8
0x1800ceb19  jz      loc_1800CF46A
0x1800ceb1f  cmp     byte ptr [rax+19h], 2
0x1800ceb23  jb      loc_1800CF46A
0x1800ceb29  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ceb2e  mov     edx, 0Dh
0x1800ceb33  lea     rcx, aInitializeCall; "Initialize called again??"
0x1800ceb3a  mov     [rsp+0B8h+var_90], 80004005h
0x1800ceb42  mov     qword ptr [rsp+0B8h+var_98], rcx
0x1800ceb47  lea     r8, WPP_31da59e976293b80d4967d257e9d0aa8_Traceguids
0x1800ceb4e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceb55  mov     r9d, eax
0x1800ceb58  mov     rcx, [rcx+10h]
0x1800ceb5c  call    WPP_SF_DsD
0x1800ceb61  jmp     loc_1800CF46A
0x1800ceb66  add     rcx, 90h
0x1800ceb6d  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x1800ceb72  mov     eax, [rsp+0B8h+arg_20]
0x1800ceb79  lea     r12, [rdi+58h]
0x1800ceb7d  mov     [rdi+4Ch], eax
0x1800ceb80  lea     r14, [rdi+100h]
0x1800ceb87  mov     eax, [rbp+48h]
0x1800ceb8a  mov     [rdi+50h], eax
0x1800ceb8d  mov     eax, [rbp+4Ch]
0x1800ceb90  mov     [rdi+54h], eax
0x1800ceb93  mov     eax, [rsp+0B8h+arg_50]
0x1800ceb9a  mov     [r12], eax
0x1800ceb9e  cmp     rsi, [r14]
0x1800ceba1  jz      short loc_1800CEBBD
0x1800ceba3  mov     rcx, r14
0x1800ceba6  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800cebab  mov     [r14], rsi
0x1800cebae  mov     rcx, rsi
0x1800cebb1  mov     rax, [rsi]
0x1800cebb4  mov     rax, [rax+8]
0x1800cebb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cebbd  mov     eax, [rbx+8]
0x1800cebc0  xor     esi, esi
0x1800cebc2  mov     [rdi+0D0h], eax
0x1800cebc8  mov     edx, 1
0x1800cebcd  test    eax, eax
0x1800cebcf  jnz     short loc_1800CEC28
0x1800cebd1  mov     dword ptr [rdi+0D0h], 3
0x1800cebdb  mov     ecx, [rdi+4Ch]
0x1800cebde  cmp     ecx, 7
0x1800cebe1  jz      loc_1800CED59
0x1800cebe7  cmp     ecx, 0Ch
0x1800cebea  jz      loc_1800CED50
0x1800cebf0  lea     eax, [rcx-8]
0x1800cebf3  cmp     eax, edx
0x1800cebf5  jbe     loc_1800CECFD
0x1800cebfb  cmp     ecx, 0Ah
0x1800cebfe  jnz     loc_1800CEC92
0x1800cec04  movups  xmm0, cs:CODEC_GUID_HEVC_CODEC
0x1800cec0b  movdqu  xmmword ptr [rdi+7Ch], xmm0
0x1800cec10  mov     eax, [rbx+1Ch]
0x1800cec13  test    eax, eax
0x1800cec15  jz      short loc_1800CEC1D
0x1800cec17  mov     [rdi+0E0h], eax
0x1800cec1d  mov     [rdi+0F4h], esi
0x1800cec23  jmp     loc_1800CED9D
0x1800cec28  cmp     eax, edx
0x1800cec2a  jnz     short loc_1800CEBDB
0x1800cec2c  mov     ecx, [rdi+4Ch]
0x1800cec2f  call    ?GetCodecName@@YAPEADW4PipelineCodec@@@Z; GetCodecName(PipelineCodec)
0x1800cec34  mov     ebx, 80004005h
0x1800cec39  lea     rdx, aAvcprogressive_34; "AvcProgressiveWorkItemError_InitializeL"...
0x1800cec40  mov     r9d, ebx; unsigned int
0x1800cec43  mov     rcx, rax; this
0x1800cec46  mov     r8d, 8Ch; char *
0x1800cec4c  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800cec51  mov     rax, cs:WPP_GLOBAL_Control
0x1800cec58  lea     rsi, WPP_GLOBAL_Control
0x1800cec5f  cmp     rax, rsi
0x1800cec62  jz      loc_1800CF46A
0x1800cec68  test    byte ptr [rax+1Ch], 8
0x1800cec6c  jz      loc_1800CF46A
0x1800cec72  cmp     byte ptr [rax+19h], 2
0x1800cec76  jb      loc_1800CF46A
0x1800cec7c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cec81  mov     edx, 0Eh
0x1800cec86  lea     rcx, aLosslessImageQ; "Lossless image quality mode is not supp"...
0x1800cec8d  jmp     loc_1800CEB3A
0x1800cec92  xorps   xmm0, xmm0
0x1800cec95  movdqu  xmmword ptr [rdi+7Ch], xmm0
0x1800cec9a  call    ?GetCodecName@@YAPEADW4PipelineCodec@@@Z; GetCodecName(PipelineCodec)
0x1800cec9f  mov     ebx, 80004005h
0x1800ceca4  lea     rdx, aAvcprogressive_28; "AvcProgressiveWorkItemError_InitializeB"...
0x1800cecab  mov     r9d, ebx; unsigned int
0x1800cecae  mov     rcx, rax; this
0x1800cecb1  mov     r8d, 0E3h; char *
0x1800cecb7  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800cecbc  mov     rax, cs:WPP_GLOBAL_Control
0x1800cecc3  lea     rsi, WPP_GLOBAL_Control
0x1800cecca  cmp     rax, rsi
0x1800ceccd  jz      loc_1800CF46A
0x1800cecd3  test    byte ptr [rax+1Ch], 8
0x1800cecd7  jz      loc_1800CF46A
0x1800cecdd  cmp     byte ptr [rax+19h], 2
0x1800cece1  jb      loc_1800CF46A
0x1800cece7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cecec  mov     edx, 0Fh
0x1800cecf1  lea     rcx, aAvcWorkitemCal; "AVC Workitem called with a non AVC code"...
0x1800cecf8  jmp     loc_1800CEB3A
0x1800cecfd  cmp     ecx, 8
0x1800ced00  jnz     short loc_1800CED0B
0x1800ced02  movups  xmm0, cs:CODEC_GUID_AVC444V1_CODEC
0x1800ced09  jmp     short loc_1800CED12
0x1800ced0b  movups  xmm0, cs:CODEC_GUID_AVC444V2_CODEC
0x1800ced12  cmp     [rsp+0B8h+arg_48], 0FFh
0x1800ced1a  movdqu  xmmword ptr [rdi+7Ch], xmm0
0x1800ced1f  jz      short loc_1800CED2F
0x1800ced21  movzx   eax, [rsp+0B8h+arg_48]
0x1800ced29  mov     [rdi+0C4h], eax
0x1800ced2f  movzx   eax, [rsp+0B8h+arg_49]
0x1800ced37  cmp     al, 0FFh
0x1800ced39  jz      short loc_1800CED41
0x1800ced3b  mov     [rdi+0C8h], eax
0x1800ced41  mov     eax, [rbx+14h]
0x1800ced44  test    eax, eax
0x1800ced46  jz      short loc_1800CED7D
0x1800ced48  mov     [rdi+0CCh], eax
0x1800ced4e  jmp     short loc_1800CED7D
0x1800ced50  movups  xmm0, cs:CODEC_GUID_AVC420_DRM_CODEC
0x1800ced57  jmp     short loc_1800CED60
0x1800ced59  movups  xmm0, cs:CODEC_GUID_AVC420_CODEC
0x1800ced60  cmp     [rsp+0B8h+arg_48], 0FFh
0x1800ced68  movdqu  xmmword ptr [rdi+7Ch], xmm0
0x1800ced6d  jz      short loc_1800CED7D
0x1800ced6f  movzx   eax, [rsp+0B8h+arg_48]
0x1800ced77  mov     [rdi+0C4h], eax
0x1800ced7d  mov     eax, [rbx+18h]
0x1800ced80  test    eax, eax
0x1800ced82  jz      short loc_1800CED8A
0x1800ced84  mov     [rdi+0DCh], eax
0x1800ced8a  mov     eax, [rbx+20h]
0x1800ced8d  test    eax, eax
0x1800ced8f  jz      short loc_1800CED97
0x1800ced91  mov     [rdi+0E4h], eax
0x1800ced97  mov     [rdi+0F4h], edx
0x1800ced9d  mov     rcx, rdi; this
0x1800ceda0  call    ?CreateCompressor@AvcProgressiveWorkItem@@MEAAJXZ; AvcProgressiveWorkItem::CreateCompressor(void)
0x1800ceda5  mov     ebx, eax
0x1800ceda7  test    eax, eax
0x1800ceda9  jns     short loc_1800CEE10
0x1800cedab  mov     ecx, [rdi+4Ch]
0x1800cedae  call    ?GetCodecName@@YAPEADW4PipelineCodec@@@Z; GetCodecName(PipelineCodec)
0x1800cedb3  mov     rcx, rax; this
0x1800cedb6  lea     rdx, aAvcprogressive_13; "AvcProgressiveWorkItemError_InitializeC"...
0x1800cedbd  mov     r9d, ebx; unsigned int
0x1800cedc0  mov     r8d, 0FAh; char *
0x1800cedc6  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800cedcb  mov     rax, cs:WPP_GLOBAL_Control
0x1800cedd2  lea     rsi, WPP_GLOBAL_Control
0x1800cedd9  cmp     rax, rsi
0x1800ceddc  jz      loc_1800CF46A
0x1800cede2  test    byte ptr [rax+1Ch], 8
0x1800cede6  jz      loc_1800CF46A
0x1800cedec  cmp     byte ptr [rax+19h], 2
0x1800cedf0  jb      loc_1800CF46A
0x1800cedf6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800cedfb  mov     edx, 11h
0x1800cee00  mov     [rsp+0B8h+var_90], ebx
0x1800cee04  lea     rcx, aFailedToCreate_29; "Failed to create encoder"
0x1800cee0b  jmp     loc_1800CEB42
0x1800cee10  cmp     [rdi+0CCh], esi
0x1800cee16  mov     eax, esi
0x1800cee18  mov     ecx, [rdi+0E0h]
0x1800cee1e  mov     r8d, 12h
0x1800cee24  movss   xmm6, [rsp+0B8h+arg_58]
0x1800cee2d  setnz   al
0x1800cee30  mov     r9d, [rdi+0D0h]
0x1800cee37  mov     edx, eax
0x1800cee39  or      edx, 2
0x1800cee3c  mov     [rsp+0B8h+var_68], rbp
0x1800cee41  cmp     [rdi+0DCh], esi
0x1800cee47  movss   [rsp+0B8h+var_70], xmm6
0x1800cee4d  cmovz   edx, eax
0x1800cee50  movss   dword ptr [rdi+0F0h], xmm6
0x1800cee58  mov     eax, edx
0x1800cee5a  test    ecx, ecx
0x1800cee5c  cmovz   r8d, r13d
0x1800cee60  or      eax, 4
0x1800cee63  test    ecx, ecx
0x1800cee65  mov     dword ptr [rsp+0B8h+arg_28], r8d
0x1800cee6d  mov     rcx, [r15]
0x1800cee70  mov     r8d, [rdi+54h]
0x1800cee74  cmovz   eax, edx
0x1800cee77  mov     edx, [rsp+0B8h+arg_30]
0x1800cee7e  mov     r13d, eax
0x1800cee81  or      r13d, 8
0x1800cee85  cmp     [rdi+0E4h], esi
0x1800cee8b  cmovz   r13d, eax
0x1800cee8f  mov     rax, [rcx]
0x1800cee92  mov     [rsp+0B8h+var_78], r13d
0x1800cee97  mov     [rsp+0B8h+var_80], r12
0x1800cee9c  mov     dword ptr [rsp+0B8h+var_88], edx
0x1800ceea0  mov     edx, [rdi+0C8h]
0x1800ceea6  mov     rax, [rax+58h]
  ... truncated ...
```
