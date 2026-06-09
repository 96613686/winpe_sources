# CTranscodeConfig::GetOutputByteStream(IMFByteStream * *)

- ea: `0x180035700`
- end: `0x180035816`
- name: `?GetOutputByteStream@CTranscodeConfig@@UEAAJPEAPEAUIMFByteStream@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(CTranscodeConfig *__hidden this, struct IMFByteStream **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x180035700`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035746`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035746`

## string_xrefs

- `0x180035715`: `CTranscodeConfig::GetOutputByteStream`
- `0x18003579d`: `CTranscodeConfig::GetOutputByteStream`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::GetOutputByteStream(CTranscodeConfig *this, struct IMFByteStream **a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  unsigned int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFByteStream *v9; // rcx
  char v11; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v11, "CTranscodeConfig::GetOutputByteStream", 460);
  if ( a2 )
  {
    v9 = (struct IMFByteStream *)*((_QWORD *)this + 7);
    v6 = 0;
    *a2 = v9;
    if ( v9 )
      ((void (__fastcall *)(struct IMFByteStream *))v9->lpVtbl->AddRef)(v9);
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
        CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeConfig::GetOutputByteStream", 460, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
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
0x180035700  mov     [rsp+arg_0], rbx
0x180035705  mov     [rsp+arg_10], rsi
0x18003570a  push    rdi
0x18003570b  sub     rsp, 30h
0x18003570f  mov     rdi, rdx
0x180035712  mov     rsi, rcx
0x180035715  lea     rdx, aCtranscodeconf_0; "CTranscodeConfig::GetOutputByteStream"
0x18003571c  mov     r8d, 1CCh; int
0x180035722  lea     rcx, [rsp+38h+arg_8]; this
0x180035727  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003572c  test    rdi, rdi
0x18003572f  jnz     loc_1800357E0
0x180035735  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003573c  mov     ebx, 80004003h
0x180035741  test    rcx, rcx
0x180035744  jnz     short loc_180035787
0x180035746  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003574c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035753  mov     rcx, rax
0x180035756  test    rax, rax
0x180035759  jz      short loc_180035779
0x18003575b  mov     rax, [rax]
0x18003575e  mov     edx, 7F0h
0x180035763  mov     rax, [rax+8]
0x180035767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003576c  test    eax, eax
0x18003576e  jz      short loc_180035779
0x180035770  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035777  jmp     short loc_180035787
0x180035779  lea     rcx, qword_180069A90; this
0x180035780  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035787  cmp     byte ptr [rcx+8], 0
0x18003578b  jz      short loc_1800357B2
0x18003578d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035792  cmp     [rax+7CCh], ebx
0x180035798  jz      short loc_1800357B2
0x18003579a  mov     r9d, ebx; int
0x18003579d  lea     rdx, aCtranscodeconf_0; "CTranscodeConfig::GetOutputByteStream"
0x1800357a4  mov     r8d, 1CCh; int
0x1800357aa  mov     rcx, rax; this
0x1800357ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800357b2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800357b7  cmp     al, 1
0x1800357b9  jb      short loc_1800357FA
0x1800357bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800357c2  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x1800357c9  mov     edx, 3Ch ; '<'
0x1800357ce  mov     [rsp+38h+var_18], ebx
0x1800357d2  mov     r9, rsi
0x1800357d5  mov     rcx, [rcx+10h]
0x1800357d9  call    WPP_SF_qd
0x1800357de  jmp     short loc_1800357FA
0x1800357e0  mov     rcx, [rsi+38h]
0x1800357e4  xor     ebx, ebx
0x1800357e6  mov     [rdi], rcx
0x1800357e9  test    rcx, rcx
0x1800357ec  jz      short loc_1800357FA
0x1800357ee  mov     rdx, [rcx]
0x1800357f1  mov     rax, [rdx+8]
0x1800357f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357fa  lea     rcx, [rsp+38h+arg_8]; this
0x1800357ff  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180035804  mov     rsi, [rsp+38h+arg_10]
0x180035809  mov     eax, ebx
0x18003580b  mov     rbx, [rsp+38h+arg_0]
0x180035810  add     rsp, 30h
0x180035814  pop     rdi
0x180035815  retn
```
