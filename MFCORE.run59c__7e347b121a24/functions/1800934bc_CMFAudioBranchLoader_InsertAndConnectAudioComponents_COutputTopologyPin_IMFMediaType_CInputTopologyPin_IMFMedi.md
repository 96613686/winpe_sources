# CMFAudioBranchLoader::InsertAndConnectAudioComponents(COutputTopologyPin &,IMFMediaType *,CInputTopologyPin &,IMFMediaType *,ulong)

- ea: `0x1800934bc`
- end: `0x18009432d`
- name: `?InsertAndConnectAudioComponents@CMFAudioBranchLoader@@QEAAJAEAVCOutputTopologyPin@@PEAUIMFMediaType@@AEAVCInputTopologyPin@@1K@Z`
- size: `3697`
- prototype: `__int64 __usercall@<rax>(CMFAudioBranchLoader *__hidden this@<rcx>, struct COutputTopologyPin *@<rdx>, struct IMFMediaType *@<r8>, struct CInputTopologyPin *@<r9>, struct IMFMediaType *, unsigned int)`
- caller_count: `2`
- callee_count: `35`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010a12c`
- `0x180192f5c`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x1800483d0`
- `0x18004a904`
- `0x18004ae20`
- `0x18004c67c`
- `0x180050d6c`
- `0x180063f00`
- `0x18006b388`
- `0x1800717b4`
- `0x180091eb0`
- `0x180092630`
- `0x18009302c`
- `0x1800934bc`
- `0x180095bcc`
- `0x18009efc4`
- `0x1800ae158`
- `0x1800ae554`
- `0x1800cac5c`
- `0x1800e9c38`
- `0x1800ec0e0`
- `0x1801208ec`
- `0x18014c0fc`
- `0x180161f50`
- `0x1801856c4`
- `0x18020cca4`
- `0x180227364`
- `0x180258480`
- `0x1802c2da8`
- `0x1802c4cb0`
- `0x1802c54d0`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800935ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800936ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093860`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093d74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093f85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094041`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094107`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009424a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800935ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800936ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093860`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093d74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180093f85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094041`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094107`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009424a`

## string_xrefs

- `0x180093503`: `CMFAudioBranchLoader::InsertAndConnectAudioComponents`
- `0x18009364a`: `CMFAudioBranchLoader::InsertAndConnectAudioComponents`
- `0x18009372b`: `CMFAudioBranchLoader::InsertAndConnectAudioComponents`
- `0x1800938bd`: `CMFAudioBranchLoader::InsertAndConnectAudioComponents`
- `0x180093a01`: `CMFAudioBranchLoader::InsertAndConnectAudioComponents`
- `0x180093dd2`: `CMFAudioBranchLoader::InsertAndConnectAudioComponents`
- `0x180093fe3`: `CMFAudioBranchLoader::InsertAndConnectAudioComponents`
- `0x18009409f`: `CMFAudioBranchLoader::InsertAndConnectAudioComponents`
- `0x180094165`: `CMFAudioBranchLoader::InsertAndConnectAudioComponents`
- `0x1800942a7`: `CMFAudioBranchLoader::InsertAndConnectAudioComponents`

## pseudocode

```c
__int64 __fastcall CMFAudioBranchLoader::InsertAndConnectAudioComponents(
        CTopoConnectorShared **this,
        struct COutputTopologyPin *a2,
        struct IMFAttributes *a3,
        struct IMFMediaType *a4,
        struct IMFAttributes *a5,
        char a6)
{
  struct IMFTopologyNode *v6; // rbx
  struct IMFAttributes *v7; // r14
  struct IMFMediaType *v9; // r15
  __int64 v10; // rdx
  __int64 v11; // r8
  const char *String; // rax
  const char *v13; // rax
  struct IMFAttributes v14; // rax
  __int64 v15; // rdx
  int v16; // esi
  __int64 v17; // r8
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v21; // rdx
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  struct IMFMediaType **v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  struct IMFMediaType *v34; // rsi
  int v35; // r15d
  unsigned int NodeId; // eax
  struct IMFMediaTypeVtbl *v37; // rsi
  unsigned int v38; // edi
  int v39; // r14d
  unsigned int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // r8
  struct IMFMediaType *v43; // rdi
  const char *v44; // rax
  CTopoConnectorShared *v45; // rcx
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  struct IMFMediaTypeVtbl *v48; // rcx
  struct IMFTopologyNode *v49; // r8
  int v50; // ebx
  unsigned int v51; // eax
  int MediaTypeHandler; // ebx
  int CurrentTypeFromMFT; // eax
  unsigned int v54; // r8d
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  unsigned int v60; // eax
  struct CTopoConnectorShared *v61; // rdx
  CTopoConnectorShared *v62; // rcx
  int v63; // eax
  __int64 v64; // rdx
  struct IMFAttributes v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  __int64 *v82; // rcx
  CallStackTracing *v83; // rax
  struct CallStackContext *v84; // rax
  _BYTE v86[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct IMFMediaType v87; // [rsp+58h] [rbp-A8h] BYREF
  struct IMFTransform *v88; // [rsp+60h] [rbp-A0h] BYREF
  struct IMFMediaType *v89; // [rsp+68h] [rbp-98h] BYREF
  int v90; // [rsp+70h] [rbp-90h] BYREF
  int v91; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v92; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v93; // [rsp+7Ch] [rbp-84h] BYREF
  struct IMFTopologyNode *v94; // [rsp+80h] [rbp-80h] BYREF
  CTopologyPin *v95; // [rsp+88h] [rbp-78h]
  _BYTE v96[192]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v97[192]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v98[192]; // [rsp+210h] [rbp+110h] BYREF
  __int128 Buf2; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 Buf1; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 v101; // [rsp+2F0h] [rbp+1F0h] BYREF
  struct _GUID v102; // [rsp+300h] [rbp+200h] BYREF
  _QWORD v103[2]; // [rsp+310h] [rbp+210h] BYREF
  __int64 v104; // [rsp+320h] [rbp+220h]
  int v105; // [rsp+32Ch] [rbp+22Ch]
  _QWORD v106[12]; // [rsp+370h] [rbp+270h] BYREF
  _QWORD v107[12]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v6 = 0;
  v7 = a3;
  *(_QWORD *)&Buf2 = a3;
  v95 = a2;
  v89 = a4;
  v94 = 0;
  v9 = a4;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v86,
    "CMFAudioBranchLoader::InsertAndConnectAudioComponents",
    31);
  if ( (a6 & 8) != 0 )
  {
    v87.lpVtbl = 0;
    CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v97, v7);
    CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v96, a5);
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    {
      String = CMFAttributesTrace::GetString((CMFAttributesTrace *)v97, 0);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, String);
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      {
        v13 = CMFAttributesTrace::GetString((CMFAttributesTrace *)v96, 0);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, v13);
      }
    }
    v14.lpVtbl = v7->lpVtbl;
    Buf1 = 0;
    v16 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, __int128 *))v14.lpVtbl->GetGUID)(
            v7,
            &MF_MT_SUBTYPE,
            &Buf1);
    if ( v16 < 0 )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v16 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFAudioBranchLoader::InsertAndConnectAudioComponents",
            47,
            v16);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v21 = 13;
      goto LABEL_16;
    }
    lpVtbl = (struct IMFMediaTypeVtbl *)a5->lpVtbl;
    v101 = 0;
    v16 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, __int128 *))lpVtbl->GetGUID)(
            a5,
            &MF_MT_SUBTYPE,
            &v101);
    if ( v16 < 0 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24);
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)v27 + 499) != v16 )
          CallStackContext::TraceFailure(v27, "CMFAudioBranchLoader::InsertAndConnectAudioComponents", 50, v16);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v21 = 14;
      goto LABEL_16;
    }
    if ( memcmp_0(&Buf1, &MFAudioFormat_PCM, 0x10u) && memcmp_0(&Buf1, &MFAudioFormat_Float, 0x10u)
      || memcmp_0(&v101, &MFAudioFormat_PCM, 0x10u) && memcmp_0(&v101, &MFAudioFormat_Float, 0x10u) )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 4u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, this);
      v16 = -1072861841;
      if ( g_wppLevels >= 4u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids,
          this,
          -1072861841);
      goto LABEL_36;
    }
    v16 = MFMEDIATYPEUtils::MergeAudioMediaTypes((MFMEDIATYPEUtils *)v7, (struct IMFMediaType *)a5, &v87, v28);
    if ( v16 < 0 )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v33 + 499) != v16 )
          CallStackContext::TraceFailure(v33, "CMFAudioBranchLoader::InsertAndConnectAudioComponents", 63, v16);
      }
      if ( !g_wppLevels )
        goto LABEL_148;
      v21 = 17;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, this, v16);
