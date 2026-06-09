# CRdpUT::ProcessGraphicsUpdate(_RDPGFX_PROVIDER_UPDATE_HDR *)

- ea: `0x18001dd38`
- end: `0x18001e962`
- name: `?ProcessGraphicsUpdate@CRdpUT@@IEAAJPEAU_RDPGFX_PROVIDER_UPDATE_HDR@@@Z`
- size: `3114`
- prototype: `__int64 __fastcall(CRdpUT *__hidden this, struct _RDPGFX_PROVIDER_UPDATE_HDR *)`
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002653c`

## callees

- `0x18000cdac`
- `0x18000ce04`
- `0x18001dd38`
- `0x18001e968`
- `0x18001e9e0`
- `0x18001edf0`
- `0x18001f884`
- `0x180020d28`
- `0x18002aafc`
- `0x18002b14c`
- `0x180033f78`
- `0x18004b188`
- `0x180075854`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x18007a404`
- `0x180089628`
- `0x180089d2c`
- `0x1800affe4`
- `0x1800b0a34`
- `0x1800ca040`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x18001ddc6`: `UpdateTrackerError_ProcessGraphicsUpdateGetSurfaceDataFail`
- `0x18001de39`: `UpdateTrackerError_ProcessGraphicsUpdateGetSurfaceDataFail`
- `0x18001deca`: `UpdateTrackerError_ProcessGraphicsUpdateGetSurfaceDataFail`
- `0x18001df44`: `UpdateTrackerError_ProcessGraphicsUpdateGetSurfaceDataFail`
- `0x18001ddd3`: `IID_IRdpUpdateTracker`
- `0x18001de43`: `IID_IRdpUpdateTracker`
- `0x18001ded4`: `IID_IRdpUpdateTracker`
- `0x18001df51`: `IID_IRdpUpdateTracker`
- `0x18001e03d`: `IID_IRdpUpdateTracker`
- `0x18001e0db`: `IID_IRdpUpdateTracker`
- `0x18001e154`: `IID_IRdpUpdateTracker`
- `0x18001e32d`: `IID_IRdpUpdateTracker`
- `0x18001e455`: `IID_IRdpUpdateTracker`
- `0x18001e58f`: `IID_IRdpUpdateTracker`
- `0x18001de8a`: `pUpdateBA`
- `0x18001e582`: `UpdateTrackerError_ProcessGraphicsUpdateBALogicFail`
- `0x18001e147`: `UpdateTrackerError_ProcessGraphicsUpdatePipePrimitiveCreateInstanceFail`
- `0x18001e320`: `UpdateTrackerError_ProcessGraphicsUpdatePipePrimitiveCreateInstanceFail`
- `0x18001e5b8`: `Failed to add rect to pUpdateBA`
- `0x18001e448`: `UpdateTrackerError_ProcessGraphicsSetWindowContextFail`
- `0x18001e0ce`: `UpdateTrackerError_ProcessGraphicsScreenCaptureProtectFail`
- `0x18001e115`: `Failed to process screen capture protection update`
- `0x18001e030`: `UpdateTrackerError_ProcessGraphicsWatermarkingFail`
- `0x18001e077`: `Failed to process watermarking update`
- `0x18001e887`: `Failed to align rects in pUpdateBA`

## pseudocode

```c
__int64 __fastcall CRdpUT::ProcessGraphicsUpdate(CRdpUT *this, struct _RDPGFX_PROVIDER_UPDATE_HDR *a2)
{
  CTSCriticalSection *v2; // rsi
  __int64 v4; // rdi
  __int64 v6; // rcx
  int v7; // esi
  signed int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v12; // edx
  const char *v13; // rcx
  signed int PrimitiveList; // eax
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  signed int v27; // eax
  unsigned int v28; // eax
  int v29; // edx
  const char *v30; // rcx
  signed int v31; // eax
  __int128 v32; // xmm0
  signed int v33; // eax
  struct IRdpCacheManContext *v34; // rbx
  struct IRdpBoundsAccumulator *v35; // rbx
  unsigned int v36; // eax
  struct IRdpCacheManContext **v37; // rcx
  CRdpUT *v38; // rcx
  unsigned int v39; // edx
  int v40; // ecx
  int v41; // r8d
  unsigned int v42; // r10d
  int v43; // r9d
  __int64 v44; // rax
  void (__fastcall *v45)(struct IRdpBoundsAccumulator *, __int64 *, struct IRdpCacheManContext **); // rax
  __int64 v46; // rcx
  unsigned int v47; // eax
  signed int v48; // eax
  struct PipePrimitive *v49; // rbx
  unsigned int v50; // eax
  CRdpUT *v51; // rcx
  signed int v52; // eax
  bool v53; // zf
  __int64 v54; // rcx
  unsigned int i; // eax
  signed int v56; // eax
  unsigned int v57; // eax
  __int64 v58; // r15
  PVOID *v59; // rdx
  unsigned int v60; // eax
  __int64 v61; // rax
  __int64 v62; // rcx
  struct PipePrimitive *TimeHNS; // rax
  unsigned int v64; // eax
  __int64 v65; // rax
  unsigned int v66; // eax
  unsigned int v67; // r14d
  __int64 v68; // rax
  RdpSurface *v69; // rcx
  int v71; // [rsp+20h] [rbp-49h]
  struct IRdpBoundsAccumulator *v72; // [rsp+30h] [rbp-39h]
  RdpSurface *v73; // [rsp+38h] [rbp-31h] BYREF
  __int128 v74; // [rsp+40h] [rbp-29h] BYREF
  char *v75; // [rsp+50h] [rbp-19h]
  __int64 v76; // [rsp+58h] [rbp-11h] BYREF
  int v77; // [rsp+60h] [rbp-9h]
  int v78; // [rsp+64h] [rbp-5h]
  __int64 v79; // [rsp+68h] [rbp-1h]
  struct PipePrimitiveList *v80; // [rsp+70h] [rbp+7h] BYREF
  _DWORD v81[18]; // [rsp+78h] [rbp+Fh] BYREF
  struct IRdpCacheManContext *v82; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int v83; // [rsp+E0h] [rbp+77h] BYREF
  struct PipePrimitive *v84; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = (CRdpUT *)((char *)this + 152);
  v73 = 0;
  v4 = 0;
  v80 = 0;
  v83 = 0;
  CTSCriticalSection::Lock((CRdpUT *)((char *)this + 152));
  v6 = *((_QWORD *)this + 14);
  if ( v6 )
  {
    v4 = *((_QWORD *)this + 14);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  if ( v2 )
    CTSCriticalSection::UnLock(v2);
  if ( !v4 )
  {
    v7 = 0;
    goto LABEL_151;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, RdpSurface **))(*(_QWORD *)v4 + 32LL))(v4, *((_QWORD *)a2 + 1), &v73);
  v7 = v8;
  if ( v8 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
      "UpdateTrackerError_ProcessGraphicsUpdateGetSurfaceDataFail",
      (char *)0x71F,
      v8,
      v71);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, *((_QWORD *)a2 + 1));
    }
    goto LABEL_151;
  }
  v72 = (struct IRdpBoundsAccumulator *)*((_QWORD *)v73 + 33);
  if ( !v72 )
  {
    v7 = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
      "UpdateTrackerError_ProcessGraphicsUpdateGetSurfaceDataFail",
      (char *)0x727,
      0x80004003,
      v71);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_151;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 97;
    v13 = "pUpdateBA";
    goto LABEL_17;
  }
  v79 = *((_QWORD *)v73 + 34);
  if ( !v79 )
  {
    v7 = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
      "UpdateTrackerError_ProcessGraphicsUpdateGetSurfaceDataFail",
      (char *)0x72B,
      0x80004003,
      v71);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_151;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 98;
    v13 = "pPrimitiveBA";
