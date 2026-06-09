# CTranscodeConfig::GetProfile(IMFTranscodeProfile * *)

- ea: `0x180035a50`
- end: `0x180035b66`
- name: `?GetProfile@CTranscodeConfig@@UEAAJPEAPEAUIMFTranscodeProfile@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(CTranscodeConfig *__hidden this, struct IMFTranscodeProfile **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x180035a50`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035a96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035a96`

## string_xrefs

- `0x180035a65`: `CTranscodeConfig::GetProfile`
- `0x180035aed`: `CTranscodeConfig::GetProfile`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::GetProfile(CTranscodeConfig *this, struct IMFTranscodeProfile **a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  unsigned int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFTranscodeProfile *v9; // rcx
  char v11; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v11, "CTranscodeConfig::GetProfile", 490);
  if ( a2 )
  {
    v9 = (struct IMFTranscodeProfile *)*((_QWORD *)this + 2);
    v6 = 0;
    *a2 = v9;
    if ( v9 )
      ((void (__fastcall *)(struct IMFTranscodeProfile *))v9->lpVtbl->AddRef)(v9);
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
        CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeConfig::GetProfile", 490, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
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
0x180035a50  mov     [rsp+arg_0], rbx
0x180035a55  mov     [rsp+arg_10], rsi
0x180035a5a  push    rdi
0x180035a5b  sub     rsp, 30h
0x180035a5f  mov     rdi, rdx
0x180035a62  mov     rsi, rcx
0x180035a65  lea     rdx, aCtranscodeconf; "CTranscodeConfig::GetProfile"
0x180035a6c  mov     r8d, 1EAh; int
0x180035a72  lea     rcx, [rsp+38h+arg_8]; this
0x180035a77  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180035a7c  test    rdi, rdi
0x180035a7f  jnz     loc_180035B30
0x180035a85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035a8c  mov     ebx, 80004003h
0x180035a91  test    rcx, rcx
0x180035a94  jnz     short loc_180035AD7
0x180035a96  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035a9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035aa3  mov     rcx, rax
0x180035aa6  test    rax, rax
0x180035aa9  jz      short loc_180035AC9
0x180035aab  mov     rax, [rax]
0x180035aae  mov     edx, 7F0h
0x180035ab3  mov     rax, [rax+8]
0x180035ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035abc  test    eax, eax
0x180035abe  jz      short loc_180035AC9
0x180035ac0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ac7  jmp     short loc_180035AD7
0x180035ac9  lea     rcx, qword_180069A90; this
0x180035ad0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ad7  cmp     byte ptr [rcx+8], 0
0x180035adb  jz      short loc_180035B02
0x180035add  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035ae2  cmp     [rax+7CCh], ebx
0x180035ae8  jz      short loc_180035B02
0x180035aea  mov     r9d, ebx; int
0x180035aed  lea     rdx, aCtranscodeconf; "CTranscodeConfig::GetProfile"
0x180035af4  mov     r8d, 1EAh; int
0x180035afa  mov     rcx, rax; this
0x180035afd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035b02  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180035b07  cmp     al, 1
0x180035b09  jb      short loc_180035B4A
0x180035b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b12  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x180035b19  mov     edx, 3Fh ; '?'
0x180035b1e  mov     [rsp+38h+var_18], ebx
0x180035b22  mov     r9, rsi
0x180035b25  mov     rcx, [rcx+10h]
0x180035b29  call    WPP_SF_qd
0x180035b2e  jmp     short loc_180035B4A
0x180035b30  mov     rcx, [rsi+10h]
0x180035b34  xor     ebx, ebx
0x180035b36  mov     [rdi], rcx
0x180035b39  test    rcx, rcx
0x180035b3c  jz      short loc_180035B4A
0x180035b3e  mov     rdx, [rcx]
0x180035b41  mov     rax, [rdx+8]
0x180035b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b4a  lea     rcx, [rsp+38h+arg_8]; this
0x180035b4f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180035b54  mov     rsi, [rsp+38h+arg_10]
0x180035b59  mov     eax, ebx
0x180035b5b  mov     rbx, [rsp+38h+arg_0]
0x180035b60  add     rsp, 30h
0x180035b64  pop     rdi
0x180035b65  retn
```
