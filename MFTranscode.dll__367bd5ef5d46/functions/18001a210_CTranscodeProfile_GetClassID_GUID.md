# CTranscodeProfile::GetClassID(_GUID *)

- ea: `0x18001a210`
- end: `0x18001a31a`
- name: `?GetClassID@CTranscodeProfile@@UEAAJPEAU_GUID@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(CTranscodeProfile *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a210`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a256`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a256`

## string_xrefs

- `0x18001a225`: `CTranscodeProfile::GetClassID`
- `0x18001a2ad`: `CTranscodeProfile::GetClassID`

## pseudocode

```c
__int64 __fastcall CTranscodeProfile::GetClassID(CTranscodeProfile *this, struct _GUID *a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  unsigned int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v10; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v10, "CTranscodeProfile::GetClassID", 449);
  if ( a2 )
  {
    v6 = 0;
    *a2 = CLSID_MFTranscodeProfile;
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
        CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeProfile::GetClassID", 452, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_60c454de96f7327ebad2115a8fee1984_Traceguids,
        (char *)this - 8,
        -2147467261);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v10);
  return v6;
}

```

## disassembly

```asm
0x18001a210  mov     [rsp+arg_8], rbx
0x18001a215  mov     [rsp+arg_10], rsi
0x18001a21a  push    rdi
0x18001a21b  sub     rsp, 30h
0x18001a21f  mov     rdi, rdx
0x18001a222  mov     rsi, rcx
0x18001a225  lea     rdx, aCtranscodeprof_23; "CTranscodeProfile::GetClassID"
0x18001a22c  mov     r8d, 1C1h; int
0x18001a232  lea     rcx, [rsp+38h+arg_0]; this
0x18001a237  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001a23c  test    rdi, rdi
0x18001a23f  jnz     loc_18001A2F1
0x18001a245  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a24c  mov     ebx, 80004003h
0x18001a251  test    rcx, rcx
0x18001a254  jnz     short loc_18001A297
0x18001a256  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a25c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a263  mov     rcx, rax
0x18001a266  test    rax, rax
0x18001a269  jz      short loc_18001A289
0x18001a26b  mov     rax, [rax]
0x18001a26e  mov     edx, 7F0h
0x18001a273  mov     rax, [rax+8]
0x18001a277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a27c  test    eax, eax
0x18001a27e  jz      short loc_18001A289
0x18001a280  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a287  jmp     short loc_18001A297
0x18001a289  lea     rcx, qword_180069A90; this
0x18001a290  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a297  cmp     byte ptr [rcx+8], 0
0x18001a29b  jz      short loc_18001A2C2
0x18001a29d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a2a2  cmp     [rax+7CCh], ebx
0x18001a2a8  jz      short loc_18001A2C2
0x18001a2aa  mov     r9d, ebx; int
0x18001a2ad  lea     rdx, aCtranscodeprof_23; "CTranscodeProfile::GetClassID"
0x18001a2b4  mov     r8d, 1C4h; int
0x18001a2ba  mov     rcx, rax; this
0x18001a2bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001a2c2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001a2c7  cmp     al, 1
0x18001a2c9  jb      short loc_18001A2FE
0x18001a2cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2d2  lea     r9, [rsi-8]
0x18001a2d6  mov     edx, 2Eh ; '.'
0x18001a2db  mov     [rsp+38h+var_18], ebx
0x18001a2df  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x18001a2e6  mov     rcx, [rcx+10h]
0x18001a2ea  call    WPP_SF_qd
0x18001a2ef  jmp     short loc_18001A2FE
0x18001a2f1  movups  xmm0, xmmword ptr cs:CLSID_MFTranscodeProfile.Data1
0x18001a2f8  xor     ebx, ebx
0x18001a2fa  movdqu  xmmword ptr [rdi], xmm0
0x18001a2fe  lea     rcx, [rsp+38h+arg_0]; this
0x18001a303  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001a308  mov     rsi, [rsp+38h+arg_10]
0x18001a30d  mov     eax, ebx
0x18001a30f  mov     rbx, [rsp+38h+arg_8]
0x18001a314  add     rsp, 30h
0x18001a318  pop     rdi
0x18001a319  retn
```
