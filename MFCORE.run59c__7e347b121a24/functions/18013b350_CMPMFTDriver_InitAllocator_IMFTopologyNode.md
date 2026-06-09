# CMPMFTDriver::InitAllocator(IMFTopologyNode *)

- ea: `0x18013b350`
- end: `0x18013c6ab`
- name: `?InitAllocator@CMPMFTDriver@@AEAAJPEAUIMFTopologyNode@@@Z`
- size: `4955`
- prototype: `__int64 __fastcall(CMPMFTDriver *__hidden this, struct IMFTopologyNode *)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f4a0`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003a41c`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d118`
- `0x180050d6c`
- `0x18005a3d4`
- `0x180063f00`
- `0x18006b388`
- `0x18008b3a0`
- `0x180091eb0`
- `0x180092630`
- `0x18009302c`
- `0x1800b5bd8`
- `0x1800b9780`
- `0x1800ec0e0`
- `0x18013b350`
- `0x180162090`
- `0x1801646ac`
- `0x180258480`
- `0x18028bf3c`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013b505`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013b751`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013b829`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013b94a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013ba03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013bac3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013bb78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013bc7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013bd2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013be3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013bf1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c127`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c206`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c2d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c3a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c621`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013b505`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013b751`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013b829`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013b94a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013ba03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013bac3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013bb78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013bc7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013bd2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013be3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013bf1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c127`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c206`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c2d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c3a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c621`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x18013b925`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x18013b925`
- `MFPlat!MFCreateAttributes` at `0x18013c042`
- `MFPlat!MFCreateAttributes` at `0x18013c042`

## pseudocode