LABEL_148:
      CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v96);
      CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v97);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v87);
LABEL_149:
      if ( v6 )
        CTopoConnectorShared::RemoveDestNode(*this, v6);
      goto LABEL_162;
    }
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    {
      v34 = v89;
      v35 = (int)v9[3].lpVtbl;
      NodeId = CTopologyPin::GetNodeId((CTopologyPin *)v89);
      v37 = v34[2].lpVtbl;
      v38 = NodeId;
      v39 = *((_DWORD *)v95 + 6);
      v40 = CTopologyPin::GetNodeId(v95);
      WPP_SF_qqddqdd(*((_QWORD *)WPP_GLOBAL_Control + 7), v41, v42, this, *((_QWORD *)v95 + 2), v40, v39, v37, v38, v35);
      v7 = (struct IMFAttributes *)Buf2;
      v9 = v89;
    }
    v43 = (struct IMFMediaType *)v87.lpVtbl;
    CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v98, (struct IMFAttributes *)v87.lpVtbl);
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    {
      v44 = CMFAttributesTrace::GetString((CMFAttributesTrace *)v98, 0);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, v44);
    }
    v45 = *this;
    v88 = 0;
    v102 = 0;
    v16 = CTopoLoaderTransformCreator::CreateSampleRateConverter(
            (CTopoConnectorShared *)((char *)v45 + 32),
            &v88,
            &v102);
    if ( v16 < 0 )
    {
      v46 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v46 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v46 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext(v46);
        if ( *((_DWORD *)v47 + 499) != v16 )
          CallStackContext::TraceFailure(v47, "CMFAudioBranchLoader::InsertAndConnectAudioComponents", 79, v16);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, this, v16);
      if ( v88 )
        ((void (__fastcall *)(struct IMFTransform *))v88->lpVtbl->Release)(v88);
      CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v98);
      CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v96);
      CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v97);
      if ( v43 )
        ((void (__fastcall *)(struct IMFMediaType *))v43->lpVtbl->Release)(v43);
      goto LABEL_149;
    }
    v48 = v9[2].lpVtbl;
    v90 = 0;
    if ( (*((int (__fastcall **)(struct IMFMediaTypeVtbl *, int *))v48->QueryInterface + 39))(v48, &v90) < 0 || v90 != 1 )
    {
LABEL_91:
      v16 = CTopoConnectorShared::AddTransformNode(*this, (struct IUnknown *)v88, &v102, &v94);
      if ( v16 < 0 )
      {
        v57 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56);
          CallStackTracing::s_wpInstance = v58;
          if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
          {
            v57 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v57 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v57 + 8) )
        {
          v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
          if ( *((_DWORD *)v59 + 499) != v16 )
            CallStackContext::TraceFailure(v59, "CMFAudioBranchLoader::InsertAndConnectAudioComponents", 122, v16);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids,
            this,
            v16);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v88);
        CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v98);
        CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v96);
        CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v97);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v87);
        v6 = v94;
        goto LABEL_149;
      }
      v6 = v94;
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      {
        v60 = CTypeHandlerWrapper::GetNodeId(v94);
        WPP_SF_qqD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          23,
          &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids,
          this,
          v6,
          v60);
      }
      CTopologyPin::CTopologyPin((CTopologyPin *)v107, *this, v6, 0, 0);
      v61 = *this;
      v107[0] = &CTopologyPin::`vftable';
      CTopologyPin::CTopologyPin((CTopologyPin *)v106, v61, v6, 0, 1);
      v62 = *this;
      v106[0] = &CTopologyPin::`vftable';
      v63 = CTopoConnectorShared::ConnectNodesWithProvidedMediaType(
              v62,
              v95,
              (struct CInputTopologyPin *)v107,
              (struct IMFMediaType *)v7);
      v16 = v63;
      if ( v63 < 0 )
      {
        if ( g_wppLevels >= 8u )
        {
          v64 = 24;
LABEL_108:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v64,
            &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids,
            this,
            v63);
        }
