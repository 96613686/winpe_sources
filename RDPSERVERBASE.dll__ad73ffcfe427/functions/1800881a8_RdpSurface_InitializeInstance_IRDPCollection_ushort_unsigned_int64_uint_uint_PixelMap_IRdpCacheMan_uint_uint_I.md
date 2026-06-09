# RdpSurface::InitializeInstance(IRDPCollection *,ushort,unsigned __int64,uint,uint,PixelMap *,IRdpCacheMan *,uint,uint,IRdpGFXSourceUpdateContext *,IRdpSurfaceManager *)

- ea: `0x1800881a8`
- end: `0x180088e1b`
- name: `?InitializeInstance@RdpSurface@@AEAAJPEAUIRDPCollection@@G_KIIPEAVPixelMap@@PEAVIRdpCacheMan@@IIPEAUIRdpGFXSourceUpdateContext@@PEAVIRdpSurfaceManager@@@Z`
- size: `3187`
- prototype: `__int64 __fastcall(RdpSurface *this, struct IRDPCollection *, __int16, __int64, unsigned int, unsigned int, struct PixelMap *, struct IRdpCacheMan *, unsigned int, unsigned int, struct IRdpGFXSourceUpdateContext *, struct IRdpSurfaceManager *)`
- caller_count: `2`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180086f20`
- `0x180087340`

## callees

- `0x18000cdac`
- `0x18000cddc`
- `0x18000ce04`
- `0x18000ce34`
- `0x18000f660`
- `0x18002d8f4`
- `0x180076090`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x18007a404`
- `0x18007a664`
- `0x18007cdf0`
- `0x18007ceb8`
- `0x18007f6b0`
- `0x180085c94`
- `0x180085d0c`
- `0x180085da8`
- `0x180086e3c`
- `0x180087fd4`
- `0x1800881a8`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180088832`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180088861`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180088832`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x180088861`

## string_xrefs

- `0x180088311`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x180088387`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x1800883fd`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x180088473`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x1800884e9`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x18008855f`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x1800885d5`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x18008864b`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x1800886c1`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x180088737`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x1800887ad`: `RdpSurfaceError_InitInstanceCreateBAsFail`
- `0x180088363`: `failed to create encoding BA`
- `0x1800883d9`: `failed to create update BA`
- `0x18008844f`: `failed to create spoil BA`
- `0x1800884c5`: `failed to create IntraframeCachehit BA`
- `0x18008853b`: `failed to create Deferred BA`
- `0x1800885b1`: `failed to create PreClassifierProcUpdated BA`
- `0x180088627`: `failed to create NextFrame SpoilBA`
- `0x18008869d`: `failed to create InvalidGrid BA`
- `0x180088713`: `failed to create primitive BA`
- `0x180088789`: `failed to create frameDirty BA`
- `0x1800887ff`: `failed to create Current FrameDirty BA`
- `0x180088cd9`: `IRdpCacheMan::AllocateSurfaceContext failed`

## pseudocode

