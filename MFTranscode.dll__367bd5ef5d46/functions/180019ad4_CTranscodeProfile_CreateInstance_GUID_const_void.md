# CTranscodeProfile::CreateInstance(_GUID const &,void * *)

- ea: `0x180019ad4`
- end: `0x180019d9d`
- name: `?CreateInstance@CTranscodeProfile@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `713`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180012420`
- `0x18001c050`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180017074`
- `0x1800189a4`
- `0x180019ad4`
- `0x18001a330`
- `0x18001b350`
- `0x18001c280`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019b1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019c33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019ce9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019b1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019c33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019ce9`

## string_xrefs

- `0x180019ae9`: `CTranscodeProfile::CreateInstance`
- `0x180019b71`: `CTranscodeProfile::CreateInstance`
- `0x180019c8a`: `CTranscodeProfile::CreateInstance`
- `0x180019d40`: `CTranscodeProfile::CreateInstance`

## pseudocode

```c
__int64 __fastcall CTranscodeProfile::CreateInstance(const struct _GUID *a1, void **a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  int Interface; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // rdi
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v17; // edx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  char v22; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CTranscodeProfile::CreateInstance", 253);
  if ( a2 )
  {
    *a2 = 0;
    v10 = operator new(0x30u);
    v12 = v10;
    if ( v10 )
    {
      *v10 = &CTranscodeProfile::`vftable'{for `IMFTranscodeProfile'};
      v10[1] = &CTranscodeProfile::`vftable'{for `IPersistStream'};
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CTranscodeProfile::CTranscodeProfile", 276);
      *((_DWORD *)v12 + 4) = 0;
      v12[3] = 0;
      v12[4] = 0;
      v12[5] = 0;
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
      Interface = CTranscodeProfile::QueryInterface((CTranscodeProfile *)v12, a1, a2);
      if ( Interface < 0 )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != Interface )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeProfile::CreateInstance", 265, Interface);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            WPP_60c454de96f7327ebad2115a8fee1984_Traceguids,
            0,
            Interface);
        CTranscodeProfile::`scalar deleting destructor'((CTranscodeProfile *)v12, v17);
      }
    }
    else
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      Interface = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v20, "CTranscodeProfile::CreateInstance", 263, -2147024882);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 30;
        goto LABEL_35;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    Interface = -2147467261;
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
        CallStackContext::TraceFailure(v8, "CTranscodeProfile::CreateInstance", 258, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 29;
LABEL_35:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, 0, Interface);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180019ad4  mov     [rsp+arg_0], rbx
0x180019ad9  mov     [rsp+arg_10], rsi
0x180019ade  push    rdi
0x180019adf  sub     rsp, 30h
0x180019ae3  mov     rbx, rdx
0x180019ae6  mov     rsi, rcx
0x180019ae9  lea     rdx, aCtranscodeprof; "CTranscodeProfile::CreateInstance"
0x180019af0  mov     r8d, 0FDh; int
0x180019af6  lea     rcx, [rsp+38h+arg_8]; this
0x180019afb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180019b00  test    rbx, rbx
0x180019b03  jnz     loc_180019B9D
0x180019b09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019b10  mov     ebx, 80004003h
0x180019b15  test    rcx, rcx
0x180019b18  jnz     short loc_180019B5B
0x180019b1a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019b20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019b27  mov     rcx, rax
0x180019b2a  test    rax, rax
0x180019b2d  jz      short loc_180019B4D
0x180019b2f  mov     rax, [rax]
0x180019b32  mov     edx, 7F0h
0x180019b37  mov     rax, [rax+8]
0x180019b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b40  test    eax, eax
0x180019b42  jz      short loc_180019B4D
0x180019b44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019b4b  jmp     short loc_180019B5B
0x180019b4d  lea     rcx, qword_180069A90; this
0x180019b54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019b5b  cmp     byte ptr [rcx+8], 0
0x180019b5f  jz      short loc_180019B86
0x180019b61  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019b66  cmp     [rax+7CCh], ebx
0x180019b6c  jz      short loc_180019B86
0x180019b6e  mov     r9d, ebx; int
0x180019b71  lea     rdx, aCtranscodeprof; "CTranscodeProfile::CreateInstance"
0x180019b78  mov     r8d, 102h; int
0x180019b7e  mov     rcx, rax; this
0x180019b81  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019b86  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019b8b  cmp     al, 1
0x180019b8d  jb      loc_180019D81
0x180019b93  mov     edx, 1Dh
0x180019b98  jmp     loc_180019D63
0x180019b9d  mov     ecx, 30h ; '0'; Size
0x180019ba2  mov     qword ptr [rbx], 0
0x180019ba9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019bae  mov     rdi, rax
0x180019bb1  test    rax, rax
0x180019bb4  jz      loc_180019CD8
0x180019bba  lea     rax, ??_7CTranscodeProfile@@6BIMFTranscodeProfile@@@; const CTranscodeProfile::`vftable'{for `IMFTranscodeProfile'}
0x180019bc1  mov     r8d, 114h; int
0x180019bc7  mov     [rdi], rax
0x180019bca  lea     rdx, aCtranscodeprof_22; "CTranscodeProfile::CTranscodeProfile"
0x180019bd1  lea     rax, ??_7CTranscodeProfile@@6BIPersistStream@@@; const CTranscodeProfile::`vftable'{for `IPersistStream'}
0x180019bd8  lea     rcx, [rsp+38h+arg_8]; this
0x180019bdd  mov     [rdi+8], rax
0x180019be1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180019be6  mov     dword ptr [rdi+10h], 0
0x180019bed  mov     qword ptr [rdi+18h], 0
0x180019bf5  mov     qword ptr [rdi+20h], 0
0x180019bfd  mov     qword ptr [rdi+28h], 0
0x180019c05  lea     rcx, [rsp+38h+arg_8]; this
0x180019c0a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180019c0f  mov     r8, rbx; void **
0x180019c12  mov     rdx, rsi; struct _GUID *
0x180019c15  mov     rcx, rdi; this
0x180019c18  call    ?QueryInterface@CTranscodeProfile@@UEAAJAEBU_GUID@@PEAPEAX@Z; CTranscodeProfile::QueryInterface(_GUID const &,void * *)
0x180019c1d  mov     ebx, eax
0x180019c1f  test    eax, eax
0x180019c21  jns     loc_180019D81
0x180019c27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c2e  test    rcx, rcx
0x180019c31  jnz     short loc_180019C74
0x180019c33  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019c39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c40  mov     rcx, rax
0x180019c43  test    rax, rax
0x180019c46  jz      short loc_180019C66
0x180019c48  mov     rax, [rax]
0x180019c4b  mov     edx, 7F0h
0x180019c50  mov     rax, [rax+8]
0x180019c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c59  test    eax, eax
0x180019c5b  jz      short loc_180019C66
0x180019c5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c64  jmp     short loc_180019C74
0x180019c66  lea     rcx, qword_180069A90; this
0x180019c6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c74  cmp     byte ptr [rcx+8], 0
0x180019c78  jz      short loc_180019C9F
0x180019c7a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019c7f  cmp     [rax+7CCh], ebx
0x180019c85  jz      short loc_180019C9F
0x180019c87  mov     r9d, ebx; int
0x180019c8a  lea     rdx, aCtranscodeprof; "CTranscodeProfile::CreateInstance"
0x180019c91  mov     r8d, 109h; int
0x180019c97  mov     rcx, rax; this
0x180019c9a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019c9f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019ca4  cmp     al, 1
0x180019ca6  jb      short loc_180019CCB
0x180019ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180019caf  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x180019cb6  mov     edx, 1Fh
0x180019cbb  mov     [rsp+38h+var_18], ebx
0x180019cbf  xor     r9d, r9d
0x180019cc2  mov     rcx, [rcx+10h]
0x180019cc6  call    WPP_SF_qd
0x180019ccb  mov     rcx, rdi; this
0x180019cce  call    ??_GCTranscodeProfile@@QEAAPEAXI@Z; CTranscodeProfile::`scalar deleting destructor'(uint)
0x180019cd3  jmp     loc_180019D81
0x180019cd8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019cdf  mov     ebx, 8007000Eh
0x180019ce4  test    rcx, rcx
0x180019ce7  jnz     short loc_180019D2A
0x180019ce9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019cef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019cf6  mov     rcx, rax
0x180019cf9  test    rax, rax
0x180019cfc  jz      short loc_180019D1C
0x180019cfe  mov     rax, [rax]
0x180019d01  mov     edx, 7F0h
0x180019d06  mov     rax, [rax+8]
0x180019d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d0f  test    eax, eax
0x180019d11  jz      short loc_180019D1C
0x180019d13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019d1a  jmp     short loc_180019D2A
0x180019d1c  lea     rcx, qword_180069A90; this
0x180019d23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019d2a  cmp     byte ptr [rcx+8], 0
0x180019d2e  jz      short loc_180019D55
0x180019d30  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019d35  cmp     [rax+7CCh], ebx
0x180019d3b  jz      short loc_180019D55
0x180019d3d  mov     r9d, ebx; int
0x180019d40  lea     rdx, aCtranscodeprof; "CTranscodeProfile::CreateInstance"
0x180019d47  mov     r8d, 107h; int
0x180019d4d  mov     rcx, rax; this
0x180019d50  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019d55  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019d5a  cmp     al, 1
0x180019d5c  jb      short loc_180019D81
0x180019d5e  mov     edx, 1Eh
0x180019d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d6a  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x180019d71  xor     r9d, r9d
0x180019d74  mov     [rsp+38h+var_18], ebx
0x180019d78  mov     rcx, [rcx+10h]
0x180019d7c  call    WPP_SF_qd
0x180019d81  lea     rcx, [rsp+38h+arg_8]; this
0x180019d86  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180019d8b  mov     rsi, [rsp+38h+arg_10]
0x180019d90  mov     eax, ebx
0x180019d92  mov     rbx, [rsp+38h+arg_0]
0x180019d97  add     rsp, 30h
0x180019d9b  pop     rdi
0x180019d9c  retn
```
