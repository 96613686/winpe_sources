# CASFTranscodeDestination::ConfigContentInfo(IMFASFContentInfo *)

- ea: `0x1800446a8`
- end: `0x180044a48`
- name: `?ConfigContentInfo@CASFTranscodeDestination@@IEAAJPEAUIMFASFContentInfo@@@Z`
- size: `928`
- prototype: `__int64 __fastcall(CASFTranscodeDestination *__hidden this, struct IMFASFContentInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180044340`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180010110`
- `0x18001a330`
- `0x18001c280`
- `0x1800446a8`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044734`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800447db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004488f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004494f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044734`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800447db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004488f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004494f`
- `MFPlat!DestroyPropVariant` at `0x180044a18`
- `MFPlat!DestroyPropVariant` at `0x180044a18`

## string_xrefs

- `0x1800446be`: `CASFTranscodeDestination::ConfigContentInfo`

## pseudocode

```c
__int64 __fastcall CASFTranscodeDestination::ConfigContentInfo(
        CASFTranscodeDestination *this,
        struct IMFASFContentInfo *a2)
{
  struct IMFTranscodeProfile *v4; // rdx
  int v5; // eax
  __int64 v6; // rdx
  void *v7; // r14
  int v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int128 v26; // [rsp+30h] [rbp-20h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h]
  void *v28; // [rsp+80h] [rbp+30h] BYREF
  __int64 v29; // [rsp+90h] [rbp+40h] BYREF
  void **v30; // [rsp+98h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v28,
    "CASFTranscodeDestination::ConfigContentInfo",
    367);
  v4 = (struct IMFTranscodeProfile *)*((_QWORD *)this + 1);
  v30 = &CASFTranscodeProfileConverter::`vftable';
  v28 = 0;
  v27 = 0;
  v29 = 0;
  v26 = 0;
  v5 = CASFTranscodeProfileConverter::ConvertProfile(
         (CASFTranscodeProfileConverter *)&v30,
         v4,
         &IID_IMFASFProfile,
         (IMFASFProfile **)&v28);
  v7 = v28;
  v8 = v5;
  if ( v5 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(struct IMFASFContentInfo *, void *))a2->lpVtbl->SetProfile)(a2, v28);
    if ( v8 >= 0 )
    {
      if ( !*((_DWORD *)this + 12) )
        goto LABEL_47;
      v8 = ((__int64 (__fastcall *)(struct IMFASFContentInfo *, _QWORD, __int64 *))a2->lpVtbl->GetEncodingConfigurationPropertyStore)(
             a2,
             0,
             &v29);
      if ( v8 >= 0 )
      {
        DWORD2(v26) = 2;
        LOWORD(v26) = 19;
        v8 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v29 + 48LL))(
               v29,
               &MFPKEY_ASFMEDIASINK_DRMACTION,
               &v26);
        if ( v8 < 0 )
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CASFTranscodeDestination::ConfigContentInfo",
                386,
                v8);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v12 = 40;
            goto LABEL_46;
          }
        }
      }
      else
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
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
          if ( *((_DWORD *)v20 + 499) != v8 )
            CallStackContext::TraceFailure(v20, "CASFTranscodeDestination::ConfigContentInfo", 382, v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v12 = 39;
          goto LABEL_46;
        }
      }
    }
    else
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
        if ( *((_DWORD *)v16 + 499) != v8 )
          CallStackContext::TraceFailure(v16, "CASFTranscodeDestination::ConfigContentInfo", 378, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 38;
        goto LABEL_46;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(v11, "CASFTranscodeDestination::ConfigContentInfo", 377, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 37;
LABEL_46:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_0a758c1def7e3974366218a1d0d46647_Traceguids, this, v8);
    }
  }
