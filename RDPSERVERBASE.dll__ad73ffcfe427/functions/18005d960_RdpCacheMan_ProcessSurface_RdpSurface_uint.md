# RdpCacheMan::ProcessSurface(RdpSurface *,uint)

- ea: `0x18005d960`
- end: `0x18005e524`
- name: `?ProcessSurface@RdpCacheMan@@UEAAJPEAVRdpSurface@@I@Z`
- size: `3012`
- prototype: `int(RdpCacheMan *__hidden this, struct RdpSurface *, unsigned int)`
- caller_count: `0`
- callee_count: `27`
- tags: `installer_update`

## callees

- `0x18000cdac`
- `0x18000cddc`
- `0x18000ce04`
- `0x18000ce34`
- `0x18000e4ec`
- `0x180011094`
- `0x18001dcf4`
- `0x18001edf0`
- `0x18001f810`
- `0x18001f850`
- `0x180028a30`
- `0x18002b16c`
- `0x1800393b0`
- `0x18004d560`
- `0x180053eac`
- `0x18005d960`
- `0x180076090`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x180079f10`
- `0x18007a404`
- `0x18007e9e0`
- `0x1800e2cdc`
- `0x180157cc8`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x18005da75`: `IID_IRdpCacheMan`
- `0x18005db61`: `IID_IRdpCacheMan`
- `0x18005de53`: `IID_IRdpCacheMan`
- `0x18005df0d`: `IID_IRdpCacheMan`
- `0x18005dfbd`: `IID_IRdpCacheMan`
- `0x18005e06b`: `IID_IRdpCacheMan`
- `0x18005e0ed`: `IID_IRdpCacheMan`
- `0x18005e1a1`: `IID_IRdpCacheMan`
- `0x18005e21a`: `IID_IRdpCacheMan`
- `0x18005e437`: `IID_IRdpCacheMan`
- `0x18005da6b`: `RdpCacheManError_ProcessSurfaceGetSurfaceDataFail`
- `0x18005db57`: `RdpCacheManError_ProcessSurfaceGetSurfaceDataFail`
- `0x18005de49`: `RdpCacheManError_ProcessSurfaceGetSurfaceDataFail`
- `0x18005de05`: `RemoveMMRBA on m_spClassifyBA failed!`
- `0x18005de9a`: `pIntraframeCacheBA`
- `0x18005df00`: `RdpCacheManError_ProcessSurfaceGetCacheManContextFail`
- `0x18005df4e`: `RdpSurface::GetCacheManContext() failed`
- `0x18005dfb0`: `RdpCacheManError_ProcessSurfaceUpdatePendingCacheFail`
- `0x18005dffe`: `UpdatePendingCache failed`
- `0x18005e05e`: `RdpCacheManError_ProcessSurfaceGetGraphicsSourceContextFail`
- `0x18005e0ac`: `Failed to get update context`
- `0x18005e0e0`: `RdpCacheManError_ProcessSurfaceGetSurfaceInfoFail`
- `0x18005e194`: `RdpCacheManError_ProcessSurfaceUpdateContextQueryInterfaceFail`
- `0x18005e20d`: `RdpCacheManError_ProcessSurfaceGetEncodingPixelMapFail`
- `0x18005e42a`: `RdpCacheManError_ProcessSurfaceProcessPixelMapFail`

## pseudocode

