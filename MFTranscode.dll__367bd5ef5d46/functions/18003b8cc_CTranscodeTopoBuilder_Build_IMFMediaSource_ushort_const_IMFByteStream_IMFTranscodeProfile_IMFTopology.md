# CTranscodeTopoBuilder::Build(IMFMediaSource *,ushort const *,IMFByteStream *,IMFTranscodeProfile *,IMFTopology * *)

- ea: `0x18003b8cc`
- end: `0x18003c307`
- name: `?Build@CTranscodeTopoBuilder@@QEAAJPEAUIMFMediaSource@@PEBGPEAUIMFByteStream@@PEAUIMFTranscodeProfile@@PEAPEAUIMFTopology@@@Z`
- size: `2619`
- prototype: `__int64 __usercall@<rax>(CTranscodeTopoBuilder *__hidden this@<rcx>, struct IMFMediaSource *@<rdx>, const unsigned __int16 *@<r8>, struct IMFByteStream *@<r9>, struct IMFTranscodeProfile *, struct IMFTopology **)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x180035b70`

## callees

- `0x180002260`
- `0x180002f50`
- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x18001a320`
- `0x18001a330`
- `0x18001c280`
- `0x1800387d0`
- `0x180038838`
- `0x180038974`
- `0x180038a10`
- `0x18003b8cc`
- `0x18003c310`
- `0x18003dd30`
- `0x18003e274`
- `0x18003e5dc`
- `0x18003f808`
- `0x18003f89c`
- `0x180040078`
- `0x18004f410`
- `0x180059128`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b9a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ba74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bb1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bbff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bcb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bd92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003be49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bf16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bff6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c0a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c181`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b9a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ba74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bb1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bbff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bcb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bd92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003be49`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bf16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bff6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c0a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c181`
- `MFCORE!MFCreateTopology` at `0x18003bfda`
- `MFCORE!MFCreateTopology` at `0x18003bfda`

## pseudocode

