# CMFAudioBranchLoader::ConnectToComponentWithUnknownInput(CUnCompToUnCompContext &,COutputTopologyPin &,CInputTopologyPin &)

- ea: `0x1801d5644`
- end: `0x1801d605f`
- name: `?ConnectToComponentWithUnknownInput@CMFAudioBranchLoader@@QEAAJAEAVCUnCompToUnCompContext@@AEAVCOutputTopologyPin@@AEAVCInputTopologyPin@@@Z`
- size: `2587`
- prototype: `__int64 __fastcall(CMFAudioBranchLoader *__hidden this, struct CUnCompToUnCompContext *, struct COutputTopologyPin *, struct CInputTopologyPin *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18016d794`

## callees

- `0x18002fee0`
- `0x18003a41c`
- `0x18003ecb0`
- `0x1800402c0`
- `0x1800483d0`
- `0x180050d6c`
- `0x180063f00`
- `0x18006b388`
- `0x180091eb0`
- `0x180092630`
- `0x18009302c`
- `0x1800ec0e0`
- `0x180192f5c`
- `0x1801d5644`
- `0x180258480`
- `0x1802c2da8`
- `0x1802c5570`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1801d58fd`
- `MFPlat!MFCreateMediaType` at `0x1801d58fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5750`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5818`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5921`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d59fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5abf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5b86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5c4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5d14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5e07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5f80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5750`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5818`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5921`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d59fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5abf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5b86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5c4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5d14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5e07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801d5f80`

## string_xrefs

- `0x1801d569e`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`
- `0x1801d57ad`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`
- `0x1801d5875`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`
- `0x1801d597e`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`
- `0x1801d5a59`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`
- `0x1801d5b1c`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`
- `0x1801d5be4`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`
- `0x1801d5cac`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`
- `0x1801d5d72`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`
- `0x1801d5e65`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`
- `0x1801d5fdd`: `CMFAudioBranchLoader::ConnectToComponentWithUnknownInput`

## pseudocode

```c
__int64 __fastcall CMFAudioBranchLoader::ConnectToComponentWithUnknownInput(
        CTopoConnectorShared **this,
        struct IMFAttributes ***a2,
        struct COutputTopologyPin *a3,
        struct CInputTopologyPin *a4)
{
  struct IMFAttributes **v4; // rax
  int v6; // ebx
  struct IMFAttributes *v9; // r15
  const char *String; // rsi
  char NodeId; // al
  __int64 v12; // rdi
  char v13; // bl
  char v14; // al
  int v15; // r8d
  __int64 v16; // rdx
  HRESULT v17; // edi
  __int64 v18; // r8
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
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
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  int v45; // ebx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  struct IMFAttributesVtbl *lpVtbl; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  const char *v67; // rax
  int v68; // ebx
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v73[8]; // [rsp+50h] [rbp-B0h] BYREF
  IMFMediaType *ppMFType; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v75; // [rsp+60h] [rbp-A0h] BYREF
  int v76; // [rsp+64h] [rbp-9Ch] BYREF
  int v77; // [rsp+68h] [rbp-98h] BYREF
  int v78; // [rsp+6Ch] [rbp-94h] BYREF
  struct IMFMediaType ***v79; // [rsp+70h] [rbp-90h]
  _BYTE v80[192]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v81[192]; // [rsp+140h] [rbp+40h] BYREF
  __int128 Buf1; // [rsp+200h] [rbp+100h] BYREF

