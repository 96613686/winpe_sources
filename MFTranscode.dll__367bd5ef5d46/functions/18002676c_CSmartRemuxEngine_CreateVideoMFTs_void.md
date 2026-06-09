# CSmartRemuxEngine::_CreateVideoMFTs(void)

- ea: `0x18002676c`
- end: `0x1800275d0`
- name: `?_CreateVideoMFTs@CSmartRemuxEngine@@IEAAJXZ`
- size: `3684`
- prototype: `__int64 __fastcall(CSmartRemuxEngine *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18001eed8`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18000b3ac`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x18001ce84`
- `0x18001d18c`
- `0x1800257dc`
- `0x18002676c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002680b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026951`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026a05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026ac5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026b75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026c54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026d04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026da3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026e97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026f4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026ff3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800270a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002715d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027206`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800272b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002736c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002741b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800274d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002680b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026951`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026a05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026ac5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026b75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026c54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026d04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026da3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026e97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026f4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026ff3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800270a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002715d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027206`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800272b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002736c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002741b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800274d1`

## string_xrefs

- `0x180026796`: `CSmartRemuxEngine::_CreateVideoMFTs`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::_CreateVideoMFTs(CSmartRemuxEngine *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rdx
  int v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  _QWORD *v39; // rsi
  _QWORD *v40; // r14
  __int64 v41; // rdx
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  __int64 *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  __int64 v74; // rcx
  __int64 v75; // rdx
  __int64 *v76; // rcx
  CallStackTracing *v77; // rax
  struct CallStackContext *v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rdx
  __int64 *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  _BYTE v85[4]; // [rsp+30h] [rbp-59h] BYREF
  int v86; // [rsp+34h] [rbp-55h] BYREF
  int v87; // [rsp+38h] [rbp-51h] BYREF
  __int64 v88; // [rsp+40h] [rbp-49h] BYREF
  __int64 v89; // [rsp+48h] [rbp-41h] BYREF
  __int64 v90; // [rsp+50h] [rbp-39h] BYREF
  struct IMFTransform *v91; // [rsp+58h] [rbp-31h] BYREF
  struct IMFTransform *v92; // [rsp+60h] [rbp-29h] BYREF
  __int64 v93; // [rsp+68h] [rbp-21h] BYREF
  IMFDXGIDeviceManager *ppDeviceManager; // [rsp+70h] [rbp-19h] BYREF
  MFT_REGISTER_TYPE_INFO v95; // [rsp+78h] [rbp-11h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v85, "CSmartRemuxEngine::_CreateVideoMFTs", 1229);
  v2 = (__int64 *)*((_QWORD *)this + 1);
  memset(&v95, 0, sizeof(v95));
  v90 = 0;
  v89 = 0;
  v86 = 1;
  v93 = 0;
  ppDeviceManager = 0;
  v87 = 0;
  v3 = *v2;
  v92 = 0;
  v91 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v3 + 64))(v2, &v93);
  if ( v5 < 0 )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSmartRemuxEngine::_CreateVideoMFTs", 1242, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 135;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, v5);
      goto LABEL_216;
    }
    goto LABEL_216;
  }
  if ( !v93 )
    goto LABEL_18;
  if ( (*(int (__fastcall **)(__int64, __int64 *, int *))(*(_QWORD *)v93 + 56LL))(v93, MF_LOW_LATENCY, &v87) < 0 )
    v87 = 0;
  if ( (*(int (__fastcall **)(__int64, const IID *, int *))(*(_QWORD *)v93 + 56LL))(
         v93,
         &MF_TRANSCODE_TOPOLOGYMODE,
         &v86) < 0 )
  {
    v10 = 1;
    v86 = 1;
  }
  else
  {
LABEL_18:
    v10 = v86;
  }
  *((_BYTE *)this + 88) = v10 != 0;
  if ( (unsigned int)CreateD3D11Manager(&ppDeviceManager) )
    *((_BYTE *)this + 88) = 0;
  ComSmartPtr<IMFTranscodeProfile>::operator=(&ppDeviceManager);
  v5 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, MFT_REGISTER_TYPE_INFO *))(**((_QWORD **)this + 19) + 80LL))(
         *((_QWORD *)this + 19),
         &MF_MT_MAJOR_TYPE,
         &v95);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, GUID *))(**((_QWORD **)this + 19) + 80LL))(
           *((_QWORD *)this + 19),
           &MF_MT_SUBTYPE,
           &v95.guidSubtype);
    if ( v5 < 0 )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != v5 )
          CallStackContext::TraceFailure(v18, "CSmartRemuxEngine::_CreateVideoMFTs", 1267, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 137;
        goto LABEL_12;
      }
      goto LABEL_216;
    }
    if ( *((_BYTE *)this + 88) )
    {
      if ( (unsigned int)CSmartRemuxEngine::_CreateMFT(&MFT_CATEGORY_VIDEO_ENCODER, 0, &v95, &v91, 0x67u) )
      {
        *((_BYTE *)this + 88) = 0;
        v5 = CSmartRemuxEngine::_CreateMFT(&MFT_CATEGORY_VIDEO_DECODER, &v95, 0, &v92, 0x61u);
        if ( v5 < 0 )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != v5 )
              CallStackContext::TraceFailure(v30, "CSmartRemuxEngine::_CreateVideoMFTs", 1281, v5);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 140;
            goto LABEL_12;
          }
          goto LABEL_216;
        }
        v5 = CSmartRemuxEngine::_CreateMFT(&MFT_CATEGORY_VIDEO_ENCODER, 0, &v95, &v91, 0x61u);
        if ( v5 < 0 )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
            if ( *((_DWORD *)v34 + 499) != v5 )
              CallStackContext::TraceFailure(v34, "CSmartRemuxEngine::_CreateVideoMFTs", 1282, v5);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 141;
            goto LABEL_12;
          }
          goto LABEL_216;
        }
      }
      else
      {
        v5 = CSmartRemuxEngine::_CreateMFT(&MFT_CATEGORY_VIDEO_DECODER, &v95, 0, &v92, 0x67u);
        if ( v5 < 0 )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
            CallStackTracing::s_wpInstance = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)v38 + 499) != v5 )
              CallStackContext::TraceFailure(v38, "CSmartRemuxEngine::_CreateVideoMFTs", 1286, v5);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 142;
            goto LABEL_12;
          }
          goto LABEL_216;
        }
      }
    }
    else
    {
      v5 = CSmartRemuxEngine::_CreateMFT(&MFT_CATEGORY_VIDEO_DECODER, &v95, 0, &v92, 0x61u);
      if ( v5 < 0 )
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)v22 + 499) != v5 )
            CallStackContext::TraceFailure(v22, "CSmartRemuxEngine::_CreateVideoMFTs", 1271, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 138;
          goto LABEL_12;
        }
        goto LABEL_216;
      }
      v5 = CSmartRemuxEngine::_CreateMFT(&MFT_CATEGORY_VIDEO_ENCODER, 0, &v95, &v91, 0x61u);
      if ( v5 < 0 )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v26 + 499) != v5 )
            CallStackContext::TraceFailure(v26, "CSmartRemuxEngine::_CreateVideoMFTs", 1272, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 139;
          goto LABEL_12;
        }
        goto LABEL_216;
      }
    }
    v39 = (_QWORD *)((char *)this + 48);
    ComSmartPtr<IMFMediaSource>::operator=((char *)this + 48, &v92);
    v40 = (_QWORD *)((char *)this + 64);
    ComSmartPtr<IMFMediaSource>::operator=((char *)this + 64, &v91);
    if ( (**(int (__fastcall ***)(_QWORD, GUID *, char *))*v40)(*v40, &IID_IMFMediaEventGenerator, (char *)this + 72) < 0 )
      *((_BYTE *)this + 88) = 0;
    if ( v87 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v40 + 64LL))(*v40, &v89);
      if ( v5 < 0 )
      {
        v42 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
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
          if ( *((_DWORD *)v44 + 499) != v5 )
            CallStackContext::TraceFailure(v44, "CSmartRemuxEngine::_CreateVideoMFTs", 1302, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 143;
          goto LABEL_12;
        }
        goto LABEL_216;
      }
      v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v89 + 168LL))(v89, MF_LOW_LATENCY, 1);
      if ( v5 < 0 )
      {
        v46 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
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
          if ( *((_DWORD *)v48 + 499) != v5 )
            CallStackContext::TraceFailure(v48, "CSmartRemuxEngine::_CreateVideoMFTs", 1303, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 144;
          goto LABEL_12;
        }
        goto LABEL_216;
      }
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v39 + 64LL))(*v39, &v90);
      if ( v5 < 0 )
      {
        v50 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49);
          CallStackTracing::s_wpInstance = v51;
          if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
          {
            v50 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v50 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v50 + 8) )
        {
          v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
          if ( *((_DWORD *)v52 + 499) != v5 )
            CallStackContext::TraceFailure(v52, "CSmartRemuxEngine::_CreateVideoMFTs", 1305, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 145;
          goto LABEL_12;
        }
        goto LABEL_216;
      }
      v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v90 + 168LL))(v90, MF_LOW_LATENCY, 1);
      if ( v5 < 0 )
      {
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53);
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
          if ( *((_DWORD *)v56 + 499) != v5 )
            CallStackContext::TraceFailure(v56, "CSmartRemuxEngine::_CreateVideoMFTs", 1306, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 146;
          goto LABEL_12;
        }
        goto LABEL_216;
      }
    }
    if ( !*((_BYTE *)this + 88) )
      goto LABEL_216;
    v57 = *v40;
    *((_DWORD *)this + 20) = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v57 + 64LL))(v57, &v89);
    if ( v5 < 0 )
    {
      v59 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
        CallStackTracing::s_wpInstance = v60;
        if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
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
        if ( *((_DWORD *)v61 + 499) != v5 )
          CallStackContext::TraceFailure(v61, "CSmartRemuxEngine::_CreateVideoMFTs", 1314, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 147;
        goto LABEL_12;
      }
      goto LABEL_216;
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v39 + 64LL))(*v39, &v90);
    if ( v5 < 0 )
    {
      v63 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62);
        CallStackTracing::s_wpInstance = v64;
        if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
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
        if ( *((_DWORD *)v65 + 499) != v5 )
          CallStackContext::TraceFailure(v65, "CSmartRemuxEngine::_CreateVideoMFTs", 1315, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 148;
        goto LABEL_12;
      }
      goto LABEL_216;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v89 + 168LL))(v89, MF_SA_D3D11_AWARE, 1);
    if ( v5 < 0 )
    {
      v67 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66);
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
        if ( *((_DWORD *)v69 + 499) != v5 )
          CallStackContext::TraceFailure(v69, "CSmartRemuxEngine::_CreateVideoMFTs", 1317, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 149;
        goto LABEL_12;
      }
      goto LABEL_216;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v90 + 168LL))(v90, MF_SA_D3D11_AWARE, 1);
    if ( v5 < 0 )
    {
      v71 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70);
        CallStackTracing::s_wpInstance = v72;
        if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
        {
          v71 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v71 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v71 + 8) )
      {
        v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
        if ( *((_DWORD *)v73 + 499) != v5 )
          CallStackContext::TraceFailure(v73, "CSmartRemuxEngine::_CreateVideoMFTs", 1318, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 150;
        goto LABEL_12;
      }
      goto LABEL_216;
    }
    v74 = *v39;
    v88 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v74 + 80LL))(v74, 0, &v88);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v88 + 168LL))(
             v88,
             MF_SA_D3D11_BINDFLAGS,
             1024);
      if ( v5 >= 0 )
        goto LABEL_215;
      v81 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v80);
        CallStackTracing::s_wpInstance = v82;
        if ( v82 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
        {
          v81 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v81 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v81 + 8) )
      {
        v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
        if ( *((_DWORD *)v83 + 499) != v5 )
          CallStackContext::TraceFailure(v83, "CSmartRemuxEngine::_CreateVideoMFTs", 1323, v5);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_215;
      v79 = 152;
    }
    else
    {
      v76 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v75);
        CallStackTracing::s_wpInstance = v77;
        if ( v77 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v77 + 8LL))(v77, 2032) )
        {
          v76 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v76 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v76 + 8) )
      {
        v78 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
        if ( *((_DWORD *)v78 + 499) != v5 )
          CallStackContext::TraceFailure(v78, "CSmartRemuxEngine::_CreateVideoMFTs", 1322, v5);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_215;
      v79 = 151;
    }
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v79, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, v5);
LABEL_215:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v88);
    goto LABEL_216;
  }
  v12 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
    CallStackTracing::s_wpInstance = v13;
    if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v12 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
    if ( *((_DWORD *)v14 + 499) != v5 )
      CallStackContext::TraceFailure(v14, "CSmartRemuxEngine::_CreateVideoMFTs", 1266, v5);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v9 = 136;
    goto LABEL_12;
  }
