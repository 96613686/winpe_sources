# MFCreateTranscodeTopology

- ea: `0x180036820`
- end: `0x1800370f8`
- name: `MFCreateTranscodeTopology`
- size: `2264`
- prototype: `HRESULT __stdcall(IMFMediaSource *pSrc, LPCWSTR pwszOutputFilePath, IMFTranscodeProfile *pProfile, IMFTopology **ppTranscodeTopo)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002260`
- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180009820`
- `0x18001a330`
- `0x18001c280`
- `0x180035498`
- `0x180036820`
- `0x180037100`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800368a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036962`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036a00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036aa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036b42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036bfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036ca9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036d55`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036e01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036ea3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036f70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003701b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800368a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036962`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036a00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036aa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036b42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036bfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036ca9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036d55`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036e01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036ea3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036f70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003701b`

## string_xrefs

- `0x18003683d`: `MFCreateTranscodeTopology`
- `0x1800368fc`: `MFCreateTranscodeTopology`
- `0x1800369b9`: `MFCreateTranscodeTopology`
- `0x180036a57`: `MFCreateTranscodeTopology`
- `0x180036afa`: `MFCreateTranscodeTopology`
- `0x180036b99`: `MFCreateTranscodeTopology`
- `0x180036c51`: `MFCreateTranscodeTopology`
- `0x180036d00`: `MFCreateTranscodeTopology`
- `0x180036dac`: `MFCreateTranscodeTopology`
- `0x180036e58`: `MFCreateTranscodeTopology`
- `0x180036efa`: `MFCreateTranscodeTopology`
- `0x180036fc7`: `MFCreateTranscodeTopology`
- `0x180037072`: `MFCreateTranscodeTopology`

## pseudocode