LABEL_147:
        CTopologyPin::~CTopologyPin((CTopologyPin *)v106);
        CTopologyPin::~CTopologyPin((CTopologyPin *)v107);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v88);
        CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v98);
        goto LABEL_148;
      }
      v63 = CTopoConnectorShared::ConnectNodesWithProvidedMediaType(
              *this,
              (struct COutputTopologyPin *)v106,
              (struct CInputTopologyPin *)v9,
              v43);
      v16 = v63;
      if ( v63 < 0 )
      {
        if ( g_wppLevels < 8u )
          goto LABEL_147;
        v64 = 25;
        goto LABEL_108;
      }
      v65.lpVtbl = v7->lpVtbl;
      v92 = 0;
      v93 = 0;
      v16 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, unsigned int *))v65.lpVtbl->GetUINT32)(
              v7,
              &MF_MT_AUDIO_NUM_CHANNELS,
              &v92);
      if ( v16 >= 0 )
      {
        v16 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned int *))v43->lpVtbl->GetUINT32)(
                v43,
                &MF_MT_AUDIO_NUM_CHANNELS,
                &v93);
        if ( v16 >= 0 )
        {
          if ( v92 <= v93
            || (v16 = CMFAudioBranchLoader::TrySetResamplerFolddownMatrix(
                        (CMFAudioBranchLoader *)this,
                        v88,
                        (struct IMFMediaType *)v7,
                        v92,
                        v93),
                v16 >= 0) )
          {
            CTopologyPin::~CTopologyPin((CTopologyPin *)v106);
            CTopologyPin::~CTopologyPin((CTopologyPin *)v107);
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v88);
            CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v98);
