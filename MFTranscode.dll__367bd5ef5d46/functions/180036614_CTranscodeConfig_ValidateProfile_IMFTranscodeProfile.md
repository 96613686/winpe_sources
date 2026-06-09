# CTranscodeConfig::ValidateProfile(IMFTranscodeProfile *)

- ea: `0x180036614`
- end: `0x18003680c`
- name: `?ValidateProfile@CTranscodeConfig@@IEAAJPEAUIMFTranscodeProfile@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(CTranscodeConfig *__hidden this, struct IMFTranscodeProfile *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036440`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x180036614`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036685`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036743`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036685`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036743`

## string_xrefs

- `0x18003663c`: `CTranscodeConfig::ValidateProfile`
- `0x1800366dc`: `CTranscodeConfig::ValidateProfile`
- `0x18003679a`: `CTranscodeConfig::ValidateProfile`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::ValidateProfile(CTranscodeConfig *this, struct IMFTranscodeProfile *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v14[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+38h] [rbp-30h] BYREF
  __int128 v16; // [rsp+40h] [rbp-28h] BYREF

  v15 = 0;
  v16 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v14, "CTranscodeConfig::ValidateProfile", 509);
  v5 = ((__int64 (__fastcall *)(struct IMFTranscodeProfile *, __int64 *))a2->lpVtbl->GetContainerAttributes)(a2, &v15);
  if ( v5 >= 0 )
  {
    if ( !v15
      || (*(int (__fastcall **)(__int64, const IID *, __int128 *))(*(_QWORD *)v15 + 80LL))(
           v15,
           &MF_TRANSCODE_CONTAINERTYPE,
           &v16) < 0 )
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      v5 = -1072847856;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072847856 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeConfig::ValidateProfile", 514, -1072847856);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 65;
        goto LABEL_24;
      }
    }
  }
  else
  {
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
      if ( *((_DWORD *)v8 + 499) != v5 )
        CallStackContext::TraceFailure(v8, "CTranscodeConfig::ValidateProfile", 509, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 64;
LABEL_24:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v14);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180036614  mov     [rsp+arg_10], rbx
0x180036619  push    rdi
0x18003661a  sub     rsp, 60h
0x18003661e  mov     rax, cs:__security_cookie
0x180036625  xor     rax, rsp
0x180036628  mov     [rsp+68h+var_18], rax
0x18003662d  mov     rbx, rdx
0x180036630  mov     [rsp+68h+var_30], 0
0x180036639  mov     rdi, rcx
0x18003663c  lea     rdx, aCtranscodeconf_7; "CTranscodeConfig::ValidateProfile"
0x180036643  xorps   xmm0, xmm0
0x180036646  lea     rcx, [rsp+68h+var_38]; this
0x18003664b  mov     r8d, 1FDh; int
0x180036651  movups  [rsp+68h+var_28], xmm0
0x180036656  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003665b  mov     rax, [rbx]
0x18003665e  lea     rdx, [rsp+68h+var_30]
0x180036663  mov     rcx, rbx
0x180036666  mov     rax, [rax+40h]
0x18003666a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003666f  mov     ebx, eax
0x180036671  test    eax, eax
0x180036673  jns     loc_180036708
0x180036679  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036680  test    rcx, rcx
0x180036683  jnz     short loc_1800366C6
0x180036685  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003668b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036692  mov     rcx, rax
0x180036695  test    rax, rax
0x180036698  jz      short loc_1800366B8
0x18003669a  mov     rax, [rax]
0x18003669d  mov     edx, 7F0h
0x1800366a2  mov     rax, [rax+8]
0x1800366a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366ab  test    eax, eax
0x1800366ad  jz      short loc_1800366B8
0x1800366af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800366b6  jmp     short loc_1800366C6
0x1800366b8  lea     rcx, qword_180069A90; this
0x1800366bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800366c6  cmp     byte ptr [rcx+8], 0
0x1800366ca  jz      short loc_1800366F1
0x1800366cc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800366d1  cmp     [rax+7CCh], ebx
0x1800366d7  jz      short loc_1800366F1
0x1800366d9  mov     r9d, ebx; int
0x1800366dc  lea     rdx, aCtranscodeconf_7; "CTranscodeConfig::ValidateProfile"
0x1800366e3  mov     r8d, 1FDh; int
0x1800366e9  mov     rcx, rax; this
0x1800366ec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800366f1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800366f6  cmp     al, 1
0x1800366f8  jb      loc_1800367DB
0x1800366fe  mov     edx, 40h ; '@'
0x180036703  jmp     loc_1800367BD
0x180036708  mov     rcx, [rsp+68h+var_30]
0x18003670d  test    rcx, rcx
0x180036710  jz      short loc_180036732
0x180036712  mov     rax, [rcx]
0x180036715  lea     r8, [rsp+68h+var_28]
0x18003671a  lea     rdx, MF_TRANSCODE_CONTAINERTYPE
0x180036721  mov     rax, [rax+50h]
0x180036725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003672a  test    eax, eax
0x18003672c  jns     loc_1800367DB
0x180036732  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036739  mov     ebx, 0C00DA410h
0x18003673e  test    rcx, rcx
0x180036741  jnz     short loc_180036784
0x180036743  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036749  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036750  mov     rcx, rax
0x180036753  test    rax, rax
0x180036756  jz      short loc_180036776
0x180036758  mov     rax, [rax]
0x18003675b  mov     edx, 7F0h
0x180036760  mov     rax, [rax+8]
0x180036764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036769  test    eax, eax
0x18003676b  jz      short loc_180036776
0x18003676d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036774  jmp     short loc_180036784
0x180036776  lea     rcx, qword_180069A90; this
0x18003677d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036784  cmp     byte ptr [rcx+8], 0
0x180036788  jz      short loc_1800367AF
0x18003678a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003678f  cmp     [rax+7CCh], ebx
0x180036795  jz      short loc_1800367AF
0x180036797  mov     r9d, ebx; int
0x18003679a  lea     rdx, aCtranscodeconf_7; "CTranscodeConfig::ValidateProfile"
0x1800367a1  mov     r8d, 202h; int
0x1800367a7  mov     rcx, rax; this
0x1800367aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800367af  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800367b4  cmp     al, 1
0x1800367b6  jb      short loc_1800367DB
0x1800367b8  mov     edx, 41h ; 'A'
0x1800367bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367c4  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x1800367cb  mov     r9, rdi
0x1800367ce  mov     [rsp+68h+var_48], ebx
0x1800367d2  mov     rcx, [rcx+10h]
0x1800367d6  call    WPP_SF_qd
0x1800367db  lea     rcx, [rsp+68h+var_38]; this
0x1800367e0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800367e5  lea     rcx, [rsp+68h+var_30]
0x1800367ea  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800367ef  mov     eax, ebx
0x1800367f1  mov     rcx, [rsp+68h+var_18]
0x1800367f6  xor     rcx, rsp; StackCookie
0x1800367f9  call    __security_check_cookie
0x1800367fe  mov     rbx, [rsp+68h+arg_10]
0x180036806  add     rsp, 60h
0x18003680a  pop     rdi
0x18003680b  retn
```
