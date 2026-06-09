# CTranscodeEngine::OnCreateObjectFromByteStream(IMFAsyncResult *)

- ea: `0x180010630`
- end: `0x180010bc3`
- name: `?OnCreateObjectFromByteStream@CTranscodeEngine@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `1427`
- prototype: `void __fastcall(CTranscodeEngine *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c7e0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18000b41c`
- `0x180010630`
- `0x180010fcc`
- `0x18001a330`
- `0x18001c280`
- `0x18002e75c`
- `0x18002f120`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010a98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010a98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010688`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010aa9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010688`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010aa9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800106c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010768`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010817`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800108c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010979`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010a16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010adc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800106c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010768`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010817`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800108c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010979`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010a16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010adc`

## string_xrefs

- `0x180010646`: `CTranscodeEngine::OnCreateObjectFromByteStream`

## pseudocode

```c
void __fastcall CTranscodeEngine::OnCreateObjectFromByteStream(CTranscodeEngine *this, struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  int TopologyAndSetOnSession; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
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
  __int64 v34; // [rsp+30h] [rbp-10h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-8h] BYREF
  char v36; // [rsp+70h] [rbp+30h] BYREF
  int v37; // [rsp+80h] [rbp+40h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, char *); // [rsp+88h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v36,
    "CTranscodeEngine::OnCreateObjectFromByteStream",
    483);
  v35 = 0;
  v34 = 0;
  v38 = 0;
  v37 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((int *)this + 168) >= 5 )
    goto LABEL_82;
  TopologyAndSetOnSession = ((__int64 (__fastcall *)(struct IMFAsyncResult *))a2->lpVtbl->GetStatus)(a2);
  if ( TopologyAndSetOnSession >= 0 )
  {
    TopologyAndSetOnSession = ((__int64 (__fastcall *)(struct IMFAsyncResult *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))a2->lpVtbl->GetState)(
                                a2,
                                &v35);
    if ( TopologyAndSetOnSession < 0 )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != TopologyAndSetOnSession )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CTranscodeEngine::OnCreateObjectFromByteStream",
            498,
            TopologyAndSetOnSession);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v9 = 60;
      goto LABEL_80;
    }
    TopologyAndSetOnSession = (**v35)(v35, &GUID_fbe5a32d_a497_4b61_bb85_97b1a848a6e3, &v34);
    if ( TopologyAndSetOnSession < 0 )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
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
        if ( *((_DWORD *)v17 + 499) != TopologyAndSetOnSession )
          CallStackContext::TraceFailure(
            v17,
            "CTranscodeEngine::OnCreateObjectFromByteStream",
            499,
            TopologyAndSetOnSession);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v9 = 61;
      goto LABEL_80;
    }
    TopologyAndSetOnSession = (*(__int64 (__fastcall **)(__int64, struct IMFAsyncResult *, int *, __int64 (__fastcall ****)(_QWORD, GUID *, char *)))(*(_QWORD *)v34 + 64LL))(
                                v34,
                                a2,
                                &v37,
                                &v38);
    if ( TopologyAndSetOnSession < 0 )
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
        if ( *((_DWORD *)v21 + 499) != TopologyAndSetOnSession )
          CallStackContext::TraceFailure(
            v21,
            "CTranscodeEngine::OnCreateObjectFromByteStream",
            501,
            TopologyAndSetOnSession);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v9 = 62;
      goto LABEL_80;
    }
    TopologyAndSetOnSession = (**v38)(v38, &GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66, (char *)this + 176);
    if ( TopologyAndSetOnSession < 0 )
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
        if ( *((_DWORD *)v25 + 499) != TopologyAndSetOnSession )
          CallStackContext::TraceFailure(
            v25,
            "CTranscodeEngine::OnCreateObjectFromByteStream",
            502,
            TopologyAndSetOnSession);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v9 = 63;
      goto LABEL_80;
    }
    TopologyAndSetOnSession = CTranscodeEngine::_ConfigureSourceAndProfile(this);
    if ( TopologyAndSetOnSession < 0 )
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
        if ( *((_DWORD *)v29 + 499) != TopologyAndSetOnSession )
          CallStackContext::TraceFailure(
            v29,
            "CTranscodeEngine::OnCreateObjectFromByteStream",
            504,
            TopologyAndSetOnSession);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v9 = 64;
      goto LABEL_80;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    CTranscodeEngine::_SetPropertyStore(this);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    if ( *((int *)this + 168) < 5 )
    {
      TopologyAndSetOnSession = CTranscodeEngine::_CreateTopologyAndSetOnSession(this, 0);
      if ( TopologyAndSetOnSession < 0 )
      {
        v31 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
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
          if ( *((_DWORD *)v33 + 499) != TopologyAndSetOnSession )
            CallStackContext::TraceFailure(
              v33,
              "CTranscodeEngine::OnCreateObjectFromByteStream",
              520,
              TopologyAndSetOnSession);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_81;
        v9 = 65;
        goto LABEL_80;
      }
    }
LABEL_82:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    goto LABEL_83;
  }
  v6 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
    CallStackTracing::s_wpInstance = v7;
    if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
    {
      v6 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v6 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v6 + 8) )
  {
    v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
    if ( *((_DWORD *)v8 + 499) != TopologyAndSetOnSession )
      CallStackContext::TraceFailure(v8, "CTranscodeEngine::OnCreateObjectFromByteStream", 496, TopologyAndSetOnSession);
  }
  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    goto LABEL_81;
  v9 = 59;
LABEL_80:
  WPP_SF_qd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v9,
    &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids,
    this,
    TopologyAndSetOnSession);
LABEL_81:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  CTranscodeEngine::_HandleAsyncError(this, TopologyAndSetOnSession);
LABEL_83:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v38);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v34);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v35);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v36);
}

```

## disassembly

```asm
0x180010630  mov     [rsp-28h+arg_8], rbx
0x180010635  push    rbp
0x180010636  push    rsi
0x180010637  push    rdi
0x180010638  push    r12
0x18001063a  push    r14
0x18001063c  mov     rbp, rsp
0x18001063f  sub     rsp, 40h
0x180010643  mov     r14, rdx
0x180010646  lea     r12, aCtranscodeengi_3; "CTranscodeEngine::OnCreateObjectFromByt"...
0x18001064d  mov     rsi, rcx
0x180010650  mov     rdx, r12; char *
0x180010653  mov     r8d, 1E3h; int
0x180010659  lea     rcx, [rbp+arg_0]; this
0x18001065d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180010662  lea     rdi, [rsi+8]
0x180010666  mov     [rbp+var_8], 0
0x18001066e  mov     rcx, rdi; lpCriticalSection
0x180010671  mov     [rbp+var_10], 0
0x180010679  mov     [rbp+arg_18], 0
0x180010681  mov     [rbp+arg_10], 0
0x180010688  call    cs:__imp_EnterCriticalSection
0x18001068e  cmp     dword ptr [rsi+2A0h], 5
0x180010695  jge     loc_180010B85
0x18001069b  mov     rax, [r14]
0x18001069e  mov     rcx, r14
0x1800106a1  mov     rax, [rax+20h]
0x1800106a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106aa  mov     ebx, eax
0x1800106ac  test    eax, eax
0x1800106ae  jns     loc_18001073F
0x1800106b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800106bb  test    rcx, rcx
0x1800106be  jnz     short loc_180010701
0x1800106c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800106c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800106cd  mov     rcx, rax
0x1800106d0  test    rax, rax
0x1800106d3  jz      short loc_1800106F3
0x1800106d5  mov     rax, [rax]
0x1800106d8  mov     edx, 7F0h
0x1800106dd  mov     rax, [rax+8]
0x1800106e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106e6  test    eax, eax
0x1800106e8  jz      short loc_1800106F3
0x1800106ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800106f1  jmp     short loc_180010701
0x1800106f3  lea     rcx, qword_180069A90; this
0x1800106fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010701  cmp     byte ptr [rcx+8], 0
0x180010705  jz      short loc_180010728
0x180010707  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001070c  cmp     [rax+7CCh], ebx
0x180010712  jz      short loc_180010728
0x180010714  mov     r9d, ebx; int
0x180010717  mov     r8d, 1F0h; int
0x18001071d  mov     rdx, r12; char *
0x180010720  mov     rcx, rax; this
0x180010723  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010728  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001072d  cmp     al, 1
0x18001072f  jb      loc_180010B70
0x180010735  mov     edx, 3Bh ; ';'
0x18001073a  jmp     loc_180010B52
0x18001073f  mov     rax, [r14]
0x180010742  lea     rdx, [rbp+var_8]
0x180010746  mov     rcx, r14
0x180010749  mov     rax, [rax+18h]
0x18001074d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010752  mov     ebx, eax
0x180010754  test    eax, eax
0x180010756  jns     loc_1800107E7
0x18001075c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010763  test    rcx, rcx
0x180010766  jnz     short loc_1800107A9
0x180010768  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001076e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010775  mov     rcx, rax
0x180010778  test    rax, rax
0x18001077b  jz      short loc_18001079B
0x18001077d  mov     rax, [rax]
0x180010780  mov     edx, 7F0h
0x180010785  mov     rax, [rax+8]
0x180010789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001078e  test    eax, eax
0x180010790  jz      short loc_18001079B
0x180010792  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010799  jmp     short loc_1800107A9
0x18001079b  lea     rcx, qword_180069A90; this
0x1800107a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800107a9  cmp     byte ptr [rcx+8], 0
0x1800107ad  jz      short loc_1800107D0
0x1800107af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800107b4  cmp     [rax+7CCh], ebx
0x1800107ba  jz      short loc_1800107D0
0x1800107bc  mov     r9d, ebx; int
0x1800107bf  mov     r8d, 1F2h; int
0x1800107c5  mov     rdx, r12; char *
0x1800107c8  mov     rcx, rax; this
0x1800107cb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800107d0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800107d5  cmp     al, 1
0x1800107d7  jb      loc_180010B70
0x1800107dd  mov     edx, 3Ch ; '<'
0x1800107e2  jmp     loc_180010B52
0x1800107e7  mov     rcx, [rbp+var_8]
0x1800107eb  lea     r8, [rbp+var_10]
0x1800107ef  lea     rdx, _GUID_fbe5a32d_a497_4b61_bb85_97b1a848a6e3
0x1800107f6  mov     rax, [rcx]
0x1800107f9  mov     rax, [rax]
0x1800107fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010801  mov     ebx, eax
0x180010803  test    eax, eax
0x180010805  jns     loc_180010896
0x18001080b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010812  test    rcx, rcx
0x180010815  jnz     short loc_180010858
0x180010817  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001081d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010824  mov     rcx, rax
0x180010827  test    rax, rax
0x18001082a  jz      short loc_18001084A
0x18001082c  mov     rax, [rax]
0x18001082f  mov     edx, 7F0h
0x180010834  mov     rax, [rax+8]
0x180010838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001083d  test    eax, eax
0x18001083f  jz      short loc_18001084A
0x180010841  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010848  jmp     short loc_180010858
0x18001084a  lea     rcx, qword_180069A90; this
0x180010851  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010858  cmp     byte ptr [rcx+8], 0
0x18001085c  jz      short loc_18001087F
0x18001085e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010863  cmp     [rax+7CCh], ebx
0x180010869  jz      short loc_18001087F
0x18001086b  mov     r9d, ebx; int
0x18001086e  mov     r8d, 1F3h; int
0x180010874  mov     rdx, r12; char *
0x180010877  mov     rcx, rax; this
0x18001087a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001087f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180010884  cmp     al, 1
0x180010886  jb      loc_180010B70
0x18001088c  mov     edx, 3Dh ; '='
0x180010891  jmp     loc_180010B52
0x180010896  mov     rcx, [rbp+var_10]
0x18001089a  lea     r9, [rbp+arg_18]
0x18001089e  lea     r8, [rbp+arg_10]
0x1800108a2  mov     rdx, r14
0x1800108a5  mov     rax, [rcx]
0x1800108a8  mov     rax, [rax+40h]
0x1800108ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108b1  mov     ebx, eax
0x1800108b3  test    eax, eax
0x1800108b5  jns     loc_180010946
0x1800108bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800108c2  test    rcx, rcx
0x1800108c5  jnz     short loc_180010908
0x1800108c7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800108cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800108d4  mov     rcx, rax
0x1800108d7  test    rax, rax
0x1800108da  jz      short loc_1800108FA
0x1800108dc  mov     rax, [rax]
0x1800108df  mov     edx, 7F0h
0x1800108e4  mov     rax, [rax+8]
0x1800108e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108ed  test    eax, eax
0x1800108ef  jz      short loc_1800108FA
0x1800108f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800108f8  jmp     short loc_180010908
0x1800108fa  lea     rcx, qword_180069A90; this
0x180010901  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010908  cmp     byte ptr [rcx+8], 0
0x18001090c  jz      short loc_18001092F
0x18001090e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010913  cmp     [rax+7CCh], ebx
0x180010919  jz      short loc_18001092F
0x18001091b  mov     r9d, ebx; int
0x18001091e  mov     r8d, 1F5h; int
0x180010924  mov     rdx, r12; char *
0x180010927  mov     rcx, rax; this
0x18001092a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001092f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180010934  cmp     al, 1
0x180010936  jb      loc_180010B70
0x18001093c  mov     edx, 3Eh ; '>'
0x180010941  jmp     loc_180010B52
0x180010946  mov     rcx, [rbp+arg_18]
0x18001094a  lea     r8, [rsi+0B0h]
0x180010951  lea     rdx, _GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66
0x180010958  mov     rax, [rcx]
0x18001095b  mov     rax, [rax]
0x18001095e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010963  mov     ebx, eax
0x180010965  test    eax, eax
0x180010967  jns     loc_1800109F8
0x18001096d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010974  test    rcx, rcx
0x180010977  jnz     short loc_1800109BA
0x180010979  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001097f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010986  mov     rcx, rax
0x180010989  test    rax, rax
0x18001098c  jz      short loc_1800109AC
0x18001098e  mov     rax, [rax]
0x180010991  mov     edx, 7F0h
0x180010996  mov     rax, [rax+8]
0x18001099a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001099f  test    eax, eax
0x1800109a1  jz      short loc_1800109AC
0x1800109a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800109aa  jmp     short loc_1800109BA
0x1800109ac  lea     rcx, qword_180069A90; this
0x1800109b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800109ba  cmp     byte ptr [rcx+8], 0
0x1800109be  jz      short loc_1800109E1
0x1800109c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800109c5  cmp     [rax+7CCh], ebx
0x1800109cb  jz      short loc_1800109E1
0x1800109cd  mov     r9d, ebx; int
0x1800109d0  mov     r8d, 1F6h; int
0x1800109d6  mov     rdx, r12; char *
0x1800109d9  mov     rcx, rax; this
0x1800109dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800109e1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800109e6  cmp     al, 1
0x1800109e8  jb      loc_180010B70
0x1800109ee  mov     edx, 3Fh ; '?'
0x1800109f3  jmp     loc_180010B52
0x1800109f8  mov     rcx, rsi; this
0x1800109fb  call    ?_ConfigureSourceAndProfile@CTranscodeEngine@@IEAAJXZ; CTranscodeEngine::_ConfigureSourceAndProfile(void)
0x180010a00  mov     ebx, eax
0x180010a02  test    eax, eax
0x180010a04  jns     loc_180010A95
0x180010a0a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010a11  test    rcx, rcx
0x180010a14  jnz     short loc_180010A57
0x180010a16  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010a1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010a23  mov     rcx, rax
0x180010a26  test    rax, rax
0x180010a29  jz      short loc_180010A49
0x180010a2b  mov     rax, [rax]
0x180010a2e  mov     edx, 7F0h
0x180010a33  mov     rax, [rax+8]
0x180010a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a3c  test    eax, eax
0x180010a3e  jz      short loc_180010A49
0x180010a40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010a47  jmp     short loc_180010A57
0x180010a49  lea     rcx, qword_180069A90; this
0x180010a50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010a57  cmp     byte ptr [rcx+8], 0
0x180010a5b  jz      short loc_180010A7E
0x180010a5d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010a62  cmp     [rax+7CCh], ebx
0x180010a68  jz      short loc_180010A7E
0x180010a6a  mov     r9d, ebx; int
0x180010a6d  mov     r8d, 1F8h; int
0x180010a73  mov     rdx, r12; char *
0x180010a76  mov     rcx, rax; this
0x180010a79  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010a7e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180010a83  cmp     al, 1
0x180010a85  jb      loc_180010B70
0x180010a8b  mov     edx, 40h ; '@'
0x180010a90  jmp     loc_180010B52
0x180010a95  mov     rcx, rdi; lpCriticalSection
0x180010a98  call    cs:__imp_LeaveCriticalSection
0x180010a9e  mov     rcx, rsi; this
0x180010aa1  call    ?_SetPropertyStore@CTranscodeEngine@@IEAAXXZ; CTranscodeEngine::_SetPropertyStore(void)
0x180010aa6  mov     rcx, rdi; lpCriticalSection
0x180010aa9  call    cs:__imp_EnterCriticalSection
0x180010aaf  cmp     dword ptr [rsi+2A0h], 5
0x180010ab6  jge     loc_180010B85
0x180010abc  xor     edx, edx; bool
0x180010abe  mov     rcx, rsi; this
0x180010ac1  call    ?_CreateTopologyAndSetOnSession@CTranscodeEngine@@IEAAJ_N@Z; CTranscodeEngine::_CreateTopologyAndSetOnSession(bool)
0x180010ac6  mov     ebx, eax
0x180010ac8  test    eax, eax
0x180010aca  jns     loc_180010B85
0x180010ad0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010ad7  test    rcx, rcx
0x180010ada  jnz     short loc_180010B1D
0x180010adc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010ae2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010ae9  mov     rcx, rax
0x180010aec  test    rax, rax
0x180010aef  jz      short loc_180010B0F
0x180010af1  mov     rax, [rax]
0x180010af4  mov     edx, 7F0h
0x180010af9  mov     rax, [rax+8]
0x180010afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b02  test    eax, eax
0x180010b04  jz      short loc_180010B0F
0x180010b06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010b0d  jmp     short loc_180010B1D
  ... truncated ...
```
