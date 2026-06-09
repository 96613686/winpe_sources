# CTranscodeProfileAdjuster::AdjustSelectedStreams(CTPtrArray<IMFStreamDescriptor,20> const &,IMFTranscodeProfile *,CTPtrArray<IMFStreamDescriptor,20> * *,IMFTranscodeProfile * *)

- ea: `0x180039a70`
- end: `0x18003ace0`
- name: `?AdjustSelectedStreams@CTranscodeProfileAdjuster@@UEAAJAEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@PEAUIMFTranscodeProfile@@PEAPEAV2@PEAPEAU3@@Z`
- size: `4720`
- prototype: `__int64 __usercall@<rax>(CTranscodeProfileAdjuster *this@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a940`
- `0x180017074`
- `0x18001a330`
- `0x18001c050`
- `0x18001c280`
- `0x1800387d0`
- `0x180038974`
- `0x180038a10`
- `0x180038b18`
- `0x180038e30`
- `0x180039274`
- `0x180039a70`
- `0x18003b58c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039b00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039c9b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039d5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039e0d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039eb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039f63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a010`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a0bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a180`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a24b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a303`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a3b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a459`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a509`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a5bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a672`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a7f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a8a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a94d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a9fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003aaa9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ab4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039b00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039bd8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039c9b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039d5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039e0d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039eb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039f63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a010`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a0bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a180`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a24b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a303`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a3b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a459`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a509`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a5bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a672`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a7f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a8a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a94d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003a9fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003aaa9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ab4f`
- `MFPlat!MFCreateAttributes` at `0x180039e97`
- `MFPlat!MFCreateAttributes` at `0x18003a43d`
- `MFPlat!MFCreateAttributes` at `0x18003a931`
- `MFPlat!MFCreateAttributes` at `0x180039e97`
- `MFPlat!MFCreateAttributes` at `0x18003a43d`
- `MFPlat!MFCreateAttributes` at `0x18003a931`

## pseudocode