LABEL_17:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      (unsigned int)&WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v13);
    goto LABEL_151;
  }
  *(_QWORD *)&v74 = *((_QWORD *)v73 + 25);
  PrimitiveList = RdpSurface::GetPrimitiveList(v73, &v80);
  v7 = PrimitiveList;
  if ( PrimitiveList < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
      "UpdateTrackerError_ProcessGraphicsUpdateGetSurfaceDataFail",
      (char *)0x736,
      PrimitiveList,
      v71);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_151;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 100;
    v17 = "Failed to get primitive list";
    goto LABEL_150;
  }
  v18 = *((_DWORD *)a2 + 1);
  v75 = (char *)v80 + 48;
  v19 = v18 - 1;
  if ( !v19 )
    goto LABEL_81;
  v20 = v19 - 16;
  if ( !v20 )
  {
    v52 = RdpSurface::SetWindowContext(v73, *((_QWORD *)a2 + 134));
    v7 = v52;
    if ( v52 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
        "UpdateTrackerError_ProcessGraphicsSetWindowContextFail",
        (char *)0x83C,
        v52,
        v71);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_151;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 108;
      v17 = "Failed to set surface window context";
LABEL_150:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        (unsigned int)&WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
        v15,
        (__int64)v17,
        v7);
      goto LABEL_151;
    }
    goto LABEL_138;
  }
  v21 = v20 - 1;
  if ( !v21 )
    goto LABEL_81;
  v22 = v21 - 1;
  if ( v22 )
  {
    v23 = v22 - 1;
    if ( v23 )
    {
      v24 = v23 - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 6;
          if ( v26 )
          {
            if ( v26 != 1 )
              goto LABEL_138;
            v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 14) + 64LL))(
                    *((_QWORD *)this + 14),
                    *((_QWORD *)a2 + 1),
                    *((unsigned int *)a2 + 268));
            v7 = v27;
            if ( v27 >= 0 )
              goto LABEL_138;
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
              "UpdateTrackerError_ProcessGraphicsWatermarkingFail",
              (char *)0x856,
              v27,
              v71);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_138;
            }
            v28 = RdpWppGetCurrentThreadActivityIdPrefix();
            v29 = 110;
            v30 = "Failed to process watermarking update";
          }
          else
          {
            v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 14) + 56LL))(
                    *((_QWORD *)this + 14),
                    *((_QWORD *)a2 + 1),
                    *((unsigned int *)a2 + 268));
            v7 = v31;
            if ( v31 >= 0 )
              goto LABEL_138;
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
              "UpdateTrackerError_ProcessGraphicsScreenCaptureProtectFail",
              (char *)0x849,
              v31,
              v71);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_138;
            }
            v28 = RdpWppGetCurrentThreadActivityIdPrefix();
            v29 = 109;
            v30 = "Failed to process screen capture protection update";
          }
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v29,
            (unsigned int)&WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
            v28,
            (__int64)v30,
            v7);