```c
__int64 __fastcall CMPMFTDriver::InitAllocator(CMPMFTDriver *this, struct IMFTopologyNode *a2)
{
  struct IMFTopologyNode *v2; // r15
  struct IMFTopologyNodeVtbl *lpVtbl; // rax
  HRESULT v5; // ebx
  HRESULT (__stdcall *GetUINT32)(IMFTopologyNode *, const GUID *const, UINT32 *); // rax
  struct IMFTopologyNodeVtbl *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  unsigned int v14; // r12d
  UINT32 v15; // r13d
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  int (__fastcall *v27)(__int64, const GUID *, GUID *, void **); // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  const char *String; // rax
  int v69; // r15d
  CallStackTracing *v70; // rcx
  struct CallStackContext *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  int v83; // eax
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 *v86; // rcx
  CallStackTracing *v87; // rax
  struct CallStackContext *v88; // rax
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 *v91; // rcx
  CallStackTracing *v92; // rax
  struct CallStackContext *v93; // rax
  struct IMFVideoSampleAllocator *v94; // rcx
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 *v98; // rcx
  CallStackTracing *v99; // rax
  struct CallStackContext *v100; // rax
  char v101[8]; // [rsp+40h] [rbp-C0h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v103; // [rsp+50h] [rbp-B0h] BYREF
  struct IMFVideoSampleAllocator *v104; // [rsp+58h] [rbp-A8h] BYREF
  void *ppSampleAllocator; // [rsp+60h] [rbp-A0h] BYREF
  struct IMFMediaType *v106; // [rsp+68h] [rbp-98h] BYREF
  __int64 v107; // [rsp+70h] [rbp-90h] BYREF
  int v108; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v109; // [rsp+80h] [rbp-80h] BYREF
  __int64 v110; // [rsp+88h] [rbp-78h] BYREF
  __int64 v111; // [rsp+90h] [rbp-70h] BYREF
  __int64 v112; // [rsp+98h] [rbp-68h] BYREF
  __int64 v113; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v114; // [rsp+A8h] [rbp-58h] BYREF
  int v115; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v116; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v117; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v118; // [rsp+C8h] [rbp-38h] BYREF
  struct IMFTopologyNode *v119; // [rsp+D0h] [rbp-30h]
  _BYTE v120[192]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v121; // [rsp+1A0h] [rbp+A0h] BYREF
  int v122; // [rsp+1A8h] [rbp+A8h]

  v2 = a2;
  v119 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v101, "CMPMFTDriver::InitAllocator", 1005);
  v103 = 0;
  v121 = 0;
  v122 = 0;
  lpVtbl = v2->lpVtbl;
  v5 = 0;
  v115 = 0;
  v118 = 0;
  v114 = 0;
  GetUINT32 = lpVtbl->GetUINT32;
  v106 = 0;
  v117 = 0;
  v113 = 0;
  v112 = 0;
  v108 = 0;
  v109 = 0;
  v111 = 0;
  v116 = 0;
  v107 = 0;
  v110 = 0;
  ppSampleAllocator = 0;
  v104 = 0;
  ((void (__fastcall *)(struct IMFTopologyNode *, const IID *, int *))GetUINT32)(v2, &MF_TOPONODE_D3DAWARE, &v108);
  if ( v108 )
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 71, &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids, this);
    goto LABEL_226;
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)this + 56LL))(
    *(_QWORD *)this,
    **((unsigned int **)this + 7),
    &v121);
  if ( (v121 & 0x300) != 0 )
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        72,
        &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
        this,
        *(_QWORD *)this);
    goto LABEL_226;
  }
  v7 = v2->lpVtbl;
  v103 = 0;
  ((void (__fastcall *)(struct IMFTopologyNode *, _QWORD, __int64 *, int *))v7->GetOutput)(v2, 0, &v103, &v115);
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v103 + 288LL))(v103, &v109);
  if ( v5 < 0 )
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMPMFTDriver::InitAllocator", 1050, v5);
    }
    if ( g_wppLevels )
    {
      v13 = 74;
LABEL_18:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids, this, v5);
      goto LABEL_226;
    }
    goto LABEL_226;
  }
  if ( *((_QWORD *)this + 42) != v109 )
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        75,
        &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
        this,
        *((_DWORD *)this + 84),
        v109);
    CMPMFTDriver::SetVideoAllocator(this, 0, 0);
  }
  if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v103 + 272LL))(v103, &v111) < 0
    || (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v111)(v111, &IID_IMFGetService, &v107) < 0 )
  {
    goto LABEL_24;
  }
  if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v111)(v111, &IID_IMFTransform, &v116) < 0 )
  {
    (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v111)(v111, &IID_IMFAttributes, &v110);
  }
  else if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v116 + 64LL))(v116, &v110) < 0 )
  {
    goto LABEL_24;
  }
  v14 = 5;
  v15 = 4;
  if ( v110 )
    v14 = MFGetAttributeUINT32(v110, &MF_SA_REQUIRED_SAMPLE_COUNT, 4) + 1;
  if ( (*(int (__fastcall **)(__int64, const GUID *, GUID *, __int64 *))(*(_QWORD *)v107 + 24LL))(
         v107,
         &MR_VIDEO_ACCELERATION_SERVICE,
         &GUID_eb533d5d_2db6_40f8_97a9_494692014f07,
         &v113) >= 0 )
  {
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v113)(
           v113,
           &GUID_00000000_0000_0000_c000_000000000046,
           &v112);
    if ( v5 < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != v5 )
          CallStackContext::TraceFailure(v26, "CMPMFTDriver::InitAllocator", 1120, v5);
      }
      if ( g_wppLevels )
      {
        v13 = 78;
        goto LABEL_18;
      }
      goto LABEL_226;
    }
    if ( (unsigned __int8)byte_1803CECE9 < 0x10u )
    {
LABEL_61:
      v27 = *(int (__fastcall **)(__int64, const GUID *, GUID *, void **))(*(_QWORD *)v107 + 24LL);
      if ( v113 )
      {
        if ( v27(v107, &MR_VIDEO_ACCELERATION_SERVICE, &GUID_545b3a48_3283_4f62_866f_a62d8f598f9f, &ppSampleAllocator) < 0 )
        {
          v5 = MFCreateVideoSampleAllocatorEx(&GUID_545b3a48_3283_4f62_866f_a62d8f598f9f, &ppSampleAllocator);
          if ( v5 < 0 )
          {
            v30 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
              CallStackTracing::s_wpInstance = v31;
              if ( v31
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
              {
                v30 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v30 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v30 + 8) )
            {
              v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
              if ( *((_DWORD *)v32 + 499) != v5 )
                CallStackContext::TraceFailure(v32, "CMPMFTDriver::InitAllocator", 1133, v5);
            }
            if ( g_wppLevels )
            {
              v13 = 80;
              goto LABEL_18;
            }
            goto LABEL_226;
          }
          v5 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppSampleAllocator + 24LL))(
                 ppSampleAllocator,
                 v112);
          if ( v5 < 0 )
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
              CallStackTracing::s_wpInstance = v36;
              if ( v36
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
              {
                v35 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v35 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v35 + 8) )
            {
              v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
              if ( *((_DWORD *)v37 + 499) != v5 )
                CallStackContext::TraceFailure(v37, "CMPMFTDriver::InitAllocator", 1143, v5);
            }
            if ( g_wppLevels )
            {
              v13 = 81;
              goto LABEL_18;
            }
            goto LABEL_226;
          }
        }
        v5 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IMFVideoSampleAllocator **))ppSampleAllocator)(
               ppSampleAllocator,
               &GUID_86cbc910_e533_4751_8e3b_f19b5b806a03,
               &v104);
        if ( v5 < 0 )
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39);
            CallStackTracing::s_wpInstance = v41;
            if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
            {
              v40 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v40 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v40 + 8) )
          {
            v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
            if ( *((_DWORD *)v42 + 499) != v5 )
              CallStackContext::TraceFailure(v42, "CMPMFTDriver::InitAllocator", 1145, v5);
          }
          if ( g_wppLevels )
          {
            v13 = 82;
            goto LABEL_18;
          }
          goto LABEL_226;
        }
      }
      else
      {
        v5 = v27(v107, &MR_VIDEO_ACCELERATION_SERVICE, &GUID_86cbc910_e533_4751_8e3b_f19b5b806a03, (void **)&v104);
        if ( v5 < 0 )
        {
          v45 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44);
            CallStackTracing::s_wpInstance = v46;
            if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
            {
              v45 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v45 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v45 + 8) )
          {
            v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
            if ( *((_DWORD *)v47 + 499) != v5 )
              CallStackContext::TraceFailure(v47, "CMPMFTDriver::InitAllocator", 1149, v5);
          }
          if ( g_wppLevels )
          {
            v13 = 83;
            goto LABEL_18;
          }
          goto LABEL_226;
        }
      }
      if ( *((_QWORD *)this + 42) == v109 )
      {
        if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
          WPP_SF_qqqd(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            84,
            &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
            this,
            v2,
            v103,
            v109);
      }
      else
      {
        if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
          WPP_SF_qqqq(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            85,
            &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
            this,
            v2,
            v104,
            v103);
        v5 = ((__int64 (__fastcall *)(struct IMFVideoSampleAllocator *, __int64))v104->lpVtbl->SetDirectXManager)(
               v104,
               v112);
        if ( v5 < 0 )
        {
          v54 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53);
            CallStackTracing::s_wpInstance = v55;
            if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
            {
              v54 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v54 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v54 + 8) )
          {
            v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
            if ( *((_DWORD *)v56 + 499) != v5 )
              CallStackContext::TraceFailure(v56, "CMPMFTDriver::InitAllocator", 1164, v5);
          }
          if ( g_wppLevels )
          {
            v13 = 86;
            goto LABEL_18;
          }
          goto LABEL_226;
        }
      }
      v5 = ((__int64 (__fastcall *)(struct IMFTopologyNode *, __int64 *))v2->lpVtbl->GetObjectA)(v2, &v118);
      if ( v5 < 0 )
      {
        v50 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49);
          CallStackTracing::s_wpInstance = v51;
          if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
          {
            v50 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v50 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v50 + 8) )
        {
          v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
          if ( *((_DWORD *)v57 + 499) != v5 )
            CallStackContext::TraceFailure(v57, "CMPMFTDriver::InitAllocator", 1172, v5);
        }
        if ( g_wppLevels )
        {
          v13 = 87;
          goto LABEL_18;
        }
        goto LABEL_226;
      }
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v118)(v118, &IID_IMFTransform, &v114);
      if ( v5 < 0 )
      {
        v60 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59);
          CallStackTracing::s_wpInstance = v61;
          if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
          {
            v60 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v60 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v60 + 8) )
        {
          v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
          if ( *((_DWORD *)v62 + 499) != v5 )
            CallStackContext::TraceFailure(v62, "CMPMFTDriver::InitAllocator", 1174, v5);
        }
        if ( g_wppLevels )
        {
          v13 = 88;
          goto LABEL_18;
        }
        goto LABEL_226;
      }
      if ( (*(int (__fastcall **)(__int64, _QWORD, struct IMFMediaType **))(*(_QWORD *)v114 + 144LL))(v114, 0, &v106) < 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct IMFMediaType **))(*(_QWORD *)v114 + 112LL))(
               v114,
               0,
               0,
               &v106);
        if ( v5 < 0 )
        {
          v65 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64);
            CallStackTracing::s_wpInstance = v66;
            if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
            {
              v65 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v65 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v65 + 8) )
          {
            v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
            if ( *((_DWORD *)v67 + 499) != v5 )
              CallStackContext::TraceFailure(v67, "CMPMFTDriver::InitAllocator", 1180, v5);
          }
          if ( g_wppLevels )
          {
            v13 = 89;
            goto LABEL_18;
          }
          goto LABEL_226;
        }
      }
      CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v120, (struct IMFAttributes *)v106);
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      {
        String = CMFAttributesTrace::GetString((CMFAttributesTrace *)v120, 0);
        WPP_SF_qs(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          90,
          (unsigned int)&WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
          (_DWORD)this,
          (__int64)String);
      }
      CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v120);
      if ( v14 < 4 )
        v14 = 4;
      if ( ppSampleAllocator )
      {
        if ( v110 && (unsigned int)MFGetAttributeUINT32(v110, &MF_SA_D3D11_SHARED_WITHOUT_MUTEX, 0) )
        {
          v69 = 1;
        }
        else
        {
          v69 = 0;
          v15 = 3;
        }
        ppMFAttributes = 0;
        v5 = MFCreateAttributes(&ppMFAttributes, v15);
        if ( v5 < 0 )
        {
          v70 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v70 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v70 + 8) )
          {
            v71 = CallStackTracing::GetThreadRelativeContext(v70);
            if ( *((_DWORD *)v71 + 499) != v5 )
              CallStackContext::TraceFailure(v71, "CMPMFTDriver::InitAllocator", 1206, v5);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              91,
              &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
              this,
              v5);
          if ( ppMFAttributes )
            ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
          goto LABEL_226;
        }
        if ( v69 )
        {
          v5 = ((__int64 (__fastcall *)(IMFAttributes *, void *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
                 ppMFAttributes,
                 &MF_SA_D3D11_SHARED_WITHOUT_MUTEX,
                 1);
          if ( v5 < 0 )
          {
            v74 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72, v73);
              CallStackTracing::s_wpInstance = v75;
              if ( v75
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
              {
                v74 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v74 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v74 + 8) )
            {
              v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
              if ( *((_DWORD *)v76 + 499) != v5 )
                CallStackContext::TraceFailure(v76, "CMPMFTDriver::InitAllocator", 1214, v5);
            }
            if ( !g_wppLevels )
              goto LABEL_189;
            v77 = 92;
LABEL_188:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v77,
              &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
              this,
              v5);
LABEL_189:
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFAttributes);
            goto LABEL_226;
          }
        }
        v5 = ((__int64 (__fastcall *)(IMFAttributes *, void *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               &MF_SA_D3D11_BINDFLAGS,
               0);
        if ( v5 < 0 )
        {
          v80 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v78, v79);
            CallStackTracing::s_wpInstance = v81;
            if ( v81 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
            {
              v80 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v80 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v80 + 8) )
          {
            v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
            if ( *((_DWORD *)v82 + 499) != v5 )
              CallStackContext::TraceFailure(v82, "CMPMFTDriver::InitAllocator", 1217, v5);
          }
          if ( !g_wppLevels )
            goto LABEL_189;
          v77 = 93;
          goto LABEL_188;
        }
        v83 = IsS3DMultiView(v106);
        v5 = ((__int64 (__fastcall *)(IMFAttributes *, void *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
               ppMFAttributes,
               &MF_SA_BUFFERS_PER_SAMPLE,
               (unsigned int)(v83 != 0) + 1);
        if ( v5 < 0 )
        {
          v86 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v87 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v84, v85);
            CallStackTracing::s_wpInstance = v87;
            if ( v87 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v87 + 8LL))(v87, 2032) )
            {
              v86 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v86 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v86 + 8) )
          {
            v88 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v86);
            if ( *((_DWORD *)v88 + 499) != v5 )
              CallStackContext::TraceFailure(v88, "CMPMFTDriver::InitAllocator", 1223, v5);
          }
          if ( !g_wppLevels )
            goto LABEL_189;
          v77 = 94;
          goto LABEL_188;
        }
        v5 = (*(__int64 (__fastcall **)(void *, __int64, __int64, IMFAttributes *, struct IMFMediaType *))(*(_QWORD *)ppSampleAllocator + 56LL))(
               ppSampleAllocator,
               1,
               10,
               ppMFAttributes,
               v106);
        if ( v5 < 0 )
        {
          v91 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v92 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v89, v90);
            CallStackTracing::s_wpInstance = v92;
            if ( v92 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v92 + 8LL))(v92, 2032) )
            {
              v91 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v91 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v91 + 8) )
          {
            v93 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v91);
            if ( *((_DWORD *)v93 + 499) != v5 )
              CallStackContext::TraceFailure(v93, "CMPMFTDriver::InitAllocator", 1228, v5);
          }
          if ( !g_wppLevels )
            goto LABEL_189;
          v77 = 95;
          goto LABEL_188;
        }
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFAttributes);
        v2 = v119;
      }
      else
      {
        v5 = ((__int64 (__fastcall *)(struct IMFVideoSampleAllocator *, _QWORD, struct IMFMediaType *))v104->lpVtbl->InitializeSampleAllocator)(
               v104,
               v14,
               v106);
        if ( v5 < 0 )
        {
          v98 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v99 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v96, v97);
            CallStackTracing::s_wpInstance = v99;
            if ( v99 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v99 + 8LL))(v99, 2032) )
            {
              v98 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v98 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v98 + 8) )
          {
            v100 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v98);
            if ( *((_DWORD *)v100 + 499) != v5 )
              CallStackContext::TraceFailure(v100, "CMPMFTDriver::InitAllocator", 1232, v5);
          }
          if ( g_wppLevels )
          {
            v13 = 96;
            goto LABEL_18;
          }
          goto LABEL_226;
        }
      }
      CMPMFTDriver::SetVideoAllocator(this, v104, v109);
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_qqqdd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          97,
          &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
          this,
          v2,
          v103,
          v109,
          v14);
      goto LABEL_226;
    }
    v21 = 79;
LABEL_60:
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), v21, &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids, this, v103);
    goto LABEL_61;
  }
  if ( (*(int (__fastcall **)(__int64, const GUID *, GUID *, __int64 *))(*(_QWORD *)v107 + 24LL))(
         v107,
         &MR_VIDEO_ACCELERATION_SERVICE,
         &GUID_a0cade0f_06d5_4cf4_a1c7_f3cdd725aa75,
         &v117) < 0 )
  {
LABEL_24:
    v5 = 0;
    goto LABEL_226;
  }
  v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v117)(
         v117,
         &GUID_00000000_0000_0000_c000_000000000046,
         &v112);
  if ( v5 >= 0 )
  {
    if ( (unsigned __int8)byte_1803CECE9 < 0x10u )
      goto LABEL_61;
    v21 = 77;
    goto LABEL_60;
  }
  v18 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v18 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
    if ( *((_DWORD *)v20 + 499) != v5 )
      CallStackContext::TraceFailure(v20, "CMPMFTDriver::InitAllocator", 1115, v5);
  }
  if ( g_wppLevels )
  {
    v13 = 76;
    goto LABEL_18;
  }
LABEL_226:
  v94 = v104;
  *((_DWORD *)this + 80) = 1;
  if ( v94 )
    ((void (__fastcall *)(struct IMFVideoSampleAllocator *))v94->lpVtbl->Release)(v94);
  if ( ppSampleAllocator )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppSampleAllocator + 16LL))(ppSampleAllocator);
  if ( v110 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
  if ( v107 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
  if ( v116 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
  if ( v111 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
  if ( v112 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
  if ( v113 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
  if ( v117 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
  if ( v106 )
    ((void (__fastcall *)(struct IMFMediaType *))v106->lpVtbl->Release)(v106);
  if ( v114 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v114 + 16LL))(v114);
  if ( v118 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
  if ( v103 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v101);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18013b350  mov     [rsp-8+arg_10], rbx
0x18013b355  mov     [rsp-8+arg_18], rsi
0x18013b35a  push    rbp
0x18013b35b  push    rdi
0x18013b35c  push    r12
0x18013b35e  push    r13
0x18013b360  push    r15
0x18013b362  lea     rbp, [rsp-0C0h]
0x18013b36a  sub     rsp, 1C0h
0x18013b371  mov     rax, cs:__security_cookie
0x18013b378  xor     rax, rsp
0x18013b37b  mov     [rbp+0E0h+var_30], rax
0x18013b382  mov     r15, rdx
0x18013b385  mov     [rbp+0E0h+var_110], rdx
0x18013b389  mov     rdi, rcx
0x18013b38c  lea     rdx, aCmpmftdriverIn_4; "CMPMFTDriver::InitAllocator"
0x18013b393  lea     rcx, [rsp+1E0h+var_1A0]; this
0x18013b398  mov     r8d, 3EDh; int
0x18013b39e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18013b3a3  xor     r13d, r13d
0x18013b3a6  lea     r8, [rsp+1E0h+var_168]
0x18013b3ab  xor     eax, eax
0x18013b3ad  mov     [rsp+1E0h+var_190], r13
0x18013b3b2  mov     [rbp+0E0h+var_40], rax
0x18013b3b9  lea     rdx, MF_TOPONODE_D3DAWARE
0x18013b3c0  mov     [rbp+0E0h+var_38], eax
0x18013b3c6  mov     rcx, r15
0x18013b3c9  mov     rax, [r15]
0x18013b3cc  mov     ebx, r13d
0x18013b3cf  mov     [rbp+0E0h+var_130], r13d
0x18013b3d3  mov     [rbp+0E0h+var_118], r13
0x18013b3d7  mov     [rbp+0E0h+var_138], r13
0x18013b3db  mov     rax, [rax+38h]
0x18013b3df  mov     [rsp+1E0h+var_178], r13
0x18013b3e4  mov     [rbp+0E0h+var_120], r13
0x18013b3e8  mov     [rbp+0E0h+var_140], r13
0x18013b3ec  mov     [rbp+0E0h+var_148], r13
0x18013b3f0  mov     [rsp+1E0h+var_168], r13d
0x18013b3f5  mov     [rbp+0E0h+var_160], r13
0x18013b3f9  mov     [rbp+0E0h+var_150], r13
0x18013b3fd  mov     [rbp+0E0h+var_128], r13
0x18013b401  mov     [rsp+1E0h+var_170], r13
0x18013b406  mov     [rbp+0E0h+var_158], r13
0x18013b40a  mov     [rsp+1E0h+ppSampleAllocator], r13
0x18013b40f  mov     [rsp+1E0h+var_188], r13
0x18013b414  call    cs:__guard_dispatch_icall_fptr
0x18013b41a  cmp     [rsp+1E0h+var_168], r13d
0x18013b41f  jz      short loc_18013B451
0x18013b421  cmp     cs:byte_1803CECE9, 10h
0x18013b428  jb      loc_18013C489
0x18013b42e  mov     rcx, cs:WPP_GLOBAL_Control
0x18013b435  lea     edx, [r13+47h]
0x18013b439  mov     r9, rdi
0x18013b43c  lea     r8, WPP_74268b52eb7b368509d4a1f76a866452_Traceguids
0x18013b443  mov     rcx, [rcx+38h]
0x18013b447  call    WPP_SF_q
0x18013b44c  jmp     loc_18013C489
0x18013b451  mov     rcx, [rdi]
0x18013b454  lea     r8, [rbp+0E0h+var_40]
0x18013b45b  mov     rdx, [rdi+38h]
0x18013b45f  mov     rax, [rcx]
0x18013b462  mov     edx, [rdx]
0x18013b464  mov     rax, [rax+38h]
0x18013b468  call    cs:__guard_dispatch_icall_fptr
0x18013b46e  test    dword ptr [rbp+0E0h+var_40], 300h
0x18013b478  jz      short loc_18013B4B3
0x18013b47a  cmp     cs:byte_1803CECE9, 8
0x18013b481  jb      loc_18013C489
0x18013b487  mov     rcx, cs:WPP_GLOBAL_Control
0x18013b48e  lea     r8, WPP_74268b52eb7b368509d4a1f76a866452_Traceguids
0x18013b495  mov     rax, [rdi]
0x18013b498  mov     edx, 48h ; 'H'
0x18013b49d  mov     r9, rdi
0x18013b4a0  mov     [rsp+1E0h+var_1C0], rax
0x18013b4a5  mov     rcx, [rcx+38h]
0x18013b4a9  call    WPP_SF_qq
0x18013b4ae  jmp     loc_18013C489
0x18013b4b3  mov     rax, [r15]
0x18013b4b6  lea     r9, [rbp+0E0h+var_130]
0x18013b4ba  lea     r8, [rsp+1E0h+var_190]
0x18013b4bf  mov     [rsp+1E0h+var_190], r13
0x18013b4c4  xor     edx, edx
0x18013b4c6  mov     rcx, r15
0x18013b4c9  mov     rax, [rax+158h]
0x18013b4d0  call    cs:__guard_dispatch_icall_fptr
0x18013b4d6  mov     rcx, [rsp+1E0h+var_190]
0x18013b4db  lea     rdx, [rbp+0E0h+var_160]
0x18013b4df  mov     rax, [rcx]
0x18013b4e2  mov     rax, [rax+120h]
0x18013b4e9  call    cs:__guard_dispatch_icall_fptr
0x18013b4ef  mov     ebx, eax
0x18013b4f1  test    eax, eax
0x18013b4f3  jns     loc_18013B5AD
0x18013b4f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b500  test    rcx, rcx
0x18013b503  jnz     short loc_18013B54D
0x18013b505  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013b50c  nop     dword ptr [rax+rax+00h]
0x18013b511  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b518  mov     rcx, rax
0x18013b51b  test    rax, rax
0x18013b51e  jz      short loc_18013B53F
0x18013b520  mov     rax, [rax]
0x18013b523  mov     edx, 7F0h
0x18013b528  mov     rax, [rax+8]
0x18013b52c  call    cs:__guard_dispatch_icall_fptr
0x18013b532  test    eax, eax
0x18013b534  jz      short loc_18013B53F
0x18013b536  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b53d  jmp     short loc_18013B54D
0x18013b53f  lea     rcx, qword_1803CE250; this
0x18013b546  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b54d  cmp     [rcx+8], r13b
0x18013b551  jz      short loc_18013B578
0x18013b553  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013b558  cmp     [rax+7CCh], ebx
0x18013b55e  jz      short loc_18013B578
0x18013b560  mov     r9d, ebx; int
0x18013b563  lea     rdx, aCmpmftdriverIn_4; "CMPMFTDriver::InitAllocator"
0x18013b56a  mov     r8d, 41Ah; int
0x18013b570  mov     rcx, rax; this
0x18013b573  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013b578  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013b57f  jb      loc_18013C489
0x18013b585  mov     edx, 4Ah ; 'J'
0x18013b58a  lea     r8, WPP_74268b52eb7b368509d4a1f76a866452_Traceguids
0x18013b591  mov     rcx, cs:WPP_GLOBAL_Control
0x18013b598  mov     r9, rdi
0x18013b59b  mov     dword ptr [rsp+1E0h+var_1C0], ebx
0x18013b59f  mov     rcx, [rcx+10h]
0x18013b5a3  call    WPP_SF_qD
0x18013b5a8  jmp     loc_18013C489
0x18013b5ad  mov     rax, [rbp+0E0h+var_160]
0x18013b5b1  lea     rsi, WPP_74268b52eb7b368509d4a1f76a866452_Traceguids
0x18013b5b8  cmp     [rdi+150h], rax
0x18013b5bf  jz      short loc_18013B600
0x18013b5c1  cmp     cs:byte_1803CECE9, 10h
0x18013b5c8  jb      short loc_18013B5F3
0x18013b5ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18013b5d1  mov     edx, 4Bh ; 'K'
0x18013b5d6  mov     dword ptr [rsp+1E0h+var_1B8], eax
0x18013b5da  mov     r9, rdi
0x18013b5dd  mov     eax, [rdi+150h]
0x18013b5e3  mov     r8, rsi
0x18013b5e6  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x18013b5ea  mov     rcx, [rcx+38h]
0x18013b5ee  call    WPP_SF_qDD
0x18013b5f3  xor     r8d, r8d; unsigned __int64
0x18013b5f6  xor     edx, edx; struct IMFVideoSampleAllocator *
0x18013b5f8  mov     rcx, rdi; this
0x18013b5fb  call    ?SetVideoAllocator@CMPMFTDriver@@AEAAXPEAUIMFVideoSampleAllocator@@_K@Z; CMPMFTDriver::SetVideoAllocator(IMFVideoSampleAllocator *,unsigned __int64)
0x18013b600  mov     rcx, [rsp+1E0h+var_190]
0x18013b605  lea     rdx, [rbp+0E0h+var_150]
0x18013b609  mov     rax, [rcx]
0x18013b60c  mov     rax, [rax+110h]
0x18013b613  call    cs:__guard_dispatch_icall_fptr
0x18013b619  test    eax, eax
0x18013b61b  jns     short loc_18013B625
0x18013b61d  mov     ebx, r13d
0x18013b620  jmp     loc_18013C489
0x18013b625  mov     rcx, [rbp+0E0h+var_150]
0x18013b629  lea     r8, [rsp+1E0h+var_170]
0x18013b62e  lea     rdx, IID_IMFGetService
0x18013b635  mov     rax, [rcx]
0x18013b638  mov     rax, [rax]
0x18013b63b  call    cs:__guard_dispatch_icall_fptr
0x18013b641  test    eax, eax
0x18013b643  js      short loc_18013B61D
0x18013b645  mov     rcx, [rbp+0E0h+var_150]
0x18013b649  lea     r8, [rbp+0E0h+var_128]
0x18013b64d  lea     rdx, IID_IMFTransform
0x18013b654  mov     rax, [rcx]
0x18013b657  mov     rax, [rax]
0x18013b65a  call    cs:__guard_dispatch_icall_fptr
0x18013b660  test    eax, eax
0x18013b662  js      short loc_18013B67F
0x18013b664  mov     rcx, [rbp+0E0h+var_128]
0x18013b668  lea     rdx, [rbp+0E0h+var_158]
0x18013b66c  mov     rax, [rcx]
0x18013b66f  mov     rax, [rax+40h]
0x18013b673  call    cs:__guard_dispatch_icall_fptr
0x18013b679  test    eax, eax
0x18013b67b  jns     short loc_18013B69A
0x18013b67d  jmp     short loc_18013B61D
0x18013b67f  mov     rcx, [rbp+0E0h+var_150]
0x18013b683  lea     r8, [rbp+0E0h+var_158]
0x18013b687  lea     rdx, IID_IMFAttributes
0x18013b68e  mov     rax, [rcx]
0x18013b691  mov     rax, [rax]
0x18013b694  call    cs:__guard_dispatch_icall_fptr
0x18013b69a  mov     rcx, [rbp+0E0h+var_158]
0x18013b69e  mov     r12d, 5
0x18013b6a4  lea     r13d, [r12-1]
0x18013b6a9  test    rcx, rcx
0x18013b6ac  jz      short loc_18013B6C1
0x18013b6ae  mov     r8d, r13d
0x18013b6b1  lea     rdx, MF_SA_REQUIRED_SAMPLE_COUNT
0x18013b6b8  call    MFGetAttributeUINT32
0x18013b6bd  lea     r12d, [rax+1]
0x18013b6c1  mov     rcx, [rsp+1E0h+var_170]
0x18013b6c6  lea     r9, [rbp+0E0h+var_140]
0x18013b6ca  lea     r8, _GUID_eb533d5d_2db6_40f8_97a9_494692014f07
0x18013b6d1  mov     rdx, [rcx]
0x18013b6d4  mov     rax, [rdx+18h]
0x18013b6d8  lea     rdx, MR_VIDEO_ACCELERATION_SERVICE
0x18013b6df  call    cs:__guard_dispatch_icall_fptr
0x18013b6e5  test    eax, eax
0x18013b6e7  jns     loc_18013B7F5
0x18013b6ed  mov     rcx, [rsp+1E0h+var_170]
0x18013b6f2  lea     r9, [rbp+0E0h+var_120]
0x18013b6f6  lea     r8, _GUID_a0cade0f_06d5_4cf4_a1c7_f3cdd725aa75
0x18013b6fd  lea     rdx, MR_VIDEO_ACCELERATION_SERVICE
0x18013b704  mov     rax, [rcx]
0x18013b707  mov     rax, [rax+18h]
0x18013b70b  call    cs:__guard_dispatch_icall_fptr
0x18013b711  test    eax, eax
0x18013b713  jns     short loc_18013B71D
0x18013b715  xor     r13d, r13d
0x18013b718  jmp     loc_18013B61D
0x18013b71d  mov     rcx, [rbp+0E0h+var_120]
0x18013b721  lea     r8, [rbp+0E0h+var_148]
0x18013b725  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18013b72c  mov     rax, [rcx]
0x18013b72f  mov     rax, [rax]
0x18013b732  call    cs:__guard_dispatch_icall_fptr
0x18013b738  mov     ebx, eax
0x18013b73a  test    eax, eax
0x18013b73c  jns     loc_18013B7DE
0x18013b742  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b749  xor     r13d, r13d
0x18013b74c  test    rcx, rcx
0x18013b74f  jnz     short loc_18013B799
0x18013b751  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013b758  nop     dword ptr [rax+rax+00h]
0x18013b75d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b764  mov     rcx, rax
0x18013b767  test    rax, rax
0x18013b76a  jz      short loc_18013B78B
0x18013b76c  mov     rax, [rax]
0x18013b76f  mov     edx, 7F0h
0x18013b774  mov     rax, [rax+8]
0x18013b778  call    cs:__guard_dispatch_icall_fptr
0x18013b77e  test    eax, eax
0x18013b780  jz      short loc_18013B78B
0x18013b782  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b789  jmp     short loc_18013B799
0x18013b78b  lea     rcx, qword_1803CE250; this
0x18013b792  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b799  cmp     [rcx+8], r13b
0x18013b79d  jz      short loc_18013B7C4
0x18013b79f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013b7a4  cmp     [rax+7CCh], ebx
0x18013b7aa  jz      short loc_18013B7C4
0x18013b7ac  mov     r9d, ebx; int
0x18013b7af  lea     rdx, aCmpmftdriverIn_4; "CMPMFTDriver::InitAllocator"
0x18013b7b6  mov     r8d, 45Bh; int
0x18013b7bc  mov     rcx, rax; this
0x18013b7bf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013b7c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013b7cb  jb      loc_18013C489
0x18013b7d1  mov     edx, 4Ch ; 'L'
0x18013b7d6  mov     r8, rsi
0x18013b7d9  jmp     loc_18013B591
0x18013b7de  cmp     cs:byte_1803CECE9, 10h
0x18013b7e5  jb      loc_18013B8E1
0x18013b7eb  mov     edx, 4Dh ; 'M'
0x18013b7f0  jmp     loc_18013B8C1
0x18013b7f5  mov     rcx, [rbp+0E0h+var_140]
0x18013b7f9  lea     r8, [rbp+0E0h+var_148]
0x18013b7fd  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18013b804  mov     rax, [rcx]
0x18013b807  mov     rax, [rax]
0x18013b80a  call    cs:__guard_dispatch_icall_fptr
0x18013b810  mov     ebx, eax
0x18013b812  test    eax, eax
0x18013b814  jns     loc_18013B8B3
0x18013b81a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b821  xor     r13d, r13d
0x18013b824  test    rcx, rcx
0x18013b827  jnz     short loc_18013B871
0x18013b829  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013b830  nop     dword ptr [rax+rax+00h]
0x18013b835  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b83c  mov     rcx, rax
0x18013b83f  test    rax, rax
0x18013b842  jz      short loc_18013B863
0x18013b844  mov     rax, [rax]
0x18013b847  mov     edx, 7F0h
0x18013b84c  mov     rax, [rax+8]
0x18013b850  call    cs:__guard_dispatch_icall_fptr
0x18013b856  test    eax, eax
0x18013b858  jz      short loc_18013B863
0x18013b85a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b861  jmp     short loc_18013B871
0x18013b863  lea     rcx, qword_1803CE250; this
0x18013b86a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013b871  cmp     [rcx+8], r13b
0x18013b875  jz      short loc_18013B89C
0x18013b877  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013b87c  cmp     [rax+7CCh], ebx
  ... truncated ...
```
