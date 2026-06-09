# RdpWorkItemManager::GetProgressiveWorkItem(_GUID,RdpSurface *,IRdpPipeManager *,IRdpPipeEvents *,_RDPX_QUALITY,_RDP_ENCODER_POLICY_ *,IRdpProgressiveEncoderWorkItem * *)

- ea: `0x1800b3810`
- end: `0x1800b4a91`
- name: `?GetProgressiveWorkItem@RdpWorkItemManager@@UEAAJU_GUID@@PEAVRdpSurface@@PEAVIRdpPipeManager@@PEAVIRdpPipeEvents@@T_RDPX_QUALITY@@PEAU_RDP_ENCODER_POLICY_@@PEAPEAVIRdpProgressiveEncoderWorkItem@@@Z`
- size: `4737`
- prototype: `int __high(struct _GUID, struct RdpSurface *, struct IRdpPipeManager *, struct IRdpPipeEvents *, union _RDPX_QUALITY, struct _RDP_ENCODER_POLICY_ *, struct IRdpProgressiveEncoderWorkItem **)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000ce04`
- `0x18000e4ec`
- `0x18001f2bc`
- `0x18001f810`
- `0x180046e64`
- `0x18004d560`
- `0x180076090`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x180079d2c`
- `0x18007a404`
- `0x18007a664`
- `0x18007f6b0`
- `0x1800b1eb0`
- `0x1800b3810`
- `0x1800cbff0`
- `0x1800ce948`
- `0x1800cf4a0`
- `0x1800cfd78`
- `0x1800d0878`
- `0x180158180`
- `0x18016cae0`
- `0x18019b310`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b4571`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b4571`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b45df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b45df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4532`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4532`

## string_xrefs

- `0x1800b4524`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x1800b3d9f`: `AddCompressorInstance failed`
- `0x1800b4039`: `spProtocol`
- `0x1800b473f`: `spProtocol`
- `0x1800b3c13`: `WorkItemManagerError_GetProgWorkItemCreateProgCaCompressorFail`
- `0x1800b3c9f`: `WorkItemManagerError_GetProgWorkItemCreateProgCaCompressorFail`
- `0x1800b3d5a`: `WorkItemManagerError_GetProgWorkItemCreateProgCaCompressorFail`
- `0x1800b3cda`: `Failed to create progressive encoderEx!`
- `0x1800b41ee`: `WorkItemManagerError_GetProgWorkItemCreateAvcWorkItemFail`
- `0x1800b49ef`: `WorkItemManagerError_GetProgWorkItemCreateAvcWorkItemFail`
- `0x1800b3f65`: `WorkItemManagerError_GetProgWorkItemGetProtocolFail`
- `0x1800b3ff5`: `WorkItemManagerError_GetProgWorkItemGetProtocolFail`
- `0x1800b466b`: `WorkItemManagerError_GetProgWorkItemGetProtocolFail`
- `0x1800b46fb`: `WorkItemManagerError_GetProgWorkItemGetProtocolFail`
- `0x1800b3fa0`: `GetProtocol failed.`
- `0x1800b46a6`: `GetProtocol failed.`
- `0x1800b40c6`: `m_spExtensionFactory`
- `0x1800b47cc`: `m_spExtensionFactory`
- `0x1800b43e2`: `WorkItemManagerError_GetProgWorkItemCreateCaProgWorkItemFail`

## pseudocode

