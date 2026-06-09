# CTranscodeDestination::CheckIfNeedInsertAudioRemuxer(IMFStreamDescriptor *,IMFActivate * *)

- ea: `0x1800405d0`
- end: `0x1800411e6`
- name: `?CheckIfNeedInsertAudioRemuxer@CTranscodeDestination@@UEAAJPEAUIMFStreamDescriptor@@PEAPEAUIMFActivate@@@Z`
- size: `3094`
- prototype: `__int64 __fastcall(CTranscodeDestination *__hidden this, struct IMFStreamDescriptor *, struct IMFActivate **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x1800405d0`
- `0x180042c2c`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004065d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800406f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800407a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040871`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004091a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800409b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040a63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040b13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040bff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040caf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040de2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040e80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040f35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040fea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004107c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004110e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004065d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800406f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800407a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040871`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004091a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800409b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040a63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040b13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040bff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040caf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040de2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040e80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040f35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180040fea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004107c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004110e`
- `MFPlat!MFCreateTransformActivate` at `0x180040e64`
- `MFPlat!MFCreateTransformActivate` at `0x180040e64`

## pseudocode

```c
__int64 __fastcall CTranscodeDestination::CheckIfNeedInsertAudioRemuxer(
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
  _BYTE v73[4]; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v74; // [rsp+34h] [rbp-45h] BYREF
  __int64 v75; // [rsp+38h] [rbp-41h] BYREF
  int v76; // [rsp+40h] [rbp-39h] BYREF
  __int64 v77; // [rsp+48h] [rbp-31h] BYREF
  __int64 v78; // [rsp+50h] [rbp-29h] BYREF
  GUID Buf1; // [rsp+58h] [rbp-21h] BYREF
  GUID v80; // [rsp+68h] [rbp-11h] BYREF
  GUID v81; // [rsp+78h] [rbp-1h] BYREF
  GUID v82; // [rsp+88h] [rbp+Fh] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v73,
    "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
    288);
  v78 = 0;
  v77 = 0;
  v75 = 0;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  v82 = GUID_00000000_0000_0000_0000_000000000000;
  v80 = GUID_00000000_0000_0000_0000_000000000000;
  v81 = GUID_00000000_0000_0000_0000_000000000000;
  if ( a3 )
  {
    if ( a2 )
    {
      *a3 = 0;
      v9 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))a2->lpVtbl->GetMediaTypeHandler)(a2, &v78);
      if ( v9 >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v78 + 56LL))(v78, &v75) >= 0
          || (v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v78 + 40LL))(v78, 0, &v75), v9 >= 0) )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 32LL))(
                 *((_QWORD *)this + 1),
                 &v77);
          if ( v9 >= 0 )
          {
            if ( v77 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)v77 + 80LL))(
                     v77,
                     &MF_MT_MAJOR_TYPE,
                     &v80);
              if ( v9 >= 0 )
              {
                v9 = (*(__int64 (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)v75 + 80LL))(
                       v75,
                       &MF_MT_MAJOR_TYPE,
                       &Buf1);
                if ( v9 >= 0 )
                {
                  if ( memcmp_0(&Buf1, &MFMediaType_Audio, 0x10u) || memcmp_0(&v80, &MFMediaType_Audio, 0x10u) )
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
                          "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
                          320,
                          -2147467259);
                    }
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v12 = 55;
                      goto LABEL_185;
                    }
                    goto LABEL_186;
                  }
                  v9 = (*(__int64 (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)v77 + 80LL))(
                         v77,
                         &MF_MT_SUBTYPE,
                         &v81);
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)v75 + 80LL))(
                           v75,
                           &MF_MT_SUBTYPE,
                           &v82);
                    if ( v9 >= 0 )
                    {
                      if ( memcmp_0(&v81, &MFAudioFormat_AAC, 0x10u) || memcmp_0(&v82, &MFAudioFormat_AAC, 0x10u) )
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
                              "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
                              327,
                              -2147467259);
                        }
                        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        {
                          v12 = 58;
                          goto LABEL_185;
                        }
                        goto LABEL_186;
                      }
                      v76 = -1;
                      v74 = -1;
                      if ( (*(int (__fastcall **)(__int64, const GUID *, unsigned int *))(*(_QWORD *)v77 + 56LL))(
                             v77,
                             &MF_MT_AAC_PAYLOAD_TYPE,
                             &v74) < 0
                        && (int)CTranscodeDestination::GetPayloadTypeFromSink(this, &v74) < 0 )
                      {
                        v74 = 0;
                      }
                      if ( (*(int (__fastcall **)(__int64, const GUID *, int *))(*(_QWORD *)v75 + 56LL))(
                             v75,
                             &MF_MT_AAC_PAYLOAD_TYPE,
                             &v76) >= 0
                        && v76 == v74 )
                      {
                        v51 = (__int64 *)CallStackTracing::s_wpInstance;
                        v8 = -2147467259;
                        v9 = -2147467259;
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
                          if ( *((_DWORD *)v53 + 499) != -2147467259 )
                            CallStackContext::TraceFailure(
                              v53,
                              "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
                              349,
                              -2147467259);
                        }
                        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        {
                          v12 = 59;
                          goto LABEL_185;
                        }
                        goto LABEL_186;
                      }
                      v9 = MFCreateTransformActivate(a3);
                      if ( v9 >= 0 )
                      {
                        v9 = ((__int64 (__fastcall *)(_QWORD, const GUID *, GUID *))(*a3)->lpVtbl->SetGUID)(
                               *a3,
                               &MFT_TRANSFORM_CLSID_Attribute,
                               &CLSID_CAACReMuxer);
                        if ( v9 >= 0 )
                        {
                          v9 = ((__int64 (__fastcall *)(_QWORD, const GUID *, const GUID *))(*a3)->lpVtbl->SetGUID)(
                                 *a3,
                                 &MF_TRANSFORM_CATEGORY_Attribute,
                                 &MFT_CATEGORY_OTHER);
                          if ( v9 >= 0 )
                            goto LABEL_186;
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
                                "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
                                357,
                                v9);
                          }
                          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                            goto LABEL_186;
                          v20 = 62;
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
                                "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
                                356,
                                v9);
                          }
                          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                            goto LABEL_186;
                          v20 = 61;
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
                              "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
                              355,
                              v9);
                        }
                        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                          goto LABEL_186;
                        v20 = 60;
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
                            "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
                            323,
                            v9);
                      }
                      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        goto LABEL_186;
                      v20 = 57;
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
                          "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
                          322,
                          v9);
                    }
                    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      goto LABEL_186;
                    v20 = 56;
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
                        "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
                        316,
                        v9);
                  }
                  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    goto LABEL_186;
                  v20 = 54;
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
                    CallStackContext::TraceFailure(v35, "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer", 315, v9);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_186;
                v20 = 53;
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
                    "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer",
                    310,
                    -2147418113);
              }
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_186;
              v20 = 52;
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
                CallStackContext::TraceFailure(v28, "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer", 309, v9);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_186;
            v20 = 51;
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
              CallStackContext::TraceFailure(v24, "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer", 307, v9);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_186;
          v20 = 50;
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
            CallStackContext::TraceFailure(v19, "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer", 304, v9);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_186;
        v20 = 49;
      }
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids, this, v9);
      goto LABEL_186;
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
        CallStackContext::TraceFailure(v15, "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer", 300, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 48;
      goto LABEL_185;
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
        CallStackContext::TraceFailure(v11, "CTranscodeDestination::CheckIfNeedInsertAudioRemuxer", 299, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 47;
LABEL_185:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids, this, v8);
    }
  }
