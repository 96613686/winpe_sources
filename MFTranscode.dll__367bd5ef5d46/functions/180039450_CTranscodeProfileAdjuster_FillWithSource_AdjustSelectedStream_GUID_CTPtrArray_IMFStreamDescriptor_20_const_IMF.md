# CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream(_GUID,CTPtrArray<IMFStreamDescriptor,20> const &,IMFAttributes *,CTPtrArray<IMFStreamDescriptor,20> *,IMFTranscodeProfile *)

- ea: `0x180039450`
- end: `0x180039a60`
- name: `?AdjustSelectedStream@CTranscodeProfileAdjuster_FillWithSource@@AEAAJU_GUID@@AEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@PEAUIMFAttributes@@PEAV3@PEAUIMFTranscodeProfile@@@Z`
- size: `1552`
- prototype: `__int64 __usercall@<rax>(CTranscodeProfileAdjuster_FillWithSource *this@<rcx>, void *Buf2@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18003acf0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18000a940`
- `0x18001a330`
- `0x18001c280`
- `0x180038974`
- `0x180038b18`
- `0x180038b58`
- `0x180039450`
- `0x18003e94c`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800394cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003958a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039632`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800396fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800397a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003986a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039917`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800399a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800394cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003958a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039632`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800396fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800397a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003986a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039917`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800399a7`

## pseudocode

```c
__int64 __fastcall CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream(
        CTranscodeProfileAdjuster_FillWithSource *this,
        void *Buf2,
        __int64 a3,
        struct IMFAttributes *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v10; // rdx
  int MatchedSrcStream; // ebx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  _BYTE v46[4]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v47; // [rsp+34h] [rbp-24h] BYREF
  int v48; // [rsp+38h] [rbp-20h] BYREF
  int v49; // [rsp+3Ch] [rbp-1Ch] BYREF
  struct IMFAttributes *v50[3]; // [rsp+40h] [rbp-18h] BYREF

  v48 = 0;
  v47 = 0;
  v49 = 0;
  v50[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v46,
    "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream",
    977);
  MatchedSrcStream = CTranscodeProfileAdjuster::FindMatchedSrcStream(
                       (_DWORD)this,
                       (_DWORD)Buf2,
                       a3,
                       (unsigned int)&v48,
                       (__int64)&v47);
  if ( MatchedSrcStream >= 0 )
  {
    if ( v48 )
    {
      v16 = CTPtrArray<IMFStreamDescriptor,20>::operator[](a3, v47);
      if ( (unsigned int)CTPtrArray<IMFStreamDescriptor,20>::Add(a5, v16, &v49) )
      {
        MatchedSrcStream = CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs((__int64)this, a3, v47, v50);
        if ( MatchedSrcStream >= 0 )
        {
          if ( !memcmp_0(&MFMediaType_Audio, Buf2, 0x10u) )
          {
            MatchedSrcStream = (*(__int64 (__fastcall **)(__int64, struct IMFAttributes *))(*(_QWORD *)a6 + 24LL))(
                                 a6,
                                 v50[0]);
            if ( MatchedSrcStream >= 0 )
            {
              if ( a4 )
              {
                MatchedSrcStream = CTranscodeProfileAdjuster_FillWithSource::AddOriginalStreamAttrs(this, a4, v50[0]);
                if ( MatchedSrcStream < 0 )
                {
                  v30 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
                    CallStackTracing::s_wpInstance = v31;
                    if ( v31
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
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
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != MatchedSrcStream )
                      CallStackContext::TraceFailure(
                        ThreadRelativeContext,
                        "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream",
                        995,
                        MatchedSrcStream);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v15 = 155;
                    goto LABEL_93;
                  }
                }
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
                if ( *((_DWORD *)v28 + 499) != MatchedSrcStream )
                  CallStackContext::TraceFailure(
                    v28,
                    "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream",
                    991,
                    MatchedSrcStream);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v15 = 154;
                goto LABEL_93;
              }
            }
          }
          else if ( !memcmp_0(&MFMediaType_Video, Buf2, 0x10u) )
          {
            MatchedSrcStream = (*(__int64 (__fastcall **)(__int64, struct IMFAttributes *))(*(_QWORD *)a6 + 40LL))(
                                 a6,
                                 v50[0]);
            if ( MatchedSrcStream >= 0 )
            {
              if ( a4 )
              {
                MatchedSrcStream = CTranscodeProfileAdjuster_FillWithSource::AddOriginalStreamAttrs(this, a4, v50[0]);
                if ( MatchedSrcStream < 0 )
                {
                  v39 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
                    CallStackTracing::s_wpInstance = v40;
                    if ( v40
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                    {
                      v39 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v39 = &qword_180069A90;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                    }
                  }
                  if ( *((_BYTE *)v39 + 8) )
                  {
                    v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
                    if ( *((_DWORD *)v41 + 499) != MatchedSrcStream )
                      CallStackContext::TraceFailure(
                        v41,
                        "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream",
                        1004,
                        MatchedSrcStream);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v15 = 157;
                    goto LABEL_93;
                  }
                }
              }
            }
            else
            {
              v35 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
                CallStackTracing::s_wpInstance = v36;
                if ( v36
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
                {
                  v35 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v35 = &qword_180069A90;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)v35 + 8) )
              {
                v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
                if ( *((_DWORD *)v37 + 499) != MatchedSrcStream )
                  CallStackContext::TraceFailure(
                    v37,
                    "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream",
                    1000,
                    MatchedSrcStream);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v15 = 156;
                goto LABEL_93;
              }
            }
          }
          else
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
            MatchedSrcStream = -2147418113;
            if ( !CallStackTracing::s_wpInstance )
            {
              v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
              CallStackTracing::s_wpInstance = v43;
              if ( v43
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
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
              if ( *((_DWORD *)v44 + 499) != -2147418113 )
                CallStackContext::TraceFailure(
                  v44,
                  "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream",
                  1010,
                  -2147418113);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v15 = 158;
              goto LABEL_93;
            }
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
            if ( *((_DWORD *)v24 + 499) != MatchedSrcStream )
              CallStackContext::TraceFailure(
                v24,
                "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream",
                987,
                MatchedSrcStream);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v15 = 153;
            goto LABEL_93;
          }
        }
      }
      else
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        MatchedSrcStream = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != -2147024882 )
            CallStackContext::TraceFailure(
              v20,
              "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream",
              983,
              -2147024882);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v15 = 152;
          goto LABEL_93;
        }
      }
    }
  }
  else
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
      if ( *((_DWORD *)v14 + 499) != MatchedSrcStream )
        CallStackContext::TraceFailure(
          v14,
          "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream",
          977,
          MatchedSrcStream);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v15 = 151;
