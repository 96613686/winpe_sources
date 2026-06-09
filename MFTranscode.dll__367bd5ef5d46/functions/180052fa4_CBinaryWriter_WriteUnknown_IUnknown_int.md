# CBinaryWriter::WriteUnknown(IUnknown *,int)

- ea: `0x180052fa4`
- end: `0x1800533d5`
- name: `?WriteUnknown@CBinaryWriter@@QEAAJPEAUIUnknown@@H@Z`
- size: `1073`
- prototype: `__int64 __fastcall(CBinaryWriter *__hidden this, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180033df0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180050750`
- `0x180052f78`
- `0x180052fa4`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053045`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800530f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053197`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053238`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800532fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053045`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800530f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053197`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053238`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800532fc`

## string_xrefs

- `0x180052fc5`: `CBinaryWriter::WriteUnknown`

## pseudocode

```c
__int64 __fastcall CBinaryWriter::WriteUnknown(CBinaryWriter *this, struct IUnknown *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 (__fastcall *v22)(__int64, __int64, __int64); // rbx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v29[8]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v30; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID v31; // [rsp+40h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v29, "CBinaryWriter::WriteUnknown", 49);
  v30 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    goto LABEL_63;
  }
  if ( (*(__int64 (__fastcall **)(CBinaryWriter *))(*(_QWORD *)this + 8LL))(this) )
  {
    v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IPersistStream,
           &v30);
    if ( v4 >= 0 )
    {
      v31 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v30 + 24LL))(v30, &v31);
      if ( v4 >= 0 )
      {
        v4 = CBinaryWriter::WriteBool(this, 1);
        if ( v4 >= 0 )
        {
          v4 = CBinaryReader::ReadGuid(this, &v31);
          if ( v4 >= 0 )
          {
            v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v30 + 48LL);
            v23 = (*(__int64 (__fastcall **)(CBinaryWriter *))(*(_QWORD *)this + 8LL))(this);
            v4 = v22(v30, v23, 1);
            if ( v4 >= 0 )
              goto LABEL_61;
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
              {
                v25 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v25 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v25 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CBinaryWriter::WriteUnknown", 88, v4);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_61;
            v9 = 15;
          }
          else
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
              CallStackTracing::s_wpInstance = v20;
              if ( v20
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
              {
                v19 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v19 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v19 + 8) )
            {
              v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
              if ( *((_DWORD *)v21 + 499) != v4 )
                CallStackContext::TraceFailure(v21, "CBinaryWriter::WriteUnknown", 85, v4);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_61;
            v9 = 14;
          }
        }
        else
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
            CallStackTracing::s_wpInstance = v16;
            if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
            {
              v15 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v15 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v15 + 8) )
          {
            v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
            if ( *((_DWORD *)v17 + 499) != v4 )
              CallStackContext::TraceFailure(v17, "CBinaryWriter::WriteUnknown", 83, v4);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_61;
          v9 = 13;
        }
      }
      else
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
          CallStackTracing::s_wpInstance = v12;
          if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
          {
            v11 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v13 + 499) != v4 )
            CallStackContext::TraceFailure(v13, "CBinaryWriter::WriteUnknown", 81, v4);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_61;
        v9 = 12;
      }
    }
    else
    {
      v6 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
        CallStackTracing::s_wpInstance = v7;
        if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
        {
          v6 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v6 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v6 + 8) )
      {
        v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
        if ( *((_DWORD *)v8 + 499) != v4 )
          CallStackContext::TraceFailure(v8, "CBinaryWriter::WriteUnknown", 75, v4);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_61;
      v9 = 11;
    }
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids, this, v4);
  }
  else
  {
    v4 = -2147467261;
  }
