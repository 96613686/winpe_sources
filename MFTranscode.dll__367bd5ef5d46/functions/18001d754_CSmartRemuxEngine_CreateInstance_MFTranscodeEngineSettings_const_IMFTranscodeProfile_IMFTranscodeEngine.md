# CSmartRemuxEngine::CreateInstance(MFTranscodeEngineSettings const &,IMFTranscodeProfile *,IMFTranscodeEngine * *)

- ea: `0x18001d754`
- end: `0x18001df48`
- name: `?CreateInstance@CSmartRemuxEngine@@SAJAEBUMFTranscodeEngineSettings@@PEAUIMFTranscodeProfile@@PEAPEAUIMFTranscodeEngine@@@Z`
- size: `2036`
- prototype: `__int64 __fastcall(const struct MFTranscodeEngineSettings *, struct IMFTranscodeProfile *, struct IMFTranscodeEngine **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bb40`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x180017074`
- `0x18001a330`
- `0x18001c050`
- `0x18001c280`
- `0x18001c9e8`
- `0x18001ca18`
- `0x18001d754`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d7bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d857`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d8fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d9a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001da79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001db38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001dbe4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001dc80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001dd2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ddf6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001de88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d7bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d857`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d8fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001d9a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001da79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001db38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001dbe4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001dc80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001dd2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ddf6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001de88`

## string_xrefs

