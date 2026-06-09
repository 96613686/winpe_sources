# CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents(COutputTopologyPin &,IMFMediaType *,CInputTopologyPin &,IMFMediaType *,ulong)

- ea: `0x1801f6040`
- end: `0x1801f6bbe`
- name: `?InsertAndConnectVideoComponents@CMFVideoBranchLoaderV1@@UEAAJAEAVCOutputTopologyPin@@PEAUIMFMediaType@@AEAVCInputTopologyPin@@1K@Z`
- size: `2942`
- prototype: `__int64 __usercall@<rax>(CMFVideoBranchLoaderV1 *__hidden this@<rcx>, struct COutputTopologyPin *@<rdx>, struct IMFMediaType *@<r8>, struct CInputTopologyPin *@<r9>, struct IMFMediaType *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18010a12c`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x1800483d0`
- `0x180050d6c`
- `0x180063f00`
- `0x18009efc4`
- `0x1800ae554`
- `0x1800ae5b8`
- `0x1800ec0e0`
- `0x180113a70`
- `0x18014c0fc`
- `0x180195878`
- `0x1801f6040`
- `0x1801f80fc`
- `0x1802338e0`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1801f611d`
- `MFPlat!MFCreateMediaType` at `0x1801f6928`
- `MFPlat!MFCreateMediaType` at `0x1801f611d`
- `MFPlat!MFCreateMediaType` at `0x1801f6928`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f613f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f61fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f62dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f639f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f652f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f65f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f670f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f67d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f6899`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f694a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f6a04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f6abb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f613f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f61fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f62dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f639f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f652f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f65f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f670f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f67d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f6899`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f694a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f6a04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f6abb`

## string_xrefs

- `0x1801f60a8`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f619d`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f625c`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f633a`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f63fd`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f658d`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f6656`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f676d`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f6830`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f68f7`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f69a8`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f6a62`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`
- `0x1801f6b19`: `CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents`

## pseudocode

```c
__int64 __fastcall CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents(
        CMFVideoBranchLoaderV1 *this,
        struct COutputTopologyPin *a2,
        struct IMFMediaType *a3,
        struct CInputTopologyPin *a4,
        struct IMFMediaType *a5,
        char a6)
{
  struct CTopoConnectorShared *v9; // rdx
  HRESULT inserted; // ebx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  int v18; // r13d
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  _BYTE v50[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v51; // [rsp+34h] [rbp-CCh] BYREF
  int v52; // [rsp+38h] [rbp-C8h] BYREF
  int v53; // [rsp+3Ch] [rbp-C4h] BYREF
  int v54; // [rsp+40h] [rbp-C0h] BYREF
  IMFMediaType *ppMFType; // [rsp+48h] [rbp-B8h] BYREF
  IMFMediaType *v56; // [rsp+50h] [rbp-B0h] BYREF
  struct CInputTopologyPin *v57; // [rsp+58h] [rbp-A8h]
  __int64 v58; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v59; // [rsp+68h] [rbp-98h] BYREF
  __int64 v60; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v61[12]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v62[3]; // [rsp+E0h] [rbp-20h] BYREF
  int v63; // [rsp+F8h] [rbp-8h]
  __int64 v64; // [rsp+FCh] [rbp-4h]
  __int64 v65; // [rsp+108h] [rbp+8h]
  __int64 v66; // [rsp+110h] [rbp+10h]
  __int64 v67; // [rsp+118h] [rbp+18h]
  __int16 v68; // [rsp+120h] [rbp+20h]

  v57 = a4;
  v60 = 0;
  v59 = 0;
  v58 = 0;
  v62[1] = 0;
  v64 = 1;
  v62[2] = 0;
  v63 = 0;
  v68 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v62[0] = &CTopologyPin::`vftable';
  ppMFType = 0;
  v56 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v50,
    "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents",
    534);
  v9 = (struct CTopoConnectorShared *)*((_QWORD *)this + 3);
  *((_DWORD *)this + 2) = 0;
  CTopologyPin::CTopologyPin((CTopologyPin *)v61, v9, *((struct IMFTopologyNode **)a2 + 2), *((_DWORD *)a2 + 6), 1);
  v61[0] = &CTopologyPin::`vftable';
  CTopologyPin::SetPin((CTopologyPin *)v62, (struct CTopologyPin *)v61);
  CTopologyPin::~CTopologyPin((CTopologyPin *)v61);
  inserted = MFCreateMediaType(&ppMFType);
  if ( inserted < 0 )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents",
          559,
          inserted);
    }
    if ( g_wppLevels )
    {
      v14 = 57;
LABEL_149:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_84077d43404e382a16b12f731fadc2a0_Traceguids,
        this,
        inserted);
      goto LABEL_150;
    }
    goto LABEL_150;
  }
  inserted = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))a3->lpVtbl->CopyAllItems)(a3, ppMFType);
  if ( inserted >= 0 )
  {
    v18 = 0;
    if ( (a6 & 4) != 0 )
    {
      v51 = 0;
      v52 = 0;
      inserted = MFGetAttribute2UINT32asUINT64(a3, &MF_MT_FRAME_RATE, &v51, &v52);
      if ( inserted < 0 )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
          if ( *((_DWORD *)v21 + 499) != inserted )
            CallStackContext::TraceFailure(
              v21,
              "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents",
              574,
              inserted);
        }
        if ( g_wppLevels )
        {
          v14 = 59;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      v53 = 0;
      v54 = 0;
      inserted = MFGetAttribute2UINT32asUINT64(a5, &MF_MT_FRAME_RATE, &v53, &v54);
      if ( inserted < 0 )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
          if ( *((_DWORD *)v24 + 499) != inserted )
            CallStackContext::TraceFailure(
              v24,
              "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents",
              577,
              inserted);
        }
        if ( g_wppLevels )
        {
          v14 = 60;
          goto LABEL_149;
        }
        goto LABEL_150;
      }
      if ( (double)v51 / (double)v52 <= (double)v53 / (double)v54 )
        goto LABEL_53;
      inserted = CMFVideoBranchLoaderV1::InsertFRC(this, (struct COutputTopologyPin *)v62, ppMFType, a3, a5, 0);
      if ( inserted < 0 )
      {
        if ( (a6 & 3) == 0 )
        {
          if ( (_BYTE)byte_1803CECE9 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 62, &WPP_84077d43404e382a16b12f731fadc2a0_Traceguids);
          goto LABEL_150;
        }
        if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 61, &WPP_84077d43404e382a16b12f731fadc2a0_Traceguids);