LABEL_47:
  if ( v7 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  DestroyPropVariant(&v26);
  v30 = &CTranscodeProfileConverter::`vftable';
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800446a8  mov     [rsp-28h+arg_8], rbx
0x1800446ad  push    rbp
0x1800446ae  push    rsi
0x1800446af  push    rdi
0x1800446b0  push    r12
0x1800446b2  push    r14
0x1800446b4  mov     rbp, rsp
0x1800446b7  sub     rsp, 50h
0x1800446bb  mov     rdi, rdx
0x1800446be  lea     r12, aCasftranscoded_3; "CASFTranscodeDestination::ConfigContent"...
0x1800446c5  mov     rsi, rcx
0x1800446c8  mov     rdx, r12; char *
0x1800446cb  mov     r8d, 16Fh; int
0x1800446d1  lea     rcx, [rbp+arg_0]; this
0x1800446d5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800446da  mov     rdx, [rsi+8]; struct IMFTranscodeProfile *
0x1800446de  lea     rax, ??_7CASFTranscodeProfileConverter@@6B@; const CASFTranscodeProfileConverter::`vftable'
0x1800446e5  mov     [rbp+arg_18], rax
0x1800446e9  lea     r9, [rbp+arg_0]; void **
0x1800446ed  xor     eax, eax
0x1800446ef  mov     [rbp+arg_0], 0
0x1800446f7  xorps   xmm0, xmm0
0x1800446fa  mov     [rbp+var_10], rax
0x1800446fe  lea     r8, IID_IMFASFProfile; struct _GUID *
0x180044705  mov     [rbp+arg_10], 0
0x18004470d  lea     rcx, [rbp+arg_18]; this
0x180044711  movups  [rbp+var_20], xmm0
0x180044715  call    ?ConvertProfile@CASFTranscodeProfileConverter@@UEAAJPEAUIMFTranscodeProfile@@AEBU_GUID@@PEAPEAX@Z; CASFTranscodeProfileConverter::ConvertProfile(IMFTranscodeProfile *,_GUID const &,void * *)
0x18004471a  mov     r14, [rbp+arg_0]
0x18004471e  mov     ebx, eax
0x180044720  test    eax, eax
0x180044722  jns     loc_1800447B3
0x180044728  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004472f  test    rcx, rcx
0x180044732  jnz     short loc_180044775
0x180044734  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004473a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044741  mov     rcx, rax
0x180044744  test    rax, rax
0x180044747  jz      short loc_180044767
0x180044749  mov     rax, [rax]
0x18004474c  mov     edx, 7F0h
0x180044751  mov     rax, [rax+8]
0x180044755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004475a  test    eax, eax
0x18004475c  jz      short loc_180044767
0x18004475e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044765  jmp     short loc_180044775
0x180044767  lea     rcx, qword_180069A90; this
0x18004476e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044775  cmp     byte ptr [rcx+8], 0
0x180044779  jz      short loc_18004479C
0x18004477b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044780  cmp     [rax+7CCh], ebx
0x180044786  jz      short loc_18004479C
0x180044788  mov     r9d, ebx; int
0x18004478b  mov     r8d, 179h; int
0x180044791  mov     rdx, r12; char *
0x180044794  mov     rcx, rax; this
0x180044797  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004479c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800447a1  cmp     al, 1
0x1800447a3  jb      loc_1800449E3
0x1800447a9  mov     edx, 25h ; '%'
0x1800447ae  jmp     loc_1800449C5
0x1800447b3  mov     rax, [rdi]
0x1800447b6  mov     rdx, r14
0x1800447b9  mov     rcx, rdi
0x1800447bc  mov     rax, [rax+38h]
0x1800447c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447c5  mov     ebx, eax
0x1800447c7  test    eax, eax
0x1800447c9  jns     loc_18004485A
0x1800447cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800447d6  test    rcx, rcx
0x1800447d9  jnz     short loc_18004481C
0x1800447db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800447e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800447e8  mov     rcx, rax
0x1800447eb  test    rax, rax
0x1800447ee  jz      short loc_18004480E
0x1800447f0  mov     rax, [rax]
0x1800447f3  mov     edx, 7F0h
0x1800447f8  mov     rax, [rax+8]
0x1800447fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044801  test    eax, eax
0x180044803  jz      short loc_18004480E
0x180044805  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004480c  jmp     short loc_18004481C
0x18004480e  lea     rcx, qword_180069A90; this
0x180044815  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004481c  cmp     byte ptr [rcx+8], 0
0x180044820  jz      short loc_180044843
0x180044822  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044827  cmp     [rax+7CCh], ebx
0x18004482d  jz      short loc_180044843
0x18004482f  mov     r9d, ebx; int
0x180044832  mov     r8d, 17Ah; int
0x180044838  mov     rdx, r12; char *
0x18004483b  mov     rcx, rax; this
0x18004483e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044843  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180044848  cmp     al, 1
0x18004484a  jb      loc_1800449E3
0x180044850  mov     edx, 26h ; '&'
0x180044855  jmp     loc_1800449C5
0x18004485a  cmp     dword ptr [rsi+30h], 0
0x18004485e  jz      loc_1800449E3
0x180044864  mov     rax, [rdi]
0x180044867  lea     r8, [rbp+arg_10]
0x18004486b  xor     edx, edx
0x18004486d  mov     rcx, rdi
0x180044870  mov     rax, [rax+48h]
0x180044874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044879  mov     ebx, eax
0x18004487b  test    eax, eax
0x18004487d  jns     loc_18004490E
0x180044883  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004488a  test    rcx, rcx
0x18004488d  jnz     short loc_1800448D0
0x18004488f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044895  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004489c  mov     rcx, rax
0x18004489f  test    rax, rax
0x1800448a2  jz      short loc_1800448C2
0x1800448a4  mov     rax, [rax]
0x1800448a7  mov     edx, 7F0h
0x1800448ac  mov     rax, [rax+8]
0x1800448b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448b5  test    eax, eax
0x1800448b7  jz      short loc_1800448C2
0x1800448b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800448c0  jmp     short loc_1800448D0
0x1800448c2  lea     rcx, qword_180069A90; this
0x1800448c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800448d0  cmp     byte ptr [rcx+8], 0
0x1800448d4  jz      short loc_1800448F7
0x1800448d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800448db  cmp     [rax+7CCh], ebx
0x1800448e1  jz      short loc_1800448F7
0x1800448e3  mov     r9d, ebx; int
0x1800448e6  mov     r8d, 17Eh; int
0x1800448ec  mov     rdx, r12; char *
0x1800448ef  mov     rcx, rax; this
0x1800448f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800448f7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800448fc  cmp     al, 1
0x1800448fe  jb      loc_1800449E3
0x180044904  mov     edx, 27h ; '''
0x180044909  jmp     loc_1800449C5
0x18004490e  mov     rcx, [rbp+arg_10]
0x180044912  lea     r8, [rbp+var_20]
0x180044916  mov     eax, 13h
0x18004491b  mov     dword ptr [rbp+var_20+8], 2
0x180044922  mov     word ptr [rbp+var_20], ax
0x180044926  lea     rdx, MFPKEY_ASFMEDIASINK_DRMACTION
0x18004492d  mov     rax, [rcx]
0x180044930  mov     rax, [rax+30h]
0x180044934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044939  mov     ebx, eax
0x18004493b  test    eax, eax
0x18004493d  jns     loc_1800449E3
0x180044943  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004494a  test    rcx, rcx
0x18004494d  jnz     short loc_180044990
0x18004494f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044955  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004495c  mov     rcx, rax
0x18004495f  test    rax, rax
0x180044962  jz      short loc_180044982
0x180044964  mov     rax, [rax]
0x180044967  mov     edx, 7F0h
0x18004496c  mov     rax, [rax+8]
0x180044970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044975  test    eax, eax
0x180044977  jz      short loc_180044982
0x180044979  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044980  jmp     short loc_180044990
0x180044982  lea     rcx, qword_180069A90; this
0x180044989  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044990  cmp     byte ptr [rcx+8], 0
0x180044994  jz      short loc_1800449B7
0x180044996  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004499b  cmp     [rax+7CCh], ebx
0x1800449a1  jz      short loc_1800449B7
0x1800449a3  mov     r9d, ebx; int
0x1800449a6  mov     r8d, 182h; int
0x1800449ac  mov     rdx, r12; char *
0x1800449af  mov     rcx, rax; this
0x1800449b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800449b7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800449bc  cmp     al, 1
0x1800449be  jb      short loc_1800449E3
0x1800449c0  mov     edx, 28h ; '('
0x1800449c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800449cc  lea     r8, WPP_0a758c1def7e3974366218a1d0d46647_Traceguids
0x1800449d3  mov     r9, rsi
0x1800449d6  mov     [rsp+50h+var_30], ebx
0x1800449da  mov     rcx, [rcx+10h]
0x1800449de  call    WPP_SF_qd
0x1800449e3  test    r14, r14
0x1800449e6  jz      short loc_1800449F7
0x1800449e8  mov     rax, [r14]
0x1800449eb  mov     rcx, r14
0x1800449ee  mov     rax, [rax+10h]
0x1800449f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800449f7  mov     rcx, [rbp+arg_10]
0x1800449fb  test    rcx, rcx
0x1800449fe  jz      short loc_180044A14
0x180044a00  mov     rax, [rcx]
0x180044a03  mov     rax, [rax+10h]
0x180044a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a0c  mov     [rbp+arg_10], 0
0x180044a14  lea     rcx, [rbp+var_20]
0x180044a18  call    cs:__imp_DestroyPropVariant
0x180044a1e  lea     rax, ??_7CTranscodeProfileConverter@@6B@; const CTranscodeProfileConverter::`vftable'
0x180044a25  mov     [rbp+arg_18], rax
0x180044a29  lea     rcx, [rbp+arg_0]; this
0x180044a2d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180044a32  mov     eax, ebx
0x180044a34  mov     rbx, [rsp+50h+arg_8]
0x180044a3c  add     rsp, 50h
0x180044a40  pop     r14
0x180044a42  pop     r12
0x180044a44  pop     rdi
0x180044a45  pop     rsi
0x180044a46  pop     rbp
0x180044a47  retn
```
