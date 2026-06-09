# CTranscodeDestination::CheckIfNeedInsertH264Remuxer(IMFStreamDescriptor *,IMFActivate * *)

- ea: `0x1800411f0`
- end: `0x180041d8d`
- name: `?CheckIfNeedInsertH264Remuxer@CTranscodeDestination@@UEAAJPEAUIMFStreamDescriptor@@PEAPEAUIMFActivate@@@Z`
- size: `2973`
- prototype: `int(CTranscodeDestination *__hidden this, struct IMFStreamDescriptor *, struct IMFActivate **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x1800411f0`
- `0x18004f410`
- `0x180053b88`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004127d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041318`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800413c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041473`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004151c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800415b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041665`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041715`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041801`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800418b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041989`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041a27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041adc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041b91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041c23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041cb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004127d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041318`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800413c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041473`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004151c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800415b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041665`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041715`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041801`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800418b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041989`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041a27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041adc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041b91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041c23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041cb5`
- `MFPlat!MFCreateTransformActivate` at `0x180041a0b`
- `MFPlat!MFCreateTransformActivate` at `0x180041a0b`

## pseudocode

```c
__int64 __fastcall CTranscodeDestination::CheckIfNeedInsertH264Remuxer(
        CTranscodeDestination *this,
        struct IMFStreamDescriptor *a2,
        struct IMFActivate **a3)
{
  __int64 v6; // rdx
  __int64 *v7; // rcx
  int v8; // edi
  HRESULT v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 v54; // rdx
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v73[8]; // [rsp+30h] [rbp-49h] BYREF
  struct IMFMediaType *v74; // [rsp+38h] [rbp-41h] BYREF
  struct IMFAttributes *v75; // [rsp+40h] [rbp-39h] BYREF
  __int64 v76; // [rsp+48h] [rbp-31h] BYREF
  GUID Buf1; // [rsp+50h] [rbp-29h] BYREF
  GUID v78; // [rsp+60h] [rbp-19h] BYREF
  GUID v79; // [rsp+70h] [rbp-9h] BYREF
  GUID v80; // [rsp+80h] [rbp+7h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v73,
    "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
    204);
  v76 = 0;
  v75 = 0;
  v74 = 0;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  v80 = GUID_00000000_0000_0000_0000_000000000000;
  v78 = GUID_00000000_0000_0000_0000_000000000000;
  v79 = GUID_00000000_0000_0000_0000_000000000000;
  if ( a3 )
  {
    if ( a2 )
    {
      *a3 = 0;
      v9 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))a2->lpVtbl->GetMediaTypeHandler)(a2, &v76);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, struct IMFMediaType **))(*(_QWORD *)v76 + 56LL))(v76, &v74);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD, struct IMFAttributes **))(**((_QWORD **)this + 1) + 48LL))(
                 *((_QWORD *)this + 1),
                 &v75);
          if ( v9 >= 0 )
          {
            if ( v75 )
            {
              v9 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, GUID *))v75->lpVtbl->GetGUID)(
                     v75,
                     &MF_MT_MAJOR_TYPE,
                     &v78);
              if ( v9 >= 0 )
              {
                v9 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))v74->lpVtbl->GetGUID)(
                       v74,
                       &MF_MT_MAJOR_TYPE,
                       &Buf1);
                if ( v9 >= 0 )
                {
                  if ( memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) || memcmp_0(&v78, &MFMediaType_Video, 0x10u) )
                  {
                    v69 = (__int64 *)CallStackTracing::s_wpInstance;
                    v8 = -2147467259;
                    v9 = -2147467259;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
                      CallStackTracing::s_wpInstance = v70;
                      if ( v70
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(
                             v70,
                             2032) )
                      {
                        v69 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v69 = &qword_180069A90;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                      }
                    }
                    if ( *((_BYTE *)v69 + 8) )
                    {
                      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
                      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467259 )
                        CallStackContext::TraceFailure(
                          ThreadRelativeContext,
                          "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
                          233,
                          -2147467259);
                    }
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v12 = 32;
                      goto LABEL_180;
                    }
                    goto LABEL_181;
                  }
                  v9 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, GUID *))v75->lpVtbl->GetGUID)(
                         v75,
                         &MF_MT_SUBTYPE,
                         &v79);
                  if ( v9 >= 0 )
                  {
                    v9 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))v74->lpVtbl->GetGUID)(
                           v74,
                           &MF_MT_SUBTYPE,
                           &v80);
                    if ( v9 >= 0 )
                    {
                      if ( memcmp_0(&v79, &MEDIASUBTYPE_H264, 0x10u) || memcmp_0(&v80, &MFVideoFormat_H264_ES, 0x10u) )
                      {
                        v66 = (__int64 *)CallStackTracing::s_wpInstance;
                        v8 = -2147467259;
                        v9 = -2147467259;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
                          CallStackTracing::s_wpInstance = v67;
                          if ( v67
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(
                                 v67,
                                 2032) )
                          {
                            v66 = (__int64 *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v66 = &qword_180069A90;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                          }
                        }
                        if ( *((_BYTE *)v66 + 8) )
                        {
                          v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
                          if ( *((_DWORD *)v68 + 499) != -2147467259 )
                            CallStackContext::TraceFailure(
                              v68,
                              "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
                              240,
                              -2147467259);
                        }
                        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        {
                          v12 = 35;
                          goto LABEL_180;
                        }
                        goto LABEL_181;
                      }
                      v9 = MFH264CheckParameters(v74, v75);
                      if ( v9 >= 0 )
                      {
                        v9 = MFCreateTransformActivate(a3);
                        if ( v9 >= 0 )
                        {
                          v9 = ((__int64 (__fastcall *)(_QWORD, const GUID *, GUID *))(*a3)->lpVtbl->SetGUID)(
                                 *a3,
                                 &MFT_TRANSFORM_CLSID_Attribute,
                                 &CLSID_CMSH264RemuxMFT);
                          if ( v9 >= 0 )
                          {
                            v9 = ((__int64 (__fastcall *)(_QWORD, const GUID *, const GUID *))(*a3)->lpVtbl->SetGUID)(
                                   *a3,
                                   &MF_TRANSFORM_CATEGORY_Attribute,
                                   &MFT_CATEGORY_OTHER);
                            if ( v9 >= 0 )
                              goto LABEL_181;
                            v63 = (__int64 *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62);
                              CallStackTracing::s_wpInstance = v64;
                              if ( v64
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(
                                     v64,
                                     2032) )
                              {
                                v63 = (__int64 *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v63 = &qword_180069A90;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                              }
                            }
                            if ( *((_BYTE *)v63 + 8) )
                            {
                              v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
                              if ( *((_DWORD *)v65 + 499) != v9 )
                                CallStackContext::TraceFailure(
                                  v65,
                                  "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
                                  253,
                                  v9);
                            }
                            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                              goto LABEL_181;
                            v20 = 39;
                          }
                          else
                          {
                            v59 = (__int64 *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
                              CallStackTracing::s_wpInstance = v60;
                              if ( v60
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(
                                     v60,
                                     2032) )
                              {
                                v59 = (__int64 *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v59 = &qword_180069A90;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                              }
                            }
                            if ( *((_BYTE *)v59 + 8) )
                            {
                              v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
                              if ( *((_DWORD *)v61 + 499) != v9 )
                                CallStackContext::TraceFailure(
                                  v61,
                                  "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
                                  252,
                                  v9);
                            }
                            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                              goto LABEL_181;
                            v20 = 38;
                          }
                        }
                        else
                        {
                          v55 = (__int64 *)CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
                            CallStackTracing::s_wpInstance = v56;
                            if ( v56
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(
                                   v56,
                                   2032) )
                            {
                              v55 = (__int64 *)CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v55 = &qword_180069A90;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                            }
                          }
                          if ( *((_BYTE *)v55 + 8) )
                          {
                            v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
                            if ( *((_DWORD *)v57 + 499) != v9 )
                              CallStackContext::TraceFailure(
                                v57,
                                "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
                                251,
                                v9);
                          }
                          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                            goto LABEL_181;
                          v20 = 37;
                        }
                      }
                      else
                      {
                        v51 = (__int64 *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
                          CallStackTracing::s_wpInstance = v52;
                          if ( v52
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(
                                 v52,
                                 2032) )
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
                          if ( *((_DWORD *)v53 + 499) != v9 )
                            CallStackContext::TraceFailure(
                              v53,
                              "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
                              246,
                              v9);
                        }
                        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                          goto LABEL_181;
                        v20 = 36;
                      }
                    }
                    else
                    {
                      v46 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
                        CallStackTracing::s_wpInstance = v47;
                        if ( v47
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(
                               v47,
                               2032) )
                        {
                          v46 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v46 = &qword_180069A90;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                        }
                      }
                      if ( *((_BYTE *)v46 + 8) )
                      {
                        v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
                        if ( *((_DWORD *)v48 + 499) != v9 )
                          CallStackContext::TraceFailure(
                            v48,
                            "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
                            236,
                            v9);
                      }
                      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        goto LABEL_181;
                      v20 = 34;
                    }
                  }
                  else
                  {
                    v42 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
                      CallStackTracing::s_wpInstance = v43;
                      if ( v43
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(
                             v43,
                             2032) )
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
                      if ( *((_DWORD *)v44 + 499) != v9 )
                        CallStackContext::TraceFailure(
                          v44,
                          "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
                          235,
                          v9);
                    }
                    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      goto LABEL_181;
                    v20 = 33;
                  }
                }
                else
                {
                  v37 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
                    CallStackTracing::s_wpInstance = v38;
                    if ( v38
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                    {
                      v37 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v37 = &qword_180069A90;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                    }
                  }
                  if ( *((_BYTE *)v37 + 8) )
                  {
                    v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                    if ( *((_DWORD *)v39 + 499) != v9 )
                      CallStackContext::TraceFailure(
                        v39,
                        "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
                        229,
                        v9);
                  }
                  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    goto LABEL_181;
                  v20 = 31;
                }
              }
              else
              {
                v33 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
                  CallStackTracing::s_wpInstance = v34;
                  if ( v34
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
                  {
                    v33 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v33 = &qword_180069A90;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)v33 + 8) )
                {
                  v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                  if ( *((_DWORD *)v35 + 499) != v9 )
                    CallStackContext::TraceFailure(v35, "CTranscodeDestination::CheckIfNeedInsertH264Remuxer", 228, v9);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_181;
                v20 = 30;
              }
            }
            else
            {
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
              v9 = -2147418113;
              if ( !CallStackTracing::s_wpInstance )
              {
                v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
                CallStackTracing::s_wpInstance = v30;
                if ( v30
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
                {
                  v29 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v29 = &qword_180069A90;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)v29 + 8) )
              {
                v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
                if ( *((_DWORD *)v31 + 499) != -2147418113 )
                  CallStackContext::TraceFailure(
                    v31,
                    "CTranscodeDestination::CheckIfNeedInsertH264Remuxer",
                    223,
                    -2147418113);
              }
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_181;
              v20 = 29;
            }
          }
          else
          {
            v26 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
              CallStackTracing::s_wpInstance = v27;
              if ( v27
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
              {
                v26 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v26 + 8) )
            {
              v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
              if ( *((_DWORD *)v28 + 499) != v9 )
                CallStackContext::TraceFailure(v28, "CTranscodeDestination::CheckIfNeedInsertH264Remuxer", 222, v9);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_181;
            v20 = 28;
          }
        }
        else
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != v9 )
              CallStackContext::TraceFailure(v24, "CTranscodeDestination::CheckIfNeedInsertH264Remuxer", 221, v9);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_181;
          v20 = 27;
        }
      }
      else
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)v19 + 499) != v9 )
            CallStackContext::TraceFailure(v19, "CTranscodeDestination::CheckIfNeedInsertH264Remuxer", 220, v9);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_181;
        v20 = 26;
      }
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids, this, v9);
      goto LABEL_181;
    }
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147467261;
    v9 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v15, "CTranscodeDestination::CheckIfNeedInsertH264Remuxer", 216, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 25;
      goto LABEL_180;
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147467261;
    v9 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v11 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v11, "CTranscodeDestination::CheckIfNeedInsertH264Remuxer", 215, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 24;
