# CTranscodeEngine::_SetPropertyStore(void)

- ea: `0x180010fcc`
- end: `0x1800115a7`
- name: `?_SetPropertyStore@CTranscodeEngine@@IEAAXXZ`
- size: `1499`
- prototype: `void __fastcall(CTranscodeEngine *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010630`
- `0x180010bcc`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x180010fcc`
- `0x18001a330`
- `0x18001c280`
- `0x18002e1bc`
- `0x18004f410`
- `0x1800539d4`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011366`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800113b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011366`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800113b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011001`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011568`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011001`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011568`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001105a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011218`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800112c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001140b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800114ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001105a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011218`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800112c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001140b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800114ba`
- `MFPlat!MFCreateStreamOnMFByteStream` at `0x1800111fc`
- `MFPlat!MFCreateStreamOnMFByteStream` at `0x1800111fc`

## pseudocode

```c
void __fastcall CTranscodeEngine::_SetPropertyStore(CTranscodeEngine *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v3; // rdx
  HRESULT v4; // esi
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  int (__fastcall ***v9)(_QWORD, GUID *, IUnknown **); // rcx
  struct IInitializeWithStream *v10; // rcx
  IMFByteStream *v11; // rcx
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  int v21; // esi
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  IStream *ppStream; // [rsp+30h] [rbp-28h] BYREF
  __int64 v31; // [rsp+38h] [rbp-20h] BYREF
  IUnknown *punkObject[3]; // [rsp+40h] [rbp-18h] BYREF
  char v33; // [rsp+90h] [rbp+38h] BYREF
  int v34; // [rsp+98h] [rbp+40h] BYREF
  struct IInitializeWithStream *v35; // [rsp+A0h] [rbp+48h] BYREF
  LPVOID ppvObject; // [rsp+A8h] [rbp+50h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v35 = 0;
  punkObject[0] = 0;
  ppvObject = 0;
  v34 = 0;
  v31 = 0;
  ppStream = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((int *)this + 168) >= 5 )
    goto LABEL_56;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "CTranscodeEngine::_SetPropertyStore", 1899);
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 19) + 64LL))(*((_QWORD *)this + 19), &v31);
  if ( v4 < 0 )
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeEngine::_SetPropertyStore", 1899, v4);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_55;
    v8 = 212;
    goto LABEL_54;
  }
  if ( !*((_QWORD *)this + 22) && !*((_QWORD *)this + 16)
    || !v31
    || (*(int (__fastcall **)(__int64, const IID *, int *))(*(_QWORD *)v31 + 56LL))(
         v31,
         &MF_TRANSCODE_SKIP_METADATA_TRANSFER,
         &v34) >= 0
    && v34 == 1 )
  {
    goto LABEL_55;
  }
  v9 = (int (__fastcall ***)(_QWORD, GUID *, IUnknown **))*((_QWORD *)this + 22);
  if ( !v9
    || (**v9)(v9, &IID_IMFGetService, punkObject) < 0
    || MFGetService(punkObject[0], &MF_PROPERTY_HANDLER_SERVICE, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppvObject) >= 0 )
  {
    goto LABEL_26;
  }
  if ( ppvObject )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    ppvObject = 0;
  }
  if ( MFGetService(
         punkObject[0],
         &MF_PROPERTY_HANDLER_SERVICE,
         &GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f,
         (LPVOID *)&v35) < 0 )
  {
    v10 = v35;
    if ( v35 )
    {
      ((void (__fastcall *)(struct IInitializeWithStream *))v35->lpVtbl->Release)(v35);
      v10 = 0;
      v35 = 0;
    }
  }
  else
  {
LABEL_26:
    v10 = v35;
  }
  if ( !ppvObject )
  {
    if ( v10 )
      goto LABEL_31;
    CTranscodeEngine::_CreateIInitializeWithStream(this, (LPVOID *)&v35);
    v10 = v35;
  }
  if ( !v10 )
    goto LABEL_58;
LABEL_31:
  v11 = (IMFByteStream *)*((_QWORD *)this + 16);
  if ( !v11 )
    goto LABEL_58;
  v4 = MFCreateStreamOnMFByteStream(v11, &ppStream);
  if ( v4 < 0 )
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
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
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != v4 )
        CallStackContext::TraceFailure(v15, "CTranscodeEngine::_SetPropertyStore", 1932, v4);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_55;
    v8 = 213;
    goto LABEL_54;
  }
  v4 = ((__int64 (__fastcall *)(IStream *, _QWORD, _QWORD, _QWORD))ppStream->lpVtbl->Seek)(ppStream, 0, 0, 0);
  if ( v4 >= 0 )
  {
LABEL_58:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
    LeaveCriticalSection(v1);
    if ( v35 && ppStream )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "CTranscodeEngine::_SetPropertyStore", 1947);
      v21 = ((__int64 (__fastcall *)(struct IInitializeWithStream *, IStream *, _QWORD))v35->lpVtbl->Initialize)(
              v35,
              ppStream,
              0);
      if ( v21 < 0 )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
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
          if ( *((_DWORD *)v24 + 499) != v21 )
            CallStackContext::TraceFailure(v24, "CTranscodeEngine::_SetPropertyStore", 1947, v21);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_83;
        v25 = 215;
LABEL_82:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids, this, v21);
LABEL_83:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
        goto LABEL_57;
      }
      v21 = ((__int64 (__fastcall *)(struct IInitializeWithStream *, GUID *, LPVOID *))v35->lpVtbl->QueryInterface)(
              v35,
              &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
              &ppvObject);
      if ( v21 < 0 )
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
          if ( *((_DWORD *)v29 + 499) != v21 )
            CallStackContext::TraceFailure(v29, "CTranscodeEngine::_SetPropertyStore", 1948, v21);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_83;
        v25 = 216;
        goto LABEL_82;
      }
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
    }
    EnterCriticalSection(v1);
    if ( *((int *)this + 168) < 5 && ppvObject )
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 216LL))(v31, MF_TRANSCODE_SOURCE_PROPSTORE);
    goto LABEL_56;
  }
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
    if ( *((_DWORD *)v19 + 499) != v4 )
      CallStackContext::TraceFailure(v19, "CTranscodeEngine::_SetPropertyStore", 1937, v4);
  }
  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    goto LABEL_55;
  v8 = 214;
LABEL_54:
  WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids, this, v4);
LABEL_55:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
LABEL_56:
  LeaveCriticalSection(v1);
LABEL_57:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppStream);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v31);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppvObject);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(punkObject);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v35);
}

```