LABEL_36:
            CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v96);
            CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v97);
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v87);
            goto LABEL_162;
          }
          v79 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v77, v78);
            CallStackTracing::s_wpInstance = v80;
            if ( v80 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
            {
              v79 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v79 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v79 + 8) )
          {
            v81 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
            if ( *((_DWORD *)v81 + 499) != v16 )
              CallStackContext::TraceFailure(v81, "CMFAudioBranchLoader::InsertAndConnectAudioComponents", 143, v16);
          }
          if ( !g_wppLevels )
            goto LABEL_147;
          v71 = 28;
        }
        else
        {
          v74 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73);
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
            if ( *((_DWORD *)v76 + 499) != v16 )
              CallStackContext::TraceFailure(v76, "CMFAudioBranchLoader::InsertAndConnectAudioComponents", 139, v16);
          }
          if ( !g_wppLevels )
            goto LABEL_147;
          v71 = 27;
        }
      }
      else
      {
        v68 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67);
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
          if ( *((_DWORD *)v70 + 499) != v16 )
            CallStackContext::TraceFailure(v70, "CMFAudioBranchLoader::InsertAndConnectAudioComponents", 138, v16);
        }
        if ( !g_wppLevels )
          goto LABEL_147;
        v71 = 26;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v71, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, this, v16);
      goto LABEL_147;
    }
    if ( (unsigned __int8)byte_1803CECE9 >= 0x20u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids);
    v49 = (struct IMFTopologyNode *)v9[2].lpVtbl;
    v89 = 0;
    CTopologyPin::CTopologyPin((CTopologyPin *)v103, 0, v49, 0, 1);
    v103[0] = &CTopologyPin::`vftable';
    v91 = 0;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v86, "CTopologyPin::GetCurrentType", 330);
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    {
      v50 = v105;
      v51 = CTopologyPin::GetNodeId((CTopologyPin *)v103);
      WPP_SF_qqDd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        20,
        &WPP_be8b147e254b344cf3a825991e896d94_Traceguids,
        v103,
        v104,
        v51,
        v50);
    }
    MediaTypeHandler = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v104 + 280LL))(v104, &v91);
    if ( MediaTypeHandler >= 0 )
    {
      switch ( v91 )
      {
        case 2:
          CurrentTypeFromMFT = CTopologyPin::GetCurrentTypeFromMFT((CTopologyPin *)v103, &v89);
LABEL_83:
          MediaTypeHandler = CurrentTypeFromMFT;
          goto LABEL_85;
        case 1:
          CurrentTypeFromMFT = CTopologyPin::GetCurrentTypeFromSourceStream((CTopologyPin *)v103, &v89);
          goto LABEL_83;
        case 0:
          *(_QWORD *)&Buf2 = 0;
          MediaTypeHandler = CTopologyPin::GetMediaTypeHandler(
                               (CTopologyPin *)v103,
                               (struct IMFMediaTypeHandler **)&Buf2);
          if ( MediaTypeHandler >= 0 )
            MediaTypeHandler = (*(__int64 (__fastcall **)(_QWORD, struct IMFMediaType **))(*(_QWORD *)Buf2 + 56LL))(
                                 Buf2,
                                 &v89);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&Buf2);
          goto LABEL_85;
      }
      if ( v91 != 3 )
      {
        MediaTypeHandler = -1072875854;
        goto LABEL_85;
      }
      LODWORD(Buf2) = 0;
      MediaTypeHandler = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v104 + 376LL))(
                           v104,
                           0,
                           &v89);
      if ( MediaTypeHandler < 0 || !v89 )
      {
        (*(void (__fastcall **)(__int64, const IID *, __int128 *))(*(_QWORD *)v104 + 56LL))(
          v104,
          &MF_TOPONODE_PRIMARYOUTPUT,
          &Buf2);
        CurrentTypeFromMFT = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v104 + 360LL))(
                               v104,
                               (unsigned int)Buf2,
                               &v89);
        goto LABEL_83;
      }
    }
LABEL_85:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v86);
    if ( MediaTypeHandler >= 0 || (int)CTopologyPin::GetPossibleType((CTopologyPin *)v103, 0, &v89) >= 0 )
    {
      Buf2 = 0;
      if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, __int128 *))v89->lpVtbl->GetGUID)(
             v89,
             &MF_MT_SUBTYPE,
             &Buf2) >= 0
        && !memcmp_0(&MEDIASUBTYPE_MFWMTimedLevel, &Buf2, 0x10u) )
      {
        CMFAudioBranchLoader::SetResamplerQuality((CMFAudioBranchLoader *)this, v88, v54);
      }
    }
    CTopologyPin::~CTopologyPin((CTopologyPin *)v103);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v89);
    goto LABEL_91;
  }
  v82 = (__int64 *)CallStackTracing::s_wpInstance;
  v16 = -2147467259;
  if ( !CallStackTracing::s_wpInstance )
  {
    v83 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
    CallStackTracing::s_wpInstance = v83;
    if ( v83 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v83 + 8LL))(v83, 2032) )
    {
      v82 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v82 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v82 + 8) )
  {
    v84 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v82);
    if ( *((_DWORD *)v84 + 499) != -2147467259 )
      CallStackContext::TraceFailure(v84, "CMFAudioBranchLoader::InsertAndConnectAudioComponents", 150, -2147467259);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids,
      this,
      -2147467259);
LABEL_162:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v86);
  if ( v6 )
    ((void (__fastcall *)(struct IMFTopologyNode *))v6->lpVtbl->Release)(v6);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800934bc  push    rbp
0x1800934be  push    rbx
0x1800934bf  push    rsi
0x1800934c0  push    rdi
0x1800934c1  push    r12
0x1800934c3  push    r13
0x1800934c5  push    r14
0x1800934c7  push    r15
0x1800934c9  lea     rbp, [rsp-348h]
0x1800934d1  sub     rsp, 448h
0x1800934d8  mov     rax, cs:__security_cookie
0x1800934df  xor     rax, rsp
0x1800934e2  mov     [rbp+380h+var_50], rax
0x1800934e9  mov     rdi, [rbp+380h+arg_20]
0x1800934f0  xor     ebx, ebx
0x1800934f2  mov     r14, r8
0x1800934f5  mov     qword ptr [rbp+380h+Buf2], r8
0x1800934fc  mov     [rbp+380h+var_3F8], rdx
0x180093500  mov     r12, rcx
0x180093503  lea     rdx, aCmfaudiobranch; "CMFAudioBranchLoader::InsertAndConnectA"...
0x18009350a  mov     [rsp+480h+var_418], r9
0x18009350f  lea     r8d, [rbx+1Fh]; int
0x180093513  mov     [rbp+380h+var_400], rbx
0x180093517  lea     rcx, [rsp+480h+var_430]; this
0x18009351c  mov     r15, r9
0x18009351f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180093524  test    byte ptr [rbp+380h+arg_28], 8
0x18009352b  jz      loc_180094239
0x180093531  mov     rdx, r14; struct IMFAttributes *
0x180093534  mov     [rsp+480h+var_428.lpVtbl], rbx
0x180093539  lea     rcx, [rbp+380h+var_330]; this
0x18009353d  call    ??0CMFAttributesTrace@@QEAA@PEAUIMFAttributes@@@Z; CMFAttributesTrace::CMFAttributesTrace(IMFAttributes *)
0x180093542  mov     rdx, rdi; struct IMFAttributes *
0x180093545  lea     rcx, [rbp+380h+var_3F0]; this
0x180093549  call    ??0CMFAttributesTrace@@QEAA@PEAUIMFAttributes@@@Z; CMFAttributesTrace::CMFAttributesTrace(IMFAttributes *)
0x18009354e  cmp     cs:byte_1803CECE9, 10h
0x180093555  lea     r13, WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids
0x18009355c  jb      short loc_1800935AF
0x18009355e  xor     edx, edx; bool
0x180093560  lea     rcx, [rbp+380h+var_330]; this
0x180093564  call    ?GetString@CMFAttributesTrace@@QEAAPEBD_N@Z; CMFAttributesTrace::GetString(bool)
0x180093569  mov     rcx, cs:WPP_GLOBAL_Control
0x180093570  lea     edx, [rbx+0Bh]
0x180093573  mov     r9, rax
0x180093576  mov     r8, r13
0x180093579  mov     rcx, [rcx+38h]
0x18009357d  call    WPP_SF_s
0x180093582  cmp     cs:byte_1803CECE9, 10h
0x180093589  jb      short loc_1800935AF
0x18009358b  xor     edx, edx; bool
0x18009358d  lea     rcx, [rbp+380h+var_3F0]; this
0x180093591  call    ?GetString@CMFAttributesTrace@@QEAAPEBD_N@Z; CMFAttributesTrace::GetString(bool)
0x180093596  mov     rcx, cs:WPP_GLOBAL_Control
0x18009359d  lea     edx, [rbx+0Ch]
0x1800935a0  mov     r9, rax
0x1800935a3  mov     r8, r13
0x1800935a6  mov     rcx, [rcx+38h]
0x1800935aa  call    WPP_SF_s
0x1800935af  mov     rax, [r14]
0x1800935b2  lea     r8, [rbp+380h+Buf1]
0x1800935b9  xorps   xmm0, xmm0
0x1800935bc  lea     rdx, MF_MT_SUBTYPE
0x1800935c3  mov     rcx, r14
0x1800935c6  movups  [rbp+380h+Buf1], xmm0
0x1800935cd  mov     rax, [rax+50h]
0x1800935d1  call    cs:__guard_dispatch_icall_fptr
0x1800935d7  mov     esi, eax
0x1800935d9  test    eax, eax
0x1800935db  jns     loc_180093690
0x1800935e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800935e8  test    rcx, rcx
0x1800935eb  jnz     short loc_180093635
0x1800935ed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800935f4  nop     dword ptr [rax+rax+00h]
0x1800935f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180093600  mov     rcx, rax
0x180093603  test    rax, rax
0x180093606  jz      short loc_180093627
0x180093608  mov     rax, [rax]
0x18009360b  mov     edx, 7F0h
0x180093610  mov     rax, [rax+8]
0x180093614  call    cs:__guard_dispatch_icall_fptr
0x18009361a  test    eax, eax
0x18009361c  jz      short loc_180093627
0x18009361e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093625  jmp     short loc_180093635
0x180093627  lea     rcx, qword_1803CE250; this
0x18009362e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180093635  cmp     [rcx+8], bl
0x180093638  jz      short loc_18009365F
0x18009363a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009363f  cmp     [rax+7CCh], esi
0x180093645  jz      short loc_18009365F
0x180093647  mov     r9d, esi; int
0x18009364a  lea     rdx, aCmfaudiobranch; "CMFAudioBranchLoader::InsertAndConnectA"...
0x180093651  mov     r8d, 2Fh ; '/'; int
0x180093657  mov     rcx, rax; this
0x18009365a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009365f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093666  jb      loc_1800941D0
0x18009366c  mov     edx, 0Dh
0x180093671  mov     rcx, cs:WPP_GLOBAL_Control
0x180093678  mov     r9, r12
0x18009367b  mov     r8, r13
0x18009367e  mov     [rsp+480h+var_460], esi
0x180093682  mov     rcx, [rcx+10h]
0x180093686  call    WPP_SF_qD
0x18009368b  jmp     loc_1800941D0
0x180093690  mov     rax, [rdi]
0x180093693  lea     r8, [rbp+380h+var_190]
0x18009369a  xorps   xmm0, xmm0
0x18009369d  lea     rdx, MF_MT_SUBTYPE
0x1800936a4  mov     rcx, rdi
0x1800936a7  movups  [rbp+380h+var_190], xmm0
0x1800936ae  mov     rax, [rax+50h]
0x1800936b2  call    cs:__guard_dispatch_icall_fptr
0x1800936b8  mov     esi, eax
0x1800936ba  test    eax, eax
0x1800936bc  jns     loc_180093757
0x1800936c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800936c9  test    rcx, rcx
0x1800936cc  jnz     short loc_180093716
0x1800936ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800936d5  nop     dword ptr [rax+rax+00h]
0x1800936da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800936e1  mov     rcx, rax
0x1800936e4  test    rax, rax
0x1800936e7  jz      short loc_180093708
0x1800936e9  mov     rax, [rax]
0x1800936ec  mov     edx, 7F0h
0x1800936f1  mov     rax, [rax+8]
0x1800936f5  call    cs:__guard_dispatch_icall_fptr
0x1800936fb  test    eax, eax
0x1800936fd  jz      short loc_180093708
0x1800936ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093706  jmp     short loc_180093716
0x180093708  lea     rcx, qword_1803CE250; this
0x18009370f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180093716  cmp     [rcx+8], bl
0x180093719  jz      short loc_180093740
0x18009371b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180093720  cmp     [rax+7CCh], esi
0x180093726  jz      short loc_180093740
0x180093728  mov     r9d, esi; int
0x18009372b  lea     rdx, aCmfaudiobranch; "CMFAudioBranchLoader::InsertAndConnectA"...
0x180093732  mov     r8d, 32h ; '2'; int
0x180093738  mov     rcx, rax; this
0x18009373b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180093740  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093747  jb      loc_1800941D0
0x18009374d  mov     edx, 0Eh
0x180093752  jmp     loc_180093671
0x180093757  mov     esi, 10h
0x18009375c  lea     rdx, MFAudioFormat_PCM; Buf2
0x180093763  mov     r8d, esi; Size
0x180093766  lea     rcx, [rbp+380h+Buf1]; Buf1
0x18009376d  call    memcmp_0
0x180093772  test    eax, eax
0x180093774  jz      short loc_180093790
0x180093776  mov     r8d, esi; Size
0x180093779  lea     rdx, MFAudioFormat_Float; Buf2
0x180093780  lea     rcx, [rbp+380h+Buf1]; Buf1
0x180093787  call    memcmp_0
0x18009378c  test    eax, eax
0x18009378e  jnz     short loc_1800937C8
0x180093790  mov     r8, rsi; Size
0x180093793  lea     rdx, MFAudioFormat_PCM; Buf2
0x18009379a  lea     rcx, [rbp+380h+var_190]; Buf1
0x1800937a1  call    memcmp_0
0x1800937a6  test    eax, eax
0x1800937a8  jz      loc_18009383A
0x1800937ae  mov     r8, rsi; Size
0x1800937b1  lea     rdx, MFAudioFormat_Float; Buf2
0x1800937b8  lea     rcx, [rbp+380h+var_190]; Buf1
0x1800937bf  call    memcmp_0
0x1800937c4  test    eax, eax
0x1800937c6  jz      short loc_18009383A
0x1800937c8  cmp     cs:byte_1803CECE9, 4
0x1800937cf  jb      short loc_1800937EC
0x1800937d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800937d8  mov     edx, 0Fh
0x1800937dd  mov     r9, r12
0x1800937e0  mov     r8, r13
0x1800937e3  mov     rcx, [rcx+38h]
0x1800937e7  call    WPP_SF_q
0x1800937ec  mov     esi, 0C00D6D6Fh
0x1800937f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x1800937f8  jb      short loc_180093819
0x1800937fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180093801  mov     edx, 10h
0x180093806  mov     r9, r12
0x180093809  mov     [rsp+480h+var_460], esi
0x18009380d  mov     r8, r13
0x180093810  mov     rcx, [rcx+10h]
0x180093814  call    WPP_SF_qD
0x180093819  lea     rcx, [rbp+380h+var_3F0]; this
0x18009381d  call    ??1CMFAttributesTrace@@QEAA@XZ; CMFAttributesTrace::~CMFAttributesTrace(void)
0x180093822  lea     rcx, [rbp+380h+var_330]; this
0x180093826  call    ??1CMFAttributesTrace@@QEAA@XZ; CMFAttributesTrace::~CMFAttributesTrace(void)
0x18009382b  lea     rcx, [rsp+480h+var_428]
0x180093830  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180093835  jmp     loc_1800942E8
0x18009383a  lea     r8, [rsp+480h+var_428]; struct IMFMediaType *
0x18009383f  mov     rdx, rdi; struct IMFMediaType *
0x180093842  mov     rcx, r14; this
0x180093845  call    ?MergeAudioMediaTypes@MFMEDIATYPEUtils@@YAJPEAUIMFMediaType@@0PEAPEAU2@@Z; MFMEDIATYPEUtils::MergeAudioMediaTypes(IMFMediaType *,IMFMediaType *,IMFMediaType * *)
0x18009384a  mov     esi, eax
0x18009384c  test    eax, eax
0x18009384e  jns     loc_1800938E9
0x180093854  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009385b  test    rcx, rcx
0x18009385e  jnz     short loc_1800938A8
0x180093860  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180093867  nop     dword ptr [rax+rax+00h]
0x18009386c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180093873  mov     rcx, rax
0x180093876  test    rax, rax
0x180093879  jz      short loc_18009389A
0x18009387b  mov     rax, [rax]
0x18009387e  mov     edx, 7F0h
0x180093883  mov     rax, [rax+8]
0x180093887  call    cs:__guard_dispatch_icall_fptr
0x18009388d  test    eax, eax
0x18009388f  jz      short loc_18009389A
0x180093891  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180093898  jmp     short loc_1800938A8
0x18009389a  lea     rcx, qword_1803CE250; this
0x1800938a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800938a8  cmp     [rcx+8], bl
0x1800938ab  jz      short loc_1800938D2
0x1800938ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800938b2  cmp     [rax+7CCh], esi
0x1800938b8  jz      short loc_1800938D2
0x1800938ba  mov     r9d, esi; int
0x1800938bd  lea     rdx, aCmfaudiobranch; "CMFAudioBranchLoader::InsertAndConnectA"...
0x1800938c4  mov     r8d, 3Fh ; '?'; int
0x1800938ca  mov     rcx, rax; this
0x1800938cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800938d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800938d9  jb      loc_1800941D0
0x1800938df  mov     edx, 11h
0x1800938e4  jmp     loc_180093671
0x1800938e9  cmp     cs:byte_1803CECE9, 10h
0x1800938f0  jb      short loc_18009395C
0x1800938f2  mov     rsi, [rsp+480h+var_418]
0x1800938f7  mov     r15d, [r15+18h]
0x1800938fb  mov     rcx, rsi; this
0x1800938fe  call    ?GetNodeId@CTopologyPin@@QEAAKXZ; CTopologyPin::GetNodeId(void)
0x180093903  mov     rsi, [rsi+10h]
0x180093907  mov     edi, eax
0x180093909  mov     rax, [rbp+380h+var_3F8]
0x18009390d  mov     rcx, rax; this
0x180093910  mov     r14d, [rax+18h]
0x180093914  call    ?GetNodeId@CTopologyPin@@QEAAKXZ; CTopologyPin::GetNodeId(void)
0x180093919  mov     rcx, cs:WPP_GLOBAL_Control
0x180093920  mov     r9, r12
0x180093923  mov     [rsp+480h+var_438], r15d
0x180093928  mov     [rsp+480h+var_440], edi
0x18009392c  mov     [rsp+480h+var_448], rsi
0x180093931  mov     rcx, [rcx+38h]
0x180093935  mov     [rsp+480h+var_450], r14d
0x18009393a  mov     [rsp+480h+var_458], eax
0x18009393e  mov     rax, [rbp+380h+var_3F8]
0x180093942  mov     rax, [rax+10h]
0x180093946  mov     qword ptr [rsp+480h+var_460], rax
0x18009394b  call    WPP_SF_qqddqdd
0x180093950  mov     r14, qword ptr [rbp+380h+Buf2]
0x180093957  mov     r15, [rsp+480h+var_418]
0x18009395c  mov     rdi, [rsp+480h+var_428.lpVtbl]
0x180093961  lea     rcx, [rbp+380h+var_270]; this
0x180093968  mov     rdx, rdi; struct IMFAttributes *
0x18009396b  call    ??0CMFAttributesTrace@@QEAA@PEAUIMFAttributes@@@Z; CMFAttributesTrace::CMFAttributesTrace(IMFAttributes *)
0x180093970  cmp     cs:byte_1803CECE9, 10h
0x180093977  jb      short loc_1800939A2
0x180093979  xor     edx, edx; bool
0x18009397b  lea     rcx, [rbp+380h+var_270]; this
0x180093982  call    ?GetString@CMFAttributesTrace@@QEAAPEBD_N@Z; CMFAttributesTrace::GetString(bool)
0x180093987  mov     rcx, cs:WPP_GLOBAL_Control
0x18009398e  mov     edx, 13h
0x180093993  mov     r9, rax
0x180093996  mov     r8, r13
0x180093999  mov     rcx, [rcx+38h]
0x18009399d  call    WPP_SF_s
0x1800939a2  mov     rcx, [r12]
0x1800939a6  lea     r8, [rbp+380h+var_180]; struct _GUID *
0x1800939ad  xorps   xmm0, xmm0
0x1800939b0  mov     [rsp+480h+var_420], rbx
0x1800939b5  add     rcx, 20h ; ' '; this
0x1800939b9  lea     rdx, [rsp+480h+var_420]; struct IMFTransform **
0x1800939be  movups  xmmword ptr [rbp+380h+var_180.Data1], xmm0
0x1800939c5  call    ?CreateSampleRateConverter@CTopoLoaderTransformCreator@@QEAAJPEAPEAUIMFTransform@@PEAU_GUID@@@Z; CTopoLoaderTransformCreator::CreateSampleRateConverter(IMFTransform * *,_GUID *)
0x1800939ca  mov     esi, eax
0x1800939cc  test    eax, eax
0x1800939ce  jns     loc_180093A91
0x1800939d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800939db  test    rcx, rcx
0x1800939de  jnz     short loc_1800939EC
0x1800939e0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800939e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800939ec  cmp     [rcx+8], bl
  ... truncated ...
```