```c
__int64 __fastcall RdpCacheMan::ProcessSurface(__int64 **this, struct RdpSurface *a2, unsigned int a3)
{
  RdpCacheMan *v3; // rdi
  __int64 *v4; // rcx
  __int64 v7; // rax
  unsigned int v8; // eax
  int v9; // eax
  int v10; // edi
  int v11; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  struct IRdpBoundsAccumulator *v13; // r12
  int GridIterator; // esi
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  RdpCacheMan *v18; // r12
  unsigned int v19; // eax
  __int64 v21; // r14
  __int64 v22; // rbx
  struct CRdpAdaptiveGrid *v23; // rdi
  unsigned int v24; // eax
  int v25; // edx
  const char *v26; // rcx
  __int64 v27; // rbx
  unsigned int v28; // eax
  int v29; // edx
  const char *v30; // rcx
  signed int CacheManContext; // eax
  unsigned int v32; // eax
  int v33; // edx
  const char *v34; // rcx
  __int64 v35; // rbx
  signed int updated; // eax
  int v37; // r13d
  signed int GraphicsSourceContext; // eax
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64); // r12
  signed int v40; // eax
  signed int v41; // eax
  signed int EncodingPixelMap; // eax
  unsigned int v43; // eax
  __int64 v44; // rcx
  bool v45; // zf
  unsigned int v46; // eax
  signed int v47; // eax
  unsigned int v48; // eax
  __int64 v49; // rcx
  unsigned int v50; // r9d
  int v51; // [rsp+20h] [rbp-89h]
  int v52; // [rsp+20h] [rbp-89h]
  unsigned int v53[2]; // [rsp+40h] [rbp-69h] BYREF
  struct CRdpAdaptiveGrid *v54; // [rsp+48h] [rbp-61h] BYREF
  __int64 v55; // [rsp+50h] [rbp-59h] BYREF
  __int64 v56; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v57; // [rsp+60h] [rbp-49h] BYREF
  _DWORD v58[3]; // [rsp+64h] [rbp-45h] BYREF
  __int64 v59; // [rsp+70h] [rbp-39h] BYREF
  struct IRdpCacheManContext *v60; // [rsp+78h] [rbp-31h] BYREF
  struct PixelMap *v61; // [rsp+80h] [rbp-29h] BYREF
  __int64 v62; // [rsp+88h] [rbp-21h]
  _OWORD v63[2]; // [rsp+90h] [rbp-19h] BYREF
  __int128 v64; // [rsp+B0h] [rbp+7h]

  *(_QWORD *)v53 = this;
  v57 = 0;
  v3 = (RdpCacheMan *)this;
  v58[0] = a3;
  v4 = this[14];
  memset(v63, 0, sizeof(v63));
  v61 = 0;
  v60 = 0;
  v64 = 0;
  v7 = *v4;
  v59 = 0;
  *(_QWORD *)&v58[1] = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *))(v7 + 112))(v4);
  PerfCounterSetRdpIntervalMarker(*((struct IRDPPerfCounterGeneric **)v3 + 4), v8, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 19) + 176LL))(*((_QWORD *)a2 + 19));
    v10 = *((unsigned __int16 *)a2 + 28);
    v11 = v9;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
      CurrentThreadActivityIdPrefix,
      v10,
      a3,
      v11);
    v3 = *(RdpCacheMan **)v53;
  }
  v13 = (struct IRdpBoundsAccumulator *)*((_QWORD *)a2 + 35);
  if ( !v13 )
  {
    GridIterator = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_ProcessSurfaceGetSurfaceDataFail",
      (char *)0x149,
      0x80004003,
      v51);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 19;
    v17 = "pFrameDirtyBA";
    goto LABEL_10;
  }
  v21 = *((_QWORD *)a2 + 19);
  if ( !v21 )
  {
    GridIterator = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_ProcessSurfaceGetSurfaceDataFail",
      (char *)0x14D,
      0x80004003,
      v51);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 20;
    v17 = "pEncodingBA";
    goto LABEL_10;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 14) + 144LL))(*((_QWORD *)v3 + 14)) )
  {
    v22 = *((_QWORD *)a2 + 205);
    v55 = 0;
    v54 = 0;
    v56 = 0;
    if ( !v22 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 21;
      v26 = "spMMRHintManager";
      goto LABEL_27;
    }
    TCntPtr<CFakeGfxProvider>::SafeRelease(&v55);
    v55 = v22;
    TCntPtr<PipePrimitive>::SafeAddRef(&v55);
    TCntPtr<IRDPCoreVirtualChannel>::operator=(&v54, *(_QWORD *)(v22 + 48));
    v23 = v54;
    if ( !v54 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 22;
      v26 = "spMMRHintBA";
LABEL_27:
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v25,
        (unsigned int)&WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
        v24,
        (__int64)v26);
LABEL_28:
      GridIterator = -2147467261;
LABEL_29:
      TCntPtr<IRdpVCMgr>::SafeRelease(&v56);
      TCntPtr<IRdpVCMgr>::SafeRelease(&v54);
      TCntPtr<CFakeGfxProvider>::SafeRelease(&v55);
      goto LABEL_11;
    }
    TCntPtr<IRDPCoreVirtualChannel>::operator=(&v56, *(_QWORD *)(v22 + 64));
    v27 = v56;
    if ( !v56 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 23;
      v26 = "spMMREncodingBA";
      goto LABEL_27;
    }
    if ( !(*(unsigned int (__fastcall **)(struct CRdpAdaptiveGrid *))(*(_QWORD *)v23 + 136LL))(v23) )
    {
      GridIterator = (*(__int64 (__fastcall **)(__int64, struct CRdpAdaptiveGrid *))(*(_QWORD *)v27 + 48LL))(v27, v23);
      if ( GridIterator < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_29;
        }
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 24;
        v30 = "AddMMRBA to mmrEncodingBA failed!";
        goto LABEL_41;
      }
      GridIterator = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 64LL))(v27, v21);
      if ( GridIterator < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_29;
        }
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 25;
        v30 = "Intersect mmrEncodingBA with encodingBA failed!";
        goto LABEL_41;
      }
      GridIterator = (*(__int64 (__fastcall **)(__int64, struct CRdpAdaptiveGrid *))(*(_QWORD *)v21 + 56LL))(v21, v23);
      if ( GridIterator < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_29;
        }
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 26;
        v30 = "RemoveMMRBA on m_spClassifyBA failed!";
LABEL_41:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v29,
          (unsigned int)&WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
          v28,
          (__int64)v30,
          GridIterator);
        goto LABEL_29;
      }
    }
    TCntPtr<IRdpVCMgr>::SafeRelease(&v56);
    TCntPtr<IRdpVCMgr>::SafeRelease(&v54);
    TCntPtr<CFakeGfxProvider>::SafeRelease(&v55);
    v3 = *(RdpCacheMan **)v53;
  }
  v62 = *((_QWORD *)a2 + 22);
  if ( !v62 )
  {
    GridIterator = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_ProcessSurfaceGetSurfaceDataFail",
      (char *)0x16E,
      0x80004003,
      v51);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 27;
    v17 = "pIntraframeCacheBA";
LABEL_10:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      (unsigned int)&WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
      v15,
      (__int64)v17);
LABEL_11:
    v18 = *(RdpCacheMan **)v53;
    goto LABEL_12;
  }
  CacheManContext = RdpSurface::GetCacheManContext(a2, &v60);
  GridIterator = CacheManContext;
  if ( CacheManContext < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_ProcessSurfaceGetCacheManContextFail",
      (char *)0x173,
      CacheManContext,
      v51);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
    v33 = 29;
    v34 = "RdpSurface::GetCacheManContext() failed";
    goto LABEL_67;
  }
  TCntPtr<RdpCacheManContext>::operator=(
    &v59,
    ((unsigned __int64)v60 - 48) & ((unsigned __int128)-(__int128)(unsigned __int64)v60 >> 64));
  v35 = v59;
  updated = RdpCacheManContext::UpdatePendingCache((RdpCacheManContext *)(v59 + 48), v13);
  GridIterator = updated;
  if ( updated < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_ProcessSurfaceUpdatePendingCacheFail",
      (char *)0x17D,
      updated,
      v51);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
    v33 = 30;
    v34 = "UpdatePendingCache failed";
    goto LABEL_67;
  }
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v21 + 136LL))(v21) )
    goto LABEL_11;
  v37 = a3 / 0xFFFFFFFF + a3;
  if ( !v37 )
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 144LL))(v21, &v57);
  GraphicsSourceContext = RdpSurface::GetGraphicsSourceContext(a2, (struct IRdpGFXSourceUpdateContext **)&v58[1]);
  GridIterator = GraphicsSourceContext;
  if ( GraphicsSourceContext < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_ProcessSurfaceGetGraphicsSourceContextFail",
      (char *)0x18D,
      GraphicsSourceContext,
      v51);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
    v33 = 31;
    v34 = "Failed to get update context";
    goto LABEL_67;
  }
  v39 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v58[1];
  v40 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _OWORD *))(**(_QWORD **)&v58[1] + 56LL))(
          *(_QWORD *)&v58[1],
          *((_QWORD *)a2 + 78),
          v63);
  GridIterator = v40;
  if ( v40 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_ProcessSurfaceGetSurfaceInfoFail",
      (char *)0x194,
      v40,
      v51);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_11;
    }
    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
    v33 = 32;
    v34 = "Failed to get surface info";
    goto LABEL_67;
  }
  if ( (_DWORD)v64 )
  {
    if ( DWORD2(v64) == 64 )
      *((_QWORD *)v3 + 7) = 4194368;
    if ( *(_QWORD *)(v35 + 312) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease(v35 + 312);
      *(_QWORD *)(v35 + 312) = 0;
    }
    v41 = (**v39)(v39, &IID_IRdpGFXSourceHashKeyCapableUpdateContext, v35 + 312);
    GridIterator = v41;
    if ( v41 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
        "RdpCacheManError_ProcessSurfaceUpdateContextQueryInterfaceFail",
        (char *)0x1A5,
        v41,
        v51);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_11;
      }
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      v33 = 33;
      v34 = "Failed to QI for advertised hashkey offload support";
      goto LABEL_67;
    }
  }
  if ( !*(_QWORD *)(v35 + 312) )
  {
    EncodingPixelMap = RdpSurface::GetEncodingPixelMap(a2, &v61);
    GridIterator = EncodingPixelMap;
    if ( EncodingPixelMap < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
        "RdpCacheManError_ProcessSurfaceGetEncodingPixelMapFail",
        (char *)0x1AD,
        EncodingPixelMap,
        v51);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_11;
      }
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      v33 = 34;
      v34 = "RdpSurface::GetEncodingPixelMap() failed";
LABEL_67:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v33,
        (unsigned int)&WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
        v32,
        (__int64)v34,
        GridIterator);
      goto LABEL_11;
    }
  }
  ++*(_DWORD *)(v35 + 296);
  if ( !*(_DWORD *)(v35 + 304) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v43 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids, v43);
    }
    GridIterator = 0;
    goto LABEL_11;
  }
  v18 = *(RdpCacheMan **)v53;
  v44 = *(_QWORD *)(*(_QWORD *)v53 + 120LL);
  if ( v44 )
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v44 + 176LL))(v44, 0, v21);
  if ( *(_DWORD *)(*(_QWORD *)v53 + 60LL) == 2 )
  {
    v54 = 0;
    v45 = *(_QWORD *)(v35 + 168) == 0;
    v53[0] = 0;
    if ( v45 || !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 39) + 136LL))(*((_QWORD *)a2 + 39)) )
    {
      if ( (int)RdpSurface::GetAdaptiveGrid(a2, &v54, (int *)v53) < 0 )
        goto LABEL_118;
      if ( !v53[0] && *(_QWORD *)(v35 + 168) )
      {
LABEL_123:
        TCntPtr<CImageClassifier>::SafeRelease(&v54);
        goto LABEL_124;
      }
      TCntPtr<MotionDetectionContext>::operator=(v35 + 168, 0);
      GridIterator = CRdpAdaptiveGrid::CreateGridIterator(v54, (struct CRdpGridIterator **)(v35 + 168));
    }
    if ( GridIterator < 0 )
    {
LABEL_118:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids, v46);
      }
      *((_DWORD *)v18 + 15) = 1;
      goto LABEL_123;
    }
    goto LABEL_123;
  }
LABEL_124:
  v54 = (struct CRdpAdaptiveGrid *)v35;
  TCntPtr<PipePrimitive>::SafeAddRef(&v54);
  v56 = v62;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v56);
  v55 = v21;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v55);
  v47 = RdpCacheMan::ProcessPixelMap((RdpCacheMan *)((char *)v18 - 56), (__int64)&v56, (__int64)&v54);
  GridIterator = v47;
  if ( v47 >= 0 )
  {
    GridIterator = 0;
    *(_DWORD *)(v35 + 304) = 0;
    v49 = *((_QWORD *)v18 + 15);
    if ( v49 )
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v49 + 200LL))(v49, 0, v21);
    if ( !v37 )
    {
      v53[0] = 0;
      if ( v57 )
      {
        if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 144LL))(v21, v53) >= 0 )
          RDPGraphicsTraceLogging::LogRDPGraphicsCachePixels(
            (RDPGraphicsTraceLogging *)v58[0],
            v57,
            v53[0],
            v50,
            *(float *)&v52);
      }
    }
  }
  else
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_ProcessSurfaceProcessPixelMapFail",
      (char *)0x1EC,
      v47,
      v52);
    if ( GridIterator != -2147024774
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v48 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
        v48,
        GridIterator);
    }
  }
LABEL_12:
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v18 + 14) + 112LL))(*((_QWORD *)v18 + 14));
  PerfCounterSetRdpIntervalMarker(*((struct IRDPPerfCounterGeneric **)v18 + 5), v19, 1u);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v58[1]);
  TCntPtr<CFakeGfxProvider>::SafeRelease(&v59);
  if ( v60 )
    (*(void (__fastcall **)(struct IRdpCacheManContext *))(*(_QWORD *)v60 + 16LL))(v60);
  return (unsigned int)GridIterator;
}

```

