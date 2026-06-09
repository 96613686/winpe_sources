# CMFTopoLoader::BuildTaskForPinInternal(CTopoLoaderConnectTask *,CTPtrList<CTopoLoaderConnectTask> &)

- ea: `0x180254a34`
- end: `0x180255329`
- name: `?BuildTaskForPinInternal@CMFTopoLoader@@IEAAJPEAVCTopoLoaderConnectTask@@AEAV?$CTPtrList@VCTopoLoaderConnectTask@@@@@Z`
- size: `2293`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task`

## callers

- `0x1800afe1c`

## callees

- `0x18002fee0`
- `0x180035170`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ae554`
- `0x1800ae5b8`
- `0x1800ec0e0`
- `0x18014c0fc`
- `0x18015c610`
- `0x18015fae4`
- `0x1802516cc`
- `0x180254a34`
- `0x1802583a8`
- `0x180258480`
- `0x1802c07e8`
- `0x1802c0a08`
- `0x1802c28dc`
- `0x1802c2eac`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180254bc4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180254e6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180254f07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18025500e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802550db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180255171`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180255234`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180254bc4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180254e6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180254f07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18025500e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802550db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180255171`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180255234`

## string_xrefs

- `0x180254b2f`: `CMFTopoLoader::BuildTaskForPinInternal`
- `0x180254c22`: `CMFTopoLoader::BuildTaskForPinInternal`
- `0x180254ecb`: `CMFTopoLoader::BuildTaskForPinInternal`
- `0x180254f65`: `CMFTopoLoader::BuildTaskForPinInternal`
- `0x18025506c`: `CMFTopoLoader::BuildTaskForPinInternal`
- `0x180255139`: `CMFTopoLoader::BuildTaskForPinInternal`
- `0x1802551cf`: `CMFTopoLoader::BuildTaskForPinInternal`
- `0x180255292`: `CMFTopoLoader::BuildTaskForPinInternal`

## pseudocode