LABEL_53:
        v18 = 1;
      }
    }
    if ( (a6 & 3) != 3 )
      goto LABEL_153;
    v51 = 0;
    v52 = 0;
    inserted = MFGetAttribute2UINT32asUINT64(a3, &MF_MT_FRAME_SIZE, &v51, &v52);
    if ( inserted < 0 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
        if ( *((_DWORD *)v27 + 499) != inserted )
          CallStackContext::TraceFailure(v27, "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents", 630, inserted);
      }
      if ( g_wppLevels )
      {
        v14 = 63;
        goto LABEL_149;
      }
      goto LABEL_150;
    }
    v53 = 0;
    v54 = 0;
    inserted = MFGetAttribute2UINT32asUINT64(a5, &MF_MT_FRAME_SIZE, &v53, &v54);
    if ( inserted < 0 )
    {
      v28 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) != inserted )
          CallStackContext::TraceFailure(v30, "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents", 633, inserted);
      }
      if ( g_wppLevels )
      {
        v14 = 64;
        goto LABEL_149;
      }
      goto LABEL_150;
    }
    if ( v51 * v52 <= (unsigned int)(v53 * v54)
      || CMFVideoBranchLoaderV1::InsertResizer(this, (struct COutputTopologyPin *)v62, ppMFType, a3, a5) < 0
      || CMFVideoBranchLoaderV1::InsertColorConverter(this, (struct COutputTopologyPin *)v62, ppMFType, a3, a5) < 0 )
    {
LABEL_153:
      if ( (a6 & 1) != 0 )
      {
        inserted = CMFVideoBranchLoaderV1::InsertColorConverter(
                     this,
                     (struct COutputTopologyPin *)v62,
                     ppMFType,
                     a3,
                     a5);
        if ( inserted < 0 )
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
            if ( *((_DWORD *)v33 + 499) != inserted )
              CallStackContext::TraceFailure(
                v33,
                "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents",
                674,
                inserted);
          }
          if ( g_wppLevels )
          {
            v14 = 65;
            goto LABEL_149;
          }
          goto LABEL_150;
        }
      }
      if ( (a6 & 2) != 0 )
      {
        inserted = CMFVideoBranchLoaderV1::InsertResizer(this, (struct COutputTopologyPin *)v62, ppMFType, a3, a5);
        if ( inserted < 0 )
        {
          v34 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
            if ( *((_DWORD *)v36 + 499) != inserted )
              CallStackContext::TraceFailure(
                v36,
                "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents",
                685,
                inserted);
          }
          if ( g_wppLevels )
          {
            v14 = 66;
            goto LABEL_149;
          }
          goto LABEL_150;
        }
      }
    }
    if ( v18
      && (inserted = CMFVideoBranchLoaderV1::InsertFRC(this, (struct COutputTopologyPin *)v62, ppMFType, a3, a5, v18),
          inserted < 0) )
    {
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
        if ( *((_DWORD *)v39 + 499) != inserted )
          CallStackContext::TraceFailure(v39, "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents", 697, inserted);
      }
      if ( g_wppLevels )
      {
        v14 = 67;
        goto LABEL_149;
      }
    }
    else
    {
      inserted = MFCreateMediaType(&v56);
      if ( inserted >= 0 )
      {
        inserted = ((__int64 (__fastcall *)(IMFMediaType *, IMFMediaType *))ppMFType->lpVtbl->CopyAllItems)(
                     ppMFType,
                     v56);
        if ( inserted >= 0 )
        {
          inserted = CTopoConnectorShared::ConnectNodesWithProvidedMediaType(
                       *((CTopoConnectorShared **)this + 3),
                       (struct COutputTopologyPin *)v62,
                       v57,
                       v56);
          if ( inserted < 0 )
          {
            v46 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v47;
              if ( v47
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
              {
                v46 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v46 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v46 + 8) )
            {
              v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
              if ( *((_DWORD *)v48 + 499) != inserted )
                CallStackContext::TraceFailure(
                  v48,
                  "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents",
                  711,
                  inserted);
            }
            if ( g_wppLevels )
            {
              v14 = 70;
              goto LABEL_149;
            }
          }
        }
        else
        {
          v43 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v44;
            if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
            {
              v43 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v43 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v43 + 8) )
          {
            v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
            if ( *((_DWORD *)v45 + 499) != inserted )
              CallStackContext::TraceFailure(
                v45,
                "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents",
                709,
                inserted);
          }
          if ( g_wppLevels )
          {
            v14 = 69;
            goto LABEL_149;
          }
        }
      }
      else
      {
        v40 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
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
          if ( *((_DWORD *)v42 + 499) != inserted )
            CallStackContext::TraceFailure(
              v42,
              "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents",
              708,
              inserted);
        }
        if ( g_wppLevels )
        {
          v14 = 68;
          goto LABEL_149;
        }
      }
    }
    goto LABEL_150;
  }
  v15 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v17 + 499) != inserted )
      CallStackContext::TraceFailure(v17, "CMFVideoBranchLoaderV1::InsertAndConnectVideoComponents", 560, inserted);
  }
  if ( g_wppLevels )
  {
    v14 = 58;
    goto LABEL_149;
  }
