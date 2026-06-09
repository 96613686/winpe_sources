# CTranscodeComponentCreator::QueryInterface(_GUID const &,void * *)

- ea: `0x18001b160`
- end: `0x18001b340`
- name: `?QueryInterface@CTranscodeComponentCreator@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `480`
- prototype: `int(CTranscodeComponentCreator *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180019850`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001b160`
- `0x18001c280`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b1a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b29c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b1a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b29c`

## string_xrefs

- `0x18001b178`: `CTranscodeComponentCreator::QueryInterface`
- `0x18001b200`: `CTranscodeComponentCreator::QueryInterface`
- `0x18001b2f3`: `CTranscodeComponentCreator::QueryInterface`

## pseudocode

```c
__int64 __fastcall CTranscodeComponentCreator::QueryInterface(
        CTranscodeComponentCreator *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v6; // rdx
  __int64 *v7; // rcx
  unsigned int v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v17; // [rsp+50h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v17,
    "CTranscodeComponentCreator::QueryInterface",
    167);
  if ( a3 )
  {
    *a3 = 0;
    if ( !memcmp_0(a2, &IID_IMFComponentCreator, 0x10u) || !memcmp_0(a2, &IID_IUnknown, 0x10u) )
    {
      v8 = 0;
      *a3 = this;
      _InterlockedIncrement((volatile signed __int32 *)this + 2);
      goto LABEL_26;
    }
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147467262;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467262 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CTranscodeComponentCreator::QueryInterface",
          180,
          -2147467262);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 20;
      goto LABEL_12;
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v10, "CTranscodeComponentCreator::QueryInterface", 167, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 19;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, this, v8);
    }
  }
LABEL_26:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
  return v8;
}

```

## disassembly

```asm
0x18001b160  mov     [rsp+arg_0], rbx
0x18001b165  mov     [rsp+arg_8], rsi
0x18001b16a  push    rdi
0x18001b16b  sub     rsp, 30h
0x18001b16f  mov     rsi, r8
0x18001b172  mov     rbx, rdx
0x18001b175  mov     rdi, rcx
0x18001b178  lea     rdx, aCtranscodecomp_0; "CTranscodeComponentCreator::QueryInterf"...
0x18001b17f  mov     r8d, 0A7h; int
0x18001b185  lea     rcx, [rsp+38h+arg_10]; this
0x18001b18a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001b18f  test    rsi, rsi
0x18001b192  jnz     loc_18001B24A
0x18001b198  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b19f  mov     ebx, 80004003h
0x18001b1a4  test    rcx, rcx
0x18001b1a7  jnz     short loc_18001B1EA
0x18001b1a9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001b1af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b1b6  mov     rcx, rax
0x18001b1b9  test    rax, rax
0x18001b1bc  jz      short loc_18001B1DC
0x18001b1be  mov     rax, [rax]
0x18001b1c1  mov     edx, 7F0h
0x18001b1c6  mov     rax, [rax+8]
0x18001b1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1cf  test    eax, eax
0x18001b1d1  jz      short loc_18001B1DC
0x18001b1d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b1da  jmp     short loc_18001B1EA
0x18001b1dc  lea     rcx, qword_180069A90; this
0x18001b1e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b1ea  cmp     byte ptr [rcx+8], 0
0x18001b1ee  jz      short loc_18001B215
0x18001b1f0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001b1f5  cmp     [rax+7CCh], ebx
0x18001b1fb  jz      short loc_18001B215
0x18001b1fd  mov     r9d, ebx; int
0x18001b200  lea     rdx, aCtranscodecomp_0; "CTranscodeComponentCreator::QueryInterf"...
0x18001b207  mov     r8d, 0A7h; int
0x18001b20d  mov     rcx, rax; this
0x18001b210  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001b215  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001b21a  cmp     al, 1
0x18001b21c  jb      loc_18001B324
0x18001b222  mov     edx, 13h
0x18001b227  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b22e  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x18001b235  mov     r9, rdi
0x18001b238  mov     [rsp+38h+var_18], ebx
0x18001b23c  mov     rcx, [rcx+10h]
0x18001b240  call    WPP_SF_qd
0x18001b245  jmp     loc_18001B324
0x18001b24a  mov     r8d, 10h; Size
0x18001b250  mov     qword ptr [rsi], 0
0x18001b257  lea     rdx, IID_IMFComponentCreator; Buf2
0x18001b25e  mov     rcx, rbx; Buf1
0x18001b261  call    memcmp_0
0x18001b266  test    eax, eax
0x18001b268  jz      loc_18001B31B
0x18001b26e  mov     r8d, 10h; Size
0x18001b274  lea     rdx, IID_IUnknown; Buf2
0x18001b27b  mov     rcx, rbx; Buf1
0x18001b27e  call    memcmp_0
0x18001b283  test    eax, eax
0x18001b285  jz      loc_18001B31B
0x18001b28b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b292  mov     ebx, 80004002h
0x18001b297  test    rcx, rcx
0x18001b29a  jnz     short loc_18001B2DD
0x18001b29c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001b2a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b2a9  mov     rcx, rax
0x18001b2ac  test    rax, rax
0x18001b2af  jz      short loc_18001B2CF
0x18001b2b1  mov     rax, [rax]
0x18001b2b4  mov     edx, 7F0h
0x18001b2b9  mov     rax, [rax+8]
0x18001b2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2c2  test    eax, eax
0x18001b2c4  jz      short loc_18001B2CF
0x18001b2c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b2cd  jmp     short loc_18001B2DD
0x18001b2cf  lea     rcx, qword_180069A90; this
0x18001b2d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b2dd  cmp     byte ptr [rcx+8], 0
0x18001b2e1  jz      short loc_18001B308
0x18001b2e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001b2e8  cmp     [rax+7CCh], ebx
0x18001b2ee  jz      short loc_18001B308
0x18001b2f0  mov     r9d, ebx; int
0x18001b2f3  lea     rdx, aCtranscodecomp_0; "CTranscodeComponentCreator::QueryInterf"...
0x18001b2fa  mov     r8d, 0B4h; int
0x18001b300  mov     rcx, rax; this
0x18001b303  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001b308  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001b30d  cmp     al, 1
0x18001b30f  jb      short loc_18001B324
0x18001b311  mov     edx, 14h
0x18001b316  jmp     loc_18001B227
0x18001b31b  xor     ebx, ebx
0x18001b31d  mov     [rsi], rdi
0x18001b320  lock inc dword ptr [rdi+8]
0x18001b324  lea     rcx, [rsp+38h+arg_10]; this
0x18001b329  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001b32e  mov     rsi, [rsp+38h+arg_8]
0x18001b333  mov     eax, ebx
0x18001b335  mov     rbx, [rsp+38h+arg_0]
0x18001b33a  add     rsp, 30h
0x18001b33e  pop     rdi
0x18001b33f  retn
```