```c
__int64 __fastcall RdpWorkItemManager::GetProgressiveWorkItem(
        RdpWorkItemManager *a1,
        struct _GUID *a2,
        RdpSurface *a3,
        __int64 *a4,
        __int64 a5,
        unsigned __int8 a6,
        __int64 a7,
        struct IRdpProgressiveEncoderWorkItem **a8)
{
  RdpSurface *v8; // rbx
  int ProgressiveWorkitem; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v13; // edx
  const char *v14; // rcx
  const wchar_t *v15; // rbx
  unsigned int v16; // eax
  signed int GraphicsSourceContext; // eax
  unsigned int v18; // eax
  int v19; // edx
  const char *v20; // rcx
  signed int Instance; // eax
  unsigned int v22; // eax
  signed int v23; // eax
  __int64 v24; // rbx
  signed int v25; // eax
  unsigned int v26; // eax
  AvcProgressiveWorkItem *v27; // rax
  AvcProgressiveWorkItem *v28; // rax
  AvcProgressiveWorkItem *v29; // r13
  signed int v30; // eax
  unsigned int v31; // eax
  int v32; // edx
  const char *v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // eax
  int v36; // edx
  const char *v37; // rcx
  RdpWorkItemManager *v38; // rax
  RdpSurface *v39; // rdi
  signed int v40; // eax
  __int64 v41; // rcx
  unsigned int v42; // eax
  int v43; // edx
  const char *v44; // rcx
  CalistaSurfaceProgressiveWorkItem *v45; // rax
  CalistaSurfaceProgressiveWorkItem *v46; // rax
  CalistaSurfaceProgressiveWorkItem *v47; // rbx
  __int64 v48; // r8
  signed int v49; // eax
  unsigned int v50; // eax
  __int64 (__fastcall ***v51)(_QWORD, GUID *, struct IRdpGFXSourceUpdateContext **); // rcx
  unsigned int v52; // eax
  __int64 *v53; // rsi
  AvcProgressiveWorkItem *v54; // rax
  AvcProgressiveWorkItem *v55; // rax
  AvcProgressiveWorkItem *v56; // rbx
  __int64 v57; // rax
  signed int v58; // eax
  unsigned int v59; // eax
  int v60; // edx
  const char *v61; // rcx
  unsigned int v62; // eax
  int v63; // edx
  const char *v64; // rcx
  RdpWorkItemManager *v65; // rax
  signed int v66; // eax
  unsigned int v67; // eax
  signed int IsHardwareEncode; // eax
  struct IRdpProgressiveEncoderWorkItem *v69; // rbx
  unsigned int v70; // eax
  int phkResult; // [rsp+28h] [rbp-C9h]
  int phkResulta; // [rsp+28h] [rbp-C9h]
  int phkResultb; // [rsp+28h] [rbp-C9h]
  struct IRdpGFXSourceUpdateContext *v75; // [rsp+78h] [rbp-79h] BYREF
  int v76; // [rsp+80h] [rbp-71h]
  unsigned int v77; // [rsp+84h] [rbp-6Dh]
  int v78; // [rsp+88h] [rbp-69h]
  __int64 v79; // [rsp+90h] [rbp-61h] BYREF
  struct IRdpProgressiveEncoderWorkItem *v80; // [rsp+98h] [rbp-59h] BYREF
  int v81; // [rsp+A0h] [rbp-51h] BYREF
  DWORD Type; // [rsp+A4h] [rbp-4Dh] BYREF
  BYTE Data[4]; // [rsp+A8h] [rbp-49h] BYREF
  int v84; // [rsp+ACh] [rbp-45h] BYREF
  int v85; // [rsp+B0h] [rbp-41h] BYREF
  struct IUnknown *v86; // [rsp+B8h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp-31h] BYREF
  struct _GUID v88; // [rsp+C8h] [rbp-29h] BYREF
  DWORD cbData[2]; // [rsp+D8h] [rbp-19h] BYREF
  _QWORD v90[9]; // [rsp+E0h] [rbp-11h] BYREF

  v80 = 0;
  v8 = a3;
  v86 = 0;
  v90[0] = 0;
  if ( !a3 )
  {
    ProgressiveWorkitem = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
      "WorkItemManagerError_GetProgWorkItemNullPtr",
      (char *)0x524,
      0x80004003,
      phkResult);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 81;
      v14 = "pSurface";
LABEL_6:
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v14);
      goto LABEL_202;
    }
    goto LABEL_202;
  }
  if ( a8 )
  {
    if ( !a4 )
    {
      ProgressiveWorkitem = -2147467261;
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
        "WorkItemManagerError_GetProgWorkItemNullPtr",
        (char *)0x528,
        0x80004003,
        phkResult);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 83;
        v14 = "pPipeManager";
        goto LABEL_6;
      }
      goto LABEL_202;
    }
    *a8 = 0;
    ProgressiveWorkitem = RdpSurface::GetProgressiveWorkitem(a3, a8);
    if ( ProgressiveWorkitem >= 0 )
      goto LABEL_202;
    v78 = 0;
    ProgressiveWorkitem = 16;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      if ( !memcmp_0(a2, &CODEC_GUID_AVC420_CODEC, 0x10u) )
      {
        v15 = (const wchar_t *)L"CODEC_GUID_AVC420_CODEC";
      }
      else if ( !memcmp_0(a2, &CODEC_GUID_AVC420_DRM_CODEC, 0x10u) )
      {
        v15 = L"CODEC_GUID_AVC420_DRM_CODEC";
      }
      else if ( !memcmp_0(a2, &CODEC_GUID_AVC444V1_CODEC, 0x10u) )
      {
        v15 = L"CODEC_GUID_AVC444V1_CODEC";
      }
      else if ( !memcmp_0(a2, &CODEC_GUID_AVC444V2_CODEC, 0x10u) )
      {
        v15 = L"CODEC_GUID_AVC444V2_CODEC";
      }
      else if ( !memcmp_0(a2, &CODEC_GUID_HEVC_CODEC, 0x10u) )
      {
        v15 = L"CODEC_GUID_HEVC_CODEC";
      }
      else
      {
        v15 = L"CODEC_GUID_PROGCACODECEX";
        if ( memcmp_0(a2, &CODEC_GUID_PROGCACODECEX, 0x10u) )
          v15 = L"Invalid GUID";
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
        v16,
        (__int64)v15);
      v8 = a3;
    }
    v88 = *a2;
    if ( (unsigned int)CTSSimpleKeyComPtrArray<_GUID,RdpWorkItemManager::CodecEntry>::Find((char *)a1 + 8, &v88, v90) )
    {
      LOBYTE(ProgressiveWorkitem) = 0;
      v77 = ProgressiveWorkitem;
      if ( memcmp_0(a2, &CODEC_GUID_PROGCACODECEX, 0x10u) )
        goto LABEL_81;
      v24 = v90[0];
      v25 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))(v90[0] + 40LL))(
              *(_QWORD *)(v90[0] + 40LL),
              &IID_IRdpProgressiveCompressorEx,
              &v86);
      ProgressiveWorkitem = v25;
      if ( v25 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
          "WorkItemManagerError_GetProgWorkItemQueryInterfaceProgCmpFail",
          (char *)0x581,
          v25,
          phkResult);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            90,
            (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
            v26,
            (__int64)"QueryInterface failed",
            ProgressiveWorkitem);
        }
        goto LABEL_202;
      }
      LOBYTE(ProgressiveWorkitem) = *(_BYTE *)(v24 + 32);
    }
    else if ( !memcmp_0(a2, &CODEC_GUID_AVC420_CODEC, 0x10u) )
    {
      v78 = 7;
      LOBYTE(ProgressiveWorkitem) = 11;
    }
    else if ( !memcmp_0(a2, &CODEC_GUID_AVC420_DRM_CODEC, 0x10u) )
    {
      v78 = 12;
      LOBYTE(ProgressiveWorkitem) = 17;
    }
    else if ( !memcmp_0(a2, &CODEC_GUID_AVC444V1_CODEC, 0x10u) )
    {
      v78 = 8;
      LOBYTE(ProgressiveWorkitem) = 14;
    }
    else if ( !memcmp_0(a2, &CODEC_GUID_AVC444V2_CODEC, 0x10u) )
    {
      v78 = 9;
      LOBYTE(ProgressiveWorkitem) = 15;
    }
    else
    {
      if ( memcmp_0(a2, &CODEC_GUID_HEVC_CODEC, 0x10u) )
      {
        if ( memcmp_0(a2, &CODEC_GUID_PROGCACODECEX, 0x10u) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids);
          }
          ProgressiveWorkitem = -2147023728;
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
            "WorkItemManagerError_GetProgWorkItemGuidNotFound",
            (char *)0x57A,
            0x80070490,
            phkResult);
          goto LABEL_202;
        }
        v75 = 0;
        GraphicsSourceContext = RdpSurface::GetGraphicsSourceContext(v8, &v75);
        ProgressiveWorkitem = GraphicsSourceContext;
        if ( GraphicsSourceContext >= 0 )
        {
          Instance = ProgressiveCalistaCompEx_CreateInstance(v75);
          ProgressiveWorkitem = Instance;
          if ( Instance >= 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v22 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                87,
                WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
                v22,
                a6);
            }
            v77 = 9;
            v88 = CODEC_GUID_PROGCACODECEX;
            v23 = RdpWorkItemManager::AddCompressorInstance(a1, &v88, 9u, v86);
            ProgressiveWorkitem = v23;
            if ( v23 >= 0 )
            {
              TCntPtr<IRdpVCMgr>::SafeRelease(&v75);
              LOBYTE(ProgressiveWorkitem) = 9;
              goto LABEL_81;
            }
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
              "WorkItemManagerError_GetProgWorkItemCreateProgCaCompressorFail",
              (char *)0x573,
              v23,
              phkResult);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_201;
            }
            v18 = RdpWppGetCurrentThreadActivityIdPrefix();
            v19 = 88;
            v20 = "AddCompressorInstance failed";
          }
          else
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
              "WorkItemManagerError_GetProgWorkItemCreateProgCaCompressorFail",
              (char *)0x569,
              Instance,
              phkResult);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_201;
            }
            v18 = RdpWppGetCurrentThreadActivityIdPrefix();
            v19 = 86;
            v20 = "Failed to create progressive encoderEx!";
          }
        }
        else
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
            "WorkItemManagerError_GetProgWorkItemCreateProgCaCompressorFail",
            (char *)0x55F,
            GraphicsSourceContext,
            phkResult);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_201;
          }
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 85;
          v20 = "Failed to get source context!";
        }
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v19,
          (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
          v18,
          (__int64)v20,
          ProgressiveWorkitem);
        goto LABEL_201;
      }
      v78 = 10;
    }
    v77 = ProgressiveWorkitem;
LABEL_81:
    if ( !memcmp_0(a2, &CODEC_GUID_HEVC_CODEC, 0x10u) )
    {
      v27 = (AvcProgressiveWorkItem *)operator new(0x110u);
      if ( v27 )
      {
        v28 = AvcProgressiveWorkItem::AvcProgressiveWorkItem(v27);
        v29 = v28;
        if ( v28 )
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v28 + 4) + 8LL))(*((_QWORD *)v28 + 4));
          TCntPtr<IRDPCoreVirtualChannel>::operator=(&v80, ((unsigned __int64)v29 + 48) & -(__int64)(v29 != 0));
          v75 = 0;
          v30 = (*(__int64 (__fastcall **)(__int64 *, struct IRdpGFXSourceUpdateContext **))(*a4 + 32))(a4, &v75);
          ProgressiveWorkitem = v30;
          if ( v30 < 0 )
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
              "WorkItemManagerError_GetProgWorkItemGetProtocolFail",
              (char *)0x590,
              v30,
              phkResult);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_90;
            }
            v31 = RdpWppGetCurrentThreadActivityIdPrefix();
            v32 = 92;
            v33 = "GetProtocol failed.";
            goto LABEL_89;
          }
          ProgressiveWorkitem = -2147467261;
          if ( !v75 )
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
              "WorkItemManagerError_GetProgWorkItemGetProtocolFail",
              (char *)0x593,
              0x80004003,
              phkResult);
            if ( !v75 )
            {
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_90;
              }
              v35 = RdpWppGetCurrentThreadActivityIdPrefix();
              v36 = 93;
              v37 = "spProtocol";
              goto LABEL_98;
            }
          }
          v38 = a1;
          if ( !*((_QWORD *)a1 + 7) )
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
              "WorkItemManagerError_GetProgWorkItemGetAvcWorkItemFail",
              (char *)0x596,
              0x80004003,
              phkResult);
            v38 = a1;
          }
          *(_QWORD *)&v88.Data1 = *((_QWORD *)v38 + 7);
          if ( !*(_QWORD *)&v88.Data1 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_90;
            }
            v35 = RdpWppGetCurrentThreadActivityIdPrefix();
            v36 = 94;
            v37 = "m_spExtensionFactory";
LABEL_98:
            WPP_SF_Ds(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v36,
              (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
              v35,
              (__int64)v37);
            goto LABEL_90;
          }
          (*(void (__fastcall **)(__int64 *))(*a4 + 208))(a4);
          (*(void (__fastcall **)(__int64 *))(*a4 + 96))(a4);
          (*(void (__fastcall **)(struct IRdpGFXSourceUpdateContext *))(*(_QWORD *)v75 + 192LL))(v75);
          v39 = a3;
          phkResulta = v78;
          v40 = AvcProgressiveWorkItem::Initialize(v29, *((_QWORD *)a1 + 6), v77, a7);
          ProgressiveWorkitem = v40;
          if ( v40 < 0 )
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
              "WorkItemManagerError_GetProgWorkItemGetAvcWorkItemFail",
              (char *)0x5AB,
              v40,
              phkResulta);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_90;
            }
            v31 = RdpWppGetCurrentThreadActivityIdPrefix();
            v32 = 95;
            v33 = "AvcProgressiveWorkItem::Initialize failed.";
LABEL_89:
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v32,
              (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
              v31,
              (__int64)v33,
              ProgressiveWorkitem);
LABEL_90:
            TCntPtr<IRdpVCMgr>::SafeRelease(&v75);
            v34 = *((_QWORD *)v29 + 4);
LABEL_91:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            goto LABEL_202;
          }
          TCntPtr<IRdpVCMgr>::SafeRelease(&v75);
          v41 = *((_QWORD *)v29 + 4);
          goto LABEL_112;
        }
      }
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
        "WorkItemManagerError_GetProgWorkItemCreateAvcWorkItemFail",
        (char *)0x58A,
        0x80004003,
        phkResult);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v42 = RdpWppGetCurrentThreadActivityIdPrefix();
        v43 = 91;
        v44 = "AvcProgressiveWorkItem";
LABEL_117:
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v43,
          (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
          v42,
          (__int64)v44);
        goto LABEL_118;
      }
      goto LABEL_118;
    }
    if ( memcmp_0(a2, &CODEC_GUID_AVC420_CODEC, 0x10u)
      && memcmp_0(a2, &CODEC_GUID_AVC420_DRM_CODEC, 0x10u)
      && memcmp_0(a2, &CODEC_GUID_AVC444V1_CODEC, 0x10u)
      && memcmp_0(a2, &CODEC_GUID_AVC444V2_CODEC, 0x10u) )
    {
      if ( memcmp_0(a2, &CODEC_GUID_PROGCACODECEX, 0x10u) )
      {
        v39 = a3;
        goto LABEL_195;
      }
      v45 = (CalistaSurfaceProgressiveWorkItem *)operator new(0xC0u);
      if ( v45 )
      {
        v46 = CalistaSurfaceProgressiveWorkItem::CalistaSurfaceProgressiveWorkItem(v45);
        v47 = v46;
        if ( v46 )
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v46 + 4) + 8LL))(*((_QWORD *)v46 + 4));
          TCntPtr<IRDPCoreVirtualChannel>::operator=(&v80, ((unsigned __int64)v47 + 48) & -(__int64)(v47 != 0));
          LOBYTE(v48) = ProgressiveWorkitem;
          v39 = a3;
          v49 = CalistaSurfaceProgressiveWorkItem::Initialize(v47, v86, v48, a7);
          ProgressiveWorkitem = v49;
          if ( v49 < 0 )
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
              "WorkItemManagerError_GetProgWorkItemInitCaProgWorkItemFail",
              (char *)0x62F,
              v49,
              (int)a3);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v50 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                105,
                (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
                v50,
                (__int64)"ProgressiveCodecWorkItem::Initialize failed for ProgressiveCA codec!",
                ProgressiveWorkitem);
            }
            v34 = *((_QWORD *)v47 + 4);
            goto LABEL_91;
          }
          v41 = *((_QWORD *)v47 + 4);
LABEL_112:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
LABEL_195:
          v69 = v80;
          TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)v39 + 96, v80);
          ProgressiveWorkitem = 0;
          v80 = 0;
          *a8 = v69;
          goto LABEL_202;
        }
      }
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
        "WorkItemManagerError_GetProgWorkItemCreateCaProgWorkItemFail",
        (char *)0x623,
        0x80004003,
        phkResult);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v42 = RdpWppGetCurrentThreadActivityIdPrefix();
        v43 = 104;
        v44 = "CalistaSurfaceProgressiveWorkItem";
        goto LABEL_117;
      }
LABEL_118:
      ProgressiveWorkitem = -2147024882;
      goto LABEL_202;
    }
    v85 = 0;
    v76 = *(_DWORD *)(a7 + 36);
    *(_QWORD *)&v88.Data1 = 0;
    v81 = 0;
    v51 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IRdpGFXSourceUpdateContext **))*((_QWORD *)a1 + 6);
    v75 = 0;
    v84 = 0;
    ProgressiveWorkitem = (**v51)(v51, &IID_IRDPCollection, &v75);
    if ( ProgressiveWorkitem < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v52 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          96,
          (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
          v52,
          (__int64)"Failed to QI for the context properties",
          ProgressiveWorkitem);
      }
      goto LABEL_201;
    }
    (*(void (__fastcall **)(struct IRdpGFXSourceUpdateContext *, const wchar_t *, int *))(*(_QWORD *)v75 + 32LL))(
      v75,
      L"WVD::EnableAVCMMHW",
      &v81);
    if ( !memcmp_0(a2, &CODEC_GUID_AVC420_CODEC, 0x10u) && !v81
      || (hKey = 0,
          RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
            0,
            0x20019u,
            &hKey)) )
    {
      v53 = a4;
      goto LABEL_156;
    }
    *(_DWORD *)Data = 0;
    cbData[0] = 4;
    Type = 0;
    if ( RegQueryValueExW(hKey, L"AVCHardwareEncodePreferred", 0, &Type, Data, cbData) || Type != 4 )
    {
      v53 = a4;
    }
    else
    {
      v53 = a4;
      if ( *(_DWORD *)Data == 1 )
        goto LABEL_152;
      if ( *(_DWORD *)Data != 2 )
      {
        if ( *(_DWORD *)Data == 3 )
          (*(__int64 (__fastcall **)(__int64 *))(*a4 + 176))(a4);
        goto LABEL_154;
      }
      if ( (*(unsigned int (__fastcall **)(__int64 *))(*a4 + 176))(a4) )
LABEL_152:
        v76 = 1;
    }
LABEL_154:
    RegCloseKey(hKey);
LABEL_156:
    v54 = (AvcProgressiveWorkItem *)operator new(0x110u);
    if ( !v54 || (v55 = AvcProgressiveWorkItem::AvcProgressiveWorkItem(v54), *(_QWORD *)cbData = v55, (v56 = v55) == 0) )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
        "WorkItemManagerError_GetProgWorkItemCreateAvcWorkItemFail",
        (char *)0x5F7,
        0x80004003,
        phkResult);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v70 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          97,
          (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
          v70,
          (__int64)"AvcProgressiveWorkItem");
      }
      ProgressiveWorkitem = -2147024882;
      goto LABEL_201;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v55 + 4) + 8LL))(*((_QWORD *)v55 + 4));
    TCntPtr<IRDPCoreVirtualChannel>::operator=(&v80, ((unsigned __int64)v56 + 48) & -(__int64)(v56 != 0));
    v57 = *v53;
    v79 = 0;
    v58 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v57 + 32))(v53, &v79);
    ProgressiveWorkitem = v58;
    if ( v58 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
        "WorkItemManagerError_GetProgWorkItemGetProtocolFail",
        (char *)0x5FD,
        v58,
        phkResult);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_164;
      }
      v59 = RdpWppGetCurrentThreadActivityIdPrefix();
      v60 = 98;
      v61 = "GetProtocol failed.";
      goto LABEL_163;
    }
    ProgressiveWorkitem = -2147467261;
    if ( v79
      || (RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
            "WorkItemManagerError_GetProgWorkItemGetProtocolFail",
            (char *)0x600,
            0x80004003,
            phkResult),
          v79) )
    {
      v65 = a1;
      if ( !*((_QWORD *)a1 + 7) )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
          "WorkItemManagerError_GetProgWorkItemGetAvcWorkItemFail",
          (char *)0x603,
          0x80004003,
          phkResult);
        v65 = a1;
      }
      hKey = (HKEY)*((_QWORD *)v65 + 7);
      if ( hKey )
      {
        (*(void (__fastcall **)(__int64 *))(*a4 + 208))(a4);
        (*(void (__fastcall **)(__int64 *))(*a4 + 96))(a4);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 192LL))(v79);
        v39 = a3;
        v56 = *(AvcProgressiveWorkItem **)cbData;
        phkResultb = v78;
        v66 = AvcProgressiveWorkItem::Initialize(*(_QWORD *)cbData, *((_QWORD *)a1 + 6), v77, a7);
        ProgressiveWorkitem = v66;
        if ( v66 >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v67 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids, v67);
          }
          IsHardwareEncode = AvcProgressiveWorkItem::IsHardwareEncode(
                               (AvcProgressiveWorkItem *)((char *)v56 + 48),
                               &v85,
                               (unsigned __int16 **)&v88,
                               &v84);
          ProgressiveWorkitem = IsHardwareEncode;
          if ( IsHardwareEncode >= 0 )
          {
            (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(*a4 + 200))(
              a4,
              (unsigned int)v85,
              *(_QWORD *)&v88.Data1,
              (unsigned int)v84);
            TCntPtr<IRdpVCMgr>::SafeRelease(&v79);
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v56 + 4) + 16LL))(*((_QWORD *)v56 + 4));
            TCntPtr<IRdpVCMgr>::SafeRelease(&v75);
            goto LABEL_195;
          }
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
            "WorkItemManagerError_GetProgWorkItemGetAvcWorkItemFail",
            (char *)0x61A,
            IsHardwareEncode,
            phkResultb);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_164;
          }
          v59 = RdpWppGetCurrentThreadActivityIdPrefix();
          v60 = 103;
          v61 = "AvcProgressiveWorkItem::IsHardwareEncode failed";
        }
        else
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
            "WorkItemManagerError_GetProgWorkItemGetAvcWorkItemFail",
            (char *)0x614,
            v66,
            phkResultb);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_164;
          }
          v59 = RdpWppGetCurrentThreadActivityIdPrefix();
          v60 = 101;
          v61 = "AvcProgressiveWorkItem::Initialize failed.";
        }
LABEL_163:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v60,
          (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
          v59,
          (__int64)v61,
          ProgressiveWorkitem);
LABEL_164:
        TCntPtr<IRdpVCMgr>::SafeRelease(&v79);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v56 + 4) + 16LL))(*((_QWORD *)v56 + 4));
LABEL_201:
        TCntPtr<IRdpVCMgr>::SafeRelease(&v75);
        goto LABEL_202;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_164;
      }
      v62 = RdpWppGetCurrentThreadActivityIdPrefix();
      v63 = 100;
      v64 = "m_spExtensionFactory";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_164;
      }
      v62 = RdpWppGetCurrentThreadActivityIdPrefix();
      v63 = 99;
      v64 = "spProtocol";
    }
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v63,
      (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
      v62,
      (__int64)v64);
    goto LABEL_164;
  }
  ProgressiveWorkitem = -2147467261;
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpWorkItemManager",
    "WorkItemManagerError_GetProgWorkItemNullPtr",
    (char *)0x526,
    0x80004003,
    phkResult);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 82;
    v14 = "ppWorkItem";
    goto LABEL_6;
  }
LABEL_202:
  TCntPtr<CImageClassifier>::SafeRelease(v90);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v86);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v80);
  return (unsigned int)ProgressiveWorkitem;
}

```