  v4 = *a2;
  v79 = (struct IMFMediaType ***)a2;
  v6 = 0;
  ppMFType = 0;
  v9 = *v4;
  CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v81, *v4);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v73,
    "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput",
    378);
  if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
  {
    String = CMFAttributesTrace::GetString((CMFAttributesTrace *)v81, 0);
    NodeId = CTopologyPin::GetNodeId(a4);
    v12 = *((_QWORD *)a4 + 2);
    v13 = NodeId;
    v14 = CTopologyPin::GetNodeId(a3);
    WPP_SF_qqdqds(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      53,
      v15,
      (_DWORD)this,
      *((_QWORD *)a3 + 2),
      v14,
      v12,
      v13,
      (__int64)String);
    v6 = 0;
  }
  Buf1 = 0;
  v17 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, __int128 *))v9->lpVtbl->GetGUID)(
          v9,
          &MF_MT_SUBTYPE,
          &Buf1);
  if ( v17 >= 0 )
  {
    v75 = 0;
    v17 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, unsigned int *))v9->lpVtbl->GetUINT32)(
            v9,
            &MF_MT_AUDIO_NUM_CHANNELS,
            &v75);
    if ( v17 >= 0 )
    {
      if ( memcmp_0(&Buf1, &MFAudioFormat_Float, 0x10u) )
      {
        v17 = -1072875852;
        if ( (unsigned __int8)byte_1803CECE9 >= 4u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 64, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, this);
        v69 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
          CallStackTracing::s_wpInstance = v70;
          if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
          {
            v69 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v69 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v69 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875852 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput",
              429,
              -1072875852);
        }
        if ( g_wppLevels )
        {
          v22 = 65;
          goto LABEL_126;
        }
        goto LABEL_127;
      }
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 56, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, this);
      if ( v75 > 2 )
      {
        v17 = MFCreateMediaType(&ppMFType);
        if ( v17 < 0 )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
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
            if ( *((_DWORD *)v34 + 499) != v17 )
              CallStackContext::TraceFailure(v34, "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput", 400, v17);
          }
          if ( g_wppLevels )
          {
            v22 = 57;
            goto LABEL_126;
          }
          goto LABEL_127;
        }
        ((void (__fastcall *)(struct IMFAttributes *, IMFMediaType *))v9->lpVtbl->CopyAllItems)(v9, ppMFType);
        v17 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                ppMFType,
                &MF_MT_AUDIO_NUM_CHANNELS,
                2);
        if ( v17 < 0 )
        {
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
            if ( *((_DWORD *)v39 + 499) != v17 )
              CallStackContext::TraceFailure(v39, "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput", 403, v17);
          }
          if ( g_wppLevels )
          {
            v22 = 58;
            goto LABEL_126;
          }
          goto LABEL_127;
        }
        v76 = 0;
        v17 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, int *))ppMFType->lpVtbl->GetUINT32)(
                ppMFType,
                &MF_MT_AUDIO_BITS_PER_SAMPLE,
                &v76);
        if ( v17 < 0 )
        {
          v42 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41);
            CallStackTracing::s_wpInstance = v43;
            if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
            {
              v42 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v42 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v42 + 8) )
          {
            v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
            if ( *((_DWORD *)v44 + 499) != v17 )
              CallStackContext::TraceFailure(v44, "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput", 406, v17);
          }
          if ( g_wppLevels )
          {
            v22 = 59;
            goto LABEL_126;
          }
          goto LABEL_127;
        }
        v45 = 2 * v76;
        v17 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                ppMFType,
                &MF_MT_AUDIO_BLOCK_ALIGNMENT,
                (unsigned int)(2 * v76));
        if ( v17 < 0 )
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
            if ( *((_DWORD *)v50 + 499) != v17 )
              CallStackContext::TraceFailure(v50, "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput", 409, v17);
          }
          if ( g_wppLevels )
          {
            v22 = 60;
            goto LABEL_126;
          }
          goto LABEL_127;
        }
        v77 = 0;
        v17 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, int *))ppMFType->lpVtbl->GetUINT32)(
                ppMFType,
                &MF_MT_AUDIO_SAMPLES_PER_SECOND,
                &v77);
        if ( v17 < 0 )
        {
          v53 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52);
            CallStackTracing::s_wpInstance = v54;
            if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
            {
              v53 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v53 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v53 + 8) )
          {
            v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
            if ( *((_DWORD *)v55 + 499) != v17 )
              CallStackContext::TraceFailure(v55, "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput", 412, v17);
          }
          if ( g_wppLevels )
          {
            v22 = 61;
            goto LABEL_126;
          }
          goto LABEL_127;
        }
        v17 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                ppMFType,
                &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
                (unsigned int)(v77 * v45));
        if ( v17 < 0 )
        {
          v58 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57);
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
            if ( *((_DWORD *)v60 + 499) != v17 )
              CallStackContext::TraceFailure(v60, "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput", 413, v17);
          }
          if ( g_wppLevels )
          {
            v22 = 62;
            goto LABEL_126;
          }
          goto LABEL_127;
        }
        lpVtbl = v9->lpVtbl;
        v78 = 0;
        v6 = 1;
        if ( !((unsigned int (__fastcall *)(struct IMFAttributes *, const GUID *, int *))lpVtbl->GetUINT32)(
                v9,
                &MF_MT_AUDIO_CHANNEL_MASK,
                &v78) )
        {
          v17 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                  ppMFType,
                  &MF_MT_AUDIO_CHANNEL_MASK,
                  3);
          if ( v17 < 0 )
          {
            v64 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63);
              CallStackTracing::s_wpInstance = v65;
              if ( v65
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
              {
                v64 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v64 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v64 + 8) )
            {
              v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
              if ( *((_DWORD *)v66 + 499) != v17 )
                CallStackContext::TraceFailure(
                  v66,
                  "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput",
                  420,
                  v17);
            }
            if ( g_wppLevels )
            {
              v22 = 63;
              goto LABEL_126;
            }
            goto LABEL_127;
          }
        }
      }
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, this, v6);
      if ( !v6 )
        goto LABEL_113;
      CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v80, (struct IMFAttributes *)ppMFType);
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      {
        v67 = CMFAttributesTrace::GetString((CMFAttributesTrace *)v80, 0);
        WPP_SF_qs(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          67,
          (unsigned int)&WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids,
          (_DWORD)this,
          (__int64)v67);
      }
      v68 = CTopoConnectorShared::ConnectNodesWithProvidedMediaType(*this, a3, a4, ppMFType);
      CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v80);
      if ( v68 < 0 )
