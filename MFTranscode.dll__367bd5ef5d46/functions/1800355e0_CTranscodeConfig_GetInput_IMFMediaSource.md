# CTranscodeConfig::GetInput(IMFMediaSource * *)

- ea: `0x1800355e0`
- end: `0x1800356f6`
- name: `?GetInput@CTranscodeConfig@@UEAAJPEAPEAUIMFMediaSource@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(CTranscodeConfig *__hidden this, struct IMFMediaSource **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x1800355e0`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035626`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035626`

## string_xrefs

- `0x1800355f5`: `CTranscodeConfig::GetInput`
- `0x18003567d`: `CTranscodeConfig::GetInput`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::GetInput(CTranscodeConfig *this, struct IMFMediaSource **a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  unsigned int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFMediaSource *v9; // rcx
  char v11; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v11, "CTranscodeConfig::GetInput", 398);
  if ( a2 )
  {
    v9 = (struct IMFMediaSource *)*((_QWORD *)this + 3);
    v6 = 0;
    *a2 = v9;
    if ( v9 )
      ((void (__fastcall *)(struct IMFMediaSource *))v9->lpVtbl->AddRef)(v9);
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeConfig::GetInput", 398, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids,
        this,
        -2147467261);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v11);
  return v6;
}

```

## disassembly

```asm
0x1800355e0  mov     [rsp+arg_0], rbx
0x1800355e5  mov     [rsp+arg_10], rsi
0x1800355ea  push    rdi
0x1800355eb  sub     rsp, 30h
0x1800355ef  mov     rdi, rdx
0x1800355f2  mov     rsi, rcx
0x1800355f5  lea     rdx, aCtranscodeconf_2; "CTranscodeConfig::GetInput"
0x1800355fc  mov     r8d, 18Eh; int
0x180035602  lea     rcx, [rsp+38h+arg_8]; this
0x180035607  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003560c  test    rdi, rdi
0x18003560f  jnz     loc_1800356C0
0x180035615  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003561c  mov     ebx, 80004003h
0x180035621  test    rcx, rcx
0x180035624  jnz     short loc_180035667
0x180035626  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003562c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035633  mov     rcx, rax
0x180035636  test    rax, rax
0x180035639  jz      short loc_180035659
0x18003563b  mov     rax, [rax]
0x18003563e  mov     edx, 7F0h
0x180035643  mov     rax, [rax+8]
0x180035647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003564c  test    eax, eax
0x18003564e  jz      short loc_180035659
0x180035650  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035657  jmp     short loc_180035667
0x180035659  lea     rcx, qword_180069A90; this
0x180035660  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035667  cmp     byte ptr [rcx+8], 0
0x18003566b  jz      short loc_180035692
0x18003566d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035672  cmp     [rax+7CCh], ebx
0x180035678  jz      short loc_180035692
0x18003567a  mov     r9d, ebx; int
0x18003567d  lea     rdx, aCtranscodeconf_2; "CTranscodeConfig::GetInput"
0x180035684  mov     r8d, 18Eh; int
0x18003568a  mov     rcx, rax; this
0x18003568d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035692  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180035697  cmp     al, 1
0x180035699  jb      short loc_1800356DA
0x18003569b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356a2  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x1800356a9  mov     edx, 36h ; '6'
0x1800356ae  mov     [rsp+38h+var_18], ebx
0x1800356b2  mov     r9, rsi
0x1800356b5  mov     rcx, [rcx+10h]
0x1800356b9  call    WPP_SF_qd
0x1800356be  jmp     short loc_1800356DA
0x1800356c0  mov     rcx, [rsi+18h]
0x1800356c4  xor     ebx, ebx
0x1800356c6  mov     [rdi], rcx
0x1800356c9  test    rcx, rcx
0x1800356cc  jz      short loc_1800356DA
0x1800356ce  mov     rdx, [rcx]
0x1800356d1  mov     rax, [rdx+8]
0x1800356d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356da  lea     rcx, [rsp+38h+arg_8]; this
0x1800356df  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800356e4  mov     rsi, [rsp+38h+arg_10]
0x1800356e9  mov     eax, ebx
0x1800356eb  mov     rbx, [rsp+38h+arg_0]
0x1800356f0  add     rsp, 30h
0x1800356f4  pop     rdi
0x1800356f5  retn
```
