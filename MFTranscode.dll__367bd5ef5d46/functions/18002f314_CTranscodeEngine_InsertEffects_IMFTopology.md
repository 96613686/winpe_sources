# CTranscodeEngine::_InsertEffects(IMFTopology *)

- ea: `0x18002f314`
- end: `0x18002fecd`
- name: `?_InsertEffects@CTranscodeEngine@@IEAAJPEAUIMFTopology@@@Z`
- size: `3001`
- prototype: `__int64 __fastcall(CTranscodeEngine *__hidden this, struct IMFTopology *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18002e75c`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18000abc8`
- `0x18000b3ac`
- `0x1800153ac`
- `0x18001a320`
- `0x18001a330`
- `0x18001c280`
- `0x18002f314`
- `0x18003126c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f37b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f591`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f833`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f8c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f976`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fa06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fa96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fb26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fbb6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fc46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fcd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fd66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fdf6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f37b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f591`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f833`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f8c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f976`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fa06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fa96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fb26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fbb6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fc46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fcd6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fd66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fdf6`
- `MFCORE!MFCreateTopologyNode` at `0x18002f610`
- `MFCORE!MFCreateTopologyNode` at `0x18002f610`

## pseudocode

```c
__int64 __fastcall CTranscodeEngine::_InsertEffects(__int64 **this, struct IMFTopology *a2)
{
  __int64 v4; // rdx
  HRESULT SourceNodes; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v9; // r13
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r14
  __int64 v13; // rax
  unsigned __int8 v14; // r15
  int v15; // ecx
  __int64 v16; // r8
  bool v17; // zf
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  struct IMFTopologyNode **v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  struct IMFTopologyNode *v71; // [rsp+40h] [rbp-20h] BYREF
  struct IMFTopologyNode *v72; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v73[2]; // [rsp+50h] [rbp-10h] BYREF
  int v74; // [rsp+A0h] [rbp+40h] BYREF
  IMFTopologyNode *ppNode; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v76; // [rsp+B8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v74, "CTranscodeEngine::_InsertEffects", 623);
  v72 = 0;
  v71 = 0;
  SourceNodes = CTranscodeEngine::_GetSourceNodes((CTranscodeEngine *)this, a2, &v72, &v71);
  if ( SourceNodes < 0 )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != SourceNodes )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeEngine::_InsertEffects", 629, SourceNodes);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids,
        this,
        SourceNodes);
    goto LABEL_173;
  }
  v9 = this[81];
LABEL_13:
  while ( 2 )
  {
    v10 = *(_QWORD *)&MFMediaType_Audio.Data1;
    v11 = *(_QWORD *)MFMediaType_Audio.Data4;
    while ( 1 )
    {
      if ( !v9 )
        goto LABEL_173;
      v12 = *v9;
      v9 = (__int64 *)v9[1];
      v13 = *(_QWORD *)v12 - v10;
      if ( *(_QWORD *)v12 == v10 )
        v13 = *(_QWORD *)(v12 + 8) - v11;
      if ( v13 )
        break;
      v14 = 1;
      if ( v72 )
        goto LABEL_23;
LABEL_21:
      if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() )
      {
        WPP_SF_qqdd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          80,
          v10,
          this,
          *(_QWORD *)(v12 + 16),
          v15,
          *(_DWORD *)(v12 + 24));
        goto LABEL_13;
      }
    }
    v14 = 0;
    if ( !v71 )
      goto LABEL_21;
