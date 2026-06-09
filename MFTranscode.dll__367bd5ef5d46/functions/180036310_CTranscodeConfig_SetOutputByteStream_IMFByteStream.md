# CTranscodeConfig::SetOutputByteStream(IMFByteStream *)

- ea: `0x180036310`
- end: `0x180036436`
- name: `?SetOutputByteStream@CTranscodeConfig@@UEAAJPEAUIMFByteStream@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(CTranscodeConfig *__hidden this, struct IMFByteStream *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x180036310`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036356`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036356`

## string_xrefs

- `0x180036325`: `CTranscodeConfig::SetOutputByteStream`
- `0x1800363ad`: `CTranscodeConfig::SetOutputByteStream`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::SetOutputByteStream(CTranscodeConfig *this, struct IMFByteStream *a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  unsigned int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rcx
  char v11; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v11, "CTranscodeConfig::SetOutputByteStream", 443);
  if ( a2 )
  {
    v9 = *((_QWORD *)this + 7);
    v6 = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 7) = a2;
    ((void (__fastcall *)(struct IMFByteStream *))a2->lpVtbl->AddRef)(a2);
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
        CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeConfig::SetOutputByteStream", 443, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
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
0x180036310  mov     [rsp+arg_0], rbx
0x180036315  mov     [rsp+arg_10], rsi
0x18003631a  push    rdi
0x18003631b  sub     rsp, 30h
0x18003631f  mov     rdi, rdx
0x180036322  mov     rsi, rcx
0x180036325  lea     rdx, aCtranscodeconf_3; "CTranscodeConfig::SetOutputByteStream"
0x18003632c  mov     r8d, 1BBh; int
0x180036332  lea     rcx, [rsp+38h+arg_8]; this
0x180036337  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003633c  test    rdi, rdi
0x18003633f  jnz     loc_1800363F0
0x180036345  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003634c  mov     ebx, 80004003h
0x180036351  test    rcx, rcx
0x180036354  jnz     short loc_180036397
0x180036356  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003635c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036363  mov     rcx, rax
0x180036366  test    rax, rax
0x180036369  jz      short loc_180036389
0x18003636b  mov     rax, [rax]
0x18003636e  mov     edx, 7F0h
0x180036373  mov     rax, [rax+8]
0x180036377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003637c  test    eax, eax
0x18003637e  jz      short loc_180036389
0x180036380  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036387  jmp     short loc_180036397
0x180036389  lea     rcx, qword_180069A90; this
0x180036390  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036397  cmp     byte ptr [rcx+8], 0
0x18003639b  jz      short loc_1800363C2
0x18003639d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800363a2  cmp     [rax+7CCh], ebx
0x1800363a8  jz      short loc_1800363C2
0x1800363aa  mov     r9d, ebx; int
0x1800363ad  lea     rdx, aCtranscodeconf_3; "CTranscodeConfig::SetOutputByteStream"
0x1800363b4  mov     r8d, 1BBh; int
0x1800363ba  mov     rcx, rax; this
0x1800363bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800363c2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800363c7  cmp     al, 1
0x1800363c9  jb      short loc_18003641A
0x1800363cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363d2  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x1800363d9  mov     edx, 3Bh ; ';'
0x1800363de  mov     [rsp+38h+var_18], ebx
0x1800363e2  mov     r9, rsi
0x1800363e5  mov     rcx, [rcx+10h]
0x1800363e9  call    WPP_SF_qd
0x1800363ee  jmp     short loc_18003641A
0x1800363f0  mov     rcx, [rsi+38h]
0x1800363f4  xor     ebx, ebx
0x1800363f6  test    rcx, rcx
0x1800363f9  jz      short loc_180036407
0x1800363fb  mov     rax, [rcx]
0x1800363fe  mov     rax, [rax+10h]
0x180036402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036407  mov     [rsi+38h], rdi
0x18003640b  mov     rcx, [rdi]
0x18003640e  mov     rax, [rcx+8]
0x180036412  mov     rcx, rdi
0x180036415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003641a  lea     rcx, [rsp+38h+arg_8]; this
0x18003641f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180036424  mov     rsi, [rsp+38h+arg_10]
0x180036429  mov     eax, ebx
0x18003642b  mov     rbx, [rsp+38h+arg_0]
0x180036430  add     rsp, 30h
0x180036434  pop     rdi
0x180036435  retn
```
