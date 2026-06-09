# CSmartRemuxEngine::_ProcessOutputVideoDecSW(void)

- ea: `0x180029548`
- end: `0x18002a00e`
- name: `?_ProcessOutputVideoDecSW@CSmartRemuxEngine@@IEAAJXZ`
- size: `2758`
- prototype: `__int64 __fastcall(CSmartRemuxEngine *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800275d8`
- `0x18002b3d4`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a320`
- `0x18001a330`
- `0x18001c280`
- `0x180029548`
- `0x18002a014`
- `0x18002bc78`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029874`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029923`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800299af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029a40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029acc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029b58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029be4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029c70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029cfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029d88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029e1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029ea8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029f34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029874`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029923`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800299af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029a40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029acc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029b58`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029be4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029c70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029cfc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029d88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029e1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029ea8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029f34`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x1800295b4`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x1800295b4`
- `MFPlat!MFCreateSample` at `0x180029598`
- `MFPlat!MFCreateSample` at `0x180029598`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::_ProcessOutputVideoDecSW(DWORD *this)
{
  __int64 v2; // rdx
  HRESULT v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  unsigned int i; // esi
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
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
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v65; // [rsp+40h] [rbp-30h] BYREF
  __int128 v66; // [rsp+48h] [rbp-28h] BYREF
  __int128 v67; // [rsp+58h] [rbp-18h]
  IMFSample *ppIMFSample; // [rsp+B0h] [rbp+40h] BYREF
  int v69; // [rsp+B8h] [rbp+48h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v71; // [rsp+C8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&ppIMFSample,
    "CSmartRemuxEngine::_ProcessOutputVideoDecSW",
    1935);
  v66 = 0;
  v69 = 0;
  v67 = 0;
  while ( 1 )
  {
    ppIMFSample = 0;
    ppBuffer = 0;
    v3 = MFCreateSample(&ppIMFSample);
    if ( v3 < 0 )
    {
      v61 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 1945, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_167;
      v36 = 251;
LABEL_166:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, v3);
      goto LABEL_167;
    }
    v3 = MFCreateAlignedMemoryBuffer(this[14], 0xFu, &ppBuffer);
    if ( v3 < 0 )
    {
      v58 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
        CallStackTracing::s_wpInstance = v59;
        if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
        {
          v58 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v58 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v58 + 8) )
      {
        v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
        if ( *((_DWORD *)v60 + 499) != v3 )
          CallStackContext::TraceFailure(v60, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 1946, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_167;
      v36 = 252;
      goto LABEL_166;
    }
    v3 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, ppBuffer);
    if ( v3 < 0 )
    {
      v55 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
        CallStackTracing::s_wpInstance = v56;
        if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
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
        if ( *((_DWORD *)v57 + 499) != v3 )
          CallStackContext::TraceFailure(v57, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 1947, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_167;
      v36 = 253;
      goto LABEL_166;
    }
    v6 = *((_QWORD *)this + 6);
    *((_QWORD *)&v66 + 1) = ppIMFSample;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int128 *, int *))(*(_QWORD *)v6 + 200LL))(
           v6,
           0,
           1,
           &v66,
           &v69);
    v3 = v7;
    if ( v7 == -1072861838 )
    {
      v3 = 0;
      goto LABEL_167;
    }
    if ( v7 == -1072861855 )
      break;
    if ( v7 < 0 )
    {
      v52 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v54 + 499) != v3 )
          CallStackContext::TraceFailure(v54, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 1987, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_167;
      v36 = 258;
      goto LABEL_166;
    }
    v65 = 0;
    v3 = ((__int64 (__fastcall *)(IMFSample *, __int64 *))ppIMFSample->lpVtbl->GetSampleTime)(ppIMFSample, &v65);
    if ( v3 < 0 )
    {
      v49 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v51 + 499) != v3 )
          CallStackContext::TraceFailure(v51, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 1990, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_167;
      v36 = 259;
      goto LABEL_166;
    }
    if ( v65 < *((_QWORD *)this + 32) )
      goto LABEL_15;
    v15 = *((_QWORD *)this + 33);
    if ( v15 && v65 > v15 )
    {
      *((_BYTE *)this + 148) = 1;
      goto LABEL_15;
    }
    v3 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleTime)(
           ppIMFSample,
           v65 - *((_QWORD *)this + 20));
    if ( v3 < 0 )
    {
      v46 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
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
        if ( *((_DWORD *)v48 + 499) != v3 )
          CallStackContext::TraceFailure(v48, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 2001, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_167;
      v36 = 260;
      goto LABEL_166;
    }
    if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() )
      WPP_SF_qiii(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        261,
        v17,
        this,
        v65,
        *((_QWORD *)this + 20),
        *((_QWORD *)this + 32));
    v18 = *((_QWORD *)this + 25);
    if ( v18 <= v65 - *((_QWORD *)this + 32) )
      v18 = v65 - *((_QWORD *)this + 32);
    *((_QWORD *)this + 25) = v18;
    if ( !this[35] )
    {
      v3 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
             ppIMFSample,
             &MFSampleExtension_Discontinuity,
             1);
      if ( v3 < 0 )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
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
          if ( *((_DWORD *)v39 + 499) != v3 )
            CallStackContext::TraceFailure(v39, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 2009, v3);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_167;
        v36 = 262;
        goto LABEL_166;
      }
    }
    v20 = *((_QWORD *)this + 8);
    ++this[35];
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, IMFSample *, _QWORD))(*(_QWORD *)v20 + 192LL))(
           v20,
           0,
           ppIMFSample,
           0);
    if ( v3 < 0 )
    {
      v43 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
        CallStackTracing::s_wpInstance = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
        {
          v43 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v43 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v43 + 8) )
      {
        v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
        if ( *((_DWORD *)v45 + 499) != v3 )
          CallStackContext::TraceFailure(v45, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 2013, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_167;
      v36 = 263;
      goto LABEL_166;
    }
    v3 = CSmartRemuxEngine::_ProcessOutputVideoEnc((CSmartRemuxEngine *)this);
    if ( v3 < 0 )
    {
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != v3 )
          CallStackContext::TraceFailure(v42, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 2014, v3);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_167;
      v36 = 264;
      goto LABEL_166;
    }
    if ( *((_QWORD *)&v67 + 1) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v67 + 1) + 16LL))(*((_QWORD *)&v67 + 1));
      *((_QWORD *)&v67 + 1) = 0;
    }
LABEL_15:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppBuffer);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppIMFSample);
  }
  if ( v69 != 256 )
  {
    v33 = (__int64 *)CallStackTracing::s_wpInstance;
    v3 = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
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
      if ( *((_DWORD *)v35 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v35, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 1960, -1072875845);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_167;
    v36 = 254;
    goto LABEL_166;
  }
  for ( i = 0; ; ++i )
  {
    v10 = *((_QWORD *)this + 6);
    v71 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v10 + 112LL))(v10, 0, i, &v71);
    if ( v3 < 0 )
    {
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)v32 + 499) != v3 )
          CallStackContext::TraceFailure(v32, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 1973, v3);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v26 = 255;
        goto LABEL_43;
      }
      goto LABEL_44;
    }
    v3 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v71 + 168LL))(
           v71,
           &MF_MT_INTERLACE_MODE,
           2);
    if ( v3 < 0 )
      break;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 8) + 120LL))(
           *((_QWORD *)this + 8),
           0,
           v71,
           0) >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 6) + 128LL))(
             *((_QWORD *)this + 6),
             0,
             v71,
             0);
      if ( v3 >= 0 )
      {
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v71);
        goto LABEL_15;
      }
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v3 )
          CallStackContext::TraceFailure(v25, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 1978, v3);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v26 = 257;
LABEL_43:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, v3);
        goto LABEL_44;
      }
      goto LABEL_44;
    }
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v71);
  }
  v27 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
    CallStackTracing::s_wpInstance = v28;
    if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v27 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v27 + 8) )
  {
    v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
    if ( *((_DWORD *)v29 + 499) != v3 )
      CallStackContext::TraceFailure(v29, "CSmartRemuxEngine::_ProcessOutputVideoDecSW", 1975, v3);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v26 = 256;
    goto LABEL_43;
  }
LABEL_44:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v71);
LABEL_167:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppBuffer);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppIMFSample);
  if ( *((_QWORD *)&v67 + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v67 + 1) + 16LL))(*((_QWORD *)&v67 + 1));
    *((_QWORD *)&v67 + 1) = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&ppIMFSample);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180029548  push    rbp
0x18002954a  push    rbx
0x18002954b  push    rsi
0x18002954c  push    rdi
0x18002954d  push    r12
0x18002954f  push    r14
0x180029551  push    r15
0x180029553  mov     rbp, rsp
0x180029556  sub     rsp, 70h
0x18002955a  mov     rdi, rcx
0x18002955d  lea     r12, aCsmartremuxeng_27; "CSmartRemuxEngine::_ProcessOutputVideoD"...
0x180029564  mov     rdx, r12; char *
0x180029567  lea     rcx, [rbp+ppIMFSample]; this
0x18002956b  mov     r8d, 78Fh; int
0x180029571  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180029576  xor     r14d, r14d
0x180029579  xorps   xmm0, xmm0
0x18002957c  movups  [rbp+var_28], xmm0
0x180029580  mov     [rbp+arg_8], r14d
0x180029584  movups  [rbp+var_18], xmm0
0x180029588  lea     r15d, [r14+1]
0x18002958c  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x180029590  mov     [rbp+ppIMFSample], r14
0x180029594  mov     [rbp+ppBuffer], r14
0x180029598  call    cs:__imp_MFCreateSample
0x18002959e  mov     ebx, eax
0x1800295a0  test    eax, eax
0x1800295a2  js      loc_180029F28
0x1800295a8  mov     ecx, [rdi+38h]; cbMaxLength
0x1800295ab  lea     r8, [rbp+ppBuffer]; ppBuffer
0x1800295af  mov     edx, 0Fh; cbAligment
0x1800295b4  call    cs:__imp_MFCreateAlignedMemoryBuffer
0x1800295ba  mov     ebx, eax
0x1800295bc  test    eax, eax
0x1800295be  js      loc_180029E9C
0x1800295c4  mov     rcx, [rbp+ppIMFSample]
0x1800295c8  mov     rdx, [rbp+ppBuffer]
0x1800295cc  mov     rax, [rcx]
0x1800295cf  mov     rax, [rax+150h]
0x1800295d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295db  mov     ebx, eax
0x1800295dd  test    eax, eax
0x1800295df  js      loc_180029E10
0x1800295e5  mov     rax, [rbp+ppIMFSample]
0x1800295e9  lea     rdx, [rbp+arg_8]
0x1800295ed  mov     rcx, [rdi+30h]
0x1800295f1  lea     r9, [rbp+var_28]
0x1800295f5  mov     qword ptr [rbp+var_28+8], rax
0x1800295f9  mov     r8d, r15d
0x1800295fc  mov     [rsp+70h+var_50], rdx
0x180029601  xor     edx, edx
0x180029603  mov     rax, [rcx]
0x180029606  mov     rax, [rax+0C8h]
0x18002960d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029612  mov     ebx, eax
0x180029614  cmp     eax, 0C00D6D72h
0x180029619  jz      loc_180029E08
0x18002961f  cmp     eax, 0C00D6D61h
0x180029624  jnz     loc_1800296FC
0x18002962a  cmp     [rbp+arg_8], 100h
0x180029631  jnz     loc_180029A2F
0x180029637  mov     esi, r14d
0x18002963a  mov     rcx, [rdi+30h]
0x18002963e  lea     r9, [rbp+arg_18]
0x180029642  mov     [rbp+arg_18], r14
0x180029646  mov     r8d, esi
0x180029649  xor     edx, edx
0x18002964b  mov     rax, [rcx]
0x18002964e  mov     rax, [rax+70h]
0x180029652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029657  mov     ebx, eax
0x180029659  test    eax, eax
0x18002965b  js      loc_1800299A3
0x180029661  mov     rcx, [rbp+arg_18]
0x180029665  lea     rdx, MF_MT_INTERLACE_MODE
0x18002966c  mov     r8d, 2
0x180029672  mov     rax, [rcx]
0x180029675  mov     rax, [rax+0A8h]
0x18002967c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029681  mov     ebx, eax
0x180029683  test    eax, eax
0x180029685  js      loc_180029917
0x18002968b  mov     rcx, [rdi+40h]
0x18002968f  xor     r9d, r9d
0x180029692  mov     r8, [rbp+arg_18]
0x180029696  xor     edx, edx
0x180029698  mov     rax, [rcx]
0x18002969b  mov     rax, [rax+78h]
0x18002969f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296a4  test    eax, eax
0x1800296a6  jns     short loc_1800296B6
0x1800296a8  add     esi, r15d
0x1800296ab  lea     rcx, [rbp+arg_18]
0x1800296af  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800296b4  jmp     short loc_18002963A
0x1800296b6  mov     rcx, [rdi+30h]
0x1800296ba  xor     r9d, r9d
0x1800296bd  mov     r8, [rbp+arg_18]
0x1800296c1  xor     edx, edx
0x1800296c3  mov     rax, [rcx]
0x1800296c6  mov     rax, [rax+80h]
0x1800296cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296d2  mov     ebx, eax
0x1800296d4  test    eax, eax
0x1800296d6  js      loc_180029868
0x1800296dc  lea     rcx, [rbp+arg_18]
0x1800296e0  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800296e5  lea     rcx, [rbp+ppBuffer]
0x1800296e9  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800296ee  lea     rcx, [rbp+ppIMFSample]
0x1800296f2  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800296f7  jmp     loc_18002958C
0x1800296fc  test    ebx, ebx
0x1800296fe  js      loc_180029D7C
0x180029704  mov     rcx, [rbp+ppIMFSample]
0x180029708  lea     rdx, [rbp+var_30]
0x18002970c  mov     [rbp+var_30], r14
0x180029710  mov     rax, [rcx]
0x180029713  mov     rax, [rax+118h]
0x18002971a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002971f  mov     ebx, eax
0x180029721  test    eax, eax
0x180029723  js      loc_180029CF0
0x180029729  mov     rdx, [rbp+var_30]
0x18002972d  cmp     rdx, [rdi+100h]
0x180029734  jl      short loc_1800296E5
0x180029736  mov     rax, [rdi+108h]
0x18002973d  test    rax, rax
0x180029740  jz      short loc_180029750
0x180029742  cmp     rdx, rax
0x180029745  jle     short loc_180029750
0x180029747  mov     [rdi+94h], r15b
0x18002974e  jmp     short loc_1800296E5
0x180029750  mov     rcx, [rbp+ppIMFSample]
0x180029754  sub     rdx, [rdi+0A0h]
0x18002975b  mov     rax, [rcx]
0x18002975e  mov     rax, [rax+120h]
0x180029765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002976a  mov     ebx, eax
0x18002976c  test    eax, eax
0x18002976e  js      loc_180029C64
0x180029774  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x180029779  cmp     al, r15b
0x18002977c  jb      short loc_1800297B7
0x18002977e  mov     rax, [rdi+100h]
0x180029785  mov     edx, 105h
0x18002978a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029791  mov     r9, rdi
0x180029794  mov     [rsp+70h+var_40], rax
0x180029799  mov     rax, [rdi+0A0h]
0x1800297a0  mov     [rsp+70h+var_48], rax
0x1800297a5  mov     rax, [rbp+var_30]
0x1800297a9  mov     rcx, [rcx+38h]
0x1800297ad  mov     [rsp+70h+var_50], rax
0x1800297b2  call    WPP_SF_qiii
0x1800297b7  mov     rax, [rdi+0C8h]
0x1800297be  mov     rcx, [rbp+var_30]
0x1800297c2  sub     rcx, [rdi+100h]
0x1800297c9  cmp     rax, rcx
0x1800297cc  cmovle  rax, rcx
0x1800297d0  mov     [rdi+0C8h], rax
0x1800297d7  cmp     [rdi+8Ch], r14d
0x1800297de  jnz     short loc_180029807
0x1800297e0  mov     rcx, [rbp+ppIMFSample]
0x1800297e4  lea     rdx, MFSampleExtension_Discontinuity
0x1800297eb  mov     r8d, r15d
0x1800297ee  mov     rax, [rcx]
0x1800297f1  mov     rax, [rax+0A8h]
0x1800297f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297fd  mov     ebx, eax
0x1800297ff  test    eax, eax
0x180029801  js      loc_180029AC0
0x180029807  mov     rcx, [rdi+40h]
0x18002980b  xor     r9d, r9d
0x18002980e  add     [rdi+8Ch], r15d
0x180029815  xor     edx, edx
0x180029817  mov     r8, [rbp+ppIMFSample]
0x18002981b  mov     rax, [rcx]
0x18002981e  mov     rax, [rax+0C0h]
0x180029825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002982a  mov     ebx, eax
0x18002982c  test    eax, eax
0x18002982e  js      loc_180029BD8
0x180029834  mov     rcx, rdi; this
0x180029837  call    ?_ProcessOutputVideoEnc@CSmartRemuxEngine@@IEAAJXZ; CSmartRemuxEngine::_ProcessOutputVideoEnc(void)
0x18002983c  mov     ebx, eax
0x18002983e  test    eax, eax
0x180029840  js      loc_180029B4C
0x180029846  mov     rcx, qword ptr [rbp+var_18+8]
0x18002984a  test    rcx, rcx
0x18002984d  jz      loc_1800296E5
0x180029853  mov     rax, [rcx]
0x180029856  mov     rax, [rax+10h]
0x18002985a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002985f  mov     qword ptr [rbp+var_18+8], r14
0x180029863  jmp     loc_1800296E5
0x180029868  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002986f  test    rcx, rcx
0x180029872  jnz     short loc_1800298B5
0x180029874  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002987a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180029881  mov     rcx, rax
0x180029884  test    rax, rax
0x180029887  jz      short loc_1800298A7
0x180029889  mov     rax, [rax]
0x18002988c  mov     edx, 7F0h
0x180029891  mov     rax, [rax+8]
0x180029895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002989a  test    eax, eax
0x18002989c  jz      short loc_1800298A7
0x18002989e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800298a5  jmp     short loc_1800298B5
0x1800298a7  lea     rcx, qword_180069A90; this
0x1800298ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800298b5  cmp     [rcx+8], r14b
0x1800298b9  jz      short loc_1800298DC
0x1800298bb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800298c0  cmp     [rax+7CCh], ebx
0x1800298c6  jz      short loc_1800298DC
0x1800298c8  mov     r9d, ebx; int
0x1800298cb  mov     r8d, 7BAh; int
0x1800298d1  mov     rdx, r12; char *
0x1800298d4  mov     rcx, rax; this
0x1800298d7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800298dc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800298e1  cmp     al, r15b
0x1800298e4  jb      short loc_180029909
0x1800298e6  mov     edx, 101h
0x1800298eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800298f2  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x1800298f9  mov     r9, rdi
0x1800298fc  mov     dword ptr [rsp+70h+var_50], ebx
0x180029900  mov     rcx, [rcx+10h]
0x180029904  call    WPP_SF_qd
0x180029909  lea     rcx, [rbp+arg_18]
0x18002990d  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180029912  jmp     loc_180029FC9
0x180029917  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002991e  test    rcx, rcx
0x180029921  jnz     short loc_180029964
0x180029923  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180029929  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180029930  mov     rcx, rax
0x180029933  test    rax, rax
0x180029936  jz      short loc_180029956
0x180029938  mov     rax, [rax]
0x18002993b  mov     edx, 7F0h
0x180029940  mov     rax, [rax+8]
0x180029944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029949  test    eax, eax
0x18002994b  jz      short loc_180029956
0x18002994d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029954  jmp     short loc_180029964
0x180029956  lea     rcx, qword_180069A90; this
0x18002995d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180029964  cmp     [rcx+8], r14b
0x180029968  jz      short loc_18002998B
0x18002996a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002996f  cmp     [rax+7CCh], ebx
0x180029975  jz      short loc_18002998B
0x180029977  mov     r9d, ebx; int
0x18002997a  mov     r8d, 7B7h; int
0x180029980  mov     rdx, r12; char *
0x180029983  mov     rcx, rax; this
0x180029986  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002998b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180029990  cmp     al, r15b
0x180029993  jb      loc_180029909
0x180029999  mov     edx, 100h
0x18002999e  jmp     loc_1800298EB
0x1800299a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800299aa  test    rcx, rcx
0x1800299ad  jnz     short loc_1800299F0
0x1800299af  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800299b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800299bc  mov     rcx, rax
0x1800299bf  test    rax, rax
0x1800299c2  jz      short loc_1800299E2
0x1800299c4  mov     rax, [rax]
0x1800299c7  mov     edx, 7F0h
0x1800299cc  mov     rax, [rax+8]
0x1800299d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299d5  test    eax, eax
0x1800299d7  jz      short loc_1800299E2
0x1800299d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800299e0  jmp     short loc_1800299F0
0x1800299e2  lea     rcx, qword_180069A90; this
0x1800299e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800299f0  cmp     [rcx+8], r14b
0x1800299f4  jz      short loc_180029A17
0x1800299f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800299fb  cmp     [rax+7CCh], ebx
0x180029a01  jz      short loc_180029A17
0x180029a03  mov     r9d, ebx; int
0x180029a06  mov     r8d, 7B5h; int
0x180029a0c  mov     rdx, r12; char *
0x180029a0f  mov     rcx, rax; this
0x180029a12  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180029a17  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180029a1c  cmp     al, r15b
  ... truncated ...
```