LABEL_23:
    if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() )
      WPP_SF_qqdd(*((_QWORD *)WPP_GLOBAL_Control + 7), 81, v16, this, *(_QWORD *)(v12 + 16), v14, *(_DWORD *)(v12 + 24));
    if ( v14 )
      goto LABEL_37;
    v17 = *((_DWORD *)this + 19) == 0;
    v73[0] = 0;
    if ( !v17
      || (*(int (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(v12 + 16) + 64LL))(*(_QWORD *)(v12 + 16), v73) < 0
      || !(unsigned int)MFGetAttributeUINT32(v73[0], MF_SA_D3D11_AWARE, 0) )
    {
      SourceNodes = ((__int64 (__fastcall *)(struct IMFTopology *, const IID *, __int64))a2->lpVtbl->SetUINT32)(
                      a2,
                      &MF_TOPOLOGY_DXVA_MODE,
                      1);
      if ( SourceNodes >= 0 )
        goto LABEL_36;
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != SourceNodes )
          CallStackContext::TraceFailure(v37, "CTranscodeEngine::_InsertEffects", 685, SourceNodes);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v34 = 83;
LABEL_57:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v34,
          &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids,
          this,
          SourceNodes);
      }
LABEL_58:
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v73);
      goto LABEL_173;
    }
    if ( (unsigned int)MFGetAttributeUINT32(a2, &MF_TOPOLOGY_DXVA_MODE, 0) != 1 )
    {
      SourceNodes = ((__int64 (__fastcall *)(struct IMFTopology *, const IID *, __int64))a2->lpVtbl->SetUINT32)(
                      a2,
                      &MF_TOPOLOGY_DXVA_MODE,
                      2);
      if ( SourceNodes < 0 )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)v33 + 499) != SourceNodes )
            CallStackContext::TraceFailure(v33, "CTranscodeEngine::_InsertEffects", 680, SourceNodes);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v34 = 82;
          goto LABEL_57;
        }
        goto LABEL_58;
      }
    }
LABEL_36:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v73);
LABEL_37:
    ppNode = 0;
    SourceNodes = MFCreateTopologyNode(MF_TOPOLOGY_TRANSFORM_NODE, &ppNode);
    if ( SourceNodes < 0 )
    {
      v67 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
        CallStackTracing::s_wpInstance = v68;
        if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
        {
          v67 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v67 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v67 + 8) )
      {
        v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
        if ( *((_DWORD *)v69 + 499) != SourceNodes )
          CallStackContext::TraceFailure(v69, "CTranscodeEngine::_InsertEffects", 694, SourceNodes);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_172;
      v60 = 84;
LABEL_171:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v60,
        &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids,
        this,
        SourceNodes);
      goto LABEL_172;
    }
    SourceNodes = ((__int64 (__fastcall *)(IMFTopologyNode *, _QWORD))ppNode->lpVtbl->SetObject)(
                    ppNode,
                    *(_QWORD *)(v12 + 16));
    if ( SourceNodes < 0 )
    {
      v64 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
        CallStackTracing::s_wpInstance = v65;
        if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
        {
          v64 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v64 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v64 + 8) )
      {
        v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
        if ( *((_DWORD *)v66 + 499) != SourceNodes )
          CallStackContext::TraceFailure(v66, "CTranscodeEngine::_InsertEffects", 696, SourceNodes);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_172;
      v60 = 85;
      goto LABEL_171;
    }
    SourceNodes = ((__int64 (__fastcall *)(IMFTopologyNode *, const IID *, _QWORD))ppNode->lpVtbl->SetUINT32)(
                    ppNode,
                    &MF_TOPONODE_CONNECT_METHOD,
                    *(_DWORD *)(v12 + 24) != 0 ? 3 : 65539);
    if ( SourceNodes < 0 )
    {
      v61 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
        CallStackTracing::s_wpInstance = v62;
        if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
        {
          v61 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v61 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v61 + 8) )
      {
        v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
        if ( *((_DWORD *)v63 + 499) != SourceNodes )
          CallStackContext::TraceFailure(v63, "CTranscodeEngine::_InsertEffects", 703, SourceNodes);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_172;
      v60 = 86;
      goto LABEL_171;
    }
    SourceNodes = ((__int64 (__fastcall *)(struct IMFTopology *, IMFTopologyNode *))a2->lpVtbl->AddNode)(a2, ppNode);
    if ( SourceNodes < 0 )
    {
      v57 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v58;
        if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
        {
          v57 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v57 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v57 + 8) )
      {
        v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
        if ( *((_DWORD *)v59 + 499) != SourceNodes )
          CallStackContext::TraceFailure(v59, "CTranscodeEngine::_InsertEffects", 709, SourceNodes);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_172;
      v60 = 87;
      goto LABEL_171;
    }
    v74 = 0;
    v76 = 0;
    if ( !v14 )
    {
      SourceNodes = ((__int64 (__fastcall *)(struct IMFTopologyNode *, _QWORD, __int64 *, int *))v71->lpVtbl->GetOutput)(
                      v71,
                      0,
                      &v76,
                      &v74);
      if ( SourceNodes < 0 )
      {
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v54 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != SourceNodes )
            CallStackContext::TraceFailure(v56, "CTranscodeEngine::_InsertEffects", 729, SourceNodes);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_80;
        v41 = 91;
      }
      else
      {
        SourceNodes = ((__int64 (__fastcall *)(struct IMFTopologyNode *, _QWORD, IMFTopologyNode *, _QWORD))v71->lpVtbl->ConnectOutput)(
                        v71,
                        0,
                        ppNode,
                        0);
        if ( SourceNodes < 0 )
        {
          v51 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
            CallStackTracing::s_wpInstance = v52;
            if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
            {
              v51 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v51 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v51 + 8) )
          {
            v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
            if ( *((_DWORD *)v53 + 499) != SourceNodes )
              CallStackContext::TraceFailure(v53, "CTranscodeEngine::_InsertEffects", 731, SourceNodes);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_80;
          v41 = 92;
        }
        else
        {
          SourceNodes = ((__int64 (__fastcall *)(IMFTopologyNode *, _QWORD, __int64, _QWORD))ppNode->lpVtbl->ConnectOutput)(
                          ppNode,
                          0,
                          v76,
                          0);
          if ( SourceNodes >= 0 )
          {
            v29 = &v71;
            goto LABEL_50;
          }
          v48 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
            CallStackTracing::s_wpInstance = v49;
            if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
            {
              v48 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v48 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v48 + 8) )
          {
            v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
            if ( *((_DWORD *)v50 + 499) != SourceNodes )
              CallStackContext::TraceFailure(v50, "CTranscodeEngine::_InsertEffects", 734, SourceNodes);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_80;
          v41 = 93;
        }
      }
