# CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs(CTPtrArray<IMFStreamDescriptor,20> const &,ulong,IMFAttributes * *)

- ea: `0x18003e94c`
- end: `0x18003ef9a`
- name: `?GetSrcStreamMTAttrs@CTranscodeProfileAdjuster_FillWithSource@@AEAAJAEBV?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@KPEAPEAUIMFAttributes@@@Z`
- size: `1614`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180039450`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x18001ce84`
- `0x180038974`
- `0x18003e94c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e9e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003eaab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003eb4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ec1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ecc9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ed75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ee17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003eec3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e9e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003eaab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003eb4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ec1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ecc9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ed75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ee17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003eec3`
- `MFPlat!MFCreateAttributes` at `0x18003edfb`
- `MFPlat!MFCreateAttributes` at `0x18003edfb`

## pseudocode

```c
__int64 __fastcall CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        IMFAttributes **a4)
{
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 *v11; // rcx
  HRESULT v12; // ebx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
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
  UINT32 cInitialSize; // [rsp+30h] [rbp-30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+38h] [rbp-28h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-20h] BYREF
  __int64 v48; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v49[2]; // [rsp+50h] [rbp-10h] BYREF
  __int64 v50; // [rsp+90h] [rbp+30h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v50,
    "CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs",
    1024);
  v8 = CTPtrArray<IMFStreamDescriptor,20>::operator[](a2, a3);
  v50 = v8;
  v10 = v8;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v49[0] = 0;
  v47 = 0;
  v48 = 0;
  ppMFAttributes = 0;
  cInitialSize = 0;
  if ( !v10 )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    v12 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs",
          1034,
          -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v15 = 160;
LABEL_14:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids,
        a1,
        -2147418113);
      goto LABEL_96;
    }
    goto LABEL_96;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 272LL))(v10, v49);
  if ( v12 < 0 )
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
      if ( *((_DWORD *)v19 + 499) != v12 )
        CallStackContext::TraceFailure(v19, "CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs", 1035, v12);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_96;
    v20 = 161;
    goto LABEL_27;
  }
  if ( !v49[0] )
  {
    v21 = (__int64 *)CallStackTracing::s_wpInstance;
    v12 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
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
      if ( *((_DWORD *)v23 + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          v23,
          "CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs",
          1036,
          -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v15 = 162;
      goto LABEL_14;
    }
    goto LABEL_96;
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v49[0] + 56LL))(
         v49[0],
         &v47) < 0 )
  {
    ComSmartPtr<IMFTranscodeProfile>::operator=(&v47);
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v49[0] + 40LL))(v49[0], 0, &v47);
    if ( v12 < 0 )
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
        if ( *((_DWORD *)v27 + 499) != v12 )
          CallStackContext::TraceFailure(
            v27,
            "CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs",
            1041,
            v12);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_96;
      v20 = 163;
      goto LABEL_27;
    }
  }
  v12 = (**v47)(v47, &IID_IMFAttributes, &v48);
  if ( v12 < 0 )
  {
    v29 = (__int64 *)CallStackTracing::s_wpInstance;
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
      if ( *((_DWORD *)v31 + 499) != v12 )
        CallStackContext::TraceFailure(v31, "CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs", 1044, v12);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_96;
    v20 = 164;
    goto LABEL_27;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v48 + 240LL))(v48, &cInitialSize);
  if ( v12 < 0 )
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
      if ( *((_DWORD *)v35 + 499) != v12 )
        CallStackContext::TraceFailure(v35, "CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs", 1045, v12);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_96;
    v20 = 165;
    goto LABEL_27;
  }
  v12 = MFCreateAttributes(&ppMFAttributes, cInitialSize);
  if ( v12 < 0 )
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
      if ( *((_DWORD *)v39 + 499) != v12 )
        CallStackContext::TraceFailure(v39, "CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs", 1046, v12);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_96;
    v20 = 166;
LABEL_27:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids, a1, v12);
    goto LABEL_96;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v48 + 256LL))(v48, ppMFAttributes);
  if ( v12 >= 0 )
  {
    *a4 = ppMFAttributes;
    ppMFAttributes = 0;
    goto LABEL_96;
  }
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
    if ( *((_DWORD *)v43 + 499) != v12 )
      CallStackContext::TraceFailure(v43, "CTranscodeProfileAdjuster_FillWithSource::GetSrcStreamMTAttrs", 1047, v12);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v20 = 167;
    goto LABEL_27;
  }
LABEL_96:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFAttributes);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v48);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v47);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v49);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v50);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v50);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003e94c  mov     [rsp-28h+arg_8], rbx
0x18003e951  mov     [rsp-28h+arg_10], rsi
0x18003e956  push    rbp
0x18003e957  push    rdi
0x18003e958  push    r12
0x18003e95a  push    r14
0x18003e95c  push    r15
0x18003e95e  mov     rbp, rsp
0x18003e961  sub     rsp, 60h
0x18003e965  mov     ebx, r8d
0x18003e968  lea     r12, aCtranscodeprof_2; "CTranscodeProfileAdjuster_FillWithSourc"...
0x18003e96f  mov     rdi, rdx
0x18003e972  mov     rsi, rcx
0x18003e975  mov     rdx, r12; char *
0x18003e978  lea     rcx, [rbp+arg_0]; this
0x18003e97c  mov     r8d, 400h; int
0x18003e982  mov     r14, r9
0x18003e985  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003e98a  mov     edx, ebx
0x18003e98c  mov     rcx, rdi
0x18003e98f  call    ??A?$CTPtrArray@UIMFStreamDescriptor@@$0BE@@@QEBAPEAUIMFStreamDescriptor@@K@Z; CTPtrArray<IMFStreamDescriptor,20>::operator[](ulong)
0x18003e994  xor     r15d, r15d
0x18003e997  mov     [rbp+arg_0], rax
0x18003e99b  mov     rbx, rax
0x18003e99e  test    rax, rax
0x18003e9a1  jz      short loc_18003E9B2
0x18003e9a3  mov     rcx, [rax]
0x18003e9a6  mov     rax, [rcx+8]
0x18003e9aa  mov     rcx, rbx
0x18003e9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9b2  mov     [rbp+var_10], r15
0x18003e9b6  mov     [rbp+var_20], r15
0x18003e9ba  mov     [rbp+var_18], r15
0x18003e9be  mov     [rbp+ppMFAttributes], r15
0x18003e9c2  mov     [rbp+cInitialSize], r15d
0x18003e9c6  test    rbx, rbx
0x18003e9c9  jnz     loc_18003EA7F
0x18003e9cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e9d6  mov     edi, 8000FFFFh
0x18003e9db  mov     ebx, edi
0x18003e9dd  test    rcx, rcx
0x18003e9e0  jnz     short loc_18003EA23
0x18003e9e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e9e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e9ef  mov     rcx, rax
0x18003e9f2  test    rax, rax
0x18003e9f5  jz      short loc_18003EA15
0x18003e9f7  mov     rax, [rax]
0x18003e9fa  mov     edx, 7F0h
0x18003e9ff  mov     rax, [rax+8]
0x18003ea03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea08  test    eax, eax
0x18003ea0a  jz      short loc_18003EA15
0x18003ea0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ea13  jmp     short loc_18003EA23
0x18003ea15  lea     rcx, qword_180069A90; this
0x18003ea1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ea23  cmp     [rcx+8], r15b
0x18003ea27  jz      short loc_18003EA4A
0x18003ea29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ea2e  cmp     [rax+7CCh], edi
0x18003ea34  jz      short loc_18003EA4A
0x18003ea36  mov     r9d, edi; int
0x18003ea39  mov     r8d, 40Ah; int
0x18003ea3f  mov     rdx, r12; char *
0x18003ea42  mov     rcx, rax; this
0x18003ea45  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ea4a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003ea4f  cmp     al, 1
0x18003ea51  jb      loc_18003EF49
0x18003ea57  mov     edx, 0A0h
0x18003ea5c  mov     [rsp+60h+var_40], edi
0x18003ea60  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea67  lea     r8, WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids
0x18003ea6e  mov     r9, rsi
0x18003ea71  mov     rcx, [rcx+10h]
0x18003ea75  call    WPP_SF_qd
0x18003ea7a  jmp     loc_18003EF49
0x18003ea7f  mov     rax, [rbx]
0x18003ea82  lea     rdx, [rbp+var_10]
0x18003ea86  mov     rcx, rbx
0x18003ea89  mov     rax, [rax+110h]
0x18003ea90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea95  mov     ebx, eax
0x18003ea97  test    eax, eax
0x18003ea99  jns     loc_18003EB2E
0x18003ea9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eaa6  test    rcx, rcx
0x18003eaa9  jnz     short loc_18003EAEC
0x18003eaab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003eab1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eab8  mov     rcx, rax
0x18003eabb  test    rax, rax
0x18003eabe  jz      short loc_18003EADE
0x18003eac0  mov     rax, [rax]
0x18003eac3  mov     edx, 7F0h
0x18003eac8  mov     rax, [rax+8]
0x18003eacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ead1  test    eax, eax
0x18003ead3  jz      short loc_18003EADE
0x18003ead5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eadc  jmp     short loc_18003EAEC
0x18003eade  lea     rcx, qword_180069A90; this
0x18003eae5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eaec  cmp     [rcx+8], r15b
0x18003eaf0  jz      short loc_18003EB13
0x18003eaf2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003eaf7  cmp     [rax+7CCh], ebx
0x18003eafd  jz      short loc_18003EB13
0x18003eaff  mov     r9d, ebx; int
0x18003eb02  mov     r8d, 40Bh; int
0x18003eb08  mov     rdx, r12; char *
0x18003eb0b  mov     rcx, rax; this
0x18003eb0e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003eb13  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003eb18  cmp     al, 1
0x18003eb1a  jb      loc_18003EF49
0x18003eb20  mov     edx, 0A1h
0x18003eb25  mov     [rsp+60h+var_40], ebx
0x18003eb29  jmp     loc_18003EA60
0x18003eb2e  mov     rcx, [rbp+var_10]
0x18003eb32  test    rcx, rcx
0x18003eb35  jnz     loc_18003EBCD
0x18003eb3b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eb42  mov     edi, 8000FFFFh
0x18003eb47  mov     ebx, edi
0x18003eb49  test    rcx, rcx
0x18003eb4c  jnz     short loc_18003EB8F
0x18003eb4e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003eb54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eb5b  mov     rcx, rax
0x18003eb5e  test    rax, rax
0x18003eb61  jz      short loc_18003EB81
0x18003eb63  mov     rax, [rax]
0x18003eb66  mov     edx, 7F0h
0x18003eb6b  mov     rax, [rax+8]
0x18003eb6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb74  test    eax, eax
0x18003eb76  jz      short loc_18003EB81
0x18003eb78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eb7f  jmp     short loc_18003EB8F
0x18003eb81  lea     rcx, qword_180069A90; this
0x18003eb88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eb8f  cmp     [rcx+8], r15b
0x18003eb93  jz      short loc_18003EBB6
0x18003eb95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003eb9a  cmp     [rax+7CCh], edi
0x18003eba0  jz      short loc_18003EBB6
0x18003eba2  mov     r9d, edi; int
0x18003eba5  mov     r8d, 40Ch; int
0x18003ebab  mov     rdx, r12; char *
0x18003ebae  mov     rcx, rax; this
0x18003ebb1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ebb6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003ebbb  cmp     al, 1
0x18003ebbd  jb      loc_18003EF49
0x18003ebc3  mov     edx, 0A2h
0x18003ebc8  jmp     loc_18003EA5C
0x18003ebcd  mov     rax, [rcx]
0x18003ebd0  lea     rdx, [rbp+var_20]
0x18003ebd4  mov     rax, [rax+38h]
0x18003ebd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebdd  test    eax, eax
0x18003ebdf  jns     loc_18003EC99
0x18003ebe5  lea     rcx, [rbp+var_20]
0x18003ebe9  call    ??4?$ComSmartPtr@UIMFTranscodeProfile@@@@QEAAPEAUIMFTranscodeProfile@@PEAU1@@Z; ComSmartPtr<IMFTranscodeProfile>::operator=(IMFTranscodeProfile *)
0x18003ebee  mov     rcx, [rbp+var_10]
0x18003ebf2  lea     r8, [rbp+var_20]
0x18003ebf6  xor     edx, edx
0x18003ebf8  mov     rax, [rcx]
0x18003ebfb  mov     rax, [rax+28h]
0x18003ebff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec04  mov     ebx, eax
0x18003ec06  test    eax, eax
0x18003ec08  jns     loc_18003EC99
0x18003ec0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ec15  test    rcx, rcx
0x18003ec18  jnz     short loc_18003EC5B
0x18003ec1a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ec20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ec27  mov     rcx, rax
0x18003ec2a  test    rax, rax
0x18003ec2d  jz      short loc_18003EC4D
0x18003ec2f  mov     rax, [rax]
0x18003ec32  mov     edx, 7F0h
0x18003ec37  mov     rax, [rax+8]
0x18003ec3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec40  test    eax, eax
0x18003ec42  jz      short loc_18003EC4D
0x18003ec44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ec4b  jmp     short loc_18003EC5B
0x18003ec4d  lea     rcx, qword_180069A90; this
0x18003ec54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ec5b  cmp     [rcx+8], r15b
0x18003ec5f  jz      short loc_18003EC82
0x18003ec61  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ec66  cmp     [rax+7CCh], ebx
0x18003ec6c  jz      short loc_18003EC82
0x18003ec6e  mov     r9d, ebx; int
0x18003ec71  mov     r8d, 411h; int
0x18003ec77  mov     rdx, r12; char *
0x18003ec7a  mov     rcx, rax; this
0x18003ec7d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ec82  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003ec87  cmp     al, 1
0x18003ec89  jb      loc_18003EF49
0x18003ec8f  mov     edx, 0A3h
0x18003ec94  jmp     loc_18003EB25
0x18003ec99  mov     rcx, [rbp+var_20]
0x18003ec9d  lea     r8, [rbp+var_18]
0x18003eca1  lea     rdx, IID_IMFAttributes
0x18003eca8  mov     rax, [rcx]
0x18003ecab  mov     rax, [rax]
0x18003ecae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecb3  mov     ebx, eax
0x18003ecb5  test    eax, eax
0x18003ecb7  jns     loc_18003ED48
0x18003ecbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ecc4  test    rcx, rcx
0x18003ecc7  jnz     short loc_18003ED0A
0x18003ecc9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003eccf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ecd6  mov     rcx, rax
0x18003ecd9  test    rax, rax
0x18003ecdc  jz      short loc_18003ECFC
0x18003ecde  mov     rax, [rax]
0x18003ece1  mov     edx, 7F0h
0x18003ece6  mov     rax, [rax+8]
0x18003ecea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecef  test    eax, eax
0x18003ecf1  jz      short loc_18003ECFC
0x18003ecf3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ecfa  jmp     short loc_18003ED0A
0x18003ecfc  lea     rcx, qword_180069A90; this
0x18003ed03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ed0a  cmp     [rcx+8], r15b
0x18003ed0e  jz      short loc_18003ED31
0x18003ed10  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ed15  cmp     [rax+7CCh], ebx
0x18003ed1b  jz      short loc_18003ED31
0x18003ed1d  mov     r9d, ebx; int
0x18003ed20  mov     r8d, 414h; int
0x18003ed26  mov     rdx, r12; char *
0x18003ed29  mov     rcx, rax; this
0x18003ed2c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ed31  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003ed36  cmp     al, 1
0x18003ed38  jb      loc_18003EF49
0x18003ed3e  mov     edx, 0A4h
0x18003ed43  jmp     loc_18003EB25
0x18003ed48  mov     rcx, [rbp+var_18]
0x18003ed4c  lea     rdx, [rbp+cInitialSize]
0x18003ed50  mov     rax, [rcx]
0x18003ed53  mov     rax, [rax+0F0h]
0x18003ed5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed5f  mov     ebx, eax
0x18003ed61  test    eax, eax
0x18003ed63  jns     loc_18003EDF4
0x18003ed69  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ed70  test    rcx, rcx
0x18003ed73  jnz     short loc_18003EDB6
0x18003ed75  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ed7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ed82  mov     rcx, rax
0x18003ed85  test    rax, rax
0x18003ed88  jz      short loc_18003EDA8
0x18003ed8a  mov     rax, [rax]
0x18003ed8d  mov     edx, 7F0h
0x18003ed92  mov     rax, [rax+8]
0x18003ed96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed9b  test    eax, eax
0x18003ed9d  jz      short loc_18003EDA8
0x18003ed9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eda6  jmp     short loc_18003EDB6
0x18003eda8  lea     rcx, qword_180069A90; this
0x18003edaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003edb6  cmp     [rcx+8], r15b
0x18003edba  jz      short loc_18003EDDD
0x18003edbc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003edc1  cmp     [rax+7CCh], ebx
0x18003edc7  jz      short loc_18003EDDD
0x18003edc9  mov     r9d, ebx; int
0x18003edcc  mov     r8d, 415h; int
0x18003edd2  mov     rdx, r12; char *
0x18003edd5  mov     rcx, rax; this
0x18003edd8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003eddd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003ede2  cmp     al, 1
0x18003ede4  jb      loc_18003EF49
0x18003edea  mov     edx, 0A5h
0x18003edef  jmp     loc_18003EB25
0x18003edf4  mov     edx, [rbp+cInitialSize]; cInitialSize
0x18003edf7  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18003edfb  call    cs:__imp_MFCreateAttributes
0x18003ee01  mov     ebx, eax
0x18003ee03  test    eax, eax
0x18003ee05  jns     loc_18003EE96
0x18003ee0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee12  test    rcx, rcx
0x18003ee15  jnz     short loc_18003EE58
  ... truncated ...
```
