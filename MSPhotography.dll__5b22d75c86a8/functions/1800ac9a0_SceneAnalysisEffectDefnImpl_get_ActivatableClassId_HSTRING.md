# SceneAnalysisEffectDefnImpl::get_ActivatableClassId(HSTRING__ * *)

- ea: `0x1800ac9a0`
- end: `0x1800acb36`
- name: `?get_ActivatableClassId@SceneAnalysisEffectDefnImpl@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `406`
- prototype: `int(SceneAnalysisEffectDefnImpl *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x18000b490`
- `0x18000c0f8`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x1800ac9a0`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800aca6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800aca6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ac9dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aca87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ac9dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aca87`

## string_xrefs

- `0x1800ac9b0`: `SceneAnalysisEffectDefnImpl::get_ActivatableClassId`
- `0x1800aca38`: `SceneAnalysisEffectDefnImpl::get_ActivatableClassId`
- `0x1800acade`: `SceneAnalysisEffectDefnImpl::get_ActivatableClassId`

## pseudocode

```c
__int64 __fastcall SceneAnalysisEffectDefnImpl::get_ActivatableClassId(HSTRING *this, HSTRING *a2)
{
  __int64 *v4; // rcx
  CallStackTracing *v5; // rax
  HRESULT v6; // ebx
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v13; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v13,
    "SceneAnalysisEffectDefnImpl::get_ActivatableClassId",
    51);
  if ( a2 )
  {
    v6 = WindowsDuplicateString(this[8], a2);
    if ( v6 < 0 )
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_18015FF10;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "SceneAnalysisEffectDefnImpl::get_ActivatableClassId",
            56,
            v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 16;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v4 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v4 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    v6 = -2147467261;
    if ( *((_BYTE *)v4 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)v7 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v7, "SceneAnalysisEffectDefnImpl::get_ActivatableClassId", 54, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = 15;
LABEL_23:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_45341311ee633afec8922ce86d82bcb5_Traceguids, this, v6);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ac9a0  mov     [rsp+arg_8], rbx
0x1800ac9a5  push    rdi
0x1800ac9a6  sub     rsp, 30h
0x1800ac9aa  mov     rbx, rdx
0x1800ac9ad  mov     rdi, rcx
0x1800ac9b0  lea     rdx, aSceneanalysise_3; "SceneAnalysisEffectDefnImpl::get_Activa"...
0x1800ac9b7  mov     r8d, 33h ; '3'; int
0x1800ac9bd  lea     rcx, [rsp+38h+arg_0]; this
0x1800ac9c2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ac9c7  test    rbx, rbx
0x1800ac9ca  jnz     loc_1800ACA64
0x1800ac9d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac9d7  test    rcx, rcx
0x1800ac9da  jnz     short loc_1800ACA1D
0x1800ac9dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ac9e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ac9e9  mov     rcx, rax
0x1800ac9ec  test    rax, rax
0x1800ac9ef  jz      short loc_1800ACA0F
0x1800ac9f1  mov     rax, [rax]
0x1800ac9f4  mov     edx, 7F0h
0x1800ac9f9  mov     rax, [rax+8]
0x1800ac9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aca02  test    eax, eax
0x1800aca04  jz      short loc_1800ACA0F
0x1800aca06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aca0d  jmp     short loc_1800ACA1D
0x1800aca0f  lea     rcx, qword_18015FF10; this
0x1800aca16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aca1d  cmp     byte ptr [rcx+8], 0
0x1800aca21  mov     ebx, 80004003h
0x1800aca26  jz      short loc_1800ACA4D
0x1800aca28  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aca2d  cmp     [rax+7CCh], ebx
0x1800aca33  jz      short loc_1800ACA4D
0x1800aca35  mov     r9d, ebx; int
0x1800aca38  lea     rdx, aSceneanalysise_3; "SceneAnalysisEffectDefnImpl::get_Activa"...
0x1800aca3f  mov     r8d, 36h ; '6'; int
0x1800aca45  mov     rcx, rax; this
0x1800aca48  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aca4d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800aca52  cmp     al, 1
0x1800aca54  jb      loc_1800ACB1F
0x1800aca5a  mov     edx, 0Fh
0x1800aca5f  jmp     loc_1800ACB01
0x1800aca64  mov     rcx, [rdi+40h]; string
0x1800aca68  mov     rdx, rbx; newString
0x1800aca6b  call    cs:__imp_WindowsDuplicateString
0x1800aca71  mov     ebx, eax
0x1800aca73  test    eax, eax
0x1800aca75  jns     loc_1800ACB1F
0x1800aca7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aca82  test    rcx, rcx
0x1800aca85  jnz     short loc_1800ACAC8
0x1800aca87  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800aca8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aca94  mov     rcx, rax
0x1800aca97  test    rax, rax
0x1800aca9a  jz      short loc_1800ACABA
0x1800aca9c  mov     rax, [rax]
0x1800aca9f  mov     edx, 7F0h
0x1800acaa4  mov     rax, [rax+8]
0x1800acaa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acaad  test    eax, eax
0x1800acaaf  jz      short loc_1800ACABA
0x1800acab1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800acab8  jmp     short loc_1800ACAC8
0x1800acaba  lea     rcx, qword_18015FF10; this
0x1800acac1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800acac8  cmp     byte ptr [rcx+8], 0
0x1800acacc  jz      short loc_1800ACAF3
0x1800acace  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800acad3  cmp     [rax+7CCh], ebx
0x1800acad9  jz      short loc_1800ACAF3
0x1800acadb  mov     r9d, ebx; int
0x1800acade  lea     rdx, aSceneanalysise_3; "SceneAnalysisEffectDefnImpl::get_Activa"...
0x1800acae5  mov     r8d, 38h ; '8'; int
0x1800acaeb  mov     rcx, rax; this
0x1800acaee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800acaf3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800acaf8  cmp     al, 1
0x1800acafa  jb      short loc_1800ACB1F
0x1800acafc  mov     edx, 10h
0x1800acb01  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acb08  lea     r8, WPP_45341311ee633afec8922ce86d82bcb5_Traceguids
0x1800acb0f  mov     r9, rdi
0x1800acb12  mov     [rsp+38h+var_18], ebx
0x1800acb16  mov     rcx, [rcx+10h]
0x1800acb1a  call    WPP_SF_qD
0x1800acb1f  lea     rcx, [rsp+38h+arg_0]; this
0x1800acb24  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800acb29  mov     eax, ebx
0x1800acb2b  mov     rbx, [rsp+38h+arg_8]
0x1800acb30  add     rsp, 30h
0x1800acb34  pop     rdi
0x1800acb35  retn
```
