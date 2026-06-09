# CMFHardwareVideoBranchLoader::InsertMFT(COutputTopologyPin &,IMFMediaType *,CInputTopologyPin &,IMFMediaType *,IMFTransform *,int)

- ea: `0x1800e8910`
- end: `0x1800e94d2`
- name: `?InsertMFT@CMFHardwareVideoBranchLoader@@IEAAJAEAVCOutputTopologyPin@@PEAUIMFMediaType@@AEAVCInputTopologyPin@@1PEAUIMFTransform@@H@Z`
- size: `3010`
- prototype: `int(CMFHardwareVideoBranchLoader *__hidden this, struct COutputTopologyPin *, struct IMFMediaType *, struct CInputTopologyPin *, struct IMFMediaType *, struct IMFTransform *, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18016df00`
- `0x1802c5684`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x1800483d0`
- `0x18004d118`
- `0x180050d6c`
- `0x180063f00`
- `0x18008967c`
- `0x1800ae158`
- `0x1800ae554`
- `0x1800ae5b8`
- `0x1800e8910`
- `0x1800e9c38`
- `0x1800ec0e0`
- `0x180113a70`
- `0x18014c0fc`
- `0x1801abd9c`
- `0x1801ae910`
- `0x180222470`
- `0x180258480`
- `0x1802c4cb0`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800e8bf5`
- `MFPlat!MFCreateMediaType` at `0x1800e8f58`
- `MFPlat!MFCreateMediaType` at `0x1800e8bf5`
- `MFPlat!MFCreateMediaType` at `0x1800e8f58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e8b66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e8c17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e8ccf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e8d84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e8e85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e908f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e913c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e91d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e926e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e9307`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e93a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e8b66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e8c17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e8ccf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e8d84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e8e85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e908f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e913c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e91d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e926e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e9307`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e93a0`

## pseudocode