```c
__int64 __fastcall CTranscodeProfileAdjuster::AdjustSelectedStreams(
        CTranscodeProfileAdjuster *this,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        IMFTranscodeProfile **a5)
{
  IMFTranscodeProfile **v9; // r15
  void *v10; // rdi
  __int64 v11; // rdx
  HRESULT MatchedSrcStream; // ebx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  void *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
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
  unsigned int v57; // r15d
  struct IMFAttributes *v58; // rbx
  struct IMFStreamDescriptor *v59; // rax
  __int64 v60; // rdx
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 v69; // rdx
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 v73; // rdx
  __int64 *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 v77; // rdx
  __int64 *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  struct IMFAttributes *v81; // rbx
  struct IMFStreamDescriptor *v82; // rax
  __int64 v83; // rdx
  __int64 *v84; // rcx
  CallStackTracing *v85; // rax
  struct CallStackContext *v86; // rax
  struct IMFAttributes *v87; // rbx
  struct IMFStreamDescriptor *v88; // rdx
  __int64 v89; // rdx
  __int64 *v90; // rcx
  CallStackTracing *v91; // rax
  struct CallStackContext *v92; // rax
  IMFTranscodeProfile *v93; // rsi
  __int64 v94; // rdx
  __int64 *v95; // rcx
  CallStackTracing *v96; // rax
  struct CallStackContext *v97; // rax
  __int64 v98; // rdx
  __int64 v99; // rdx
  __int64 *v100; // rcx
  CallStackTracing *v101; // rax
  struct CallStackContext *v102; // rax
  __int64 v103; // rdx
  __int64 *v104; // rcx
  CallStackTracing *v105; // rax
  struct CallStackContext *v106; // rax
  __int64 v107; // rdx
  __int64 *v108; // rcx
  CallStackTracing *v109; // rax
  struct CallStackContext *v110; // rax
  __int64 v111; // rdx
  __int64 *v112; // rcx
  CallStackTracing *v113; // rax
  struct CallStackContext *v114; // rax
  __int64 v115; // rdx
  __int64 *v116; // rcx
  CallStackTracing *v117; // rax
  struct CallStackContext *v118; // rax
  __int64 *v119; // rcx
  CallStackTracing *v120; // rax
  struct CallStackContext *v121; // rax
  IMFTranscodeProfile *ppTranscodeProfile; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v124; // [rsp+38h] [rbp-48h] BYREF
  struct IMFAttributes *v125; // [rsp+40h] [rbp-40h] BYREF
  IMFAttributes *v126; // [rsp+48h] [rbp-38h] BYREF
  __int64 v127; // [rsp+50h] [rbp-30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+58h] [rbp-28h] BYREF
  __int64 v129; // [rsp+60h] [rbp-20h] BYREF
  IMFAttributes *v130; // [rsp+68h] [rbp-18h] BYREF
  int v131[4]; // [rsp+70h] [rbp-10h] BYREF
  int v132; // [rsp+C0h] [rbp+40h] BYREF
  UINT32 cInitialSize; // [rsp+D8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v132,
    "CTranscodeProfileAdjuster::AdjustSelectedStreams",
    624);
  v9 = a5;
  v10 = 0;
  *a4 = 0;
  v127 = 0;
  *v9 = 0;
  ppMFAttributes = 0;
  v125 = 0;
  v126 = 0;
  v129 = 0;
  v130 = 0;
  ppTranscodeProfile = 0;
  v132 = 0;
  v124 = 0;
  v131[0] = 0;
  cInitialSize = 0;
  MatchedSrcStream = MFCreateTranscodeProfile(&ppTranscodeProfile);
  if ( MatchedSrcStream < 0 )
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != MatchedSrcStream )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CTranscodeProfileAdjuster::AdjustSelectedStreams",
          643,
          MatchedSrcStream);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_276;
    v16 = 99;
    goto LABEL_12;
  }
  v17 = operator new(0xD0u);
  if ( !v17 || (v10 = (void *)CTPtrArray<IMFStreamDescriptor,20>::CTPtrArray<IMFStreamDescriptor,20>(v17)) == 0 )
  {
    v119 = (__int64 *)CallStackTracing::s_wpInstance;
    MatchedSrcStream = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v120 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
      CallStackTracing::s_wpInstance = v120;
      if ( v120 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v120 + 8LL))(v120, 2032) )
      {
        v119 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v119 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v119 + 8) )
    {
      v121 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v119);
      if ( *((_DWORD *)v121 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v121, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 646, -2147024882);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_276;
    v32 = 100;
LABEL_275:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v32,
      &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids,
      this,
      -2147024882);
    goto LABEL_276;
  }
  MatchedSrcStream = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 32LL))(a3, &v127);
  if ( MatchedSrcStream < 0 )
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
      if ( *((_DWORD *)v22 + 499) != MatchedSrcStream )
        CallStackContext::TraceFailure(v22, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 648, MatchedSrcStream);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_276;
    v16 = 101;
    goto LABEL_12;
  }
  if ( v127 )
  {
    MatchedSrcStream = CTranscodeProfileAdjuster::FindMatchedSrcStream(
                         (_DWORD)this,
                         (unsigned int)&MFMediaType_Audio,
                         a2,
                         (unsigned int)&v132,
                         (__int64)&v124);
    if ( MatchedSrcStream < 0 )
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
        if ( *((_DWORD *)v26 + 499) != MatchedSrcStream )
          CallStackContext::TraceFailure(v26, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 651, MatchedSrcStream);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_276;
      v16 = 102;
      goto LABEL_12;
    }
    if ( v132 )
    {
      v27 = CTPtrArray<IMFStreamDescriptor,20>::operator[](a2, v124);
      if ( !(unsigned int)CTPtrArray<IMFStreamDescriptor,20>::Add(v10, v27, v131) )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
        MatchedSrcStream = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
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
          if ( *((_DWORD *)v31 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v31, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 656, -2147024882);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_276;
        v32 = 103;
        goto LABEL_275;
      }
      MatchedSrcStream = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v127 + 240LL))(v127, &cInitialSize);
      if ( MatchedSrcStream < 0 )
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != MatchedSrcStream )
            CallStackContext::TraceFailure(
              v36,
              "CTranscodeProfileAdjuster::AdjustSelectedStreams",
              659,
              MatchedSrcStream);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_276;
        v16 = 104;
        goto LABEL_12;
      }
      MatchedSrcStream = MFCreateAttributes(&ppMFAttributes, cInitialSize);
      if ( MatchedSrcStream < 0 )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
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
          if ( *((_DWORD *)v40 + 499) != MatchedSrcStream )
            CallStackContext::TraceFailure(
              v40,
              "CTranscodeProfileAdjuster::AdjustSelectedStreams",
              660,
              MatchedSrcStream);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_276;
        v16 = 105;
        goto LABEL_12;
      }
      MatchedSrcStream = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v127 + 256LL))(
                           v127,
                           ppMFAttributes);
      if ( MatchedSrcStream < 0 )
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
          if ( *((_DWORD *)v44 + 499) != MatchedSrcStream )
            CallStackContext::TraceFailure(
              v44,
              "CTranscodeProfileAdjuster::AdjustSelectedStreams",
              661,
              MatchedSrcStream);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_276;
        v16 = 106;
        goto LABEL_12;
      }
      MatchedSrcStream = ((__int64 (__fastcall *)(IMFTranscodeProfile *, IMFAttributes *))ppTranscodeProfile->lpVtbl->SetAudioAttributes)(
                           ppTranscodeProfile,
                           ppMFAttributes);
      if ( MatchedSrcStream < 0 )
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
          if ( *((_DWORD *)v48 + 499) != MatchedSrcStream )
            CallStackContext::TraceFailure(
              v48,
              "CTranscodeProfileAdjuster::AdjustSelectedStreams",
              662,
              MatchedSrcStream);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_276;
        v16 = 107;
        goto LABEL_12;
      }
    }
  }
  MatchedSrcStream = (*(__int64 (__fastcall **)(__int64, struct IMFAttributes **))(*(_QWORD *)a3 + 48LL))(a3, &v125);
  if ( MatchedSrcStream < 0 )
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
      if ( *((_DWORD *)v52 + 499) != MatchedSrcStream )
        CallStackContext::TraceFailure(v52, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 666, MatchedSrcStream);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_276;
    v16 = 108;
    goto LABEL_12;
  }
  if ( !v125 )
    goto LABEL_208;
  MatchedSrcStream = CTranscodeProfileAdjuster::FindMatchedSrcStream(
                       (_DWORD)this,
                       (unsigned int)&MFMediaType_Video,
                       a2,
                       (unsigned int)&v132,
                       (__int64)&v124);
  if ( MatchedSrcStream < 0 )
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
      if ( *((_DWORD *)v56 + 499) != MatchedSrcStream )
        CallStackContext::TraceFailure(v56, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 669, MatchedSrcStream);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_276;
    v16 = 109;
    goto LABEL_12;
  }
  if ( v132 )
  {
    v57 = v124;
    v58 = v125;
    v132 = 0;
    v59 = (struct IMFStreamDescriptor *)CTPtrArray<IMFStreamDescriptor,20>::operator[](a2, v124);
    MatchedSrcStream = CTranscodeProfileAdjuster::AdjustSourceRotation(this, v59, v58);
    if ( MatchedSrcStream < 0 )
    {
      v61 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60);
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
        if ( *((_DWORD *)v63 + 499) != MatchedSrcStream )
          CallStackContext::TraceFailure(v63, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 674, MatchedSrcStream);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_276;
      v16 = 110;
      goto LABEL_12;
    }
    v64 = CTPtrArray<IMFStreamDescriptor,20>::operator[](a2, v57);
    if ( !(unsigned int)CTPtrArray<IMFStreamDescriptor,20>::Add(v10, v64, &v132) )
    {
      v66 = (__int64 *)CallStackTracing::s_wpInstance;
      MatchedSrcStream = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v65);
        CallStackTracing::s_wpInstance = v67;
        if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
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
        if ( *((_DWORD *)v68 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v68, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 678, -2147024882);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_276;
      v32 = 111;
      goto LABEL_275;
    }
    MatchedSrcStream = ((__int64 (__fastcall *)(struct IMFAttributes *, UINT32 *))v125->lpVtbl->GetCount)(
                         v125,
                         &cInitialSize);
    if ( MatchedSrcStream < 0 )
    {
      v70 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v69);
        CallStackTracing::s_wpInstance = v71;
        if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
        {
          v70 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v70 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v70 + 8) )
      {
        v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
        if ( *((_DWORD *)v72 + 499) != MatchedSrcStream )
          CallStackContext::TraceFailure(v72, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 681, MatchedSrcStream);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_276;
      v16 = 112;
      goto LABEL_12;
    }
    MatchedSrcStream = MFCreateAttributes(&v126, cInitialSize);
    if ( MatchedSrcStream < 0 )
    {
      v74 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v73);
        CallStackTracing::s_wpInstance = v75;
        if ( v75 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
        {
          v74 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v74 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v74 + 8) )
      {
        v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
        if ( *((_DWORD *)v76 + 499) != MatchedSrcStream )
          CallStackContext::TraceFailure(v76, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 682, MatchedSrcStream);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_276;
      v16 = 113;
      goto LABEL_12;
    }
    MatchedSrcStream = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))v125->lpVtbl->CopyAllItems)(
                         v125,
                         v126);
    if ( MatchedSrcStream < 0 )
    {
      v78 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v77);
        CallStackTracing::s_wpInstance = v79;
        if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
        {
          v78 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v78 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v78 + 8) )
      {
        v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
        if ( *((_DWORD *)v80 + 499) != MatchedSrcStream )
          CallStackContext::TraceFailure(v80, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 683, MatchedSrcStream);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_276;
      v16 = 114;
      goto LABEL_12;
    }
    v81 = v126;
    v82 = (struct IMFStreamDescriptor *)CTPtrArray<IMFStreamDescriptor,20>::operator[](a2, v57);
    MatchedSrcStream = CTranscodeProfileAdjuster::AdjustFrameRateIfNeeded(this, v82, v81);
    if ( MatchedSrcStream < 0 )
    {
      v84 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v85 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v83);
        CallStackTracing::s_wpInstance = v85;
        if ( v85 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v85 + 8LL))(v85, 2032) )
        {
          v84 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v84 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v84 + 8) )
      {
        v86 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v84);
        if ( *((_DWORD *)v86 + 499) != MatchedSrcStream )
          CallStackContext::TraceFailure(v86, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 696, MatchedSrcStream);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_276;
      v16 = 115;
      goto LABEL_12;
    }
    v87 = v126;
    CTPtrArray<IMFStreamDescriptor,20>::operator[](a2, v57);
    MatchedSrcStream = CTranscodeProfileAdjuster::AdjustInterlaceModeIfNeeded(this, v88, v87);
    if ( MatchedSrcStream < 0 )
    {
      v90 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v91 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v89);
        CallStackTracing::s_wpInstance = v91;
        if ( v91 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v91 + 8LL))(v91, 2032) )
        {
          v90 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v90 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v90 + 8) )
      {
        v92 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v90);
        if ( *((_DWORD *)v92 + 499) != MatchedSrcStream )
          CallStackContext::TraceFailure(v92, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 702, MatchedSrcStream);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_276;
      v16 = 116;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids,
        this,
        MatchedSrcStream);
LABEL_276:
      v93 = ppTranscodeProfile;
      goto LABEL_277;
    }
    v93 = ppTranscodeProfile;
    MatchedSrcStream = ((__int64 (__fastcall *)(IMFTranscodeProfile *, IMFAttributes *))ppTranscodeProfile->lpVtbl->SetVideoAttributes)(
                         ppTranscodeProfile,
                         v126);
    if ( MatchedSrcStream < 0 )
    {
      v95 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v96 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v94);
        CallStackTracing::s_wpInstance = v96;
        if ( v96 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v96 + 8LL))(v96, 2032) )
        {
          v95 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v95 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v95 + 8) )
      {
        v97 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v95);
        if ( *((_DWORD *)v97 + 499) != MatchedSrcStream )
          CallStackContext::TraceFailure(v97, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 704, MatchedSrcStream);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v98 = 117;
LABEL_206:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v98,
          &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids,
          this,
          MatchedSrcStream);
        goto LABEL_277;
      }
      goto LABEL_277;
    }
    v9 = a5;
  }
  else
  {
LABEL_208:
    v93 = ppTranscodeProfile;
  }
  MatchedSrcStream = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 64LL))(a3, &v129);
  if ( MatchedSrcStream >= 0 )
  {
    MatchedSrcStream = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v129 + 240LL))(v129, &cInitialSize);
    if ( MatchedSrcStream >= 0 )
    {
      MatchedSrcStream = MFCreateAttributes(&v130, cInitialSize);
      if ( MatchedSrcStream >= 0 )
      {
        MatchedSrcStream = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v129 + 256LL))(v129, v130);
        if ( MatchedSrcStream >= 0 )
        {
          MatchedSrcStream = ((__int64 (__fastcall *)(IMFTranscodeProfile *, IMFAttributes *))v93->lpVtbl->SetContainerAttributes)(
                               v93,
                               v130);
          if ( MatchedSrcStream >= 0 )
          {
            *a4 = v10;
            v10 = 0;
            *v9 = v93;
            v93 = 0;
            goto LABEL_277;
          }
          v116 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v117 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v115);
            CallStackTracing::s_wpInstance = v117;
            if ( v117
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v117 + 8LL))(v117, 2032) )
            {
              v116 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v116 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v116 + 8) )
          {
            v118 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v116);
            if ( *((_DWORD *)v118 + 499) != MatchedSrcStream )
              CallStackContext::TraceFailure(
                v118,
                "CTranscodeProfileAdjuster::AdjustSelectedStreams",
                712,
                MatchedSrcStream);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v98 = 122;
            goto LABEL_206;
          }
        }
        else
        {
          v112 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v113 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v111);
            CallStackTracing::s_wpInstance = v113;
            if ( v113
              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v113 + 8LL))(v113, 2032) )
            {
              v112 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v112 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v112 + 8) )
          {
            v114 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v112);
            if ( *((_DWORD *)v114 + 499) != MatchedSrcStream )
              CallStackContext::TraceFailure(
                v114,
                "CTranscodeProfileAdjuster::AdjustSelectedStreams",
                711,
                MatchedSrcStream);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v98 = 121;
            goto LABEL_206;
          }
        }
      }
      else
      {
        v108 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v109 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v107);
          CallStackTracing::s_wpInstance = v109;
          if ( v109 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v109 + 8LL))(v109, 2032) )
          {
            v108 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v108 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v108 + 8) )
        {
          v110 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v108);
          if ( *((_DWORD *)v110 + 499) != MatchedSrcStream )
            CallStackContext::TraceFailure(
              v110,
              "CTranscodeProfileAdjuster::AdjustSelectedStreams",
              710,
              MatchedSrcStream);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v98 = 120;
          goto LABEL_206;
        }
      }
    }
    else
    {
      v104 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v105 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v103);
        CallStackTracing::s_wpInstance = v105;
        if ( v105 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v105 + 8LL))(v105, 2032) )
        {
          v104 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v104 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v104 + 8) )
      {
        v106 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v104);
        if ( *((_DWORD *)v106 + 499) != MatchedSrcStream )
          CallStackContext::TraceFailure(
            v106,
            "CTranscodeProfileAdjuster::AdjustSelectedStreams",
            709,
            MatchedSrcStream);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v98 = 119;
        goto LABEL_206;
      }
    }
  }
  else
  {
    v100 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v101 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v99);
      CallStackTracing::s_wpInstance = v101;
      if ( v101 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v101 + 8LL))(v101, 2032) )
      {
        v100 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v100 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v100 + 8) )
    {
      v102 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v100);
      if ( *((_DWORD *)v102 + 499) != MatchedSrcStream )
        CallStackContext::TraceFailure(v102, "CTranscodeProfileAdjuster::AdjustSelectedStreams", 708, MatchedSrcStream);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v98 = 118;
      goto LABEL_206;
    }
  }
LABEL_277:
  if ( v127 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
    v127 = 0;
  }
  if ( ppMFAttributes )
  {
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
    ppMFAttributes = 0;
  }
  if ( v125 )
  {
    ((void (__fastcall *)(struct IMFAttributes *))v125->lpVtbl->Release)(v125);
    v125 = 0;
  }
  if ( v126 )
  {
    ((void (__fastcall *)(IMFAttributes *))v126->lpVtbl->Release)(v126);
    v126 = 0;
  }
  if ( v129 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v129 + 16LL))(v129);
    v129 = 0;
  }
  if ( v130 )
  {
    ((void (__fastcall *)(IMFAttributes *))v130->lpVtbl->Release)(v130);
    v130 = 0;
  }
  if ( v10 )
    CTPtrArray<IMFStreamDescriptor,20>::`scalar deleting destructor'(v10);
  if ( v93 )
    ((void (__fastcall *)(IMFTranscodeProfile *))v93->lpVtbl->Release)(v93);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v132);
  return (unsigned int)MatchedSrcStream;
}