LABEL_186:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v75);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v77);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v78);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v73);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800405d0  push    rbp
0x1800405d2  push    rbx
0x1800405d3  push    rsi
0x1800405d4  push    rdi
0x1800405d5  push    r12
0x1800405d7  push    r14
0x1800405d9  push    r15
0x1800405db  lea     rbp, [rsp-27h]
0x1800405e0  sub     rsp, 0A0h
0x1800405e7  mov     rax, cs:__security_cookie
0x1800405ee  xor     rax, rsp
0x1800405f1  mov     [rbp+57h+var_38], rax
0x1800405f5  mov     rdi, r8
0x1800405f8  lea     r15, aCtranscodedest_7; "CTranscodeDestination::CheckIfNeedInser"...
0x1800405ff  mov     rbx, rdx
0x180040602  mov     rsi, rcx
0x180040605  mov     rdx, r15; char *
0x180040608  lea     rcx, [rbp+57h+var_A0]; this
0x18004060c  mov     r8d, 120h; int
0x180040612  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180040617  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004061e  xor     r14d, r14d
0x180040621  mov     [rbp+57h+var_80], r14
0x180040625  mov     [rbp+57h+var_88], r14
0x180040629  mov     [rbp+57h+var_98], r14
0x18004062d  movdqu  [rbp+57h+Buf1], xmm0
0x180040632  movdqu  [rbp+57h+var_48], xmm0
0x180040637  movdqu  [rbp+57h+var_68], xmm0
0x18004063c  movdqu  [rbp+57h+var_58], xmm0
0x180040641  test    rdi, rdi
0x180040644  jnz     loc_1800406DC
0x18004064a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040651  mov     edi, 80004003h
0x180040656  mov     ebx, edi
0x180040658  test    rcx, rcx
0x18004065b  jnz     short loc_18004069E
0x18004065d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180040663  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004066a  mov     rcx, rax
0x18004066d  test    rax, rax
0x180040670  jz      short loc_180040690
0x180040672  mov     rax, [rax]
0x180040675  mov     edx, 7F0h
0x18004067a  mov     rax, [rax+8]
0x18004067e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040683  test    eax, eax
0x180040685  jz      short loc_180040690
0x180040687  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004068e  jmp     short loc_18004069E
0x180040690  lea     rcx, qword_180069A90; this
0x180040697  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004069e  cmp     [rcx+8], r14b
0x1800406a2  jz      short loc_1800406C5
0x1800406a4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800406a9  cmp     [rax+7CCh], edi
0x1800406af  jz      short loc_1800406C5
0x1800406b1  mov     r9d, edi; int
0x1800406b4  mov     r8d, 12Bh; int
0x1800406ba  mov     rdx, r15; char *
0x1800406bd  mov     rcx, rax; this
0x1800406c0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800406c5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800406ca  cmp     al, 1
0x1800406cc  jb      loc_1800411A2
0x1800406d2  mov     edx, 2Fh ; '/'
0x1800406d7  jmp     loc_180041184
0x1800406dc  test    rbx, rbx
0x1800406df  jnz     loc_180040777
0x1800406e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800406ec  mov     edi, 80004003h
0x1800406f1  mov     ebx, edi
0x1800406f3  test    rcx, rcx
0x1800406f6  jnz     short loc_180040739
0x1800406f8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800406fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180040705  mov     rcx, rax
0x180040708  test    rax, rax
0x18004070b  jz      short loc_18004072B
0x18004070d  mov     rax, [rax]
0x180040710  mov     edx, 7F0h
0x180040715  mov     rax, [rax+8]
0x180040719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004071e  test    eax, eax
0x180040720  jz      short loc_18004072B
0x180040722  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040729  jmp     short loc_180040739
0x18004072b  lea     rcx, qword_180069A90; this
0x180040732  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180040739  cmp     [rcx+8], r14b
0x18004073d  jz      short loc_180040760
0x18004073f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180040744  cmp     [rax+7CCh], edi
0x18004074a  jz      short loc_180040760
0x18004074c  mov     r9d, edi; int
0x18004074f  mov     r8d, 12Ch; int
0x180040755  mov     rdx, r15; char *
0x180040758  mov     rcx, rax; this
0x18004075b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180040760  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040765  cmp     al, 1
0x180040767  jb      loc_1800411A2
0x18004076d  mov     edx, 30h ; '0'
0x180040772  jmp     loc_180041184
0x180040777  mov     [rdi], r14
0x18004077a  lea     rdx, [rbp+57h+var_80]
0x18004077e  mov     rax, [rbx]
0x180040781  mov     rcx, rbx
0x180040784  mov     rax, [rax+110h]
0x18004078b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040790  mov     ebx, eax
0x180040792  test    eax, eax
0x180040794  jns     loc_180040829
0x18004079a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800407a1  test    rcx, rcx
0x1800407a4  jnz     short loc_1800407E7
0x1800407a6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800407ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800407b3  mov     rcx, rax
0x1800407b6  test    rax, rax
0x1800407b9  jz      short loc_1800407D9
0x1800407bb  mov     rax, [rax]
0x1800407be  mov     edx, 7F0h
0x1800407c3  mov     rax, [rax+8]
0x1800407c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407cc  test    eax, eax
0x1800407ce  jz      short loc_1800407D9
0x1800407d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800407d7  jmp     short loc_1800407E7
0x1800407d9  lea     rcx, qword_180069A90; this
0x1800407e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800407e7  cmp     [rcx+8], r14b
0x1800407eb  jz      short loc_18004080E
0x1800407ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800407f2  cmp     [rax+7CCh], ebx
0x1800407f8  jz      short loc_18004080E
0x1800407fa  mov     r9d, ebx; int
0x1800407fd  mov     r8d, 130h; int
0x180040803  mov     rdx, r15; char *
0x180040806  mov     rcx, rax; this
0x180040809  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004080e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040813  cmp     al, 1
0x180040815  jb      loc_1800411A2
0x18004081b  mov     edx, 31h ; '1'
0x180040820  mov     [rsp+0D0h+var_B0], ebx
0x180040824  jmp     loc_180041188
0x180040829  mov     rcx, [rbp+57h+var_80]
0x18004082d  lea     rdx, [rbp+57h+var_98]
0x180040831  mov     rax, [rcx]
0x180040834  mov     rax, [rax+38h]
0x180040838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004083d  test    eax, eax
0x18004083f  jns     loc_1800408F0
0x180040845  mov     rcx, [rbp+57h+var_80]
0x180040849  lea     r8, [rbp+57h+var_98]
0x18004084d  xor     edx, edx
0x18004084f  mov     rax, [rcx]
0x180040852  mov     rax, [rax+28h]
0x180040856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004085b  mov     ebx, eax
0x18004085d  test    eax, eax
0x18004085f  jns     loc_1800408F0
0x180040865  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004086c  test    rcx, rcx
0x18004086f  jnz     short loc_1800408B2
0x180040871  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180040877  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004087e  mov     rcx, rax
0x180040881  test    rax, rax
0x180040884  jz      short loc_1800408A4
0x180040886  mov     rax, [rax]
0x180040889  mov     edx, 7F0h
0x18004088e  mov     rax, [rax+8]
0x180040892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040897  test    eax, eax
0x180040899  jz      short loc_1800408A4
0x18004089b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800408a2  jmp     short loc_1800408B2
0x1800408a4  lea     rcx, qword_180069A90; this
0x1800408ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800408b2  cmp     [rcx+8], r14b
0x1800408b6  jz      short loc_1800408D9
0x1800408b8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800408bd  cmp     [rax+7CCh], ebx
0x1800408c3  jz      short loc_1800408D9
0x1800408c5  mov     r9d, ebx; int
0x1800408c8  mov     r8d, 133h; int
0x1800408ce  mov     rdx, r15; char *
0x1800408d1  mov     rcx, rax; this
0x1800408d4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800408d9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800408de  cmp     al, 1
0x1800408e0  jb      loc_1800411A2
0x1800408e6  mov     edx, 32h ; '2'
0x1800408eb  jmp     loc_180040820
0x1800408f0  mov     rcx, [rsi+8]
0x1800408f4  lea     rdx, [rbp+57h+var_88]
0x1800408f8  mov     rax, [rcx]
0x1800408fb  mov     rax, [rax+20h]
0x1800408ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040904  mov     ebx, eax
0x180040906  test    eax, eax
0x180040908  jns     loc_180040999
0x18004090e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040915  test    rcx, rcx
0x180040918  jnz     short loc_18004095B
0x18004091a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180040920  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180040927  mov     rcx, rax
0x18004092a  test    rax, rax
0x18004092d  jz      short loc_18004094D
0x18004092f  mov     rax, [rax]
0x180040932  mov     edx, 7F0h
0x180040937  mov     rax, [rax+8]
0x18004093b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040940  test    eax, eax
0x180040942  jz      short loc_18004094D
0x180040944  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004094b  jmp     short loc_18004095B
0x18004094d  lea     rcx, qword_180069A90; this
0x180040954  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004095b  cmp     [rcx+8], r14b
0x18004095f  jz      short loc_180040982
0x180040961  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180040966  cmp     [rax+7CCh], ebx
0x18004096c  jz      short loc_180040982
0x18004096e  mov     r9d, ebx; int
0x180040971  mov     r8d, 135h; int
0x180040977  mov     rdx, r15; char *
0x18004097a  mov     rcx, rax; this
0x18004097d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180040982  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040987  cmp     al, 1
0x180040989  jb      loc_1800411A2
0x18004098f  mov     edx, 33h ; '3'
0x180040994  jmp     loc_180040820
0x180040999  mov     rcx, [rbp+57h+var_88]
0x18004099d  test    rcx, rcx
0x1800409a0  jnz     loc_180040A36
0x1800409a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800409ad  mov     ebx, 8000FFFFh
0x1800409b2  test    rcx, rcx
0x1800409b5  jnz     short loc_1800409F8
0x1800409b7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800409bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800409c4  mov     rcx, rax
0x1800409c7  test    rax, rax
0x1800409ca  jz      short loc_1800409EA
0x1800409cc  mov     rax, [rax]
0x1800409cf  mov     edx, 7F0h
0x1800409d4  mov     rax, [rax+8]
0x1800409d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409dd  test    eax, eax
0x1800409df  jz      short loc_1800409EA
0x1800409e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800409e8  jmp     short loc_1800409F8
0x1800409ea  lea     rcx, qword_180069A90; this
0x1800409f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800409f8  cmp     [rcx+8], r14b
0x1800409fc  jz      short loc_180040A1F
0x1800409fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180040a03  cmp     [rax+7CCh], ebx
0x180040a09  jz      short loc_180040A1F
0x180040a0b  mov     r9d, ebx; int
0x180040a0e  mov     r8d, 136h; int
0x180040a14  mov     rdx, r15; char *
0x180040a17  mov     rcx, rax; this
0x180040a1a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180040a1f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180040a24  cmp     al, 1
0x180040a26  jb      loc_1800411A2
0x180040a2c  mov     edx, 34h ; '4'
0x180040a31  jmp     loc_180040820
0x180040a36  mov     rax, [rcx]
0x180040a39  lea     r8, [rbp+57h+var_68]
0x180040a3d  lea     rdx, MF_MT_MAJOR_TYPE
0x180040a44  mov     rax, [rax+50h]
0x180040a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a4d  mov     ebx, eax
0x180040a4f  test    eax, eax
0x180040a51  jns     loc_180040AE2
0x180040a57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040a5e  test    rcx, rcx
0x180040a61  jnz     short loc_180040AA4
0x180040a63  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180040a69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180040a70  mov     rcx, rax
0x180040a73  test    rax, rax
0x180040a76  jz      short loc_180040A96
0x180040a78  mov     rax, [rax]
0x180040a7b  mov     edx, 7F0h
0x180040a80  mov     rax, [rax+8]
0x180040a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a89  test    eax, eax
0x180040a8b  jz      short loc_180040A96
0x180040a8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180040a94  jmp     short loc_180040AA4
0x180040a96  lea     rcx, qword_180069A90; this
0x180040a9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180040aa4  cmp     [rcx+8], r14b
  ... truncated ...
```