```c
__int64 __fastcall CMFHardwareVideoBranchLoader::InsertMFT(
        CTopoConnectorShared **this,
        struct COutputTopologyPin *a2,
        struct IMFMediaType *a3,
        struct IMFTopologyNode **a4,
        struct IMFMediaType *a5,
        struct IUnknown *a6,
        int a7)
{
  int v11; // eax
  struct IMFTopologyNode *v12; // rbx
  HRESULT PossibleType; // edi
  CallStackTracing *v14; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
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
  unsigned int *v37; // r9
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // r15
  unsigned int v44; // r14d
  __int64 v45; // r12
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // rdx
  __int64 *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  __int64 *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  __int64 *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  __int64 *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  IMFMediaType *v78; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v79[8]; // [rsp+38h] [rbp-C8h] BYREF
  struct IMFMediaType *v80; // [rsp+40h] [rbp-C0h] BYREF
  struct IMFMediaType v81; // [rsp+48h] [rbp-B8h] BYREF
  IMFMediaType *ppMFType; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v83[12]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v84[3]; // [rsp+C0h] [rbp-40h] BYREF
  int v85; // [rsp+D8h] [rbp-28h]
  __int64 v86; // [rsp+DCh] [rbp-24h]
  __int64 v87; // [rsp+E8h] [rbp-18h]
  __int64 v88; // [rsp+F0h] [rbp-10h]
  __int64 v89; // [rsp+F8h] [rbp-8h]
  __int16 v90; // [rsp+100h] [rbp+0h]
  _QWORD v91[4]; // [rsp+120h] [rbp+20h] BYREF
  int v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  __int16 v96; // [rsp+160h] [rbp+60h]

  v91[0] = &CTopologyPin::`vftable';
  v78 = 0;
  v84[0] = &CTopologyPin::`vftable';
  ppMFType = 0;
  memset(&v91[1], 0, 24);
  v92 = 0;
  v96 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v84[1] = 0;
  v84[2] = 0;
  v85 = 0;
  v86 = 1;
  v90 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v79, "CMFHardwareVideoBranchLoader::InsertMFT", 304);
  if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, &WPP_84077d43404e382a16b12f731fadc2a0_Traceguids, this, a6);
  v11 = CTopoConnectorShared::AddTransformNode(this[3], a6, 0, (struct IMFTopologyNode **)&v78);
  v12 = (struct IMFTopologyNode *)v78;
  PossibleType = v11;
  if ( v11 < 0 )
  {
    v14 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v14 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != PossibleType )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFHardwareVideoBranchLoader::InsertMFT",
          306,
          PossibleType);
    }
    if ( !g_wppLevels )
      goto LABEL_146;
    v16 = 28;
    goto LABEL_11;
  }
  CTopologyPin::CTopologyPin((CTopologyPin *)v83, this[3], (struct IMFTopologyNode *)v78, 0, 0);
  v83[0] = &CTopologyPin::`vftable';
  CTopologyPin::SetPin((CTopologyPin *)v91, (struct CTopologyPin *)v83);
  CTopologyPin::~CTopologyPin((CTopologyPin *)v83);
  CTopologyPin::CTopologyPin((CTopologyPin *)v83, this[3], v12, 0, 1);
  v83[0] = &CTopologyPin::`vftable';
  CTopologyPin::SetPin((CTopologyPin *)v84, (struct CTopologyPin *)v83);
  CTopologyPin::~CTopologyPin((CTopologyPin *)v83);
  if ( ((unsigned int)IsDXGITranscodeTopology(*((struct IMFTopology **)this[3] + 1)) || *(_QWORD *)this[2]) && !a7 )
  {
    PossibleType = CTopoConnectorShared::SetupD3DManager(this[3], this[2], v12, a4[2]);
    if ( PossibleType < 0 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != PossibleType )
          CallStackContext::TraceFailure(v21, "CMFHardwareVideoBranchLoader::InsertMFT", 315, PossibleType);
      }
      if ( !g_wppLevels )
        goto LABEL_146;
      v16 = 29;
      goto LABEL_11;
    }
  }
  PossibleType = MFCreateMediaType(&ppMFType);
  if ( PossibleType < 0 )
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
      if ( *((_DWORD *)v26 + 499) != PossibleType )
        CallStackContext::TraceFailure(v26, "CMFHardwareVideoBranchLoader::InsertMFT", 318, PossibleType);
    }
    if ( !g_wppLevels )
      goto LABEL_146;
    v16 = 30;
    goto LABEL_11;
  }
  PossibleType = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))a3->lpVtbl->CopyAllItems)(a3, ppMFType);
  if ( PossibleType < 0 )
  {
    v29 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
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
      if ( *((_DWORD *)v31 + 499) != PossibleType )
        CallStackContext::TraceFailure(v31, "CMFHardwareVideoBranchLoader::InsertMFT", 319, PossibleType);
    }
    if ( !g_wppLevels )
      goto LABEL_146;
    v16 = 31;
    goto LABEL_11;
  }
  PossibleType = CTopoConnectorShared::ConnectNodesWithProvidedMediaType(
                   this[3],
                   a2,
                   (struct CInputTopologyPin *)v91,
                   ppMFType);
  if ( PossibleType < 0 )
  {
    v34 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33);
      CallStackTracing::s_wpInstance = v35;
      if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
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
      if ( *((_DWORD *)v36 + 499) != PossibleType )
        CallStackContext::TraceFailure(v36, "CMFHardwareVideoBranchLoader::InsertMFT", 320, PossibleType);
    }
    if ( !g_wppLevels )
      goto LABEL_146;
    v16 = 32;
    goto LABEL_11;
  }
  *((_DWORD *)this + 2) = 1;
  PossibleType = CMFHardwareVideoBranchLoader::ConnectPinsWithMatchedType(
                   (CMFHardwareVideoBranchLoader *)this,
                   (struct COutputTopologyPin *)v84,
                   (struct CInputTopologyPin *)a4);
  if ( PossibleType >= 0 )
    goto LABEL_148;
  v81.lpVtbl = 0;
  if ( (int)MFMEDIATYPEUtils::GetNativeVideoSize(
              (MFMEDIATYPEUtils *)ppMFType,
              &v81,
              (unsigned int *)&v81.lpVtbl + 1,
              v37) >= 0
    || (PossibleType = MFGetAttribute2UINT32asUINT64(ppMFType, &MF_MT_FRAME_SIZE, &v81, (char *)&v81.lpVtbl + 4),
        PossibleType >= 0) )
  {
    LODWORD(v80) = 0;
    LODWORD(v78) = 0;
    MFGetAttribute2UINT32asUINT64(ppMFType, &MF_MT_FRAME_RATE, &v80, &v78);
    v43 = (unsigned int)v80;
    v44 = 0;
    v45 = (unsigned int)v78;
    while ( 1 )
    {
      v80 = 0;
      v78 = 0;
      PossibleType = MFCreateMediaType(&v78);
      if ( PossibleType < 0 )
      {
        v74 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47);
          CallStackTracing::s_wpInstance = v75;
          if ( v75 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
          {
            v74 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v74 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v74 + 8) )
        {
          v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
          if ( *((_DWORD *)v76 + 499) != PossibleType )
            CallStackContext::TraceFailure(v76, "CMFHardwareVideoBranchLoader::InsertMFT", 352, PossibleType);
        }
        if ( g_wppLevels )
        {
          v61 = 34;
          goto LABEL_144;
        }
        goto LABEL_145;
      }
      PossibleType = CTopologyPin::GetPossibleType((CTopologyPin *)v84, v44, &v80);
      if ( PossibleType < 0 )
      {
        v71 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49);
          CallStackTracing::s_wpInstance = v72;
          if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
          {
            v71 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v71 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v71 + 8) )
        {
          v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
          if ( *((_DWORD *)v73 + 499) != PossibleType )
            CallStackContext::TraceFailure(v73, "CMFHardwareVideoBranchLoader::InsertMFT", 353, PossibleType);
        }
        if ( g_wppLevels )
        {
          v61 = 35;
          goto LABEL_144;
        }
        goto LABEL_145;
      }
      PossibleType = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))v80->lpVtbl->CopyAllItems)(
                       v80,
                       v78);
      if ( PossibleType < 0 )
      {
        v68 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51);
          CallStackTracing::s_wpInstance = v69;
          if ( v69 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
          {
            v68 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v68 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v68 + 8) )
        {
          v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
          if ( *((_DWORD *)v70 + 499) != PossibleType )
            CallStackContext::TraceFailure(v70, "CMFHardwareVideoBranchLoader::InsertMFT", 355, PossibleType);
        }
        if ( g_wppLevels )
        {
          v61 = 36;
          goto LABEL_144;
        }
        goto LABEL_145;
      }
      PossibleType = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, unsigned __int64))v78->lpVtbl->SetUINT64)(
                       v78,
                       &MF_MT_FRAME_SIZE,
                       HIDWORD(v81.lpVtbl) | ((unsigned __int64)LODWORD(v81.lpVtbl) << 32));
      if ( PossibleType < 0 )
      {
        v65 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53);
          CallStackTracing::s_wpInstance = v66;
          if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
          {
            v65 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v65 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v65 + 8) )
        {
          v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
          if ( *((_DWORD *)v67 + 499) != PossibleType )
            CallStackContext::TraceFailure(v67, "CMFHardwareVideoBranchLoader::InsertMFT", 356, PossibleType);
        }
        if ( g_wppLevels )
        {
          v61 = 37;
          goto LABEL_144;
        }
        goto LABEL_145;
      }
      if ( (_DWORD)v45 )
      {
        if ( (_DWORD)v43 )
        {
          PossibleType = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))v78->lpVtbl->SetUINT64)(
                           v78,
                           &MF_MT_FRAME_RATE,
                           v45 | (v43 << 32));
          if ( PossibleType < 0 )
            break;
        }
      }
      PossibleType = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))v78->lpVtbl->SetUINT32)(
                       v78,
                       &MF_MT_INTERLACE_MODE,
                       2);
      if ( PossibleType < 0 )
      {
        v62 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57);
          CallStackTracing::s_wpInstance = v63;
          if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
          {
            v62 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v62 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v62 + 8) )
        {
          v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
          if ( *((_DWORD *)v64 + 499) != PossibleType )
            CallStackContext::TraceFailure(v64, "CMFHardwareVideoBranchLoader::InsertMFT", 361, PossibleType);
        }
        if ( g_wppLevels )
        {
          v61 = 39;
          goto LABEL_144;
        }
        goto LABEL_145;
      }
      PossibleType = CTopoConnectorShared::ConnectNodesWithProvidedMediaType(
                       this[3],
                       (struct COutputTopologyPin *)v84,
                       (struct CInputTopologyPin *)a4,
                       v78);
      if ( PossibleType >= 0 )
      {
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v78);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v80);
        goto LABEL_148;
      }
      ++v44;
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v78);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v80);
    }
    v58 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54, v55);
      CallStackTracing::s_wpInstance = v59;
      if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
      {
        v58 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v58 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v58 + 8) )
    {
      v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
      if ( *((_DWORD *)v60 + 499) != PossibleType )
        CallStackContext::TraceFailure(v60, "CMFHardwareVideoBranchLoader::InsertMFT", 359, PossibleType);
    }
    if ( g_wppLevels )
    {
      v61 = 38;
LABEL_144:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v61,
        &WPP_84077d43404e382a16b12f731fadc2a0_Traceguids,
        this,
        PossibleType);
    }
LABEL_145:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v78);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v80);
    goto LABEL_146;
  }
  v40 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39);
    CallStackTracing::s_wpInstance = v41;
    if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
    {
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v40 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v40 + 8) )
  {
    v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
    if ( *((_DWORD *)v42 + 499) != PossibleType )
      CallStackContext::TraceFailure(v42, "CMFHardwareVideoBranchLoader::InsertMFT", 335, PossibleType);
  }
  if ( g_wppLevels )
  {
    v16 = 33;
LABEL_11:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      &WPP_84077d43404e382a16b12f731fadc2a0_Traceguids,
      this,
      PossibleType);
  }
LABEL_146:
  if ( v12 )
    CTopoConnectorShared::RemoveDestNode(this[3], v12);
LABEL_148:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v79);
  CTopologyPin::~CTopologyPin((CTopologyPin *)v84);
  CTopologyPin::~CTopologyPin((CTopologyPin *)v91);
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  if ( v12 )
    ((void (__fastcall *)(struct IMFTopologyNode *))v12->lpVtbl->Release)(v12);
  return (unsigned int)PossibleType;
}

```

