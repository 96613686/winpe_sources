# CDShowSBEWrapper::CreateGraph(void)

- ea: `0x180097eb0`
- end: `0x180098e14`
- name: `?CreateGraph@CDShowSBEWrapper@@EEAAJXZ`
- size: `3940`
- prototype: `__int64 __fastcall(CDShowSBEWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18006a8d0`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x18002d514`
- `0x18003221c`
- `0x180032570`
- `0x180032a50`
- `0x180051ce4`
- `0x180053934`
- `0x18006cd70`
- `0x180074160`
- `0x180097eb0`
- `0x180099058`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180097f90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800981a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180097f90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800981a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098db0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098db0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098061`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098104`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800981c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009827b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098320`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800983d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009847a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098547`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800985ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098691`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098736`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800987f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800988cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009898d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098a42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098ae8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098bb6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098d12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180097fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098061`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098104`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800981c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009827b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098320`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800983d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009847a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098547`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800985ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098691`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098736`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800987f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800988cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009898d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098a42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098ae8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098bb6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098d12`
- `MFPlat!MFCreatePathFromURL` at `0x18009888c`
- `MFPlat!MFCreatePathFromURL` at `0x18009888c`

## string_xrefs

- `0x180097edd`: `CDShowSBEWrapper::CreateGraph`

## pseudocode