LABEL_61:
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
LABEL_63:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v29);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180052fa4  mov     [rsp-18h+arg_10], rbx
0x180052fa9  push    rbp
0x180052faa  push    rdi
0x180052fab  push    r14
0x180052fad  mov     rbp, rsp
0x180052fb0  sub     rsp, 60h
0x180052fb4  mov     rax, cs:__security_cookie
0x180052fbb  xor     rax, rsp
0x180052fbe  mov     [rbp+var_10], rax
0x180052fc2  mov     rbx, rdx
0x180052fc5  lea     r14, aCbinarywriterW; "CBinaryWriter::WriteUnknown"
0x180052fcc  mov     rdi, rcx
0x180052fcf  mov     rdx, r14; char *
0x180052fd2  mov     r8d, 31h ; '1'; int
0x180052fd8  lea     rcx, [rbp+var_30]; this
0x180052fdc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052fe1  mov     [rbp+var_28], 0
0x180052fe9  test    rbx, rbx
0x180052fec  jnz     short loc_180052FF8
0x180052fee  mov     ebx, 80070057h
0x180052ff3  jmp     loc_1800533AD
0x180052ff8  mov     rax, [rdi]
0x180052ffb  mov     rcx, rdi
0x180052ffe  mov     rax, [rax+8]
0x180053002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053007  test    rax, rax
0x18005300a  jnz     short loc_180053016
0x18005300c  mov     ebx, 80004003h
0x180053011  jmp     loc_180053390
0x180053016  mov     rax, [rbx]
0x180053019  lea     r8, [rbp+var_28]
0x18005301d  lea     rdx, IID_IPersistStream
0x180053024  mov     rcx, rbx
0x180053027  mov     rax, [rax]
0x18005302a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005302f  mov     ebx, eax
0x180053031  test    eax, eax
0x180053033  jns     loc_1800530C4
0x180053039  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053040  test    rcx, rcx
0x180053043  jnz     short loc_180053086
0x180053045  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005304b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053052  mov     rcx, rax
0x180053055  test    rax, rax
0x180053058  jz      short loc_180053078
0x18005305a  mov     rax, [rax]
0x18005305d  mov     edx, 7F0h
0x180053062  mov     rax, [rax+8]
0x180053066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005306b  test    eax, eax
0x18005306d  jz      short loc_180053078
0x18005306f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053076  jmp     short loc_180053086
0x180053078  lea     rcx, qword_180069A90; this
0x18005307f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053086  cmp     byte ptr [rcx+8], 0
0x18005308a  jz      short loc_1800530AD
0x18005308c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053091  cmp     [rax+7CCh], ebx
0x180053097  jz      short loc_1800530AD
0x180053099  mov     r9d, ebx; int
0x18005309c  mov     r8d, 4Bh ; 'K'; int
0x1800530a2  mov     rdx, r14; char *
0x1800530a5  mov     rcx, rax; this
0x1800530a8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800530ad  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800530b2  cmp     al, 1
0x1800530b4  jb      loc_180053390
0x1800530ba  mov     edx, 0Bh
0x1800530bf  jmp     loc_180053372
0x1800530c4  mov     rcx, [rbp+var_28]
0x1800530c8  lea     rdx, [rbp+var_20]
0x1800530cc  xorps   xmm0, xmm0
0x1800530cf  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x1800530d3  mov     rax, [rcx]
0x1800530d6  mov     rax, [rax+18h]
0x1800530da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530df  mov     ebx, eax
0x1800530e1  test    eax, eax
0x1800530e3  jns     loc_180053174
0x1800530e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800530f0  test    rcx, rcx
0x1800530f3  jnz     short loc_180053136
0x1800530f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800530fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053102  mov     rcx, rax
0x180053105  test    rax, rax
0x180053108  jz      short loc_180053128
0x18005310a  mov     rax, [rax]
0x18005310d  mov     edx, 7F0h
0x180053112  mov     rax, [rax+8]
0x180053116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005311b  test    eax, eax
0x18005311d  jz      short loc_180053128
0x18005311f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053126  jmp     short loc_180053136
0x180053128  lea     rcx, qword_180069A90; this
0x18005312f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053136  cmp     byte ptr [rcx+8], 0
0x18005313a  jz      short loc_18005315D
0x18005313c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053141  cmp     [rax+7CCh], ebx
0x180053147  jz      short loc_18005315D
0x180053149  mov     r9d, ebx; int
0x18005314c  mov     r8d, 51h ; 'Q'; int
0x180053152  mov     rdx, r14; char *
0x180053155  mov     rcx, rax; this
0x180053158  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005315d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053162  cmp     al, 1
0x180053164  jb      loc_180053390
0x18005316a  mov     edx, 0Ch
0x18005316f  jmp     loc_180053372
0x180053174  mov     edx, 1; int
0x180053179  mov     rcx, rdi; this
0x18005317c  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x180053181  mov     ebx, eax
0x180053183  test    eax, eax
0x180053185  jns     loc_180053216
0x18005318b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053192  test    rcx, rcx
0x180053195  jnz     short loc_1800531D8
0x180053197  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005319d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800531a4  mov     rcx, rax
0x1800531a7  test    rax, rax
0x1800531aa  jz      short loc_1800531CA
0x1800531ac  mov     rax, [rax]
0x1800531af  mov     edx, 7F0h
0x1800531b4  mov     rax, [rax+8]
0x1800531b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800531bd  test    eax, eax
0x1800531bf  jz      short loc_1800531CA
0x1800531c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800531c8  jmp     short loc_1800531D8
0x1800531ca  lea     rcx, qword_180069A90; this
0x1800531d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800531d8  cmp     byte ptr [rcx+8], 0
0x1800531dc  jz      short loc_1800531FF
0x1800531de  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800531e3  cmp     [rax+7CCh], ebx
0x1800531e9  jz      short loc_1800531FF
0x1800531eb  mov     r9d, ebx; int
0x1800531ee  mov     r8d, 53h ; 'S'; int
0x1800531f4  mov     rdx, r14; char *
0x1800531f7  mov     rcx, rax; this
0x1800531fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800531ff  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053204  cmp     al, 1
0x180053206  jb      loc_180053390
0x18005320c  mov     edx, 0Dh
0x180053211  jmp     loc_180053372
0x180053216  lea     rdx, [rbp+var_20]; struct _GUID *
0x18005321a  mov     rcx, rdi; this
0x18005321d  call    ?ReadGuid@CBinaryReader@@QEAAJAEAU_GUID@@@Z; CBinaryReader::ReadGuid(_GUID &)
0x180053222  mov     ebx, eax
0x180053224  test    eax, eax
0x180053226  jns     loc_1800532B7
0x18005322c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053233  test    rcx, rcx
0x180053236  jnz     short loc_180053279
0x180053238  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005323e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053245  mov     rcx, rax
0x180053248  test    rax, rax
0x18005324b  jz      short loc_18005326B
0x18005324d  mov     rax, [rax]
0x180053250  mov     edx, 7F0h
0x180053255  mov     rax, [rax+8]
0x180053259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005325e  test    eax, eax
0x180053260  jz      short loc_18005326B
0x180053262  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053269  jmp     short loc_180053279
0x18005326b  lea     rcx, qword_180069A90; this
0x180053272  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053279  cmp     byte ptr [rcx+8], 0
0x18005327d  jz      short loc_1800532A0
0x18005327f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053284  cmp     [rax+7CCh], ebx
0x18005328a  jz      short loc_1800532A0
0x18005328c  mov     r9d, ebx; int
0x18005328f  mov     r8d, 55h ; 'U'; int
0x180053295  mov     rdx, r14; char *
0x180053298  mov     rcx, rax; this
0x18005329b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800532a0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800532a5  cmp     al, 1
0x1800532a7  jb      loc_180053390
0x1800532ad  mov     edx, 0Eh
0x1800532b2  jmp     loc_180053372
0x1800532b7  mov     rax, [rbp+var_28]
0x1800532bb  mov     rcx, [rax]
0x1800532be  mov     rbx, [rcx+30h]
0x1800532c2  mov     rcx, [rdi]
0x1800532c5  mov     rax, [rcx+8]
0x1800532c9  mov     rcx, rdi
0x1800532cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532d1  mov     rcx, [rbp+var_28]
0x1800532d5  mov     rdx, rax
0x1800532d8  mov     rax, rbx
0x1800532db  mov     r8d, 1
0x1800532e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532e6  mov     ebx, eax
0x1800532e8  test    eax, eax
0x1800532ea  jns     loc_180053390
0x1800532f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800532f7  test    rcx, rcx
0x1800532fa  jnz     short loc_18005333D
0x1800532fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053302  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053309  mov     rcx, rax
0x18005330c  test    rax, rax
0x18005330f  jz      short loc_18005332F
0x180053311  mov     rax, [rax]
0x180053314  mov     edx, 7F0h
0x180053319  mov     rax, [rax+8]
0x18005331d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053322  test    eax, eax
0x180053324  jz      short loc_18005332F
0x180053326  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005332d  jmp     short loc_18005333D
0x18005332f  lea     rcx, qword_180069A90; this
0x180053336  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005333d  cmp     byte ptr [rcx+8], 0
0x180053341  jz      short loc_180053364
0x180053343  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053348  cmp     [rax+7CCh], ebx
0x18005334e  jz      short loc_180053364
0x180053350  mov     r9d, ebx; int
0x180053353  mov     r8d, 58h ; 'X'; int
0x180053359  mov     rdx, r14; char *
0x18005335c  mov     rcx, rax; this
0x18005335f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053364  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053369  cmp     al, 1
0x18005336b  jb      short loc_180053390
0x18005336d  mov     edx, 0Fh
0x180053372  mov     rcx, cs:WPP_GLOBAL_Control
0x180053379  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x180053380  mov     r9, rdi
0x180053383  mov     [rsp+60h+var_40], ebx
0x180053387  mov     rcx, [rcx+10h]
0x18005338b  call    WPP_SF_qd
0x180053390  mov     rcx, [rbp+var_28]
0x180053394  test    rcx, rcx
0x180053397  jz      short loc_1800533AD
0x180053399  mov     rax, [rcx]
0x18005339c  mov     rax, [rax+10h]
0x1800533a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533a5  mov     [rbp+var_28], 0
0x1800533ad  lea     rcx, [rbp+var_30]; this
0x1800533b1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800533b6  mov     eax, ebx
0x1800533b8  mov     rcx, [rbp+var_10]
0x1800533bc  xor     rcx, rsp; StackCookie
0x1800533bf  call    __security_check_cookie
0x1800533c4  mov     rbx, [rsp+60h+arg_10]
0x1800533cc  add     rsp, 60h
0x1800533d0  pop     r14
0x1800533d2  pop     rdi
0x1800533d3  pop     rbp
0x1800533d4  retn
```
