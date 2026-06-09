# CDShowWrapper::CreateGraph(void)

- ea: `0x180030060`
- end: `0x180030f39`
- name: `?CreateGraph@CDShowWrapper@@MEAAJXZ`
- size: `3801`
- prototype: `__int64 __fastcall(CDShowWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x18002fa04`
- `0x18002fb4c`
- `0x18002ff0c`
- `0x180030060`
- `0x180030f40`
- `0x18003153c`
- `0x18003221c`
- `0x180032570`
- `0x180032700`
- `0x180032988`
- `0x180032a50`
- `0x180032d8c`
- `0x18004a638`
- `0x180051ce4`
- `0x180053934`
- `0x180074160`
- `0x18007c8e8`
- `0x18007eb88`
- `0x18007f3d0`
- `0x180083f14`
- `0x18008471c`
- `0x180086600`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003014c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003014c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030e99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030e99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003016e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003021d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800302c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030363`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030426`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800304f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800305b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003069c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003075f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003085d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030912`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800309d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030a7d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030c7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030d4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030dfb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003016e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003021d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800302c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030363`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030426`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800304f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800305b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003069c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003075f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003085d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030912`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800309d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030a7d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030c7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030d4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030dfb`
- `MFPlat!MFCreatePathFromURL` at `0x180030658`
- `MFPlat!MFCreatePathFromURL` at `0x180030658`

## string_xrefs

- `0x18003008a`: `CDShowWrapper::CreateGraph`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::CreateGraph(CDShowWrapper *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int128 v4; // xmm0
  struct IPin *v5; // rbx
  HRESULT Instance; // edi
  CallStackTracing *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  CallStackTracing *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  CGITPtr *v20; // rcx
  CallStackTracing *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  CallStackTracing *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  struct IBaseFilter **v31; // r14
  __int64 v32; // rax
  CallStackTracing *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rax
  __int64 v37; // r11
  CallStackTracing *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  struct IBaseFilter *v41; // rdx
  CallStackTracing *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  CallStackTracing *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  CallStackTracing *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  CallStackTracing *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // r8
  const struct _GUID *v56; // rdx
  struct IBaseFilter *v57; // rdx
  struct IBaseFilter *v58; // rdx
  CallStackTracing *v59; // rcx
  struct CallStackContext *v60; // rax
  CallStackTracing *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  CallStackTracing *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  CallStackTracing *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  CallStackTracing *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  _BYTE v74[8]; // [rsp+30h] [rbp-49h] BYREF
  struct IUnknown *ppv; // [rsp+38h] [rbp-41h] BYREF
  int v76; // [rsp+40h] [rbp-39h] BYREF
  int v77; // [rsp+44h] [rbp-35h] BYREF
  struct IMFCollection *v78; // [rsp+48h] [rbp-31h] BYREF
  struct IPin *v79; // [rsp+50h] [rbp-29h] BYREF
  struct IBaseFilter *v80; // [rsp+58h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-19h] BYREF
  __int64 v82; // [rsp+68h] [rbp-11h] BYREF
  struct IPin *v83[2]; // [rsp+70h] [rbp-9h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v74, "CDShowWrapper::CreateGraph", 3185);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
    v4 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, struct IPin **))(**((_QWORD **)this + 60) + 280LL))(
                      *((_QWORD *)this + 60),
                      v83);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
    *((_OWORD *)ThreadRelativeContext + 125) = v4;
  }
  v80 = 0;
  v83[0] = 0;
  v5 = 0;
  v82 = 0;
  v79 = 0;
  v76 = 0;
  v77 = 0;
  pv = 0;
  ppv = 0;
  Instance = CoCreateInstance(&CLSID_FilterGraph, 0, 1u, &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770, (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)v9 + 499) != Instance )
        CallStackContext::TraceFailure(v9, "CDShowWrapper::CreateGraph", 3206, Instance);
    }
    if ( g_wppLevels )
    {
      v10 = 285;
LABEL_228:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
        this,
        Instance);
      goto LABEL_229;
    }
    goto LABEL_229;
  }
  Instance = CGITPtr::Set((CDShowWrapper *)((char *)this + 48), &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770, ppv);
  if ( Instance >= 0 )
  {
    Instance = CDShowWrapper::SetupThreadpoolWait(this);
    if ( Instance < 0 )
    {
      v14 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext(v14);
        if ( *((_DWORD *)v16 + 499) != Instance )
          CallStackContext::TraceFailure(v16, "CDShowWrapper::CreateGraph", 3212, Instance);
      }
      if ( g_wppLevels )
      {
        v10 = 287;
        goto LABEL_228;
      }
      goto LABEL_229;
    }
    Instance = CDShowWrapper::SetupFilterScreening(this);
    if ( Instance < 0 )
    {
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext(v17);
        if ( *((_DWORD *)v19 + 499) != Instance )
          CallStackContext::TraceFailure(v19, "CDShowWrapper::CreateGraph", 3217, Instance);
      }
      if ( g_wppLevels )
      {
        v10 = 288;
        goto LABEL_228;
      }
      goto LABEL_229;
    }
    v20 = (CGITPtr *)(*((_QWORD *)this + 1) + 204LL);
    if ( *(_DWORD *)v20 )
    {
      v78 = 0;
      Instance = CGITPtr::Get(v20, &GUID_5bc8a76b_869a_46a3_9b03_fa218a66aebe, (void **)&v78);
      if ( Instance < 0 )
      {
        v21 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext(v21);
          if ( *((_DWORD *)v23 + 499) != Instance )
            CallStackContext::TraceFailure(v23, "CDShowWrapper::CreateGraph", 3227, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_61;
        v24 = 289;
LABEL_60:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v24,
          &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
          this,
          Instance);
LABEL_61:
        ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v78);
        goto LABEL_229;
      }
      Instance = CDShowWrapper::RegisterServiceProviders(this, v78);
      if ( Instance < 0 )
      {
        v25 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext(v25);
          if ( *((_DWORD *)v27 + 499) != Instance )
            CallStackContext::TraceFailure(v27, "CDShowWrapper::CreateGraph", 3228, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_61;
        v24 = 290;
        goto LABEL_60;
      }
      ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v78);
    }
    if ( *((_DWORD *)this + 107) )
    {
      Instance = CDShowWrapper::SetupMFBytestreamSource(this, &v80, &v76, &v77);
      if ( Instance < 0 )
      {
        v28 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext(v28);
          if ( *((_DWORD *)v30 + 499) != Instance )
            CallStackContext::TraceFailure(v30, "CDShowWrapper::CreateGraph", 3237, Instance);
        }
        if ( g_wppLevels )
        {
          v10 = 291;
          goto LABEL_228;
        }
        goto LABEL_229;
      }
    }
    v31 = (struct IBaseFilter **)((char *)this + 64);
    if ( v76 )
    {
      if ( v80 )
      {
        ((void (__fastcall *)(struct IBaseFilter *))v80->lpVtbl->AddRef)(v80);
        if ( *v31 )
          ((void (__fastcall *)(struct IBaseFilter *))(*v31)->lpVtbl->Release)(*v31);
        v41 = v80;
        *v31 = v80;
      }
      else
      {
        if ( *v31 )
        {
          ((void (__fastcall *)(struct IBaseFilter *))(*v31)->lpVtbl->Release)(*v31);
          *v31 = 0;
        }
        v41 = 0;
      }
      Instance = ((__int64 (__fastcall *)(struct IUnknown *, struct IBaseFilter *, const wchar_t *))ppv->lpVtbl[1].QueryInterface)(
                   ppv,
                   v41,
                   L"MF Source Filter");
      if ( Instance < 0 )
      {
        v42 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext(v42);
          if ( *((_DWORD *)v44 + 499) != Instance )
            CallStackContext::TraceFailure(v44, "CDShowWrapper::CreateGraph", 3261, Instance);
        }
        if ( g_wppLevels )
        {
          v10 = 294;
          goto LABEL_228;
        }
        goto LABEL_229;
      }
    }
    else
    {
      v32 = CMFBaseStringT<unsigned short>::PContents((char *)this + 16);
      if ( (int)MFCreatePathFromURL(v32, &pv) < 0 )
      {
        v36 = CMFBaseStringT<unsigned short>::PContents((char *)this + 16);
        Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, char *))(*(_QWORD *)v37 + 112LL))(
                     v37,
                     v36,
                     0,
                     (char *)this + 64);
        if ( Instance < 0 )
        {
          v38 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v39;
            if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
            {
              v38 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v38 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v38 + 8) )
          {
            v40 = CallStackTracing::GetThreadRelativeContext(v38);
            if ( *((_DWORD *)v40 + 499) != Instance )
              CallStackContext::TraceFailure(v40, "CDShowWrapper::CreateGraph", 3255, Instance);
          }
          if ( g_wppLevels )
          {
            v10 = 293;
            goto LABEL_228;
          }
          goto LABEL_229;
        }
      }
      else
      {
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, _QWORD, char *))ppv->lpVtbl[4].Release)(
                     ppv,
                     pv,
                     0,
                     (char *)this + 64);
        if ( Instance < 0 )
        {
          v33 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v34;
            if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
            {
              v33 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v33 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v33 + 8) )
          {
            v35 = CallStackTracing::GetThreadRelativeContext(v33);
            if ( *((_DWORD *)v35 + 499) != Instance )
              CallStackContext::TraceFailure(v35, "CDShowWrapper::CreateGraph", 3251, Instance);
          }
          if ( g_wppLevels )
          {
            v10 = 292;
            goto LABEL_228;
          }
          goto LABEL_229;
        }
      }
    }
    if ( v77 )
    {
      Instance = CDShowWrapper::SetupDemux(this, v83, &v79);
      if ( Instance < 0 )
      {
        v45 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext(v45);
          if ( *((_DWORD *)v47 + 499) != Instance )
            CallStackContext::TraceFailure(v47, "CDShowWrapper::CreateGraph", 3266, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_141;
        v48 = 295;
LABEL_140:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v48,
          &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
          this,
          Instance);
LABEL_141:
        v5 = v79;
        goto LABEL_229;
      }
      Instance = CDShowWrapper::ConnectSourceToDemux(this);
      if ( Instance < 0 )
      {
        v49 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext(v49);
          if ( *((_DWORD *)v51 + 499) != Instance )
            CallStackContext::TraceFailure(v51, "CDShowWrapper::CreateGraph", 3267, Instance);
        }
        if ( !g_wppLevels )
          goto LABEL_141;
        v48 = 296;
        goto LABEL_140;
      }
      v5 = v79;
      Instance = CDShowWrapper::ConfigureDemux(this, v79);
      if ( Instance < 0 )
      {
        v52 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v53;
          if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
          {
            v52 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v52 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v52 + 8) )
        {
          v54 = CallStackTracing::GetThreadRelativeContext(v52);
          if ( *((_DWORD *)v54 + 499) != Instance )
            CallStackContext::TraceFailure(v54, "CDShowWrapper::CreateGraph", 3272, Instance);
        }
        if ( g_wppLevels )
        {
          v10 = 297;
          goto LABEL_228;
        }
        goto LABEL_229;
      }
    }
    if ( *((_DWORD *)this + 116) )
    {
      if ( !*((_QWORD *)this + 9) )
        CDShowWrapper::CreatePreferredDemuxFilters(this);
      CDShowWrapper::CreatePreferredDecoderFilters(this);
    }
    else
    {
      v55 = *((_QWORD *)this + 1);
      v56 = *(const struct _GUID **)(v55 + 192);
      if ( !v56 )
        goto LABEL_171;
      CDShowWrapper::CreatePreferredFilters(this, v56, *(_DWORD *)(v55 + 200));
    }
    CDShowWrapper::InsertPreferredFilters(this);
LABEL_171:
    v57 = (struct IBaseFilter *)*((_QWORD *)this + 9);
    if ( !v57 )
      v57 = *v31;
    Instance = CDShowWrapper::ConnectSplittersAndDecryptors(this, v57);
    if ( Instance >= 0 )
    {
      Instance = CDShowWrapper::CollectMediaTypes(this, v58);
      if ( Instance >= 0 )
      {
        if ( *((_DWORD *)this + 72) )
        {
          if ( *((_DWORD *)this + 116) || *(_QWORD *)(*((_QWORD *)this + 1) + 192LL) )
            CDShowWrapper::RemoveUnusedPreferredFilters(this);
          Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))ppv->lpVtbl->QueryInterface)(
                       ppv,
                       &GUID_56a86899_0ad4_11ce_b03a_0020af0ba770,
                       &v82);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v82 + 64LL))(v82, 0);
            if ( Instance < 0 )
            {
              v70 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v71;
                if ( v71
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
                {
                  v70 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v70 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              if ( *((_BYTE *)v70 + 8) )
              {
                v72 = CallStackTracing::GetThreadRelativeContext(v70);
                if ( *((_DWORD *)v72 + 499) != Instance )
                  CallStackContext::TraceFailure(v72, "CDShowWrapper::CreateGraph", 3339, Instance);
              }
              if ( g_wppLevels )
              {
                v10 = 302;
                goto LABEL_228;
              }
            }
          }
          else
          {
            v67 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v68;
              if ( v68
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
              {
                v67 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v67 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v67 + 8) )
            {
              v69 = CallStackTracing::GetThreadRelativeContext(v67);
              if ( *((_DWORD *)v69 + 499) != Instance )
                CallStackContext::TraceFailure(v69, "CDShowWrapper::CreateGraph", 3337, Instance);
            }
            if ( g_wppLevels )
            {
              v10 = 301;
              goto LABEL_228;
            }
          }
        }
        else
        {
          v64 = CallStackTracing::s_wpInstance;
          Instance = -1072873832;
          if ( !CallStackTracing::s_wpInstance )
          {
            v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v65;
            if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
            {
              v64 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v64 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v64 + 8) )
          {
            v66 = CallStackTracing::GetThreadRelativeContext(v64);
            if ( *((_DWORD *)v66 + 499) != -1072873832 )
              CallStackContext::TraceFailure(v66, "CDShowWrapper::CreateGraph", 3323, -1072873832);
          }
          if ( g_wppLevels )
          {
            v10 = 300;
            goto LABEL_228;
          }
        }
      }
      else
      {
        v61 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v62;
          if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
          {
            v61 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v61 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v61 + 8) )
        {
          v63 = CallStackTracing::GetThreadRelativeContext(v61);
          if ( *((_DWORD *)v63 + 499) != Instance )
            CallStackContext::TraceFailure(v63, "CDShowWrapper::CreateGraph", 3316, Instance);
        }
        if ( g_wppLevels )
        {
          v10 = 299;
          goto LABEL_228;
        }
      }
    }
    else
    {
      v59 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v59 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v60 = CallStackTracing::GetThreadRelativeContext(v59);
        if ( *((_DWORD *)v60 + 499) != Instance )
          CallStackContext::TraceFailure(v60, "CDShowWrapper::CreateGraph", 3314, Instance);
      }
      if ( g_wppLevels )
      {
        v10 = 298;
        goto LABEL_228;
      }
    }
    goto LABEL_229;
  }
  v11 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
    CallStackTracing::s_wpInstance = v12;
    if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
    {
      v11 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = (CallStackTracing *)&qword_1800EB130;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v13 = CallStackTracing::GetThreadRelativeContext(v11);
    if ( *((_DWORD *)v13 + 499) != Instance )
      CallStackContext::TraceFailure(v13, "CDShowWrapper::CreateGraph", 3207, Instance);
  }
  if ( g_wppLevels )
  {
    v10 = 286;
    goto LABEL_228;
  }
LABEL_229:
  CoTaskMemFree(pv);
  if ( ppv )
    ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
  if ( v82 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
  if ( v5 )
    ((void (__fastcall *)(struct IPin *))v5->lpVtbl->Release)(v5);
  if ( v83[0] )
    ((void (__fastcall *)(struct IPin *))v83[0]->lpVtbl->Release)(v83[0]);
  if ( v80 )
    ((void (__fastcall *)(struct IBaseFilter *))v80->lpVtbl->Release)(v80);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v74);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180030060  push    rbp
0x180030062  push    rbx
0x180030063  push    rsi
0x180030064  push    rdi
0x180030065  push    r12
0x180030067  push    r13
0x180030069  push    r14
0x18003006b  push    r15
0x18003006d  lea     rbp, [rsp-1Fh]
0x180030072  sub     rsp, 98h
0x180030079  mov     rax, cs:__security_cookie
0x180030080  xor     rax, rsp
0x180030083  mov     [rbp+57h+var_50], rax
0x180030087  mov     rsi, rcx
0x18003008a  lea     r13, aCdshowwrapperC_2; "CDShowWrapper::CreateGraph"
0x180030091  mov     rdx, r13; char *
0x180030094  lea     rcx, [rbp+57h+var_A0]; this
0x180030098  mov     r8d, 0C71h; int
0x18003009e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800300a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800300aa  xor     r15d, r15d
0x1800300ad  cmp     [rcx+8], r15b
0x1800300b1  jz      short loc_180030107
0x1800300b3  cmp     [rsi+1E0h], r15
0x1800300ba  jz      short loc_180030107
0x1800300bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800300c1  mov     rcx, [rsi+1E0h]
0x1800300c8  mov     rdi, rax
0x1800300cb  mov     rdx, [rcx]
0x1800300ce  mov     rax, [rdx+128h]
0x1800300d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300da  mov     rcx, [rsi+1E0h]
0x1800300e1  mov     ebx, eax
0x1800300e3  mov     rdx, [rcx]
0x1800300e6  mov     rax, [rdx+118h]
0x1800300ed  lea     rdx, [rbp+57h+var_60]
0x1800300f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300f6  movups  xmm0, xmmword ptr [rax]
0x1800300f9  mov     [rdi+7E0h], ebx
0x1800300ff  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180030107  lea     rax, [rbp+57h+var_98]
0x18003010b  mov     [rbp+57h+var_78], r15
0x18003010f  mov     r12d, 1
0x180030115  mov     [rbp+57h+var_60], r15
0x180030119  mov     rbx, r15
0x18003011c  mov     [rbp+57h+var_68], r15
0x180030120  mov     r8d, r12d; dwClsContext
0x180030123  mov     [rbp+57h+var_80], rbx
0x180030127  lea     r9, _GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770; riid
0x18003012e  mov     [rbp+57h+var_90], r15d
0x180030132  xor     edx, edx; pUnkOuter
0x180030134  mov     [rbp+57h+var_8C], r15d
0x180030138  lea     rcx, CLSID_FilterGraph; rclsid
0x18003013f  mov     [rbp+57h+pv], r15
0x180030143  mov     [rbp+57h+var_98], r15
0x180030147  mov     [rsp+0D0h+ppv], rax; ppv
0x18003014c  call    cs:__imp_CoCreateInstance
0x180030153  nop     dword ptr [rax+rax+00h]
0x180030158  mov     edi, eax
0x18003015a  test    eax, eax
0x18003015c  jns     loc_1800301F3
0x180030162  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030169  test    rcx, rcx
0x18003016c  jnz     short loc_1800301B5
0x18003016e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030175  nop     dword ptr [rax+rax+00h]
0x18003017a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030181  mov     rcx, rax
0x180030184  test    rax, rax
0x180030187  jz      short loc_1800301A7
0x180030189  mov     rax, [rax]
0x18003018c  mov     edx, 7F0h
0x180030191  mov     rax, [rax+8]
0x180030195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003019a  test    eax, eax
0x18003019c  jz      short loc_1800301A7
0x18003019e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800301a5  jmp     short loc_1800301B5
0x1800301a7  lea     rcx, qword_1800EB130; this
0x1800301ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800301b5  cmp     [rcx+8], r15b
0x1800301b9  jz      short loc_1800301DC
0x1800301bb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800301c0  cmp     [rax+7CCh], edi
0x1800301c6  jz      short loc_1800301DC
0x1800301c8  mov     r9d, edi; int
0x1800301cb  mov     r8d, 0C86h; int
0x1800301d1  mov     rdx, r13; char *
0x1800301d4  mov     rcx, rax; this
0x1800301d7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800301dc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800301e3  jb      loc_180030E95
0x1800301e9  mov     edx, 11Dh
0x1800301ee  jmp     loc_180030E77
0x1800301f3  mov     r8, [rbp+57h+var_98]; struct IUnknown *
0x1800301f7  lea     rcx, [rsi+30h]; this
0x1800301fb  lea     rdx, _GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770; struct _GUID *
0x180030202  call    ?Set@CGITPtr@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z; CGITPtr::Set(_GUID const &,IUnknown *)
0x180030207  mov     edi, eax
0x180030209  test    eax, eax
0x18003020b  jns     loc_1800302A2
0x180030211  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030218  test    rcx, rcx
0x18003021b  jnz     short loc_180030264
0x18003021d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030224  nop     dword ptr [rax+rax+00h]
0x180030229  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030230  mov     rcx, rax
0x180030233  test    rax, rax
0x180030236  jz      short loc_180030256
0x180030238  mov     rax, [rax]
0x18003023b  mov     edx, 7F0h
0x180030240  mov     rax, [rax+8]
0x180030244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030249  test    eax, eax
0x18003024b  jz      short loc_180030256
0x18003024d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030254  jmp     short loc_180030264
0x180030256  lea     rcx, qword_1800EB130; this
0x18003025d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030264  cmp     [rcx+8], r15b
0x180030268  jz      short loc_18003028B
0x18003026a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003026f  cmp     [rax+7CCh], edi
0x180030275  jz      short loc_18003028B
0x180030277  mov     r9d, edi; int
0x18003027a  mov     r8d, 0C87h; int
0x180030280  mov     rdx, r13; char *
0x180030283  mov     rcx, rax; this
0x180030286  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003028b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180030292  jb      loc_180030E95
0x180030298  mov     edx, 11Eh
0x18003029d  jmp     loc_180030E77
0x1800302a2  mov     rcx, rsi; this
0x1800302a5  call    ?SetupThreadpoolWait@CDShowWrapper@@IEAAJXZ; CDShowWrapper::SetupThreadpoolWait(void)
0x1800302aa  mov     edi, eax
0x1800302ac  test    eax, eax
0x1800302ae  jns     loc_180030345
0x1800302b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800302bb  test    rcx, rcx
0x1800302be  jnz     short loc_180030307
0x1800302c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800302c7  nop     dword ptr [rax+rax+00h]
0x1800302cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800302d3  mov     rcx, rax
0x1800302d6  test    rax, rax
0x1800302d9  jz      short loc_1800302F9
0x1800302db  mov     rax, [rax]
0x1800302de  mov     edx, 7F0h
0x1800302e3  mov     rax, [rax+8]
0x1800302e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302ec  test    eax, eax
0x1800302ee  jz      short loc_1800302F9
0x1800302f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800302f7  jmp     short loc_180030307
0x1800302f9  lea     rcx, qword_1800EB130; this
0x180030300  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030307  cmp     [rcx+8], r15b
0x18003030b  jz      short loc_18003032E
0x18003030d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030312  cmp     [rax+7CCh], edi
0x180030318  jz      short loc_18003032E
0x18003031a  mov     r9d, edi; int
0x18003031d  mov     r8d, 0C8Ch; int
0x180030323  mov     rdx, r13; char *
0x180030326  mov     rcx, rax; this
0x180030329  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003032e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180030335  jb      loc_180030E95
0x18003033b  mov     edx, 11Fh
0x180030340  jmp     loc_180030E77
0x180030345  mov     rcx, rsi; this
0x180030348  call    ?SetupFilterScreening@CDShowWrapper@@IEAAJXZ; CDShowWrapper::SetupFilterScreening(void)
0x18003034d  mov     edi, eax
0x18003034f  test    eax, eax
0x180030351  jns     loc_1800303E8
0x180030357  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003035e  test    rcx, rcx
0x180030361  jnz     short loc_1800303AA
0x180030363  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003036a  nop     dword ptr [rax+rax+00h]
0x18003036f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030376  mov     rcx, rax
0x180030379  test    rax, rax
0x18003037c  jz      short loc_18003039C
0x18003037e  mov     rax, [rax]
0x180030381  mov     edx, 7F0h
0x180030386  mov     rax, [rax+8]
0x18003038a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003038f  test    eax, eax
0x180030391  jz      short loc_18003039C
0x180030393  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003039a  jmp     short loc_1800303AA
0x18003039c  lea     rcx, qword_1800EB130; this
0x1800303a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800303aa  cmp     [rcx+8], r15b
0x1800303ae  jz      short loc_1800303D1
0x1800303b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800303b5  cmp     [rax+7CCh], edi
0x1800303bb  jz      short loc_1800303D1
0x1800303bd  mov     r9d, edi; int
0x1800303c0  mov     r8d, 0C91h; int
0x1800303c6  mov     rdx, r13; char *
0x1800303c9  mov     rcx, rax; this
0x1800303cc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800303d1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800303d8  jb      loc_180030E95
0x1800303de  mov     edx, 120h
0x1800303e3  jmp     loc_180030E77
0x1800303e8  mov     rcx, [rsi+8]
0x1800303ec  add     rcx, 0CCh; this
0x1800303f3  cmp     [rcx], r15d
0x1800303f6  jz      loc_18003057E
0x1800303fc  lea     r8, [rbp+57h+var_88]; void **
0x180030400  mov     [rbp+57h+var_88], r15
0x180030404  lea     rdx, _GUID_5bc8a76b_869a_46a3_9b03_fa218a66aebe; struct _GUID *
0x18003040b  call    ?Get@CGITPtr@@QEAAJAEBU_GUID@@PEAPEAX@Z; CGITPtr::Get(_GUID const &,void * *)
0x180030410  mov     edi, eax
0x180030412  test    eax, eax
0x180030414  jns     loc_1800304CE
0x18003041a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030421  test    rcx, rcx
0x180030424  jnz     short loc_18003046D
0x180030426  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003042d  nop     dword ptr [rax+rax+00h]
0x180030432  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030439  mov     rcx, rax
0x18003043c  test    rax, rax
0x18003043f  jz      short loc_18003045F
0x180030441  mov     rax, [rax]
0x180030444  mov     edx, 7F0h
0x180030449  mov     rax, [rax+8]
0x18003044d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030452  test    eax, eax
0x180030454  jz      short loc_18003045F
0x180030456  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003045d  jmp     short loc_18003046D
0x18003045f  lea     rcx, qword_1800EB130; this
0x180030466  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003046d  cmp     [rcx+8], r15b
0x180030471  jz      short loc_180030494
0x180030473  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030478  cmp     [rax+7CCh], edi
0x18003047e  jz      short loc_180030494
0x180030480  mov     r9d, edi; int
0x180030483  mov     r8d, 0C9Bh; int
0x180030489  mov     rdx, r13; char *
0x18003048c  mov     rcx, rax; this
0x18003048f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030494  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18003049b  jb      short loc_1800304C0
0x18003049d  mov     edx, 121h
0x1800304a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800304a9  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x1800304b0  mov     r9, rsi
0x1800304b3  mov     dword ptr [rsp+0D0h+ppv], edi
0x1800304b7  mov     rcx, [rcx+10h]
0x1800304bb  call    WPP_SF_qD
0x1800304c0  lea     rcx, [rbp+57h+var_88]; void *
0x1800304c4  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x1800304c9  jmp     loc_180030E95
0x1800304ce  mov     rdx, [rbp+57h+var_88]; struct IMFCollection *
0x1800304d2  mov     rcx, rsi; this
0x1800304d5  call    ?RegisterServiceProviders@CDShowWrapper@@IEAAJPEAUIMFCollection@@@Z; CDShowWrapper::RegisterServiceProviders(IMFCollection *)
0x1800304da  mov     edi, eax
0x1800304dc  test    eax, eax
0x1800304de  jns     loc_180030575
0x1800304e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800304eb  test    rcx, rcx
0x1800304ee  jnz     short loc_180030537
0x1800304f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800304f7  nop     dword ptr [rax+rax+00h]
0x1800304fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030503  mov     rcx, rax
0x180030506  test    rax, rax
0x180030509  jz      short loc_180030529
0x18003050b  mov     rax, [rax]
0x18003050e  mov     edx, 7F0h
0x180030513  mov     rax, [rax+8]
0x180030517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003051c  test    eax, eax
0x18003051e  jz      short loc_180030529
0x180030520  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030527  jmp     short loc_180030537
0x180030529  lea     rcx, qword_1800EB130; this
0x180030530  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030537  cmp     [rcx+8], r15b
0x18003053b  jz      short loc_18003055E
0x18003053d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030542  cmp     [rax+7CCh], edi
0x180030548  jz      short loc_18003055E
0x18003054a  mov     r9d, edi; int
0x18003054d  mov     r8d, 0C9Ch; int
0x180030553  mov     rdx, r13; char *
0x180030556  mov     rcx, rax; this
0x180030559  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003055e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180030565  jb      loc_1800304C0
0x18003056b  mov     edx, 122h
  ... truncated ...
```