## disassembly

```asm
0x18005d960  mov     [rsp-8+arg_18], rbx
0x18005d965  push    rbp
0x18005d966  push    rsi
0x18005d967  push    rdi
0x18005d968  push    r12
0x18005d96a  push    r13
0x18005d96c  push    r14
0x18005d96e  push    r15
0x18005d970  lea     rbp, [rsp-27h]
0x18005d975  sub     rsp, 0D0h
0x18005d97c  mov     rax, cs:__security_cookie
0x18005d983  xor     rax, rsp
0x18005d986  mov     [rbp+57h+var_40], rax
0x18005d98a  xor     esi, esi
0x18005d98c  mov     qword ptr [rbp+57h+var_C0], rcx
0x18005d990  xorps   xmm0, xmm0
0x18005d993  mov     [rbp+57h+var_A0], esi
0x18005d996  mov     rdi, rcx
0x18005d999  mov     dword ptr [rbp+57h+var_9C], r8d
0x18005d99d  mov     rcx, [rcx+70h]
0x18005d9a1  mov     r13d, r8d
0x18005d9a4  movups  [rbp+57h+var_70], xmm0
0x18005d9a8  mov     r15, rdx
0x18005d9ab  mov     [rbp+57h+var_80], rsi
0x18005d9af  movups  [rbp+57h+var_60], xmm0
0x18005d9b3  mov     [rbp+57h+var_88], rsi
0x18005d9b7  movups  [rbp+57h+var_50], xmm0
0x18005d9bb  mov     rax, [rcx]
0x18005d9be  mov     [rbp+57h+var_90], rsi
0x18005d9c2  mov     qword ptr [rbp+57h+var_9C+4], rsi
0x18005d9c6  mov     rax, [rax+70h]
0x18005d9ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9cf  mov     rcx, [rdi+20h]; struct IRDPPerfCounterGeneric *
0x18005d9d3  xor     r8d, r8d; unsigned int
0x18005d9d6  mov     edx, eax; unsigned int
0x18005d9d8  call    ?PerfCounterSetRdpIntervalMarker@@YAJPEAUIRDPPerfCounterGeneric@@II@Z; PerfCounterSetRdpIntervalMarker(IRDPPerfCounterGeneric *,uint,uint)
0x18005d9dd  mov     rax, cs:WPP_GLOBAL_Control
0x18005d9e4  lea     rbx, WPP_GLOBAL_Control
0x18005d9eb  cmp     rax, rbx
0x18005d9ee  jz      short loc_18005DA56
0x18005d9f0  test    dword ptr [rax+1Ch], 100h
0x18005d9f7  jz      short loc_18005DA56
0x18005d9f9  cmp     byte ptr [rax+19h], 5
0x18005d9fd  jb      short loc_18005DA56
0x18005d9ff  mov     rcx, [r15+98h]
0x18005da06  mov     rax, [rcx]
0x18005da09  mov     rax, [rax+0B0h]
0x18005da10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da15  movzx   edi, word ptr [r15+38h]
0x18005da1a  mov     ebx, eax
0x18005da1c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005da21  mov     rcx, cs:WPP_GLOBAL_Control
0x18005da28  lea     edx, [rsi+10h]
0x18005da2b  mov     [rsp+100h+var_D0], ebx
0x18005da2f  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x18005da36  mov     dword ptr [rsp+100h+var_D8], r13d
0x18005da3b  mov     r9d, eax
0x18005da3e  mov     [rsp+100h+var_E0], edi; int
0x18005da42  mov     rcx, [rcx+10h]
0x18005da46  call    WPP_SF_DDDD
0x18005da4b  mov     rdi, qword ptr [rbp+57h+var_C0]
0x18005da4f  lea     rbx, WPP_GLOBAL_Control
0x18005da56  mov     r12, [r15+118h]
0x18005da5d  test    r12, r12
0x18005da60  jnz     loc_18005DB46
0x18005da66  mov     esi, 80004003h
0x18005da6b  lea     rdx, aRdpcachemanerr_1; "RdpCacheManError_ProcessSurfaceGetSurfa"...
0x18005da72  mov     r9d, esi; unsigned int
0x18005da75  lea     rcx, aIidIrdpcachema; "IID_IRdpCacheMan"
0x18005da7c  mov     r8d, 149h; char *
0x18005da82  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18005da87  mov     rax, cs:WPP_GLOBAL_Control
0x18005da8e  cmp     rax, rbx
0x18005da91  jz      short loc_18005DACF
0x18005da93  test    byte ptr [rax+1Ch], 8
0x18005da97  jz      short loc_18005DACF
0x18005da99  cmp     byte ptr [rax+19h], 2
0x18005da9d  jb      short loc_18005DACF
0x18005da9f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005daa4  lea     edx, [r12+13h]
0x18005daa9  lea     rcx, aPframedirtyba; "pFrameDirtyBA"
0x18005dab0  mov     qword ptr [rsp+100h+var_E0], rcx
0x18005dab5  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x18005dabc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dac3  mov     r9d, eax
0x18005dac6  mov     rcx, [rcx+10h]
0x18005daca  call    WPP_SF_Ds
0x18005dacf  mov     r12, qword ptr [rbp+57h+var_C0]
0x18005dad3  mov     rcx, [r12+70h]
0x18005dad8  mov     rax, [rcx]
0x18005dadb  mov     rax, [rax+70h]
0x18005dadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dae4  mov     rcx, [r12+28h]; struct IRDPPerfCounterGeneric *
0x18005dae9  mov     r8d, 1; unsigned int
0x18005daef  mov     edx, eax; unsigned int
0x18005daf1  call    ?PerfCounterSetRdpIntervalMarker@@YAJPEAUIRDPPerfCounterGeneric@@II@Z; PerfCounterSetRdpIntervalMarker(IRDPPerfCounterGeneric *,uint,uint)
0x18005daf6  lea     rcx, [rbp+57h+var_9C+4]
0x18005dafa  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18005daff  lea     rcx, [rbp+57h+var_90]
0x18005db03  call    ?SafeRelease@?$TCntPtr@VCFakeGfxProvider@@@@AEAAXXZ; TCntPtr<CFakeGfxProvider>::SafeRelease(void)
0x18005db08  mov     rcx, [rbp+57h+var_88]
0x18005db0c  test    rcx, rcx
0x18005db0f  jz      short loc_18005DB1D
0x18005db11  mov     rax, [rcx]
0x18005db14  mov     rax, [rax+10h]
0x18005db18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db1d  mov     eax, esi
0x18005db1f  mov     rcx, [rbp+57h+var_40]
0x18005db23  xor     rcx, rsp; StackCookie
0x18005db26  call    __security_check_cookie
0x18005db2b  mov     rbx, [rsp+100h+arg_18]
0x18005db33  add     rsp, 0D0h
0x18005db3a  pop     r15
0x18005db3c  pop     r14
0x18005db3e  pop     r13
0x18005db40  pop     r12
0x18005db42  pop     rdi
0x18005db43  pop     rsi
0x18005db44  pop     rbp
0x18005db45  retn
0x18005db46  mov     r14, [r15+98h]
0x18005db4d  test    r14, r14
0x18005db50  jnz     short loc_18005DBAC
0x18005db52  mov     esi, 80004003h
0x18005db57  lea     rdx, aRdpcachemanerr_1; "RdpCacheManError_ProcessSurfaceGetSurfa"...
0x18005db5e  mov     r9d, esi; unsigned int
0x18005db61  lea     rcx, aIidIrdpcachema; "IID_IRdpCacheMan"
0x18005db68  mov     r8d, 14Dh; char *
0x18005db6e  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18005db73  mov     rax, cs:WPP_GLOBAL_Control
0x18005db7a  cmp     rax, rbx
0x18005db7d  jz      loc_18005DACF
0x18005db83  test    byte ptr [rax+1Ch], 8
0x18005db87  jz      loc_18005DACF
0x18005db8d  cmp     byte ptr [rax+19h], 2
0x18005db91  jb      loc_18005DACF
0x18005db97  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005db9c  lea     edx, [r14+14h]
0x18005dba0  lea     rcx, aPencodingba; "pEncodingBA"
0x18005dba7  jmp     loc_18005DAB0
0x18005dbac  mov     rcx, [rdi+70h]
0x18005dbb0  mov     rax, [rcx]
0x18005dbb3  mov     rax, [rax+90h]
0x18005dbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dbbf  test    eax, eax
0x18005dbc1  jz      loc_18005DE30
0x18005dbc7  mov     rbx, [r15+668h]
0x18005dbce  mov     [rbp+57h+var_B0], rsi
0x18005dbd2  mov     [rbp+57h+var_B8], rsi
0x18005dbd6  mov     qword ptr [rbp+57h+var_A8], rsi
0x18005dbda  test    rbx, rbx
0x18005dbdd  jz      loc_18005DEA6
0x18005dbe3  lea     rcx, [rbp+57h+var_B0]
0x18005dbe7  call    ?SafeRelease@?$TCntPtr@VCFakeGfxProvider@@@@AEAAXXZ; TCntPtr<CFakeGfxProvider>::SafeRelease(void)
0x18005dbec  lea     rcx, [rbp+57h+var_B0]
0x18005dbf0  mov     [rbp+57h+var_B0], rbx
0x18005dbf4  call    ?SafeAddRef@?$TCntPtr@VPipePrimitive@@@@AEAAXXZ; TCntPtr<PipePrimitive>::SafeAddRef(void)
0x18005dbf9  mov     rdx, [rbx+30h]
0x18005dbfd  lea     rcx, [rbp+57h+var_B8]
0x18005dc01  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18005dc06  mov     rdi, [rbp+57h+var_B8]
0x18005dc0a  test    rdi, rdi
0x18005dc0d  jnz     short loc_18005DC83
0x18005dc0f  mov     rax, cs:WPP_GLOBAL_Control
0x18005dc16  lea     rdi, WPP_GLOBAL_Control
0x18005dc1d  cmp     rax, rdi
0x18005dc20  jz      short loc_18005DC5E
0x18005dc22  test    byte ptr [rax+1Ch], 8
0x18005dc26  jz      short loc_18005DC5E
0x18005dc28  cmp     byte ptr [rax+19h], 2
0x18005dc2c  jb      short loc_18005DC5E
0x18005dc2e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005dc33  mov     edx, 16h
0x18005dc38  lea     rcx, aSpmmrhintba; "spMMRHintBA"
0x18005dc3f  mov     qword ptr [rsp+100h+var_E0], rcx
0x18005dc44  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x18005dc4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dc52  mov     r9d, eax
0x18005dc55  mov     rcx, [rcx+10h]
0x18005dc59  call    WPP_SF_Ds
0x18005dc5e  mov     esi, 80004003h
0x18005dc63  lea     rcx, [rbp+57h+var_A8]
0x18005dc67  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18005dc6c  lea     rcx, [rbp+57h+var_B8]
0x18005dc70  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18005dc75  lea     rcx, [rbp+57h+var_B0]
0x18005dc79  call    ?SafeRelease@?$TCntPtr@VCFakeGfxProvider@@@@AEAAXXZ; TCntPtr<CFakeGfxProvider>::SafeRelease(void)
0x18005dc7e  jmp     loc_18005DACF
0x18005dc83  mov     rdx, [rbx+40h]
0x18005dc87  lea     rcx, [rbp+57h+var_A8]
0x18005dc8b  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x18005dc90  mov     rbx, qword ptr [rbp+57h+var_A8]
0x18005dc94  test    rbx, rbx
0x18005dc97  jnz     short loc_18005DCCC
0x18005dc99  mov     rax, cs:WPP_GLOBAL_Control
0x18005dca0  lea     rdi, WPP_GLOBAL_Control
0x18005dca7  cmp     rax, rdi
0x18005dcaa  jz      short loc_18005DC5E
0x18005dcac  test    byte ptr [rax+1Ch], 8
0x18005dcb0  jz      short loc_18005DC5E
0x18005dcb2  cmp     byte ptr [rax+19h], 2
0x18005dcb6  jb      short loc_18005DC5E
0x18005dcb8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005dcbd  lea     edx, [rbx+17h]
0x18005dcc0  lea     rcx, aSpmmrencodingb; "spMMREncodingBA"
0x18005dcc7  jmp     loc_18005DC3F
0x18005dccc  mov     rax, [rdi]
0x18005dccf  mov     rcx, rdi
0x18005dcd2  mov     rax, [rax+88h]
0x18005dcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dcde  test    eax, eax
0x18005dce0  jnz     loc_18005DE11
0x18005dce6  mov     rax, [rbx]
0x18005dce9  mov     rdx, rdi
0x18005dcec  mov     rcx, rbx
0x18005dcef  mov     rax, [rax+30h]
0x18005dcf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dcf8  mov     esi, eax
0x18005dcfa  test    eax, eax
0x18005dcfc  jns     short loc_18005DD62
0x18005dcfe  mov     rax, cs:WPP_GLOBAL_Control
0x18005dd05  lea     rdi, WPP_GLOBAL_Control
0x18005dd0c  cmp     rax, rdi
0x18005dd0f  jz      loc_18005DC63
0x18005dd15  test    byte ptr [rax+1Ch], 8
0x18005dd19  jz      loc_18005DC63
0x18005dd1f  cmp     byte ptr [rax+19h], 2
0x18005dd23  jb      loc_18005DC63
0x18005dd29  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005dd2e  mov     edx, 18h
0x18005dd33  lea     rcx, aAddmmrbaToMmre; "AddMMRBA to mmrEncodingBA failed!"
0x18005dd3a  mov     dword ptr [rsp+100h+var_D8], esi
0x18005dd3e  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x18005dd45  mov     qword ptr [rsp+100h+var_E0], rcx
0x18005dd4a  mov     r9d, eax
0x18005dd4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dd54  mov     rcx, [rcx+10h]
0x18005dd58  call    WPP_SF_DsD
0x18005dd5d  jmp     loc_18005DC63
0x18005dd62  mov     rax, [rbx]
0x18005dd65  mov     rdx, r14
0x18005dd68  mov     rcx, rbx
0x18005dd6b  mov     rax, [rax+40h]
0x18005dd6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dd74  mov     esi, eax
0x18005dd76  test    eax, eax
0x18005dd78  jns     short loc_18005DDB8
0x18005dd7a  mov     rax, cs:WPP_GLOBAL_Control
0x18005dd81  lea     rdi, WPP_GLOBAL_Control
0x18005dd88  cmp     rax, rdi
0x18005dd8b  jz      loc_18005DC63
0x18005dd91  test    byte ptr [rax+1Ch], 8
0x18005dd95  jz      loc_18005DC63
0x18005dd9b  cmp     byte ptr [rax+19h], 2
0x18005dd9f  jb      loc_18005DC63
0x18005dda5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005ddaa  mov     edx, 19h
0x18005ddaf  lea     rcx, aIntersectMmren; "Intersect mmrEncodingBA with encodingBA"...
0x18005ddb6  jmp     short loc_18005DD3A
0x18005ddb8  mov     rax, [r14]
0x18005ddbb  mov     rdx, rdi
0x18005ddbe  mov     rcx, r14
0x18005ddc1  mov     rax, [rax+38h]
0x18005ddc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ddca  mov     esi, eax
0x18005ddcc  test    eax, eax
0x18005ddce  jns     short loc_18005DE11
0x18005ddd0  mov     rax, cs:WPP_GLOBAL_Control
0x18005ddd7  lea     rdi, WPP_GLOBAL_Control
0x18005ddde  cmp     rax, rdi
0x18005dde1  jz      loc_18005DC63
0x18005dde7  test    byte ptr [rax+1Ch], 8
0x18005ddeb  jz      loc_18005DC63
0x18005ddf1  cmp     byte ptr [rax+19h], 2
0x18005ddf5  jb      loc_18005DC63
0x18005ddfb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005de00  mov     edx, 1Ah
0x18005de05  lea     rcx, aRemovemmrbaOnM; "RemoveMMRBA on m_spClassifyBA failed!"
0x18005de0c  jmp     loc_18005DD3A
0x18005de11  lea     rcx, [rbp+57h+var_A8]
0x18005de15  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18005de1a  lea     rcx, [rbp+57h+var_B8]
0x18005de1e  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18005de23  lea     rcx, [rbp+57h+var_B0]
0x18005de27  call    ?SafeRelease@?$TCntPtr@VCFakeGfxProvider@@@@AEAAXXZ; TCntPtr<CFakeGfxProvider>::SafeRelease(void)
0x18005de2c  mov     rdi, qword ptr [rbp+57h+var_C0]
0x18005de30  mov     rax, [r15+0B0h]
0x18005de37  mov     [rbp+57h+var_78], rax
0x18005de3b  test    rax, rax
0x18005de3e  jnz     loc_18005DEE7
0x18005de44  mov     esi, 80004003h
0x18005de49  lea     rdx, aRdpcachemanerr_1; "RdpCacheManError_ProcessSurfaceGetSurfa"...
0x18005de50  mov     r9d, esi; unsigned int
0x18005de53  lea     rcx, aIidIrdpcachema; "IID_IRdpCacheMan"
0x18005de5a  mov     r8d, 16Eh; char *
0x18005de60  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18005de65  mov     rax, cs:WPP_GLOBAL_Control
0x18005de6c  lea     rdi, WPP_GLOBAL_Control
0x18005de73  cmp     rax, rdi
0x18005de76  jz      loc_18005DACF
  ... truncated ...
```