- `0x18001d769`: `CSmartRemuxEngine::CreateInstance`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::CreateInstance(
        const struct MFTranscodeEngineSettings *a1,
        struct IMFTranscodeProfile *a2,
        struct IMFTranscodeEngine **a3)
{
  __int64 v6; // rdx
  __int64 *v7; // rcx
  HRESULT v8; // edi
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  struct IMFTranscodeProfile *v22; // rbx
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  CSmartRemuxEngine *v44; // rax
  __int64 v45; // rdx
  struct IMFTranscodeEngine *v46; // rax
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v54; // [rsp+70h] [rbp+40h] BYREF
  IMFTranscodeProfile *ppTranscodeProfile; // [rsp+80h] [rbp+50h] BYREF
  struct IMFTranscodeEngine *v56; // [rsp+88h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v54, "CSmartRemuxEngine::CreateInstance", 233);
  v56 = 0;
  ComSmartPtr<IMFTranscodeProfile>::ComSmartPtr<IMFTranscodeProfile>(&ppTranscodeProfile, a2);
  *a3 = 0;
  if ( !*((_DWORD *)a1 + 7) )
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSmartRemuxEngine::CreateInstance", 242, -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 15;
LABEL_134:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids,
        0,
        -2147024809);
      goto LABEL_135;
    }
    goto LABEL_135;
  }
  if ( *((_DWORD *)a1 + 4) )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
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
      if ( *((_DWORD *)v14 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v14, "CSmartRemuxEngine::CreateInstance", 248, -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 16;
      goto LABEL_134;
    }
    goto LABEL_135;
  }
  if ( !*(_QWORD *)a1 && !*((_QWORD *)a1 + 1) )
  {
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v17, "CSmartRemuxEngine::CreateInstance", 260, -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 17;
      goto LABEL_134;
    }
    goto LABEL_135;
  }
  v18 = *((_QWORD *)a1 + 1);
  if ( v18 && *(_QWORD *)a1 > v18 )
  {
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
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
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v21, "CSmartRemuxEngine::CreateInstance", 265, -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 18;
      goto LABEL_134;
    }
    goto LABEL_135;
  }
  if ( *(_QWORD *)a1 == 0x7FFFFFFFFFFFFFFFLL || v18 == 0x7FFFFFFFFFFFFFFFLL )
  {
    v50 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
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
      if ( *((_DWORD *)v52 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v52, "CSmartRemuxEngine::CreateInstance", 271, -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 19;
      goto LABEL_134;
    }
    goto LABEL_135;
  }
  v22 = ppTranscodeProfile;
  if ( ppTranscodeProfile )
  {
    v54 = 0;
    v8 = ((__int64 (__fastcall *)(IMFTranscodeProfile *, __int64 *))ppTranscodeProfile->lpVtbl->GetAudioAttributes)(
           ppTranscodeProfile,
           &v54);
    if ( v8 < 0 )
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
        if ( *((_DWORD *)v26 + 499) != v8 )
          CallStackContext::TraceFailure(v26, "CSmartRemuxEngine::CreateInstance", 279, v8);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_62;
      v27 = 20;
      goto LABEL_61;
    }
    if ( v54 )
    {
      v28 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
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
        if ( *((_DWORD *)v30 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v30, "CSmartRemuxEngine::CreateInstance", 282, -2147024809);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_62;
      v31 = 21;
      goto LABEL_74;
    }
    v8 = ((__int64 (__fastcall *)(struct IMFTranscodeProfile *, __int64 *))v22->lpVtbl->GetVideoAttributes)(v22, &v54);
    if ( v8 < 0 )
    {
      v33 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
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
        if ( *((_DWORD *)v35 + 499) != v8 )
          CallStackContext::TraceFailure(v35, "CSmartRemuxEngine::CreateInstance", 285, v8);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_62;
      v27 = 22;
LABEL_61:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, 0, v8);
LABEL_62:
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v54);
      goto LABEL_135;
    }
    if ( v54 )
    {
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
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
        if ( *((_DWORD *)v38 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v38, "CSmartRemuxEngine::CreateInstance", 288, -2147024809);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_62;
      v31 = 23;
LABEL_74:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v31,
        &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids,
        0,
        -2147024809);
      goto LABEL_62;
    }
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v54);
  }
  else
  {
    v8 = MFCreateTranscodeProfile(&ppTranscodeProfile);
    if ( v8 < 0 )
    {
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
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
        if ( *((_DWORD *)v42 + 499) != v8 )
          CallStackContext::TraceFailure(v42, "CSmartRemuxEngine::CreateInstance", 294, v8);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_135;
      v43 = 24;
LABEL_109:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v43, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, 0, v8);
      goto LABEL_135;
    }
    v22 = ppTranscodeProfile;
  }
  v44 = (CSmartRemuxEngine *)operator new(0x178u);
  if ( v44 )
  {
    v46 = CSmartRemuxEngine::CSmartRemuxEngine(v44, a1, v22);
    v56 = v46;
    if ( v46 )
    {
      v56 = 0;
      *a3 = v46;
      goto LABEL_135;
    }
  }
  v47 = (__int64 *)CallStackTracing::s_wpInstance;
  v8 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
    CallStackTracing::s_wpInstance = v48;
    if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
    {
      v47 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v47 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v47 + 8) )
  {
    v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
    if ( *((_DWORD *)v49 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v49, "CSmartRemuxEngine::CreateInstance", 298, -2147024882);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v43 = 25;
    goto LABEL_109;
  }
LABEL_135:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppTranscodeProfile);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v56);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v54);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d754  push    rbp
0x18001d756  push    rbx
0x18001d757  push    rsi
0x18001d758  push    rdi
0x18001d759  push    r12
0x18001d75b  push    r14
0x18001d75d  push    r15
0x18001d75f  mov     rbp, rsp
0x18001d762  sub     rsp, 30h
0x18001d766  mov     r14, r8
0x18001d769  lea     r12, aCsmartremuxeng_16; "CSmartRemuxEngine::CreateInstance"
0x18001d770  mov     rbx, rdx
0x18001d773  mov     rsi, rcx
0x18001d776  mov     rdx, r12; char *
0x18001d779  lea     rcx, [rbp+arg_0]; this
0x18001d77d  mov     r8d, 0E9h; int
0x18001d783  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001d788  xor     r15d, r15d
0x18001d78b  lea     rcx, [rbp+ppTranscodeProfile]
0x18001d78f  mov     rdx, rbx
0x18001d792  mov     [rbp+arg_18], r15
0x18001d796  call    ??0?$ComSmartPtr@UIMFTranscodeProfile@@@@QEAA@PEAUIMFTranscodeProfile@@@Z; ComSmartPtr<IMFTranscodeProfile>::ComSmartPtr<IMFTranscodeProfile>(IMFTranscodeProfile *)
0x18001d79b  mov     [r14], r15
0x18001d79e  cmp     [rsi+1Ch], r15d
0x18001d7a2  jnz     loc_18001D83A
0x18001d7a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d7af  mov     ebx, 80070057h
0x18001d7b4  mov     edi, ebx
0x18001d7b6  test    rcx, rcx
0x18001d7b9  jnz     short loc_18001D7FC
0x18001d7bb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d7c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d7c8  mov     rcx, rax
0x18001d7cb  test    rax, rax
0x18001d7ce  jz      short loc_18001D7EE
0x18001d7d0  mov     rax, [rax]
0x18001d7d3  mov     edx, 7F0h
0x18001d7d8  mov     rax, [rax+8]
0x18001d7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7e1  test    eax, eax
0x18001d7e3  jz      short loc_18001D7EE
0x18001d7e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d7ec  jmp     short loc_18001D7FC
0x18001d7ee  lea     rcx, qword_180069A90; this
0x18001d7f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d7fc  cmp     [rcx+8], r15b
0x18001d800  jz      short loc_18001D823
0x18001d802  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d807  cmp     [rax+7CCh], ebx
0x18001d80d  jz      short loc_18001D823
0x18001d80f  mov     r9d, ebx; int
0x18001d812  mov     r8d, 0F2h; int
0x18001d818  mov     rdx, r12; char *
0x18001d81b  mov     rcx, rax; this
0x18001d81e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d823  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001d828  cmp     al, 1
0x18001d82a  jb      loc_18001DF1C
0x18001d830  mov     edx, 0Fh
0x18001d835  jmp     loc_18001DEFE
0x18001d83a  cmp     [rsi+10h], r15d
0x18001d83e  jz      loc_18001D8D6
0x18001d844  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d84b  mov     ebx, 80070057h
0x18001d850  mov     edi, ebx
0x18001d852  test    rcx, rcx
0x18001d855  jnz     short loc_18001D898
0x18001d857  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d85d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d864  mov     rcx, rax
0x18001d867  test    rax, rax
0x18001d86a  jz      short loc_18001D88A
0x18001d86c  mov     rax, [rax]
0x18001d86f  mov     edx, 7F0h
0x18001d874  mov     rax, [rax+8]
0x18001d878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d87d  test    eax, eax
0x18001d87f  jz      short loc_18001D88A
0x18001d881  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d888  jmp     short loc_18001D898
0x18001d88a  lea     rcx, qword_180069A90; this
0x18001d891  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d898  cmp     [rcx+8], r15b
0x18001d89c  jz      short loc_18001D8BF
0x18001d89e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d8a3  cmp     [rax+7CCh], ebx
0x18001d8a9  jz      short loc_18001D8BF
0x18001d8ab  mov     r9d, ebx; int
0x18001d8ae  mov     r8d, 0F8h; int
0x18001d8b4  mov     rdx, r12; char *
0x18001d8b7  mov     rcx, rax; this
0x18001d8ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d8bf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001d8c4  cmp     al, 1
0x18001d8c6  jb      loc_18001DF1C
0x18001d8cc  mov     edx, 10h
0x18001d8d1  jmp     loc_18001DEFE
0x18001d8d6  cmp     [rsi], r15
0x18001d8d9  jnz     loc_18001D97B
0x18001d8df  cmp     [rsi+8], r15
0x18001d8e3  jnz     loc_18001D97B
0x18001d8e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d8f0  mov     ebx, 80070057h
0x18001d8f5  mov     edi, ebx
0x18001d8f7  test    rcx, rcx
0x18001d8fa  jnz     short loc_18001D93D
0x18001d8fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d902  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d909  mov     rcx, rax
0x18001d90c  test    rax, rax
0x18001d90f  jz      short loc_18001D92F
0x18001d911  mov     rax, [rax]
0x18001d914  mov     edx, 7F0h
0x18001d919  mov     rax, [rax+8]
0x18001d91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d922  test    eax, eax
0x18001d924  jz      short loc_18001D92F
0x18001d926  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d92d  jmp     short loc_18001D93D
0x18001d92f  lea     rcx, qword_180069A90; this
0x18001d936  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d93d  cmp     [rcx+8], r15b
0x18001d941  jz      short loc_18001D964
0x18001d943  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d948  cmp     [rax+7CCh], ebx
0x18001d94e  jz      short loc_18001D964
0x18001d950  mov     r9d, ebx; int
0x18001d953  mov     r8d, 104h; int
0x18001d959  mov     rdx, r12; char *
0x18001d95c  mov     rcx, rax; this
0x18001d95f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d964  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001d969  cmp     al, 1
0x18001d96b  jb      loc_18001DF1C
0x18001d971  mov     edx, 11h
0x18001d976  jmp     loc_18001DEFE
0x18001d97b  mov     rax, [rsi+8]
0x18001d97f  test    rax, rax
0x18001d982  jz      loc_18001DA23
0x18001d988  cmp     [rsi], rax
0x18001d98b  jle     loc_18001DA23
0x18001d991  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d998  mov     ebx, 80070057h
0x18001d99d  mov     edi, ebx
0x18001d99f  test    rcx, rcx
0x18001d9a2  jnz     short loc_18001D9E5
0x18001d9a4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001d9aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d9b1  mov     rcx, rax
0x18001d9b4  test    rax, rax
0x18001d9b7  jz      short loc_18001D9D7
0x18001d9b9  mov     rax, [rax]
0x18001d9bc  mov     edx, 7F0h
0x18001d9c1  mov     rax, [rax+8]
0x18001d9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9ca  test    eax, eax
0x18001d9cc  jz      short loc_18001D9D7
0x18001d9ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d9d5  jmp     short loc_18001D9E5
0x18001d9d7  lea     rcx, qword_180069A90; this
0x18001d9de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d9e5  cmp     [rcx+8], r15b
0x18001d9e9  jz      short loc_18001DA0C
0x18001d9eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d9f0  cmp     [rax+7CCh], ebx
0x18001d9f6  jz      short loc_18001DA0C
0x18001d9f8  mov     r9d, ebx; int
0x18001d9fb  mov     r8d, 109h; int
0x18001da01  mov     rdx, r12; char *
0x18001da04  mov     rcx, rax; this
0x18001da07  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001da0c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001da11  cmp     al, 1
0x18001da13  jb      loc_18001DF1C
0x18001da19  mov     edx, 12h
0x18001da1e  jmp     loc_18001DEFE
0x18001da23  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18001da2d  cmp     [rsi], rcx
0x18001da30  jge     loc_18001DE75
0x18001da36  cmp     rax, rcx
0x18001da39  jge     loc_18001DE75
0x18001da3f  mov     rbx, [rbp+ppTranscodeProfile]
0x18001da43  test    rbx, rbx
0x18001da46  jz      loc_18001DD0D
0x18001da4c  mov     [rbp+arg_0], r15
0x18001da50  lea     rdx, [rbp+arg_0]
0x18001da54  mov     rax, [rbx]
0x18001da57  mov     rcx, rbx
0x18001da5a  mov     rax, [rax+20h]
0x18001da5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da63  mov     edi, eax
0x18001da65  test    eax, eax
0x18001da67  jns     loc_18001DB1B
0x18001da6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001da74  test    rcx, rcx
0x18001da77  jnz     short loc_18001DABA
0x18001da79  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001da7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001da86  mov     rcx, rax
0x18001da89  test    rax, rax
0x18001da8c  jz      short loc_18001DAAC
0x18001da8e  mov     rax, [rax]
0x18001da91  mov     edx, 7F0h
0x18001da96  mov     rax, [rax+8]
0x18001da9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da9f  test    eax, eax
0x18001daa1  jz      short loc_18001DAAC
0x18001daa3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001daaa  jmp     short loc_18001DABA
0x18001daac  lea     rcx, qword_180069A90; this
0x18001dab3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001daba  cmp     [rcx+8], r15b
0x18001dabe  jz      short loc_18001DAE1
0x18001dac0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001dac5  cmp     [rax+7CCh], edi
0x18001dacb  jz      short loc_18001DAE1
0x18001dacd  mov     r9d, edi; int
0x18001dad0  mov     r8d, 117h; int
0x18001dad6  mov     rdx, r12; char *
0x18001dad9  mov     rcx, rax; this
0x18001dadc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001dae1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001dae6  cmp     al, 1
0x18001dae8  jb      short loc_18001DB0D
0x18001daea  mov     edx, 14h
0x18001daef  mov     [rsp+30h+var_10], edi
0x18001daf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dafa  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x18001db01  xor     r9d, r9d
0x18001db04  mov     rcx, [rcx+10h]
0x18001db08  call    WPP_SF_qd
0x18001db0d  lea     rcx, [rbp+arg_0]
0x18001db11  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001db16  jmp     loc_18001DF1C
0x18001db1b  cmp     [rbp+arg_0], r15
0x18001db1f  jz      loc_18001DBBB
0x18001db25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001db2c  mov     ebx, 80070057h
0x18001db31  mov     edi, ebx
0x18001db33  test    rcx, rcx
0x18001db36  jnz     short loc_18001DB79
0x18001db38  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001db3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001db45  mov     rcx, rax
0x18001db48  test    rax, rax
0x18001db4b  jz      short loc_18001DB6B
0x18001db4d  mov     rax, [rax]
0x18001db50  mov     edx, 7F0h
0x18001db55  mov     rax, [rax+8]
0x18001db59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db5e  test    eax, eax
0x18001db60  jz      short loc_18001DB6B
0x18001db62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001db69  jmp     short loc_18001DB79
0x18001db6b  lea     rcx, qword_180069A90; this
0x18001db72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001db79  cmp     [rcx+8], r15b
0x18001db7d  jz      short loc_18001DBA0
0x18001db7f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001db84  cmp     [rax+7CCh], ebx
0x18001db8a  jz      short loc_18001DBA0
0x18001db8c  mov     r9d, ebx; int
0x18001db8f  mov     r8d, 11Ah; int
0x18001db95  mov     rdx, r12; char *
0x18001db98  mov     rcx, rax; this
0x18001db9b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001dba0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001dba5  cmp     al, 1
0x18001dba7  jb      loc_18001DB0D
0x18001dbad  mov     edx, 15h
0x18001dbb2  mov     [rsp+30h+var_10], ebx
0x18001dbb6  jmp     loc_18001DAF3
0x18001dbbb  mov     rax, [rbx]
0x18001dbbe  lea     rdx, [rbp+arg_0]
0x18001dbc2  mov     rcx, rbx
0x18001dbc5  mov     rax, [rax+30h]
0x18001dbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbce  mov     edi, eax
0x18001dbd0  test    eax, eax
0x18001dbd2  jns     loc_18001DC63
0x18001dbd8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dbdf  test    rcx, rcx
0x18001dbe2  jnz     short loc_18001DC25
0x18001dbe4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001dbea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dbf1  mov     rcx, rax
0x18001dbf4  test    rax, rax
0x18001dbf7  jz      short loc_18001DC17
0x18001dbf9  mov     rax, [rax]
0x18001dbfc  mov     edx, 7F0h
0x18001dc01  mov     rax, [rax+8]
0x18001dc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc0a  test    eax, eax
0x18001dc0c  jz      short loc_18001DC17
0x18001dc0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dc15  jmp     short loc_18001DC25
0x18001dc17  lea     rcx, qword_180069A90; this
0x18001dc1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dc25  cmp     [rcx+8], r15b
0x18001dc29  jz      short loc_18001DC4C
  ... truncated ...
```
