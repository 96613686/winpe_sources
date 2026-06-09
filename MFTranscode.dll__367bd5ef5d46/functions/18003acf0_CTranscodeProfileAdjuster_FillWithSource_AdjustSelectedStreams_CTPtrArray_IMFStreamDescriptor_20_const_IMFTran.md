# CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams(CTPtrArray<IMFStreamDescriptor,20> const &,IMFTranscodeProfile *,CTPtrArray<IMFStreamDescriptor,20> * *,IMFTranscodeProfile * *)

- ea: `0x18003acf0`
- end: `0x18003b583`
- name: `?AdjustSelectedStreams@CTranscodeProfileAdjuster_FillWithSource@@UEAAJAEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@PEAUIMFTranscodeProfile@@PEAPEAV2@PEAPEAU3@@Z`
- size: `2195`
- prototype: `__int64 __usercall@<rax>(CTranscodeProfileAdjuster_FillWithSource *this@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x180017074`
- `0x18001a330`
- `0x18001c050`
- `0x18001c280`
- `0x1800387d0`
- `0x180038a10`
- `0x180039450`
- `0x18003acf0`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ad6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ae3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003af03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003afaf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b074`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b120`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b1d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b276`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b326`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b3d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b49c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ad6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ae3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003af03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003afaf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b074`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b120`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b1d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b276`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b326`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b3d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b49c`
- `MFPlat!MFCreateAttributes` at `0x18003b25a`
- `MFPlat!MFCreateAttributes` at `0x18003b25a`

## pseudocode

```c
__int64 __fastcall CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams(
        CTranscodeProfileAdjuster_FillWithSource *this,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5)
{
  _QWORD *v8; // rax
  __int64 v9; // rdx
  HRESULT v10; // edi
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  void *v15; // rax
  __int64 v16; // rdx
  void *v17; // rsi
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  IMFTranscodeProfile *v23; // rbx
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
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
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  IMFTranscodeProfile **v56; // rax
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v61; // [rsp+30h] [rbp-30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+38h] [rbp-28h] BYREF
  __int64 v63; // [rsp+40h] [rbp-20h] BYREF
  __int64 v64; // [rsp+48h] [rbp-18h] BYREF
  GUID Buf2; // [rsp+50h] [rbp-10h] BYREF
  IMFTranscodeProfile *ppTranscodeProfile; // [rsp+A0h] [rbp+40h] BYREF
  UINT32 cInitialSize; // [rsp+B8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&ppTranscodeProfile,
    "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
    912);
  v8 = a5;
  *a4 = 0;
  ppMFAttributes = 0;
  *v8 = 0;
  v61 = 0;
  ppTranscodeProfile = 0;
  v64 = 0;
  v63 = 0;
  cInitialSize = 0;
  v10 = MFCreateTranscodeProfile(&ppTranscodeProfile);
  if ( v10 < 0 )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
          926,
          v10);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 140;