## disassembly

```asm
0x1800b3810  mov     rax, rsp
0x1800b3813  mov     [rax+20h], r9
0x1800b3817  mov     [rax+18h], r8
0x1800b381b  mov     [rax+8], rcx
0x1800b381f  push    rbp
0x1800b3820  push    rbx
0x1800b3821  push    rsi
0x1800b3822  push    rdi
0x1800b3823  push    r12
0x1800b3825  push    r13
0x1800b3827  push    r15
0x1800b3829  lea     rbp, [rax-3Fh]
0x1800b382d  sub     rsp, 0F0h
0x1800b3834  movaps  xmmword ptr [rax-48h], xmm6
0x1800b3838  mov     rax, r9
0x1800b383b  mov     [rbp+37h+var_90], 0
0x1800b3843  mov     rbx, r8
0x1800b3846  mov     [rbp+37h+var_70], 0
0x1800b384e  mov     r13, rdx
0x1800b3851  mov     [rbp+37h+var_48], 0
0x1800b3859  mov     rdi, rcx
0x1800b385c  test    r8, r8
0x1800b385f  jnz     short loc_1800B38E0
0x1800b3861  mov     esi, 80004003h
0x1800b3866  lea     rdx, aWorkitemmanage_4; "WorkItemManagerError_GetProgWorkItemNul"...
0x1800b386d  mov     r9d, esi; unsigned int
0x1800b3870  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x1800b3877  mov     r8d, 524h; char *
0x1800b387d  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b3882  mov     rax, cs:WPP_GLOBAL_Control
0x1800b3889  lea     r15, WPP_GLOBAL_Control
0x1800b3890  cmp     rax, r15
0x1800b3893  jz      loc_1800B4A5A
0x1800b3899  test    byte ptr [rax+1Ch], 8
0x1800b389d  jz      loc_1800B4A5A
0x1800b38a3  cmp     byte ptr [rax+19h], 2
0x1800b38a7  jb      loc_1800B4A5A
0x1800b38ad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b38b2  lea     edx, [rbx+51h]
0x1800b38b5  lea     rcx, aPsurface; "pSurface"
0x1800b38bc  mov     [rsp+120h+phkResult], rcx
0x1800b38c1  lea     r8, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids
0x1800b38c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b38cf  mov     r9d, eax
0x1800b38d2  mov     rcx, [rcx+10h]
0x1800b38d6  call    WPP_SF_Ds
0x1800b38db  jmp     loc_1800B4A5A
0x1800b38e0  mov     rcx, [rbp+37h+arg_38]
0x1800b38e4  test    rcx, rcx
0x1800b38e7  jnz     short loc_1800B394B
0x1800b38e9  mov     esi, 80004003h
0x1800b38ee  lea     rdx, aWorkitemmanage_4; "WorkItemManagerError_GetProgWorkItemNul"...
0x1800b38f5  mov     r9d, esi; unsigned int
0x1800b38f8  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x1800b38ff  mov     r8d, 526h; char *
0x1800b3905  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b390a  mov     rax, cs:WPP_GLOBAL_Control
0x1800b3911  lea     r15, WPP_GLOBAL_Control
0x1800b3918  cmp     rax, r15
0x1800b391b  jz      loc_1800B4A5A
0x1800b3921  test    byte ptr [rax+1Ch], 8
0x1800b3925  jz      loc_1800B4A5A
0x1800b392b  cmp     byte ptr [rax+19h], 2
0x1800b392f  jb      loc_1800B4A5A
0x1800b3935  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b393a  mov     edx, 52h ; 'R'
0x1800b393f  lea     rcx, aPpworkitem; "ppWorkItem"
0x1800b3946  jmp     loc_1800B38BC
0x1800b394b  test    rax, rax
0x1800b394e  jnz     short loc_1800B39B2
0x1800b3950  mov     esi, 80004003h
0x1800b3955  lea     rdx, aWorkitemmanage_4; "WorkItemManagerError_GetProgWorkItemNul"...
0x1800b395c  mov     r9d, esi; unsigned int
0x1800b395f  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x1800b3966  mov     r8d, 528h; char *
0x1800b396c  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b3971  mov     rax, cs:WPP_GLOBAL_Control
0x1800b3978  lea     r15, WPP_GLOBAL_Control
0x1800b397f  cmp     rax, r15
0x1800b3982  jz      loc_1800B4A5A
0x1800b3988  test    byte ptr [rax+1Ch], 8
0x1800b398c  jz      loc_1800B4A5A
0x1800b3992  cmp     byte ptr [rax+19h], 2
0x1800b3996  jb      loc_1800B4A5A
0x1800b399c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b39a1  mov     edx, 53h ; 'S'
0x1800b39a6  lea     rcx, aPpipemanager; "pPipeManager"
0x1800b39ad  jmp     loc_1800B38BC
0x1800b39b2  mov     qword ptr [rcx], 0
0x1800b39b9  mov     rdx, rcx; struct IRdpProgressiveEncoderWorkItem **
0x1800b39bc  mov     rcx, rbx; this
0x1800b39bf  call    ?GetProgressiveWorkitem@RdpSurface@@QEAAJPEAPEAVIRdpProgressiveEncoderWorkItem@@@Z; RdpSurface::GetProgressiveWorkitem(IRdpProgressiveEncoderWorkItem * *)
0x1800b39c4  mov     esi, eax
0x1800b39c6  test    eax, eax
0x1800b39c8  jns     loc_1800B4A5A
0x1800b39ce  mov     [rbp+37h+var_A0], 0
0x1800b39d5  mov     rax, cs:WPP_GLOBAL_Control
0x1800b39dc  lea     r15, WPP_GLOBAL_Control
0x1800b39e3  lea     r12, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids
0x1800b39ea  mov     esi, 10h
0x1800b39ef  cmp     rax, r15
0x1800b39f2  jz      loc_1800B3AFF
0x1800b39f8  test    dword ptr [rax+1Ch], 100h
0x1800b39ff  jz      loc_1800B3AFF
0x1800b3a05  cmp     byte ptr [rax+19h], 3
0x1800b3a09  jb      loc_1800B3AFF
0x1800b3a0f  mov     r8d, esi; Size
0x1800b3a12  lea     rdx, CODEC_GUID_AVC420_CODEC; Buf2
0x1800b3a19  mov     rcx, r13; Buf1
0x1800b3a1c  call    memcmp_0
0x1800b3a21  test    eax, eax
0x1800b3a23  jnz     short loc_1800B3A31
0x1800b3a25  lea     rbx, aCodecGuidAvc42_0; "CODEC_GUID_AVC420_CODEC"
0x1800b3a2c  jmp     loc_1800B3AD6
0x1800b3a31  mov     r8, rsi; Size
0x1800b3a34  lea     rdx, CODEC_GUID_AVC420_DRM_CODEC; Buf2
0x1800b3a3b  mov     rcx, r13; Buf1
0x1800b3a3e  call    memcmp_0
0x1800b3a43  test    eax, eax
0x1800b3a45  jnz     short loc_1800B3A53
0x1800b3a47  lea     rbx, aCodecGuidAvc42; "CODEC_GUID_AVC420_DRM_CODEC"
0x1800b3a4e  jmp     loc_1800B3AD6
0x1800b3a53  mov     r8, rsi; Size
0x1800b3a56  lea     rdx, CODEC_GUID_AVC444V1_CODEC; Buf2
0x1800b3a5d  mov     rcx, r13; Buf1
0x1800b3a60  call    memcmp_0
0x1800b3a65  test    eax, eax
0x1800b3a67  jnz     short loc_1800B3A72
0x1800b3a69  lea     rbx, aCodecGuidAvc44; "CODEC_GUID_AVC444V1_CODEC"
0x1800b3a70  jmp     short loc_1800B3AD6
0x1800b3a72  mov     r8, rsi; Size
0x1800b3a75  lea     rdx, CODEC_GUID_AVC444V2_CODEC; Buf2
0x1800b3a7c  mov     rcx, r13; Buf1
0x1800b3a7f  call    memcmp_0
0x1800b3a84  test    eax, eax
0x1800b3a86  jnz     short loc_1800B3A91
0x1800b3a88  lea     rbx, aCodecGuidAvc44_0; "CODEC_GUID_AVC444V2_CODEC"
0x1800b3a8f  jmp     short loc_1800B3AD6
0x1800b3a91  mov     r8, rsi; Size
0x1800b3a94  lea     rdx, CODEC_GUID_HEVC_CODEC; Buf2
0x1800b3a9b  mov     rcx, r13; Buf1
0x1800b3a9e  call    memcmp_0
0x1800b3aa3  test    eax, eax
0x1800b3aa5  jnz     short loc_1800B3AB0
0x1800b3aa7  lea     rbx, aCodecGuidHevcC; "CODEC_GUID_HEVC_CODEC"
0x1800b3aae  jmp     short loc_1800B3AD6
0x1800b3ab0  mov     r8, rsi; Size
0x1800b3ab3  lea     rdx, CODEC_GUID_PROGCACODECEX; Buf2
0x1800b3aba  mov     rcx, r13; Buf1
0x1800b3abd  call    memcmp_0
0x1800b3ac2  test    eax, eax
0x1800b3ac4  lea     rbx, aCodecGuidProgc; "CODEC_GUID_PROGCACODECEX"
0x1800b3acb  lea     rcx, aInvalidGuid; "Invalid GUID"
0x1800b3ad2  cmovnz  rbx, rcx
0x1800b3ad6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b3adb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3ae2  mov     edx, 54h ; 'T'
0x1800b3ae7  mov     r9d, eax
0x1800b3aea  mov     [rsp+120h+phkResult], rbx; int
0x1800b3aef  mov     r8, r12
0x1800b3af2  mov     rcx, [rcx+10h]
0x1800b3af6  call    WPP_SF_DS
0x1800b3afb  mov     rbx, qword ptr [rbp+37h+arg_10]
0x1800b3aff  movups  xmm0, xmmword ptr [r13+0]
0x1800b3b04  lea     rcx, [rdi+8]
0x1800b3b08  lea     r8, [rbp+37h+var_48]
0x1800b3b0c  lea     rdx, [rbp+37h+var_60]
0x1800b3b10  movdqu  xmmword ptr [rbp+37h+var_60.Data1], xmm0
0x1800b3b15  call    ?Find@?$CTSSimpleKeyComPtrArray@U_GUID@@UCodecEntry@RdpWorkItemManager@@@@QEAAHU_GUID@@PEAPEAUCodecEntry@RdpWorkItemManager@@@Z; CTSSimpleKeyComPtrArray<_GUID,RdpWorkItemManager::CodecEntry>::Find(_GUID,RdpWorkItemManager::CodecEntry * *)
0x1800b3b1a  mov     rdi, [rbp+37h+arg_28]
0x1800b3b1e  mov     rcx, r13; Buf1
0x1800b3b21  test    eax, eax
0x1800b3b23  jnz     loc_1800B3E0C
0x1800b3b29  mov     r8, rsi; Size
0x1800b3b2c  lea     rdx, CODEC_GUID_AVC420_CODEC; Buf2
0x1800b3b33  call    memcmp_0
0x1800b3b38  test    eax, eax
0x1800b3b3a  jnz     short loc_1800B3B4B
0x1800b3b3c  mov     [rbp+37h+var_A0], 7
0x1800b3b43  mov     sil, 0Bh
0x1800b3b46  jmp     loc_1800B3EC9
0x1800b3b4b  mov     r8, rsi; Size
0x1800b3b4e  lea     rdx, CODEC_GUID_AVC420_DRM_CODEC; Buf2
0x1800b3b55  mov     rcx, r13; Buf1
0x1800b3b58  call    memcmp_0
0x1800b3b5d  test    eax, eax
0x1800b3b5f  jnz     short loc_1800B3B70
0x1800b3b61  mov     [rbp+37h+var_A0], 0Ch
0x1800b3b68  mov     sil, 11h
0x1800b3b6b  jmp     loc_1800B3EC9
0x1800b3b70  mov     r8, rsi; Size
0x1800b3b73  lea     rdx, CODEC_GUID_AVC444V1_CODEC; Buf2
0x1800b3b7a  mov     rcx, r13; Buf1
0x1800b3b7d  call    memcmp_0
0x1800b3b82  test    eax, eax
0x1800b3b84  jnz     short loc_1800B3B95
0x1800b3b86  mov     [rbp+37h+var_A0], 8
0x1800b3b8d  mov     sil, 0Eh
0x1800b3b90  jmp     loc_1800B3EC9
0x1800b3b95  mov     r8, rsi; Size
0x1800b3b98  lea     rdx, CODEC_GUID_AVC444V2_CODEC; Buf2
0x1800b3b9f  mov     rcx, r13; Buf1
0x1800b3ba2  call    memcmp_0
0x1800b3ba7  test    eax, eax
0x1800b3ba9  jnz     short loc_1800B3BBA
0x1800b3bab  mov     [rbp+37h+var_A0], 9
0x1800b3bb2  mov     sil, 0Fh
0x1800b3bb5  jmp     loc_1800B3EC9
0x1800b3bba  mov     r8, rsi; Size
0x1800b3bbd  lea     rdx, CODEC_GUID_HEVC_CODEC; Buf2
0x1800b3bc4  mov     rcx, r13; Buf1
0x1800b3bc7  call    memcmp_0
0x1800b3bcc  test    eax, eax
0x1800b3bce  jnz     short loc_1800B3BDC
0x1800b3bd0  mov     [rbp+37h+var_A0], 0Ah
0x1800b3bd7  jmp     loc_1800B3EC9
0x1800b3bdc  mov     r8, rsi; Size
0x1800b3bdf  lea     rdx, CODEC_GUID_PROGCACODECEX; Buf2
0x1800b3be6  mov     rcx, r13; Buf1
0x1800b3be9  call    memcmp_0
0x1800b3bee  test    eax, eax
0x1800b3bf0  jnz     loc_1800B3DBB
0x1800b3bf6  lea     rdx, [rbp+37h+var_B0]; struct IRdpGFXSourceUpdateContext **
0x1800b3bfa  mov     [rbp+37h+var_B0], 0
0x1800b3c02  mov     rcx, rbx; this
0x1800b3c05  call    ?GetGraphicsSourceContext@RdpSurface@@QEAAJPEAPEAUIRdpGFXSourceUpdateContext@@@Z; RdpSurface::GetGraphicsSourceContext(IRdpGFXSourceUpdateContext * *)
0x1800b3c0a  mov     esi, eax
0x1800b3c0c  test    eax, eax
0x1800b3c0e  jns     short loc_1800B3C82
0x1800b3c10  mov     r9d, eax; unsigned int
0x1800b3c13  lea     rdx, aWorkitemmanage_5; "WorkItemManagerError_GetProgWorkItemCre"...
0x1800b3c1a  mov     r8d, 55Fh; char *
0x1800b3c20  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x1800b3c27  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b3c2c  mov     rax, cs:WPP_GLOBAL_Control
0x1800b3c33  cmp     rax, r15
0x1800b3c36  jz      short loc_1800B3C74
0x1800b3c38  test    byte ptr [rax+1Ch], 8
0x1800b3c3c  jz      short loc_1800B3C74
0x1800b3c3e  cmp     byte ptr [rax+19h], 2
0x1800b3c42  jb      short loc_1800B3C74
0x1800b3c44  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b3c49  mov     edx, 55h ; 'U'
0x1800b3c4e  lea     rcx, aFailedToGetSou; "Failed to get source context!"
0x1800b3c55  mov     dword ptr [rsp+120h+lpcbData], esi
0x1800b3c59  mov     r9d, eax
0x1800b3c5c  mov     [rsp+120h+phkResult], rcx
0x1800b3c61  mov     r8, r12
0x1800b3c64  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3c6b  mov     rcx, [rcx+10h]
0x1800b3c6f  call    WPP_SF_DsD
0x1800b3c74  lea     rcx, [rbp+37h+var_B0]
0x1800b3c78  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800b3c7d  jmp     loc_1800B4A5A
0x1800b3c82  mov     rdx, [rbp+37h+arg_30]
0x1800b3c86  lea     r8, [rbp+37h+var_70]
0x1800b3c8a  mov     rcx, [rbp+37h+var_B0]; struct IRdpGFXSourceUpdateContext *
0x1800b3c8e  mov     edx, [rdx+8]
0x1800b3c91  call    ?ProgressiveCalistaCompEx_CreateInstance@@YAJPEAUIRdpGFXSourceUpdateContext@@IAEAV?$TCntPtr@UIRdpProgressiveCompressorEx@@@@@Z; ProgressiveCalistaCompEx_CreateInstance(IRdpGFXSourceUpdateContext *,uint,TCntPtr<IRdpProgressiveCompressorEx> &)
0x1800b3c96  mov     esi, eax
0x1800b3c98  test    eax, eax
0x1800b3c9a  jns     short loc_1800B3CE6
0x1800b3c9c  mov     r9d, eax; unsigned int
0x1800b3c9f  lea     rdx, aWorkitemmanage_5; "WorkItemManagerError_GetProgWorkItemCre"...
0x1800b3ca6  mov     r8d, 569h; char *
0x1800b3cac  lea     rcx, aIidIrdpworkite_0; "IID_IRdpWorkItemManager"
0x1800b3cb3  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b3cb8  mov     rax, cs:WPP_GLOBAL_Control
0x1800b3cbf  cmp     rax, r15
0x1800b3cc2  jz      short loc_1800B3C74
0x1800b3cc4  test    byte ptr [rax+1Ch], 8
0x1800b3cc8  jz      short loc_1800B3C74
0x1800b3cca  cmp     byte ptr [rax+19h], 2
0x1800b3cce  jb      short loc_1800B3C74
0x1800b3cd0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b3cd5  mov     edx, 56h ; 'V'
0x1800b3cda  lea     rcx, aFailedToCreate_49; "Failed to create progressive encoderEx!"
0x1800b3ce1  jmp     loc_1800B3C55
0x1800b3ce6  mov     rax, cs:WPP_GLOBAL_Control
0x1800b3ced  cmp     rax, r15
0x1800b3cf0  jz      short loc_1800B3D29
0x1800b3cf2  test    dword ptr [rax+1Ch], 100h
0x1800b3cf9  jz      short loc_1800B3D29
0x1800b3cfb  cmp     byte ptr [rax+19h], 4
0x1800b3cff  jb      short loc_1800B3D29
0x1800b3d01  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b3d06  movzx   ecx, dil
0x1800b3d0a  mov     edx, 57h ; 'W'
0x1800b3d0f  mov     dword ptr [rsp+120h+phkResult], ecx; int
0x1800b3d13  mov     r9d, eax
0x1800b3d16  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3d1d  mov     r8, r12
0x1800b3d20  mov     rcx, [rcx+10h]
0x1800b3d24  call    WPP_SF_Dd
0x1800b3d29  movups  xmm0, xmmword ptr cs:CODEC_GUID_PROGCACODECEX.Data1
0x1800b3d30  mov     r9, [rbp+37h+var_70]; struct IUnknown *
0x1800b3d34  lea     rdx, [rbp+37h+var_60]; struct _GUID
0x1800b3d38  mov     rcx, [rbp+37h+arg_0]; this
0x1800b3d3c  mov     ebx, 9
0x1800b3d41  mov     r8b, bl; unsigned __int8
  ... truncated ...
```