LABEL_93:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids,
        this,
        MatchedSrcStream);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v50);
  return (unsigned int)MatchedSrcStream;
}

```

## disassembly

```asm
0x180039450  push    rbp
0x180039452  push    rbx
0x180039453  push    rsi
0x180039454  push    rdi
0x180039455  push    r12
0x180039457  push    r13
0x180039459  push    r14
0x18003945b  push    r15
0x18003945d  mov     rbp, rsp
0x180039460  sub     rsp, 58h
0x180039464  xor     r12d, r12d
0x180039467  lea     r13, aCtranscodeprof_6; "CTranscodeProfileAdjuster_FillWithSourc"...
0x18003946e  mov     r15, r8
0x180039471  mov     [rbp+var_20], r12d
0x180039475  mov     r14, rdx
0x180039478  mov     [rbp+var_24], r12d
0x18003947c  mov     rdi, rcx
0x18003947f  mov     [rbp+var_1C], r12d
0x180039483  mov     rdx, r13; char *
0x180039486  mov     [rbp+var_18], r12
0x18003948a  mov     r8d, 3D1h; int
0x180039490  lea     rcx, [rbp+var_28]; this
0x180039494  mov     rsi, r9
0x180039497  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003949c  lea     rax, [rbp+var_24]
0x1800394a0  mov     r8, r15
0x1800394a3  lea     r9, [rbp+var_20]
0x1800394a7  mov     [rsp+58h+var_38], rax
0x1800394ac  mov     rdx, r14
0x1800394af  mov     rcx, rdi
0x1800394b2  call    ?FindMatchedSrcStream@CTranscodeProfileAdjuster@@IEAAJAEBU_GUID@@AEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@PEAHPEAK@Z; CTranscodeProfileAdjuster::FindMatchedSrcStream(_GUID const &,CTPtrArray<IMFStreamDescriptor,20> const &,int *,ulong *)
0x1800394b7  mov     ebx, eax
0x1800394b9  test    eax, eax
0x1800394bb  jns     loc_18003954C
0x1800394c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800394c8  test    rcx, rcx
0x1800394cb  jnz     short loc_18003950E
0x1800394cd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800394d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800394da  mov     rcx, rax
0x1800394dd  test    rax, rax
0x1800394e0  jz      short loc_180039500
0x1800394e2  mov     rax, [rax]
0x1800394e5  mov     edx, 7F0h
0x1800394ea  mov     rax, [rax+8]
0x1800394ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394f3  test    eax, eax
0x1800394f5  jz      short loc_180039500
0x1800394f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800394fe  jmp     short loc_18003950E
0x180039500  lea     rcx, qword_180069A90; this
0x180039507  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003950e  cmp     [rcx+8], r12b
0x180039512  jz      short loc_180039535
0x180039514  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039519  cmp     [rax+7CCh], ebx
0x18003951f  jz      short loc_180039535
0x180039521  mov     r9d, ebx; int
0x180039524  mov     r8d, 3D1h; int
0x18003952a  mov     rdx, r13; char *
0x18003952d  mov     rcx, rax; this
0x180039530  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039535  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003953a  cmp     al, 1
0x18003953c  jb      loc_180039A3B
0x180039542  mov     edx, 97h
0x180039547  jmp     loc_180039A1D
0x18003954c  cmp     [rbp+var_20], r12d
0x180039550  jz      loc_180039A3B
0x180039556  mov     edx, [rbp+var_24]
0x180039559  mov     rcx, r15
0x18003955c  call    ??A?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEBAPEAUIMFStreamDescriptor@@K@Z; CTPtrArray<IMFStreamDescriptor,20>::operator[](ulong)
0x180039561  mov     rcx, [rbp+arg_20]
0x180039565  lea     r8, [rbp+var_1C]
0x180039569  mov     rdx, rax
0x18003956c  call    ?Add@?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEAAHPEAUIMFStreamDescriptor@@PEAK@Z; CTPtrArray<IMFStreamDescriptor,20>::Add(IMFStreamDescriptor *,ulong *)
0x180039571  test    eax, eax
0x180039573  jnz     loc_180039609
0x180039579  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039580  mov     ebx, 8007000Eh
0x180039585  test    rcx, rcx
0x180039588  jnz     short loc_1800395CB
0x18003958a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039590  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039597  mov     rcx, rax
0x18003959a  test    rax, rax
0x18003959d  jz      short loc_1800395BD
0x18003959f  mov     rax, [rax]
0x1800395a2  mov     edx, 7F0h
0x1800395a7  mov     rax, [rax+8]
0x1800395ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395b0  test    eax, eax
0x1800395b2  jz      short loc_1800395BD
0x1800395b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800395bb  jmp     short loc_1800395CB
0x1800395bd  lea     rcx, qword_180069A90; this
0x1800395c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800395cb  cmp     [rcx+8], r12b
0x1800395cf  jz      short loc_1800395F2
0x1800395d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800395d6  cmp     [rax+7CCh], ebx
0x1800395dc  jz      short loc_1800395F2
0x1800395de  mov     r9d, ebx; int
0x1800395e1  mov     r8d, 3D7h; int
0x1800395e7  mov     rdx, r13; char *
0x1800395ea  mov     rcx, rax; this
0x1800395ed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800395f2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800395f7  cmp     al, 1
0x1800395f9  jb      loc_180039A3B
0x1800395ff  mov     edx, 98h
0x180039604  jmp     loc_180039A1D
0x180039609  mov     r8d, [rbp+var_24]
0x18003960d  lea     r9, [rbp+var_18]
0x180039611  mov     rdx, r15
0x180039614  mov     rcx, rdi
0x180039617  call    ?GetSrcStreamMTAttrs@CTranscodeProfileAdjuster_FillWithSource@@AEAAJAEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@KPEAPEAUIMFAttributes@@@Z; CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs(CTPtrArray<IMFStreamDescriptor,20> const &,ulong,IMFAttributes * *)
0x18003961c  mov     ebx, eax
0x18003961e  test    eax, eax
0x180039620  jns     loc_1800396B1
0x180039626  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003962d  test    rcx, rcx
0x180039630  jnz     short loc_180039673
0x180039632  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039638  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003963f  mov     rcx, rax
0x180039642  test    rax, rax
0x180039645  jz      short loc_180039665
0x180039647  mov     rax, [rax]
0x18003964a  mov     edx, 7F0h
0x18003964f  mov     rax, [rax+8]
0x180039653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039658  test    eax, eax
0x18003965a  jz      short loc_180039665
0x18003965c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039663  jmp     short loc_180039673
0x180039665  lea     rcx, qword_180069A90; this
0x18003966c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039673  cmp     [rcx+8], r12b
0x180039677  jz      short loc_18003969A
0x180039679  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003967e  cmp     [rax+7CCh], ebx
0x180039684  jz      short loc_18003969A
0x180039686  mov     r9d, ebx; int
0x180039689  mov     r8d, 3DBh; int
0x18003968f  mov     rdx, r13; char *
0x180039692  mov     rcx, rax; this
0x180039695  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003969a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003969f  cmp     al, 1
0x1800396a1  jb      loc_180039A3B
0x1800396a7  mov     edx, 99h
0x1800396ac  jmp     loc_180039A1D
0x1800396b1  mov     ebx, 10h
0x1800396b6  lea     rcx, MFMediaType_Audio; Buf1
0x1800396bd  mov     r8d, ebx; Size
0x1800396c0  mov     rdx, r14; Buf2
0x1800396c3  call    memcmp_0
0x1800396c8  test    eax, eax
0x1800396ca  jnz     loc_180039826
0x1800396d0  mov     rcx, [rbp+arg_28]
0x1800396d4  mov     rdx, [rbp+var_18]
0x1800396d8  mov     rax, [rcx]
0x1800396db  mov     rax, [rax+18h]
0x1800396df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396e4  mov     ebx, eax
0x1800396e6  test    eax, eax
0x1800396e8  jns     loc_180039779
0x1800396ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800396f5  test    rcx, rcx
0x1800396f8  jnz     short loc_18003973B
0x1800396fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039700  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039707  mov     rcx, rax
0x18003970a  test    rax, rax
0x18003970d  jz      short loc_18003972D
0x18003970f  mov     rax, [rax]
0x180039712  mov     edx, 7F0h
0x180039717  mov     rax, [rax+8]
0x18003971b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039720  test    eax, eax
0x180039722  jz      short loc_18003972D
0x180039724  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003972b  jmp     short loc_18003973B
0x18003972d  lea     rcx, qword_180069A90; this
0x180039734  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003973b  cmp     [rcx+8], r12b
0x18003973f  jz      short loc_180039762
0x180039741  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039746  cmp     [rax+7CCh], ebx
0x18003974c  jz      short loc_180039762
0x18003974e  mov     r9d, ebx; int
0x180039751  mov     r8d, 3DFh; int
0x180039757  mov     rdx, r13; char *
0x18003975a  mov     rcx, rax; this
0x18003975d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039762  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180039767  cmp     al, 1
0x180039769  jb      loc_180039A3B
0x18003976f  mov     edx, 9Ah
0x180039774  jmp     loc_180039A1D
0x180039779  test    rsi, rsi
0x18003977c  jz      loc_180039A3B
0x180039782  mov     r8, [rbp+var_18]; struct IMFAttributes *
0x180039786  mov     rdx, rsi; struct IMFAttributes *
0x180039789  mov     rcx, rdi; this
0x18003978c  call    ?AddOriginalStreamAttrs@CTranscodeProfileAdjuster_FillWithSource@@AEAAJPEAUIMFAttributes@@0@Z; CTranscodeProfileAdjuster_FillWithSource::AddOriginalStreamAttrs(IMFAttributes *,IMFAttributes *)
0x180039791  mov     ebx, eax
0x180039793  test    eax, eax
0x180039795  jns     loc_180039A3B
0x18003979b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800397a2  test    rcx, rcx
0x1800397a5  jnz     short loc_1800397E8
0x1800397a7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800397ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800397b4  mov     rcx, rax
0x1800397b7  test    rax, rax
0x1800397ba  jz      short loc_1800397DA
0x1800397bc  mov     rax, [rax]
0x1800397bf  mov     edx, 7F0h
0x1800397c4  mov     rax, [rax+8]
0x1800397c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397cd  test    eax, eax
0x1800397cf  jz      short loc_1800397DA
0x1800397d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800397d8  jmp     short loc_1800397E8
0x1800397da  lea     rcx, qword_180069A90; this
0x1800397e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800397e8  cmp     [rcx+8], r12b
0x1800397ec  jz      short loc_18003980F
0x1800397ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800397f3  cmp     [rax+7CCh], ebx
0x1800397f9  jz      short loc_18003980F
0x1800397fb  mov     r9d, ebx; int
0x1800397fe  mov     r8d, 3E3h; int
0x180039804  mov     rdx, r13; char *
0x180039807  mov     rcx, rax; this
0x18003980a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003980f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180039814  cmp     al, 1
0x180039816  jb      loc_180039A3B
0x18003981c  mov     edx, 9Bh
0x180039821  jmp     loc_180039A1D
0x180039826  mov     r8, rbx; Size
0x180039829  lea     rcx, MFMediaType_Video; Buf1
0x180039830  mov     rdx, r14; Buf2
0x180039833  call    memcmp_0
0x180039838  test    eax, eax
0x18003983a  jnz     loc_180039996
0x180039840  mov     rcx, [rbp+arg_28]
0x180039844  mov     rdx, [rbp+var_18]
0x180039848  mov     rax, [rcx]
0x18003984b  mov     rax, [rax+28h]
0x18003984f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039854  mov     ebx, eax
0x180039856  test    eax, eax
0x180039858  jns     loc_1800398E9
0x18003985e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039865  test    rcx, rcx
0x180039868  jnz     short loc_1800398AB
0x18003986a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039870  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039877  mov     rcx, rax
0x18003987a  test    rax, rax
0x18003987d  jz      short loc_18003989D
0x18003987f  mov     rax, [rax]
0x180039882  mov     edx, 7F0h
0x180039887  mov     rax, [rax+8]
0x18003988b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039890  test    eax, eax
0x180039892  jz      short loc_18003989D
0x180039894  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003989b  jmp     short loc_1800398AB
0x18003989d  lea     rcx, qword_180069A90; this
0x1800398a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800398ab  cmp     [rcx+8], r12b
0x1800398af  jz      short loc_1800398D2
0x1800398b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800398b6  cmp     [rax+7CCh], ebx
0x1800398bc  jz      short loc_1800398D2
0x1800398be  mov     r9d, ebx; int
0x1800398c1  mov     r8d, 3E8h; int
0x1800398c7  mov     rdx, r13; char *
0x1800398ca  mov     rcx, rax; this
0x1800398cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800398d2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800398d7  cmp     al, 1
0x1800398d9  jb      loc_180039A3B
0x1800398df  mov     edx, 9Ch
0x1800398e4  jmp     loc_180039A1D
0x1800398e9  test    rsi, rsi
0x1800398ec  jz      loc_180039A3B
0x1800398f2  mov     r8, [rbp+var_18]; struct IMFAttributes *
0x1800398f6  mov     rdx, rsi; struct IMFAttributes *
0x1800398f9  mov     rcx, rdi; this
0x1800398fc  call    ?AddOriginalStreamAttrs@CTranscodeProfileAdjuster_FillWithSource@@AEAAJPEAUIMFAttributes@@0@Z; CTranscodeProfileAdjuster_FillWithSource::AddOriginalStreamAttrs(IMFAttributes *,IMFAttributes *)
0x180039901  mov     ebx, eax
0x180039903  test    eax, eax
0x180039905  jns     loc_180039A3B
0x18003990b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