LABEL_180:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids, this, v8);
    }
  }
LABEL_181:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v74);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v75);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v76);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v73);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800411f0  push    rbp
0x1800411f2  push    rbx
0x1800411f3  push    rsi
0x1800411f4  push    rdi
0x1800411f5  push    r12
0x1800411f7  push    r14
0x1800411f9  push    r15
0x1800411fb  lea     rbp, [rsp-27h]
0x180041200  sub     rsp, 0A0h
0x180041207  mov     rax, cs:__security_cookie
0x18004120e  xor     rax, rsp
0x180041211  mov     [rbp+57h+var_40], rax
0x180041215  mov     rdi, r8
0x180041218  lea     r15, aCtranscodedest_4; "CTranscodeDestination::CheckIfNeedInser"...
0x18004121f  mov     rbx, rdx
0x180041222  mov     rsi, rcx
0x180041225  mov     rdx, r15; char *
0x180041228  lea     rcx, [rbp+57h+var_A0]; this
0x18004122c  mov     r8d, 0CCh; int
0x180041232  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180041237  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004123e  xor     r14d, r14d
0x180041241  mov     [rbp+57h+var_88], r14
0x180041245  mov     [rbp+57h+var_90], r14
0x180041249  mov     [rbp+57h+var_98], r14
0x18004124d  movdqu  [rbp+57h+Buf1], xmm0
0x180041252  movdqu  [rbp+57h+var_50], xmm0
0x180041257  movdqu  [rbp+57h+var_70], xmm0
0x18004125c  movdqu  [rbp+57h+var_60], xmm0
0x180041261  test    rdi, rdi
0x180041264  jnz     loc_1800412FC
0x18004126a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041271  mov     edi, 80004003h
0x180041276  mov     ebx, edi
0x180041278  test    rcx, rcx
0x18004127b  jnz     short loc_1800412BE
0x18004127d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041283  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004128a  mov     rcx, rax
0x18004128d  test    rax, rax
0x180041290  jz      short loc_1800412B0
0x180041292  mov     rax, [rax]
0x180041295  mov     edx, 7F0h
0x18004129a  mov     rax, [rax+8]
0x18004129e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800412a3  test    eax, eax
0x1800412a5  jz      short loc_1800412B0
0x1800412a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800412ae  jmp     short loc_1800412BE
0x1800412b0  lea     rcx, qword_180069A90; this
0x1800412b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800412be  cmp     [rcx+8], r14b
0x1800412c2  jz      short loc_1800412E5
0x1800412c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800412c9  cmp     [rax+7CCh], edi
0x1800412cf  jz      short loc_1800412E5
0x1800412d1  mov     r9d, edi; int
0x1800412d4  mov     r8d, 0D7h; int
0x1800412da  mov     rdx, r15; char *
0x1800412dd  mov     rcx, rax; this
0x1800412e0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800412e5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800412ea  cmp     al, 1
0x1800412ec  jb      loc_180041D49
0x1800412f2  mov     edx, 18h
0x1800412f7  jmp     loc_180041D2B
0x1800412fc  test    rbx, rbx
0x1800412ff  jnz     loc_180041397
0x180041305  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004130c  mov     edi, 80004003h
0x180041311  mov     ebx, edi
0x180041313  test    rcx, rcx
0x180041316  jnz     short loc_180041359
0x180041318  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004131e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041325  mov     rcx, rax
0x180041328  test    rax, rax
0x18004132b  jz      short loc_18004134B
0x18004132d  mov     rax, [rax]
0x180041330  mov     edx, 7F0h
0x180041335  mov     rax, [rax+8]
0x180041339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004133e  test    eax, eax
0x180041340  jz      short loc_18004134B
0x180041342  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041349  jmp     short loc_180041359
0x18004134b  lea     rcx, qword_180069A90; this
0x180041352  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041359  cmp     [rcx+8], r14b
0x18004135d  jz      short loc_180041380
0x18004135f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041364  cmp     [rax+7CCh], edi
0x18004136a  jz      short loc_180041380
0x18004136c  mov     r9d, edi; int
0x18004136f  mov     r8d, 0D8h; int
0x180041375  mov     rdx, r15; char *
0x180041378  mov     rcx, rax; this
0x18004137b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041380  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041385  cmp     al, 1
0x180041387  jb      loc_180041D49
0x18004138d  mov     edx, 19h
0x180041392  jmp     loc_180041D2B
0x180041397  mov     [rdi], r14
0x18004139a  lea     rdx, [rbp+57h+var_88]
0x18004139e  mov     rax, [rbx]
0x1800413a1  mov     rcx, rbx
0x1800413a4  mov     rax, [rax+110h]
0x1800413ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413b0  mov     ebx, eax
0x1800413b2  test    eax, eax
0x1800413b4  jns     loc_180041449
0x1800413ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800413c1  test    rcx, rcx
0x1800413c4  jnz     short loc_180041407
0x1800413c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800413cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800413d3  mov     rcx, rax
0x1800413d6  test    rax, rax
0x1800413d9  jz      short loc_1800413F9
0x1800413db  mov     rax, [rax]
0x1800413de  mov     edx, 7F0h
0x1800413e3  mov     rax, [rax+8]
0x1800413e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413ec  test    eax, eax
0x1800413ee  jz      short loc_1800413F9
0x1800413f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800413f7  jmp     short loc_180041407
0x1800413f9  lea     rcx, qword_180069A90; this
0x180041400  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041407  cmp     [rcx+8], r14b
0x18004140b  jz      short loc_18004142E
0x18004140d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041412  cmp     [rax+7CCh], ebx
0x180041418  jz      short loc_18004142E
0x18004141a  mov     r9d, ebx; int
0x18004141d  mov     r8d, 0DCh; int
0x180041423  mov     rdx, r15; char *
0x180041426  mov     rcx, rax; this
0x180041429  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004142e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041433  cmp     al, 1
0x180041435  jb      loc_180041D49
0x18004143b  mov     edx, 1Ah
0x180041440  mov     [rsp+0D0h+var_B0], ebx
0x180041444  jmp     loc_180041D2F
0x180041449  mov     rcx, [rbp+57h+var_88]
0x18004144d  lea     rdx, [rbp+57h+var_98]
0x180041451  mov     rax, [rcx]
0x180041454  mov     rax, [rax+38h]
0x180041458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004145d  mov     ebx, eax
0x18004145f  test    eax, eax
0x180041461  jns     loc_1800414F2
0x180041467  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004146e  test    rcx, rcx
0x180041471  jnz     short loc_1800414B4
0x180041473  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041479  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041480  mov     rcx, rax
0x180041483  test    rax, rax
0x180041486  jz      short loc_1800414A6
0x180041488  mov     rax, [rax]
0x18004148b  mov     edx, 7F0h
0x180041490  mov     rax, [rax+8]
0x180041494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041499  test    eax, eax
0x18004149b  jz      short loc_1800414A6
0x18004149d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800414a4  jmp     short loc_1800414B4
0x1800414a6  lea     rcx, qword_180069A90; this
0x1800414ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800414b4  cmp     [rcx+8], r14b
0x1800414b8  jz      short loc_1800414DB
0x1800414ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800414bf  cmp     [rax+7CCh], ebx
0x1800414c5  jz      short loc_1800414DB
0x1800414c7  mov     r9d, ebx; int
0x1800414ca  mov     r8d, 0DDh; int
0x1800414d0  mov     rdx, r15; char *
0x1800414d3  mov     rcx, rax; this
0x1800414d6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800414db  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800414e0  cmp     al, 1
0x1800414e2  jb      loc_180041D49
0x1800414e8  mov     edx, 1Bh
0x1800414ed  jmp     loc_180041440
0x1800414f2  mov     rcx, [rsi+8]
0x1800414f6  lea     rdx, [rbp+57h+var_90]
0x1800414fa  mov     rax, [rcx]
0x1800414fd  mov     rax, [rax+30h]
0x180041501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041506  mov     ebx, eax
0x180041508  test    eax, eax
0x18004150a  jns     loc_18004159B
0x180041510  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041517  test    rcx, rcx
0x18004151a  jnz     short loc_18004155D
0x18004151c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041522  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041529  mov     rcx, rax
0x18004152c  test    rax, rax
0x18004152f  jz      short loc_18004154F
0x180041531  mov     rax, [rax]
0x180041534  mov     edx, 7F0h
0x180041539  mov     rax, [rax+8]
0x18004153d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041542  test    eax, eax
0x180041544  jz      short loc_18004154F
0x180041546  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004154d  jmp     short loc_18004155D
0x18004154f  lea     rcx, qword_180069A90; this
0x180041556  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004155d  cmp     [rcx+8], r14b
0x180041561  jz      short loc_180041584
0x180041563  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041568  cmp     [rax+7CCh], ebx
0x18004156e  jz      short loc_180041584
0x180041570  mov     r9d, ebx; int
0x180041573  mov     r8d, 0DEh; int
0x180041579  mov     rdx, r15; char *
0x18004157c  mov     rcx, rax; this
0x18004157f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041584  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041589  cmp     al, 1
0x18004158b  jb      loc_180041D49
0x180041591  mov     edx, 1Ch
0x180041596  jmp     loc_180041440
0x18004159b  mov     rcx, [rbp+57h+var_90]
0x18004159f  test    rcx, rcx
0x1800415a2  jnz     loc_180041638
0x1800415a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800415af  mov     ebx, 8000FFFFh
0x1800415b4  test    rcx, rcx
0x1800415b7  jnz     short loc_1800415FA
0x1800415b9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800415bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800415c6  mov     rcx, rax
0x1800415c9  test    rax, rax
0x1800415cc  jz      short loc_1800415EC
0x1800415ce  mov     rax, [rax]
0x1800415d1  mov     edx, 7F0h
0x1800415d6  mov     rax, [rax+8]
0x1800415da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415df  test    eax, eax
0x1800415e1  jz      short loc_1800415EC
0x1800415e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800415ea  jmp     short loc_1800415FA
0x1800415ec  lea     rcx, qword_180069A90; this
0x1800415f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800415fa  cmp     [rcx+8], r14b
0x1800415fe  jz      short loc_180041621
0x180041600  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180041605  cmp     [rax+7CCh], ebx
0x18004160b  jz      short loc_180041621
0x18004160d  mov     r9d, ebx; int
0x180041610  mov     r8d, 0DFh; int
0x180041616  mov     rdx, r15; char *
0x180041619  mov     rcx, rax; this
0x18004161c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041621  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041626  cmp     al, 1
0x180041628  jb      loc_180041D49
0x18004162e  mov     edx, 1Dh
0x180041633  jmp     loc_180041440
0x180041638  mov     rax, [rcx]
0x18004163b  lea     r8, [rbp+57h+var_70]
0x18004163f  lea     rdx, MF_MT_MAJOR_TYPE
0x180041646  mov     rax, [rax+50h]
0x18004164a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004164f  mov     ebx, eax
0x180041651  test    eax, eax
0x180041653  jns     loc_1800416E4
0x180041659  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041660  test    rcx, rcx
0x180041663  jnz     short loc_1800416A6
0x180041665  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004166b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041672  mov     rcx, rax
0x180041675  test    rax, rax
0x180041678  jz      short loc_180041698
0x18004167a  mov     rax, [rax]
0x18004167d  mov     edx, 7F0h
0x180041682  mov     rax, [rax+8]
0x180041686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004168b  test    eax, eax
0x18004168d  jz      short loc_180041698
0x18004168f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041696  jmp     short loc_1800416A6
0x180041698  lea     rcx, qword_180069A90; this
0x18004169f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800416a6  cmp     [rcx+8], r14b
0x1800416aa  jz      short loc_1800416CD
0x1800416ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800416b1  cmp     [rax+7CCh], ebx
0x1800416b7  jz      short loc_1800416CD
0x1800416b9  mov     r9d, ebx; int
0x1800416bc  mov     r8d, 0E4h; int
0x1800416c2  mov     rdx, r15; char *
0x1800416c5  mov     rcx, rax; this
  ... truncated ...
```
