# CTranscodeConfig::SetProfile(IMFTranscodeProfile *)

- ea: `0x180036440`
- end: `0x18003660b`
- name: `?SetProfile@CTranscodeConfig@@UEAAJPEAUIMFTranscodeProfile@@@Z`
- size: `459`
- prototype: `__int64 __fastcall(CTranscodeConfig *__hidden this, struct IMFTranscodeProfile *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x180036440`
- `0x180036614`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036486`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036548`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036486`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036548`

## string_xrefs

- `0x180036455`: `CTranscodeConfig::SetProfile`
- `0x1800364dd`: `CTranscodeConfig::SetProfile`
- `0x18003659f`: `CTranscodeConfig::SetProfile`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::SetProfile(CTranscodeConfig *this, struct IMFTranscodeProfile *a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rcx
  char v16; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v16, "CTranscodeConfig::SetProfile", 473);
  if ( a2 )
  {
    v6 = CTranscodeConfig::ValidateProfile(this, a2);
    if ( v6 >= 0 )
    {
      v14 = *((_QWORD *)this + 2);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      *((_QWORD *)this + 2) = a2;
      ((void (__fastcall *)(struct IMFTranscodeProfile *))a2->lpVtbl->AddRef)(a2);
    }
    else
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeConfig::SetProfile", 475, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 62;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    v6 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
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
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v8 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v8, "CTranscodeConfig::SetProfile", 473, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 61;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids, this, v6);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180036440  mov     [rsp+arg_0], rbx
0x180036445  mov     [rsp+arg_10], rsi
0x18003644a  push    rdi
0x18003644b  sub     rsp, 30h
0x18003644f  mov     rdi, rdx
0x180036452  mov     rsi, rcx
0x180036455  lea     rdx, aCtranscodeconf_6; "CTranscodeConfig::SetProfile"
0x18003645c  mov     r8d, 1D9h; int
0x180036462  lea     rcx, [rsp+38h+arg_8]; this
0x180036467  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003646c  test    rdi, rdi
0x18003646f  jnz     loc_180036527
0x180036475  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003647c  mov     ebx, 80004003h
0x180036481  test    rcx, rcx
0x180036484  jnz     short loc_1800364C7
0x180036486  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003648c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036493  mov     rcx, rax
0x180036496  test    rax, rax
0x180036499  jz      short loc_1800364B9
0x18003649b  mov     rax, [rax]
0x18003649e  mov     edx, 7F0h
0x1800364a3  mov     rax, [rax+8]
0x1800364a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364ac  test    eax, eax
0x1800364ae  jz      short loc_1800364B9
0x1800364b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800364b7  jmp     short loc_1800364C7
0x1800364b9  lea     rcx, qword_180069A90; this
0x1800364c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800364c7  cmp     byte ptr [rcx+8], 0
0x1800364cb  jz      short loc_1800364F2
0x1800364cd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800364d2  cmp     [rax+7CCh], ebx
0x1800364d8  jz      short loc_1800364F2
0x1800364da  mov     r9d, ebx; int
0x1800364dd  lea     rdx, aCtranscodeconf_6; "CTranscodeConfig::SetProfile"
0x1800364e4  mov     r8d, 1D9h; int
0x1800364ea  mov     rcx, rax; this
0x1800364ed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800364f2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800364f7  cmp     al, 1
0x1800364f9  jb      loc_1800365EF
0x1800364ff  mov     edx, 3Dh ; '='
0x180036504  mov     rcx, cs:WPP_GLOBAL_Control
0x18003650b  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x180036512  mov     r9, rsi
0x180036515  mov     [rsp+38h+var_18], ebx
0x180036519  mov     rcx, [rcx+10h]
0x18003651d  call    WPP_SF_qd
0x180036522  jmp     loc_1800365EF
0x180036527  mov     rdx, rdi; struct IMFTranscodeProfile *
0x18003652a  mov     rcx, rsi; this
0x18003652d  call    ?ValidateProfile@CTranscodeConfig@@IEAAJPEAUIMFTranscodeProfile@@@Z; CTranscodeConfig::ValidateProfile(IMFTranscodeProfile *)
0x180036532  mov     ebx, eax
0x180036534  test    eax, eax
0x180036536  jns     loc_1800365C7
0x18003653c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036543  test    rcx, rcx
0x180036546  jnz     short loc_180036589
0x180036548  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003654e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036555  mov     rcx, rax
0x180036558  test    rax, rax
0x18003655b  jz      short loc_18003657B
0x18003655d  mov     rax, [rax]
0x180036560  mov     edx, 7F0h
0x180036565  mov     rax, [rax+8]
0x180036569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003656e  test    eax, eax
0x180036570  jz      short loc_18003657B
0x180036572  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036579  jmp     short loc_180036589
0x18003657b  lea     rcx, qword_180069A90; this
0x180036582  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036589  cmp     byte ptr [rcx+8], 0
0x18003658d  jz      short loc_1800365B4
0x18003658f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036594  cmp     [rax+7CCh], ebx
0x18003659a  jz      short loc_1800365B4
0x18003659c  mov     r9d, ebx; int
0x18003659f  lea     rdx, aCtranscodeconf_6; "CTranscodeConfig::SetProfile"
0x1800365a6  mov     r8d, 1DBh; int
0x1800365ac  mov     rcx, rax; this
0x1800365af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800365b4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800365b9  cmp     al, 1
0x1800365bb  jb      short loc_1800365EF
0x1800365bd  mov     edx, 3Eh ; '>'
0x1800365c2  jmp     loc_180036504
0x1800365c7  mov     rcx, [rsi+10h]
0x1800365cb  test    rcx, rcx
0x1800365ce  jz      short loc_1800365DC
0x1800365d0  mov     rax, [rcx]
0x1800365d3  mov     rax, [rax+10h]
0x1800365d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365dc  mov     [rsi+10h], rdi
0x1800365e0  mov     rcx, rdi
0x1800365e3  mov     rax, [rdi]
0x1800365e6  mov     rax, [rax+8]
0x1800365ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365ef  lea     rcx, [rsp+38h+arg_8]; this
0x1800365f4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800365f9  mov     rsi, [rsp+38h+arg_10]
0x1800365fe  mov     eax, ebx
0x180036600  mov     rbx, [rsp+38h+arg_0]
0x180036605  add     rsp, 30h
0x180036609  pop     rdi
0x18003660a  retn
```
