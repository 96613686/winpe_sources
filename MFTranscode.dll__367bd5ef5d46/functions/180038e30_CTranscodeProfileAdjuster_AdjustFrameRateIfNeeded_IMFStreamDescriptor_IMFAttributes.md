# CTranscodeProfileAdjuster::AdjustFrameRateIfNeeded(IMFStreamDescriptor *,IMFAttributes *)

- ea: `0x180038e30`
- end: `0x18003926c`
- name: `?AdjustFrameRateIfNeeded@CTranscodeProfileAdjuster@@IEAAJPEAUIMFStreamDescriptor@@PEAUIMFAttributes@@@Z`
- size: `1084`
- prototype: `__int64 __fastcall(CTranscodeProfileAdjuster *__hidden this, struct IMFStreamDescriptor *, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180039a70`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18002bb4c`
- `0x1800380b8`
- `0x180038e30`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038ea7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038f6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003901d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039173`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038ea7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038f6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003901d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039173`

## pseudocode

```c
__int64 __fastcall CTranscodeProfileAdjuster::AdjustFrameRateIfNeeded(
        CTranscodeProfileAdjuster *this,
        struct IMFStreamDescriptor *a2,
        struct IMFAttributes *a3)
{
  struct IMFStreamDescriptorVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetMediaTypeHandler)(IMFStreamDescriptor *, IMFMediaTypeHandler **); // rax
  __int64 v8; // rdx
  int v9; // ebx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  unsigned int *v22; // rdi
  __int64 v23; // rdx
  signed __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v30; // [rsp+30h] [rbp-20h] BYREF
  __int64 v31; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v32[2]; // [rsp+40h] [rbp-10h] BYREF
  char v33; // [rsp+90h] [rbp+40h] BYREF
  __int64 v34; // [rsp+98h] [rbp+48h] BYREF
  __int64 v35; // [rsp+A8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v33,
    "CTranscodeProfileAdjuster::AdjustFrameRateIfNeeded",
    770);
  lpVtbl = a2->lpVtbl;
  v34 = 0;
  v35 = 0;
  GetMediaTypeHandler = lpVtbl->GetMediaTypeHandler;
  v31 = 0;
  v30 = 0;
  v32[0] = 0;
  v9 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))GetMediaTypeHandler)(a2, &v34);
  if ( v9 >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 56LL))(v34, &v35) >= 0
      || (v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v34 + 40LL))(v34, 0, &v35), v9 >= 0) )
    {
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v35)(v35, &IID_IMFAttributes, &v31);
      if ( v9 >= 0 )
      {
        v22 = (unsigned int *)v32;
        if ( (int)MFGetAttribute2UINT32asUINT64(a3, &MF_MT_FRAME_RATE, v32, (char *)v32 + 4) < 0 )
          v22 = 0;
        if ( (int)MFGetAttribute2UINT32asUINT64(v31, &MF_MT_FRAME_RATE, &v30, (char *)&v30 + 4) < 0 )
        {
          if ( !v22 )
            goto LABEL_55;
        }
        else if ( !v22
               || (v23 = HIDWORD(*(_QWORD *)v22),
                   v24 = 1000 * (v23 * (unsigned int)v30 - HIDWORD(v30) * (unsigned __int64)*v22),
                   v24 >= -(v23 * HIDWORD(v30)))
               && v24 <= v23 * HIDWORD(v30) )
        {
          v22 = (unsigned int *)&v30;
        }
        ReduceToLowestTerms(*v22, v22[1], v22, v22 + 1);
        v9 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, unsigned __int64))a3->lpVtbl->SetUINT64)(
               a3,
               &MF_MT_FRAME_RATE,
               v22[1] | ((unsigned __int64)*v22 << 32));
        if ( v9 < 0 )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
            CallStackTracing::s_wpInstance = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v26 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v26 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CTranscodeProfileAdjuster::AdjustFrameRateIfNeeded",
                809,
                v9);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 130;
            goto LABEL_54;
          }
        }
      }
      else
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
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
          if ( *((_DWORD *)v21 + 499) != v9 )
            CallStackContext::TraceFailure(v21, "CTranscodeProfileAdjuster::AdjustFrameRateIfNeeded", 787, v9);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v13 = 129;
          goto LABEL_54;
        }
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
        if ( *((_DWORD *)v17 + 499) != v9 )
          CallStackContext::TraceFailure(v17, "CTranscodeProfileAdjuster::AdjustFrameRateIfNeeded", 784, v9);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v13 = 128;
        goto LABEL_54;
      }
    }
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v9 )
        CallStackContext::TraceFailure(v12, "CTranscodeProfileAdjuster::AdjustFrameRateIfNeeded", 780, v9);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 127;