LABEL_138:
          v35 = v72;
LABEL_139:
          if ( !(*(unsigned int (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 10) + 184LL))(
                  *((_QWORD *)this + 10),
                  &v83) )
            goto LABEL_151;
          v67 = *((_DWORD *)v73 + 18);
          v68 = *(_QWORD *)v35;
          LODWORD(v82) = *((_DWORD *)v73 + 19);
          v7 = (*(__int64 (__fastcall **)(struct IRdpBoundsAccumulator *, _QWORD, _QWORD, _QWORD))(v68 + 160))(
                 v35,
                 v67,
                 (unsigned int)v82,
                 v83);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v79 + 160LL))(
                   v79,
                   v67,
                   (unsigned int)v82,
                   v83);
            if ( v7 >= 0
              || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_151;
            }
            v15 = RdpWppGetCurrentThreadActivityIdPrefix();
            v16 = 112;
            v17 = "Failed to align rects in pPrimitiveBA";
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_151;
            }
            v15 = RdpWppGetCurrentThreadActivityIdPrefix();
            v16 = 111;
            v17 = "Failed to align rects in pUpdateBA";
          }
          goto LABEL_150;
        }
LABEL_81:
        v53 = *((_QWORD *)this + 250) == 0;
        LODWORD(v84) = *((_DWORD *)a2 + 4);
        if ( v53 )
          *((_QWORD *)this + 250) = CRdpUT::GetTimeHNS(this);
        v54 = *((_QWORD *)this + 10);
        v76 = 0;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 80LL))(v54, &v76);
        if ( v76 )
          (*(void (__fastcall **)(__int64, struct _RDPGFX_PROVIDER_UPDATE_HDR *, RdpSurface *))(*(_QWORD *)v76 + 56LL))(
            v76,
            a2,
            v73);
        v82 = 0;
        if ( (int)RdpSurface::GetVideoDetector(v73, &v82) >= 0 )
          VideoDetector::NotifyUpdate(v82, a2);
        if ( v82 )
          RefCnt::Release(v82);
        for ( i = 0; ; i = (_DWORD)v82 + 1 )
        {
          LODWORD(v82) = i;
          if ( i >= (unsigned int)v84 )
            break;
          v81[0] = *((_DWORD *)a2 + 4 * i + 10);
          v81[1] = *((_DWORD *)a2 + 4 * i + 11);
          v81[2] = *((_DWORD *)a2 + 4 * i + 12);
          v81[3] = *((_DWORD *)a2 + 4 * i + 13);
          v56 = (*(__int64 (__fastcall **)(struct IRdpBoundsAccumulator *, _DWORD *))(*(_QWORD *)v72 + 40LL))(v72, v81);
          v7 = v56;
          if ( v56 < 0 )
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
              "UpdateTrackerError_ProcessGraphicsUpdateBALogicFail",
              (char *)0x7D3,
              v56,
              v71);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v57 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                104,
                (unsigned int)&WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
                v57,
                (__int64)"Failed to add rect to pUpdateBA",
                v7);
            }
            TCntPtr<IRdpVCMgr>::SafeRelease(&v76);
            goto LABEL_151;
          }
        }
        CRdpUT::SpoilPrimitives((_DWORD)this, 0, 0, (_DWORD)v75, (__int64)v72);
        if ( *((_DWORD *)a2 + 1) == 1 || *((_DWORD *)a2 + 1) == 22 )
        {
          TimeHNS = (struct PipePrimitive *)CRdpUT::GetTimeHNS(this);
          v59 = (PVOID *)WPP_GLOBAL_Control;
          v58 = (__int64)TimeHNS;
        }
        else
        {
          v58 = *((_QWORD *)a2 + 134);
          ++*((_DWORD *)this + 488);
          if ( !*((_QWORD *)this + 251) )
            *((_QWORD *)this + 251) = v58;
          v59 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v60 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Di(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              105,
              &WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
              v60,
              v58);
            v59 = (PVOID *)WPP_GLOBAL_Control;
          }
          v61 = *((_QWORD *)this + 251);
          if ( v58 <= v61 )
            v62 = 0;
          else
            v62 = v58 - v61;
          TimeHNS = (struct PipePrimitive *)(v62 + *((_QWORD *)this + 250));
        }
        v84 = TimeHNS;
        if ( v58
          && v58 + 600000000 < (__int64)v74
          && v59 != &WPP_GLOBAL_Control
          && (*((_DWORD *)v59 + 7) & 0x100) != 0
          && *((_BYTE *)v59 + 25) >= 2u )
        {
          v64 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids, v64);
        }
        v82 = 0;
        if ( (int)RdpSurface::GetCacheManContext(v73, &v82) >= 0 )
          (*(void (__fastcall **)(struct IRdpCacheManContext *, struct _RDPGFX_PROVIDER_UPDATE_HDR *, struct PipePrimitive *))(*(_QWORD *)v82 + 32LL))(
            v82,
            a2,
            v84);
        if ( v82 )
          (*(void (__fastcall **)(struct IRdpCacheManContext *))(*(_QWORD *)v82 + 16LL))(v82);
        if ( v58 > *((_QWORD *)this + 248) + 300000LL )
        {
          ++*((_DWORD *)this + 498);
          *((_QWORD *)this + 248) = v58;
        }
        if ( v58 > *((_QWORD *)this + 243) )
          *((_QWORD *)this + 243) = v58;
        if ( !*((_QWORD *)this + 242) )
          *((_QWORD *)this + 242) = v58;
        if ( v58 > (__int64)v74 )
        {
          v7 = 0;
          *((_QWORD *)v73 + 25) = v58;
        }
        if ( *((_DWORD *)a2 + 1) == 22 )
        {
          v65 = *((_QWORD *)this + 245);
          if ( !v65 || *((_QWORD *)a2 + 134) < v65 )
            *((_QWORD *)this + 245) = *((_QWORD *)a2 + 134);
          v66 = *((_DWORD *)this + 492);
          if ( !v66 || *((_DWORD *)a2 + 270) < v66 )
            *((_DWORD *)this + 492) = *((_DWORD *)a2 + 270);
        }
        else
        {
          *((_QWORD *)this + 245) = v58;
        }
        TCntPtr<IRdpVCMgr>::SafeRelease(&v76);
        goto LABEL_138;
      }
    }
    v32 = *(_OWORD *)((char *)a2 + 40);
    v82 = 0;
    v74 = v32;
    v33 = PipePrimitive::CreateInstance(&v82, a2);
    v7 = v33;
    if ( v33 >= 0 )
    {
      v34 = v82;
      if ( v82 )
      {
        CRdpUT::SpoilPrimitives((_DWORD)this, (unsigned int)&v74, 0, (_DWORD)v75, (__int64)v72);
        CComPtrList<PipePrimitive,ComPlainSmartPtr<PipePrimitive>>::AddTail(v75, v34);
        (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v79 + 40LL))(v79, &v74);
        v35 = v72;
        CRdpUT::SpoilDirties(v38, v72, (struct RdpRect *)&v74);
LABEL_55:
        v37 = &v82;
LABEL_73:
        TCntPtr<CFakeGfxProvider>::SafeRelease(v37);
        goto LABEL_139;
      }
    }
    else
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
        "UpdateTrackerError_ProcessGraphicsUpdatePipePrimitiveCreateInstanceFail",
        (char *)0x790,
        v33,
        v71);
    }
    v35 = v72;
    (*(void (__fastcall **)(struct IRdpBoundsAccumulator *, __int128 *))(*(_QWORD *)v72 + 40LL))(v72, &v74);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v36 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids, v36);
    }
    goto LABEL_55;
  }
  v39 = *((_DWORD *)a2 + 12);
  v40 = *((_DWORD *)a2 + 268);
  v41 = *((_DWORD *)a2 + 269);
  v42 = *((_DWORD *)a2 + 11);
  v43 = *((_DWORD *)a2 + 13);
  LODWORD(v74) = *((_DWORD *)a2 + 10);
  LODWORD(v76) = v40 + v74;
  v77 = v40 + v39;
  HIDWORD(v76) = v41 + v42;
  v78 = v41 + v43;
  v44 = *(_QWORD *)v72;
  LODWORD(v82) = 0;
  *(_QWORD *)((char *)&v74 + 4) = __PAIR64__(v39, v42);
  v45 = *(void (__fastcall **)(struct IRdpBoundsAccumulator *, __int64 *, struct IRdpCacheManContext **))(v44 + 96);
  HIDWORD(v74) = v43;
  v45(v72, &v76, &v82);
  if ( (_DWORD)v82 )
    goto LABEL_75;
  v46 = *((_QWORD *)v73 + 21);
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64, __int64 *, struct IRdpCacheManContext **))(*(_QWORD *)v46 + 96LL))(v46, &v76, &v82);
    if ( !(_DWORD)v82 )
    {
      v84 = 0;
      v48 = PipePrimitive::CreateInstance(&v84, a2);
      v7 = v48;
      if ( v48 >= 0 )
      {
        v49 = v84;
        if ( v84 )
        {
          CRdpUT::SpoilPrimitives((_DWORD)this, (unsigned int)&v74, (unsigned int)&v76, (_DWORD)v75, (__int64)v72);
          CComPtrList<PipePrimitive,ComPlainSmartPtr<PipePrimitive>>::AddTail(v75, v49);
          (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v79 + 40LL))(v79, &v74);
          v35 = v72;
          CRdpUT::SpoilDirties(v51, v72, (struct RdpRect *)&v74);
LABEL_72:
          v37 = &v84;
          goto LABEL_73;
        }
      }
      else
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpUpdateTracker",
          "UpdateTrackerError_ProcessGraphicsUpdatePipePrimitiveCreateInstanceFail",
          (char *)0x761,
          v48,
          v71);
      }
      v35 = v72;
      (*(void (__fastcall **)(struct IRdpBoundsAccumulator *, __int128 *))(*(_QWORD *)v72 + 40LL))(v72, &v74);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v50 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids, v50);
      }
      goto LABEL_72;
    }