LABEL_79:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v41,
        &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids,
        this,
        SourceNodes);
      goto LABEL_80;
    }
    SourceNodes = ((__int64 (__fastcall *)(struct IMFTopologyNode *, _QWORD, __int64 *, int *))v72->lpVtbl->GetOutput)(
                    v72,
                    0,
                    &v76,
                    &v74);
    if ( SourceNodes < 0 )
    {
      v45 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v45 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != SourceNodes )
          CallStackContext::TraceFailure(v47, "CTranscodeEngine::_InsertEffects", 717, SourceNodes);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_80;
      v41 = 88;
      goto LABEL_79;
    }
    SourceNodes = ((__int64 (__fastcall *)(struct IMFTopologyNode *, _QWORD, IMFTopologyNode *, _QWORD))v72->lpVtbl->ConnectOutput)(
                    v72,
                    0,
                    ppNode,
                    0);
    if ( SourceNodes < 0 )
    {
      v42 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) != SourceNodes )
          CallStackContext::TraceFailure(v44, "CTranscodeEngine::_InsertEffects", 719, SourceNodes);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_80;
      v41 = 89;
      goto LABEL_79;
    }
    SourceNodes = ((__int64 (__fastcall *)(IMFTopologyNode *, _QWORD, __int64, _QWORD))ppNode->lpVtbl->ConnectOutput)(
                    ppNode,
                    0,
                    v76,
                    0);
    if ( SourceNodes >= 0 )
    {
      v29 = &v72;
LABEL_50:
      ComSmartPtr<IMFMediaSource>::operator=(v29, &ppNode);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v76);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppNode);
      continue;
    }
    break;
  }
  v38 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
    CallStackTracing::s_wpInstance = v39;
    if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
    {
      v38 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v38 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v38 + 8) )
  {
    v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
    if ( *((_DWORD *)v40 + 499) != SourceNodes )
      CallStackContext::TraceFailure(v40, "CTranscodeEngine::_InsertEffects", 722, SourceNodes);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v41 = 90;
    goto LABEL_79;
  }