```c
HRESULT __stdcall MFCreateTranscodeTopology(
        IMFMediaSource *pSrc,
        LPCWSTR pwszOutputFilePath,
        IMFTranscodeProfile *pProfile,
        IMFTopology **ppTranscodeTopo)
{
  __int64 v8; // rdx
  int v9; // ecx
  int v10; // r9d
  struct IMFTranscodeManagerPriv *v11; // rsi
  __int64 *v12; // rcx
  int v13; // ebx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  struct IMFTranscodeConfigPriv *v31; // r13
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
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
  __int64 v56; // rdx
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  struct IMFTranscodeManagerPriv *v61; // [rsp+30h] [rbp-18h] BYREF
  struct IMFTranscodeConfigPriv *v62; // [rsp+38h] [rbp-10h] BYREF
  int v63; // [rsp+90h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v63, "MFCreateTranscodeTopology", 204);
  v11 = 0;
  v62 = 0;
  v61 = 0;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    v63 = 1229996372;
    McTemplateU0s4pd_EventWriteTransfer(
      v9,
      (unsigned int)Transcode_Create_Transcode_Topology_Begin,
      (unsigned int)&v63,
      v10,
      0);
  }
  if ( !pSrc )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    v13 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFCreateTranscodeTopology", 214, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v16 = 25;
LABEL_14:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids,
        0,
        -2147467261);
      goto LABEL_143;
    }
    goto LABEL_143;
  }
  if ( pwszOutputFilePath )
  {
    if ( !*pwszOutputFilePath )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      v13 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
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
        if ( *((_DWORD *)v22 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v22, "MFCreateTranscodeTopology", 216, -2147024809);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids,
          0,
          -2147024809);
      goto LABEL_143;
    }
    if ( !pProfile )
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      v13 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
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
        if ( *((_DWORD *)v25 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v25, "MFCreateTranscodeTopology", 217, -2147467261);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v16 = 28;
        goto LABEL_14;
      }
      goto LABEL_143;
    }
    if ( !ppTranscodeTopo )
    {
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      v13 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
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
        if ( *((_DWORD *)v28 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v28, "MFCreateTranscodeTopology", 218, -2147467261);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v16 = 29;
        goto LABEL_14;
      }
      goto LABEL_143;
    }
    TryDumpTranscodeProfile(pProfile, L"TranscodeAPI\\DumpProfile");
    v29 = CTranscodeConfig::CreateInstance(&v62);
    v31 = v62;
    v13 = v29;
    if ( v29 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(struct IMFTranscodeConfigPriv *, IMFMediaSource *))(*(_QWORD *)v62 + 24LL))(
              v62,
              pSrc);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(struct IMFTranscodeConfigPriv *, LPCWSTR))(*(_QWORD *)v31 + 40LL))(
                v31,
                pwszOutputFilePath);
        if ( v13 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(struct IMFTranscodeConfigPriv *, IMFTranscodeProfile *))(*(_QWORD *)v31 + 72LL))(
                  v31,
                  pProfile);
          if ( v13 >= 0 )
          {
            v13 = CTranscodeManager::CreateInstance(&v61);
            if ( v13 < 0 )
            {
              v49 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
                CallStackTracing::s_wpInstance = v50;
                if ( v50
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
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
                if ( *((_DWORD *)v51 + 499) != v13 )
                  CallStackContext::TraceFailure(v51, "MFCreateTranscodeTopology", 227, v13);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                WPP_SF_qd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  34,
                  &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids,
                  0,
                  v13);
              v11 = v61;
              goto LABEL_139;
            }
            v11 = v61;
            v13 = (*(__int64 (__fastcall **)(struct IMFTranscodeManagerPriv *, struct IMFTranscodeConfigPriv *))(*(_QWORD *)v61 + 24LL))(
                    v61,
                    v31);
            if ( v13 >= 0 )
            {
              v13 = (*(__int64 (__fastcall **)(struct IMFTranscodeManagerPriv *, IMFTopology **))(*(_QWORD *)v11 + 32LL))(
                      v11,
                      ppTranscodeTopo);
              if ( v13 >= 0 )
                goto LABEL_139;
              v57 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56);
                CallStackTracing::s_wpInstance = v58;
                if ( v58
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
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
                if ( *((_DWORD *)v59 + 499) != v13 )
                  CallStackContext::TraceFailure(v59, "MFCreateTranscodeTopology", 229, v13);
              }
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_139;
              v35 = 36;
            }
            else
            {
              v53 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52);
                CallStackTracing::s_wpInstance = v54;
                if ( v54
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
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
                if ( *((_DWORD *)v55 + 499) != v13 )
                  CallStackContext::TraceFailure(v55, "MFCreateTranscodeTopology", 228, v13);
              }
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_139;
              v35 = 35;
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
              if ( *((_DWORD *)v47 + 499) != v13 )
                CallStackContext::TraceFailure(v47, "MFCreateTranscodeTopology", 225, v13);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_139;
            v35 = 33;
          }
        }
        else
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
            CallStackTracing::s_wpInstance = v42;
            if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
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
            if ( *((_DWORD *)v43 + 499) != v13 )
              CallStackContext::TraceFailure(v43, "MFCreateTranscodeTopology", 224, v13);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_139;
          v35 = 32;
        }
      }
      else
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
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
          if ( *((_DWORD *)v39 + 499) != v13 )
            CallStackContext::TraceFailure(v39, "MFCreateTranscodeTopology", 223, v13);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_139;
        v35 = 31;
      }
    }
    else
    {
      v32 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
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
        if ( *((_DWORD *)v34 + 499) != v13 )
          CallStackContext::TraceFailure(v34, "MFCreateTranscodeTopology", 222, v13);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_139;
      v35 = 30;
    }
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids, 0, v13);
LABEL_139:
    if ( v31 )
      (*(void (__fastcall **)(struct IMFTranscodeConfigPriv *))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v11 )
      (*(void (__fastcall **)(struct IMFTranscodeManagerPriv *))(*(_QWORD *)v11 + 16LL))(v11);
    goto LABEL_143;
  }
  v17 = (__int64 *)CallStackTracing::s_wpInstance;
  v13 = -2147467261;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
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
    if ( *((_DWORD *)v19 + 499) != -2147467261 )
      CallStackContext::TraceFailure(v19, "MFCreateTranscodeTopology", 215, -2147467261);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v16 = 26;
    goto LABEL_14;
  }
LABEL_143:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v63);
  return v13;
}

```

## disassembly

