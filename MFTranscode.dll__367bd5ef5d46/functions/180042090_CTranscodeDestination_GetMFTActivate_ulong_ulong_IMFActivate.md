# CTranscodeDestination::GetMFTActivate(ulong,ulong,IMFActivate * *)

- ea: `0x180042090`
- end: `0x1800428ad`
- name: `?GetMFTActivate@CTranscodeDestination@@IEAAJKKPEAPEAUIMFActivate@@@Z`
- size: `2077`
- prototype: `__int64 __fastcall(CTranscodeDestination *__hidden this, unsigned int, unsigned int, struct IMFActivate **)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041da0`

## callees

- `0x1800026f0`
- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x180042090`
- `0x1800430ec`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004285a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004285a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042134`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042202`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800422b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004237b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004243f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800424f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800425d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800426b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004276a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042134`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042202`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800422b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004237b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004243f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800424f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800425d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800426b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004276a`

## pseudocode

```c
__int64 __fastcall CTranscodeDestination::GetMFTActivate(
        CTranscodeDestination *this,
        unsigned int a2,
        unsigned int a3,
        struct IMFActivate **a4)
{
  _QWORD *v8; // rax
  __int64 (__fastcall *v9)(CTranscodeDestination *, _QWORD, struct IMFMediaType **); // rax
  __int64 v10; // rdx
  int PreferredMFTActivate; // ebx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
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
  int v48; // eax
  struct IMFActivate *v49; // rsi
  _QWORD *v50; // rcx
  unsigned int v51; // eax
  unsigned int i; // edi
  __int64 v53; // rdx
  _BYTE v55[4]; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v56; // [rsp+34h] [rbp-35h] BYREF
  struct IMFAttributes *v57; // [rsp+38h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-29h] BYREF
  struct IMFMediaType *v59; // [rsp+48h] [rbp-21h] BYREF
  __int64 v60; // [rsp+50h] [rbp-19h] BYREF
  __int64 v61; // [rsp+58h] [rbp-11h] BYREF
  struct IMFActivate *v62; // [rsp+60h] [rbp-9h] BYREF
  GUID Buf2; // [rsp+68h] [rbp-1h] BYREF
  struct _GUID v64; // [rsp+78h] [rbp+Fh] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v55, "CTranscodeDestination::GetMFTActivate", 555);
  v8 = *(_QWORD **)this;
  v59 = 0;
  Buf2 = GUID_00000000_0000_0000_0000_000000000000;
  v9 = (__int64 (__fastcall *)(CTranscodeDestination *, _QWORD, struct IMFMediaType **))v8[10];
  v64 = GUID_00000000_0000_0000_0000_000000000000;
  v57 = 0;
  v56 = 0;
  pv = 0;
  v62 = 0;
  v60 = 0;
  v61 = 0;
  PreferredMFTActivate = v9(this, a2, &v59);
  if ( PreferredMFTActivate >= 0 )
  {
    PreferredMFTActivate = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))v59->lpVtbl->GetGUID)(
                             v59,
                             &MF_MT_MAJOR_TYPE,
                             &Buf2);
    if ( PreferredMFTActivate >= 0 )
    {
      PreferredMFTActivate = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, struct _GUID *))v59->lpVtbl->GetGUID)(
                               v59,
                               &MF_MT_SUBTYPE,
                               &v64);
      if ( PreferredMFTActivate >= 0 )
      {
        if ( !memcmp_0(&MFMediaType_Video, &Buf2, 0x10u) )
        {
          PreferredMFTActivate = (*(__int64 (__fastcall **)(_QWORD, struct IMFAttributes **))(**((_QWORD **)this + 1)
                                                                                            + 48LL))(
                                   *((_QWORD *)this + 1),
                                   &v57);
          if ( PreferredMFTActivate < 0 )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
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
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != PreferredMFTActivate )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CTranscodeDestination::GetMFTActivate",
                  577,
                  PreferredMFTActivate);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v15 = 85;
              goto LABEL_12;
            }
            goto LABEL_109;
          }
        }
        else if ( !memcmp_0(&MFMediaType_Audio, &Buf2, 0x10u) )
        {
          PreferredMFTActivate = (*(__int64 (__fastcall **)(_QWORD, struct IMFAttributes **))(**((_QWORD **)this + 1)
                                                                                            + 32LL))(
                                   *((_QWORD *)this + 1),
                                   &v57);
          if ( PreferredMFTActivate < 0 )
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
              if ( *((_DWORD *)v31 + 499) != PreferredMFTActivate )
                CallStackContext::TraceFailure(v31, "CTranscodeDestination::GetMFTActivate", 581, PreferredMFTActivate);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v15 = 86;
              goto LABEL_12;
            }
            goto LABEL_109;
          }
        }
        PreferredMFTActivate = CMFTHelper::EnumMFTActivates(&Buf2, &v64, a3, &v56, (struct IMFActivate ***)&pv);
        if ( PreferredMFTActivate >= 0 )
        {
          if ( ((int (__fastcall *)(struct IMFAttributes *, const GUID *, GUID *, __int64 *))v57->lpVtbl->GetUnknown)(
                 v57,
                 &MFT_FIELDOFUSE_UNLOCK_Attribute,
                 &IID_IUnknown,
                 &v60) < 0
            && (a3 & 8) != 0 )
          {
            PreferredMFTActivate = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 64LL))(
                                     *((_QWORD *)this + 1),
                                     &v61);
            if ( PreferredMFTActivate < 0 )
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
                if ( *((_DWORD *)v39 + 499) != PreferredMFTActivate )
                  CallStackContext::TraceFailure(
                    v39,
                    "CTranscodeDestination::GetMFTActivate",
                    599,
                    PreferredMFTActivate);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v15 = 88;
                goto LABEL_12;
              }
              goto LABEL_109;
            }
            if ( (*(int (__fastcall **)(__int64, const GUID *, GUID *, __int64 *))(*(_QWORD *)v61 + 136LL))(
                   v61,
                   &MFT_FIELDOFUSE_UNLOCK_Attribute,
                   &IID_IUnknown,
                   &v60) >= 0 )
            {
              PreferredMFTActivate = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, __int64))v57->lpVtbl->SetUnknown)(
                                       v57,
                                       &MFT_FIELDOFUSE_UNLOCK_Attribute,
                                       v60);
              if ( PreferredMFTActivate < 0 )
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
                  if ( *((_DWORD *)v43 + 499) != PreferredMFTActivate )
                    CallStackContext::TraceFailure(
                      v43,
                      "CTranscodeDestination::GetMFTActivate",
                      603,
                      PreferredMFTActivate);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v15 = 89;
                  goto LABEL_12;
                }
                goto LABEL_109;
              }
            }
          }
          PreferredMFTActivate = CTranscodeDestination::GetPreferredMFTActivate(
                                   this,
                                   v57,
                                   v59,
                                   (struct IMFActivate **)pv,
                                   v56,
                                   &v62);
          if ( PreferredMFTActivate >= 0 )
          {
            v48 = memcmp_0(&MFMediaType_Video, &Buf2, 0x10u);
            v49 = v62;
            if ( !v48 )
              (*(void (__fastcall **)(CTranscodeDestination *, struct IMFActivate *))(*(_QWORD *)this + 64LL))(
                this,
                v62);
            *a4 = v49;
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
              if ( *((_DWORD *)v47 + 499) != PreferredMFTActivate )
                CallStackContext::TraceFailure(v47, "CTranscodeDestination::GetMFTActivate", 614, PreferredMFTActivate);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v15 = 90;
              goto LABEL_12;
            }
          }
          goto LABEL_109;
        }
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
          if ( *((_DWORD *)v35 + 499) != PreferredMFTActivate )
            CallStackContext::TraceFailure(v35, "CTranscodeDestination::GetMFTActivate", 591, PreferredMFTActivate);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v15 = 87;
          goto LABEL_12;
        }
      }
      else
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != PreferredMFTActivate )
            CallStackContext::TraceFailure(v23, "CTranscodeDestination::GetMFTActivate", 573, PreferredMFTActivate);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v15 = 84;
          goto LABEL_12;
        }
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
        if ( *((_DWORD *)v19 + 499) != PreferredMFTActivate )
          CallStackContext::TraceFailure(v19, "CTranscodeDestination::GetMFTActivate", 572, PreferredMFTActivate);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v15 = 83;
        goto LABEL_12;
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
      if ( *((_DWORD *)v14 + 499) != PreferredMFTActivate )
        CallStackContext::TraceFailure(v14, "CTranscodeDestination::GetMFTActivate", 571, PreferredMFTActivate);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v15 = 82;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        WPP_82ede244afe43de52d63f347cb6083ad_Traceguids,
        this,
        PreferredMFTActivate);
    }
  }
LABEL_109:
  v50 = pv;
  if ( pv )
  {
    v51 = v56;
    for ( i = 0; i < v51; ++i )
    {
      v53 = v50[i];
      if ( v53 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v53 + 16LL))(v50[i]);
        *((_QWORD *)pv + i) = 0;
        v51 = v56;
        v50 = pv;
      }
    }
    CoTaskMemFree(v50);
  }
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v61);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v60);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v57);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v59);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v55);
  return (unsigned int)PreferredMFTActivate;
}

```