```c
__int64 __fastcall CTranscodeTopoBuilder::Build(
        CTranscodeTopoBuilder *this,
        OLECHAR *a2,
        const unsigned __int16 *a3,
        OLECHAR *a4,
        struct IMFTranscodeProfile *a5,
        struct IMFTopology **a6)
{
  struct CTranscodeDestination *v9; // rsi
  struct CTranscodeProfileAdjuster *v10; // r15
  struct IMFMediaSourceVtbl *v11; // rax
  __int64 v12; // rdx
  int SelectedSourceStreams; // ebx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  struct IMFPresentationDescriptor *v34; // rbx
  int v35; // r14d
  __int64 v36; // rdx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  int v49; // ecx
  __int64 v50; // r8
  __int64 v51; // rdx
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  unsigned int i; // r14d
  __int64 v60; // rdx
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  IMFTopology *v64; // rax
  _BYTE v66[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct IMFTranscodeProfile *v67; // [rsp+38h] [rbp-C8h] BYREF
  IMFTopology *ppTopo; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  struct IMFPresentationDescriptor *v70; // [rsp+50h] [rbp-B0h] BYREF
  struct CTranscodeProfileAdjuster *v71; // [rsp+58h] [rbp-A8h] BYREF
  struct CTranscodeDestination *v72; // [rsp+60h] [rbp-A0h] BYREF
  SourceInfo v73; // [rsp+68h] [rbp-98h] BYREF
  struct IMFTopology **v74; // [rsp+88h] [rbp-78h]
  _BYTE v75[208]; // [rsp+90h] [rbp-70h] BYREF

  v74 = a6;
  v73.Hash = a4;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v66, "CTranscodeTopoBuilder::Build", 164);
  memset(&v73, 0, 24);
  CTPtrArray<IMFStreamDescriptor,20>::CTPtrArray<IMFStreamDescriptor,20>(v75);
  v70 = 0;
  v9 = 0;
  v67 = 0;
  v10 = 0;
  Block = 0;
  ppTopo = 0;
  v72 = 0;
  v71 = 0;
  CTranscodeTopoBuilder::Reset(this);
  v11 = *(struct IMFMediaSourceVtbl **)a2;
  v73.FileName = a2;
  *(_OWORD *)&v73.LineNumber = 0;
  SelectedSourceStreams = ((__int64 (__fastcall *)(OLECHAR *, struct IMFPresentationDescriptor **))v11->CreatePresentationDescriptor)(
                            a2,
                            &v70);
  if ( SelectedSourceStreams >= 0 )
  {
    *(_QWORD *)&v73.LineNumber = v70;
    SelectedSourceStreams = CTranscodeTopoBuilder::GetSelectedSourceStreams(this, v70, v75);
    if ( SelectedSourceStreams >= 0 )
    {
      SelectedSourceStreams = CTranscodeTopoBuilder::GetProfileAdjuster(this, a5, &v71);
      if ( SelectedSourceStreams >= 0 )
      {
        v10 = v71;
        SelectedSourceStreams = (*(__int64 (__fastcall **)(struct CTranscodeProfileAdjuster *, _BYTE *, struct IMFTranscodeProfile *, void **, struct IMFTranscodeProfile **))(*(_QWORD *)v71 + 8LL))(
                                  v71,
                                  v75,
                                  a5,
                                  &Block,
                                  &v67);
        if ( SelectedSourceStreams >= 0 )
        {
          TryDumpTranscodeProfile(v67, L"TranscodeAPI\\DumpAdjustedProfile");
          if ( *((_DWORD *)Block + 50) )
          {
            v34 = v70;
            CallStackScopeTrace::CallStackScopeTrace(
              (CallStackScopeTrace *)v66,
              "CTranscodeTopoBuilder::RequireProtectedEnvironment",
              314);
            SelectedSourceStreams = CPresentationDescriptorPtr::RequireProtectedEnvironment(v34);
            if ( SelectedSourceStreams )
            {
              v35 = 0;
              if ( SelectedSourceStreams == 1 )
                v35 = 0;
            }
            else
            {
              v35 = 1;
            }
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v66);
            if ( SelectedSourceStreams >= 0 )
            {
              SelectedSourceStreams = CTranscodeDestination::GetDestination(
                                        v35,
                                        a3,
                                        (struct IMFByteStream *)v73.Hash,
                                        v67,
                                        &v72);
              if ( SelectedSourceStreams >= 0 )
              {
                v9 = v72;
                SelectedSourceStreams = CTranscodeTopoBuilder::ConfigStreamMap(
                                          (__int64)this,
                                          (__int64)Block,
                                          (__int64)v72);
                if ( SelectedSourceStreams >= 0 )
                {
                  if ( (*(int (__fastcall **)(struct CTranscodeDestination *, OLECHAR *, char *))(*(_QWORD *)v9 + 24LL))(
                         v9,
                         a2,
                         (char *)this + 8) < 0
                    && _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() >= 0x10u )
                  {
                    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), v48, v50, this, v49);
                  }
                  SelectedSourceStreams = MFCreateTopology(&ppTopo);
                  if ( SelectedSourceStreams >= 0 )
                  {
                    SelectedSourceStreams = CTranscodeTopoBuilder::SetTopoAttributes(this, ppTopo, v67);
                    if ( SelectedSourceStreams >= 0 )
                    {
                      for ( i = 0; ; ++i )
                      {
                        if ( i >= *((_DWORD *)Block + 50) )
                        {
                          v64 = ppTopo;
                          ppTopo = 0;
                          *v74 = v64;
                          goto LABEL_136;
                        }
                        *(_QWORD *)&v73.CharPosition = CTPtrArray<IMFStreamDescriptor,20>::operator[](Block, i);
                        SelectedSourceStreams = CTranscodeTopoBuilder::BuildBranch(this, v67, &v73, v9, ppTopo, i);
                        if ( SelectedSourceStreams < 0 )
                          break;
                      }
                      v61 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60);
                        CallStackTracing::s_wpInstance = v62;
                        if ( v62
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(
                               v62,
                               2032) )
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
                        if ( *((_DWORD *)ThreadRelativeContext + 499) != SelectedSourceStreams )
                          CallStackContext::TraceFailure(
                            ThreadRelativeContext,
                            "CTranscodeTopoBuilder::Build",
                            246,
                            SelectedSourceStreams);
                      }
                      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      {
                        v17 = 34;
                        goto LABEL_12;
                      }
                    }
                    else
                    {
                      v56 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55);
                        CallStackTracing::s_wpInstance = v57;
                        if ( v57
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(
                               v57,
                               2032) )
                        {
                          v56 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v56 = &qword_180069A90;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                        }
                      }
                      if ( *((_BYTE *)v56 + 8) )
                      {
                        v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
                        if ( *((_DWORD *)v58 + 499) != SelectedSourceStreams )
                          CallStackContext::TraceFailure(
                            v58,
                            "CTranscodeTopoBuilder::Build",
                            238,
                            SelectedSourceStreams);
                      }
                      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      {
                        v17 = 33;
                        goto LABEL_12;
                      }
                    }
                  }
                  else
                  {
                    v52 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
                      CallStackTracing::s_wpInstance = v53;
                      if ( v53
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(
                             v53,
                             2032) )
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
                      if ( *((_DWORD *)v54 + 499) != SelectedSourceStreams )
                        CallStackContext::TraceFailure(v54, "CTranscodeTopoBuilder::Build", 233, SelectedSourceStreams);
                    }
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v17 = 32;
                      goto LABEL_12;
                    }
                  }
                }
                else
                {
                  v45 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
                    CallStackTracing::s_wpInstance = v46;
                    if ( v46
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
                    {
                      v45 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v45 = &qword_180069A90;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                    }
                  }
                  if ( *((_BYTE *)v45 + 8) )
                  {
                    v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
                    if ( *((_DWORD *)v47 + 499) != SelectedSourceStreams )
                      CallStackContext::TraceFailure(v47, "CTranscodeTopoBuilder::Build", 212, SelectedSourceStreams);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v17 = 30;
                    goto LABEL_12;
                  }
                }
              }
              else
              {
                v41 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
                  CallStackTracing::s_wpInstance = v42;
                  if ( v42
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                  {
                    v41 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v41 = &qword_180069A90;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)v41 + 8) )
                {
                  v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
                  if ( *((_DWORD *)v43 + 499) != SelectedSourceStreams )
                    CallStackContext::TraceFailure(v43, "CTranscodeTopoBuilder::Build", 206, SelectedSourceStreams);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  WPP_SF_qd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    29,
                    &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids,
                    this,
                    SelectedSourceStreams);
                v9 = v72;
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
                if ( *((_DWORD *)v39 + 499) != SelectedSourceStreams )
                  CallStackContext::TraceFailure(v39, "CTranscodeTopoBuilder::Build", 205, SelectedSourceStreams);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v17 = 28;
                goto LABEL_12;
              }
            }
          }
          else
          {
            v31 = (__int64 *)CallStackTracing::s_wpInstance;
            SelectedSourceStreams = -1072847855;
            if ( !CallStackTracing::s_wpInstance )
            {
              v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
              CallStackTracing::s_wpInstance = v32;
              if ( v32
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
              {
                v31 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v31 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v31 + 8) )
            {
              v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
              if ( *((_DWORD *)v33 + 499) != -1072847855 )
                CallStackContext::TraceFailure(v33, "CTranscodeTopoBuilder::Build", 199, -1072847855);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v17 = 27;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
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
            if ( *((_DWORD *)v29 + 499) != SelectedSourceStreams )
              CallStackContext::TraceFailure(v29, "CTranscodeTopoBuilder::Build", 193, SelectedSourceStreams);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v17 = 26;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
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
          if ( *((_DWORD *)v25 + 499) != SelectedSourceStreams )
            CallStackContext::TraceFailure(v25, "CTranscodeTopoBuilder::Build", 191, SelectedSourceStreams);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids,
            this,
            SelectedSourceStreams);
        v10 = v71;
      }
    }
    else
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
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
        if ( *((_DWORD *)v21 + 499) != SelectedSourceStreams )
          CallStackContext::TraceFailure(v21, "CTranscodeTopoBuilder::Build", 186, SelectedSourceStreams);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v17 = 24;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != SelectedSourceStreams )
        CallStackContext::TraceFailure(v16, "CTranscodeTopoBuilder::Build", 183, SelectedSourceStreams);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v17 = 23;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids,
        this,
        SelectedSourceStreams);
    }
  }
LABEL_136:
  if ( v70 )
  {
    ((void (__fastcall *)(struct IMFPresentationDescriptor *))v70->lpVtbl->Release)(v70);
    v70 = 0;
  }
  if ( Block )
    CTPtrArray<IMFStreamDescriptor,20>::`scalar deleting destructor'(Block);
  Block = 0;
  if ( v67 )
  {
    ((void (__fastcall *)(struct IMFTranscodeProfile *))v67->lpVtbl->Release)(v67);
    v67 = 0;
  }
  if ( ppTopo )
  {
    ((void (__fastcall *)(IMFTopology *))ppTopo->lpVtbl->Release)(ppTopo);
    ppTopo = 0;
  }
  if ( SelectedSourceStreams < 0 )
  {
    if ( !v9 )
      goto LABEL_149;
    (*(void (__fastcall **)(struct CTranscodeDestination *))(*(_QWORD *)v9 + 56LL))(v9);
  }
  if ( v9 )
    (**(void (__fastcall ***)(struct CTranscodeDestination *, __int64))v9)(v9, 1);