## disassembly

```asm
0x1800e8910  push    rbp
0x1800e8912  push    rbx
0x1800e8913  push    rsi
0x1800e8914  push    rdi
0x1800e8915  push    r12
0x1800e8917  push    r13
0x1800e8919  push    r14
0x1800e891b  push    r15
0x1800e891d  lea     rbp, [rsp-98h]
0x1800e8925  sub     rsp, 198h
0x1800e892c  mov     rax, cs:__security_cookie
0x1800e8933  xor     rax, rsp
0x1800e8936  mov     [rbp+0D0h+var_50], rax
0x1800e893d  mov     rbx, [rbp+0D0h+arg_28]
0x1800e8944  lea     rax, ??_7CTopologyPin@@6B@; const CTopologyPin::`vftable'
0x1800e894b  xor     r12d, r12d
0x1800e894e  mov     [rbp+0D0h+var_B0], rax
0x1800e8952  lea     rax, ??_7CTopologyPin@@6B@; const CTopologyPin::`vftable'
0x1800e8959  mov     [rsp+1D0h+var_1A0], r12
0x1800e895e  mov     r14, r8
0x1800e8961  mov     [rbp+0D0h+var_110], rax
0x1800e8965  mov     r15, rdx
0x1800e8968  mov     [rsp+1D0h+ppMFType], r12
0x1800e896d  mov     rsi, rcx
0x1800e8970  mov     [rbp+0D0h+var_A8], r12
0x1800e8974  mov     r8d, 130h; int
0x1800e897a  mov     [rbp+0D0h+var_A0], r12
0x1800e897e  lea     rdx, aCmfhardwarevid_4; "CMFHardwareVideoBranchLoader::InsertMFT"
0x1800e8985  mov     [rbp+0D0h+var_98], r12
0x1800e8989  lea     rcx, [rsp+1D0h+var_198]; this
0x1800e898e  mov     [rbp+0D0h+var_90], r12d
0x1800e8992  mov     r13, r9
0x1800e8995  mov     [rbp+0D0h+var_70], r12w
0x1800e899a  mov     [rbp+0D0h+var_88], r12
0x1800e899e  mov     [rbp+0D0h+var_80], r12
0x1800e89a2  mov     [rbp+0D0h+var_78], r12
0x1800e89a6  mov     [rbp+0D0h+var_108], r12
0x1800e89aa  mov     [rbp+0D0h+var_100], r12
0x1800e89ae  mov     [rbp+0D0h+var_F8], r12d
0x1800e89b2  mov     [rbp+0D0h+var_F4], 1
0x1800e89ba  mov     [rbp+0D0h+var_D0], r12w
0x1800e89bf  mov     [rbp+0D0h+var_E8], r12
0x1800e89c3  mov     [rbp+0D0h+var_E0], r12
0x1800e89c7  mov     [rbp+0D0h+var_D8], r12
0x1800e89cb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800e89d0  cmp     cs:byte_1803CECE9, 10h
0x1800e89d7  jb      short loc_1800E89FD
0x1800e89d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e89e0  lea     edx, [r12+1Bh]
0x1800e89e5  mov     r9, rsi
0x1800e89e8  mov     qword ptr [rsp+1D0h+var_1B0], rbx
0x1800e89ed  lea     r8, WPP_84077d43404e382a16b12f731fadc2a0_Traceguids
0x1800e89f4  mov     rcx, [rcx+38h]
0x1800e89f8  call    WPP_SF_qq
0x1800e89fd  mov     rcx, [rsi+18h]; this
0x1800e8a01  lea     r9, [rsp+1D0h+var_1A0]; struct IMFTopologyNode **
0x1800e8a06  xor     r8d, r8d; struct _GUID *
0x1800e8a09  mov     rdx, rbx; struct IUnknown *
0x1800e8a0c  call    ?AddTransformNode@CTopoConnectorShared@@QEAAJPEAUIUnknown@@PEAU_GUID@@PEAPEAUIMFTopologyNode@@@Z; CTopoConnectorShared::AddTransformNode(IUnknown *,_GUID *,IMFTopologyNode * *)
0x1800e8a11  mov     rbx, [rsp+1D0h+var_1A0]
0x1800e8a16  mov     edi, eax
0x1800e8a18  test    eax, eax
0x1800e8a1a  jns     short loc_1800E8A94
0x1800e8a1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8a23  test    rcx, rcx
0x1800e8a26  jnz     short loc_1800E8A34
0x1800e8a28  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800e8a2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e8a34  cmp     [rcx+8], r12b
0x1800e8a38  jz      short loc_1800E8A5F
0x1800e8a3a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e8a3f  cmp     [rax+7CCh], edi
0x1800e8a45  jz      short loc_1800E8A5F
0x1800e8a47  mov     r9d, edi; int
0x1800e8a4a  lea     rdx, aCmfhardwarevid_4; "CMFHardwareVideoBranchLoader::InsertMFT"
0x1800e8a51  mov     r8d, 132h; int
0x1800e8a57  mov     rcx, rax; this
0x1800e8a5a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e8a5f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e8a66  jb      loc_1800E9453
0x1800e8a6c  mov     edx, 1Ch
0x1800e8a71  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8a78  lea     r8, WPP_84077d43404e382a16b12f731fadc2a0_Traceguids
0x1800e8a7f  mov     r9, rsi
0x1800e8a82  mov     [rsp+1D0h+var_1B0], edi
0x1800e8a86  mov     rcx, [rcx+10h]
0x1800e8a8a  call    WPP_SF_qD
0x1800e8a8f  jmp     loc_1800E9453
0x1800e8a94  mov     rdx, [rsi+18h]; struct CTopoConnectorShared *
0x1800e8a98  lea     rcx, [rsp+1D0h+var_170]; this
0x1800e8a9d  xor     r9d, r9d; unsigned int
0x1800e8aa0  mov     [rsp+1D0h+var_1B0], r12d; int
0x1800e8aa5  mov     r8, rbx; struct IMFTopologyNode *
0x1800e8aa8  call    ??0CTopologyPin@@IEAA@PEAVCTopoConnectorShared@@PEAUIMFTopologyNode@@KH@Z; CTopologyPin::CTopologyPin(CTopoConnectorShared *,IMFTopologyNode *,ulong,int)
0x1800e8aad  lea     rax, ??_7CTopologyPin@@6B@; const CTopologyPin::`vftable'
0x1800e8ab4  lea     rdx, [rsp+1D0h+var_170]; struct CTopologyPin *
0x1800e8ab9  mov     [rsp+1D0h+var_170], rax
0x1800e8abe  lea     rcx, [rbp+0D0h+var_B0]; this
0x1800e8ac2  call    ?SetPin@CTopologyPin@@IEAAXAEAV1@@Z; CTopologyPin::SetPin(CTopologyPin &)
0x1800e8ac7  lea     rcx, [rsp+1D0h+var_170]; this
0x1800e8acc  call    ??1CTopologyPin@@UEAA@XZ; CTopologyPin::~CTopologyPin(void)
0x1800e8ad1  mov     rdx, [rsi+18h]; struct CTopoConnectorShared *
0x1800e8ad5  lea     rcx, [rsp+1D0h+var_170]; this
0x1800e8ada  xor     r9d, r9d; unsigned int
0x1800e8add  mov     [rsp+1D0h+var_1B0], 1; int
0x1800e8ae5  mov     r8, rbx; struct IMFTopologyNode *
0x1800e8ae8  call    ??0CTopologyPin@@IEAA@PEAVCTopoConnectorShared@@PEAUIMFTopologyNode@@KH@Z; CTopologyPin::CTopologyPin(CTopoConnectorShared *,IMFTopologyNode *,ulong,int)
0x1800e8aed  lea     rax, ??_7CTopologyPin@@6B@; const CTopologyPin::`vftable'
0x1800e8af4  lea     rdx, [rsp+1D0h+var_170]; struct CTopologyPin *
0x1800e8af9  mov     [rsp+1D0h+var_170], rax
0x1800e8afe  lea     rcx, [rbp+0D0h+var_110]; this
0x1800e8b02  call    ?SetPin@CTopologyPin@@IEAAXAEAV1@@Z; CTopologyPin::SetPin(CTopologyPin &)
0x1800e8b07  lea     rcx, [rsp+1D0h+var_170]; this
0x1800e8b0c  call    ??1CTopologyPin@@UEAA@XZ; CTopologyPin::~CTopologyPin(void)
0x1800e8b11  mov     rcx, [rsi+18h]
0x1800e8b15  mov     rcx, [rcx+8]; struct IMFTopology *
0x1800e8b19  call    ?IsDXGITranscodeTopology@@YAHPEAUIMFTopology@@@Z; IsDXGITranscodeTopology(IMFTopology *)
0x1800e8b1e  test    eax, eax
0x1800e8b20  jnz     short loc_1800E8B2F
0x1800e8b22  mov     rax, [rsi+10h]
0x1800e8b26  cmp     [rax], r12
0x1800e8b29  jz      loc_1800E8BF0
0x1800e8b2f  cmp     [rbp+0D0h+arg_30], r12d
0x1800e8b36  jnz     loc_1800E8BF0
0x1800e8b3c  mov     r9, [r13+10h]; struct IMFTopologyNode *
0x1800e8b40  mov     r8, rbx; struct IMFTopologyNode *
0x1800e8b43  mov     rdx, [rsi+10h]; struct CConnectContext *
0x1800e8b47  mov     rcx, [rsi+18h]; this
0x1800e8b4b  call    ?SetupD3DManager@CTopoConnectorShared@@QEAAJAEAVCConnectContext@@PEAUIMFTopologyNode@@1@Z; CTopoConnectorShared::SetupD3DManager(CConnectContext &,IMFTopologyNode *,IMFTopologyNode *)
0x1800e8b50  mov     edi, eax
0x1800e8b52  test    eax, eax
0x1800e8b54  jns     loc_1800E8BF0
0x1800e8b5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8b61  test    rcx, rcx
0x1800e8b64  jnz     short loc_1800E8BAE
0x1800e8b66  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e8b6d  nop     dword ptr [rax+rax+00h]
0x1800e8b72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8b79  mov     rcx, rax
0x1800e8b7c  test    rax, rax
0x1800e8b7f  jz      short loc_1800E8BA0
0x1800e8b81  mov     rax, [rax]
0x1800e8b84  mov     edx, 7F0h
0x1800e8b89  mov     rax, [rax+8]
0x1800e8b8d  call    cs:__guard_dispatch_icall_fptr
0x1800e8b93  test    eax, eax
0x1800e8b95  jz      short loc_1800E8BA0
0x1800e8b97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8b9e  jmp     short loc_1800E8BAE
0x1800e8ba0  lea     rcx, qword_1803CE250; this
0x1800e8ba7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8bae  cmp     [rcx+8], r12b
0x1800e8bb2  jz      short loc_1800E8BD9
0x1800e8bb4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e8bb9  cmp     [rax+7CCh], edi
0x1800e8bbf  jz      short loc_1800E8BD9
0x1800e8bc1  mov     r9d, edi; int
0x1800e8bc4  lea     rdx, aCmfhardwarevid_4; "CMFHardwareVideoBranchLoader::InsertMFT"
0x1800e8bcb  mov     r8d, 13Bh; int
0x1800e8bd1  mov     rcx, rax; this
0x1800e8bd4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e8bd9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e8be0  jb      loc_1800E9453
0x1800e8be6  mov     edx, 1Dh
0x1800e8beb  jmp     loc_1800E8A71
0x1800e8bf0  lea     rcx, [rsp+1D0h+ppMFType]; ppMFType
0x1800e8bf5  call    cs:__imp_MFCreateMediaType
0x1800e8bfc  nop     dword ptr [rax+rax+00h]
0x1800e8c01  mov     edi, eax
0x1800e8c03  test    eax, eax
0x1800e8c05  jns     loc_1800E8CA1
0x1800e8c0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8c12  test    rcx, rcx
0x1800e8c15  jnz     short loc_1800E8C5F
0x1800e8c17  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e8c1e  nop     dword ptr [rax+rax+00h]
0x1800e8c23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8c2a  mov     rcx, rax
0x1800e8c2d  test    rax, rax
0x1800e8c30  jz      short loc_1800E8C51
0x1800e8c32  mov     rax, [rax]
0x1800e8c35  mov     edx, 7F0h
0x1800e8c3a  mov     rax, [rax+8]
0x1800e8c3e  call    cs:__guard_dispatch_icall_fptr
0x1800e8c44  test    eax, eax
0x1800e8c46  jz      short loc_1800E8C51
0x1800e8c48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8c4f  jmp     short loc_1800E8C5F
0x1800e8c51  lea     rcx, qword_1803CE250; this
0x1800e8c58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8c5f  cmp     [rcx+8], r12b
0x1800e8c63  jz      short loc_1800E8C8A
0x1800e8c65  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e8c6a  cmp     [rax+7CCh], edi
0x1800e8c70  jz      short loc_1800E8C8A
0x1800e8c72  mov     r9d, edi; int
0x1800e8c75  lea     rdx, aCmfhardwarevid_4; "CMFHardwareVideoBranchLoader::InsertMFT"
0x1800e8c7c  mov     r8d, 13Eh; int
0x1800e8c82  mov     rcx, rax; this
0x1800e8c85  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e8c8a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e8c91  jb      loc_1800E9453
0x1800e8c97  mov     edx, 1Eh
0x1800e8c9c  jmp     loc_1800E8A71
0x1800e8ca1  mov     rax, [r14]
0x1800e8ca4  mov     rcx, r14
0x1800e8ca7  mov     rdx, [rsp+1D0h+ppMFType]
0x1800e8cac  mov     rax, [rax+100h]
0x1800e8cb3  call    cs:__guard_dispatch_icall_fptr
0x1800e8cb9  mov     edi, eax
0x1800e8cbb  test    eax, eax
0x1800e8cbd  jns     loc_1800E8D59
0x1800e8cc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8cca  test    rcx, rcx
0x1800e8ccd  jnz     short loc_1800E8D17
0x1800e8ccf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e8cd6  nop     dword ptr [rax+rax+00h]
0x1800e8cdb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8ce2  mov     rcx, rax
0x1800e8ce5  test    rax, rax
0x1800e8ce8  jz      short loc_1800E8D09
0x1800e8cea  mov     rax, [rax]
0x1800e8ced  mov     edx, 7F0h
0x1800e8cf2  mov     rax, [rax+8]
0x1800e8cf6  call    cs:__guard_dispatch_icall_fptr
0x1800e8cfc  test    eax, eax
0x1800e8cfe  jz      short loc_1800E8D09
0x1800e8d00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8d07  jmp     short loc_1800E8D17
0x1800e8d09  lea     rcx, qword_1803CE250; this
0x1800e8d10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8d17  cmp     [rcx+8], r12b
0x1800e8d1b  jz      short loc_1800E8D42
0x1800e8d1d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e8d22  cmp     [rax+7CCh], edi
0x1800e8d28  jz      short loc_1800E8D42
0x1800e8d2a  mov     r9d, edi; int
0x1800e8d2d  lea     rdx, aCmfhardwarevid_4; "CMFHardwareVideoBranchLoader::InsertMFT"
0x1800e8d34  mov     r8d, 13Fh; int
0x1800e8d3a  mov     rcx, rax; this
0x1800e8d3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e8d42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e8d49  jb      loc_1800E9453
0x1800e8d4f  mov     edx, 1Fh
0x1800e8d54  jmp     loc_1800E8A71
0x1800e8d59  mov     r9, [rsp+1D0h+ppMFType]; struct IMFMediaType *
0x1800e8d5e  lea     r8, [rbp+0D0h+var_B0]; struct CInputTopologyPin *
0x1800e8d62  mov     rcx, [rsi+18h]; this
0x1800e8d66  mov     rdx, r15; struct COutputTopologyPin *
0x1800e8d69  call    ?ConnectNodesWithProvidedMediaType@CTopoConnectorShared@@QEAAJAEAVCOutputTopologyPin@@AEAVCInputTopologyPin@@PEAUIMFMediaType@@@Z; CTopoConnectorShared::ConnectNodesWithProvidedMediaType(COutputTopologyPin &,CInputTopologyPin &,IMFMediaType *)
0x1800e8d6e  mov     edi, eax
0x1800e8d70  test    eax, eax
0x1800e8d72  jns     loc_1800E8E0E
0x1800e8d78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8d7f  test    rcx, rcx
0x1800e8d82  jnz     short loc_1800E8DCC
0x1800e8d84  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e8d8b  nop     dword ptr [rax+rax+00h]
0x1800e8d90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8d97  mov     rcx, rax
0x1800e8d9a  test    rax, rax
0x1800e8d9d  jz      short loc_1800E8DBE
0x1800e8d9f  mov     rax, [rax]
0x1800e8da2  mov     edx, 7F0h
0x1800e8da7  mov     rax, [rax+8]
0x1800e8dab  call    cs:__guard_dispatch_icall_fptr
0x1800e8db1  test    eax, eax
0x1800e8db3  jz      short loc_1800E8DBE
0x1800e8db5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8dbc  jmp     short loc_1800E8DCC
0x1800e8dbe  lea     rcx, qword_1803CE250; this
0x1800e8dc5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e8dcc  cmp     [rcx+8], r12b
0x1800e8dd0  jz      short loc_1800E8DF7
0x1800e8dd2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e8dd7  cmp     [rax+7CCh], edi
0x1800e8ddd  jz      short loc_1800E8DF7
0x1800e8ddf  mov     r9d, edi; int
0x1800e8de2  lea     rdx, aCmfhardwarevid_4; "CMFHardwareVideoBranchLoader::InsertMFT"
0x1800e8de9  mov     r8d, 140h; int
0x1800e8def  mov     rcx, rax; this
0x1800e8df2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e8df7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e8dfe  jb      loc_1800E9453
0x1800e8e04  mov     edx, 20h ; ' '
0x1800e8e09  jmp     loc_1800E8A71
0x1800e8e0e  mov     r8, r13; struct CInputTopologyPin *
0x1800e8e11  mov     dword ptr [rsi+8], 1
0x1800e8e18  lea     rdx, [rbp+0D0h+var_110]; struct COutputTopologyPin *
0x1800e8e1c  mov     rcx, rsi; this
0x1800e8e1f  call    ?ConnectPinsWithMatchedType@CMFHardwareVideoBranchLoader@@IEAAJAEAVCOutputTopologyPin@@AEAVCInputTopologyPin@@@Z; CMFHardwareVideoBranchLoader::ConnectPinsWithMatchedType(COutputTopologyPin &,CInputTopologyPin &)
0x1800e8e24  mov     edi, eax
0x1800e8e26  test    eax, eax
0x1800e8e28  jns     loc_1800E9464
0x1800e8e2e  mov     rcx, [rsp+1D0h+ppMFType]; this
0x1800e8e33  lea     r8, [rsp+1D0h+var_188.lpVtbl+4]; unsigned int *
0x1800e8e38  lea     rdx, [rsp+1D0h+var_188]; struct IMFMediaType *
0x1800e8e3d  mov     dword ptr [rsp+1D0h+var_188.lpVtbl], r12d
0x1800e8e42  mov     dword ptr [rsp+1D0h+var_188.lpVtbl+4], r12d
0x1800e8e47  call    ?GetNativeVideoSize@MFMEDIATYPEUtils@@YAJPEAUIMFMediaType@@PEAK1@Z; MFMEDIATYPEUtils::GetNativeVideoSize(IMFMediaType *,ulong *,ulong *)
  ... truncated ...
```