```c
__int64 __fastcall CDShowSBEWrapper::CreateGraph(CDShowSBEWrapper *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int128 v4; // xmm0
  HRESULT Instance; // ebx
  CallStackTracing *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  struct IBaseFilter **v16; // rdi
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  CallStackTracing *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  CallStackTracing *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 (__fastcall *v33)(__int64, __int64); // rax
  CallStackTracing *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  CallStackTracing *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  CallStackTracing *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rax
  CallStackTracing *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 v54; // rax
  __int64 v55; // r10
  CallStackTracing *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  CallStackTracing *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  CallStackTracing *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  CallStackTracing *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  CallStackTracing *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  CallStackTracing *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  _BYTE v75[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v76; // [rsp+38h] [rbp-48h] BYREF
  struct IUnknown *ppv; // [rsp+40h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-38h] BYREF
  struct IFilterGraph *v79; // [rsp+50h] [rbp-30h] BYREF
  __int64 v80; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v81[16]; // [rsp+60h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v75, "CDShowSBEWrapper::CreateGraph", 183);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
    v4 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 60) + 280LL))(
                      *((_QWORD *)this + 60),
                      v81);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
    *((_OWORD *)ThreadRelativeContext + 125) = v4;
  }
  v76 = 0;
  v80 = 0;
  pv = 0;
  ppv = 0;
  v79 = 0;
  Instance = CoCreateInstance(&CLSID_FilterGraph, 0, 1u, &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = CGITPtr::Set((CDShowSBEWrapper *)((char *)this + 48), &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770, ppv);
    if ( Instance >= 0 )
    {
      Instance = CDShowWrapper::SetupThreadpoolWait(this);
      if ( Instance >= 0 )
      {
        v16 = (struct IBaseFilter **)((char *)this + 64);
        Instance = CoCreateInstance(
                     &CLSID_StreamBufferSource,
                     0,
                     1u,
                     &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770,
                     (LPVOID *)this + 8);
        if ( Instance >= 0 )
        {
          Instance = ((__int64 (__fastcall *)(struct IBaseFilter *, GUID *, __int64 *))(*v16)->lpVtbl->QueryInterface)(
                       *v16,
                       &GUID_c6130043_9342_4cb9_8697_222ee967ced6,
                       &v76);
          if ( Instance >= 0 )
          {
            if ( v76 )
            {
              Instance = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v76)(
                           v76,
                           &GUID_4c131ffc_8c18_4ac3_b33a_494e3115a1a6,
                           &v80);
              if ( Instance < 0 )
              {
                v27 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                  CallStackTracing::s_wpInstance = v28;
                  if ( v28
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
                  {
                    v27 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v27 = (CallStackTracing *)&qword_1800EB130;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                  }
                }
                if ( *((_BYTE *)v27 + 8) )
                {
                  v29 = CallStackTracing::GetThreadRelativeContext(v27);
                  if ( *((_DWORD *)v29 + 499) != Instance )
                    CallStackContext::TraceFailure(v29, "CDShowSBEWrapper::CreateGraph", 212, Instance);
                }
                if ( g_wppLevels )
                {
                  v9 = 22;
                  goto LABEL_232;
                }
                goto LABEL_233;
              }
              if ( v80 )
              {
                v33 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v80 + 56LL);
                switch ( *((_DWORD *)this + 128) )
                {
                  case 1:
                    Instance = v33(v80, 7);
                    if ( Instance < 0 )
                    {
                      v43 = CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                        CallStackTracing::s_wpInstance = v44;
                        if ( v44
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(
                               v44,
                               2032) )
                        {
                          v43 = CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v43 = (CallStackTracing *)&qword_1800EB130;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                        }
                      }
                      if ( *((_BYTE *)v43 + 8) )
                      {
                        v45 = CallStackTracing::GetThreadRelativeContext(v43);
                        if ( *((_DWORD *)v45 + 499) != Instance )
                          CallStackContext::TraceFailure(v45, "CDShowSBEWrapper::CreateGraph", 219, Instance);
                      }
                      if ( g_wppLevels )
                      {
                        v9 = 24;
                        goto LABEL_232;
                      }
                      goto LABEL_233;
                    }
                    break;
                  case 2:
                    Instance = v33(v80, 6);
                    if ( Instance < 0 )
                    {
                      v40 = CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                        CallStackTracing::s_wpInstance = v41;
                        if ( v41
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(
                               v41,
                               2032) )
                        {
                          v40 = CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v40 = (CallStackTracing *)&qword_1800EB130;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                        }
                      }
                      if ( *((_BYTE *)v40 + 8) )
                      {
                        v42 = CallStackTracing::GetThreadRelativeContext(v40);
                        if ( *((_DWORD *)v42 + 499) != Instance )
                          CallStackContext::TraceFailure(v42, "CDShowSBEWrapper::CreateGraph", 222, Instance);
                      }
                      if ( g_wppLevels )
                      {
                        v9 = 25;
                        goto LABEL_232;
                      }
                      goto LABEL_233;
                    }
                    break;
                  case 3:
                    Instance = v33(v80, 5);
                    if ( Instance < 0 )
                    {
                      v37 = CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                        CallStackTracing::s_wpInstance = v38;
                        if ( v38
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(
                               v38,
                               2032) )
                        {
                          v37 = CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v37 = (CallStackTracing *)&qword_1800EB130;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                        }
                      }
                      if ( *((_BYTE *)v37 + 8) )
                      {
                        v39 = CallStackTracing::GetThreadRelativeContext(v37);
                        if ( *((_DWORD *)v39 + 499) != Instance )
                          CallStackContext::TraceFailure(v39, "CDShowSBEWrapper::CreateGraph", 225, Instance);
                      }
                      if ( g_wppLevels )
                      {
                        v9 = 26;
                        goto LABEL_232;
                      }
                      goto LABEL_233;
                    }
                    break;
                  default:
                    Instance = v33(v80, 7);
                    if ( Instance < 0 )
                    {
                      v34 = CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                        CallStackTracing::s_wpInstance = v35;
                        if ( v35
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(
                               v35,
                               2032) )
                        {
                          v34 = CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v34 = (CallStackTracing *)&qword_1800EB130;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                        }
                      }
                      if ( *((_BYTE *)v34 + 8) )
                      {
                        v36 = CallStackTracing::GetThreadRelativeContext(v34);
                        if ( *((_DWORD *)v36 + 499) != Instance )
                          CallStackContext::TraceFailure(v36, "CDShowSBEWrapper::CreateGraph", 228, Instance);
                      }
                      if ( g_wppLevels )
                      {
                        v9 = 27;
                        goto LABEL_232;
                      }
                      goto LABEL_233;
                    }
                    break;
                }
                v46 = *((_QWORD *)this + 93);
                if ( v46 )
                {
                  Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v76 + 40LL))(
                               v76,
                               v46,
                               0,
                               0);
                  if ( Instance < 0 )
                  {
                    v47 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                      CallStackTracing::s_wpInstance = v48;
                      if ( v48
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(
                             v48,
                             2032) )
                      {
                        v47 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v47 = (CallStackTracing *)&qword_1800EB130;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                      }
                    }
                    if ( *((_BYTE *)v47 + 8) )
                    {
                      v49 = CallStackTracing::GetThreadRelativeContext(v47);
                      if ( *((_DWORD *)v49 + 499) != Instance )
                        CallStackContext::TraceFailure(v49, "CDShowSBEWrapper::CreateGraph", 234, Instance);
                    }
                    if ( g_wppLevels )
                    {
                      v9 = 28;
                      goto LABEL_232;
                    }
                    goto LABEL_233;
                  }
                }
                else
                {
                  v50 = CMFBaseStringT<unsigned short>::PContents((char *)this + 16);
                  if ( (int)MFCreatePathFromURL(v50, &pv) < 0 )
                  {
                    v54 = CMFBaseStringT<unsigned short>::PContents((char *)this + 16);
                    Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v55 + 24LL))(
                                 v55,
                                 v54,
                                 0);
                    if ( Instance < 0 )
                    {
                      v56 = CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                        CallStackTracing::s_wpInstance = v57;
                        if ( v57
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(
                               v57,
                               2032) )
                        {
                          v56 = CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v56 = (CallStackTracing *)&qword_1800EB130;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                        }
                      }
                      if ( *((_BYTE *)v56 + 8) )
                      {
                        v58 = CallStackTracing::GetThreadRelativeContext(v56);
                        if ( *((_DWORD *)v58 + 499) != Instance )
                          CallStackContext::TraceFailure(v58, "CDShowSBEWrapper::CreateGraph", 248, Instance);
                      }
                      if ( g_wppLevels )
                      {
                        v9 = 30;
                        goto LABEL_232;
                      }
                      goto LABEL_233;
                    }
                  }
                  else
                  {
                    Instance = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD))(*(_QWORD *)v76 + 24LL))(v76, pv, 0);
                    if ( Instance < 0 )
                    {
                      v51 = CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                        CallStackTracing::s_wpInstance = v52;
                        if ( v52
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(
                               v52,
                               2032) )
                        {
                          v51 = CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v51 = (CallStackTracing *)&qword_1800EB130;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                        }
                      }
                      if ( *((_BYTE *)v51 + 8) )
                      {
                        v53 = CallStackTracing::GetThreadRelativeContext(v51);
                        if ( *((_DWORD *)v53 + 499) != Instance )
                          CallStackContext::TraceFailure(v53, "CDShowSBEWrapper::CreateGraph", 244, Instance);
                      }
                      if ( g_wppLevels )
                      {
                        v9 = 29;
                        goto LABEL_232;
                      }
                      goto LABEL_233;
                    }
                  }
                }
                Instance = ((__int64 (__fastcall *)(struct IUnknown *, struct IBaseFilter *, const wchar_t *))ppv->lpVtbl[1].QueryInterface)(
                             ppv,
                             *v16,
                             L"MF Source Filter");
                if ( Instance >= 0 )
                {
                  Instance = CDShowSBEWrapper::ConnectSBEFilter(this, *v16);
                  if ( Instance >= 0 )
                  {
                    if ( *((_DWORD *)this + 72) )
                    {
                      Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IFilterGraph **))ppv->lpVtbl->QueryInterface)(
                                   ppv,
                                   &GUID_56a8689f_0ad4_11ce_b03a_0020af0ba770,
                                   &v79);
                      if ( Instance >= 0 )
                      {
                        Instance = CDShowSBEWrapper::HookupGraphEventService(this, v79);
                        if ( Instance < 0 )
                        {
                          v71 = CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                            CallStackTracing::s_wpInstance = v72;
                            if ( v72
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(
                                   v72,
                                   2032) )
                            {
                              v71 = CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v71 = (CallStackTracing *)&qword_1800EB130;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                            }
                          }
                          if ( *((_BYTE *)v71 + 8) )
                          {
                            v73 = CallStackTracing::GetThreadRelativeContext(v71);
                            if ( *((_DWORD *)v73 + 499) != Instance )
                              CallStackContext::TraceFailure(v73, "CDShowSBEWrapper::CreateGraph", 269, Instance);
                          }
                          if ( g_wppLevels )
                          {
                            v9 = 36;
                            goto LABEL_232;
                          }
                        }
                      }
                      else
                      {
                        v68 = CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                          CallStackTracing::s_wpInstance = v69;
                          if ( v69
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(
                                 v69,
                                 2032) )
                          {
                            v68 = CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v68 = (CallStackTracing *)&qword_1800EB130;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                          }
                        }
                        if ( *((_BYTE *)v68 + 8) )
                        {
                          v70 = CallStackTracing::GetThreadRelativeContext(v68);
                          if ( *((_DWORD *)v70 + 499) != Instance )
                            CallStackContext::TraceFailure(v70, "CDShowSBEWrapper::CreateGraph", 267, Instance);
                        }
                        if ( g_wppLevels )
                        {
                          v9 = 35;
                          goto LABEL_232;
                        }
                      }
                    }
                    else
                    {
                      if ( (unsigned __int8)byte_1800EACCB >= 8u )
                        WPP_SF_q(
                          *((_QWORD *)WPP_GLOBAL_Control + 17),
                          33,
                          WPP_37ff27b5f7033090a0d8eec054f7c30c_Traceguids,
                          this);
                      v65 = CallStackTracing::s_wpInstance;
                      Instance = -1072873832;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                        CallStackTracing::s_wpInstance = v66;
                        if ( v66
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(
                               v66,
                               2032) )
                        {
                          v65 = CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v65 = (CallStackTracing *)&qword_1800EB130;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                        }
                      }
                      if ( *((_BYTE *)v65 + 8) )
                      {
                        v67 = CallStackTracing::GetThreadRelativeContext(v65);
                        if ( *((_DWORD *)v67 + 499) != -1072873832 )
                          CallStackContext::TraceFailure(v67, "CDShowSBEWrapper::CreateGraph", 264, -1072873832);
                      }
                      if ( g_wppLevels )
                      {
                        v9 = 34;
                        goto LABEL_232;
                      }
                    }
                  }
                  else
                  {
                    v62 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                      CallStackTracing::s_wpInstance = v63;
                      if ( v63
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(
                             v63,
                             2032) )
                      {
                        v62 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v62 = (CallStackTracing *)&qword_1800EB130;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                      }
                    }
                    if ( *((_BYTE *)v62 + 8) )
                    {
                      v64 = CallStackTracing::GetThreadRelativeContext(v62);
                      if ( *((_DWORD *)v64 + 499) != Instance )
                        CallStackContext::TraceFailure(v64, "CDShowSBEWrapper::CreateGraph", 254, Instance);
                    }
                    if ( g_wppLevels )
                    {
                      v9 = 32;
                      goto LABEL_232;
                    }
                  }
                }
                else
                {
                  v59 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                    CallStackTracing::s_wpInstance = v60;
                    if ( v60
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
                    {
                      v59 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v59 = (CallStackTracing *)&qword_1800EB130;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                    }
                  }
                  if ( *((_BYTE *)v59 + 8) )
                  {
                    v61 = CallStackTracing::GetThreadRelativeContext(v59);
                    if ( *((_DWORD *)v61 + 499) != Instance )
                      CallStackContext::TraceFailure(v61, "CDShowSBEWrapper::CreateGraph", 252, Instance);
                  }
                  if ( g_wppLevels )
                  {
                    v9 = 31;
                    goto LABEL_232;
                  }
                }
                goto LABEL_233;
              }
              v30 = CallStackTracing::s_wpInstance;
              Instance = -2147467261;
              if ( !CallStackTracing::s_wpInstance )
              {
                v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v31;
                if ( v31
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                {
                  v30 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v30 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              if ( *((_BYTE *)v30 + 8) )
              {
                v32 = CallStackTracing::GetThreadRelativeContext(v30);
                if ( *((_DWORD *)v32 + 499) != -2147467261 )
                  CallStackContext::TraceFailure(v32, "CDShowSBEWrapper::CreateGraph", 214, -2147467261);
              }
              if ( !g_wppLevels )
                goto LABEL_233;
              v26 = 23;
            }
            else
            {
              v23 = CallStackTracing::s_wpInstance;
              Instance = -2147467261;
              if ( !CallStackTracing::s_wpInstance )
              {
                v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v24;
                if ( v24
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
                {
                  v23 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v23 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              if ( *((_BYTE *)v23 + 8) )
              {
                v25 = CallStackTracing::GetThreadRelativeContext(v23);
                if ( *((_DWORD *)v25 + 499) != -2147467261 )
                  CallStackContext::TraceFailure(v25, "CDShowSBEWrapper::CreateGraph", 209, -2147467261);
              }
              if ( !g_wppLevels )
                goto LABEL_233;
              v26 = 21;
            }
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v26,
              WPP_37ff27b5f7033090a0d8eec054f7c30c_Traceguids,
              this,
              -2147467261);
            goto LABEL_233;
          }
          v20 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext(v20);
            if ( *((_DWORD *)v22 + 499) != Instance )
              CallStackContext::TraceFailure(v22, "CDShowSBEWrapper::CreateGraph", 207, Instance);
          }
          if ( g_wppLevels )
          {
            v9 = 20;
            goto LABEL_232;
          }
        }
        else
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
              CallStackContext::TraceFailure(v19, "CDShowSBEWrapper::CreateGraph", 206, Instance);
          }
          if ( g_wppLevels )
          {
            v9 = 19;
            goto LABEL_232;
          }
        }
      }
      else
      {
        v13 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v15 = CallStackTracing::GetThreadRelativeContext(v13);
          if ( *((_DWORD *)v15 + 499) != Instance )
            CallStackContext::TraceFailure(v15, "CDShowSBEWrapper::CreateGraph", 201, Instance);
        }
        if ( g_wppLevels )
        {
          v9 = 18;
          goto LABEL_232;
        }
      }
    }
    else
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext(v10);
        if ( *((_DWORD *)v12 + 499) != Instance )
          CallStackContext::TraceFailure(v12, "CDShowSBEWrapper::CreateGraph", 196, Instance);
      }
      if ( g_wppLevels )
      {
        v9 = 17;
        goto LABEL_232;
      }
    }
  }
  else
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v6);
      if ( *((_DWORD *)v8 + 499) != Instance )
        CallStackContext::TraceFailure(v8, "CDShowSBEWrapper::CreateGraph", 195, Instance);
    }
    if ( g_wppLevels )
    {
      v9 = 16;
LABEL_232:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        WPP_37ff27b5f7033090a0d8eec054f7c30c_Traceguids,
        this,
        Instance);
    }
  }
LABEL_233:
  CoTaskMemFree(pv);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v79);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppv);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v80);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v76);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v75);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180097eb0  mov     [rsp-28h+arg_8], rbx
0x180097eb5  mov     [rsp-28h+arg_10], rsi
0x180097eba  push    rbp
0x180097ebb  push    rdi
0x180097ebc  push    r12
0x180097ebe  push    r14
0x180097ec0  push    r15
0x180097ec2  mov     rbp, rsp
0x180097ec5  sub     rsp, 80h
0x180097ecc  mov     rax, cs:__security_cookie
0x180097ed3  xor     rax, rsp
0x180097ed6  mov     [rbp+var_10], rax
0x180097eda  mov     rsi, rcx
0x180097edd  lea     r12, aCdshowsbewrapp_1; "CDShowSBEWrapper::CreateGraph"
0x180097ee4  mov     rdx, r12; char *
0x180097ee7  lea     rcx, [rbp+var_50]; this
0x180097eeb  mov     r8d, 0B7h; int
0x180097ef1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180097ef6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180097efd  xor     r14d, r14d
0x180097f00  cmp     [rcx+8], r14b
0x180097f04  jz      short loc_180097F5A
0x180097f06  cmp     [rsi+1E0h], r14
0x180097f0d  jz      short loc_180097F5A
0x180097f0f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180097f14  mov     rcx, [rsi+1E0h]
0x180097f1b  mov     rdi, rax
0x180097f1e  mov     rdx, [rcx]
0x180097f21  mov     rax, [rdx+128h]
0x180097f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097f2d  mov     rcx, [rsi+1E0h]
0x180097f34  mov     ebx, eax
0x180097f36  mov     rdx, [rcx]
0x180097f39  mov     rax, [rdx+118h]
0x180097f40  lea     rdx, [rbp+var_20]
0x180097f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097f49  movups  xmm0, xmmword ptr [rax]
0x180097f4c  mov     [rdi+7E0h], ebx
0x180097f52  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180097f5a  lea     rax, [rbp+var_40]
0x180097f5e  mov     [rbp+var_48], r14
0x180097f62  mov     r15d, 1
0x180097f68  mov     [rbp+var_28], r14
0x180097f6c  mov     r8d, r15d; dwClsContext
0x180097f6f  mov     [rbp+pv], r14
0x180097f73  lea     r9, _GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770; riid
0x180097f7a  mov     [rbp+var_40], r14
0x180097f7e  xor     edx, edx; pUnkOuter
0x180097f80  mov     [rbp+var_30], r14
0x180097f84  lea     rcx, CLSID_FilterGraph; rclsid
0x180097f8b  mov     [rsp+80h+ppv], rax; ppv
0x180097f90  call    cs:__imp_CoCreateInstance
0x180097f97  nop     dword ptr [rax+rax+00h]
0x180097f9c  mov     ebx, eax
0x180097f9e  test    eax, eax
0x180097fa0  jns     loc_180098037
0x180097fa6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097fad  test    rcx, rcx
0x180097fb0  jnz     short loc_180097FF9
0x180097fb2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180097fb9  nop     dword ptr [rax+rax+00h]
0x180097fbe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180097fc5  mov     rcx, rax
0x180097fc8  test    rax, rax
0x180097fcb  jz      short loc_180097FEB
0x180097fcd  mov     rax, [rax]
0x180097fd0  mov     edx, 7F0h
0x180097fd5  mov     rax, [rax+8]
0x180097fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097fde  test    eax, eax
0x180097fe0  jz      short loc_180097FEB
0x180097fe2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180097fe9  jmp     short loc_180097FF9
0x180097feb  lea     rcx, qword_1800EB130; this
0x180097ff2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180097ff9  cmp     [rcx+8], r14b
0x180097ffd  jz      short loc_180098020
0x180097fff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098004  cmp     [rax+7CCh], ebx
0x18009800a  jz      short loc_180098020
0x18009800c  mov     r9d, ebx; int
0x18009800f  mov     r8d, 0C3h; int
0x180098015  mov     rdx, r12; char *
0x180098018  mov     rcx, rax; this
0x18009801b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098020  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180098027  jb      loc_180098DAC
0x18009802d  mov     edx, 10h
0x180098032  jmp     loc_180098D8E
0x180098037  mov     r8, [rbp+var_40]; struct IUnknown *
0x18009803b  lea     rcx, [rsi+30h]; this
0x18009803f  lea     rdx, _GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770; struct _GUID *
0x180098046  call    ?Set@CGITPtr@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z; CGITPtr::Set(_GUID const &,IUnknown *)
0x18009804b  mov     ebx, eax
0x18009804d  test    eax, eax
0x18009804f  jns     loc_1800980E6
0x180098055  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009805c  test    rcx, rcx
0x18009805f  jnz     short loc_1800980A8
0x180098061  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098068  nop     dword ptr [rax+rax+00h]
0x18009806d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098074  mov     rcx, rax
0x180098077  test    rax, rax
0x18009807a  jz      short loc_18009809A
0x18009807c  mov     rax, [rax]
0x18009807f  mov     edx, 7F0h
0x180098084  mov     rax, [rax+8]
0x180098088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009808d  test    eax, eax
0x18009808f  jz      short loc_18009809A
0x180098091  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098098  jmp     short loc_1800980A8
0x18009809a  lea     rcx, qword_1800EB130; this
0x1800980a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800980a8  cmp     [rcx+8], r14b
0x1800980ac  jz      short loc_1800980CF
0x1800980ae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800980b3  cmp     [rax+7CCh], ebx
0x1800980b9  jz      short loc_1800980CF
0x1800980bb  mov     r9d, ebx; int
0x1800980be  mov     r8d, 0C4h; int
0x1800980c4  mov     rdx, r12; char *
0x1800980c7  mov     rcx, rax; this
0x1800980ca  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800980cf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800980d6  jb      loc_180098DAC
0x1800980dc  mov     edx, 11h
0x1800980e1  jmp     loc_180098D8E
0x1800980e6  mov     rcx, rsi; this
0x1800980e9  call    ?SetupThreadpoolWait@CDShowWrapper@@IEAAJXZ; CDShowWrapper::SetupThreadpoolWait(void)
0x1800980ee  mov     ebx, eax
0x1800980f0  test    eax, eax
0x1800980f2  jns     loc_180098189
0x1800980f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800980ff  test    rcx, rcx
0x180098102  jnz     short loc_18009814B
0x180098104  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009810b  nop     dword ptr [rax+rax+00h]
0x180098110  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098117  mov     rcx, rax
0x18009811a  test    rax, rax
0x18009811d  jz      short loc_18009813D
0x18009811f  mov     rax, [rax]
0x180098122  mov     edx, 7F0h
0x180098127  mov     rax, [rax+8]
0x18009812b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098130  test    eax, eax
0x180098132  jz      short loc_18009813D
0x180098134  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009813b  jmp     short loc_18009814B
0x18009813d  lea     rcx, qword_1800EB130; this
0x180098144  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009814b  cmp     [rcx+8], r14b
0x18009814f  jz      short loc_180098172
0x180098151  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098156  cmp     [rax+7CCh], ebx
0x18009815c  jz      short loc_180098172
0x18009815e  mov     r9d, ebx; int
0x180098161  mov     r8d, 0C9h; int
0x180098167  mov     rdx, r12; char *
0x18009816a  mov     rcx, rax; this
0x18009816d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098172  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180098179  jb      loc_180098DAC
0x18009817f  mov     edx, 12h
0x180098184  jmp     loc_180098D8E
0x180098189  lea     rdi, [rsi+40h]
0x18009818d  mov     r8d, r15d; dwClsContext
0x180098190  lea     r9, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770; riid
0x180098197  mov     [rsp+80h+ppv], rdi; ppv
0x18009819c  xor     edx, edx; pUnkOuter
0x18009819e  lea     rcx, CLSID_StreamBufferSource; rclsid
0x1800981a5  call    cs:__imp_CoCreateInstance
0x1800981ac  nop     dword ptr [rax+rax+00h]
0x1800981b1  mov     ebx, eax
0x1800981b3  test    eax, eax
0x1800981b5  jns     loc_18009824C
0x1800981bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800981c2  test    rcx, rcx
0x1800981c5  jnz     short loc_18009820E
0x1800981c7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800981ce  nop     dword ptr [rax+rax+00h]
0x1800981d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800981da  mov     rcx, rax
0x1800981dd  test    rax, rax
0x1800981e0  jz      short loc_180098200
0x1800981e2  mov     rax, [rax]
0x1800981e5  mov     edx, 7F0h
0x1800981ea  mov     rax, [rax+8]
0x1800981ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800981f3  test    eax, eax
0x1800981f5  jz      short loc_180098200
0x1800981f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800981fe  jmp     short loc_18009820E
0x180098200  lea     rcx, qword_1800EB130; this
0x180098207  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009820e  cmp     [rcx+8], r14b
0x180098212  jz      short loc_180098235
0x180098214  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098219  cmp     [rax+7CCh], ebx
0x18009821f  jz      short loc_180098235
0x180098221  mov     r9d, ebx; int
0x180098224  mov     r8d, 0CEh; int
0x18009822a  mov     rdx, r12; char *
0x18009822d  mov     rcx, rax; this
0x180098230  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098235  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18009823c  jb      loc_180098DAC
0x180098242  mov     edx, 13h
0x180098247  jmp     loc_180098D8E
0x18009824c  mov     rcx, [rdi]
0x18009824f  lea     r8, [rbp+var_48]
0x180098253  lea     rdx, _GUID_c6130043_9342_4cb9_8697_222ee967ced6
0x18009825a  mov     rax, [rcx]
0x18009825d  mov     rax, [rax]
0x180098260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098265  mov     ebx, eax
0x180098267  test    eax, eax
0x180098269  jns     loc_180098300
0x18009826f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098276  test    rcx, rcx
0x180098279  jnz     short loc_1800982C2
0x18009827b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098282  nop     dword ptr [rax+rax+00h]
0x180098287  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009828e  mov     rcx, rax
0x180098291  test    rax, rax
0x180098294  jz      short loc_1800982B4
0x180098296  mov     rax, [rax]
0x180098299  mov     edx, 7F0h
0x18009829e  mov     rax, [rax+8]
0x1800982a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800982a7  test    eax, eax
0x1800982a9  jz      short loc_1800982B4
0x1800982ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800982b2  jmp     short loc_1800982C2
0x1800982b4  lea     rcx, qword_1800EB130; this
0x1800982bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800982c2  cmp     [rcx+8], r14b
0x1800982c6  jz      short loc_1800982E9
0x1800982c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800982cd  cmp     [rax+7CCh], ebx
0x1800982d3  jz      short loc_1800982E9
0x1800982d5  mov     r9d, ebx; int
0x1800982d8  mov     r8d, 0CFh; int
0x1800982de  mov     rdx, r12; char *
0x1800982e1  mov     rcx, rax; this
0x1800982e4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800982e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800982f0  jb      loc_180098DAC
0x1800982f6  mov     edx, 14h
0x1800982fb  jmp     loc_180098D8E
0x180098300  mov     rcx, [rbp+var_48]
0x180098304  test    rcx, rcx
0x180098307  jnz     loc_1800983A9
0x18009830d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098314  mov     edi, 80004003h
0x180098319  mov     ebx, edi
0x18009831b  test    rcx, rcx
0x18009831e  jnz     short loc_180098367
0x180098320  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098327  nop     dword ptr [rax+rax+00h]
0x18009832c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098333  mov     rcx, rax
0x180098336  test    rax, rax
0x180098339  jz      short loc_180098359
0x18009833b  mov     rax, [rax]
0x18009833e  mov     edx, 7F0h
0x180098343  mov     rax, [rax+8]
0x180098347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009834c  test    eax, eax
0x18009834e  jz      short loc_180098359
0x180098350  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098357  jmp     short loc_180098367
0x180098359  lea     rcx, qword_1800EB130; this
0x180098360  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098367  cmp     [rcx+8], r14b
0x18009836b  jz      short loc_18009838E
0x18009836d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098372  cmp     [rax+7CCh], edi
0x180098378  jz      short loc_18009838E
0x18009837a  mov     r9d, edi; int
0x18009837d  mov     r8d, 0D1h; int
0x180098383  mov     rdx, r12; char *
0x180098386  mov     rcx, rax; this
0x180098389  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009838e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180098395  jb      loc_180098DAC
0x18009839b  mov     edx, 15h
0x1800983a0  mov     dword ptr [rsp+80h+ppv], edi
0x1800983a4  jmp     loc_180098D92
0x1800983a9  mov     rax, [rcx]
0x1800983ac  lea     r8, [rbp+var_28]
0x1800983b0  lea     rdx, _GUID_4c131ffc_8c18_4ac3_b33a_494e3115a1a6
0x1800983b7  mov     rax, [rax]
0x1800983ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800983bf  mov     ebx, eax
0x1800983c1  test    eax, eax
0x1800983c3  jns     loc_18009845A
  ... truncated ...
```