```c
__int64 __fastcall RdpSurface::InitializeInstance(
        RdpSurface *this,
        struct IRDPCollection *a2,
        __int16 a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        struct PixelMap *a7,
        struct IRdpCacheMan *a8,
        unsigned int a9,
        unsigned int a10,
        struct IRdpGFXSourceUpdateContext *a11,
        struct IRdpSurfaceManager *a12)
{
  unsigned int GenericCounter; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int BA; // eax
  unsigned int v19; // eax
  signed int v20; // eax
  unsigned int v21; // eax
  signed int v22; // eax
  unsigned int v23; // eax
  signed int v24; // eax
  unsigned int v25; // eax
  signed int v26; // eax
  unsigned int v27; // eax
  signed int v28; // eax
  unsigned int v29; // eax
  signed int v30; // eax
  unsigned int v31; // eax
  signed int v32; // eax
  unsigned int v33; // eax
  signed int v34; // eax
  unsigned int v35; // eax
  signed int v36; // eax
  unsigned int v37; // eax
  signed int v38; // eax
  unsigned int v39; // eax
  ImageHintManager *v40; // rax
  ImageHintManager *v41; // rsi
  ImageHintManager **v42; // rbx
  unsigned int v43; // eax
  int v44; // edx
  const char *v45; // rcx
  signed int v46; // eax
  unsigned int v47; // eax
  MMRHintManager *v48; // rax
  MMRHintManager *v49; // rsi
  MMRHintManager **v50; // rbx
  signed int v51; // eax
  unsigned int v52; // eax
  MotionVectorList *v53; // rax
  MotionVectorList *v54; // rsi
  MotionVectorList **v55; // rbx
  signed int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // eax
  signed int v59; // eax
  unsigned int v60; // eax
  char *v61; // rdx
  __int64 v62; // r8
  unsigned int v63; // eax
  int v65; // [rsp+20h] [rbp-78h]

  if ( !(unsigned int)CTSCriticalSection::Initialize((RdpSurface *)((char *)this + 360)) )
  {
    GenericCounter = -2147024882;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceInitLockFail",
      (char *)0x2F7,
      0x8007000E,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"m_csLock.Initialize() failed",
        14);
    }
    return GenericCounter;
  }
  if ( !a5 || !a6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v63 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids, v63);
    }
    GenericCounter = -2147024809;
    v61 = "RdpSurfaceError_InitInstanceInvalidSize";
    v62 = 767;
    goto LABEL_148;
  }
  *((_WORD *)this + 28) = a3;
  if ( a12 != *((struct IRdpSurfaceManager **)this + 8) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 64);
    *((_QWORD *)this + 8) = a12;
    if ( a12 )
      (*(void (__fastcall **)(struct IRdpSurfaceManager *))(*(_QWORD *)a12 + 8LL))(a12);
  }
  *((_DWORD *)this + 108) = a9;
  *((_DWORD *)this + 18) = a5;
  *((_DWORD *)this + 19) = a6;
  *((_QWORD *)this + 78) = a4;
  *((_DWORD *)this + 60) = 0;
  if ( a2 != *((struct IRDPCollection **)this + 11) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 88);
    *((_QWORD *)this + 11) = a2;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 88);
  }
  BA = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 19);
  GenericCounter = BA;
  if ( BA < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x30D,
      BA,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v19,
        (__int64)"failed to create encoding BA",
        GenericCounter);
    }
    return GenericCounter;
  }
  v20 = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 33);
  GenericCounter = v20;
  if ( v20 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x311,
      v20,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v21,
        (__int64)"failed to create update BA",
        GenericCounter);
    }
    return GenericCounter;
  }
  v22 = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 20);
  GenericCounter = v22;
  if ( v22 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x315,
      v22,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v23,
        (__int64)"failed to create spoil BA",
        GenericCounter);
    }
    return GenericCounter;
  }
  v24 = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 22);
  GenericCounter = v24;
  if ( v24 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x319,
      v24,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v25,
        (__int64)"failed to create IntraframeCachehit BA",
        GenericCounter);
    }
    return GenericCounter;
  }
  v26 = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 23);
  GenericCounter = v26;
  if ( v26 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x31D,
      v26,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v27,
        (__int64)"failed to create Deferred BA",
        GenericCounter);
    }
    return GenericCounter;
  }
  v28 = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 24);
  GenericCounter = v28;
  if ( v28 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x321,
      v28,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v29,
        (__int64)"failed to create PreClassifierProcUpdated BA",
        GenericCounter);
    }
    return GenericCounter;
  }
  v30 = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 21);
  GenericCounter = v30;
  if ( v30 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x325,
      v30,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v31,
        (__int64)"failed to create NextFrame SpoilBA",
        GenericCounter);
    }
    return GenericCounter;
  }
  v32 = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 39);
  GenericCounter = v32;
  if ( v32 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x329,
      v32,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v33,
        (__int64)"failed to create InvalidGrid BA",
        GenericCounter);
    }
    return GenericCounter;
  }
  v34 = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 34);
  GenericCounter = v34;
  if ( v34 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x32D,
      v34,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v35 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v35,
        (__int64)"failed to create primitive BA",
        GenericCounter);
    }
    return GenericCounter;
  }
  v36 = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 35);
  GenericCounter = v36;
  if ( v36 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x331,
      v36,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v37 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v37,
        (__int64)"failed to create frameDirty BA",
        GenericCounter);
    }
    return GenericCounter;
  }
  v38 = RdpSurface::CreateBA(this, (struct IRdpBoundsAccumulator **)this + 36);
  GenericCounter = v38;
  if ( v38 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceCreateBAsFail",
      (char *)0x335,
      v38,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v39,
        (__int64)"failed to create Current FrameDirty BA",
        GenericCounter);
    }
    return GenericCounter;
  }
  GenericCounter = RDPAPI_GetGenericCounter(
                     L"RDV::RDP::GraphicsPipeline::ProcessorActiveGridStart",
                     0xFFFFFFFFLL,
                     0xFFFFFFFFLL,
                     0xFFFFFFFFLL,
                     4,
                     (char *)this + 344);
  if ( (GenericCounter & 0x80000000) != 0 )
    return GenericCounter;
  GenericCounter = RDPAPI_GetGenericCounter(
                     L"RDV::RDP::GraphicsPipeline::ProcessorActiveGridEnd",
                     0xFFFFFFFFLL,
                     0xFFFFFFFFLL,
                     0xFFFFFFFFLL,
                     4,
                     (char *)this + 352);
  if ( (GenericCounter & 0x80000000) != 0 )
    return GenericCounter;
  v40 = (ImageHintManager *)operator new(0x200u);
  if ( v40 )
    v41 = ImageHintManager::ImageHintManager(v40, a10);
  else
    v41 = 0;
  v42 = (ImageHintManager **)((char *)this + 1632);
  if ( v41 != *((ImageHintManager **)this + 204) )
  {
    TCntPtr<CFakeGfxProvider>::SafeRelease((char *)this + 1632);
    *v42 = v41;
    TCntPtr<PipePrimitive>::SafeAddRef((char *)this + 1632);
  }
  if ( !*v42 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024882;
    }
    v43 = RdpWppGetCurrentThreadActivityIdPrefix();
    v44 = 67;
    v45 = "ImageHintManager";
LABEL_81:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v44,
      (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
      v43,
      (__int64)v45);
    return (unsigned int)-2147024882;
  }
  v46 = ImageHintManager::InitializeInstance(*v42);
  GenericCounter = v46;
  if ( v46 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceImageHintManagerFail",
      (char *)0x33F,
      v46,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v47 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v47,
        (__int64)"failed to initialize instance of ImageHintManager",
        GenericCounter);
    }
    return GenericCounter;
  }
  v48 = (MMRHintManager *)operator new(0x218u);
  if ( v48 )
    v49 = MMRHintManager::MMRHintManager(v48);
  else
    v49 = 0;
  v50 = (MMRHintManager **)((char *)this + 1640);
  if ( v49 != *((MMRHintManager **)this + 205) )
  {
    TCntPtr<CFakeGfxProvider>::SafeRelease((char *)this + 1640);
    *v50 = v49;
    TCntPtr<PipePrimitive>::SafeAddRef((char *)this + 1640);
  }
  if ( !*v50 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024882;
    }
    v43 = RdpWppGetCurrentThreadActivityIdPrefix();
    v44 = 69;
    v45 = "MMRHintManager";
    goto LABEL_81;
  }
  v51 = MMRHintManager::InitializeInstance(*v50);
  GenericCounter = v51;
  if ( v51 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceMMRHintManagerFail",
      (char *)0x346,
      v51,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v52 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v52,
        (__int64)"failed to initialize instance of MMRHintManager",
        GenericCounter);
    }
    return GenericCounter;
  }
  v53 = (MotionVectorList *)operator new(0x1F8u);
  if ( v53 )
    v54 = MotionVectorList::MotionVectorList(v53);
  else
    v54 = 0;
  v55 = (MotionVectorList **)((char *)this + 1624);
  if ( v54 != *((MotionVectorList **)this + 203) )
  {
    TCntPtr<CFakeGfxProvider>::SafeRelease((char *)this + 1624);
    *v55 = v54;
    TCntPtr<PipePrimitive>::SafeAddRef((char *)this + 1624);
  }
  if ( !*v55 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024882;
    }
    v43 = RdpWppGetCurrentThreadActivityIdPrefix();
    v44 = 71;
    v45 = "MotionVectorList";
    goto LABEL_81;
  }
  v56 = MotionVectorList::InitializeInstance(*v55);
  GenericCounter = v56;
  if ( v56 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceMotionVectorListFail",
      (char *)0x34D,
      v56,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v57 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v57,
        (__int64)"failed to initialize instance of MotionVectorList",
        GenericCounter);
    }
    return GenericCounter;
  }
  if ( !a7 )
  {
    if ( a11 )
      goto LABEL_125;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids);
    }
    GenericCounter = -2147418113;
    v61 = "RdpSurfaceError_InitInstanceNoSrfProvided";
    v62 = 872;
LABEL_148:
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      v61,
      (char *)v62,
      GenericCounter,
      v65);
    return GenericCounter;
  }
  if ( !(unsigned __int8)PixelMap::AttachInternal(
                           (RdpSurface *)((char *)this + 112),
                           *((_DWORD *)a7 + 1),
                           *((_DWORD *)a7 + 2),
                           *((_DWORD *)a7 + 3),
                           0,
                           0,
                           *(_DWORD *)a7,
                           *((_DWORD *)a7 + 1)) )
  {
    GenericCounter = -2147024809;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstancePixelMapAttachFail",
      (char *)0x35B,
      0x80070057,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v58 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v58,
        -2147024809);
    }
    return GenericCounter;
  }
LABEL_125:
  if ( a8
    && (v59 = (*(__int64 (__fastcall **)(struct IRdpCacheMan *, _QWORD, _QWORD, char *))(*(_QWORD *)a8 + 24LL))(
                a8,
                a5,
                a6,
                (char *)this + 296),
        GenericCounter = v59,
        v59 < 0) )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpSurface",
      "RdpSurfaceError_InitInstanceAllocateSrfCtxFail",
      (char *)0x372,
      v59,
      v65);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v60 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids,
        v60,
        (__int64)"IRdpCacheMan::AllocateSurfaceContext failed",
        GenericCounter);
    }
  }
  else if ( a11 )
  {
    if ( a11 != *((struct IRdpGFXSourceUpdateContext **)this + 42) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 336);
      *((_QWORD *)this + 42) = a11;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 336);
    }
    GenericCounter = (**(__int64 (__fastcall ***)(struct IRdpGFXSourceUpdateContext *, GUID *, char *))a11)(
                       a11,
                       &IID_IRdpGFXSourceCompressionCapableUpdateContext,
                       (char *)this + 328);
    if ( (GenericCounter & 0x80000000) != 0 )
    {
      if ( *((_QWORD *)this + 41) )
      {
        TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 328);
        *((_QWORD *)this + 41) = 0;
      }
      return 0;
    }
  }
  return GenericCounter;
}

```