```asm
0x180036820  push    rbp
0x180036822  push    rbx
0x180036823  push    rsi
0x180036824  push    rdi
0x180036825  push    r12
0x180036827  push    r13
0x180036829  push    r14
0x18003682b  push    r15
0x18003682d  mov     rbp, rsp
0x180036830  sub     rsp, 48h
0x180036834  mov     r14, r8
0x180036837  mov     rdi, rdx
0x18003683a  mov     r15, rcx
0x18003683d  lea     rdx, aMfcreatetransc_6; "MFCreateTranscodeTopology"
0x180036844  mov     r8d, 0CCh; int
0x18003684a  lea     rcx, [rbp+arg_0]; this
0x18003684e  mov     r12, r9
0x180036851  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180036856  xor     r13d, r13d
0x180036859  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180036860  mov     esi, r13d
0x180036863  mov     [rbp+var_10], r13
0x180036867  mov     [rbp+var_18], r13
0x18003686b  jz      short loc_180036889
0x18003686d  lea     r8, [rbp+arg_0]
0x180036871  mov     [rbp+arg_0], 49504154h
0x180036878  lea     rdx, Transcode_Create_Transcode_Topology_Begin
0x18003687f  mov     [rsp+48h+var_28], r13d
0x180036884  call    McTemplateU0s4pd_EventWriteTransfer
0x180036889  test    r15, r15
0x18003688c  jnz     loc_180036946
0x180036892  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036899  mov     edi, 80004003h
0x18003689e  mov     ebx, edi
0x1800368a0  test    rcx, rcx
0x1800368a3  jnz     short loc_1800368E6
0x1800368a5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800368ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800368b2  mov     rcx, rax
0x1800368b5  test    rax, rax
0x1800368b8  jz      short loc_1800368D8
0x1800368ba  mov     rax, [rax]
0x1800368bd  mov     edx, 7F0h
0x1800368c2  mov     rax, [rax+8]
0x1800368c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368cb  test    eax, eax
0x1800368cd  jz      short loc_1800368D8
0x1800368cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800368d6  jmp     short loc_1800368E6
0x1800368d8  lea     rcx, qword_180069A90; this
0x1800368df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800368e6  cmp     [rcx+8], r13b
0x1800368ea  jz      short loc_180036911
0x1800368ec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800368f1  cmp     [rax+7CCh], edi
0x1800368f7  jz      short loc_180036911
0x1800368f9  mov     r9d, edi; int
0x1800368fc  lea     rdx, aMfcreatetransc_6; "MFCreateTranscodeTopology"
0x180036903  mov     r8d, 0D6h; int
0x180036909  mov     rcx, rax; this
0x18003690c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036911  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180036916  cmp     al, 1
0x180036918  jb      loc_1800370DC
0x18003691e  mov     edx, 19h
0x180036923  mov     [rsp+48h+var_28], edi
0x180036927  mov     rcx, cs:WPP_GLOBAL_Control
0x18003692e  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x180036935  xor     r9d, r9d
0x180036938  mov     rcx, [rcx+10h]
0x18003693c  call    WPP_SF_qd
0x180036941  jmp     loc_1800370DC
0x180036946  test    rdi, rdi
0x180036949  jnz     loc_1800369E5
0x18003694f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036956  mov     edi, 80004003h
0x18003695b  mov     ebx, edi
0x18003695d  test    rcx, rcx
0x180036960  jnz     short loc_1800369A3
0x180036962  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036968  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003696f  mov     rcx, rax
0x180036972  test    rax, rax
0x180036975  jz      short loc_180036995
0x180036977  mov     rax, [rax]
0x18003697a  mov     edx, 7F0h
0x18003697f  mov     rax, [rax+8]
0x180036983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036988  test    eax, eax
0x18003698a  jz      short loc_180036995
0x18003698c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036993  jmp     short loc_1800369A3
0x180036995  lea     rcx, qword_180069A90; this
0x18003699c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800369a3  cmp     [rcx+8], r13b
0x1800369a7  jz      short loc_1800369CE
0x1800369a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800369ae  cmp     [rax+7CCh], edi
0x1800369b4  jz      short loc_1800369CE
0x1800369b6  mov     r9d, edi; int
0x1800369b9  lea     rdx, aMfcreatetransc_6; "MFCreateTranscodeTopology"
0x1800369c0  mov     r8d, 0D7h; int
0x1800369c6  mov     rcx, rax; this
0x1800369c9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800369ce  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800369d3  cmp     al, 1
0x1800369d5  jb      loc_1800370DC
0x1800369db  mov     edx, 1Ah
0x1800369e0  jmp     loc_180036923
0x1800369e5  cmp     [rdi], r13w
0x1800369e9  jnz     loc_180036A87
0x1800369ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800369f6  mov     ebx, 80070057h
0x1800369fb  test    rcx, rcx
0x1800369fe  jnz     short loc_180036A41
0x180036a00  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036a06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036a0d  mov     rcx, rax
0x180036a10  test    rax, rax
0x180036a13  jz      short loc_180036A33
0x180036a15  mov     rax, [rax]
0x180036a18  mov     edx, 7F0h
0x180036a1d  mov     rax, [rax+8]
0x180036a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a26  test    eax, eax
0x180036a28  jz      short loc_180036A33
0x180036a2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036a31  jmp     short loc_180036A41
0x180036a33  lea     rcx, qword_180069A90; this
0x180036a3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036a41  cmp     [rcx+8], r13b
0x180036a45  jz      short loc_180036A6C
0x180036a47  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036a4c  cmp     [rax+7CCh], ebx
0x180036a52  jz      short loc_180036A6C
0x180036a54  mov     r9d, ebx; int
0x180036a57  lea     rdx, aMfcreatetransc_6; "MFCreateTranscodeTopology"
0x180036a5e  mov     r8d, 0D8h; int
0x180036a64  mov     rcx, rax; this
0x180036a67  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036a6c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180036a71  cmp     al, 1
0x180036a73  jb      loc_1800370DC
0x180036a79  mov     edx, 1Bh
0x180036a7e  mov     [rsp+48h+var_28], ebx
0x180036a82  jmp     loc_180036927
0x180036a87  test    r14, r14
0x180036a8a  jnz     loc_180036B26
0x180036a90  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036a97  mov     edi, 80004003h
0x180036a9c  mov     ebx, edi
0x180036a9e  test    rcx, rcx
0x180036aa1  jnz     short loc_180036AE4
0x180036aa3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036aa9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036ab0  mov     rcx, rax
0x180036ab3  test    rax, rax
0x180036ab6  jz      short loc_180036AD6
0x180036ab8  mov     rax, [rax]
0x180036abb  mov     edx, 7F0h
0x180036ac0  mov     rax, [rax+8]
0x180036ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ac9  test    eax, eax
0x180036acb  jz      short loc_180036AD6
0x180036acd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036ad4  jmp     short loc_180036AE4
0x180036ad6  lea     rcx, qword_180069A90; this
0x180036add  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036ae4  cmp     [rcx+8], r13b
0x180036ae8  jz      short loc_180036B0F
0x180036aea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036aef  cmp     [rax+7CCh], edi
0x180036af5  jz      short loc_180036B0F
0x180036af7  mov     r9d, edi; int
0x180036afa  lea     rdx, aMfcreatetransc_6; "MFCreateTranscodeTopology"
0x180036b01  mov     r8d, 0D9h; int
0x180036b07  mov     rcx, rax; this
0x180036b0a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036b0f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180036b14  cmp     al, 1
0x180036b16  jb      loc_1800370DC
0x180036b1c  mov     edx, 1Ch
0x180036b21  jmp     loc_180036923
0x180036b26  test    r12, r12
0x180036b29  jnz     loc_180036BC5
0x180036b2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036b36  mov     edi, 80004003h
0x180036b3b  mov     ebx, edi
0x180036b3d  test    rcx, rcx
0x180036b40  jnz     short loc_180036B83
0x180036b42  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036b48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036b4f  mov     rcx, rax
0x180036b52  test    rax, rax
0x180036b55  jz      short loc_180036B75
0x180036b57  mov     rax, [rax]
0x180036b5a  mov     edx, 7F0h
0x180036b5f  mov     rax, [rax+8]
0x180036b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b68  test    eax, eax
0x180036b6a  jz      short loc_180036B75
0x180036b6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036b73  jmp     short loc_180036B83
0x180036b75  lea     rcx, qword_180069A90; this
0x180036b7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036b83  cmp     [rcx+8], r13b
0x180036b87  jz      short loc_180036BAE
0x180036b89  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036b8e  cmp     [rax+7CCh], edi
0x180036b94  jz      short loc_180036BAE
0x180036b96  mov     r9d, edi; int
0x180036b99  lea     rdx, aMfcreatetransc_6; "MFCreateTranscodeTopology"
0x180036ba0  mov     r8d, 0DAh; int
0x180036ba6  mov     rcx, rax; this
0x180036ba9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036bae  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180036bb3  cmp     al, 1
0x180036bb5  jb      loc_1800370DC
0x180036bbb  mov     edx, 1Dh
0x180036bc0  jmp     loc_180036923
0x180036bc5  lea     rdx, aTranscodeapiDu; "TranscodeAPI\\DumpProfile"
0x180036bcc  mov     rcx, r14; struct IMFTranscodeProfile *
0x180036bcf  call    ?TryDumpTranscodeProfile@@YAJPEAUIMFTranscodeProfile@@PEBG@Z; TryDumpTranscodeProfile(IMFTranscodeProfile *,ushort const *)
0x180036bd4  lea     rcx, [rbp+var_10]; struct IMFTranscodeConfigPriv **
0x180036bd8  call    ?CreateInstance@CTranscodeConfig@@SAJPEAPEAUIMFTranscodeConfigPriv@@@Z; CTranscodeConfig::CreateInstance(IMFTranscodeConfigPriv * *)
0x180036bdd  mov     r13, [rbp+var_10]
0x180036be1  mov     ebx, eax
0x180036be3  test    eax, eax
0x180036be5  jns     loc_180036C7D
0x180036beb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036bf2  xor     r15d, r15d
0x180036bf5  test    rcx, rcx
0x180036bf8  jnz     short loc_180036C3B
0x180036bfa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036c00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036c07  mov     rcx, rax
0x180036c0a  test    rax, rax
0x180036c0d  jz      short loc_180036C2D
0x180036c0f  mov     rax, [rax]
0x180036c12  mov     edx, 7F0h
0x180036c17  mov     rax, [rax+8]
0x180036c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c20  test    eax, eax
0x180036c22  jz      short loc_180036C2D
0x180036c24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036c2b  jmp     short loc_180036C3B
0x180036c2d  lea     rcx, qword_180069A90; this
0x180036c34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036c3b  cmp     [rcx+8], r15b
0x180036c3f  jz      short loc_180036C66
0x180036c41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036c46  cmp     [rax+7CCh], ebx
0x180036c4c  jz      short loc_180036C66
0x180036c4e  mov     r9d, ebx; int
0x180036c51  lea     rdx, aMfcreatetransc_6; "MFCreateTranscodeTopology"
0x180036c58  mov     r8d, 0DEh; int
0x180036c5e  mov     rcx, rax; this
0x180036c61  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036c66  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180036c6b  cmp     al, 1
0x180036c6d  jb      loc_1800370B3
0x180036c73  mov     edx, 1Eh
0x180036c78  jmp     loc_180037095
0x180036c7d  mov     rax, [r13+0]
0x180036c81  mov     rdx, r15
0x180036c84  mov     rcx, r13
0x180036c87  mov     rax, [rax+18h]
0x180036c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c90  xor     r15d, r15d
0x180036c93  mov     ebx, eax
0x180036c95  test    eax, eax
0x180036c97  jns     loc_180036D2C
0x180036c9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036ca4  test    rcx, rcx
0x180036ca7  jnz     short loc_180036CEA
0x180036ca9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036caf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036cb6  mov     rcx, rax
0x180036cb9  test    rax, rax
0x180036cbc  jz      short loc_180036CDC
0x180036cbe  mov     rax, [rax]
0x180036cc1  mov     edx, 7F0h
0x180036cc6  mov     rax, [rax+8]
0x180036cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ccf  test    eax, eax
0x180036cd1  jz      short loc_180036CDC
0x180036cd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036cda  jmp     short loc_180036CEA
0x180036cdc  lea     rcx, qword_180069A90; this
0x180036ce3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036cea  cmp     [rcx+8], r15b
0x180036cee  jz      short loc_180036D15
0x180036cf0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036cf5  cmp     [rax+7CCh], ebx
0x180036cfb  jz      short loc_180036D15
0x180036cfd  mov     r9d, ebx; int
0x180036d00  lea     rdx, aMfcreatetransc_6; "MFCreateTranscodeTopology"
0x180036d07  mov     r8d, 0DFh; int
0x180036d0d  mov     rcx, rax; this
0x180036d10  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
