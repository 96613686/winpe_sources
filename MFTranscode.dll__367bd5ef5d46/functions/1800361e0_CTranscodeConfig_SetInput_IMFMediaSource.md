# CTranscodeConfig::SetInput(IMFMediaSource *)

- ea: `0x1800361e0`
- end: `0x180036306`
- name: `?SetInput@CTranscodeConfig@@UEAAJPEAUIMFMediaSource@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(CTranscodeConfig *__hidden this, struct IMFMediaSource *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x1800361e0`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036226`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036226`

## string_xrefs

- `0x1800361f5`: `CTranscodeConfig::SetInput`
- `0x18003627d`: `CTranscodeConfig::SetInput`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::SetInput(CTranscodeConfig *this, struct IMFMediaSource *a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  unsigned int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rcx
  char v11; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v11, "CTranscodeConfig::SetInput", 383);
  if ( a2 )
  {
    v9 = *((_QWORD *)this + 3);
    v6 = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 3) = a2;
    ((void (__fastcall *)(struct IMFMediaSource *))a2->lpVtbl->AddRef)(a2);
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
        CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeConfig::SetInput", 383, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
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
0x1800361e0  mov     [rsp+arg_0], rbx
0x1800361e5  mov     [rsp+arg_10], rsi
0x1800361ea  push    rdi
0x1800361eb  sub     rsp, 30h
0x1800361ef  mov     rdi, rdx
0x1800361f2  mov     rsi, rcx
0x1800361f5  lea     rdx, aCtranscodeconf_9; "CTranscodeConfig::SetInput"
0x1800361fc  mov     r8d, 17Fh; int
0x180036202  lea     rcx, [rsp+38h+arg_8]; this
0x180036207  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003620c  test    rdi, rdi
0x18003620f  jnz     loc_1800362C0
0x180036215  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003621c  mov     ebx, 80004003h
0x180036221  test    rcx, rcx
0x180036224  jnz     short loc_180036267
0x180036226  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003622c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036233  mov     rcx, rax
0x180036236  test    rax, rax
0x180036239  jz      short loc_180036259
0x18003623b  mov     rax, [rax]
0x18003623e  mov     edx, 7F0h
0x180036243  mov     rax, [rax+8]
0x180036247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003624c  test    eax, eax
0x18003624e  jz      short loc_180036259
0x180036250  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036257  jmp     short loc_180036267
0x180036259  lea     rcx, qword_180069A90; this
0x180036260  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036267  cmp     byte ptr [rcx+8], 0
0x18003626b  jz      short loc_180036292
0x18003626d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036272  cmp     [rax+7CCh], ebx
0x180036278  jz      short loc_180036292
0x18003627a  mov     r9d, ebx; int
0x18003627d  lea     rdx, aCtranscodeconf_9; "CTranscodeConfig::SetInput"
0x180036284  mov     r8d, 17Fh; int
0x18003628a  mov     rcx, rax; this
0x18003628d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036292  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180036297  cmp     al, 1
0x180036299  jb      short loc_1800362EA
0x18003629b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362a2  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x1800362a9  mov     edx, 35h ; '5'
0x1800362ae  mov     [rsp+38h+var_18], ebx
0x1800362b2  mov     r9, rsi
0x1800362b5  mov     rcx, [rcx+10h]
0x1800362b9  call    WPP_SF_qd
0x1800362be  jmp     short loc_1800362EA
0x1800362c0  mov     rcx, [rsi+18h]
0x1800362c4  xor     ebx, ebx
0x1800362c6  test    rcx, rcx
0x1800362c9  jz      short loc_1800362D7
0x1800362cb  mov     rax, [rcx]
0x1800362ce  mov     rax, [rax+10h]
0x1800362d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362d7  mov     [rsi+18h], rdi
0x1800362db  mov     rcx, [rdi]
0x1800362de  mov     rax, [rcx+8]
0x1800362e2  mov     rcx, rdi
0x1800362e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362ea  lea     rcx, [rsp+38h+arg_8]; this
0x1800362ef  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800362f4  mov     rsi, [rsp+38h+arg_10]
0x1800362f9  mov     eax, ebx
0x1800362fb  mov     rbx, [rsp+38h+arg_0]
0x180036300  add     rsp, 30h
0x180036304  pop     rdi
0x180036305  retn
```