LABEL_149:
  if ( v10 )
    (**(void (__fastcall ***)(struct CTranscodeProfileAdjuster *, __int64))v10)(v10, 1);
  CTSparseBlock<unsigned long,IMFStreamDescriptor *,20,1>::~CTSparseBlock<unsigned long,IMFStreamDescriptor *,20,1>(v75);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v66);
  return (unsigned int)SelectedSourceStreams;
}

```

## disassembly

```asm
0x18003b8cc  push    rbp
0x18003b8ce  push    rbx
0x18003b8cf  push    rsi
0x18003b8d0  push    rdi
0x18003b8d1  push    r12
0x18003b8d3  push    r13
0x18003b8d5  push    r14
0x18003b8d7  push    r15
0x18003b8d9  lea     rbp, [rsp-78h]
0x18003b8de  sub     rsp, 178h
0x18003b8e5  mov     rax, cs:__security_cookie
0x18003b8ec  xor     rax, rsp
0x18003b8ef  mov     [rbp+0B0h+var_50], rax
0x18003b8f3  mov     rax, [rbp+0B0h+arg_28]
0x18003b8fa  mov     r13, r8
0x18003b8fd  mov     r14, [rbp+0B0h+arg_20]
0x18003b904  mov     r12, rdx
0x18003b907  mov     rdi, rcx
0x18003b90a  mov     [rbp+0B0h+var_128], rax
0x18003b90e  mov     r8d, 0A4h; int
0x18003b914  mov     [rbp+0B0h+var_148.Hash], r9
0x18003b918  lea     rdx, aCtranscodetopo_4; "CTranscodeTopoBuilder::Build"
0x18003b91f  lea     rcx, [rsp+1B0h+var_180]; this
0x18003b924  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b929  xorps   xmm0, xmm0
0x18003b92c  lea     rcx, [rbp+0B0h+var_120]
0x18003b930  xor     eax, eax
0x18003b932  movups  xmmword ptr [rsp+1B0h+var_148.FileName], xmm0
0x18003b937  mov     qword ptr [rsp+1B0h+var_148.CharPosition], rax
0x18003b93c  call    ??0?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEAA@XZ; CTPtrArray<IMFStreamDescriptor,20>::CTPtrArray<IMFStreamDescriptor,20>(void)
0x18003b941  xor     eax, eax
0x18003b943  mov     rcx, rdi; this
0x18003b946  mov     [rsp+1B0h+var_160], rax
0x18003b94b  mov     esi, eax
0x18003b94d  mov     [rsp+1B0h+var_178], rax
0x18003b952  mov     r15d, eax
0x18003b955  mov     [rsp+1B0h+Block], rax
0x18003b95a  mov     [rsp+1B0h+ppTopo], rax
0x18003b95f  mov     [rsp+1B0h+var_150], rax
0x18003b964  mov     [rsp+1B0h+var_158], rax
0x18003b969  call    ?Reset@CTranscodeTopoBuilder@@IEAAXXZ; CTranscodeTopoBuilder::Reset(void)
0x18003b96e  mov     rax, [r12]
0x18003b972  lea     rdx, [rsp+1B0h+var_160]
0x18003b977  xorps   xmm0, xmm0
0x18003b97a  mov     [rsp+1B0h+var_148.FileName], r12
0x18003b97f  mov     rcx, r12
0x18003b982  movdqu  xmmword ptr [rsp+1B0h+var_148.LineNumber], xmm0
0x18003b988  mov     rax, [rax+40h]
0x18003b98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b991  mov     ebx, eax
0x18003b993  test    eax, eax
0x18003b995  jns     loc_18003BA48
0x18003b99b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b9a2  test    rcx, rcx
0x18003b9a5  jnz     short loc_18003B9E8
0x18003b9a7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b9ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b9b4  mov     rcx, rax
0x18003b9b7  test    rax, rax
0x18003b9ba  jz      short loc_18003B9DA
0x18003b9bc  mov     rax, [rax]
0x18003b9bf  mov     edx, 7F0h
0x18003b9c4  mov     rax, [rax+8]
0x18003b9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9cd  test    eax, eax
0x18003b9cf  jz      short loc_18003B9DA
0x18003b9d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b9d8  jmp     short loc_18003B9E8
0x18003b9da  lea     rcx, qword_180069A90; this
0x18003b9e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b9e8  cmp     [rcx+8], sil
0x18003b9ec  jz      short loc_18003BA13
0x18003b9ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b9f3  cmp     [rax+7CCh], ebx
0x18003b9f9  jz      short loc_18003BA13
0x18003b9fb  mov     r9d, ebx; int
0x18003b9fe  lea     rdx, aCtranscodetopo_4; "CTranscodeTopoBuilder::Build"
0x18003ba05  mov     r8d, 0B7h; int
0x18003ba0b  mov     rcx, rax; this
0x18003ba0e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ba13  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003ba18  cmp     al, 1
0x18003ba1a  jb      loc_18003C215
0x18003ba20  mov     edx, 17h
0x18003ba25  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba2c  lea     r8, WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids
0x18003ba33  mov     r9, rdi
0x18003ba36  mov     dword ptr [rsp+1B0h+var_190], ebx
0x18003ba3a  mov     rcx, [rcx+10h]
0x18003ba3e  call    WPP_SF_qd
0x18003ba43  jmp     loc_18003C215
0x18003ba48  mov     rdx, [rsp+1B0h+var_160]
0x18003ba4d  lea     r8, [rbp+0B0h+var_120]
0x18003ba51  mov     rcx, rdi
0x18003ba54  mov     qword ptr [rsp+1B0h+var_148.LineNumber], rdx
0x18003ba59  call    ?GetSelectedSourceStreams@CTranscodeTopoBuilder@@IEAAJPEAUIMFPresentationDescriptor@@AEAV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@@Z; CTranscodeTopoBuilder::GetSelectedSourceStreams(IMFPresentationDescriptor *,CTPtrArray<IMFStreamDescriptor,20> &)
0x18003ba5e  mov     ebx, eax
0x18003ba60  test    eax, eax
0x18003ba62  jns     loc_18003BAF7
0x18003ba68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ba6f  test    rcx, rcx
0x18003ba72  jnz     short loc_18003BAB5
0x18003ba74  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ba7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ba81  mov     rcx, rax
0x18003ba84  test    rax, rax
0x18003ba87  jz      short loc_18003BAA7
0x18003ba89  mov     rax, [rax]
0x18003ba8c  mov     edx, 7F0h
0x18003ba91  mov     rax, [rax+8]
0x18003ba95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba9a  test    eax, eax
0x18003ba9c  jz      short loc_18003BAA7
0x18003ba9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003baa5  jmp     short loc_18003BAB5
0x18003baa7  lea     rcx, qword_180069A90; this
0x18003baae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bab5  cmp     [rcx+8], sil
0x18003bab9  jz      short loc_18003BAE0
0x18003babb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003bac0  cmp     [rax+7CCh], ebx
0x18003bac6  jz      short loc_18003BAE0
0x18003bac8  mov     r9d, ebx; int
0x18003bacb  lea     rdx, aCtranscodetopo_4; "CTranscodeTopoBuilder::Build"
0x18003bad2  mov     r8d, 0BAh; int
0x18003bad8  mov     rcx, rax; this
0x18003badb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003bae0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003bae5  cmp     al, 1
0x18003bae7  jb      loc_18003C215
0x18003baed  mov     edx, 18h
0x18003baf2  jmp     loc_18003BA25
0x18003baf7  lea     r8, [rsp+1B0h+var_158]; struct CTranscodeProfileAdjuster **
0x18003bafc  mov     rdx, r14; struct IMFTranscodeProfile *
0x18003baff  mov     rcx, rdi; this
0x18003bb02  call    ?GetProfileAdjuster@CTranscodeTopoBuilder@@IEAAJPEAUIMFTranscodeProfile@@PEAPEAVCTranscodeProfileAdjuster@@@Z; CTranscodeTopoBuilder::GetProfileAdjuster(IMFTranscodeProfile *,CTranscodeProfileAdjuster * *)
0x18003bb07  mov     ebx, eax
0x18003bb09  test    eax, eax
0x18003bb0b  jns     loc_18003BBBF
0x18003bb11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bb18  test    rcx, rcx
0x18003bb1b  jnz     short loc_18003BB5E
0x18003bb1d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003bb23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bb2a  mov     rcx, rax
0x18003bb2d  test    rax, rax
0x18003bb30  jz      short loc_18003BB50
0x18003bb32  mov     rax, [rax]
0x18003bb35  mov     edx, 7F0h
0x18003bb3a  mov     rax, [rax+8]
0x18003bb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb43  test    eax, eax
0x18003bb45  jz      short loc_18003BB50
0x18003bb47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bb4e  jmp     short loc_18003BB5E
0x18003bb50  lea     rcx, qword_180069A90; this
0x18003bb57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bb5e  cmp     [rcx+8], sil
0x18003bb62  jz      short loc_18003BB89
0x18003bb64  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003bb69  cmp     [rax+7CCh], ebx
0x18003bb6f  jz      short loc_18003BB89
0x18003bb71  mov     r9d, ebx; int
0x18003bb74  lea     rdx, aCtranscodetopo_4; "CTranscodeTopoBuilder::Build"
0x18003bb7b  mov     r8d, 0BFh; int
0x18003bb81  mov     rcx, rax; this
0x18003bb84  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003bb89  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003bb8e  cmp     al, 1
0x18003bb90  jb      short loc_18003BBB5
0x18003bb92  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bb99  lea     r8, WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids
0x18003bba0  mov     edx, 19h
0x18003bba5  mov     dword ptr [rsp+1B0h+var_190], ebx
0x18003bba9  mov     r9, rdi
0x18003bbac  mov     rcx, [rcx+10h]
0x18003bbb0  call    WPP_SF_qd
0x18003bbb5  mov     r15, [rsp+1B0h+var_158]
0x18003bbba  jmp     loc_18003C215
0x18003bbbf  mov     r15, [rsp+1B0h+var_158]
0x18003bbc4  lea     rcx, [rsp+1B0h+var_178]
0x18003bbc9  mov     [rsp+1B0h+var_190], rcx
0x18003bbce  lea     r9, [rsp+1B0h+Block]
0x18003bbd3  mov     r8, r14
0x18003bbd6  lea     rdx, [rbp+0B0h+var_120]
0x18003bbda  mov     rcx, r15
0x18003bbdd  mov     rax, [r15]
0x18003bbe0  mov     rax, [rax+8]
0x18003bbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbe9  mov     ebx, eax
0x18003bbeb  test    eax, eax
0x18003bbed  jns     loc_18003BC82
0x18003bbf3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bbfa  test    rcx, rcx
0x18003bbfd  jnz     short loc_18003BC40
0x18003bbff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003bc05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bc0c  mov     rcx, rax
0x18003bc0f  test    rax, rax
0x18003bc12  jz      short loc_18003BC32
0x18003bc14  mov     rax, [rax]
0x18003bc17  mov     edx, 7F0h
0x18003bc1c  mov     rax, [rax+8]
0x18003bc20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc25  test    eax, eax
0x18003bc27  jz      short loc_18003BC32
0x18003bc29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bc30  jmp     short loc_18003BC40
0x18003bc32  lea     rcx, qword_180069A90; this
0x18003bc39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bc40  cmp     [rcx+8], sil
0x18003bc44  jz      short loc_18003BC6B
0x18003bc46  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003bc4b  cmp     [rax+7CCh], ebx
0x18003bc51  jz      short loc_18003BC6B
0x18003bc53  mov     r9d, ebx; int
0x18003bc56  lea     rdx, aCtranscodetopo_4; "CTranscodeTopoBuilder::Build"
0x18003bc5d  mov     r8d, 0C1h; int
0x18003bc63  mov     rcx, rax; this
0x18003bc66  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003bc6b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003bc70  cmp     al, 1
0x18003bc72  jb      loc_18003C215
0x18003bc78  mov     edx, 1Ah
0x18003bc7d  jmp     loc_18003BA25
0x18003bc82  mov     rcx, [rsp+1B0h+var_178]; struct IMFTranscodeProfile *
0x18003bc87  lea     rdx, aTranscodeapiDu_0; "TranscodeAPI\\DumpAdjustedProfile"
0x18003bc8e  call    ?TryDumpTranscodeProfile@@YAJPEAUIMFTranscodeProfile@@PEBG@Z; TryDumpTranscodeProfile(IMFTranscodeProfile *,ushort const *)
0x18003bc93  mov     rax, [rsp+1B0h+Block]
0x18003bc98  cmp     [rax+0C8h], esi
0x18003bc9e  jnz     loc_18003BD38
0x18003bca4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bcab  mov     ebx, 0C00DA411h
0x18003bcb0  test    rcx, rcx
0x18003bcb3  jnz     short loc_18003BCF6
0x18003bcb5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003bcbb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bcc2  mov     rcx, rax
0x18003bcc5  test    rax, rax
0x18003bcc8  jz      short loc_18003BCE8
0x18003bcca  mov     rax, [rax]
0x18003bccd  mov     edx, 7F0h
0x18003bcd2  mov     rax, [rax+8]
0x18003bcd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcdb  test    eax, eax
0x18003bcdd  jz      short loc_18003BCE8
0x18003bcdf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bce6  jmp     short loc_18003BCF6
0x18003bce8  lea     rcx, qword_180069A90; this
0x18003bcef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bcf6  cmp     [rcx+8], sil
0x18003bcfa  jz      short loc_18003BD21
0x18003bcfc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003bd01  cmp     [rax+7CCh], ebx
0x18003bd07  jz      short loc_18003BD21
0x18003bd09  mov     r9d, ebx; int
0x18003bd0c  lea     rdx, aCtranscodetopo_4; "CTranscodeTopoBuilder::Build"
0x18003bd13  mov     r8d, 0C7h; int
0x18003bd19  mov     rcx, rax; this
0x18003bd1c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003bd21  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003bd26  cmp     al, 1
0x18003bd28  jb      loc_18003C215
0x18003bd2e  mov     edx, 1Bh
0x18003bd33  jmp     loc_18003BA25
0x18003bd38  mov     rbx, [rsp+1B0h+var_160]
0x18003bd3d  lea     rdx, aCtranscodetopo_10; "CTranscodeTopoBuilder::RequireProtected"...
0x18003bd44  mov     r8d, 13Ah; int
0x18003bd4a  lea     rcx, [rsp+1B0h+var_180]; this
0x18003bd4f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003bd54  mov     rcx, rbx; struct IMFPresentationDescriptor *
0x18003bd57  call    ?RequireProtectedEnvironment@CPresentationDescriptorPtr@@SAJPEAUIMFPresentationDescriptor@@@Z; CPresentationDescriptorPtr::RequireProtectedEnvironment(IMFPresentationDescriptor *)
0x18003bd5c  mov     ebx, eax
0x18003bd5e  test    eax, eax
0x18003bd60  jnz     short loc_18003BD68
0x18003bd62  lea     r14d, [rax+1]
0x18003bd66  jmp     short loc_18003BD74
0x18003bd68  xor     r14d, r14d
0x18003bd6b  xor     eax, eax
0x18003bd6d  cmp     ebx, 1
0x18003bd70  cmovz   r14d, eax
0x18003bd74  lea     rcx, [rsp+1B0h+var_180]; this
0x18003bd79  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003bd7e  test    ebx, ebx
0x18003bd80  jns     loc_18003BE15
0x18003bd86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bd8d  test    rcx, rcx
0x18003bd90  jnz     short loc_18003BDD3
0x18003bd92  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003bd98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bd9f  mov     rcx, rax
0x18003bda2  test    rax, rax
0x18003bda5  jz      short loc_18003BDC5
0x18003bda7  mov     rax, [rax]
0x18003bdaa  mov     edx, 7F0h
0x18003bdaf  mov     rax, [rax+8]
0x18003bdb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdb8  test    eax, eax
0x18003bdba  jz      short loc_18003BDC5
0x18003bdbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