LABEL_126:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids, this, v10);
      goto LABEL_127;
    }
    goto LABEL_127;
  }
  v15 = operator new(0xD0u);
  if ( v15 )
  {
    v17 = (void *)CTPtrArray<IMFStreamDescriptor,20>::CTPtrArray<IMFStreamDescriptor,20>(v15);
    if ( v17 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 32LL))(a3, &v64);
      if ( v10 >= 0 )
      {
        v23 = ppTranscodeProfile;
        Buf2 = MFMediaType_Audio;
        v10 = CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream(
                this,
                &Buf2,
                (__int64)v17,
                (__int64)ppTranscodeProfile);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v63);
          if ( v10 >= 0 )
          {
            Buf2 = MFMediaType_Video;
            v10 = CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream(
                    this,
                    &Buf2,
                    (__int64)v17,
                    (__int64)v23);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 64LL))(a3, &v61);
              if ( v10 >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v61 + 240LL))(v61, &cInitialSize);
                if ( v10 >= 0 )
                {
                  v10 = MFCreateAttributes(&ppMFAttributes, cInitialSize);
                  if ( v10 >= 0 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v61 + 256LL))(
                            v61,
                            ppMFAttributes);
                    if ( v10 >= 0 )
                    {
                      v10 = ((__int64 (__fastcall *)(IMFTranscodeProfile *, IMFAttributes *))v23->lpVtbl->SetContainerAttributes)(
                              v23,
                              ppMFAttributes);
                      if ( v10 >= 0 )
                      {
                        v56 = (IMFTranscodeProfile **)a5;
                        *a4 = v17;
                        ppTranscodeProfile = 0;
                        *v56 = v23;
                        goto LABEL_127;
                      }
                      v53 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52);
                        CallStackTracing::s_wpInstance = v54;
                        if ( v54
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(
                               v54,
                               2032) )
                        {
                          v53 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v53 = &qword_180069A90;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                        }
                      }
                      if ( *((_BYTE *)v53 + 8) )
                      {
                        v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
                        if ( *((_DWORD *)v55 + 499) != v10 )
                          CallStackContext::TraceFailure(
                            v55,
                            "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
                            951,
                            v10);
                      }
                      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        goto LABEL_114;
                      v22 = 150;
                    }
                    else
                    {
                      v49 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
                        CallStackTracing::s_wpInstance = v50;
                        if ( v50
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(
                               v50,
                               2032) )
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
                        if ( *((_DWORD *)v51 + 499) != v10 )
                          CallStackContext::TraceFailure(
                            v51,
                            "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
                            950,
                            v10);
                      }
                      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        goto LABEL_114;
                      v22 = 149;
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
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(
                             v46,
                             2032) )
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
                      if ( *((_DWORD *)v47 + 499) != v10 )
                        CallStackContext::TraceFailure(
                          v47,
                          "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
                          949,
                          v10);
                    }
                    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      goto LABEL_114;
                    v22 = 148;
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
                    if ( *((_DWORD *)v43 + 499) != v10 )
                      CallStackContext::TraceFailure(
                        v43,
                        "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
                        948,
                        v10);
                  }
                  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    goto LABEL_114;
                  v22 = 147;
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
                  if ( *((_DWORD *)v39 + 499) != v10 )
                    CallStackContext::TraceFailure(
                      v39,
                      "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
                      947,
                      v10);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_114;
                v22 = 146;
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
                if ( *((_DWORD *)v35 + 499) != v10 )
                  CallStackContext::TraceFailure(
                    v35,
                    "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
                    945,
                    v10);
              }
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_114;
              v22 = 145;
            }
          }
          else
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
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
              if ( *((_DWORD *)v31 + 499) != v10 )
                CallStackContext::TraceFailure(
                  v31,
                  "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
                  939,
                  v10);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_114;
            v22 = 144;
          }
        }
        else
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v25 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v25 + 8) )
          {
            v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
            if ( *((_DWORD *)v27 + 499) != v10 )
              CallStackContext::TraceFailure(
                v27,
                "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
                937,
                v10);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_114;
          v22 = 143;
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
          if ( *((_DWORD *)v21 + 499) != v10 )
            CallStackContext::TraceFailure(
              v21,
              "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
              931,
              v10);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_114;
        v22 = 142;
      }
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids, this, v10);
LABEL_114:
      CTPtrArray<IMFStreamDescriptor,20>::`scalar deleting destructor'(v17);
      goto LABEL_127;
    }
  }
  v57 = (__int64 *)CallStackTracing::s_wpInstance;
  v10 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
    CallStackTracing::s_wpInstance = v58;
    if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
    {
      v57 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v57 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v57 + 8) )
  {
    v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
    if ( *((_DWORD *)v59 + 499) != -2147024882 )
      CallStackContext::TraceFailure(
        v59,
        "CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStreams",
        929,
        -2147024882);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v14 = 141;
    goto LABEL_126;
  }
LABEL_127:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v63);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v64);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppTranscodeProfile);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v61);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFAttributes);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&ppTranscodeProfile);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003acf0  mov     [rsp-38h+arg_8], rbx
0x18003acf5  push    rbp
0x18003acf6  push    rsi
0x18003acf7  push    rdi
0x18003acf8  push    r12
0x18003acfa  push    r13
0x18003acfc  push    r14
0x18003acfe  push    r15
0x18003ad00  mov     rbp, rsp
0x18003ad03  sub     rsp, 60h
0x18003ad07  mov     r15, r8
0x18003ad0a  mov     r12, rdx
0x18003ad0d  mov     r14, rcx
0x18003ad10  lea     rdx, aCtranscodeprof_3; "CTranscodeProfileAdjuster_FillWithSourc"...
0x18003ad17  mov     r8d, 390h; int
0x18003ad1d  lea     rcx, [rbp+ppTranscodeProfile]; this
0x18003ad21  mov     r13, r9
0x18003ad24  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003ad29  mov     rax, [rbp+arg_20]
0x18003ad2d  lea     rcx, [rbp+ppTranscodeProfile]; ppTranscodeProfile
0x18003ad31  xor     ebx, ebx
0x18003ad33  mov     [r13+0], rbx
0x18003ad37  mov     [rbp+ppMFAttributes], rbx
0x18003ad3b  mov     [rax], rbx
0x18003ad3e  mov     [rbp+var_30], rbx
0x18003ad42  mov     [rbp+ppTranscodeProfile], rbx
0x18003ad46  mov     [rbp+var_18], rbx
0x18003ad4a  mov     [rbp+var_20], rbx
0x18003ad4e  mov     [rbp+cInitialSize], ebx
0x18003ad51  call    MFCreateTranscodeProfile
0x18003ad56  mov     edi, eax
0x18003ad58  test    eax, eax
0x18003ad5a  jns     loc_18003ADEE
0x18003ad60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad67  test    rcx, rcx
0x18003ad6a  jnz     short loc_18003ADAD
0x18003ad6c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ad72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad79  mov     rcx, rax
0x18003ad7c  test    rax, rax
0x18003ad7f  jz      short loc_18003AD9F
0x18003ad81  mov     rax, [rax]
0x18003ad84  mov     edx, 7F0h
0x18003ad89  mov     rax, [rax+8]
0x18003ad8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad92  test    eax, eax
0x18003ad94  jz      short loc_18003AD9F
0x18003ad96  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad9d  jmp     short loc_18003ADAD
0x18003ad9f  lea     rcx, qword_180069A90; this
0x18003ada6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003adad  cmp     [rcx+8], bl
0x18003adb0  jz      short loc_18003ADD7
0x18003adb2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003adb7  cmp     [rax+7CCh], edi
0x18003adbd  jz      short loc_18003ADD7
0x18003adbf  mov     r9d, edi; int
0x18003adc2  lea     rdx, aCtranscodeprof_3; "CTranscodeProfileAdjuster_FillWithSourc"...
0x18003adc9  mov     r8d, 39Eh; int
0x18003adcf  mov     rcx, rax; this
0x18003add2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003add7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003addc  cmp     al, 1
0x18003adde  jb      loc_18003B533
0x18003ade4  mov     edx, 8Ch
0x18003ade9  jmp     loc_18003B515
0x18003adee  mov     ecx, 0D0h; Size
0x18003adf3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003adf8  test    rax, rax
0x18003adfb  jz      loc_18003B48B
0x18003ae01  mov     rcx, rax
0x18003ae04  call    ??0?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEAA@XZ; CTPtrArray<IMFStreamDescriptor,20>::CTPtrArray<IMFStreamDescriptor,20>(void)
0x18003ae09  mov     rsi, rax
0x18003ae0c  test    rax, rax
0x18003ae0f  jz      loc_18003B48B
0x18003ae15  mov     rax, [r15]
0x18003ae18  lea     rdx, [rbp+var_18]
0x18003ae1c  mov     rcx, r15
0x18003ae1f  mov     rax, [rax+20h]
0x18003ae23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae28  mov     edi, eax
0x18003ae2a  test    eax, eax
0x18003ae2c  jns     loc_18003AEC0
0x18003ae32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ae39  test    rcx, rcx
0x18003ae3c  jnz     short loc_18003AE7F
0x18003ae3e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ae44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ae4b  mov     rcx, rax
0x18003ae4e  test    rax, rax
0x18003ae51  jz      short loc_18003AE71
0x18003ae53  mov     rax, [rax]
0x18003ae56  mov     edx, 7F0h
0x18003ae5b  mov     rax, [rax+8]
0x18003ae5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae64  test    eax, eax
0x18003ae66  jz      short loc_18003AE71
0x18003ae68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ae6f  jmp     short loc_18003AE7F
0x18003ae71  lea     rcx, qword_180069A90; this
0x18003ae78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ae7f  cmp     [rcx+8], bl
0x18003ae82  jz      short loc_18003AEA9
0x18003ae84  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ae89  cmp     [rax+7CCh], edi
0x18003ae8f  jz      short loc_18003AEA9
0x18003ae91  mov     r9d, edi; int
0x18003ae94  lea     rdx, aCtranscodeprof_3; "CTranscodeProfileAdjuster_FillWithSourc"...
0x18003ae9b  mov     r8d, 3A3h; int
0x18003aea1  mov     rcx, rax; this
0x18003aea4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003aea9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003aeae  cmp     al, 1
0x18003aeb0  jb      loc_18003B46A
0x18003aeb6  mov     edx, 8Eh
0x18003aebb  jmp     loc_18003B44C
0x18003aec0  movups  xmm0, xmmword ptr cs:MFMediaType_Audio.Data1
0x18003aec7  mov     rbx, [rbp+ppTranscodeProfile]
0x18003aecb  lea     rdx, [rbp+Buf2]; Buf2
0x18003aecf  mov     r9, [rbp+var_18]
0x18003aed3  mov     r8, r12
0x18003aed6  mov     [rsp+60h+var_38], rbx; __int64
0x18003aedb  mov     rcx, r14; this
0x18003aede  movdqu  [rbp+Buf2], xmm0
0x18003aee3  mov     [rsp+60h+var_40], rsi; __int64
0x18003aee8  call    ?AdjustSelectedStream@CTranscodeProfileAdjuster_FillWithSource@@AEAAJU_GUID@@AEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@PEAUIMFAttributes@@PEAV3@PEAUIMFTranscodeProfile@@@Z; CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream(_GUID,CTPtrArray<IMFStreamDescriptor,20> const &,IMFAttributes *,CTPtrArray<IMFStreamDescriptor,20> *,IMFTranscodeProfile *)
0x18003aeed  mov     edi, eax
0x18003aeef  test    eax, eax
0x18003aef1  jns     loc_18003AF86
0x18003aef7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aefe  test    rcx, rcx
0x18003af01  jnz     short loc_18003AF44
0x18003af03  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003af09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003af10  mov     rcx, rax
0x18003af13  test    rax, rax
0x18003af16  jz      short loc_18003AF36
0x18003af18  mov     rax, [rax]
0x18003af1b  mov     edx, 7F0h
0x18003af20  mov     rax, [rax+8]
0x18003af24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af29  test    eax, eax
0x18003af2b  jz      short loc_18003AF36
0x18003af2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003af34  jmp     short loc_18003AF44
0x18003af36  lea     rcx, qword_180069A90; this
0x18003af3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003af44  cmp     byte ptr [rcx+8], 0
0x18003af48  jz      short loc_18003AF6F
0x18003af4a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003af4f  cmp     [rax+7CCh], edi
0x18003af55  jz      short loc_18003AF6F
0x18003af57  mov     r9d, edi; int
0x18003af5a  lea     rdx, aCtranscodeprof_3; "CTranscodeProfileAdjuster_FillWithSourc"...
0x18003af61  mov     r8d, 3A9h; int
0x18003af67  mov     rcx, rax; this
0x18003af6a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003af6f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003af74  cmp     al, 1
0x18003af76  jb      loc_18003B46A
0x18003af7c  mov     edx, 8Fh
0x18003af81  jmp     loc_18003B44C
0x18003af86  mov     rax, [r15]
0x18003af89  lea     rdx, [rbp+var_20]
0x18003af8d  mov     rcx, r15
0x18003af90  mov     rax, [rax+30h]
0x18003af94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af99  mov     edi, eax
0x18003af9b  test    eax, eax
0x18003af9d  jns     loc_18003B032
0x18003afa3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003afaa  test    rcx, rcx
0x18003afad  jnz     short loc_18003AFF0
0x18003afaf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003afb5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003afbc  mov     rcx, rax
0x18003afbf  test    rax, rax
0x18003afc2  jz      short loc_18003AFE2
0x18003afc4  mov     rax, [rax]
0x18003afc7  mov     edx, 7F0h
0x18003afcc  mov     rax, [rax+8]
0x18003afd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afd5  test    eax, eax
0x18003afd7  jz      short loc_18003AFE2
0x18003afd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003afe0  jmp     short loc_18003AFF0
0x18003afe2  lea     rcx, qword_180069A90; this
0x18003afe9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aff0  cmp     byte ptr [rcx+8], 0
0x18003aff4  jz      short loc_18003B01B
0x18003aff6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003affb  cmp     [rax+7CCh], edi
0x18003b001  jz      short loc_18003B01B
0x18003b003  mov     r9d, edi; int
0x18003b006  lea     rdx, aCtranscodeprof_3; "CTranscodeProfileAdjuster_FillWithSourc"...
0x18003b00d  mov     r8d, 3ABh; int
0x18003b013  mov     rcx, rax; this
0x18003b016  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b01b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b020  cmp     al, 1
0x18003b022  jb      loc_18003B46A
0x18003b028  mov     edx, 90h
0x18003b02d  jmp     loc_18003B44C
0x18003b032  movups  xmm0, xmmword ptr cs:MFMediaType_Video.Data1
0x18003b039  mov     r9, [rbp+var_20]
0x18003b03d  lea     rdx, [rbp+Buf2]; Buf2
0x18003b041  mov     [rsp+60h+var_38], rbx; __int64
0x18003b046  mov     r8, r12
0x18003b049  mov     rcx, r14; this
0x18003b04c  mov     [rsp+60h+var_40], rsi; __int64
0x18003b051  movdqu  [rbp+Buf2], xmm0
0x18003b056  call    ?AdjustSelectedStream@CTranscodeProfileAdjuster_FillWithSource@@AEAAJU_GUID@@AEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@PEAUIMFAttributes@@PEAV3@PEAUIMFTranscodeProfile@@@Z; CTranscodeProfileAdjuster_FillWithSource::AdjustSelectedStream(_GUID,CTPtrArray<IMFStreamDescriptor,20> const &,IMFAttributes *,CTPtrArray<IMFStreamDescriptor,20> *,IMFTranscodeProfile *)
0x18003b05b  xor     r12d, r12d
0x18003b05e  mov     edi, eax
0x18003b060  test    eax, eax
0x18003b062  jns     loc_18003B0F7
0x18003b068  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b06f  test    rcx, rcx
0x18003b072  jnz     short loc_18003B0B5
0x18003b074  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b07a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b081  mov     rcx, rax
0x18003b084  test    rax, rax
0x18003b087  jz      short loc_18003B0A7
0x18003b089  mov     rax, [rax]
0x18003b08c  mov     edx, 7F0h
0x18003b091  mov     rax, [rax+8]
0x18003b095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b09a  test    eax, eax
0x18003b09c  jz      short loc_18003B0A7
0x18003b09e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b0a5  jmp     short loc_18003B0B5
0x18003b0a7  lea     rcx, qword_180069A90; this
0x18003b0ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b0b5  cmp     [rcx+8], r12b
0x18003b0b9  jz      short loc_18003B0E0
0x18003b0bb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b0c0  cmp     [rax+7CCh], edi
0x18003b0c6  jz      short loc_18003B0E0
0x18003b0c8  mov     r9d, edi; int
0x18003b0cb  lea     rdx, aCtranscodeprof_3; "CTranscodeProfileAdjuster_FillWithSourc"...
0x18003b0d2  mov     r8d, 3B1h; int
0x18003b0d8  mov     rcx, rax; this
0x18003b0db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b0e0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b0e5  cmp     al, 1
0x18003b0e7  jb      loc_18003B46A
0x18003b0ed  mov     edx, 91h
0x18003b0f2  jmp     loc_18003B44C
0x18003b0f7  mov     rax, [r15]
0x18003b0fa  lea     rdx, [rbp+var_30]
0x18003b0fe  mov     rcx, r15
0x18003b101  mov     rax, [rax+40h]
0x18003b105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b10a  mov     edi, eax
0x18003b10c  test    eax, eax
0x18003b10e  jns     loc_18003B1A3
0x18003b114  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b11b  test    rcx, rcx
0x18003b11e  jnz     short loc_18003B161
0x18003b120  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b126  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b12d  mov     rcx, rax
0x18003b130  test    rax, rax
0x18003b133  jz      short loc_18003B153
0x18003b135  mov     rax, [rax]
0x18003b138  mov     edx, 7F0h
0x18003b13d  mov     rax, [rax+8]
0x18003b141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b146  test    eax, eax
0x18003b148  jz      short loc_18003B153
0x18003b14a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b151  jmp     short loc_18003B161
0x18003b153  lea     rcx, qword_180069A90; this
0x18003b15a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b161  cmp     [rcx+8], r12b
0x18003b165  jz      short loc_18003B18C
0x18003b167  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b16c  cmp     [rax+7CCh], edi
0x18003b172  jz      short loc_18003B18C
0x18003b174  mov     r9d, edi; int
0x18003b177  lea     rdx, aCtranscodeprof_3; "CTranscodeProfileAdjuster_FillWithSourc"...
0x18003b17e  mov     r8d, 3B3h; int
0x18003b184  mov     rcx, rax; this
0x18003b187  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b18c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b191  cmp     al, 1
0x18003b193  jb      loc_18003B46A
0x18003b199  mov     edx, 92h
0x18003b19e  jmp     loc_18003B44C
0x18003b1a3  mov     rcx, [rbp+var_30]
0x18003b1a7  lea     rdx, [rbp+cInitialSize]
0x18003b1ab  mov     rax, [rcx]
0x18003b1ae  mov     rax, [rax+0F0h]
0x18003b1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1ba  mov     edi, eax
0x18003b1bc  test    eax, eax
0x18003b1be  jns     loc_18003B253
0x18003b1c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b1cb  test    rcx, rcx
  ... truncated ...
```