## disassembly

```asm
0x180010fcc  push    rbp
0x180010fce  push    rbx
0x180010fcf  push    rsi
0x180010fd0  push    rdi
0x180010fd1  push    r14
0x180010fd3  push    r15
0x180010fd5  mov     rbp, rsp
0x180010fd8  sub     rsp, 58h
0x180010fdc  xor     r14d, r14d
0x180010fdf  lea     rdi, [rcx+8]
0x180010fe3  mov     rbx, rcx
0x180010fe6  mov     [rbp+arg_10], r14
0x180010fea  mov     rcx, rdi; lpCriticalSection
0x180010fed  mov     [rbp+punkObject], r14
0x180010ff1  mov     [rbp+ppvObject], r14
0x180010ff5  mov     [rbp+arg_8], r14d
0x180010ff9  mov     [rbp+var_20], r14
0x180010ffd  mov     [rbp+ppStream], r14
0x180011001  call    cs:__imp_EnterCriticalSection
0x180011007  cmp     dword ptr [rbx+2A0h], 5
0x18001100e  jge     loc_180011363
0x180011014  lea     r15, aCtranscodeengi_9; "CTranscodeEngine::_SetPropertyStore"
0x18001101b  mov     r8d, 76Bh; int
0x180011021  mov     rdx, r15; char *
0x180011024  lea     rcx, [rbp+arg_0]; this
0x180011028  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001102d  mov     rcx, [rbx+98h]
0x180011034  lea     rdx, [rbp+var_20]
0x180011038  mov     rax, [rcx]
0x18001103b  mov     rax, [rax+40h]
0x18001103f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011044  mov     esi, eax
0x180011046  test    eax, eax
0x180011048  jns     loc_1800110D9
0x18001104e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011055  test    rcx, rcx
0x180011058  jnz     short loc_18001109B
0x18001105a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011060  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011067  mov     rcx, rax
0x18001106a  test    rax, rax
0x18001106d  jz      short loc_18001108D
0x18001106f  mov     rax, [rax]
0x180011072  mov     edx, 7F0h
0x180011077  mov     rax, [rax+8]
0x18001107b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011080  test    eax, eax
0x180011082  jz      short loc_18001108D
0x180011084  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001108b  jmp     short loc_18001109B
0x18001108d  lea     rcx, qword_180069A90; this
0x180011094  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001109b  cmp     [rcx+8], r14b
0x18001109f  jz      short loc_1800110C2
0x1800110a1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800110a6  cmp     [rax+7CCh], esi
0x1800110ac  jz      short loc_1800110C2
0x1800110ae  mov     r9d, esi; int
0x1800110b1  mov     r8d, 76Bh; int
0x1800110b7  mov     rdx, r15; char *
0x1800110ba  mov     rcx, rax; this
0x1800110bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800110c2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800110c7  cmp     al, 1
0x1800110c9  jb      loc_18001135A
0x1800110cf  mov     edx, 0D4h
0x1800110d4  jmp     loc_18001133C
0x1800110d9  cmp     [rbx+0B0h], r14
0x1800110e0  jnz     short loc_1800110EF
0x1800110e2  cmp     [rbx+80h], r14
0x1800110e9  jz      loc_18001135A
0x1800110ef  mov     rcx, [rbp+var_20]
0x1800110f3  test    rcx, rcx
0x1800110f6  jz      loc_18001135A
0x1800110fc  mov     rax, [rcx]
0x1800110ff  lea     r8, [rbp+arg_8]
0x180011103  lea     rdx, MF_TRANSCODE_SKIP_METADATA_TRANSFER
0x18001110a  mov     rax, [rax+38h]
0x18001110e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011113  test    eax, eax
0x180011115  js      short loc_180011121
0x180011117  cmp     [rbp+arg_8], 1
0x18001111b  jz      loc_18001135A
0x180011121  mov     rcx, [rbx+0B0h]
0x180011128  test    rcx, rcx
0x18001112b  jz      loc_1800111C0
0x180011131  mov     rax, [rcx]
0x180011134  lea     r8, [rbp+punkObject]
0x180011138  lea     rdx, IID_IMFGetService
0x18001113f  mov     rax, [rax]
0x180011142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011147  test    eax, eax
0x180011149  js      short loc_1800111C0
0x18001114b  mov     rcx, [rbp+punkObject]; punkObject
0x18001114f  lea     r9, [rbp+ppvObject]; ppvObject
0x180011153  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18001115a  lea     rdx, MF_PROPERTY_HANDLER_SERVICE; guidService
0x180011161  call    MFGetService
0x180011166  test    eax, eax
0x180011168  jns     short loc_1800111C0
0x18001116a  mov     rcx, [rbp+ppvObject]
0x18001116e  test    rcx, rcx
0x180011171  jz      short loc_180011183
0x180011173  mov     rax, [rcx]
0x180011176  mov     rax, [rax+10h]
0x18001117a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001117f  mov     [rbp+ppvObject], r14
0x180011183  mov     rcx, [rbp+punkObject]; punkObject
0x180011187  lea     r9, [rbp+arg_10]; ppvObject
0x18001118b  lea     r8, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f; riid
0x180011192  lea     rdx, MF_PROPERTY_HANDLER_SERVICE; guidService
0x180011199  call    MFGetService
0x18001119e  test    eax, eax
0x1800111a0  jns     short loc_1800111C0
0x1800111a2  mov     rcx, [rbp+arg_10]
0x1800111a6  test    rcx, rcx
0x1800111a9  jz      short loc_1800111C4
0x1800111ab  mov     rax, [rcx]
0x1800111ae  mov     rax, [rax+10h]
0x1800111b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111b7  mov     rcx, r14
0x1800111ba  mov     [rbp+arg_10], rcx
0x1800111be  jmp     short loc_1800111C4
0x1800111c0  mov     rcx, [rbp+arg_10]
0x1800111c4  cmp     [rbp+ppvObject], r14
0x1800111c8  jnz     short loc_1800111DF
0x1800111ca  test    rcx, rcx
0x1800111cd  jnz     short loc_1800111E8
0x1800111cf  lea     rdx, [rbp+arg_10]; struct IInitializeWithStream **
0x1800111d3  mov     rcx, rbx; this
0x1800111d6  call    ?_CreateIInitializeWithStream@CTranscodeEngine@@IEAAXPEAPEAUIInitializeWithStream@@@Z; CTranscodeEngine::_CreateIInitializeWithStream(IInitializeWithStream * *)
0x1800111db  mov     rcx, [rbp+arg_10]
0x1800111df  test    rcx, rcx
0x1800111e2  jz      loc_1800113A6
0x1800111e8  mov     rcx, [rbx+80h]; pByteStream
0x1800111ef  test    rcx, rcx
0x1800111f2  jz      loc_1800113A6
0x1800111f8  lea     rdx, [rbp+ppStream]; ppStream
0x1800111fc  call    cs:__imp_MFCreateStreamOnMFByteStream
0x180011202  mov     esi, eax
0x180011204  test    eax, eax
0x180011206  jns     loc_180011297
0x18001120c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011213  test    rcx, rcx
0x180011216  jnz     short loc_180011259
0x180011218  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001121e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011225  mov     rcx, rax
0x180011228  test    rax, rax
0x18001122b  jz      short loc_18001124B
0x18001122d  mov     rax, [rax]
0x180011230  mov     edx, 7F0h
0x180011235  mov     rax, [rax+8]
0x180011239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001123e  test    eax, eax
0x180011240  jz      short loc_18001124B
0x180011242  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011249  jmp     short loc_180011259
0x18001124b  lea     rcx, qword_180069A90; this
0x180011252  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180011259  cmp     [rcx+8], r14b
0x18001125d  jz      short loc_180011280
0x18001125f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180011264  cmp     [rax+7CCh], esi
0x18001126a  jz      short loc_180011280
0x18001126c  mov     r9d, esi; int
0x18001126f  mov     r8d, 78Ch; int
0x180011275  mov     rdx, r15; char *
0x180011278  mov     rcx, rax; this
0x18001127b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180011280  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011285  cmp     al, 1
0x180011287  jb      loc_18001135A
0x18001128d  mov     edx, 0D5h
0x180011292  jmp     loc_18001133C
0x180011297  mov     rcx, [rbp+ppStream]
0x18001129b  mov     rdx, r14
0x18001129e  xor     r9d, r9d
0x1800112a1  xor     r8d, r8d
0x1800112a4  mov     rax, [rcx]
0x1800112a7  mov     rax, [rax+28h]
0x1800112ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112b0  mov     esi, eax
0x1800112b2  test    eax, eax
0x1800112b4  jns     loc_1800113A6
0x1800112ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800112c1  test    rcx, rcx
0x1800112c4  jnz     short loc_180011307
0x1800112c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800112cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800112d3  mov     rcx, rax
0x1800112d6  test    rax, rax
0x1800112d9  jz      short loc_1800112F9
0x1800112db  mov     rax, [rax]
0x1800112de  mov     edx, 7F0h
0x1800112e3  mov     rax, [rax+8]
0x1800112e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ec  test    eax, eax
0x1800112ee  jz      short loc_1800112F9
0x1800112f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800112f7  jmp     short loc_180011307
0x1800112f9  lea     rcx, qword_180069A90; this
0x180011300  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180011307  cmp     [rcx+8], r14b
0x18001130b  jz      short loc_18001132E
0x18001130d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180011312  cmp     [rax+7CCh], esi
0x180011318  jz      short loc_18001132E
0x18001131a  mov     r9d, esi; int
0x18001131d  mov     r8d, 791h; int
0x180011323  mov     rdx, r15; char *
0x180011326  mov     rcx, rax; this
0x180011329  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001132e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011333  cmp     al, 1
0x180011335  jb      short loc_18001135A
0x180011337  mov     edx, 0D6h
0x18001133c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011343  lea     r8, WPP_e568207c201a3850f272ae9c45155cdf_Traceguids
0x18001134a  mov     r9, rbx
0x18001134d  mov     [rsp+58h+var_38], esi
0x180011351  mov     rcx, [rcx+10h]
0x180011355  call    WPP_SF_qd
0x18001135a  lea     rcx, [rbp+arg_0]; this
0x18001135e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180011363  mov     rcx, rdi; lpCriticalSection
0x180011366  call    cs:__imp_LeaveCriticalSection
0x18001136c  lea     rcx, [rbp+ppStream]
0x180011370  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180011375  lea     rcx, [rbp+var_20]
0x180011379  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18001137e  lea     rcx, [rbp+ppvObject]
0x180011382  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180011387  lea     rcx, [rbp+punkObject]
0x18001138b  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180011390  lea     rcx, [rbp+arg_10]
0x180011394  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180011399  add     rsp, 58h
0x18001139d  pop     r15
0x18001139f  pop     r14
0x1800113a1  pop     rdi
0x1800113a2  pop     rsi
0x1800113a3  pop     rbx
0x1800113a4  pop     rbp
0x1800113a5  retn
0x1800113a6  lea     rcx, [rbp+arg_0]; this
0x1800113aa  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800113af  mov     rcx, rdi; lpCriticalSection
0x1800113b2  call    cs:__imp_LeaveCriticalSection
0x1800113b8  cmp     [rbp+arg_10], r14
0x1800113bc  jz      loc_180011565
0x1800113c2  cmp     [rbp+ppStream], r14
0x1800113c6  jz      loc_180011565
0x1800113cc  mov     r8d, 79Bh; int
0x1800113d2  lea     rcx, [rbp+arg_0]; this
0x1800113d6  mov     rdx, r15; char *
0x1800113d9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800113de  mov     rcx, [rbp+arg_10]
0x1800113e2  xor     r8d, r8d
0x1800113e5  mov     rdx, [rbp+ppStream]
0x1800113e9  mov     rax, [rcx]
0x1800113ec  mov     rax, [rax+18h]
0x1800113f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113f5  mov     esi, eax
0x1800113f7  test    eax, eax
0x1800113f9  jns     loc_18001148A
0x1800113ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011406  test    rcx, rcx
0x180011409  jnz     short loc_18001144C
0x18001140b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011411  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180011418  mov     rcx, rax
0x18001141b  test    rax, rax
0x18001141e  jz      short loc_18001143E
0x180011420  mov     rax, [rax]
0x180011423  mov     edx, 7F0h
0x180011428  mov     rax, [rax+8]
0x18001142c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011431  test    eax, eax
0x180011433  jz      short loc_18001143E
0x180011435  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001143c  jmp     short loc_18001144C
0x18001143e  lea     rcx, qword_180069A90; this
0x180011445  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001144c  cmp     [rcx+8], r14b
0x180011450  jz      short loc_180011473
0x180011452  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180011457  cmp     [rax+7CCh], esi
0x18001145d  jz      short loc_180011473
0x18001145f  mov     r9d, esi; int
0x180011462  mov     r8d, 79Bh; int
0x180011468  mov     rdx, r15; char *
0x18001146b  mov     rcx, rax; this
0x18001146e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180011473  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011478  cmp     al, 1
0x18001147a  jb      loc_18001154E
0x180011480  mov     edx, 0D7h
0x180011485  jmp     loc_180011530
0x18001148a  mov     rcx, [rbp+arg_10]
  ... truncated ...
```
