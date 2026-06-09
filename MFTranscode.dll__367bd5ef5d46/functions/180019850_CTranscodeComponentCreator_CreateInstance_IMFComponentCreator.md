# CTranscodeComponentCreator::CreateInstance(IMFComponentCreator * *)

- ea: `0x180019850`
- end: `0x180019acb`
- name: `?CreateInstance@CTranscodeComponentCreator@@SAJPEAPEAUIMFComponentCreator@@@Z`
- size: `635`
- prototype: `__int64 __fastcall(struct IMFComponentCreator **)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001bec0`
- `0x1800332d0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180017074`
- `0x180018888`
- `0x18001897c`
- `0x180019850`
- `0x18001a330`
- `0x18001b160`
- `0x18001c280`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019890`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019966`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019a1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019890`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019966`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019a1c`

## string_xrefs

- `0x18001985d`: `CTranscodeComponentCreator::CreateInstance`
- `0x1800198e7`: `CTranscodeComponentCreator::CreateInstance`
- `0x1800199bd`: `CTranscodeComponentCreator::CreateInstance`
- `0x180019a73`: `CTranscodeComponentCreator::CreateInstance`

## pseudocode

```c
__int64 __fastcall CTranscodeComponentCreator::CreateInstance(struct IMFComponentCreator **a1)
{
  __int64 v2; // rdx
  __int64 *v3; // rcx
  int Interface; // ebx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  CTranscodeComponentCreator *v8; // rax
  __int64 v9; // rdx
  CTranscodeComponentCreator *v10; // rax
  CTranscodeComponentCreator *v11; // rdi
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v16; // edx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  char v21; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v21,
    "CTranscodeComponentCreator::CreateInstance",
    147);
  if ( a1 )
  {
    *a1 = 0;
    v8 = (CTranscodeComponentCreator *)operator new(0x10u);
    if ( v8 && (v10 = CTranscodeComponentCreator::CTranscodeComponentCreator(v8), (v11 = v10) != 0) )
    {
      Interface = CTranscodeComponentCreator::QueryInterface(v10, &IID_IMFComponentCreator, (void **)a1);
      if ( Interface < 0 )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
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
          if ( *((_DWORD *)ThreadRelativeContext + 499) != Interface )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CTranscodeComponentCreator::CreateInstance",
              154,
              Interface);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_60c454de96f7327ebad2115a8fee1984_Traceguids,
            0,
            Interface);
        CTranscodeComponentCreator::`scalar deleting destructor'(v11, v16);
      }
    }
    else
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      Interface = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v19, "CTranscodeComponentCreator::CreateInstance", 152, -2147024882);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 17;
        goto LABEL_36;
      }
    }
  }
  else
  {
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
    Interface = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v3 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v3 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)v6 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v6, "CTranscodeComponentCreator::CreateInstance", 147, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 16;
LABEL_36:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids, 0, Interface);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180019850  mov     [rsp+arg_8], rbx
0x180019855  push    rdi
0x180019856  sub     rsp, 30h
0x18001985a  mov     rbx, rcx
0x18001985d  lea     rdx, aCtranscodecomp; "CTranscodeComponentCreator::CreateInsta"...
0x180019864  mov     edi, 93h
0x180019869  lea     rcx, [rsp+38h+arg_0]; this
0x18001986e  mov     r8d, edi; int
0x180019871  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180019876  test    rbx, rbx
0x180019879  jnz     loc_180019910
0x18001987f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019886  mov     ebx, 80004003h
0x18001988b  test    rcx, rcx
0x18001988e  jnz     short loc_1800198D1
0x180019890  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019896  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001989d  mov     rcx, rax
0x1800198a0  test    rax, rax
0x1800198a3  jz      short loc_1800198C3
0x1800198a5  mov     rax, [rax]
0x1800198a8  mov     edx, 7F0h
0x1800198ad  mov     rax, [rax+8]
0x1800198b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198b6  test    eax, eax
0x1800198b8  jz      short loc_1800198C3
0x1800198ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800198c1  jmp     short loc_1800198D1
0x1800198c3  lea     rcx, qword_180069A90; this
0x1800198ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800198d1  cmp     byte ptr [rcx+8], 0
0x1800198d5  jz      short loc_1800198F9
0x1800198d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800198dc  cmp     [rax+7CCh], ebx
0x1800198e2  jz      short loc_1800198F9
0x1800198e4  mov     r9d, ebx; int
0x1800198e7  lea     rdx, aCtranscodecomp; "CTranscodeComponentCreator::CreateInsta"...
0x1800198ee  mov     r8d, edi; int
0x1800198f1  mov     rcx, rax; this
0x1800198f4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800198f9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800198fe  cmp     al, 1
0x180019900  jb      loc_180019AB4
0x180019906  mov     edx, 10h
0x18001990b  jmp     loc_180019A96
0x180019910  mov     ecx, 10h; Size
0x180019915  mov     qword ptr [rbx], 0
0x18001991c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019921  test    rax, rax
0x180019924  jz      loc_180019A0B
0x18001992a  mov     rcx, rax; this
0x18001992d  call    ??0CTranscodeComponentCreator@@IEAA@XZ; CTranscodeComponentCreator::CTranscodeComponentCreator(void)
0x180019932  mov     rdi, rax
0x180019935  test    rax, rax
0x180019938  jz      loc_180019A0B
0x18001993e  mov     r8, rbx; void **
0x180019941  lea     rdx, IID_IMFComponentCreator; struct _GUID *
0x180019948  mov     rcx, rax; this
0x18001994b  call    ?QueryInterface@CTranscodeComponentCreator@@UEAAJAEBU_GUID@@PEAPEAX@Z; CTranscodeComponentCreator::QueryInterface(_GUID const &,void * *)
0x180019950  mov     ebx, eax
0x180019952  test    eax, eax
0x180019954  jns     loc_180019AB4
0x18001995a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019961  test    rcx, rcx
0x180019964  jnz     short loc_1800199A7
0x180019966  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001996c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019973  mov     rcx, rax
0x180019976  test    rax, rax
0x180019979  jz      short loc_180019999
0x18001997b  mov     rax, [rax]
0x18001997e  mov     edx, 7F0h
0x180019983  mov     rax, [rax+8]
0x180019987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001998c  test    eax, eax
0x18001998e  jz      short loc_180019999
0x180019990  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019997  jmp     short loc_1800199A7
0x180019999  lea     rcx, qword_180069A90; this
0x1800199a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800199a7  cmp     byte ptr [rcx+8], 0
0x1800199ab  jz      short loc_1800199D2
0x1800199ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800199b2  cmp     [rax+7CCh], ebx
0x1800199b8  jz      short loc_1800199D2
0x1800199ba  mov     r9d, ebx; int
0x1800199bd  lea     rdx, aCtranscodecomp; "CTranscodeComponentCreator::CreateInsta"...
0x1800199c4  mov     r8d, 9Ah; int
0x1800199ca  mov     rcx, rax; this
0x1800199cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800199d2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800199d7  cmp     al, 1
0x1800199d9  jb      short loc_1800199FE
0x1800199db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199e2  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x1800199e9  mov     edx, 12h
0x1800199ee  mov     [rsp+38h+var_18], ebx
0x1800199f2  xor     r9d, r9d
0x1800199f5  mov     rcx, [rcx+10h]
0x1800199f9  call    WPP_SF_qd
0x1800199fe  mov     rcx, rdi; this
0x180019a01  call    ??_GCTranscodeComponentCreator@@QEAAPEAXI@Z; CTranscodeComponentCreator::`scalar deleting destructor'(uint)
0x180019a06  jmp     loc_180019AB4
0x180019a0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a12  mov     ebx, 8007000Eh
0x180019a17  test    rcx, rcx
0x180019a1a  jnz     short loc_180019A5D
0x180019a1c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019a22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a29  mov     rcx, rax
0x180019a2c  test    rax, rax
0x180019a2f  jz      short loc_180019A4F
0x180019a31  mov     rax, [rax]
0x180019a34  mov     edx, 7F0h
0x180019a39  mov     rax, [rax+8]
0x180019a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a42  test    eax, eax
0x180019a44  jz      short loc_180019A4F
0x180019a46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a4d  jmp     short loc_180019A5D
0x180019a4f  lea     rcx, qword_180069A90; this
0x180019a56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a5d  cmp     byte ptr [rcx+8], 0
0x180019a61  jz      short loc_180019A88
0x180019a63  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019a68  cmp     [rax+7CCh], ebx
0x180019a6e  jz      short loc_180019A88
0x180019a70  mov     r9d, ebx; int
0x180019a73  lea     rdx, aCtranscodecomp; "CTranscodeComponentCreator::CreateInsta"...
0x180019a7a  mov     r8d, 98h; int
0x180019a80  mov     rcx, rax; this
0x180019a83  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019a88  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180019a8d  cmp     al, 1
0x180019a8f  jb      short loc_180019AB4
0x180019a91  mov     edx, 11h
0x180019a96  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a9d  lea     r8, WPP_60c454de96f7327ebad2115a8fee1984_Traceguids
0x180019aa4  xor     r9d, r9d
0x180019aa7  mov     [rsp+38h+var_18], ebx
0x180019aab  mov     rcx, [rcx+10h]
0x180019aaf  call    WPP_SF_qd
0x180019ab4  lea     rcx, [rsp+38h+arg_0]; this
0x180019ab9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180019abe  mov     eax, ebx
0x180019ac0  mov     rbx, [rsp+38h+arg_8]
0x180019ac5  add     rsp, 30h
0x180019ac9  pop     rdi
0x180019aca  retn
```
