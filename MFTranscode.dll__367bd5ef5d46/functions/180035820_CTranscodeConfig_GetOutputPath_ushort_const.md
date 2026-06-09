# CTranscodeConfig::GetOutputPath(ushort const * *)

- ea: `0x180035820`
- end: `0x18003592a`
- name: `?GetOutputPath@CTranscodeConfig@@UEAAJPEAPEBG@Z`
- size: `266`
- prototype: `__int64 __fastcall(CTranscodeConfig *__hidden this, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000f05c`
- `0x18001a330`
- `0x18001c280`
- `0x180035820`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035866`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035866`

## string_xrefs

- `0x180035835`: `CTranscodeConfig::GetOutputPath`
- `0x1800358bd`: `CTranscodeConfig::GetOutputPath`

## pseudocode

```c
__int64 __fastcall CTranscodeConfig::GetOutputPath(CTranscodeConfig *this, const unsigned __int16 **a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  unsigned int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v10; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v10, "CTranscodeConfig::GetOutputPath", 431);
  if ( a2 )
  {
    v6 = 0;
    *a2 = (const unsigned __int16 *)CMFBaseStringT<unsigned short>::PContents((char *)this + 32, v4);
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
        CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeConfig::GetOutputPath", 431, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids,
        this,
        -2147467261);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v10);
  return v6;
}

```

## disassembly

```asm
0x180035820  mov     [rsp+arg_0], rbx
0x180035825  mov     [rsp+arg_10], rsi
0x18003582a  push    rdi
0x18003582b  sub     rsp, 30h
0x18003582f  mov     rdi, rdx
0x180035832  mov     rsi, rcx
0x180035835  lea     rdx, aCtranscodeconf_1; "CTranscodeConfig::GetOutputPath"
0x18003583c  mov     r8d, 1AFh; int
0x180035842  lea     rcx, [rsp+38h+arg_8]; this
0x180035847  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003584c  test    rdi, rdi
0x18003584f  jnz     loc_180035900
0x180035855  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003585c  mov     ebx, 80004003h
0x180035861  test    rcx, rcx
0x180035864  jnz     short loc_1800358A7
0x180035866  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003586c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035873  mov     rcx, rax
0x180035876  test    rax, rax
0x180035879  jz      short loc_180035899
0x18003587b  mov     rax, [rax]
0x18003587e  mov     edx, 7F0h
0x180035883  mov     rax, [rax+8]
0x180035887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003588c  test    eax, eax
0x18003588e  jz      short loc_180035899
0x180035890  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035897  jmp     short loc_1800358A7
0x180035899  lea     rcx, qword_180069A90; this
0x1800358a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800358a7  cmp     byte ptr [rcx+8], 0
0x1800358ab  jz      short loc_1800358D2
0x1800358ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800358b2  cmp     [rax+7CCh], ebx
0x1800358b8  jz      short loc_1800358D2
0x1800358ba  mov     r9d, ebx; int
0x1800358bd  lea     rdx, aCtranscodeconf_1; "CTranscodeConfig::GetOutputPath"
0x1800358c4  mov     r8d, 1AFh; int
0x1800358ca  mov     rcx, rax; this
0x1800358cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800358d2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800358d7  cmp     al, 1
0x1800358d9  jb      short loc_18003590E
0x1800358db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358e2  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x1800358e9  mov     edx, 3Ah ; ':'
0x1800358ee  mov     [rsp+38h+var_18], ebx
0x1800358f2  mov     r9, rsi
0x1800358f5  mov     rcx, [rcx+10h]
0x1800358f9  call    WPP_SF_qd
0x1800358fe  jmp     short loc_18003590E
0x180035900  xor     ebx, ebx
0x180035902  lea     rcx, [rsi+20h]
0x180035906  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18003590b  mov     [rdi], rax
0x18003590e  lea     rcx, [rsp+38h+arg_8]; this
0x180035913  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180035918  mov     rsi, [rsp+38h+arg_10]
0x18003591d  mov     eax, ebx
0x18003591f  mov     rbx, [rsp+38h+arg_0]
0x180035924  add     rsp, 30h
0x180035928  pop     rdi
0x180035929  retn
```