LABEL_75:
    v35 = v72;
    (*(void (__fastcall **)(struct IRdpBoundsAccumulator *, __int128 *))(*(_QWORD *)v72 + 40LL))(v72, &v74);
    CRdpUT::SpoilPrimitives((_DWORD)this, (unsigned int)&v74, 0, (_DWORD)v75, (__int64)v72);
    goto LABEL_139;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v47 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      101,
      (unsigned int)&WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids,
      v47,
      (__int64)"pNextFrameSpoiledBA");
  }
  v7 = -2147467261;
LABEL_151:
  if ( v80 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v80 + 4) + 16LL))(*((_QWORD *)v80 + 4));
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v69 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v69 + 5) + 16LL))(*((_QWORD *)v69 + 5));
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001dd38  push    rbp
0x18001dd3a  push    rbx
0x18001dd3b  push    rsi
0x18001dd3c  push    rdi
0x18001dd3d  push    r13
0x18001dd3f  push    r14
0x18001dd41  push    r15
0x18001dd43  lea     rbp, [rsp-27h]
0x18001dd48  sub     rsp, 90h
0x18001dd4f  lea     rsi, [rcx+98h]
0x18001dd56  mov     [rbp+57h+var_88], 0
0x18001dd5e  mov     r14, rcx
0x18001dd61  xor     edi, edi
0x18001dd63  mov     rcx, rsi; this
0x18001dd66  mov     [rbp+57h+var_50], rdi
0x18001dd6a  mov     rbx, rdx
0x18001dd6d  mov     [rbp+57h+arg_10], edi
0x18001dd70  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18001dd75  mov     rcx, [r14+70h]
0x18001dd79  test    rcx, rcx
0x18001dd7c  jz      short loc_18001DD8D
0x18001dd7e  mov     rax, [rcx]
0x18001dd81  mov     rdi, rcx
0x18001dd84  mov     rax, [rax+8]
0x18001dd88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd8d  test    rsi, rsi
0x18001dd90  jz      short loc_18001DD9A
0x18001dd92  mov     rcx, rsi; this
0x18001dd95  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18001dd9a  test    rdi, rdi
0x18001dd9d  jnz     short loc_18001DDA6
0x18001dd9f  xor     esi, esi
0x18001dda1  jmp     loc_18001E900
0x18001dda6  mov     rax, [rdi]
0x18001dda9  lea     r8, [rbp+57h+var_88]
0x18001ddad  mov     rdx, [rbx+8]
0x18001ddb1  mov     rcx, rdi
0x18001ddb4  mov     rax, [rax+20h]
0x18001ddb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddbd  mov     esi, eax
0x18001ddbf  test    eax, eax
0x18001ddc1  jns     short loc_18001DE1C
0x18001ddc3  mov     r9d, eax; unsigned int
0x18001ddc6  lea     rdx, aUpdatetrackere_8; "UpdateTrackerError_ProcessGraphicsUpdat"...
0x18001ddcd  mov     r8d, 71Fh; char *
0x18001ddd3  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x18001ddda  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18001dddf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dde6  lea     r13, WPP_GLOBAL_Control
0x18001dded  cmp     rcx, r13
0x18001ddf0  jz      loc_18001E900
0x18001ddf6  test    byte ptr [rcx+1Ch], 8
0x18001ddfa  jz      loc_18001E900
0x18001de00  cmp     byte ptr [rcx+19h], 1
0x18001de04  jb      loc_18001E900
0x18001de0a  mov     r9, [rbx+8]
0x18001de0e  mov     rcx, [rcx+10h]
0x18001de12  call    WPP_SF_i
0x18001de17  jmp     loc_18001E900
0x18001de1c  mov     rcx, [rbp+57h+var_88]; this
0x18001de20  mov     rax, [rcx+108h]
0x18001de27  mov     [rbp+57h+var_90], rax
0x18001de2b  test    rax, rax
0x18001de2e  jnz     loc_18001DEB5
0x18001de34  mov     esi, 80004003h
0x18001de39  lea     rdx, aUpdatetrackere_8; "UpdateTrackerError_ProcessGraphicsUpdat"...
0x18001de40  mov     r9d, esi; unsigned int
0x18001de43  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x18001de4a  mov     r8d, 727h; char *
0x18001de50  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18001de55  mov     rax, cs:WPP_GLOBAL_Control
0x18001de5c  lea     r13, WPP_GLOBAL_Control
0x18001de63  cmp     rax, r13
0x18001de66  jz      loc_18001E900
0x18001de6c  test    byte ptr [rax+1Ch], 8
0x18001de70  jz      loc_18001E900
0x18001de76  cmp     byte ptr [rax+19h], 2
0x18001de7a  jb      loc_18001E900
0x18001de80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001de85  mov     edx, 61h ; 'a'
0x18001de8a  lea     rcx, aPupdateba; "pUpdateBA"
0x18001de91  mov     [rsp+0C0h+var_A0], rcx
0x18001de96  lea     r8, WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids
0x18001de9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dea4  mov     r9d, eax
0x18001dea7  mov     rcx, [rcx+10h]
0x18001deab  call    WPP_SF_Ds
0x18001deb0  jmp     loc_18001E900
0x18001deb5  mov     rax, [rcx+110h]
0x18001debc  mov     [rbp+57h+var_58], rax
0x18001dec0  test    rax, rax
0x18001dec3  jnz     short loc_18001DF27
0x18001dec5  mov     esi, 80004003h
0x18001deca  lea     rdx, aUpdatetrackere_8; "UpdateTrackerError_ProcessGraphicsUpdat"...
0x18001ded1  mov     r9d, esi; unsigned int
0x18001ded4  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x18001dedb  mov     r8d, 72Bh; char *
0x18001dee1  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18001dee6  mov     rax, cs:WPP_GLOBAL_Control
0x18001deed  lea     r13, WPP_GLOBAL_Control
0x18001def4  cmp     rax, r13
0x18001def7  jz      loc_18001E900
0x18001defd  test    byte ptr [rax+1Ch], 8
0x18001df01  jz      loc_18001E900
0x18001df07  cmp     byte ptr [rax+19h], 2
0x18001df0b  jb      loc_18001E900
0x18001df11  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001df16  mov     edx, 62h ; 'b'
0x18001df1b  lea     rcx, aPprimitiveba; "pPrimitiveBA"
0x18001df22  jmp     loc_18001DE91
0x18001df27  mov     rax, [rcx+0C8h]
0x18001df2e  lea     rdx, [rbp+57h+var_50]; struct PipePrimitiveList **
0x18001df32  mov     qword ptr [rbp+57h+var_80], rax
0x18001df36  call    ?GetPrimitiveList@RdpSurface@@QEAAJPEAPEAVPipePrimitiveList@@@Z; RdpSurface::GetPrimitiveList(PipePrimitiveList * *)
0x18001df3b  mov     esi, eax
0x18001df3d  test    eax, eax
0x18001df3f  jns     short loc_18001DF9E
0x18001df41  mov     r9d, eax; unsigned int
0x18001df44  lea     rdx, aUpdatetrackere_8; "UpdateTrackerError_ProcessGraphicsUpdat"...
0x18001df4b  mov     r8d, 736h; char *
0x18001df51  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x18001df58  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18001df5d  mov     rax, cs:WPP_GLOBAL_Control
0x18001df64  lea     r13, WPP_GLOBAL_Control
0x18001df6b  cmp     rax, r13
0x18001df6e  jz      loc_18001E900
0x18001df74  test    byte ptr [rax+1Ch], 8
0x18001df78  jz      loc_18001E900
0x18001df7e  cmp     byte ptr [rax+19h], 2
0x18001df82  jb      loc_18001E900
0x18001df88  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001df8d  mov     edx, 64h ; 'd'
0x18001df92  lea     rcx, aFailedToGetPri; "Failed to get primitive list"
0x18001df99  jmp     loc_18001E8DD
0x18001df9e  mov     rax, [rbp+57h+var_50]
0x18001dfa2  lea     r13, WPP_GLOBAL_Control
0x18001dfa9  mov     ecx, [rbx+4]
0x18001dfac  add     rax, 30h ; '0'
0x18001dfb0  mov     [rbp+57h+var_70], rax
0x18001dfb4  mov     r15b, 8
0x18001dfb7  sub     ecx, 1
0x18001dfba  jz      loc_18001E49B
0x18001dfc0  sub     ecx, 10h
0x18001dfc3  jz      loc_18001E42B
0x18001dfc9  sub     ecx, 1
0x18001dfcc  jz      loc_18001E49B
0x18001dfd2  sub     ecx, 1
0x18001dfd5  jz      loc_18001E218
0x18001dfdb  sub     ecx, 1
0x18001dfde  jz      loc_18001E121
0x18001dfe4  sub     ecx, 1
0x18001dfe7  jz      loc_18001E121
0x18001dfed  sub     ecx, 1
0x18001dff0  jz      loc_18001E49B
0x18001dff6  sub     ecx, 6
0x18001dff9  jz      loc_18001E0A6
0x18001dfff  cmp     ecx, 1
0x18001e002  jnz     loc_18001E806
0x18001e008  mov     rcx, [r14+70h]
0x18001e00c  mov     r8d, [rbx+430h]
0x18001e013  mov     rdx, [rbx+8]
0x18001e017  mov     rax, [rcx]
0x18001e01a  mov     rax, [rax+40h]
0x18001e01e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e023  mov     esi, eax
0x18001e025  test    eax, eax
0x18001e027  jns     loc_18001E806
0x18001e02d  mov     r9d, eax; unsigned int
0x18001e030  lea     rdx, aUpdatetrackere_13; "UpdateTrackerError_ProcessGraphicsWater"...
0x18001e037  mov     r8d, 856h; char *
0x18001e03d  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x18001e044  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18001e049  mov     rax, cs:WPP_GLOBAL_Control
0x18001e050  cmp     rax, r13
0x18001e053  jz      loc_18001E806
0x18001e059  test    [rax+1Ch], r15b
0x18001e05d  jz      loc_18001E806
0x18001e063  cmp     byte ptr [rax+19h], 2
0x18001e067  jb      loc_18001E806
0x18001e06d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e072  mov     edx, 6Eh ; 'n'
0x18001e077  lea     rcx, aFailedToProces; "Failed to process watermarking update"
0x18001e07e  mov     [rsp+0C0h+var_98], esi
0x18001e082  lea     r8, WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids
0x18001e089  mov     [rsp+0C0h+var_A0], rcx
0x18001e08e  mov     r9d, eax
0x18001e091  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e098  mov     rcx, [rcx+10h]
0x18001e09c  call    WPP_SF_DsD
0x18001e0a1  jmp     loc_18001E806
0x18001e0a6  mov     rcx, [r14+70h]
0x18001e0aa  mov     r8d, [rbx+430h]
0x18001e0b1  mov     rdx, [rbx+8]
0x18001e0b5  mov     rax, [rcx]
0x18001e0b8  mov     rax, [rax+38h]
0x18001e0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0c1  mov     esi, eax
0x18001e0c3  test    eax, eax
0x18001e0c5  jns     loc_18001E806
0x18001e0cb  mov     r9d, eax; unsigned int
0x18001e0ce  lea     rdx, aUpdatetrackere_10; "UpdateTrackerError_ProcessGraphicsScree"...
0x18001e0d5  mov     r8d, 849h; char *
0x18001e0db  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x18001e0e2  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18001e0e7  mov     rax, cs:WPP_GLOBAL_Control
0x18001e0ee  cmp     rax, r13
0x18001e0f1  jz      loc_18001E806
0x18001e0f7  test    [rax+1Ch], r15b
0x18001e0fb  jz      loc_18001E806
0x18001e101  cmp     byte ptr [rax+19h], 2
0x18001e105  jb      loc_18001E806
0x18001e10b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e110  mov     edx, 6Dh ; 'm'
0x18001e115  lea     rcx, aFailedToProces_10; "Failed to process screen capture protec"...
0x18001e11c  jmp     loc_18001E07E
0x18001e121  movups  xmm0, xmmword ptr [rbx+28h]
0x18001e125  mov     rdx, rbx; struct _RDPGFX_PROVIDER_UPDATE_HDR *
0x18001e128  mov     [rbp+57h+arg_0], 0
0x18001e130  lea     rcx, [rbp+57h+arg_0]; struct PipePrimitive **
0x18001e134  movdqu  [rbp+57h+var_80], xmm0
0x18001e139  call    ?CreateInstance@PipePrimitive@@SAJPEAPEAV1@PEAU_RDPGFX_PROVIDER_UPDATE_HDR@@@Z; PipePrimitive::CreateInstance(PipePrimitive * *,_RDPGFX_PROVIDER_UPDATE_HDR *)
0x18001e13e  mov     esi, eax
0x18001e140  test    eax, eax
0x18001e142  jns     short loc_18001E162
0x18001e144  mov     r9d, eax; unsigned int
0x18001e147  lea     rdx, aUpdatetrackere_19; "UpdateTrackerError_ProcessGraphicsUpdat"...
0x18001e14e  mov     r8d, 790h; char *
0x18001e154  lea     rcx, aIidIrdpupdatet; "IID_IRdpUpdateTracker"
0x18001e15b  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18001e160  jmp     short loc_18001E16B
0x18001e162  mov     rbx, [rbp+57h+arg_0]
0x18001e166  test    rbx, rbx
0x18001e169  jnz     short loc_18001E1CA
0x18001e16b  mov     rbx, [rbp+57h+var_90]
0x18001e16f  lea     rdx, [rbp+57h+var_80]
0x18001e173  mov     rcx, rbx
0x18001e176  mov     rax, [rbx]
0x18001e179  mov     rax, [rax+28h]
0x18001e17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e182  mov     rax, cs:WPP_GLOBAL_Control
0x18001e189  cmp     rax, r13
0x18001e18c  jz      short loc_18001E1C1
0x18001e18e  test    dword ptr [rax+1Ch], 100h
0x18001e195  jz      short loc_18001E1C1
0x18001e197  cmp     byte ptr [rax+19h], 2
0x18001e19b  jb      short loc_18001E1C1
0x18001e19d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e1a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1a9  lea     r8, WPP_5ac357a0e0813aabd78bb6e7ef699237_Traceguids
0x18001e1b0  mov     edx, 67h ; 'g'
0x18001e1b5  mov     r9d, eax
0x18001e1b8  mov     rcx, [rcx+10h]
0x18001e1bc  call    WPP_SF_d
0x18001e1c1  lea     rcx, [rbp+57h+arg_0]
0x18001e1c5  jmp     loc_18001E39E
0x18001e1ca  mov     rax, [rbp+57h+var_90]
0x18001e1ce  lea     rdx, [rbp+57h+var_80]
0x18001e1d2  mov     r9, [rbp+57h+var_70]
0x18001e1d6  xor     r8d, r8d
0x18001e1d9  mov     rcx, r14
0x18001e1dc  mov     [rsp+0C0h+var_A0], rax
0x18001e1e1  call    ?SpoilPrimitives@CRdpUT@@IEAAJPEAURdpRect@@0PEAV?$CComPtrList@VPipePrimitive@@V?$ComPlainSmartPtr@VPipePrimitive@@@@@@PEAVIRdpBoundsAccumulator@@@Z; CRdpUT::SpoilPrimitives(RdpRect *,RdpRect *,CComPtrList<PipePrimitive,ComPlainSmartPtr<PipePrimitive>> *,IRdpBoundsAccumulator *)
0x18001e1e6  mov     rcx, [rbp+57h+var_70]
0x18001e1ea  mov     rdx, rbx
0x18001e1ed  call    ?AddTail@?$CComPtrList@VPipePrimitive@@V?$ComPlainSmartPtr@VPipePrimitive@@@@@@QEAAPEAXPEAVPipePrimitive@@@Z; CComPtrList<PipePrimitive,ComPlainSmartPtr<PipePrimitive>>::AddTail(PipePrimitive *)
0x18001e1f2  mov     rcx, [rbp+57h+var_58]
0x18001e1f6  lea     rdx, [rbp+57h+var_80]
0x18001e1fa  mov     rax, [rcx]
0x18001e1fd  mov     rax, [rax+28h]
0x18001e201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e206  mov     rbx, [rbp+57h+var_90]
0x18001e20a  lea     r8, [rbp+57h+var_80]; struct RdpRect *
0x18001e20e  mov     rdx, rbx; struct IRdpBoundsAccumulator *
0x18001e211  call    ?SpoilDirties@CRdpUT@@IEAAJPEAVIRdpBoundsAccumulator@@PEAURdpRect@@@Z; CRdpUT::SpoilDirties(IRdpBoundsAccumulator *,RdpRect *)
0x18001e216  jmp     short loc_18001E1C1
0x18001e218  mov     eax, [rbx+28h]
0x18001e21b  mov     edx, [rbx+30h]
0x18001e21e  mov     ecx, [rbx+430h]
0x18001e224  mov     r8d, [rbx+434h]
0x18001e22b  mov     r10d, [rbx+2Ch]
0x18001e22f  mov     r9d, [rbx+34h]
0x18001e233  mov     dword ptr [rbp+57h+var_80], eax
0x18001e236  add     eax, ecx
0x18001e238  mov     dword ptr [rbp+57h+var_68], eax
0x18001e23b  lea     eax, [rcx+rdx]
0x18001e23e  mov     rcx, [rbp+57h+var_90]
0x18001e242  mov     [rbp+57h+var_60], eax
0x18001e245  lea     eax, [r8+r10]
0x18001e249  mov     dword ptr [rbp+57h+var_68+4], eax
0x18001e24c  lea     eax, [r8+r9]
0x18001e250  mov     [rbp+57h+var_5C], eax
0x18001e253  lea     r8, [rbp+57h+arg_0]
0x18001e257  mov     rax, [rcx]
0x18001e25a  mov     dword ptr [rbp+57h+var_80+8], edx
0x18001e25d  lea     rdx, [rbp+57h+var_68]
0x18001e261  mov     dword ptr [rbp+57h+arg_0], 0
0x18001e268  mov     dword ptr [rbp+57h+var_80+4], r10d
0x18001e26c  mov     rax, [rax+60h]
0x18001e270  mov     dword ptr [rbp+57h+var_80+0Ch], r9d
0x18001e274  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