```c
__int64 __fastcall CMFTopoLoader::BuildTaskForPinInternal(__int64 a1, struct CTopologyPin *a2, __int64 a3)
{
  CTopoLoaderConnectTask *v6; // rax
  CTopoLoaderConnectTask *v7; // r15
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v12; // ebx
  __int128 *v13; // rax
  __int128 v14; // xmm0
  int v15; // ebx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  unsigned int v18; // esi
  int v19; // ebx
  const unsigned __int16 *v20; // rax
  int DownNodeInputPin; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8
  int v26; // ecx
  unsigned __int8 v27; // al
  const unsigned __int16 *v28; // rax
  const unsigned __int16 *v29; // rax
  __int64 v30; // r8
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  const unsigned __int16 *v38; // rax
  __int64 v39; // rdx
  const unsigned __int16 *v40; // rax
  __int64 v41; // r8
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // r8
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  _BYTE v56[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v57; // [rsp+34h] [rbp-CCh] BYREF
  int v58; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v59[12]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v60[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct IMFTopologyNode *v61; // [rsp+B0h] [rbp-50h]
  __int64 v62; // [rsp+B8h] [rbp-48h]
  int v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+C8h] [rbp-38h]
  __int64 v65; // [rsp+D0h] [rbp-30h]
  __int64 v66; // [rsp+D8h] [rbp-28h]
  __int16 v67; // [rsp+E0h] [rbp-20h]
  _QWORD v68[3]; // [rsp+100h] [rbp+0h] BYREF
  int v69; // [rsp+118h] [rbp+18h]
  __int64 v70; // [rsp+11Ch] [rbp+1Ch]
  __int64 v71; // [rsp+128h] [rbp+28h]
  __int64 v72; // [rsp+130h] [rbp+30h]
  __int64 v73; // [rsp+138h] [rbp+38h]
  __int16 v74; // [rsp+140h] [rbp+40h]
  _QWORD v75[3]; // [rsp+160h] [rbp+60h] BYREF
  int v76; // [rsp+178h] [rbp+78h]
  __int64 v77; // [rsp+17Ch] [rbp+7Ch]
  __int64 v78; // [rsp+188h] [rbp+88h]
  __int64 v79; // [rsp+190h] [rbp+90h]
  __int64 v80; // [rsp+198h] [rbp+98h]
  __int16 v81; // [rsp+1A0h] [rbp+A0h]
  _BYTE v82[16]; // [rsp+1C0h] [rbp+C0h] BYREF

  v70 = 1;
  v68[1] = 0;
  v68[2] = 0;
  v68[0] = &CTopologyPin::`vftable';
  v75[0] = &CTopologyPin::`vftable';
  v69 = 0;
  v74 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v75[1] = 0;
  v75[2] = 0;
  v76 = 0;
  v77 = 1;
  v81 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v60[1] = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v67 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v60[0] = &CTopologyPin::`vftable';
  v58 = 0;
  CTopologyPin::SetPin((CTopologyPin *)v68, a2);
  v6 = (CTopoLoaderConnectTask *)operator new(0x190u);
  if ( v6 )
    v7 = CTopoLoaderConnectTask::CTopoLoaderConnectTask(v6);
  else
    v7 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v56, "CMFTopoLoader::BuildTaskForPinInternal", 939);
  v10 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *(_QWORD *)(a1 + 552) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 552) + 296LL))(*(_QWORD *)(a1 + 552));
    v13 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 552) + 280LL))(
                        *(_QWORD *)(a1 + 552),
                        v82);
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    v14 = *v13;
    *((_DWORD *)ThreadRelativeContext + 504) = v12;
    *((_OWORD *)ThreadRelativeContext + 125) = v14;
  }
  if ( !v7 )
  {
    v15 = -2147024882;
    if ( !v10 )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v17 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v17, "CMFTopoLoader::BuildTaskForPinInternal", 939, -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids,
        a1,
        -2147024882);
    goto LABEL_113;
  }
  v18 = 0;
  if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
  {
    v19 = *((_DWORD *)a2 + 49);
    v20 = CTopologyPin::ToString((CTopologyPin *)v68);
    WPP_SF_qSd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      75,
      (unsigned int)&WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids,
      a1,
      (__int64)v20,
      v19);
  }
  CTopologyPin::SetPin(v7, (struct CTopologyPin *)v68);
  CTopologyPin::SetPin((CTopologyPin *)v75, (struct CTopologyPin *)v68);
  while ( 1 )
  {
    DownNodeInputPin = COutputTopologyPin::GetDownNodeInputPin(
                         (COutputTopologyPin *)v75,
                         (struct CInputTopologyPin *)v60);
    v15 = DownNodeInputPin;
    if ( DownNodeInputPin == -1072875819 )
    {
      v15 = 0;
      goto LABEL_99;
    }
    if ( DownNodeInputPin < 0 )
    {
      v48 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
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
        if ( *((_DWORD *)v50 + 499) != v15 )
          CallStackContext::TraceFailure(v50, "CMFTopoLoader::BuildTaskForPinInternal", 965, v15);
      }
      if ( !g_wppLevels )
        goto LABEL_112;
      v34 = 76;
LABEL_48:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids, a1, v15);
      goto LABEL_112;
    }
    v15 = ((__int64 (__fastcall *)(struct IMFTopologyNode *, int *))v61->lpVtbl->GetNodeType)(v61, &v58);
    if ( v15 < 0 )
    {
      v45 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v24);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v45 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != v15 )
          CallStackContext::TraceFailure(v47, "CMFTopoLoader::BuildTaskForPinInternal", 968, v15);
      }
      if ( !g_wppLevels )
        goto LABEL_112;
      v34 = 77;
      goto LABEL_48;
    }
    if ( v58 == 1 )
    {
      if ( (_BYTE)byte_1803CECE9 )
      {
        v38 = CTopologyPin::ToString((CTopologyPin *)v60);
        v39 = 78;
        goto LABEL_76;
      }
LABEL_77:
      v15 = -1072868844;
      goto LABEL_112;
    }
    v57 = 3;
    v15 = ((__int64 (__fastcall *)(struct IMFTopologyNode *, const IID *, int *))v61->lpVtbl->GetUINT32)(
            v61,
            &MF_TOPONODE_CONNECT_METHOD,
            &v57);
    if ( (int)(v15 + 0x80000000) >= 0 && v15 != -1072875802 )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v25);
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
        if ( *((_DWORD *)v33 + 499) != v15 )
          CallStackContext::TraceFailure(v33, "CMFTopoLoader::BuildTaskForPinInternal", 986, v15);
      }
      if ( g_wppLevels )
      {
        v34 = 79;
        goto LABEL_48;
      }
      goto LABEL_112;
    }
    v26 = v57;
    if ( (v57 & 0x20000) != 0 )
    {
      v27 = (unsigned __int8)byte_1803CECE9;
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
      {
        v28 = CTopologyPin::ToString((CTopologyPin *)v60);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 80, &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids, v28);
        v26 = v57;
        v27 = (unsigned __int8)byte_1803CECE9;
      }
      v18 = 1;
    }
    else
    {
      v18 = *((_DWORD *)a2 + 49);
      v27 = (unsigned __int8)byte_1803CECE9;
    }
    if ( (v26 & 0x10000) == 0 )
      break;
    if ( !v58 )
    {
      if ( v27 )
      {
        v38 = CTopologyPin::ToString((CTopologyPin *)v60);
        v39 = 83;
LABEL_76:
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), v39, &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids, v38);
        goto LABEL_77;
      }
      goto LABEL_77;
    }
    *((_DWORD *)v7 + 48) = 1;
    if ( v27 >= 8u )
    {
      v29 = CTopologyPin::ToString((CTopologyPin *)v60);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 84, &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids, v29);
    }
    v15 = CMFTopoLoader::AddPinsToQueue(a1, v61, v18, 1, a3);
    if ( v15 < 0 )
    {
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v30);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != v15 )
          CallStackContext::TraceFailure(v37, "CMFTopoLoader::BuildTaskForPinInternal", 1041, v15);
      }
      if ( g_wppLevels )
      {
        v34 = 85;
        goto LABEL_48;
      }
      goto LABEL_112;
    }
    CTopologyPin::CTopologyPin((CTopologyPin *)v59, 0, v61, 0, 1);
    v59[0] = &CTopologyPin::`vftable';
    CTopologyPin::SetPin((CTopologyPin *)v75, (struct CTopologyPin *)v59);
    CTopologyPin::~CTopologyPin((CTopologyPin *)v59);
  }
  if ( v27 >= 8u )
  {
    v40 = CTopologyPin::ToString((CTopologyPin *)v60);
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 81, &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids, v40);
  }
  CTopologyPin::SetPin((CTopoLoaderConnectTask *)((char *)v7 + 96), (struct CTopologyPin *)v60);
  v15 = CMFTopoLoader::AddPinsToQueue(a1, v61, v18, 0, a3);
  if ( v15 < 0 )
  {
    v42 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v41);
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
      if ( *((_DWORD *)v44 + 499) != v15 )
        CallStackContext::TraceFailure(v44, "CMFTopoLoader::BuildTaskForPinInternal", 1015, v15);
    }
    if ( g_wppLevels )
    {
      v34 = 82;
      goto LABEL_48;
    }
LABEL_112:
    CTopoLoaderConnectTask::`scalar deleting destructor'(v7, v22);
    goto LABEL_113;
  }
