# CMFAudioBranchLoader::TrySetResamplerFolddownMatrix(IMFTransform *,IMFMediaType *,uint,uint)

- ea: `0x180227364`
- end: `0x1802278a3`
- name: `?TrySetResamplerFolddownMatrix@CMFAudioBranchLoader@@AEAAJPEAUIMFTransform@@PEAUIMFMediaType@@II@Z`
- size: `1343`
- prototype: `__int64 __fastcall(CMFAudioBranchLoader *__hidden this, struct IMFTransform *, struct IMFMediaType *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800934bc`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x18005a3d4`
- `0x180063f00`
- `0x1800ec0e0`
- `0x180227364`
- `0x180344d40`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180227423`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180227423`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180227864`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180227864`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18022752a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18022752a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1802275fe`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1802275fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180227879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180227879`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180227468`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18022754c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180227620`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802276d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18022778f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180227468`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18022754c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180227620`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802276d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18022778f`

## pseudocode

```c
__int64 __fastcall CMFAudioBranchLoader::TrySetResamplerFolddownMatrix(
        CMFAudioBranchLoader *this,
        struct IMFTransform *a2,
        struct IMFMediaType *a3,
        int a4,
        unsigned int a5)
{
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  _DWORD *v8; // rsi
  unsigned int v9; // r12d
  ULONG *v10; // rdi
  HRESULT v11; // ebx
  ULONG v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 i; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  int v41; // [rsp+30h] [rbp-50h] BYREF
  __int64 v42; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  void *ppvData; // [rsp+48h] [rbp-38h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-30h] BYREF
  int v46; // [rsp+58h] [rbp-28h]
  int v47; // [rsp+5Ch] [rbp-24h]
  SAFEARRAY *psa[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v49; // [rsp+70h] [rbp-10h]
  char v51; // [rsp+D0h] [rbp+50h] BYREF

  v49 = 0;
  pv = 0;
  v41 = 0;
  lpVtbl = a3->lpVtbl;
  *(_OWORD *)psa = 0;
  if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, LPVOID *, int *))lpVtbl->GetAllocatedBlob)(
         a3,
         &MF_MT_AUDIO_FOLDDOWN_MATRIX,
         &pv,
         &v41) >= 0 )
  {
    v8 = pv;
    v9 = a5;
    v42 = 0;
    ppvData = 0;
    v10 = (ULONG *)((char *)pv + 8);
    if ( *((_DWORD *)pv + 1) != a4 && *v10 != a5 )
    {
      v11 = 0;
LABEL_5:
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v42);
      goto LABEL_69;
    }
    rgsabound.lLbound = 1;
    v12 = *v10;
    v47 = 1;
    rgsabound.cElements = v12;
    v46 = *((_DWORD *)pv + 1);
    psa[1] = SafeArrayCreate(3u, 2u, &rgsabound);
    if ( !psa[1] )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v51,
        "CMFAudioBranchLoader::TrySetResamplerFolddownMatrix",
        198);
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFAudioBranchLoader::TrySetResamplerFolddownMatrix",
            198,
            -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_18;
      v18 = 30;
LABEL_17:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids, this, v11);
LABEL_18:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v51);
      goto LABEL_5;
    }
    LOWORD(psa[0]) = 8195;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v51,
      "CMFAudioBranchLoader::TrySetResamplerFolddownMatrix",
      203);
    v11 = SafeArrayAccessData(psa[1], &ppvData);
    if ( v11 < 0 )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != v11 )
          CallStackContext::TraceFailure(v23, "CMFAudioBranchLoader::TrySetResamplerFolddownMatrix", 203, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_18;
      v18 = 31;
      goto LABEL_17;
    }
    for ( i = 0; (unsigned int)i < v8[1] * *v10; i = (unsigned int)(i + 1) )
      *((_DWORD *)ppvData + i) = v8[i + 4];
    v11 = SafeArrayUnaccessData(psa[1]);
    if ( v11 < 0 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != v11 )
          CallStackContext::TraceFailure(v29, "CMFAudioBranchLoader::TrySetResamplerFolddownMatrix", 210, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_18;
      v18 = 32;
      goto LABEL_17;
    }
    v11 = ((__int64 (__fastcall *)(struct IMFTransform *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IPropertyStore,
            &v42);
    if ( v11 < 0 )
    {
      v32 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31);
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( *((_DWORD *)v34 + 499) != v11 )
          CallStackContext::TraceFailure(v34, "CMFAudioBranchLoader::TrySetResamplerFolddownMatrix", 212, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_18;
      v18 = 33;
      goto LABEL_17;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, void *, SAFEARRAY **))(*(_QWORD *)v42 + 48LL))(v42, &unk_1803828A8, psa);
    if ( v11 < 0 )
    {
      v37 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36);
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v37 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v39 + 499) != v11 )
          CallStackContext::TraceFailure(v39, "CMFAudioBranchLoader::TrySetResamplerFolddownMatrix", 213, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_18;
      v18 = 34;
      goto LABEL_17;
    }
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        35,
        &WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids,
        this,
        a4,
        v9);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v51);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v42);
  }
  v11 = 0;
LABEL_69:
  if ( psa[1] )
    SafeArrayDestroy(psa[1]);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180227364  mov     [rsp-38h+arg_0], rbx
0x180227369  mov     [rsp-38h+arg_8], rdx
0x18022736e  push    rbp
0x18022736f  push    rsi
0x180227370  push    rdi
0x180227371  push    r12
0x180227373  push    r13
0x180227375  push    r14
0x180227377  push    r15
0x180227379  mov     rbp, rsp
0x18022737c  sub     rsp, 80h
0x180227383  xor     eax, eax
0x180227385  lea     rdx, MF_MT_AUDIO_FOLDDOWN_MATRIX
0x18022738c  mov     [rbp+var_10], rax
0x180227390  mov     r10, r8
0x180227393  mov     [rbp+pv], rax
0x180227397  mov     r13d, r9d
0x18022739a  mov     [rbp+var_50], eax
0x18022739d  lea     r9, [rbp+var_50]
0x1802273a1  mov     rax, [r8]
0x1802273a4  mov     r15, rcx
0x1802273a7  xorps   xmm0, xmm0
0x1802273aa  lea     r8, [rbp+pv]
0x1802273ae  mov     rcx, r10
0x1802273b1  movups  xmmword ptr [rbp+psa], xmm0
0x1802273b5  mov     rax, [rax+80h]
0x1802273bc  call    cs:__guard_dispatch_icall_fptr
0x1802273c2  test    eax, eax
0x1802273c4  js      loc_180227859
0x1802273ca  mov     rsi, [rbp+pv]
0x1802273ce  mov     r12d, [rbp+arg_20]
0x1802273d2  mov     [rbp+var_48], 0
0x1802273da  mov     [rbp+ppvData], 0
0x1802273e2  lea     rdi, [rsi+8]
0x1802273e6  cmp     [rsi+4], r13d
0x1802273ea  jz      short loc_180227401
0x1802273ec  cmp     [rdi], r12d
0x1802273ef  jz      short loc_180227401
0x1802273f1  xor     ebx, ebx
0x1802273f3  lea     rcx, [rbp+var_48]
0x1802273f7  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1802273fc  jmp     loc_18022785B
0x180227401  mov     ecx, 1
0x180227406  lea     r8, [rbp+rgsabound]; rgsabound
0x18022740a  mov     [rbp+rgsabound.lLbound], ecx
0x18022740d  mov     eax, [rdi]
0x18022740f  mov     [rbp+var_24], ecx
0x180227412  mov     ecx, 3; vt
0x180227417  mov     [rbp+rgsabound.cElements], eax
0x18022741a  mov     eax, [rsi+4]
0x18022741d  mov     [rbp+var_28], eax
0x180227420  lea     edx, [rcx-1]; cDims
0x180227423  call    cs:__imp_SafeArrayCreate
0x18022742a  nop     dword ptr [rax+rax+00h]
0x18022742f  mov     [rbp+psa+8], rax
0x180227433  lea     r14, aCmfaudiobranch_3; "CMFAudioBranchLoader::TrySetResamplerFo"...
0x18022743a  lea     rcx, [rbp+arg_10]; this
0x18022743e  mov     rdx, r14; char *
0x180227441  test    rax, rax
0x180227444  jnz     loc_18022750E
0x18022744a  mov     edi, 0C6h
0x18022744f  mov     r8d, edi; int
0x180227452  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180227457  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18022745e  mov     ebx, 8007000Eh
0x180227463  test    rcx, rcx
0x180227466  jnz     short loc_1802274B0
0x180227468  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18022746f  nop     dword ptr [rax+rax+00h]
0x180227474  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18022747b  mov     rcx, rax
0x18022747e  test    rax, rax
0x180227481  jz      short loc_1802274A2
0x180227483  mov     rax, [rax]
0x180227486  mov     edx, 7F0h
0x18022748b  mov     rax, [rax+8]
0x18022748f  call    cs:__guard_dispatch_icall_fptr
0x180227495  test    eax, eax
0x180227497  jz      short loc_1802274A2
0x180227499  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802274a0  jmp     short loc_1802274B0
0x1802274a2  lea     rcx, qword_1803CE250; this
0x1802274a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802274b0  cmp     byte ptr [rcx+8], 0
0x1802274b4  jz      short loc_1802274D4
0x1802274b6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802274bb  cmp     [rax+7CCh], ebx
0x1802274c1  jz      short loc_1802274D4
0x1802274c3  mov     r9d, ebx; int
0x1802274c6  mov     r8d, edi; int
0x1802274c9  mov     rdx, r14; char *
0x1802274cc  mov     rcx, rax; this
0x1802274cf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802274d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802274db  jb      short loc_180227500
0x1802274dd  mov     edx, 1Eh
0x1802274e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1802274e9  lea     r8, WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids
0x1802274f0  mov     r9, r15
0x1802274f3  mov     [rsp+80h+var_60], ebx
0x1802274f7  mov     rcx, [rcx+10h]
0x1802274fb  call    WPP_SF_qD
0x180227500  lea     rcx, [rbp+arg_10]; this
0x180227504  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180227509  jmp     loc_1802273F3
0x18022750e  mov     eax, 2003h
0x180227513  mov     r8d, 0CBh; int
0x180227519  mov     word ptr [rbp+psa], ax
0x18022751d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180227522  mov     rcx, [rbp+psa+8]; psa
0x180227526  lea     rdx, [rbp+ppvData]; ppvData
0x18022752a  call    cs:__imp_SafeArrayAccessData
0x180227531  nop     dword ptr [rax+rax+00h]
0x180227536  mov     ebx, eax
0x180227538  test    eax, eax
0x18022753a  jns     loc_1802275D2
0x180227540  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180227547  test    rcx, rcx
0x18022754a  jnz     short loc_180227594
0x18022754c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180227553  nop     dword ptr [rax+rax+00h]
0x180227558  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18022755f  mov     rcx, rax
0x180227562  test    rax, rax
0x180227565  jz      short loc_180227586
0x180227567  mov     rax, [rax]
0x18022756a  mov     edx, 7F0h
0x18022756f  mov     rax, [rax+8]
0x180227573  call    cs:__guard_dispatch_icall_fptr
0x180227579  test    eax, eax
0x18022757b  jz      short loc_180227586
0x18022757d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180227584  jmp     short loc_180227594
0x180227586  lea     rcx, qword_1803CE250; this
0x18022758d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180227594  cmp     byte ptr [rcx+8], 0
0x180227598  jz      short loc_1802275BB
0x18022759a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18022759f  cmp     [rax+7CCh], ebx
0x1802275a5  jz      short loc_1802275BB
0x1802275a7  mov     r9d, ebx; int
0x1802275aa  mov     r8d, 0CBh; int
0x1802275b0  mov     rdx, r14; char *
0x1802275b3  mov     rcx, rax; this
0x1802275b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802275bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802275c2  jb      loc_180227500
0x1802275c8  mov     edx, 1Fh
0x1802275cd  jmp     loc_1802274E2
0x1802275d2  mov     eax, [rsi+4]
0x1802275d5  xor     r8d, r8d
0x1802275d8  imul    eax, [rdi]
0x1802275db  test    eax, eax
0x1802275dd  jz      short loc_1802275FA
0x1802275df  mov     rax, [rbp+ppvData]
0x1802275e3  mov     ecx, [rsi+r8*4+10h]
0x1802275e8  mov     [rax+r8*4], ecx
0x1802275ec  inc     r8d
0x1802275ef  mov     eax, [rdi]
0x1802275f1  imul    eax, [rsi+4]
0x1802275f5  cmp     r8d, eax
0x1802275f8  jb      short loc_1802275DF
0x1802275fa  mov     rcx, [rbp+psa+8]; psa
0x1802275fe  call    cs:__imp_SafeArrayUnaccessData
0x180227605  nop     dword ptr [rax+rax+00h]
0x18022760a  mov     ebx, eax
0x18022760c  test    eax, eax
0x18022760e  jns     loc_1802276A6
0x180227614  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18022761b  test    rcx, rcx
0x18022761e  jnz     short loc_180227668
0x180227620  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180227627  nop     dword ptr [rax+rax+00h]
0x18022762c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180227633  mov     rcx, rax
0x180227636  test    rax, rax
0x180227639  jz      short loc_18022765A
0x18022763b  mov     rax, [rax]
0x18022763e  mov     edx, 7F0h
0x180227643  mov     rax, [rax+8]
0x180227647  call    cs:__guard_dispatch_icall_fptr
0x18022764d  test    eax, eax
0x18022764f  jz      short loc_18022765A
0x180227651  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180227658  jmp     short loc_180227668
0x18022765a  lea     rcx, qword_1803CE250; this
0x180227661  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180227668  cmp     byte ptr [rcx+8], 0
0x18022766c  jz      short loc_18022768F
0x18022766e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180227673  cmp     [rax+7CCh], ebx
0x180227679  jz      short loc_18022768F
0x18022767b  mov     r9d, ebx; int
0x18022767e  mov     r8d, 0D2h; int
0x180227684  mov     rdx, r14; char *
0x180227687  mov     rcx, rax; this
0x18022768a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18022768f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180227696  jb      loc_180227500
0x18022769c  mov     edx, 20h ; ' '
0x1802276a1  jmp     loc_1802274E2
0x1802276a6  mov     rcx, [rbp+arg_8]
0x1802276aa  lea     r8, [rbp+var_48]
0x1802276ae  lea     rdx, IID_IPropertyStore
0x1802276b5  mov     rax, [rcx]
0x1802276b8  mov     rax, [rax]
0x1802276bb  call    cs:__guard_dispatch_icall_fptr
0x1802276c1  mov     ebx, eax
0x1802276c3  test    eax, eax
0x1802276c5  jns     loc_18022775D
0x1802276cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802276d2  test    rcx, rcx
0x1802276d5  jnz     short loc_18022771F
0x1802276d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802276de  nop     dword ptr [rax+rax+00h]
0x1802276e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802276ea  mov     rcx, rax
0x1802276ed  test    rax, rax
0x1802276f0  jz      short loc_180227711
0x1802276f2  mov     rax, [rax]
0x1802276f5  mov     edx, 7F0h
0x1802276fa  mov     rax, [rax+8]
0x1802276fe  call    cs:__guard_dispatch_icall_fptr
0x180227704  test    eax, eax
0x180227706  jz      short loc_180227711
0x180227708  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18022770f  jmp     short loc_18022771F
0x180227711  lea     rcx, qword_1803CE250; this
0x180227718  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18022771f  cmp     byte ptr [rcx+8], 0
0x180227723  jz      short loc_180227746
0x180227725  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18022772a  cmp     [rax+7CCh], ebx
0x180227730  jz      short loc_180227746
0x180227732  mov     r9d, ebx; int
0x180227735  mov     r8d, 0D4h; int
0x18022773b  mov     rdx, r14; char *
0x18022773e  mov     rcx, rax; this
0x180227741  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180227746  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18022774d  jb      loc_180227500
0x180227753  mov     edx, 21h ; '!'
0x180227758  jmp     loc_1802274E2
0x18022775d  mov     rcx, [rbp+var_48]
0x180227761  lea     r8, [rbp+psa]
0x180227765  lea     rdx, unk_1803828A8
0x18022776c  mov     rax, [rcx]
0x18022776f  mov     rax, [rax+30h]
0x180227773  call    cs:__guard_dispatch_icall_fptr
0x180227779  mov     ebx, eax
0x18022777b  test    eax, eax
0x18022777d  jns     loc_180227815
0x180227783  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18022778a  test    rcx, rcx
0x18022778d  jnz     short loc_1802277D7
0x18022778f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180227796  nop     dword ptr [rax+rax+00h]
0x18022779b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802277a2  mov     rcx, rax
0x1802277a5  test    rax, rax
0x1802277a8  jz      short loc_1802277C9
0x1802277aa  mov     rax, [rax]
0x1802277ad  mov     edx, 7F0h
0x1802277b2  mov     rax, [rax+8]
0x1802277b6  call    cs:__guard_dispatch_icall_fptr
0x1802277bc  test    eax, eax
0x1802277be  jz      short loc_1802277C9
0x1802277c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802277c7  jmp     short loc_1802277D7
0x1802277c9  lea     rcx, qword_1803CE250; this
0x1802277d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802277d7  cmp     byte ptr [rcx+8], 0
0x1802277db  jz      short loc_1802277FE
0x1802277dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802277e2  cmp     [rax+7CCh], ebx
0x1802277e8  jz      short loc_1802277FE
0x1802277ea  mov     r9d, ebx; int
0x1802277ed  mov     r8d, 0D5h; int
0x1802277f3  mov     rdx, r14; char *
0x1802277f6  mov     rcx, rax; this
0x1802277f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802277fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180227805  jb      loc_180227500
0x18022780b  mov     edx, 22h ; '"'
0x180227810  jmp     loc_1802274E2
0x180227815  cmp     cs:byte_1803CECE9, 10h
0x18022781c  jb      short loc_180227847
0x18022781e  mov     rcx, cs:WPP_GLOBAL_Control
0x180227825  lea     r8, WPP_59fbcb2ab26a39c107bb4b691a80283e_Traceguids
0x18022782c  mov     edx, 23h ; '#'
0x180227831  mov     [rsp+80h+var_58], r12d
0x180227836  mov     r9, r15
0x180227839  mov     [rsp+80h+var_60], r13d
0x18022783e  mov     rcx, [rcx+38h]
0x180227842  call    WPP_SF_qDD
0x180227847  lea     rcx, [rbp+arg_10]; this
0x18022784b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180227850  lea     rcx, [rbp+var_48]
0x180227854  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180227859  xor     ebx, ebx
  ... truncated ...
```