LABEL_150:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v50);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v56);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFType);
  CTopologyPin::~CTopologyPin((CTopologyPin *)v62);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v58);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v59);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v60);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801f6040  push    rbp
0x1801f6042  push    rbx
0x1801f6043  push    rsi
0x1801f6044  push    rdi
0x1801f6045  push    r12
0x1801f6047  push    r13
0x1801f6049  push    r14
0x1801f604b  push    r15
0x1801f604d  lea     rbp, [rsp-58h]
0x1801f6052  sub     rsp, 158h
0x1801f6059  mov     rax, cs:__security_cookie
0x1801f6060  xor     rax, rsp
0x1801f6063  mov     [rbp+90h+var_50], rax
0x1801f6067  mov     r15, [rbp+90h+arg_20]
0x1801f606e  lea     rsi, ??_7CTopologyPin@@6B@; const CTopologyPin::`vftable'
0x1801f6075  xor     r12d, r12d
0x1801f6078  mov     [rsp+190h+var_138], r9
0x1801f607d  mov     r14, r8
0x1801f6080  mov     [rsp+190h+var_120], r12
0x1801f6085  mov     rbx, rdx
0x1801f6088  mov     [rsp+190h+var_128], r12
0x1801f608d  mov     rdi, rcx
0x1801f6090  mov     [rsp+190h+var_130], r12
0x1801f6095  lea     r13d, [r12+1]
0x1801f609a  mov     [rbp+90h+var_A8], r12
0x1801f609e  mov     r8d, 216h; int
0x1801f60a4  mov     [rbp+90h+var_94], r13
0x1801f60a8  lea     rdx, aCmfvideobranch_2; "CMFVideoBranchLoaderV1::InsertAndConnec"...
0x1801f60af  mov     [rbp+90h+var_A0], r12
0x1801f60b3  lea     rcx, [rsp+190h+var_160]; this
0x1801f60b8  mov     [rbp+90h+var_98], r12d
0x1801f60bc  mov     [rbp+90h+var_70], r12w
0x1801f60c1  mov     [rbp+90h+var_88], r12
0x1801f60c5  mov     [rbp+90h+var_80], r12
0x1801f60c9  mov     [rbp+90h+var_78], r12
0x1801f60cd  mov     [rbp+90h+var_B0], rsi
0x1801f60d1  mov     [rsp+190h+ppMFType], r12
0x1801f60d6  mov     [rsp+190h+var_140], r12
0x1801f60db  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801f60e0  mov     rdx, [rdi+18h]; struct CTopoConnectorShared *
0x1801f60e4  lea     rcx, [rbp+90h+var_110]; this
0x1801f60e8  mov     [rdi+8], r12d
0x1801f60ec  mov     r9d, [rbx+18h]; unsigned int
0x1801f60f0  mov     r8, [rbx+10h]; struct IMFTopologyNode *
0x1801f60f4  mov     dword ptr [rsp+190h+var_170], r13d; int
0x1801f60f9  call    ??0CTopologyPin@@IEAA@PEAVCTopoConnectorShared@@PEAUIMFTopologyNode@@KH@Z; CTopologyPin::CTopologyPin(CTopoConnectorShared *,IMFTopologyNode *,ulong,int)
0x1801f60fe  lea     rdx, [rbp+90h+var_110]; struct CTopologyPin *
0x1801f6102  mov     [rbp+90h+var_110], rsi
0x1801f6106  lea     rcx, [rbp+90h+var_B0]; this
0x1801f610a  call    ?SetPin@CTopologyPin@@IEAAXAEAV1@@Z; CTopologyPin::SetPin(CTopologyPin &)
0x1801f610f  lea     rcx, [rbp+90h+var_110]; this
0x1801f6113  call    ??1CTopologyPin@@UEAA@XZ; CTopologyPin::~CTopologyPin(void)
0x1801f6118  lea     rcx, [rsp+190h+ppMFType]; ppMFType
0x1801f611d  call    cs:__imp_MFCreateMediaType
0x1801f6124  nop     dword ptr [rax+rax+00h]
0x1801f6129  mov     ebx, eax
0x1801f612b  test    eax, eax
0x1801f612d  jns     loc_1801F61D0
0x1801f6133  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f613a  test    rcx, rcx
0x1801f613d  jnz     short loc_1801F6187
0x1801f613f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f6146  nop     dword ptr [rax+rax+00h]
0x1801f614b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f6152  mov     rcx, rax
0x1801f6155  test    rax, rax
0x1801f6158  jz      short loc_1801F6179
0x1801f615a  mov     rax, [rax]
0x1801f615d  mov     edx, 7F0h
0x1801f6162  mov     rax, [rax+8]
0x1801f6166  call    cs:__guard_dispatch_icall_fptr
0x1801f616c  test    eax, eax
0x1801f616e  jz      short loc_1801F6179
0x1801f6170  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f6177  jmp     short loc_1801F6187
0x1801f6179  lea     rcx, qword_1803CE250; this
0x1801f6180  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f6187  cmp     [rcx+8], r12b
0x1801f618b  jz      short loc_1801F61B2
0x1801f618d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f6192  cmp     [rax+7CCh], ebx
0x1801f6198  jz      short loc_1801F61B2
0x1801f619a  mov     r9d, ebx; int
0x1801f619d  lea     rdx, aCmfvideobranch_2; "CMFVideoBranchLoaderV1::InsertAndConnec"...
0x1801f61a4  mov     r8d, 22Fh; int
0x1801f61aa  mov     rcx, rax; this
0x1801f61ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f61b2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1801f61b9  jb      loc_1801F6B56
0x1801f61bf  mov     edx, 39h ; '9'
0x1801f61c4  lea     r8, WPP_84077d43404e382a16b12f731fadc2a0_Traceguids
0x1801f61cb  jmp     loc_1801F6B3F
0x1801f61d0  mov     rax, [r14]
0x1801f61d3  mov     rcx, r14
0x1801f61d6  mov     rdx, [rsp+190h+ppMFType]
0x1801f61db  mov     rax, [rax+100h]
0x1801f61e2  call    cs:__guard_dispatch_icall_fptr
0x1801f61e8  mov     ebx, eax
0x1801f61ea  test    eax, eax
0x1801f61ec  jns     loc_1801F6288
0x1801f61f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f61f9  test    rcx, rcx
0x1801f61fc  jnz     short loc_1801F6246
0x1801f61fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f6205  nop     dword ptr [rax+rax+00h]
0x1801f620a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f6211  mov     rcx, rax
0x1801f6214  test    rax, rax
0x1801f6217  jz      short loc_1801F6238
0x1801f6219  mov     rax, [rax]
0x1801f621c  mov     edx, 7F0h
0x1801f6221  mov     rax, [rax+8]
0x1801f6225  call    cs:__guard_dispatch_icall_fptr
0x1801f622b  test    eax, eax
0x1801f622d  jz      short loc_1801F6238
0x1801f622f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f6236  jmp     short loc_1801F6246
0x1801f6238  lea     rcx, qword_1803CE250; this
0x1801f623f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f6246  cmp     [rcx+8], r12b
0x1801f624a  jz      short loc_1801F6271
0x1801f624c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f6251  cmp     [rax+7CCh], ebx
0x1801f6257  jz      short loc_1801F6271
0x1801f6259  mov     r9d, ebx; int
0x1801f625c  lea     rdx, aCmfvideobranch_2; "CMFVideoBranchLoaderV1::InsertAndConnec"...
0x1801f6263  mov     r8d, 230h; int
0x1801f6269  mov     rcx, rax; this
0x1801f626c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f6271  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1801f6278  jb      loc_1801F6B56
0x1801f627e  mov     edx, 3Ah ; ':'
0x1801f6283  jmp     loc_1801F61C4
0x1801f6288  mov     r13d, r12d
0x1801f628b  lea     rsi, WPP_84077d43404e382a16b12f731fadc2a0_Traceguids
0x1801f6292  mov     r12d, [rbp+90h+arg_28]
0x1801f6299  test    r12b, 4
0x1801f629d  jz      loc_1801F64E2
0x1801f62a3  lea     r9, [rsp+190h+var_158]
0x1801f62a8  mov     [rsp+190h+var_15C], r13d
0x1801f62ad  lea     r8, [rsp+190h+var_15C]
0x1801f62b2  mov     [rsp+190h+var_158], r13d
0x1801f62b7  lea     rdx, MF_MT_FRAME_RATE
0x1801f62be  mov     rcx, r14
0x1801f62c1  call    MFGetAttribute2UINT32asUINT64
0x1801f62c6  mov     ebx, eax
0x1801f62c8  test    eax, eax
0x1801f62ca  jns     loc_1801F6366
0x1801f62d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f62d7  test    rcx, rcx
0x1801f62da  jnz     short loc_1801F6324
0x1801f62dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f62e3  nop     dword ptr [rax+rax+00h]
0x1801f62e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f62ef  mov     rcx, rax
0x1801f62f2  test    rax, rax
0x1801f62f5  jz      short loc_1801F6316
0x1801f62f7  mov     rax, [rax]
0x1801f62fa  mov     edx, 7F0h
0x1801f62ff  mov     rax, [rax+8]
0x1801f6303  call    cs:__guard_dispatch_icall_fptr
0x1801f6309  test    eax, eax
0x1801f630b  jz      short loc_1801F6316
0x1801f630d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f6314  jmp     short loc_1801F6324
0x1801f6316  lea     rcx, qword_1803CE250; this
0x1801f631d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f6324  cmp     [rcx+8], r13b
0x1801f6328  jz      short loc_1801F634F
0x1801f632a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f632f  cmp     [rax+7CCh], ebx
0x1801f6335  jz      short loc_1801F634F
0x1801f6337  mov     r9d, ebx; int
0x1801f633a  lea     rdx, aCmfvideobranch_2; "CMFVideoBranchLoaderV1::InsertAndConnec"...
0x1801f6341  mov     r8d, 23Eh; int
0x1801f6347  mov     rcx, rax; this
0x1801f634a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f634f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801f6356  jb      loc_1801F6B56
0x1801f635c  mov     edx, 3Bh ; ';'
0x1801f6361  jmp     loc_1801F6B3C
0x1801f6366  lea     r9, [rsp+190h+var_150]
0x1801f636b  mov     [rsp+190h+var_154], r13d
0x1801f6370  lea     r8, [rsp+190h+var_154]
0x1801f6375  mov     [rsp+190h+var_150], r13d
0x1801f637a  lea     rdx, MF_MT_FRAME_RATE
0x1801f6381  mov     rcx, r15
0x1801f6384  call    MFGetAttribute2UINT32asUINT64
0x1801f6389  mov     ebx, eax
0x1801f638b  test    eax, eax
0x1801f638d  jns     loc_1801F6429
0x1801f6393  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f639a  test    rcx, rcx
0x1801f639d  jnz     short loc_1801F63E7
0x1801f639f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f63a6  nop     dword ptr [rax+rax+00h]
0x1801f63ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f63b2  mov     rcx, rax
0x1801f63b5  test    rax, rax
0x1801f63b8  jz      short loc_1801F63D9
0x1801f63ba  mov     rax, [rax]
0x1801f63bd  mov     edx, 7F0h
0x1801f63c2  mov     rax, [rax+8]
0x1801f63c6  call    cs:__guard_dispatch_icall_fptr
0x1801f63cc  test    eax, eax
0x1801f63ce  jz      short loc_1801F63D9
0x1801f63d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f63d7  jmp     short loc_1801F63E7
0x1801f63d9  lea     rcx, qword_1803CE250; this
0x1801f63e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f63e7  cmp     [rcx+8], r13b
0x1801f63eb  jz      short loc_1801F6412
0x1801f63ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f63f2  cmp     [rax+7CCh], ebx
0x1801f63f8  jz      short loc_1801F6412
0x1801f63fa  mov     r9d, ebx; int
0x1801f63fd  lea     rdx, aCmfvideobranch_2; "CMFVideoBranchLoaderV1::InsertAndConnec"...
0x1801f6404  mov     r8d, 241h; int
0x1801f640a  mov     rcx, rax; this
0x1801f640d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f6412  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801f6419  jb      loc_1801F6B56
0x1801f641f  mov     edx, 3Ch ; '<'
0x1801f6424  jmp     loc_1801F6B3C
0x1801f6429  mov     eax, [rsp+190h+var_15C]
0x1801f642d  xorps   xmm0, xmm0
0x1801f6430  xorps   xmm2, xmm2
0x1801f6433  xorps   xmm1, xmm1
0x1801f6436  cvtsi2sd xmm2, rax
0x1801f643b  mov     eax, [rsp+190h+var_158]
0x1801f643f  cvtsi2sd xmm0, rax
0x1801f6444  mov     eax, [rsp+190h+var_154]
0x1801f6448  cvtsi2sd xmm1, rax
0x1801f644d  mov     eax, [rsp+190h+var_150]
0x1801f6451  divsd   xmm2, xmm0
0x1801f6455  xorps   xmm0, xmm0
0x1801f6458  cvtsi2sd xmm0, rax
0x1801f645d  divsd   xmm1, xmm0
0x1801f6461  comisd  xmm2, xmm1
0x1801f6465  jbe     short loc_1801F64DC
0x1801f6467  mov     r8, [rsp+190h+ppMFType]; struct IMFMediaType *
0x1801f646c  lea     rdx, [rbp+90h+var_B0]; struct COutputTopologyPin *
0x1801f6470  mov     [rsp+190h+var_168], r13d; int
0x1801f6475  mov     r9, r14; struct IMFMediaType *
0x1801f6478  mov     rcx, rdi; this
0x1801f647b  mov     [rsp+190h+var_170], r15; struct IMFMediaType *
0x1801f6480  call    ?InsertFRC@CMFVideoBranchLoaderV1@@QEAAJAEAVCOutputTopologyPin@@PEAUIMFMediaType@@11H@Z; CMFVideoBranchLoaderV1::InsertFRC(COutputTopologyPin &,IMFMediaType *,IMFMediaType *,IMFMediaType *,int)
0x1801f6485  mov     ebx, eax
0x1801f6487  test    eax, eax
0x1801f6489  jns     short loc_1801F64E2
0x1801f648b  test    r12b, 3
0x1801f648f  jnz     short loc_1801F64BB
0x1801f6491  cmp     cs:byte_1803CECE9, 1
0x1801f6498  jb      loc_1801F6B56
0x1801f649e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f64a5  mov     edx, 3Eh ; '>'
0x1801f64aa  mov     r8, rsi
0x1801f64ad  mov     rcx, [rcx+38h]
0x1801f64b1  call    WPP_SF_
0x1801f64b6  jmp     loc_1801F6B56
0x1801f64bb  cmp     cs:byte_1803CECE9, 10h
0x1801f64c2  jb      short loc_1801F64DC
0x1801f64c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801f64cb  mov     edx, 3Dh ; '='
0x1801f64d0  mov     r8, rsi
0x1801f64d3  mov     rcx, [rcx+38h]
0x1801f64d7  call    WPP_SF_
0x1801f64dc  mov     r13d, 1
0x1801f64e2  mov     eax, r12d
0x1801f64e5  and     eax, 3
0x1801f64e8  cmp     al, 3
0x1801f64ea  jnz     loc_1801F66D6
0x1801f64f0  lea     r9, [rsp+190h+var_158]
0x1801f64f5  mov     [rsp+190h+var_15C], 0
0x1801f64fd  lea     r8, [rsp+190h+var_15C]
0x1801f6502  mov     [rsp+190h+var_158], 0
0x1801f650a  lea     rdx, MF_MT_FRAME_SIZE
0x1801f6511  mov     rcx, r14
0x1801f6514  call    MFGetAttribute2UINT32asUINT64
0x1801f6519  mov     ebx, eax
0x1801f651b  test    eax, eax
0x1801f651d  jns     loc_1801F65B9
0x1801f6523  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f652a  test    rcx, rcx
0x1801f652d  jnz     short loc_1801F6577
0x1801f652f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f6536  nop     dword ptr [rax+rax+00h]
0x1801f653b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f6542  mov     rcx, rax
0x1801f6545  test    rax, rax
0x1801f6548  jz      short loc_1801F6569
0x1801f654a  mov     rax, [rax]
0x1801f654d  mov     edx, 7F0h
0x1801f6552  mov     rax, [rax+8]
0x1801f6556  call    cs:__guard_dispatch_icall_fptr
0x1801f655c  test    eax, eax
0x1801f655e  jz      short loc_1801F6569
0x1801f6560  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f6567  jmp     short loc_1801F6577
0x1801f6569  lea     rcx, qword_1803CE250; this
  ... truncated ...
```