LABEL_80:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v76);
LABEL_172:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppNode);
LABEL_173:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v71);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v72);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v74);
  return (unsigned int)SourceNodes;
}

```

## disassembly

```asm
0x18002f314  mov     [rsp-38h+arg_8], rbx
0x18002f319  push    rbp
0x18002f31a  push    rsi
0x18002f31b  push    rdi
0x18002f31c  push    r12
0x18002f31e  push    r13
0x18002f320  push    r14
0x18002f322  push    r15
0x18002f324  mov     rbp, rsp
0x18002f327  sub     rsp, 60h
0x18002f32b  mov     r12, rdx
0x18002f32e  mov     rsi, rcx
0x18002f331  lea     rdx, aCtranscodeengi_13; "CTranscodeEngine::_InsertEffects"
0x18002f338  mov     r8d, 26Fh; int
0x18002f33e  lea     rcx, [rbp+arg_0]; this
0x18002f342  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002f347  xor     r14d, r14d
0x18002f34a  lea     r9, [rbp+var_20]; struct IMFTopologyNode **
0x18002f34e  lea     r8, [rbp+var_18]; struct IMFTopologyNode **
0x18002f352  mov     [rbp+var_18], r14
0x18002f356  mov     rdx, r12; struct IMFTopology *
0x18002f359  mov     [rbp+var_20], r14
0x18002f35d  mov     rcx, rsi; this
0x18002f360  call    ?_GetSourceNodes@CTranscodeEngine@@IEAAJPEAUIMFTopology@@PEAPEAUIMFTopologyNode@@1@Z; CTranscodeEngine::_GetSourceNodes(IMFTopology *,IMFTopologyNode * *,IMFTopologyNode * *)
0x18002f365  mov     ebx, eax
0x18002f367  test    eax, eax
0x18002f369  jns     loc_18002F420
0x18002f36f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f376  test    rcx, rcx
0x18002f379  jnz     short loc_18002F3BC
0x18002f37b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f381  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f388  mov     rcx, rax
0x18002f38b  test    rax, rax
0x18002f38e  jz      short loc_18002F3AE
0x18002f390  mov     rax, [rax]
0x18002f393  mov     edx, 7F0h
0x18002f398  mov     rax, [rax+8]
0x18002f39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3a1  test    eax, eax
0x18002f3a3  jz      short loc_18002F3AE
0x18002f3a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f3ac  jmp     short loc_18002F3BC
0x18002f3ae  lea     rcx, qword_180069A90; this
0x18002f3b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f3bc  cmp     [rcx+8], r14b
0x18002f3c0  jz      short loc_18002F3E7
0x18002f3c2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f3c7  cmp     [rax+7CCh], ebx
0x18002f3cd  jz      short loc_18002F3E7
0x18002f3cf  mov     r9d, ebx; int
0x18002f3d2  lea     rdx, aCtranscodeengi_13; "CTranscodeEngine::_InsertEffects"
0x18002f3d9  mov     r8d, 275h; int
0x18002f3df  mov     rcx, rax; this
0x18002f3e2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002f3e7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f3ec  mov     edi, 1
0x18002f3f1  cmp     al, dil
0x18002f3f4  jb      loc_18002FE98
0x18002f3fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f401  lea     edx, [rdi+4Eh]
0x18002f404  mov     r9, rsi
0x18002f407  mov     dword ptr [rsp+60h+var_40], ebx
0x18002f40b  lea     r8, WPP_e568207c201a3850f272ae9c45155cdf_Traceguids
0x18002f412  mov     rcx, [rcx+10h]
0x18002f416  call    WPP_SF_qd
0x18002f41b  jmp     loc_18002FE98
0x18002f420  mov     r13, [rsi+288h]
0x18002f427  mov     edi, 1
0x18002f42c  mov     r8, qword ptr cs:MFMediaType_Audio.Data1
0x18002f433  mov     rdx, qword ptr cs:MFMediaType_Audio.Data4
0x18002f43a  test    r13, r13
0x18002f43d  jz      loc_18002FE98
0x18002f443  mov     r14, [r13+0]
0x18002f447  mov     r13, [r13+8]
0x18002f44b  mov     rax, [r14]
0x18002f44e  sub     rax, r8
0x18002f451  jnz     short loc_18002F45A
0x18002f453  mov     rax, [r14+8]
0x18002f457  sub     rax, rdx
0x18002f45a  test    rax, rax
0x18002f45d  jnz     short loc_18002F46C
0x18002f45f  mov     r15b, dil
0x18002f462  cmp     [rbp+var_18], rax
0x18002f466  jnz     short loc_18002F4B4
0x18002f468  mov     ecx, edi
0x18002f46a  jmp     short loc_18002F478
0x18002f46c  xor     r15b, r15b
0x18002f46f  cmp     [rbp+var_20], 0
0x18002f474  jnz     short loc_18002F4B4
0x18002f476  xor     ecx, ecx
0x18002f478  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x18002f47d  cmp     al, dil
0x18002f480  jb      short loc_18002F43A
0x18002f482  mov     eax, [r14+18h]
0x18002f486  mov     edx, 50h ; 'P'
0x18002f48b  mov     [rsp+60h+var_30], eax
0x18002f48f  mov     r9, rsi
0x18002f492  mov     rax, [r14+10h]
0x18002f496  mov     [rsp+60h+var_38], ecx
0x18002f49a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4a1  mov     [rsp+60h+var_40], rax
0x18002f4a6  mov     rcx, [rcx+38h]
0x18002f4aa  call    WPP_SF_qqdd
0x18002f4af  jmp     loc_18002F42C
0x18002f4b4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x18002f4b9  cmp     al, dil
0x18002f4bc  jb      short loc_18002F4EF
0x18002f4be  mov     eax, [r14+18h]
0x18002f4c2  mov     edx, 51h ; 'Q'
0x18002f4c7  mov     [rsp+60h+var_30], eax
0x18002f4cb  mov     r9, rsi
0x18002f4ce  mov     rax, [r14+10h]
0x18002f4d2  movzx   ecx, r15b
0x18002f4d6  mov     [rsp+60h+var_38], ecx
0x18002f4da  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4e1  mov     [rsp+60h+var_40], rax
0x18002f4e6  mov     rcx, [rcx+38h]
0x18002f4ea  call    WPP_SF_qqdd
0x18002f4ef  test    r15b, r15b
0x18002f4f2  jnz     loc_18002F5FF
0x18002f4f8  cmp     dword ptr [rsi+4Ch], 0
0x18002f4fc  mov     [rbp+var_10], 0
0x18002f504  jnz     loc_18002F5CF
0x18002f50a  mov     rcx, [r14+10h]
0x18002f50e  lea     rdx, [rbp+var_10]
0x18002f512  mov     rax, [rcx]
0x18002f515  mov     rax, [rax+40h]
0x18002f519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f51e  test    eax, eax
0x18002f520  js      loc_18002F5CF
0x18002f526  mov     rcx, [rbp+var_10]
0x18002f52a  lea     rdx, MF_SA_D3D11_AWARE
0x18002f531  xor     r8d, r8d
0x18002f534  call    MFGetAttributeUINT32
0x18002f539  test    eax, eax
0x18002f53b  jz      loc_18002F5CF
0x18002f541  xor     r8d, r8d
0x18002f544  lea     rdx, MF_TOPOLOGY_DXVA_MODE
0x18002f54b  mov     rcx, r12
0x18002f54e  call    MFGetAttributeUINT32
0x18002f553  cmp     eax, edi
0x18002f555  jz      loc_18002F5F6
0x18002f55b  mov     rax, [r12]
0x18002f55f  lea     rdx, MF_TOPOLOGY_DXVA_MODE
0x18002f566  mov     r8d, 2
0x18002f56c  mov     rcx, r12
0x18002f56f  mov     rax, [rax+0A8h]
0x18002f576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f57b  mov     ebx, eax
0x18002f57d  test    eax, eax
0x18002f57f  jns     short loc_18002F5F6
0x18002f581  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f588  test    rcx, rcx
0x18002f58b  jnz     loc_18002F7C1
0x18002f591  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f597  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f59e  mov     rcx, rax
0x18002f5a1  test    rax, rax
0x18002f5a4  jz      loc_18002F7B3
0x18002f5aa  mov     rax, [rax]
0x18002f5ad  mov     edx, 7F0h
0x18002f5b2  mov     rax, [rax+8]
0x18002f5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5bb  test    eax, eax
0x18002f5bd  jz      loc_18002F7B3
0x18002f5c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f5ca  jmp     loc_18002F7C1
0x18002f5cf  mov     rax, [r12]
0x18002f5d3  lea     rdx, MF_TOPOLOGY_DXVA_MODE
0x18002f5da  mov     r8d, edi
0x18002f5dd  mov     rcx, r12
0x18002f5e0  mov     rax, [rax+0A8h]
0x18002f5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5ec  mov     ebx, eax
0x18002f5ee  test    eax, eax
0x18002f5f0  js      loc_18002F827
0x18002f5f6  lea     rcx, [rbp+var_10]
0x18002f5fa  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002f5ff  lea     rdx, [rbp+ppNode]; ppNode
0x18002f603  mov     [rbp+ppNode], 0
0x18002f60b  mov     ecx, 2; NodeType
0x18002f610  call    cs:__imp_MFCreateTopologyNode
0x18002f616  mov     ebx, eax
0x18002f618  test    eax, eax
0x18002f61a  js      loc_18002FDEA
0x18002f620  mov     rcx, [rbp+ppNode]
0x18002f624  mov     rdx, [r14+10h]
0x18002f628  mov     rax, [rcx]
0x18002f62b  mov     rax, [rax+108h]
0x18002f632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f637  mov     ebx, eax
0x18002f639  test    eax, eax
0x18002f63b  js      loc_18002FD5A
0x18002f641  mov     eax, [r14+18h]
0x18002f645  lea     rdx, MF_TOPONODE_CONNECT_METHOD
0x18002f64c  mov     rcx, [rbp+ppNode]
0x18002f650  neg     eax
0x18002f652  sbb     r8d, r8d
0x18002f655  and     r8d, 0FFFF0000h
0x18002f65c  mov     r9, [rcx]
0x18002f65f  add     r8d, 10003h
0x18002f666  mov     rax, [r9+0A8h]
0x18002f66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f672  xor     r14d, r14d
0x18002f675  mov     ebx, eax
0x18002f677  test    eax, eax
0x18002f679  js      loc_18002FCCA
0x18002f67f  mov     rax, [r12]
0x18002f683  mov     rcx, r12
0x18002f686  mov     rdx, [rbp+ppNode]
0x18002f68a  mov     rax, [rax+110h]
0x18002f691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f696  mov     ebx, eax
0x18002f698  test    eax, eax
0x18002f69a  js      loc_18002FC3A
0x18002f6a0  xor     edx, edx
0x18002f6a2  mov     [rbp+arg_0], r14d
0x18002f6a6  mov     [rbp+arg_18], r14
0x18002f6aa  lea     r9, [rbp+arg_0]
0x18002f6ae  lea     r8, [rbp+arg_18]
0x18002f6b2  test    r15b, r15b
0x18002f6b5  jz      short loc_18002F726
0x18002f6b7  mov     rcx, [rbp+var_18]
0x18002f6bb  mov     rax, [rcx]
0x18002f6be  mov     rax, [rax+158h]
0x18002f6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6ca  mov     ebx, eax
0x18002f6cc  test    eax, eax
0x18002f6ce  js      loc_18002F9FA
0x18002f6d4  mov     rcx, [rbp+var_18]
0x18002f6d8  xor     r9d, r9d
0x18002f6db  mov     r8, [rbp+ppNode]
0x18002f6df  xor     edx, edx
0x18002f6e1  mov     rax, [rcx]
0x18002f6e4  mov     rax, [rax+140h]
0x18002f6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6f0  mov     ebx, eax
0x18002f6f2  test    eax, eax
0x18002f6f4  js      loc_18002F96A
0x18002f6fa  mov     rcx, [rbp+ppNode]
0x18002f6fe  xor     r9d, r9d
0x18002f701  mov     r8, [rbp+arg_18]
0x18002f705  xor     edx, edx
0x18002f707  mov     rax, [rcx]
0x18002f70a  mov     rax, [rax+140h]
0x18002f711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f716  mov     ebx, eax
0x18002f718  test    eax, eax
0x18002f71a  js      loc_18002F8B7
0x18002f720  lea     rcx, [rbp+var_18]
0x18002f724  jmp     short loc_18002F793
0x18002f726  mov     rcx, [rbp+var_20]
0x18002f72a  mov     rax, [rcx]
0x18002f72d  mov     rax, [rax+158h]
0x18002f734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f739  mov     ebx, eax
0x18002f73b  test    eax, eax
0x18002f73d  js      loc_18002FBAA
0x18002f743  mov     rcx, [rbp+var_20]
0x18002f747  xor     r9d, r9d
0x18002f74a  mov     r8, [rbp+ppNode]
0x18002f74e  xor     edx, edx
0x18002f750  mov     rax, [rcx]
0x18002f753  mov     rax, [rax+140h]
0x18002f75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f75f  mov     ebx, eax
0x18002f761  test    eax, eax
0x18002f763  js      loc_18002FB1A
0x18002f769  mov     rcx, [rbp+ppNode]
0x18002f76d  xor     r9d, r9d
0x18002f770  mov     r8, [rbp+arg_18]
0x18002f774  xor     edx, edx
0x18002f776  mov     rax, [rcx]
0x18002f779  mov     rax, [rax+140h]
0x18002f780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f785  mov     ebx, eax
0x18002f787  test    eax, eax
0x18002f789  js      loc_18002FA8A
0x18002f78f  lea     rcx, [rbp+var_20]
0x18002f793  lea     rdx, [rbp+ppNode]
0x18002f797  call    ??4?$ComSmartPtr@UIMFMediaSource@@@@QEAAPEAUIMFMediaSource@@AEBV0@@Z; ComSmartPtr<IMFMediaSource>::operator=(ComSmartPtr<IMFMediaSource> const &)
0x18002f79c  lea     rcx, [rbp+arg_18]
0x18002f7a0  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002f7a5  lea     rcx, [rbp+ppNode]
0x18002f7a9  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002f7ae  jmp     loc_18002F42C
0x18002f7b3  lea     rcx, qword_180069A90; this
0x18002f7ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f7c1  cmp     byte ptr [rcx+8], 0
0x18002f7c5  jz      short loc_18002F7EC
0x18002f7c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f7cc  cmp     [rax+7CCh], ebx
0x18002f7d2  jz      short loc_18002F7EC
0x18002f7d4  mov     r9d, ebx; int
0x18002f7d7  lea     rdx, aCtranscodeengi_13; "CTranscodeEngine::_InsertEffects"
0x18002f7de  mov     r8d, 2A8h; int
0x18002f7e4  mov     rcx, rax; this
0x18002f7e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002f7ec  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
  ... truncated ...
```