```

## disassembly

```asm
0x180039a70  mov     [rsp-38h+arg_8], rbx
0x180039a75  push    rbp
0x180039a76  push    rsi
0x180039a77  push    rdi
0x180039a78  push    r12
0x180039a7a  push    r13
0x180039a7c  push    r14
0x180039a7e  push    r15
0x180039a80  mov     rbp, rsp
0x180039a83  sub     rsp, 80h
0x180039a8a  mov     r12, r8
0x180039a8d  mov     rsi, rdx
0x180039a90  mov     r14, rcx
0x180039a93  lea     rdx, aCtranscodeprof_16; "CTranscodeProfileAdjuster::AdjustSelect"...
0x180039a9a  mov     r8d, 270h; int
0x180039aa0  lea     rcx, [rbp+arg_0]; this
0x180039aa4  mov     r13, r9
0x180039aa7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180039aac  mov     r15, [rbp+arg_20]
0x180039ab0  lea     rcx, [rbp+ppTranscodeProfile]; ppTranscodeProfile
0x180039ab4  xor     edi, edi
0x180039ab6  mov     [r13+0], rdi
0x180039aba  mov     [rbp+var_30], rdi
0x180039abe  mov     [r15], rdi
0x180039ac1  mov     [rbp+ppMFAttributes], rdi
0x180039ac5  mov     [rbp+var_40], rdi
0x180039ac9  mov     [rbp+var_38], rdi
0x180039acd  mov     [rbp+var_20], rdi
0x180039ad1  mov     [rbp+var_18], rdi
0x180039ad5  mov     [rbp+ppTranscodeProfile], rdi
0x180039ad9  mov     [rbp+arg_0], edi
0x180039adc  mov     [rbp+var_48], edi
0x180039adf  mov     [rbp+var_10], edi
0x180039ae2  mov     [rbp+cInitialSize], edi
0x180039ae5  call    MFCreateTranscodeProfile
0x180039aea  mov     ebx, eax
0x180039aec  test    eax, eax
0x180039aee  jns     loc_180039B87
0x180039af4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039afb  test    rcx, rcx
0x180039afe  jnz     short loc_180039B41
0x180039b00  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039b06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039b0d  mov     rcx, rax
0x180039b10  test    rax, rax
0x180039b13  jz      short loc_180039B33
0x180039b15  mov     rax, [rax]
0x180039b18  mov     edx, 7F0h
0x180039b1d  mov     rax, [rax+8]
0x180039b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b26  test    eax, eax
0x180039b28  jz      short loc_180039B33
0x180039b2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039b31  jmp     short loc_180039B41
0x180039b33  lea     rcx, qword_180069A90; this
0x180039b3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039b41  cmp     [rcx+8], dil
0x180039b45  jz      short loc_180039B6C
0x180039b47  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039b4c  cmp     [rax+7CCh], ebx
0x180039b52  jz      short loc_180039B6C
0x180039b54  mov     r9d, ebx; int
0x180039b57  lea     rdx, aCtranscodeprof_16; "CTranscodeProfileAdjuster::AdjustSelect"...
0x180039b5e  mov     r8d, 283h; int
0x180039b64  mov     rcx, rax; this
0x180039b67  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039b6c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180039b71  cmp     al, 1
0x180039b73  jb      loc_18003ABE7
0x180039b79  mov     edx, 63h ; 'c'
0x180039b7e  mov     dword ptr [rsp+80h+var_60], ebx
0x180039b82  jmp     loc_18003ABCD
0x180039b87  mov     ecx, 0D0h; Size
0x180039b8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039b91  test    rax, rax
0x180039b94  jz      loc_18003AB3C
0x180039b9a  mov     rcx, rax
0x180039b9d  call    ??0?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEAA@XZ; CTPtrArray<IMFStreamDescriptor,20>::CTPtrArray<IMFStreamDescriptor,20>(void)
0x180039ba2  mov     rdi, rax
0x180039ba5  test    rax, rax
0x180039ba8  jz      loc_18003AB3C
0x180039bae  mov     rax, [r12]
0x180039bb2  lea     rdx, [rbp+var_30]
0x180039bb6  mov     rcx, r12
0x180039bb9  mov     rax, [rax+20h]
0x180039bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bc2  mov     ebx, eax
0x180039bc4  test    eax, eax
0x180039bc6  jns     loc_180039C5B
0x180039bcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039bd3  test    rcx, rcx
0x180039bd6  jnz     short loc_180039C19
0x180039bd8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039bde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039be5  mov     rcx, rax
0x180039be8  test    rax, rax
0x180039beb  jz      short loc_180039C0B
0x180039bed  mov     rax, [rax]
0x180039bf0  mov     edx, 7F0h
0x180039bf5  mov     rax, [rax+8]
0x180039bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bfe  test    eax, eax
0x180039c00  jz      short loc_180039C0B
0x180039c02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039c09  jmp     short loc_180039C19
0x180039c0b  lea     rcx, qword_180069A90; this
0x180039c12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039c19  cmp     byte ptr [rcx+8], 0
0x180039c1d  jz      short loc_180039C44
0x180039c1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039c24  cmp     [rax+7CCh], ebx
0x180039c2a  jz      short loc_180039C44
0x180039c2c  mov     r9d, ebx; int
0x180039c2f  lea     rdx, aCtranscodeprof_16; "CTranscodeProfileAdjuster::AdjustSelect"...
0x180039c36  mov     r8d, 288h; int
0x180039c3c  mov     rcx, rax; this
0x180039c3f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039c44  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180039c49  cmp     al, 1
0x180039c4b  jb      loc_18003ABE7
0x180039c51  mov     edx, 65h ; 'e'
0x180039c56  jmp     loc_180039B7E
0x180039c5b  cmp     [rbp+var_30], 0
0x180039c60  jz      loc_18003A093
0x180039c66  lea     rax, [rbp+var_48]
0x180039c6a  mov     r8, rsi
0x180039c6d  lea     r9, [rbp+arg_0]
0x180039c71  mov     [rsp+80h+var_60], rax
0x180039c76  lea     rdx, MFMediaType_Audio
0x180039c7d  mov     rcx, r14
0x180039c80  call    ?FindMatchedSrcStream@CTranscodeProfileAdjuster@@IEAAJAEBU_GUID@@AEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@PEAHPEAK@Z; CTranscodeProfileAdjuster::FindMatchedSrcStream(_GUID const &,CTPtrArray<IMFStreamDescriptor,20> const &,int *,ulong *)
0x180039c85  mov     ebx, eax
0x180039c87  test    eax, eax
0x180039c89  jns     loc_180039D1E
0x180039c8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039c96  test    rcx, rcx
0x180039c99  jnz     short loc_180039CDC
0x180039c9b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039ca1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039ca8  mov     rcx, rax
0x180039cab  test    rax, rax
0x180039cae  jz      short loc_180039CCE
0x180039cb0  mov     rax, [rax]
0x180039cb3  mov     edx, 7F0h
0x180039cb8  mov     rax, [rax+8]
0x180039cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cc1  test    eax, eax
0x180039cc3  jz      short loc_180039CCE
0x180039cc5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039ccc  jmp     short loc_180039CDC
0x180039cce  lea     rcx, qword_180069A90; this
0x180039cd5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039cdc  cmp     byte ptr [rcx+8], 0
0x180039ce0  jz      short loc_180039D07
0x180039ce2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039ce7  cmp     [rax+7CCh], ebx
0x180039ced  jz      short loc_180039D07
0x180039cef  mov     r9d, ebx; int
0x180039cf2  lea     rdx, aCtranscodeprof_16; "CTranscodeProfileAdjuster::AdjustSelect"...
0x180039cf9  mov     r8d, 28Bh; int
0x180039cff  mov     rcx, rax; this
0x180039d02  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039d07  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180039d0c  cmp     al, 1
0x180039d0e  jb      loc_18003ABE7
0x180039d14  mov     edx, 66h ; 'f'
0x180039d19  jmp     loc_180039B7E
0x180039d1e  cmp     [rbp+arg_0], 0
0x180039d22  jz      loc_18003A093
0x180039d28  mov     edx, [rbp+var_48]
0x180039d2b  mov     rcx, rsi
0x180039d2e  call    ??A?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEBAPEAUIMFStreamDescriptor@@K@Z; CTPtrArray<IMFStreamDescriptor,20>::operator[](ulong)
0x180039d33  mov     rdx, rax
0x180039d36  lea     r8, [rbp+var_10]
0x180039d3a  mov     rcx, rdi
0x180039d3d  call    ?Add@?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEAAHPEAUIMFStreamDescriptor@@PEAK@Z; CTPtrArray<IMFStreamDescriptor,20>::Add(IMFStreamDescriptor *,ulong *)
0x180039d42  test    eax, eax
0x180039d44  jnz     loc_180039DE0
0x180039d4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039d51  mov     esi, 8007000Eh
0x180039d56  mov     ebx, esi
0x180039d58  test    rcx, rcx
0x180039d5b  jnz     short loc_180039D9E
0x180039d5d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039d63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039d6a  mov     rcx, rax
0x180039d6d  test    rax, rax
0x180039d70  jz      short loc_180039D90
0x180039d72  mov     rax, [rax]
0x180039d75  mov     edx, 7F0h
0x180039d7a  mov     rax, [rax+8]
0x180039d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d83  test    eax, eax
0x180039d85  jz      short loc_180039D90
0x180039d87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039d8e  jmp     short loc_180039D9E
0x180039d90  lea     rcx, qword_180069A90; this
0x180039d97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039d9e  cmp     byte ptr [rcx+8], 0
0x180039da2  jz      short loc_180039DC9
0x180039da4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039da9  cmp     [rax+7CCh], esi
0x180039daf  jz      short loc_180039DC9
0x180039db1  mov     r9d, esi; int
0x180039db4  lea     rdx, aCtranscodeprof_16; "CTranscodeProfileAdjuster::AdjustSelect"...
0x180039dbb  mov     r8d, 290h; int
0x180039dc1  mov     rcx, rax; this
0x180039dc4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039dc9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180039dce  cmp     al, 1
0x180039dd0  jb      loc_18003ABE7
0x180039dd6  mov     edx, 67h ; 'g'
0x180039ddb  jmp     loc_18003ABC9
0x180039de0  mov     rcx, [rbp+var_30]
0x180039de4  lea     rdx, [rbp+cInitialSize]
0x180039de8  mov     rax, [rcx]
0x180039deb  mov     rax, [rax+0F0h]
0x180039df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039df7  mov     ebx, eax
0x180039df9  test    eax, eax
0x180039dfb  jns     loc_180039E90
0x180039e01  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039e08  test    rcx, rcx
0x180039e0b  jnz     short loc_180039E4E
0x180039e0d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039e13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039e1a  mov     rcx, rax
0x180039e1d  test    rax, rax
0x180039e20  jz      short loc_180039E40
0x180039e22  mov     rax, [rax]
0x180039e25  mov     edx, 7F0h
0x180039e2a  mov     rax, [rax+8]
0x180039e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e33  test    eax, eax
0x180039e35  jz      short loc_180039E40
0x180039e37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039e3e  jmp     short loc_180039E4E
0x180039e40  lea     rcx, qword_180069A90; this
0x180039e47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039e4e  cmp     byte ptr [rcx+8], 0
0x180039e52  jz      short loc_180039E79
0x180039e54  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039e59  cmp     [rax+7CCh], ebx
0x180039e5f  jz      short loc_180039E79
0x180039e61  mov     r9d, ebx; int
0x180039e64  lea     rdx, aCtranscodeprof_16; "CTranscodeProfileAdjuster::AdjustSelect"...
0x180039e6b  mov     r8d, 293h; int
0x180039e71  mov     rcx, rax; this
0x180039e74  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039e79  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180039e7e  cmp     al, 1
0x180039e80  jb      loc_18003ABE7
0x180039e86  mov     edx, 68h ; 'h'
0x180039e8b  jmp     loc_180039B7E
0x180039e90  mov     edx, [rbp+cInitialSize]; cInitialSize
0x180039e93  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180039e97  call    cs:__imp_MFCreateAttributes
0x180039e9d  mov     ebx, eax
0x180039e9f  test    eax, eax
0x180039ea1  jns     loc_180039F36
0x180039ea7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039eae  test    rcx, rcx
0x180039eb1  jnz     short loc_180039EF4
0x180039eb3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039eb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039ec0  mov     rcx, rax
0x180039ec3  test    rax, rax
0x180039ec6  jz      short loc_180039EE6
0x180039ec8  mov     rax, [rax]
0x180039ecb  mov     edx, 7F0h
0x180039ed0  mov     rax, [rax+8]
0x180039ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ed9  test    eax, eax
0x180039edb  jz      short loc_180039EE6
0x180039edd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039ee4  jmp     short loc_180039EF4
0x180039ee6  lea     rcx, qword_180069A90; this
0x180039eed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039ef4  cmp     byte ptr [rcx+8], 0
0x180039ef8  jz      short loc_180039F1F
0x180039efa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039eff  cmp     [rax+7CCh], ebx
0x180039f05  jz      short loc_180039F1F
0x180039f07  mov     r9d, ebx; int
0x180039f0a  lea     rdx, aCtranscodeprof_16; "CTranscodeProfileAdjuster::AdjustSelect"...
0x180039f11  mov     r8d, 294h; int
0x180039f17  mov     rcx, rax; this
0x180039f1a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039f1f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180039f24  cmp     al, 1
0x180039f26  jb      loc_18003ABE7
0x180039f2c  mov     edx, 69h ; 'i'
0x180039f31  jmp     loc_180039B7E
0x180039f36  mov     rcx, [rbp+var_30]
0x180039f3a  mov     rdx, [rbp+ppMFAttributes]
0x180039f3e  mov     rax, [rcx]
0x180039f41  mov     rax, [rax+100h]
0x180039f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f4d  mov     ebx, eax
0x180039f4f  test    eax, eax
  ... truncated ...
```