LABEL_99:
  if ( v18 )
    *((_DWORD *)v7 + 49) = 1;
  if ( !CVPtrList::AddTail((CVPtrList *)(a1 + 96), v7) )
  {
    v52 = (__int64 *)CallStackTracing::s_wpInstance;
    v15 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v51);
      CallStackTracing::s_wpInstance = v53;
      if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
      {
        v52 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v52 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v52 + 8) )
    {
      v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
      if ( *((_DWORD *)v54 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v54, "CMFTopoLoader::BuildTaskForPinInternal", 1056, -2147024882);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids,
        a1,
        -2147024882);
    goto LABEL_112;
  }
LABEL_113:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v56);
  CTopologyPin::~CTopologyPin((CTopologyPin *)v60);
  CTopologyPin::~CTopologyPin((CTopologyPin *)v75);
  CTopologyPin::~CTopologyPin((CTopologyPin *)v68);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180254a34  mov     [rsp-8+arg_18], rbx
0x180254a39  push    rbp
0x180254a3a  push    rsi
0x180254a3b  push    rdi
0x180254a3c  push    r12
0x180254a3e  push    r13
0x180254a40  push    r14
0x180254a42  push    r15
0x180254a44  lea     rbp, [rsp-0E0h]
0x180254a4c  sub     rsp, 1E0h
0x180254a53  mov     rax, cs:__security_cookie
0x180254a5a  xor     rax, rsp
0x180254a5d  mov     [rbp+110h+var_40], rax
0x180254a64  xor     edi, edi
0x180254a66  mov     [rbp+110h+var_F4], 1
0x180254a6e  mov     r13, rdx
0x180254a71  mov     [rbp+110h+var_108], rdi
0x180254a75  lea     rdx, ??_7CTopologyPin@@6B@; const CTopologyPin::`vftable'
0x180254a7c  mov     [rbp+110h+var_100], rdi
0x180254a80  mov     [rbp+110h+var_110], rdx
0x180254a84  lea     rax, ??_7CTopologyPin@@6B@; const CTopologyPin::`vftable'
0x180254a8b  mov     [rbp+110h+var_B0], rdx
0x180254a8f  mov     r14, rcx
0x180254a92  mov     rdx, r13; struct CTopologyPin *
0x180254a95  mov     [rbp+110h+var_F8], edi
0x180254a98  lea     rcx, [rbp+110h+var_110]; this
0x180254a9c  mov     [rbp+110h+var_D0], di
0x180254aa0  mov     r12, r8
0x180254aa3  mov     [rbp+110h+var_E8], rdi
0x180254aa7  mov     [rbp+110h+var_E0], rdi
0x180254aab  mov     [rbp+110h+var_D8], rdi
0x180254aaf  mov     [rbp+110h+var_A8], rdi
0x180254ab3  mov     [rbp+110h+var_A0], rdi
0x180254ab7  mov     [rbp+110h+var_98], edi
0x180254aba  mov     [rbp+110h+var_94], 1
0x180254ac2  mov     [rbp+110h+var_70], di
0x180254ac9  mov     [rbp+110h+var_88], rdi
0x180254ad0  mov     [rbp+110h+var_80], rdi
0x180254ad7  mov     [rbp+110h+var_78], rdi
0x180254ade  mov     [rbp+110h+var_168], rdi
0x180254ae2  mov     [rbp+110h+var_160], rdi
0x180254ae6  mov     [rbp+110h+var_158], rdi
0x180254aea  mov     [rbp+110h+var_150], edi
0x180254aed  mov     [rbp+110h+var_130], di
0x180254af1  mov     [rbp+110h+var_148], rdi
0x180254af5  mov     [rbp+110h+var_140], rdi
0x180254af9  mov     [rbp+110h+var_138], rdi
0x180254afd  mov     [rbp+110h+var_170], rax
0x180254b01  mov     [rsp+210h+var_1D8], edi
0x180254b05  call    ?SetPin@CTopologyPin@@IEAAXAEAV1@@Z; CTopologyPin::SetPin(CTopologyPin &)
0x180254b0a  mov     ecx, 190h; Size
0x180254b0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180254b14  test    rax, rax
0x180254b17  jz      short loc_180254B26
0x180254b19  mov     rcx, rax; this
0x180254b1c  call    ??0CTopoLoaderConnectTask@@QEAA@XZ; CTopoLoaderConnectTask::CTopoLoaderConnectTask(void)
0x180254b21  mov     r15, rax
0x180254b24  jmp     short loc_180254B29
0x180254b26  mov     r15, rdi
0x180254b29  mov     r8d, 3ABh; int
0x180254b2f  lea     rdx, aCmftopoloaderB_0; "CMFTopoLoader::BuildTaskForPinInternal"
0x180254b36  lea     rcx, [rsp+210h+var_1E0]; this
0x180254b3b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180254b40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180254b47  cmp     [rcx+8], dil
0x180254b4b  jz      short loc_180254BAF
0x180254b4d  cmp     [r14+228h], rdi
0x180254b54  jz      short loc_180254BAF
0x180254b56  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180254b5b  mov     rcx, [r14+228h]
0x180254b62  mov     rdi, rax
0x180254b65  mov     rdx, [rcx]
0x180254b68  mov     rax, [rdx+128h]
0x180254b6f  call    cs:__guard_dispatch_icall_fptr
0x180254b75  mov     rcx, [r14+228h]
0x180254b7c  mov     ebx, eax
0x180254b7e  mov     rdx, [rcx]
0x180254b81  mov     rax, [rdx+118h]
0x180254b88  lea     rdx, [rbp+110h+var_50]
0x180254b8f  call    cs:__guard_dispatch_icall_fptr
0x180254b95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180254b9c  movups  xmm0, xmmword ptr [rax]
0x180254b9f  mov     [rdi+7E0h], ebx
0x180254ba5  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180254bad  xor     edi, edi
0x180254baf  test    r15, r15
0x180254bb2  jnz     loc_180254C6C
0x180254bb8  mov     esi, 8007000Eh
0x180254bbd  mov     ebx, esi
0x180254bbf  test    rcx, rcx
0x180254bc2  jnz     short loc_180254C0C
0x180254bc4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180254bcb  nop     dword ptr [rax+rax+00h]
0x180254bd0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180254bd7  mov     rcx, rax
0x180254bda  test    rax, rax
0x180254bdd  jz      short loc_180254BFE
0x180254bdf  mov     rax, [rax]
0x180254be2  mov     edx, 7F0h
0x180254be7  mov     rax, [rax+8]
0x180254beb  call    cs:__guard_dispatch_icall_fptr
0x180254bf1  test    eax, eax
0x180254bf3  jz      short loc_180254BFE
0x180254bf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180254bfc  jmp     short loc_180254C0C
0x180254bfe  lea     rcx, qword_1803CE250; this
0x180254c05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180254c0c  cmp     [rcx+8], dil
0x180254c10  jz      short loc_180254C37
0x180254c12  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180254c17  cmp     [rax+7CCh], esi
0x180254c1d  jz      short loc_180254C37
0x180254c1f  mov     r9d, esi; int
0x180254c22  lea     rdx, aCmftopoloaderB_0; "CMFTopoLoader::BuildTaskForPinInternal"
0x180254c29  mov     r8d, 3ABh; int
0x180254c2f  mov     rcx, rax; this
0x180254c32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180254c37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180254c3e  jb      loc_1802552D7
0x180254c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180254c4b  lea     r8, WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids
0x180254c52  mov     edx, 4Ah ; 'J'
0x180254c57  mov     [rsp+210h+var_1F0], esi
0x180254c5b  mov     r9, r14
0x180254c5e  mov     rcx, [rcx+10h]
0x180254c62  call    WPP_SF_qD
0x180254c67  jmp     loc_1802552D7
0x180254c6c  cmp     cs:byte_1803CECE9, 10h
0x180254c73  mov     esi, edi
0x180254c75  lea     rdi, WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids
0x180254c7c  jb      short loc_180254CB2
0x180254c7e  mov     ebx, [r13+0C4h]
0x180254c85  lea     rcx, [rbp+110h+var_110]; this
0x180254c89  call    ?ToString@CTopologyPin@@QEAAPEBGXZ; CTopologyPin::ToString(void)
0x180254c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180254c95  mov     edx, 4Bh ; 'K'
0x180254c9a  mov     [rsp+210h+var_1E8], ebx
0x180254c9e  mov     r9, r14
0x180254ca1  mov     r8, rdi
0x180254ca4  mov     qword ptr [rsp+210h+var_1F0], rax
0x180254ca9  mov     rcx, [rcx+38h]
0x180254cad  call    WPP_SF_qSd
0x180254cb2  lea     rdx, [rbp+110h+var_110]; struct CTopologyPin *
0x180254cb6  mov     rcx, r15; this
0x180254cb9  call    ?SetPin@CTopologyPin@@IEAAXAEAV1@@Z; CTopologyPin::SetPin(CTopologyPin &)
0x180254cbe  lea     rdx, [rbp+110h+var_110]; struct CTopologyPin *
0x180254cc2  lea     rcx, [rbp+110h+var_B0]; this
0x180254cc6  call    ?SetPin@CTopologyPin@@IEAAXAEAV1@@Z; CTopologyPin::SetPin(CTopologyPin &)
0x180254ccb  lea     rdx, [rbp+110h+var_170]; struct CInputTopologyPin *
0x180254ccf  lea     rcx, [rbp+110h+var_B0]; this
0x180254cd3  call    ?GetDownNodeInputPin@COutputTopologyPin@@QEAAJAEAVCInputTopologyPin@@@Z; COutputTopologyPin::GetDownNodeInputPin(CInputTopologyPin &)
0x180254cd8  mov     ebx, eax
0x180254cda  cmp     eax, 0C00D36D5h
0x180254cdf  jz      loc_1802551FB
0x180254ce5  xor     esi, esi
0x180254ce7  test    eax, eax
0x180254ce9  js      loc_180255165
0x180254cef  mov     rcx, [rbp+110h+var_160]
0x180254cf3  lea     rdx, [rsp+210h+var_1D8]
0x180254cf8  mov     rax, [rcx]
0x180254cfb  mov     rax, [rax+118h]
0x180254d02  call    cs:__guard_dispatch_icall_fptr
0x180254d08  mov     ebx, eax
0x180254d0a  test    eax, eax
0x180254d0c  js      loc_1802550CF
0x180254d12  cmp     [rsp+210h+var_1D8], 1
0x180254d17  jz      loc_180255098
0x180254d1d  mov     rcx, [rbp+110h+var_160]
0x180254d21  lea     r8, [rsp+210h+var_1DC]
0x180254d26  mov     [rsp+210h+var_1DC], 3
0x180254d2e  lea     rdx, MF_TOPONODE_CONNECT_METHOD
0x180254d35  mov     rax, [rcx]
0x180254d38  mov     rax, [rax+38h]
0x180254d3c  call    cs:__guard_dispatch_icall_fptr
0x180254d42  mov     ecx, 80000000h
0x180254d47  mov     ebx, eax
0x180254d49  add     eax, ecx
0x180254d4b  test    ecx, eax
0x180254d4d  jnz     short loc_180254D5B
0x180254d4f  cmp     ebx, 0C00D36E6h
0x180254d55  jnz     loc_180254E61
0x180254d5b  mov     ecx, [rsp+210h+var_1DC]
0x180254d5f  bt      ecx, 11h
0x180254d63  jnb     short loc_180254DA4
0x180254d65  mov     al, cs:byte_1803CECE9
0x180254d6b  cmp     al, 8
0x180254d6d  jb      short loc_180254D9D
0x180254d6f  lea     rcx, [rbp+110h+var_170]; this
0x180254d73  call    ?ToString@CTopologyPin@@QEAAPEBGXZ; CTopologyPin::ToString(void)
0x180254d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180254d7f  mov     edx, 50h ; 'P'
0x180254d84  mov     r9, rax
0x180254d87  mov     r8, rdi
0x180254d8a  mov     rcx, [rcx+38h]
0x180254d8e  call    WPP_SF_S
0x180254d93  mov     ecx, [rsp+210h+var_1DC]
0x180254d97  mov     al, cs:byte_1803CECE9
0x180254d9d  mov     esi, 1
0x180254da2  jmp     short loc_180254DB1
0x180254da4  mov     esi, [r13+0C4h]
0x180254dab  mov     al, cs:byte_1803CECE9
0x180254db1  bt      ecx, 10h
0x180254db5  jnb     loc_180254FAC
0x180254dbb  cmp     [rsp+210h+var_1D8], 0
0x180254dc0  jz      loc_180254F91
0x180254dc6  mov     dword ptr [r15+0C0h], 1
0x180254dd1  cmp     al, 8
0x180254dd3  jb      short loc_180254DF9
0x180254dd5  lea     rcx, [rbp+110h+var_170]; this
0x180254dd9  call    ?ToString@CTopologyPin@@QEAAPEBGXZ; CTopologyPin::ToString(void)
0x180254dde  mov     rcx, cs:WPP_GLOBAL_Control
0x180254de5  mov     edx, 54h ; 'T'
0x180254dea  mov     r9, rax
0x180254ded  mov     r8, rdi
0x180254df0  mov     rcx, [rcx+38h]
0x180254df4  call    WPP_SF_S
0x180254df9  mov     rdx, [rbp+110h+var_160]
0x180254dfd  mov     r9d, 1
0x180254e03  mov     r8d, esi
0x180254e06  mov     qword ptr [rsp+210h+var_1F0], r12
0x180254e0b  mov     rcx, r14
0x180254e0e  call    ?AddPinsToQueue@CMFTopoLoader@@IEAAJPEAUIMFTopologyNode@@HHAEAV?$CTPtrList@VCTopoLoaderConnectTask@@@@@Z; CMFTopoLoader::AddPinsToQueue(IMFTopologyNode *,int,int,CTPtrList<CTopoLoaderConnectTask> &)
0x180254e13  mov     ebx, eax
0x180254e15  test    eax, eax
0x180254e17  js      loc_180254EFB
0x180254e1d  mov     r8, [rbp+110h+var_160]; struct IMFTopologyNode *
0x180254e21  lea     rcx, [rsp+210h+var_1D0]; this
0x180254e26  xor     r9d, r9d; unsigned int
0x180254e29  mov     [rsp+210h+var_1F0], 1; int
0x180254e31  xor     edx, edx; struct CTopoConnectorShared *
0x180254e33  call    ??0CTopologyPin@@IEAA@PEAVCTopoConnectorShared@@PEAUIMFTopologyNode@@KH@Z; CTopologyPin::CTopologyPin(CTopoConnectorShared *,IMFTopologyNode *,ulong,int)
0x180254e38  lea     rax, ??_7CTopologyPin@@6B@; const CTopologyPin::`vftable'
0x180254e3f  lea     rdx, [rsp+210h+var_1D0]; struct CTopologyPin *
0x180254e44  mov     [rsp+210h+var_1D0], rax
0x180254e49  lea     rcx, [rbp+110h+var_B0]; this
0x180254e4d  call    ?SetPin@CTopologyPin@@IEAAXAEAV1@@Z; CTopologyPin::SetPin(CTopologyPin &)
0x180254e52  lea     rcx, [rsp+210h+var_1D0]; this
0x180254e57  call    ??1CTopologyPin@@UEAA@XZ; CTopologyPin::~CTopologyPin(void)
0x180254e5c  jmp     loc_180254CCB
0x180254e61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180254e68  test    rcx, rcx
0x180254e6b  jnz     short loc_180254EB5
0x180254e6d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180254e74  nop     dword ptr [rax+rax+00h]
0x180254e79  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180254e80  mov     rcx, rax
0x180254e83  test    rax, rax
0x180254e86  jz      short loc_180254EA7
0x180254e88  mov     rax, [rax]
0x180254e8b  mov     edx, 7F0h
0x180254e90  mov     rax, [rax+8]
0x180254e94  call    cs:__guard_dispatch_icall_fptr
0x180254e9a  test    eax, eax
0x180254e9c  jz      short loc_180254EA7
0x180254e9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180254ea5  jmp     short loc_180254EB5
0x180254ea7  lea     rcx, qword_1803CE250; this
0x180254eae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180254eb5  cmp     [rcx+8], sil
0x180254eb9  jz      short loc_180254EE0
0x180254ebb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180254ec0  cmp     [rax+7CCh], ebx
0x180254ec6  jz      short loc_180254EE0
0x180254ec8  mov     r9d, ebx; int
0x180254ecb  lea     rdx, aCmftopoloaderB_0; "CMFTopoLoader::BuildTaskForPinInternal"
0x180254ed2  mov     r8d, 3DAh; int
0x180254ed8  mov     rcx, rax; this
0x180254edb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180254ee0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180254ee7  jb      loc_1802552CF
0x180254eed  mov     edx, 4Fh ; 'O'
0x180254ef2  mov     [rsp+210h+var_1F0], ebx
0x180254ef6  jmp     loc_1802552B9
0x180254efb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180254f02  test    rcx, rcx
0x180254f05  jnz     short loc_180254F4F
0x180254f07  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180254f0e  nop     dword ptr [rax+rax+00h]
0x180254f13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180254f1a  mov     rcx, rax
0x180254f1d  test    rax, rax
0x180254f20  jz      short loc_180254F41
0x180254f22  mov     rax, [rax]
0x180254f25  mov     edx, 7F0h
0x180254f2a  mov     rax, [rax+8]
0x180254f2e  call    cs:__guard_dispatch_icall_fptr
0x180254f34  test    eax, eax
0x180254f36  jz      short loc_180254F41
0x180254f38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180254f3f  jmp     short loc_180254F4F
0x180254f41  lea     rcx, qword_1803CE250; this
0x180254f48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180254f4f  cmp     byte ptr [rcx+8], 0
0x180254f53  jz      short loc_180254F7A
0x180254f55  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180254f5a  cmp     [rax+7CCh], ebx
0x180254f60  jz      short loc_180254F7A
0x180254f62  mov     r9d, ebx; int
0x180254f65  lea     rdx, aCmftopoloaderB_0; "CMFTopoLoader::BuildTaskForPinInternal"
0x180254f6c  mov     r8d, 411h; int
  ... truncated ...
```