LABEL_216:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppDeviceManager);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v93);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v89);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v90);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v91);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v92);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v85);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002676c  push    rbp
0x18002676e  push    rbx
0x18002676f  push    rsi
0x180026770  push    rdi
0x180026771  push    r12
0x180026773  push    r13
0x180026775  push    r14
0x180026777  push    r15
0x180026779  lea     rbp, [rsp-1Fh]
0x18002677e  sub     rsp, 0A8h
0x180026785  mov     rax, cs:__security_cookie
0x18002678c  xor     rax, rsp
0x18002678f  mov     [rbp+57h+var_48], rax
0x180026793  mov     rdi, rcx
0x180026796  lea     r13, aCsmartremuxeng_10; "CSmartRemuxEngine::_CreateVideoMFTs"
0x18002679d  mov     rdx, r13; char *
0x1800267a0  lea     rcx, [rbp+57h+var_B0]; this
0x1800267a4  mov     r8d, 4CDh; int
0x1800267aa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800267af  mov     rcx, [rdi+8]
0x1800267b3  lea     rdx, [rbp+57h+var_78]
0x1800267b7  xor     r15d, r15d
0x1800267ba  xorps   xmm0, xmm0
0x1800267bd  movups  [rbp+57h+var_68], xmm0
0x1800267c1  mov     [rbp+57h+var_90], r15
0x1800267c5  movups  [rbp+57h+var_58], xmm0
0x1800267c9  mov     [rbp+57h+var_98], r15
0x1800267cd  lea     r12d, [r15+1]
0x1800267d1  mov     [rbp+57h+var_AC], r12d
0x1800267d5  mov     [rbp+57h+var_78], r15
0x1800267d9  mov     [rbp+57h+ppDeviceManager], r15
0x1800267dd  mov     [rbp+57h+var_A8], r15d
0x1800267e1  mov     rax, [rcx]
0x1800267e4  mov     [rbp+57h+var_80], r15
0x1800267e8  mov     [rbp+57h+var_88], r15
0x1800267ec  mov     rax, [rax+40h]
0x1800267f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267f5  mov     ebx, eax
0x1800267f7  test    eax, eax
0x1800267f9  jns     loc_1800268A9
0x1800267ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026806  test    rcx, rcx
0x180026809  jnz     short loc_18002684C
0x18002680b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026811  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026818  mov     rcx, rax
0x18002681b  test    rax, rax
0x18002681e  jz      short loc_18002683E
0x180026820  mov     rax, [rax]
0x180026823  mov     edx, 7F0h
0x180026828  mov     rax, [rax+8]
0x18002682c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026831  test    eax, eax
0x180026833  jz      short loc_18002683E
0x180026835  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002683c  jmp     short loc_18002684C
0x18002683e  lea     rcx, qword_180069A90; this
0x180026845  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002684c  cmp     [rcx+8], r15b
0x180026850  jz      short loc_180026873
0x180026852  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026857  cmp     [rax+7CCh], ebx
0x18002685d  jz      short loc_180026873
0x18002685f  mov     r9d, ebx; int
0x180026862  mov     r8d, 4DAh; int
0x180026868  mov     rdx, r13; char *
0x18002686b  mov     rcx, rax; this
0x18002686e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026873  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026878  cmp     al, r12b
0x18002687b  jb      loc_18002756F
0x180026881  mov     edx, 87h
0x180026886  mov     rcx, cs:WPP_GLOBAL_Control
0x18002688d  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x180026894  mov     r9, rdi
0x180026897  mov     [rsp+0E0h+var_C0], ebx
0x18002689b  mov     rcx, [rcx+10h]
0x18002689f  call    WPP_SF_qd
0x1800268a4  jmp     loc_18002756F
0x1800268a9  mov     rcx, [rbp+57h+var_78]
0x1800268ad  test    rcx, rcx
0x1800268b0  jz      short loc_1800268F8
0x1800268b2  mov     rax, [rcx]
0x1800268b5  lea     r8, [rbp+57h+var_A8]
0x1800268b9  lea     rdx, MF_LOW_LATENCY
0x1800268c0  mov     rax, [rax+38h]
0x1800268c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268c9  test    eax, eax
0x1800268cb  jns     short loc_1800268D1
0x1800268cd  mov     [rbp+57h+var_A8], r15d
0x1800268d1  mov     rcx, [rbp+57h+var_78]
0x1800268d5  lea     r8, [rbp+57h+var_AC]
0x1800268d9  lea     rdx, MF_TRANSCODE_TOPOLOGYMODE
0x1800268e0  mov     rax, [rcx]
0x1800268e3  mov     rax, [rax+38h]
0x1800268e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268ec  test    eax, eax
0x1800268ee  jns     short loc_1800268F8
0x1800268f0  mov     eax, r12d
0x1800268f3  mov     [rbp+57h+var_AC], eax
0x1800268f6  jmp     short loc_1800268FB
0x1800268f8  mov     eax, [rbp+57h+var_AC]
0x1800268fb  test    eax, eax
0x1800268fd  lea     rcx, [rbp+57h+ppDeviceManager]; ppDeviceManager
0x180026901  setnz   al
0x180026904  mov     [rdi+58h], al
0x180026907  call    ?CreateD3D11Manager@@YAJPEAPEAUIMFDXGIDeviceManager@@@Z; CreateD3D11Manager(IMFDXGIDeviceManager * *)
0x18002690c  test    eax, eax
0x18002690e  jz      short loc_180026914
0x180026910  mov     [rdi+58h], r15b
0x180026914  lea     rcx, [rbp+57h+ppDeviceManager]
0x180026918  call    ??4?$ComSmartPtr@UIMFTranscodeProfile@@@@QEAAPEAUIMFTranscodeProfile@@PEAU1@@Z; ComSmartPtr<IMFTranscodeProfile>::operator=(IMFTranscodeProfile *)
0x18002691d  mov     rcx, [rdi+98h]
0x180026924  lea     r8, [rbp+57h+var_68]
0x180026928  lea     rdx, MF_MT_MAJOR_TYPE
0x18002692f  mov     rax, [rcx]
0x180026932  mov     rax, [rax+50h]
0x180026936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002693b  mov     ebx, eax
0x18002693d  test    eax, eax
0x18002693f  jns     loc_1800269D1
0x180026945  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002694c  test    rcx, rcx
0x18002694f  jnz     short loc_180026992
0x180026951  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026957  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002695e  mov     rcx, rax
0x180026961  test    rax, rax
0x180026964  jz      short loc_180026984
0x180026966  mov     rax, [rax]
0x180026969  mov     edx, 7F0h
0x18002696e  mov     rax, [rax+8]
0x180026972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026977  test    eax, eax
0x180026979  jz      short loc_180026984
0x18002697b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026982  jmp     short loc_180026992
0x180026984  lea     rcx, qword_180069A90; this
0x18002698b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026992  cmp     [rcx+8], r15b
0x180026996  jz      short loc_1800269B9
0x180026998  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002699d  cmp     [rax+7CCh], ebx
0x1800269a3  jz      short loc_1800269B9
0x1800269a5  mov     r9d, ebx; int
0x1800269a8  mov     r8d, 4F2h; int
0x1800269ae  mov     rdx, r13; char *
0x1800269b1  mov     rcx, rax; this
0x1800269b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800269b9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800269be  cmp     al, r12b
0x1800269c1  jb      loc_18002756F
0x1800269c7  mov     edx, 88h
0x1800269cc  jmp     loc_180026886
0x1800269d1  mov     rcx, [rdi+98h]
0x1800269d8  lea     r8, [rbp+57h+var_58]
0x1800269dc  lea     rdx, MF_MT_SUBTYPE
0x1800269e3  mov     rax, [rcx]
0x1800269e6  mov     rax, [rax+50h]
0x1800269ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269ef  mov     ebx, eax
0x1800269f1  test    eax, eax
0x1800269f3  jns     loc_180026A85
0x1800269f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a00  test    rcx, rcx
0x180026a03  jnz     short loc_180026A46
0x180026a05  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026a0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a12  mov     rcx, rax
0x180026a15  test    rax, rax
0x180026a18  jz      short loc_180026A38
0x180026a1a  mov     rax, [rax]
0x180026a1d  mov     edx, 7F0h
0x180026a22  mov     rax, [rax+8]
0x180026a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a2b  test    eax, eax
0x180026a2d  jz      short loc_180026A38
0x180026a2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a36  jmp     short loc_180026A46
0x180026a38  lea     rcx, qword_180069A90; this
0x180026a3f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026a46  cmp     [rcx+8], r15b
0x180026a4a  jz      short loc_180026A6D
0x180026a4c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026a51  cmp     [rax+7CCh], ebx
0x180026a57  jz      short loc_180026A6D
0x180026a59  mov     r9d, ebx; int
0x180026a5c  mov     r8d, 4F3h; int
0x180026a62  mov     rdx, r13; char *
0x180026a65  mov     rcx, rax; this
0x180026a68  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026a6d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026a72  cmp     al, r12b
0x180026a75  jb      loc_18002756F
0x180026a7b  mov     edx, 89h
0x180026a80  jmp     loc_180026886
0x180026a85  cmp     [rdi+58h], r15b
0x180026a89  jnz     loc_180026BF5
0x180026a8f  mov     esi, 61h ; 'a'
0x180026a94  lea     r9, [rbp+57h+var_80]; struct IMFTransform **
0x180026a98  xor     r8d, r8d; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180026a9b  mov     [rsp+0E0h+var_C0], esi; unsigned int
0x180026a9f  lea     rdx, [rbp+57h+var_68]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180026aa3  lea     rcx, MFT_CATEGORY_VIDEO_DECODER; struct _GUID *
0x180026aaa  call    ?_CreateMFT@CSmartRemuxEngine@@KAJAEBU_GUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAUIMFTransform@@I@Z; CSmartRemuxEngine::_CreateMFT(_GUID const &,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,uint)
0x180026aaf  mov     ebx, eax
0x180026ab1  test    eax, eax
0x180026ab3  jns     loc_180026B45
0x180026ab9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ac0  test    rcx, rcx
0x180026ac3  jnz     short loc_180026B06
0x180026ac5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026acb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ad2  mov     rcx, rax
0x180026ad5  test    rax, rax
0x180026ad8  jz      short loc_180026AF8
0x180026ada  mov     rax, [rax]
0x180026add  mov     edx, 7F0h
0x180026ae2  mov     rax, [rax+8]
0x180026ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aeb  test    eax, eax
0x180026aed  jz      short loc_180026AF8
0x180026aef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026af6  jmp     short loc_180026B06
0x180026af8  lea     rcx, qword_180069A90; this
0x180026aff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b06  cmp     [rcx+8], r15b
0x180026b0a  jz      short loc_180026B2D
0x180026b0c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026b11  cmp     [rax+7CCh], ebx
0x180026b17  jz      short loc_180026B2D
0x180026b19  mov     r9d, ebx; int
0x180026b1c  mov     r8d, 4F7h; int
0x180026b22  mov     rdx, r13; char *
0x180026b25  mov     rcx, rax; this
0x180026b28  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026b2d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026b32  cmp     al, r12b
0x180026b35  jb      loc_18002756F
0x180026b3b  mov     edx, 8Ah
0x180026b40  jmp     loc_180026886
0x180026b45  lea     r9, [rbp+57h+var_88]; struct IMFTransform **
0x180026b49  mov     [rsp+0E0h+var_C0], esi; unsigned int
0x180026b4d  lea     r8, [rbp+57h+var_68]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180026b51  xor     edx, edx; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180026b53  lea     rcx, MFT_CATEGORY_VIDEO_ENCODER; struct _GUID *
0x180026b5a  call    ?_CreateMFT@CSmartRemuxEngine@@KAJAEBU_GUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAUIMFTransform@@I@Z; CSmartRemuxEngine::_CreateMFT(_GUID const &,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,uint)
0x180026b5f  mov     ebx, eax
0x180026b61  test    eax, eax
0x180026b63  jns     loc_180026E23
0x180026b69  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b70  test    rcx, rcx
0x180026b73  jnz     short loc_180026BB6
0x180026b75  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180026b7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026b82  mov     rcx, rax
0x180026b85  test    rax, rax
0x180026b88  jz      short loc_180026BA8
0x180026b8a  mov     rax, [rax]
0x180026b8d  mov     edx, 7F0h
0x180026b92  mov     rax, [rax+8]
0x180026b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b9b  test    eax, eax
0x180026b9d  jz      short loc_180026BA8
0x180026b9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026ba6  jmp     short loc_180026BB6
0x180026ba8  lea     rcx, qword_180069A90; this
0x180026baf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026bb6  cmp     [rcx+8], r15b
0x180026bba  jz      short loc_180026BDD
0x180026bbc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026bc1  cmp     [rax+7CCh], ebx
0x180026bc7  jz      short loc_180026BDD
0x180026bc9  mov     r9d, ebx; int
0x180026bcc  mov     r8d, 4F8h; int
0x180026bd2  mov     rdx, r13; char *
0x180026bd5  mov     rcx, rax; this
0x180026bd8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026bdd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180026be2  cmp     al, r12b
0x180026be5  jb      loc_18002756F
0x180026beb  mov     edx, 8Bh
0x180026bf0  jmp     loc_180026886
0x180026bf5  mov     ebx, 67h ; 'g'
0x180026bfa  lea     r9, [rbp+57h+var_88]; struct IMFTransform **
0x180026bfe  lea     r8, [rbp+57h+var_68]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180026c02  mov     [rsp+0E0h+var_C0], ebx; unsigned int
0x180026c06  xor     edx, edx; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180026c08  lea     rcx, MFT_CATEGORY_VIDEO_ENCODER; struct _GUID *
0x180026c0f  call    ?_CreateMFT@CSmartRemuxEngine@@KAJAEBU_GUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAUIMFTransform@@I@Z; CSmartRemuxEngine::_CreateMFT(_GUID const &,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,uint)
0x180026c14  xor     r8d, r8d; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180026c17  lea     r9, [rbp+57h+var_80]; struct IMFTransform **
0x180026c1b  lea     rdx, [rbp+57h+var_68]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x180026c1f  lea     rcx, MFT_CATEGORY_VIDEO_DECODER; struct _GUID *
0x180026c26  test    eax, eax
0x180026c28  jz      loc_180026D84
0x180026c2e  lea     esi, [rbx-6]
0x180026c31  mov     [rdi+58h], r15b
0x180026c35  mov     [rsp+0E0h+var_C0], esi; unsigned int
0x180026c39  call    ?_CreateMFT@CSmartRemuxEngine@@KAJAEBU_GUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAPEAUIMFTransform@@I@Z; CSmartRemuxEngine::_CreateMFT(_GUID const &,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,uint)
  ... truncated ...
```