## disassembly

```asm
0x1800881a8  push    rbx
0x1800881aa  push    rbp
0x1800881ab  push    rsi
0x1800881ac  push    rdi
0x1800881ad  push    r12
0x1800881af  push    r14
0x1800881b1  push    r15
0x1800881b3  sub     rsp, 60h
0x1800881b7  mov     rdi, rcx
0x1800881ba  mov     r14, r9
0x1800881bd  add     rcx, 168h; this
0x1800881c4  movzx   ebx, r8w
0x1800881c8  mov     rbp, rdx
0x1800881cb  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800881d0  test    eax, eax
0x1800881d2  jnz     loc_180088261
0x1800881d8  mov     ebx, 8007000Eh
0x1800881dd  lea     rdx, aRdpsurfaceerro; "RdpSurfaceError_InitInstanceInitLockFai"...
0x1800881e4  mov     r9d, ebx; unsigned int
0x1800881e7  lea     rcx, aIidIrdpsurface_0; "IID_IRdpSurface"
0x1800881ee  mov     r8d, 2F7h; char *
0x1800881f4  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800881f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180088200  lea     rax, WPP_GLOBAL_Control
0x180088207  cmp     rcx, rax
0x18008820a  jz      loc_180088E0A
0x180088210  test    byte ptr [rcx+1Ch], 8
0x180088214  jz      loc_180088E0A
0x18008821a  cmp     byte ptr [rcx+19h], 2
0x18008821e  jb      loc_180088E0A
0x180088224  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180088229  mov     edx, 36h ; '6'
0x18008822e  mov     [rsp+98h+var_70], 8007000Eh
0x180088236  lea     rcx, aMCslockInitial; "m_csLock.Initialize() failed"
0x18008823d  mov     qword ptr [rsp+98h+var_78], rcx
0x180088242  lea     r8, WPP_8030014fd9d93604a44c247aa0ba509b_Traceguids
0x180088249  mov     rcx, cs:WPP_GLOBAL_Control
0x180088250  mov     r9d, eax
0x180088253  mov     rcx, [rcx+10h]
0x180088257  call    WPP_SF_DsD
0x18008825c  jmp     loc_180088E0A
0x180088261  mov     r15d, [rsp+98h+arg_20]
0x180088269  test    r15d, r15d
0x18008826c  jz      loc_180088DA3
0x180088272  mov     r12d, [rsp+98h+arg_28]
0x18008827a  test    r12d, r12d
0x18008827d  jz      loc_180088DA3
0x180088283  mov     [rdi+38h], bx
0x180088287  lea     rsi, [rdi+40h]
0x18008828b  mov     rbx, [rsp+98h+arg_58]
0x180088293  cmp     rbx, [rsi]
0x180088296  jz      short loc_1800882B7
0x180088298  mov     rcx, rsi
0x18008829b  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800882a0  mov     [rsi], rbx
0x1800882a3  test    rbx, rbx
0x1800882a6  jz      short loc_1800882B7
0x1800882a8  mov     rax, [rbx]
0x1800882ab  mov     rcx, rbx
0x1800882ae  mov     rax, [rax+8]
0x1800882b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800882b7  mov     eax, [rsp+98h+arg_40]
0x1800882be  lea     rbx, [rdi+58h]
0x1800882c2  mov     [rdi+1B0h], eax
0x1800882c8  mov     [rdi+48h], r15d
0x1800882cc  mov     [rdi+4Ch], r12d
0x1800882d0  mov     [rdi+270h], r14
0x1800882d7  mov     dword ptr [rdi+0F0h], 0
0x1800882e1  cmp     rbp, [rbx]
0x1800882e4  jz      short loc_1800882F9
0x1800882e6  mov     rcx, rbx
0x1800882e9  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800882ee  mov     rcx, rbx
0x1800882f1  mov     [rbx], rbp
0x1800882f4  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800882f9  lea     rdx, [rdi+98h]; struct IRdpBoundsAccumulator **
0x180088300  mov     rcx, rdi; this
0x180088303  call    ?CreateBA@RdpSurface@@QEAAJPEAPEAVIRdpBoundsAccumulator@@@Z; RdpSurface::CreateBA(IRdpBoundsAccumulator * *)
0x180088308  mov     ebx, eax
0x18008830a  test    eax, eax
0x18008830c  jns     short loc_18008836F
0x18008830e  mov     r9d, eax; unsigned int
0x180088311  lea     rdx, aRdpsurfaceerro_24; "RdpSurfaceError_InitInstanceCreateBAsFa"...
0x180088318  mov     r8d, 30Dh; char *
0x18008831e  lea     rcx, aIidIrdpsurface_0; "IID_IRdpSurface"
0x180088325  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008832a  mov     rcx, cs:WPP_GLOBAL_Control
0x180088331  lea     rax, WPP_GLOBAL_Control
0x180088338  cmp     rcx, rax
0x18008833b  jz      loc_180088E0A
0x180088341  test    byte ptr [rcx+1Ch], 8
0x180088345  jz      loc_180088E0A
0x18008834b  cmp     byte ptr [rcx+19h], 2
0x18008834f  jb      loc_180088E0A
0x180088355  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008835a  mov     edx, 38h ; '8'
0x18008835f  mov     [rsp+98h+var_70], ebx
0x180088363  lea     rcx, aFailedToCreate_71; "failed to create encoding BA"
0x18008836a  jmp     loc_18008823D
0x18008836f  lea     rdx, [rdi+108h]; struct IRdpBoundsAccumulator **
0x180088376  mov     rcx, rdi; this
0x180088379  call    ?CreateBA@RdpSurface@@QEAAJPEAPEAVIRdpBoundsAccumulator@@@Z; RdpSurface::CreateBA(IRdpBoundsAccumulator * *)
0x18008837e  mov     ebx, eax
0x180088380  test    eax, eax
0x180088382  jns     short loc_1800883E5
0x180088384  mov     r9d, eax; unsigned int
0x180088387  lea     rdx, aRdpsurfaceerro_24; "RdpSurfaceError_InitInstanceCreateBAsFa"...
0x18008838e  mov     r8d, 311h; char *
0x180088394  lea     rcx, aIidIrdpsurface_0; "IID_IRdpSurface"
0x18008839b  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800883a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800883a7  lea     rax, WPP_GLOBAL_Control
0x1800883ae  cmp     rcx, rax
0x1800883b1  jz      loc_180088E0A
0x1800883b7  test    byte ptr [rcx+1Ch], 8
0x1800883bb  jz      loc_180088E0A
0x1800883c1  cmp     byte ptr [rcx+19h], 2
0x1800883c5  jb      loc_180088E0A
0x1800883cb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800883d0  mov     edx, 39h ; '9'
0x1800883d5  mov     [rsp+98h+var_70], ebx
0x1800883d9  lea     rcx, aFailedToCreate_35; "failed to create update BA"
0x1800883e0  jmp     loc_18008823D
0x1800883e5  lea     rdx, [rdi+0A0h]; struct IRdpBoundsAccumulator **
0x1800883ec  mov     rcx, rdi; this
0x1800883ef  call    ?CreateBA@RdpSurface@@QEAAJPEAPEAVIRdpBoundsAccumulator@@@Z; RdpSurface::CreateBA(IRdpBoundsAccumulator * *)
0x1800883f4  mov     ebx, eax
0x1800883f6  test    eax, eax
0x1800883f8  jns     short loc_18008845B
0x1800883fa  mov     r9d, eax; unsigned int
0x1800883fd  lea     rdx, aRdpsurfaceerro_24; "RdpSurfaceError_InitInstanceCreateBAsFa"...
0x180088404  mov     r8d, 315h; char *
0x18008840a  lea     rcx, aIidIrdpsurface_0; "IID_IRdpSurface"
0x180088411  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180088416  mov     rcx, cs:WPP_GLOBAL_Control
0x18008841d  lea     rax, WPP_GLOBAL_Control
0x180088424  cmp     rcx, rax
0x180088427  jz      loc_180088E0A
0x18008842d  test    byte ptr [rcx+1Ch], 8
0x180088431  jz      loc_180088E0A
0x180088437  cmp     byte ptr [rcx+19h], 2
0x18008843b  jb      loc_180088E0A
0x180088441  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180088446  mov     edx, 3Ah ; ':'
0x18008844b  mov     [rsp+98h+var_70], ebx
0x18008844f  lea     rcx, aFailedToCreate_63; "failed to create spoil BA"
0x180088456  jmp     loc_18008823D
0x18008845b  lea     rdx, [rdi+0B0h]; struct IRdpBoundsAccumulator **
0x180088462  mov     rcx, rdi; this
0x180088465  call    ?CreateBA@RdpSurface@@QEAAJPEAPEAVIRdpBoundsAccumulator@@@Z; RdpSurface::CreateBA(IRdpBoundsAccumulator * *)
0x18008846a  mov     ebx, eax
0x18008846c  test    eax, eax
0x18008846e  jns     short loc_1800884D1
0x180088470  mov     r9d, eax; unsigned int
0x180088473  lea     rdx, aRdpsurfaceerro_24; "RdpSurfaceError_InitInstanceCreateBAsFa"...
0x18008847a  mov     r8d, 319h; char *
0x180088480  lea     rcx, aIidIrdpsurface_0; "IID_IRdpSurface"
0x180088487  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008848c  mov     rcx, cs:WPP_GLOBAL_Control
0x180088493  lea     rax, WPP_GLOBAL_Control
0x18008849a  cmp     rcx, rax
0x18008849d  jz      loc_180088E0A
0x1800884a3  test    byte ptr [rcx+1Ch], 8
0x1800884a7  jz      loc_180088E0A
0x1800884ad  cmp     byte ptr [rcx+19h], 2
0x1800884b1  jb      loc_180088E0A
0x1800884b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800884bc  mov     edx, 3Bh ; ';'
0x1800884c1  mov     [rsp+98h+var_70], ebx
0x1800884c5  lea     rcx, aFailedToCreate_46; "failed to create IntraframeCachehit BA"
0x1800884cc  jmp     loc_18008823D
0x1800884d1  lea     rdx, [rdi+0B8h]; struct IRdpBoundsAccumulator **
0x1800884d8  mov     rcx, rdi; this
0x1800884db  call    ?CreateBA@RdpSurface@@QEAAJPEAPEAVIRdpBoundsAccumulator@@@Z; RdpSurface::CreateBA(IRdpBoundsAccumulator * *)
0x1800884e0  mov     ebx, eax
0x1800884e2  test    eax, eax
0x1800884e4  jns     short loc_180088547
0x1800884e6  mov     r9d, eax; unsigned int
0x1800884e9  lea     rdx, aRdpsurfaceerro_24; "RdpSurfaceError_InitInstanceCreateBAsFa"...
0x1800884f0  mov     r8d, 31Dh; char *
0x1800884f6  lea     rcx, aIidIrdpsurface_0; "IID_IRdpSurface"
0x1800884fd  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180088502  mov     rcx, cs:WPP_GLOBAL_Control
0x180088509  lea     rax, WPP_GLOBAL_Control
0x180088510  cmp     rcx, rax
0x180088513  jz      loc_180088E0A
0x180088519  test    byte ptr [rcx+1Ch], 8
0x18008851d  jz      loc_180088E0A
0x180088523  cmp     byte ptr [rcx+19h], 2
0x180088527  jb      loc_180088E0A
0x18008852d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180088532  mov     edx, 3Ch ; '<'
0x180088537  mov     [rsp+98h+var_70], ebx
0x18008853b  lea     rcx, aFailedToCreate_107; "failed to create Deferred BA"
0x180088542  jmp     loc_18008823D
0x180088547  lea     rdx, [rdi+0C0h]; struct IRdpBoundsAccumulator **
0x18008854e  mov     rcx, rdi; this
0x180088551  call    ?CreateBA@RdpSurface@@QEAAJPEAPEAVIRdpBoundsAccumulator@@@Z; RdpSurface::CreateBA(IRdpBoundsAccumulator * *)
0x180088556  mov     ebx, eax
0x180088558  test    eax, eax
0x18008855a  jns     short loc_1800885BD
0x18008855c  mov     r9d, eax; unsigned int
0x18008855f  lea     rdx, aRdpsurfaceerro_24; "RdpSurfaceError_InitInstanceCreateBAsFa"...
0x180088566  mov     r8d, 321h; char *
0x18008856c  lea     rcx, aIidIrdpsurface_0; "IID_IRdpSurface"
0x180088573  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180088578  mov     rcx, cs:WPP_GLOBAL_Control
0x18008857f  lea     rax, WPP_GLOBAL_Control
0x180088586  cmp     rcx, rax
0x180088589  jz      loc_180088E0A
0x18008858f  test    byte ptr [rcx+1Ch], 8
0x180088593  jz      loc_180088E0A
0x180088599  cmp     byte ptr [rcx+19h], 2
0x18008859d  jb      loc_180088E0A
0x1800885a3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800885a8  mov     edx, 3Dh ; '='
0x1800885ad  mov     [rsp+98h+var_70], ebx
0x1800885b1  lea     rcx, aFailedToCreate_128; "failed to create PreClassifierProcUpdat"...
0x1800885b8  jmp     loc_18008823D
0x1800885bd  lea     rdx, [rdi+0A8h]; struct IRdpBoundsAccumulator **
0x1800885c4  mov     rcx, rdi; this
0x1800885c7  call    ?CreateBA@RdpSurface@@QEAAJPEAPEAVIRdpBoundsAccumulator@@@Z; RdpSurface::CreateBA(IRdpBoundsAccumulator * *)
0x1800885cc  mov     ebx, eax
0x1800885ce  test    eax, eax
0x1800885d0  jns     short loc_180088633
0x1800885d2  mov     r9d, eax; unsigned int
0x1800885d5  lea     rdx, aRdpsurfaceerro_24; "RdpSurfaceError_InitInstanceCreateBAsFa"...
0x1800885dc  mov     r8d, 325h; char *
0x1800885e2  lea     rcx, aIidIrdpsurface_0; "IID_IRdpSurface"
0x1800885e9  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800885ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800885f5  lea     rax, WPP_GLOBAL_Control
0x1800885fc  cmp     rcx, rax
0x1800885ff  jz      loc_180088E0A
0x180088605  test    byte ptr [rcx+1Ch], 8
0x180088609  jz      loc_180088E0A
0x18008860f  cmp     byte ptr [rcx+19h], 2
0x180088613  jb      loc_180088E0A
0x180088619  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008861e  mov     edx, 3Eh ; '>'
0x180088623  mov     [rsp+98h+var_70], ebx
0x180088627  lea     rcx, aFailedToCreate_122; "failed to create NextFrame SpoilBA"
0x18008862e  jmp     loc_18008823D
0x180088633  lea     rdx, [rdi+138h]; struct IRdpBoundsAccumulator **
0x18008863a  mov     rcx, rdi; this
0x18008863d  call    ?CreateBA@RdpSurface@@QEAAJPEAPEAVIRdpBoundsAccumulator@@@Z; RdpSurface::CreateBA(IRdpBoundsAccumulator * *)
0x180088642  mov     ebx, eax
0x180088644  test    eax, eax
0x180088646  jns     short loc_1800886A9
0x180088648  mov     r9d, eax; unsigned int
0x18008864b  lea     rdx, aRdpsurfaceerro_24; "RdpSurfaceError_InitInstanceCreateBAsFa"...
0x180088652  mov     r8d, 329h; char *
0x180088658  lea     rcx, aIidIrdpsurface_0; "IID_IRdpSurface"
0x18008865f  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x180088664  mov     rcx, cs:WPP_GLOBAL_Control
0x18008866b  lea     rax, WPP_GLOBAL_Control
0x180088672  cmp     rcx, rax
0x180088675  jz      loc_180088E0A
0x18008867b  test    byte ptr [rcx+1Ch], 8
0x18008867f  jz      loc_180088E0A
0x180088685  cmp     byte ptr [rcx+19h], 2
0x180088689  jb      loc_180088E0A
0x18008868f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180088694  mov     edx, 3Fh ; '?'
0x180088699  mov     [rsp+98h+var_70], ebx
0x18008869d  lea     rcx, aFailedToCreate_92; "failed to create InvalidGrid BA"
0x1800886a4  jmp     loc_18008823D
0x1800886a9  lea     rdx, [rdi+110h]; struct IRdpBoundsAccumulator **
0x1800886b0  mov     rcx, rdi; this
0x1800886b3  call    ?CreateBA@RdpSurface@@QEAAJPEAPEAVIRdpBoundsAccumulator@@@Z; RdpSurface::CreateBA(IRdpBoundsAccumulator * *)
0x1800886b8  mov     ebx, eax
0x1800886ba  test    eax, eax
0x1800886bc  jns     short loc_18008871F
0x1800886be  mov     r9d, eax; unsigned int
0x1800886c1  lea     rdx, aRdpsurfaceerro_24; "RdpSurfaceError_InitInstanceCreateBAsFa"...
0x1800886c8  mov     r8d, 32Dh; char *
0x1800886ce  lea     rcx, aIidIrdpsurface_0; "IID_IRdpSurface"
0x1800886d5  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800886da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800886e1  lea     rax, WPP_GLOBAL_Control
0x1800886e8  cmp     rcx, rax
0x1800886eb  jz      loc_180088E0A
0x1800886f1  test    byte ptr [rcx+1Ch], 8
0x1800886f5  jz      loc_180088E0A
0x1800886fb  cmp     byte ptr [rcx+19h], 2
0x1800886ff  jb      loc_180088E0A
0x180088705  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008870a  mov     edx, 40h ; '@'
0x18008870f  mov     [rsp+98h+var_70], ebx
0x180088713  lea     rcx, aFailedToCreate_82; "failed to create primitive BA"
0x18008871a  jmp     loc_18008823D
0x18008871f  lea     rdx, [rdi+118h]; struct IRdpBoundsAccumulator **
0x180088726  mov     rcx, rdi; this
0x180088729  call    ?CreateBA@RdpSurface@@QEAAJPEAPEAVIRdpBoundsAccumulator@@@Z; RdpSurface::CreateBA(IRdpBoundsAccumulator * *)
0x18008872e  mov     ebx, eax
0x180088730  test    eax, eax
0x180088732  jns     short loc_180088795
0x180088734  mov     r9d, eax; unsigned int
0x180088737  lea     rdx, aRdpsurfaceerro_24; "RdpSurfaceError_InitInstanceCreateBAsFa"...
0x18008873e  mov     r8d, 331h; char *
  ... truncated ...
```