## disassembly

```asm
0x180042090  push    rbp
0x180042092  push    rbx
0x180042093  push    rsi
0x180042094  push    rdi
0x180042095  push    r13
0x180042097  push    r14
0x180042099  push    r15
0x18004209b  lea     rbp, [rsp-27h]
0x1800420a0  sub     rsp, 90h
0x1800420a7  mov     rax, cs:__security_cookie
0x1800420ae  xor     rax, rsp
0x1800420b1  mov     [rbp+57h+var_38], rax
0x1800420b5  mov     esi, r8d
0x1800420b8  lea     r13, aCtranscodedest_1; "CTranscodeDestination::GetMFTActivate"
0x1800420bf  mov     ebx, edx
0x1800420c1  mov     rdi, rcx
0x1800420c4  mov     rdx, r13; char *
0x1800420c7  lea     rcx, [rbp+57h+var_90]; this
0x1800420cb  mov     r8d, 22Bh; int
0x1800420d1  mov     r14, r9
0x1800420d4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800420d9  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800420e0  mov     rax, [rdi]
0x1800420e3  lea     r8, [rbp+57h+var_78]
0x1800420e7  xor     r15d, r15d
0x1800420ea  mov     edx, ebx
0x1800420ec  mov     rcx, rdi
0x1800420ef  mov     [rbp+57h+var_78], r15
0x1800420f3  movdqu  [rbp+57h+Buf2], xmm0
0x1800420f8  mov     rax, [rax+50h]
0x1800420fc  movdqu  xmmword ptr [rbp+57h+var_48.Data1], xmm0
0x180042101  mov     [rbp+57h+var_88], r15
0x180042105  mov     [rbp+57h+var_8C], r15d
0x180042109  mov     [rbp+57h+pv], r15
0x18004210d  mov     [rbp+57h+var_60], r15
0x180042111  mov     [rbp+57h+var_70], r15
0x180042115  mov     [rbp+57h+var_68], r15
0x180042119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004211e  mov     ebx, eax
0x180042120  test    eax, eax
0x180042122  jns     loc_1800421D1
0x180042128  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004212f  test    rcx, rcx
0x180042132  jnz     short loc_180042175
0x180042134  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004213a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042141  mov     rcx, rax
0x180042144  test    rax, rax
0x180042147  jz      short loc_180042167
0x180042149  mov     rax, [rax]
0x18004214c  mov     edx, 7F0h
0x180042151  mov     rax, [rax+8]
0x180042155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004215a  test    eax, eax
0x18004215c  jz      short loc_180042167
0x18004215e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042165  jmp     short loc_180042175
0x180042167  lea     rcx, qword_180069A90; this
0x18004216e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042175  cmp     [rcx+8], r15b
0x180042179  jz      short loc_18004219C
0x18004217b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042180  cmp     [rax+7CCh], ebx
0x180042186  jz      short loc_18004219C
0x180042188  mov     r9d, ebx; int
0x18004218b  mov     r8d, 23Bh; int
0x180042191  mov     rdx, r13; char *
0x180042194  mov     rcx, rax; this
0x180042197  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004219c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800421a1  cmp     al, 1
0x1800421a3  jb      loc_180042818
0x1800421a9  mov     edx, 52h ; 'R'
0x1800421ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800421b5  lea     r8, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids
0x1800421bc  mov     r9, rdi
0x1800421bf  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800421c3  mov     rcx, [rcx+10h]
0x1800421c7  call    WPP_SF_qd
0x1800421cc  jmp     loc_180042818
0x1800421d1  mov     rcx, [rbp+57h+var_78]
0x1800421d5  lea     r8, [rbp+57h+Buf2]
0x1800421d9  lea     rdx, MF_MT_MAJOR_TYPE
0x1800421e0  mov     rax, [rcx]
0x1800421e3  mov     rax, [rax+50h]
0x1800421e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421ec  mov     ebx, eax
0x1800421ee  test    eax, eax
0x1800421f0  jns     loc_180042281
0x1800421f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800421fd  test    rcx, rcx
0x180042200  jnz     short loc_180042243
0x180042202  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042208  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004220f  mov     rcx, rax
0x180042212  test    rax, rax
0x180042215  jz      short loc_180042235
0x180042217  mov     rax, [rax]
0x18004221a  mov     edx, 7F0h
0x18004221f  mov     rax, [rax+8]
0x180042223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042228  test    eax, eax
0x18004222a  jz      short loc_180042235
0x18004222c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042233  jmp     short loc_180042243
0x180042235  lea     rcx, qword_180069A90; this
0x18004223c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042243  cmp     [rcx+8], r15b
0x180042247  jz      short loc_18004226A
0x180042249  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004224e  cmp     [rax+7CCh], ebx
0x180042254  jz      short loc_18004226A
0x180042256  mov     r9d, ebx; int
0x180042259  mov     r8d, 23Ch; int
0x18004225f  mov     rdx, r13; char *
0x180042262  mov     rcx, rax; this
0x180042265  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004226a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004226f  cmp     al, 1
0x180042271  jb      loc_180042818
0x180042277  mov     edx, 53h ; 'S'
0x18004227c  jmp     loc_1800421AE
0x180042281  mov     rcx, [rbp+57h+var_78]
0x180042285  lea     r8, [rbp+57h+var_48]
0x180042289  lea     rdx, MF_MT_SUBTYPE
0x180042290  mov     rax, [rcx]
0x180042293  mov     rax, [rax+50h]
0x180042297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004229c  mov     ebx, eax
0x18004229e  test    eax, eax
0x1800422a0  jns     loc_180042331
0x1800422a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800422ad  test    rcx, rcx
0x1800422b0  jnz     short loc_1800422F3
0x1800422b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800422b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800422bf  mov     rcx, rax
0x1800422c2  test    rax, rax
0x1800422c5  jz      short loc_1800422E5
0x1800422c7  mov     rax, [rax]
0x1800422ca  mov     edx, 7F0h
0x1800422cf  mov     rax, [rax+8]
0x1800422d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422d8  test    eax, eax
0x1800422da  jz      short loc_1800422E5
0x1800422dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800422e3  jmp     short loc_1800422F3
0x1800422e5  lea     rcx, qword_180069A90; this
0x1800422ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800422f3  cmp     [rcx+8], r15b
0x1800422f7  jz      short loc_18004231A
0x1800422f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800422fe  cmp     [rax+7CCh], ebx
0x180042304  jz      short loc_18004231A
0x180042306  mov     r9d, ebx; int
0x180042309  mov     r8d, 23Dh; int
0x18004230f  mov     rdx, r13; char *
0x180042312  mov     rcx, rax; this
0x180042315  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004231a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004231f  cmp     al, 1
0x180042321  jb      loc_180042818
0x180042327  mov     edx, 54h ; 'T'
0x18004232c  jmp     loc_1800421AE
0x180042331  mov     ebx, 10h
0x180042336  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18004233a  mov     r8d, ebx; Size
0x18004233d  lea     rcx, MFMediaType_Video; Buf1
0x180042344  call    memcmp_0
0x180042349  test    eax, eax
0x18004234b  jnz     loc_1800423FA
0x180042351  mov     rcx, [rdi+8]
0x180042355  lea     rdx, [rbp+57h+var_88]
0x180042359  mov     rax, [rcx]
0x18004235c  mov     rax, [rax+30h]
0x180042360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042365  mov     ebx, eax
0x180042367  test    eax, eax
0x180042369  jns     loc_1800424BE
0x18004236f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042376  test    rcx, rcx
0x180042379  jnz     short loc_1800423BC
0x18004237b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042381  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042388  mov     rcx, rax
0x18004238b  test    rax, rax
0x18004238e  jz      short loc_1800423AE
0x180042390  mov     rax, [rax]
0x180042393  mov     edx, 7F0h
0x180042398  mov     rax, [rax+8]
0x18004239c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423a1  test    eax, eax
0x1800423a3  jz      short loc_1800423AE
0x1800423a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800423ac  jmp     short loc_1800423BC
0x1800423ae  lea     rcx, qword_180069A90; this
0x1800423b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800423bc  cmp     [rcx+8], r15b
0x1800423c0  jz      short loc_1800423E3
0x1800423c2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800423c7  cmp     [rax+7CCh], ebx
0x1800423cd  jz      short loc_1800423E3
0x1800423cf  mov     r9d, ebx; int
0x1800423d2  mov     r8d, 241h; int
0x1800423d8  mov     rdx, r13; char *
0x1800423db  mov     rcx, rax; this
0x1800423de  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800423e3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800423e8  cmp     al, 1
0x1800423ea  jb      loc_180042818
0x1800423f0  mov     edx, 55h ; 'U'
0x1800423f5  jmp     loc_1800421AE
0x1800423fa  mov     r8, rbx; Size
0x1800423fd  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180042401  lea     rcx, MFMediaType_Audio; Buf1
0x180042408  call    memcmp_0
0x18004240d  test    eax, eax
0x18004240f  jnz     loc_1800424BE
0x180042415  mov     rcx, [rdi+8]
0x180042419  lea     rdx, [rbp+57h+var_88]
0x18004241d  mov     rax, [rcx]
0x180042420  mov     rax, [rax+20h]
0x180042424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042429  mov     ebx, eax
0x18004242b  test    eax, eax
0x18004242d  jns     loc_1800424BE
0x180042433  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004243a  test    rcx, rcx
0x18004243d  jnz     short loc_180042480
0x18004243f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042445  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004244c  mov     rcx, rax
0x18004244f  test    rax, rax
0x180042452  jz      short loc_180042472
0x180042454  mov     rax, [rax]
0x180042457  mov     edx, 7F0h
0x18004245c  mov     rax, [rax+8]
0x180042460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042465  test    eax, eax
0x180042467  jz      short loc_180042472
0x180042469  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042470  jmp     short loc_180042480
0x180042472  lea     rcx, qword_180069A90; this
0x180042479  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042480  cmp     [rcx+8], r15b
0x180042484  jz      short loc_1800424A7
0x180042486  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004248b  cmp     [rax+7CCh], ebx
0x180042491  jz      short loc_1800424A7
0x180042493  mov     r9d, ebx; int
0x180042496  mov     r8d, 245h; int
0x18004249c  mov     rdx, r13; char *
0x18004249f  mov     rcx, rax; this
0x1800424a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800424a7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800424ac  cmp     al, 1
0x1800424ae  jb      loc_180042818
0x1800424b4  mov     edx, 56h ; 'V'
0x1800424b9  jmp     loc_1800421AE
0x1800424be  lea     rax, [rbp+57h+pv]
0x1800424c2  mov     r8d, esi; unsigned int
0x1800424c5  lea     r9, [rbp+57h+var_8C]; unsigned int *
0x1800424c9  mov     [rsp+0C0h+var_A0], rax; struct IMFActivate ***
0x1800424ce  lea     rdx, [rbp+57h+var_48]; struct _GUID *
0x1800424d2  lea     rcx, [rbp+57h+Buf2]; struct _GUID *
0x1800424d6  call    ?EnumMFTActivates@CMFTHelper@@SAJAEBU_GUID@@0KPEAIPEAPEAPEAUIMFActivate@@@Z; CMFTHelper::EnumMFTActivates(_GUID const &,_GUID const &,ulong,uint *,IMFActivate * * *)
0x1800424db  mov     ebx, eax
0x1800424dd  test    eax, eax
0x1800424df  jns     loc_180042570
0x1800424e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800424ec  test    rcx, rcx
0x1800424ef  jnz     short loc_180042532
0x1800424f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800424f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800424fe  mov     rcx, rax
0x180042501  test    rax, rax
0x180042504  jz      short loc_180042524
0x180042506  mov     rax, [rax]
0x180042509  mov     edx, 7F0h
0x18004250e  mov     rax, [rax+8]
0x180042512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042517  test    eax, eax
0x180042519  jz      short loc_180042524
0x18004251b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042522  jmp     short loc_180042532
0x180042524  lea     rcx, qword_180069A90; this
0x18004252b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042532  cmp     [rcx+8], r15b
0x180042536  jz      short loc_180042559
0x180042538  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004253d  cmp     [rax+7CCh], ebx
0x180042543  jz      short loc_180042559
0x180042545  mov     r9d, ebx; int
0x180042548  mov     r8d, 24Fh; int
0x18004254e  mov     rdx, r13; char *
0x180042551  mov     rcx, rax; this
0x180042554  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042559  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004255e  cmp     al, 1
0x180042560  jb      loc_180042818
  ... truncated ...
```