LABEL_54:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids, this, v9);
    }
  }
LABEL_55:
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180038e30  push    rbp
0x180038e32  push    rbx
0x180038e33  push    rsi
0x180038e34  push    rdi
0x180038e35  push    r12
0x180038e37  push    r14
0x180038e39  push    r15
0x180038e3b  mov     rbp, rsp
0x180038e3e  sub     rsp, 50h
0x180038e42  mov     r14, r8
0x180038e45  lea     r12, aCtranscodeprof_0; "CTranscodeProfileAdjuster::AdjustFrameR"...
0x180038e4c  mov     rbx, rdx
0x180038e4f  mov     rsi, rcx
0x180038e52  mov     rdx, r12; char *
0x180038e55  lea     rcx, [rbp+arg_0]; this
0x180038e59  mov     r8d, 302h; int
0x180038e5f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038e64  mov     rax, [rbx]
0x180038e67  lea     rdx, [rbp+arg_8]
0x180038e6b  xor     r15d, r15d
0x180038e6e  mov     rcx, rbx
0x180038e71  mov     [rbp+arg_8], r15
0x180038e75  mov     [rbp+arg_18], r15
0x180038e79  mov     rax, [rax+110h]
0x180038e80  mov     [rbp+var_18], r15
0x180038e84  mov     [rbp+var_20], r15
0x180038e88  mov     [rbp+var_10], r15
0x180038e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e91  mov     ebx, eax
0x180038e93  test    eax, eax
0x180038e95  jns     loc_180038F26
0x180038e9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038ea2  test    rcx, rcx
0x180038ea5  jnz     short loc_180038EE8
0x180038ea7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038ead  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038eb4  mov     rcx, rax
0x180038eb7  test    rax, rax
0x180038eba  jz      short loc_180038EDA
0x180038ebc  mov     rax, [rax]
0x180038ebf  mov     edx, 7F0h
0x180038ec4  mov     rax, [rax+8]
0x180038ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ecd  test    eax, eax
0x180038ecf  jz      short loc_180038EDA
0x180038ed1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038ed8  jmp     short loc_180038EE8
0x180038eda  lea     rcx, qword_180069A90; this
0x180038ee1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038ee8  cmp     [rcx+8], r15b
0x180038eec  jz      short loc_180038F0F
0x180038eee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038ef3  cmp     [rax+7CCh], ebx
0x180038ef9  jz      short loc_180038F0F
0x180038efb  mov     r9d, ebx; int
0x180038efe  mov     r8d, 30Ch; int
0x180038f04  mov     rdx, r12; char *
0x180038f07  mov     rcx, rax; this
0x180038f0a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038f0f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180038f14  cmp     al, 1
0x180038f16  jb      loc_180039207
0x180038f1c  mov     edx, 7Fh
0x180038f21  jmp     loc_1800391E9
0x180038f26  mov     rcx, [rbp+arg_8]
0x180038f2a  lea     rdx, [rbp+arg_18]
0x180038f2e  mov     rax, [rcx]
0x180038f31  mov     rax, [rax+38h]
0x180038f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f3a  test    eax, eax
0x180038f3c  jns     loc_180038FED
0x180038f42  mov     rcx, [rbp+arg_8]
0x180038f46  lea     r8, [rbp+arg_18]
0x180038f4a  xor     edx, edx
0x180038f4c  mov     rax, [rcx]
0x180038f4f  mov     rax, [rax+28h]
0x180038f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f58  mov     ebx, eax
0x180038f5a  test    eax, eax
0x180038f5c  jns     loc_180038FED
0x180038f62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038f69  test    rcx, rcx
0x180038f6c  jnz     short loc_180038FAF
0x180038f6e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038f74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038f7b  mov     rcx, rax
0x180038f7e  test    rax, rax
0x180038f81  jz      short loc_180038FA1
0x180038f83  mov     rax, [rax]
0x180038f86  mov     edx, 7F0h
0x180038f8b  mov     rax, [rax+8]
0x180038f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f94  test    eax, eax
0x180038f96  jz      short loc_180038FA1
0x180038f98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038f9f  jmp     short loc_180038FAF
0x180038fa1  lea     rcx, qword_180069A90; this
0x180038fa8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038faf  cmp     [rcx+8], r15b
0x180038fb3  jz      short loc_180038FD6
0x180038fb5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038fba  cmp     [rax+7CCh], ebx
0x180038fc0  jz      short loc_180038FD6
0x180038fc2  mov     r9d, ebx; int
0x180038fc5  mov     r8d, 310h; int
0x180038fcb  mov     rdx, r12; char *
0x180038fce  mov     rcx, rax; this
0x180038fd1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038fd6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180038fdb  cmp     al, 1
0x180038fdd  jb      loc_180039207
0x180038fe3  mov     edx, 80h
0x180038fe8  jmp     loc_1800391E9
0x180038fed  mov     rcx, [rbp+arg_18]
0x180038ff1  lea     r8, [rbp+var_18]
0x180038ff5  lea     rdx, IID_IMFAttributes
0x180038ffc  mov     rax, [rcx]
0x180038fff  mov     rax, [rax]
0x180039002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039007  mov     ebx, eax
0x180039009  test    eax, eax
0x18003900b  jns     loc_18003909C
0x180039011  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039018  test    rcx, rcx
0x18003901b  jnz     short loc_18003905E
0x18003901d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039023  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003902a  mov     rcx, rax
0x18003902d  test    rax, rax
0x180039030  jz      short loc_180039050
0x180039032  mov     rax, [rax]
0x180039035  mov     edx, 7F0h
0x18003903a  mov     rax, [rax+8]
0x18003903e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039043  test    eax, eax
0x180039045  jz      short loc_180039050
0x180039047  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003904e  jmp     short loc_18003905E
0x180039050  lea     rcx, qword_180069A90; this
0x180039057  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003905e  cmp     [rcx+8], r15b
0x180039062  jz      short loc_180039085
0x180039064  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039069  cmp     [rax+7CCh], ebx
0x18003906f  jz      short loc_180039085
0x180039071  mov     r9d, ebx; int
0x180039074  mov     r8d, 313h; int
0x18003907a  mov     rdx, r12; char *
0x18003907d  mov     rcx, rax; this
0x180039080  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039085  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003908a  cmp     al, 1
0x18003908c  jb      loc_180039207
0x180039092  mov     edx, 81h
0x180039097  jmp     loc_1800391E9
0x18003909c  lea     r9, [rbp+var_10+4]
0x1800390a0  mov     rcx, r14
0x1800390a3  lea     r8, [rbp+var_10]
0x1800390a7  lea     rdx, MF_MT_FRAME_RATE
0x1800390ae  call    MFGetAttribute2UINT32asUINT64
0x1800390b3  mov     rcx, [rbp+var_18]
0x1800390b7  lea     rdi, [rbp+var_10]
0x1800390bb  test    eax, eax
0x1800390bd  lea     r9, [rbp+var_20+4]
0x1800390c1  lea     r8, [rbp+var_20]
0x1800390c5  lea     rdx, MF_MT_FRAME_RATE
0x1800390cc  cmovs   rdi, r15
0x1800390d0  call    MFGetAttribute2UINT32asUINT64
0x1800390d5  test    eax, eax
0x1800390d7  js      short loc_18003911C
0x1800390d9  test    rdi, rdi
0x1800390dc  jz      short loc_180039116
0x1800390de  mov     eax, dword ptr [rbp+var_20+4]
0x1800390e1  mov     ecx, [rdi]
0x1800390e3  mov     r8d, eax
0x1800390e6  mov     rdx, [rdi]
0x1800390e9  imul    rcx, rax
0x1800390ed  mov     eax, dword ptr [rbp+var_20]
0x1800390f0  shr     rdx, 20h
0x1800390f4  imul    rax, rdx
0x1800390f8  imul    r8, rdx
0x1800390fc  sub     rax, rcx
0x1800390ff  imul    rcx, rax, 3E8h
0x180039106  mov     rax, r8
0x180039109  neg     rax
0x18003910c  cmp     rcx, rax
0x18003910f  jl      short loc_180039125
0x180039111  cmp     rcx, r8
0x180039114  jg      short loc_180039125
0x180039116  lea     rdi, [rbp+var_20]
0x18003911a  jmp     short loc_180039125
0x18003911c  test    rdi, rdi
0x18003911f  jz      loc_180039207
0x180039125  mov     ecx, [rdi]; unsigned int
0x180039127  lea     rbx, [rdi+4]
0x18003912b  mov     edx, [rbx]; unsigned int
0x18003912d  mov     r9, rbx; unsigned int *
0x180039130  mov     r8, rdi; unsigned int *
0x180039133  call    ?ReduceToLowestTerms@@YAXIIPEAI0@Z; ReduceToLowestTerms(uint,uint,uint *,uint *)
0x180039138  mov     r9, [r14]
0x18003913b  lea     rdx, MF_MT_FRAME_RATE
0x180039142  mov     eax, [rbx]
0x180039144  mov     rcx, r14
0x180039147  mov     r8d, [rdi]
0x18003914a  shl     r8, 20h
0x18003914e  or      r8, rax
0x180039151  mov     rax, [r9+0B0h]
0x180039158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003915d  mov     ebx, eax
0x18003915f  test    eax, eax
0x180039161  jns     loc_180039207
0x180039167  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003916e  test    rcx, rcx
0x180039171  jnz     short loc_1800391B4
0x180039173  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180039179  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180039180  mov     rcx, rax
0x180039183  test    rax, rax
0x180039186  jz      short loc_1800391A6
0x180039188  mov     rax, [rax]
0x18003918b  mov     edx, 7F0h
0x180039190  mov     rax, [rax+8]
0x180039194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039199  test    eax, eax
0x18003919b  jz      short loc_1800391A6
0x18003919d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800391a4  jmp     short loc_1800391B4
0x1800391a6  lea     rcx, qword_180069A90; this
0x1800391ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800391b4  cmp     [rcx+8], r15b
0x1800391b8  jz      short loc_1800391DB
0x1800391ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800391bf  cmp     [rax+7CCh], ebx
0x1800391c5  jz      short loc_1800391DB
0x1800391c7  mov     r9d, ebx; int
0x1800391ca  mov     r8d, 329h; int
0x1800391d0  mov     rdx, r12; char *
0x1800391d3  mov     rcx, rax; this
0x1800391d6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800391db  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800391e0  cmp     al, 1
0x1800391e2  jb      short loc_180039207
0x1800391e4  mov     edx, 82h
0x1800391e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391f0  lea     r8, WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids
0x1800391f7  mov     r9, rsi
0x1800391fa  mov     [rsp+50h+var_30], ebx
0x1800391fe  mov     rcx, [rcx+10h]
0x180039202  call    WPP_SF_qd
0x180039207  mov     rcx, [rbp+arg_8]
0x18003920b  test    rcx, rcx
0x18003920e  jz      short loc_180039220
0x180039210  mov     rax, [rcx]
0x180039213  mov     rax, [rax+10h]
0x180039217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003921c  mov     [rbp+arg_8], r15
0x180039220  mov     rcx, [rbp+arg_18]
0x180039224  test    rcx, rcx
0x180039227  jz      short loc_180039239
0x180039229  mov     rax, [rcx]
0x18003922c  mov     rax, [rax+10h]
0x180039230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039235  mov     [rbp+arg_18], r15
0x180039239  mov     rcx, [rbp+var_18]
0x18003923d  test    rcx, rcx
0x180039240  jz      short loc_180039252
0x180039242  mov     rax, [rcx]
0x180039245  mov     rax, [rax+10h]
0x180039249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003924e  mov     [rbp+var_18], r15
0x180039252  lea     rcx, [rbp+arg_0]; this
0x180039256  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003925b  mov     eax, ebx
0x18003925d  add     rsp, 50h
0x180039261  pop     r15
0x180039263  pop     r14
0x180039265  pop     r12
0x180039267  pop     rdi
0x180039268  pop     rsi
0x180039269  pop     rbx
0x18003926a  pop     rbp
0x18003926b  retn
```