LABEL_113:
        v17 = CMFAudioBranchLoader::ConnectUnknownInputUsingResampler((CMFAudioBranchLoader *)this, a3, **v79, a4);
      goto LABEL_127;
    }
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
      if ( *((_DWORD *)v27 + 499) != v17 )
        CallStackContext::TraceFailure(v27, "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput", 384, v17);
    }
    if ( g_wppLevels )
    {
      v22 = 55;
      goto LABEL_126;
    }
  }
  else
  {
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v18);
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
      if ( *((_DWORD *)v21 + 499) != v17 )
        CallStackContext::TraceFailure(v21, "CMFAudioBranchLoader::ConnectToComponentWithUnknownInput", 381, v17);
    }
    if ( g_wppLevels )
    {
      v22 = 54;
LABEL_126:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, this, v17);
    }
  }
LABEL_127:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v73);
  CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v81);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFType);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1801d5644  push    rbp
0x1801d5646  push    rbx
0x1801d5647  push    rsi
0x1801d5648  push    rdi
0x1801d5649  push    r12
0x1801d564b  push    r13
0x1801d564d  push    r14
0x1801d564f  push    r15
0x1801d5651  lea     rbp, [rsp-128h]
0x1801d5659  sub     rsp, 228h
0x1801d5660  mov     rax, cs:__security_cookie
0x1801d5667  xor     rax, rsp
0x1801d566a  mov     [rbp+160h+var_50], rax
0x1801d5671  mov     rax, [rdx]
0x1801d5674  mov     r14, rcx
0x1801d5677  mov     [rsp+260h+var_1F0], rdx
0x1801d567c  lea     rcx, [rbp+160h+var_120]; this
0x1801d5680  xor     ebx, ebx
0x1801d5682  mov     r12, r9
0x1801d5685  mov     [rsp+260h+ppMFType], rbx
0x1801d568a  mov     r13, r8
0x1801d568d  mov     r15, [rax]
0x1801d5690  mov     rdx, r15; struct IMFAttributes *
0x1801d5693  call    ??0CMFAttributesTrace@@QEAA@PEAUIMFAttributes@@@Z; CMFAttributesTrace::CMFAttributesTrace(IMFAttributes *)
0x1801d5698  mov     r8d, 17Ah; int
0x1801d569e  lea     rdx, aCmfaudiobranch_2; "CMFAudioBranchLoader::ConnectToComponen"...
0x1801d56a5  lea     rcx, [rsp+260h+var_210]; this
0x1801d56aa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801d56af  cmp     cs:byte_1803CECE9, 10h
0x1801d56b6  jb      short loc_1801D5712
0x1801d56b8  xor     edx, edx; bool
0x1801d56ba  lea     rcx, [rbp+160h+var_120]; this
0x1801d56be  call    ?GetString@CMFAttributesTrace@@QEAAPEBD_N@Z; CMFAttributesTrace::GetString(bool)
0x1801d56c3  mov     rcx, r12; this
0x1801d56c6  mov     rsi, rax
0x1801d56c9  call    ?GetNodeId@CTopologyPin@@QEAAKXZ; CTopologyPin::GetNodeId(void)
0x1801d56ce  mov     rdi, [r12+10h]
0x1801d56d3  mov     rcx, r13; this
0x1801d56d6  mov     ebx, eax
0x1801d56d8  call    ?GetNodeId@CTopologyPin@@QEAAKXZ; CTopologyPin::GetNodeId(void)
0x1801d56dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d56e4  mov     edx, 35h ; '5'
0x1801d56e9  mov     [rsp+260h+var_220], rsi
0x1801d56ee  mov     r9, r14
0x1801d56f1  mov     [rsp+260h+var_228], ebx
0x1801d56f5  mov     [rsp+260h+var_230], rdi
0x1801d56fa  mov     rcx, [rcx+38h]
0x1801d56fe  mov     [rsp+260h+var_238], eax
0x1801d5702  mov     rax, [r13+10h]
0x1801d5706  mov     [rsp+260h+var_240], rax
0x1801d570b  call    WPP_SF_qqdqds
0x1801d5710  xor     ebx, ebx
0x1801d5712  xorps   xmm0, xmm0
0x1801d5715  lea     r8, [rbp+160h+Buf1]
0x1801d571c  movups  [rbp+160h+Buf1], xmm0
0x1801d5723  mov     rax, [r15]
0x1801d5726  lea     rdx, MF_MT_SUBTYPE
0x1801d572d  mov     rcx, r15
0x1801d5730  mov     rax, [rax+50h]
0x1801d5734  call    cs:__guard_dispatch_icall_fptr
0x1801d573a  mov     edi, eax
0x1801d573c  test    eax, eax
0x1801d573e  jns     loc_1801D57E2
0x1801d5744  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d574b  test    rcx, rcx
0x1801d574e  jnz     short loc_1801D5798
0x1801d5750  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801d5757  nop     dword ptr [rax+rax+00h]
0x1801d575c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5763  mov     rcx, rax
0x1801d5766  test    rax, rax
0x1801d5769  jz      short loc_1801D578A
0x1801d576b  mov     rax, [rax]
0x1801d576e  mov     edx, 7F0h
0x1801d5773  mov     rax, [rax+8]
0x1801d5777  call    cs:__guard_dispatch_icall_fptr
0x1801d577d  test    eax, eax
0x1801d577f  jz      short loc_1801D578A
0x1801d5781  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5788  jmp     short loc_1801D5798
0x1801d578a  lea     rcx, qword_1803CE250; this
0x1801d5791  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5798  cmp     [rcx+8], bl
0x1801d579b  jz      short loc_1801D57C2
0x1801d579d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801d57a2  cmp     [rax+7CCh], edi
0x1801d57a8  jz      short loc_1801D57C2
0x1801d57aa  mov     r9d, edi; int
0x1801d57ad  lea     rdx, aCmfaudiobranch_2; "CMFAudioBranchLoader::ConnectToComponen"...
0x1801d57b4  mov     r8d, 17Dh; int
0x1801d57ba  mov     rcx, rax; this
0x1801d57bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801d57c2  mov     ebx, 1
0x1801d57c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801d57cd  jb      loc_1801D601C
0x1801d57d3  lea     edx, [rbx+35h]
0x1801d57d6  lea     r8, WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids
0x1801d57dd  jmp     loc_1801D6005
0x1801d57e2  mov     [rsp+260h+var_200], ebx
0x1801d57e6  lea     r8, [rsp+260h+var_200]
0x1801d57eb  mov     rax, [r15]
0x1801d57ee  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x1801d57f5  mov     rcx, r15
0x1801d57f8  mov     rax, [rax+38h]
0x1801d57fc  call    cs:__guard_dispatch_icall_fptr
0x1801d5802  mov     edi, eax
0x1801d5804  test    eax, eax
0x1801d5806  jns     loc_1801D58A3
0x1801d580c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5813  test    rcx, rcx
0x1801d5816  jnz     short loc_1801D5860
0x1801d5818  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801d581f  nop     dword ptr [rax+rax+00h]
0x1801d5824  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d582b  mov     rcx, rax
0x1801d582e  test    rax, rax
0x1801d5831  jz      short loc_1801D5852
0x1801d5833  mov     rax, [rax]
0x1801d5836  mov     edx, 7F0h
0x1801d583b  mov     rax, [rax+8]
0x1801d583f  call    cs:__guard_dispatch_icall_fptr
0x1801d5845  test    eax, eax
0x1801d5847  jz      short loc_1801D5852
0x1801d5849  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5850  jmp     short loc_1801D5860
0x1801d5852  lea     rcx, qword_1803CE250; this
0x1801d5859  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5860  cmp     [rcx+8], bl
0x1801d5863  jz      short loc_1801D588A
0x1801d5865  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801d586a  cmp     [rax+7CCh], edi
0x1801d5870  jz      short loc_1801D588A
0x1801d5872  mov     r9d, edi; int
0x1801d5875  lea     rdx, aCmfaudiobranch_2; "CMFAudioBranchLoader::ConnectToComponen"...
0x1801d587c  mov     r8d, 180h; int
0x1801d5882  mov     rcx, rax; this
0x1801d5885  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801d588a  mov     ebx, 1
0x1801d588f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801d5895  jb      loc_1801D601C
0x1801d589b  lea     edx, [rbx+36h]
0x1801d589e  jmp     loc_1801D57D6
0x1801d58a3  mov     r8d, 10h; Size
0x1801d58a9  lea     rdx, MFAudioFormat_Float; Buf2
0x1801d58b0  lea     rcx, [rbp+160h+Buf1]; Buf1
0x1801d58b7  call    memcmp_0
0x1801d58bc  test    eax, eax
0x1801d58be  jnz     loc_1801D5F44
0x1801d58c4  cmp     cs:byte_1803CECE9, 10h
0x1801d58cb  lea     rsi, WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids
0x1801d58d2  jb      short loc_1801D58ED
0x1801d58d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d58db  lea     edx, [rax+38h]
0x1801d58de  mov     r9, r14
0x1801d58e1  mov     r8, rsi
0x1801d58e4  mov     rcx, [rcx+38h]
0x1801d58e8  call    WPP_SF_q
0x1801d58ed  cmp     [rsp+260h+var_200], 2
0x1801d58f2  jbe     loc_1801D5E90
0x1801d58f8  lea     rcx, [rsp+260h+ppMFType]; ppMFType
0x1801d58fd  call    cs:__imp_MFCreateMediaType
0x1801d5904  nop     dword ptr [rax+rax+00h]
0x1801d5909  xor     ebx, ebx
0x1801d590b  mov     edi, eax
0x1801d590d  test    eax, eax
0x1801d590f  jns     loc_1801D59AC
0x1801d5915  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d591c  test    rcx, rcx
0x1801d591f  jnz     short loc_1801D5969
0x1801d5921  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801d5928  nop     dword ptr [rax+rax+00h]
0x1801d592d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5934  mov     rcx, rax
0x1801d5937  test    rax, rax
0x1801d593a  jz      short loc_1801D595B
0x1801d593c  mov     rax, [rax]
0x1801d593f  mov     edx, 7F0h
0x1801d5944  mov     rax, [rax+8]
0x1801d5948  call    cs:__guard_dispatch_icall_fptr
0x1801d594e  test    eax, eax
0x1801d5950  jz      short loc_1801D595B
0x1801d5952  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5959  jmp     short loc_1801D5969
0x1801d595b  lea     rcx, qword_1803CE250; this
0x1801d5962  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5969  cmp     [rcx+8], bl
0x1801d596c  jz      short loc_1801D5993
0x1801d596e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801d5973  cmp     [rax+7CCh], edi
0x1801d5979  jz      short loc_1801D5993
0x1801d597b  mov     r9d, edi; int
0x1801d597e  lea     rdx, aCmfaudiobranch_2; "CMFAudioBranchLoader::ConnectToComponen"...
0x1801d5985  mov     r8d, 190h; int
0x1801d598b  mov     rcx, rax; this
0x1801d598e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801d5993  mov     ebx, 1
0x1801d5998  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801d599e  jb      loc_1801D601C
0x1801d59a4  lea     edx, [rbx+38h]
0x1801d59a7  jmp     loc_1801D6002
0x1801d59ac  mov     rax, [r15]
0x1801d59af  mov     rcx, r15
0x1801d59b2  mov     rdx, [rsp+260h+ppMFType]
0x1801d59b7  mov     rax, [rax+100h]
0x1801d59be  call    cs:__guard_dispatch_icall_fptr
0x1801d59c4  mov     rcx, [rsp+260h+ppMFType]
0x1801d59c9  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x1801d59d0  mov     r8d, 2
0x1801d59d6  mov     rax, [rcx]
0x1801d59d9  mov     rax, [rax+0A8h]
0x1801d59e0  call    cs:__guard_dispatch_icall_fptr
0x1801d59e6  mov     edi, eax
0x1801d59e8  test    eax, eax
0x1801d59ea  jns     loc_1801D5A87
0x1801d59f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d59f7  test    rcx, rcx
0x1801d59fa  jnz     short loc_1801D5A44
0x1801d59fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801d5a03  nop     dword ptr [rax+rax+00h]
0x1801d5a08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5a0f  mov     rcx, rax
0x1801d5a12  test    rax, rax
0x1801d5a15  jz      short loc_1801D5A36
0x1801d5a17  mov     rax, [rax]
0x1801d5a1a  mov     edx, 7F0h
0x1801d5a1f  mov     rax, [rax+8]
0x1801d5a23  call    cs:__guard_dispatch_icall_fptr
0x1801d5a29  test    eax, eax
0x1801d5a2b  jz      short loc_1801D5A36
0x1801d5a2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5a34  jmp     short loc_1801D5A44
0x1801d5a36  lea     rcx, qword_1803CE250; this
0x1801d5a3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5a44  cmp     [rcx+8], bl
0x1801d5a47  jz      short loc_1801D5A6E
0x1801d5a49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801d5a4e  cmp     [rax+7CCh], edi
0x1801d5a54  jz      short loc_1801D5A6E
0x1801d5a56  mov     r9d, edi; int
0x1801d5a59  lea     rdx, aCmfaudiobranch_2; "CMFAudioBranchLoader::ConnectToComponen"...
0x1801d5a60  mov     r8d, 193h; int
0x1801d5a66  mov     rcx, rax; this
0x1801d5a69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801d5a6e  mov     ebx, 1
0x1801d5a73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801d5a79  jb      loc_1801D601C
0x1801d5a7f  lea     edx, [rbx+39h]
0x1801d5a82  jmp     loc_1801D6002
0x1801d5a87  mov     rcx, [rsp+260h+ppMFType]
0x1801d5a8c  lea     r8, [rsp+260h+var_1FC]
0x1801d5a91  mov     [rsp+260h+var_1FC], ebx
0x1801d5a95  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x1801d5a9c  mov     rax, [rcx]
0x1801d5a9f  mov     rax, [rax+38h]
0x1801d5aa3  call    cs:__guard_dispatch_icall_fptr
0x1801d5aa9  mov     edi, eax
0x1801d5aab  test    eax, eax
0x1801d5aad  jns     loc_1801D5B4A
0x1801d5ab3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5aba  test    rcx, rcx
0x1801d5abd  jnz     short loc_1801D5B07
0x1801d5abf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801d5ac6  nop     dword ptr [rax+rax+00h]
0x1801d5acb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5ad2  mov     rcx, rax
0x1801d5ad5  test    rax, rax
0x1801d5ad8  jz      short loc_1801D5AF9
0x1801d5ada  mov     rax, [rax]
0x1801d5add  mov     edx, 7F0h
0x1801d5ae2  mov     rax, [rax+8]
0x1801d5ae6  call    cs:__guard_dispatch_icall_fptr
0x1801d5aec  test    eax, eax
0x1801d5aee  jz      short loc_1801D5AF9
0x1801d5af0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5af7  jmp     short loc_1801D5B07
0x1801d5af9  lea     rcx, qword_1803CE250; this
0x1801d5b00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801d5b07  cmp     [rcx+8], bl
0x1801d5b0a  jz      short loc_1801D5B31
0x1801d5b0c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801d5b11  cmp     [rax+7CCh], edi
0x1801d5b17  jz      short loc_1801D5B31
0x1801d5b19  mov     r9d, edi; int
0x1801d5b1c  lea     rdx, aCmfaudiobranch_2; "CMFAudioBranchLoader::ConnectToComponen"...
0x1801d5b23  mov     r8d, 196h; int
0x1801d5b29  mov     rcx, rax; this
0x1801d5b2c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801d5b31  mov     ebx, 1
0x1801d5b36  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801d5b3c  jb      loc_1801D601C
0x1801d5b42  lea     edx, [rbx+3Ah]
0x1801d5b45  jmp     loc_1801D6002
0x1801d5b4a  mov     eax, [rsp+260h+var_1FC]
0x1801d5b4e  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x1801d5b55  mov     rcx, [rsp+260h+ppMFType]
0x1801d5b5a  lea     ebx, [rax+rax]
0x1801d5b5d  mov     rax, [rcx]
0x1801d5b60  mov     r8d, ebx
0x1801d5b63  mov     rax, [rax+0A8h]
0x1801d5b6a  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
