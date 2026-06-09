# CWMPropTranslator::AddLanguage(ushort const *,ushort *)

- ea: `0x180014e14`
- end: `0x1800153a6`
- name: `?AddLanguage@CWMPropTranslator@@AEAAJPEBGPEAG@Z`
- size: `1426`
- prototype: `__int64 __fastcall(CWMPropTranslator *this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180048310`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800085a0`
- `0x180014e14`
- `0x18001a330`
- `0x18001c280`
- `0x1800469b0`
- `0x180048ca4`
- `0x180048d18`
- `0x180048d88`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001507e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001507e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015374`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015374`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014eea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014f56`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014fa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800150a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001516a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800152bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014f56`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014fa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800150a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001516a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800152bc`

## pseudocode

```c
__int64 __fastcall CWMPropTranslator::AddLanguage(
        CWMPropTranslator *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  PROPVARIANT *v4; // rcx
  _QWORD *v7; // rdi
  __int64 v8; // rdx
  void *v9; // rcx
  int v10; // ebx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  CallStackTracing *v15; // rcx
  CallStackTracing *v16; // rax
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v20; // rdx
  int v21; // ecx
  __int64 v22; // rdx
  void *v23; // r9
  LPVOID v24; // rax
  CallStackTracing *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  CallStackTracing *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  CallStackTracing *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  PROPVARIANT *pvar; // [rsp+30h] [rbp-10h]
  SIZE_T cb; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int64 v41; // [rsp+98h] [rbp+58h] BYREF

  v41 = 0;
  v4 = (PROPVARIANT *)((char *)this + 784);
  pvar = v4;
  if ( !v4->vt )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&cb, "CWMPropTranslator::AddLanguage", 864);
    cb = 0;
    v7 = (_QWORD *)((char *)this + 800);
    *((_QWORD *)this + 100) = 0;
    v10 = ULongLongMult(1u, 8u, &cb);
    if ( v10 >= 0 )
    {
      v10 = CTCoAllocPolicy::Alloc(v9, 1u, cb, (void **)this + 100);
      if ( v10 >= 0 )
      {
        *((_WORD *)this + 392) = 4127;
        *((_DWORD *)this + 198) = 0;
        goto LABEL_5;
      }
    }
    v17 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v17);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMPropTranslator::AddLanguage", 864, v10);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
LABEL_59:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
LABEL_60:
      if ( v10 >= 0 )
        return (unsigned int)v10;
      goto LABEL_73;
    }
    v20 = 57;
LABEL_58:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids, this, v10);
    goto LABEL_59;
  }
  if ( v4->vt != 4127 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&cb, "CWMPropTranslator::AddLanguage", 875);
    v35 = CallStackTracing::s_wpInstance;
    v10 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
      CallStackTracing::s_wpInstance = v36;
      if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
      {
        v35 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v35 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v35 + 8) )
    {
      v37 = CallStackTracing::GetThreadRelativeContext(v35);
      if ( *((_DWORD *)v37 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v37, "CWMPropTranslator::AddLanguage", 875, -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids,
        this,
        -2147418113);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
    v7 = (_QWORD *)((char *)this + 800);
    goto LABEL_73;
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&cb, "CWMPropTranslator::AddLanguage", 870);
  v21 = *((_DWORD *)this + 198);
  v7 = (_QWORD *)((char *)this + 800);
  *((_QWORD *)this + 100) = 0;
  cb = 0;
  v10 = ULongLongMult((unsigned int)(v21 + 1), 8u, &cb);
  if ( v10 < 0 )
  {
LABEL_27:
    v25 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v25 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v25 + 8) )
    {
      v33 = CallStackTracing::GetThreadRelativeContext(v25);
      if ( *((_DWORD *)v33 + 499) != v10 )
        CallStackContext::TraceFailure(v33, "CWMPropTranslator::AddLanguage", 870, v10);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_59;
    v20 = 58;
    goto LABEL_58;
  }
  v24 = CoTaskMemRealloc(v23, cb);
  *v7 = v24;
  if ( !v24 )
  {
    v10 = -2147024882;
    goto LABEL_27;
  }
LABEL_5:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
  v10 = StringCbLengthW(a2, 0x104u, &v41);
  if ( v10 < 0 )
  {
LABEL_50:
    *a3 = *((_WORD *)this + 396) - 1;
    goto LABEL_60;
  }
  v11 = v41;
  *(_QWORD *)(*v7 + 8LL * *((unsigned int *)this + 198)) = CoTaskMemAlloc(v41 + 2);
  v12 = *(unsigned __int16 **)(*v7 + 8LL * *((unsigned int *)this + 198));
  if ( !v12 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&cb, "CWMPropTranslator::AddLanguage", 897);
    v30 = CallStackTracing::s_wpInstance;
    v10 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
      {
        v30 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v30 = (CallStackTracing *)&qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext(v30);
      if ( *((_DWORD *)v32 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v32, "CWMPropTranslator::AddLanguage", 897, -2147024882);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_49;
    v28 = 61;
    goto LABEL_48;
  }
  v13 = StringCbCopyW(v12, v11 + 2, a2);
  ++*((_DWORD *)this + 198);
  v10 = v13;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&cb, "CWMPropTranslator::AddLanguage", 893);
  if ( v10 >= 0 )
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
    goto LABEL_50;
  }
  v15 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = (CallStackTracing *)&qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v27 = CallStackTracing::GetThreadRelativeContext(v15);
    if ( *((_DWORD *)v27 + 499) != v10 )
      CallStackContext::TraceFailure(v27, "CWMPropTranslator::AddLanguage", 893, v10);
  }
  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    goto LABEL_49;
  v28 = 60;
LABEL_48:
  WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids, this, v10);
LABEL_49:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
LABEL_73:
  if ( *((_DWORD *)this + 198) )
  {
    CMFPropVariant::Clear(pvar);
  }
  else
  {
    CoTaskMemFree(pvar->bstrblobVal.pData);
    *v7 = 0;
    pvar->vt = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180014e14  mov     [rsp-38h+arg_8], rbx
0x180014e19  push    rbp
0x180014e1a  push    rsi
0x180014e1b  push    rdi
0x180014e1c  push    r12
0x180014e1e  push    r13
0x180014e20  push    r14
0x180014e22  push    r15
0x180014e24  mov     rbp, rsp
0x180014e27  sub     rsp, 40h
0x180014e2b  xor     ebx, ebx
0x180014e2d  lea     r15, aCwmproptransla_9; "CWMPropTranslator::AddLanguage"
0x180014e34  mov     rsi, rcx
0x180014e37  mov     [rbp+arg_18], rbx
0x180014e3b  add     rcx, 310h
0x180014e42  mov     r12, rdx
0x180014e45  mov     r13, r8
0x180014e48  mov     [rbp+pvar], rcx
0x180014e4c  mov     rdx, r15; char *
0x180014e4f  cmp     [rcx], bx
0x180014e52  jnz     loc_180015027
0x180014e58  mov     r8d, 360h; int
0x180014e5e  lea     rcx, [rbp+cb]; this
0x180014e62  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180014e67  lea     r14d, [rbx+1]
0x180014e6b  mov     [rbp+cb], rbx
0x180014e6f  lea     rdi, [rsi+320h]
0x180014e76  mov     ecx, r14d; unsigned __int64
0x180014e79  lea     r8, [rbp+cb]; unsigned __int64 *
0x180014e7d  mov     [rdi], rbx
0x180014e80  lea     edx, [rbx+8]; unsigned __int64
0x180014e83  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180014e88  mov     ebx, eax
0x180014e8a  test    eax, eax
0x180014e8c  js      loc_180014F94
0x180014e92  mov     r8, [rbp+cb]; unsigned __int64
0x180014e96  mov     r9, rdi; void **
0x180014e99  mov     edx, r14d; unsigned int
0x180014e9c  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180014ea1  mov     ebx, eax
0x180014ea3  test    eax, eax
0x180014ea5  js      loc_180014F94
0x180014eab  mov     word ptr [rsi+310h], 101Fh
0x180014eb4  mov     dword ptr [rsi+318h], 0
0x180014ebe  lea     rcx, [rbp+cb]; this
0x180014ec2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180014ec7  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x180014ecb  mov     edx, 104h; unsigned __int64
0x180014ed0  mov     rcx, r12; unsigned __int16 *
0x180014ed3  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180014ed8  mov     ebx, eax
0x180014eda  test    eax, eax
0x180014edc  js      loc_18001520A
0x180014ee2  mov     rbx, [rbp+arg_18]
0x180014ee6  lea     rcx, [rbx+2]; cb
0x180014eea  call    cs:__imp_CoTaskMemAlloc
0x180014ef0  mov     rcx, [rdi]
0x180014ef3  mov     r8d, [rsi+318h]
0x180014efa  mov     [rcx+r8*8], rax
0x180014efe  mov     ecx, [rsi+318h]
0x180014f04  mov     rax, [rdi]
0x180014f07  mov     rcx, [rax+rcx*8]; unsigned __int16 *
0x180014f0b  test    rcx, rcx
0x180014f0e  jz      loc_180015141
0x180014f14  mov     r8, r12; unsigned __int16 *
0x180014f17  lea     rdx, [rbx+2]; unsigned __int64
0x180014f1b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180014f20  add     [rsi+318h], r14d
0x180014f27  lea     rcx, [rbp+cb]; this
0x180014f2b  mov     r8d, 37Dh; int
0x180014f31  mov     rdx, r15; char *
0x180014f34  mov     ebx, eax
0x180014f36  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180014f3b  xor     r12d, r12d
0x180014f3e  test    ebx, ebx
0x180014f40  jns     loc_180015133
0x180014f46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014f4d  test    rcx, rcx
0x180014f50  jnz     loc_1800150F4
0x180014f56  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014f5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014f63  mov     rcx, rax
0x180014f66  test    rax, rax
0x180014f69  jz      loc_1800150E6
0x180014f6f  mov     rax, [rax]
0x180014f72  mov     edx, 7F0h
0x180014f77  mov     rax, [rax+8]
0x180014f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f80  test    eax, eax
0x180014f82  jz      loc_1800150E6
0x180014f88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014f8f  jmp     loc_1800150F4
0x180014f94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014f9b  xor     r12d, r12d
0x180014f9e  test    rcx, rcx
0x180014fa1  jnz     short loc_180014FE4
0x180014fa3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014fa9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014fb0  mov     rcx, rax
0x180014fb3  test    rax, rax
0x180014fb6  jz      short loc_180014FD6
0x180014fb8  mov     rax, [rax]
0x180014fbb  mov     edx, 7F0h
0x180014fc0  mov     rax, [rax+8]
0x180014fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fc9  test    eax, eax
0x180014fcb  jz      short loc_180014FD6
0x180014fcd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014fd4  jmp     short loc_180014FE4
0x180014fd6  lea     rcx, qword_180069A90; this
0x180014fdd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180014fe4  cmp     [rcx+8], r12b
0x180014fe8  jz      short loc_18001500F
0x180014fea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180014fef  test    ebx, ebx
0x180014ff1  jns     short loc_18001500F
0x180014ff3  cmp     [rax+7CCh], ebx
0x180014ff9  jz      short loc_18001500F
0x180014ffb  mov     r9d, ebx; int
0x180014ffe  mov     r8d, 360h; int
0x180015004  mov     rdx, r15; char *
0x180015007  mov     rcx, rax; this
0x18001500a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001500f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180015014  cmp     al, r14b
0x180015017  jb      loc_180015285
0x18001501d  mov     edx, 39h ; '9'
0x180015022  jmp     loc_180015267
0x180015027  mov     eax, 101Fh
0x18001502c  cmp     [rcx], ax
0x18001502f  lea     rcx, [rbp+cb]; this
0x180015033  jnz     loc_18001529B
0x180015039  mov     r8d, 366h; int
0x18001503f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015044  mov     ecx, [rsi+318h]
0x18001504a  lea     rdi, [rsi+320h]
0x180015051  mov     r9, [rdi]
0x180015054  lea     r8, [rbp+cb]; unsigned __int64 *
0x180015058  mov     r14d, 1
0x18001505e  mov     [rdi], rbx
0x180015061  add     ecx, r14d; unsigned __int64
0x180015064  mov     [rbp+cb], rbx
0x180015068  lea     edx, [r14+7]; unsigned __int64
0x18001506c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180015071  mov     ebx, eax
0x180015073  test    eax, eax
0x180015075  js      short loc_180015095
0x180015077  mov     rdx, [rbp+cb]; cb
0x18001507b  mov     rcx, r9; pv
0x18001507e  call    cs:__imp_CoTaskMemRealloc
0x180015084  mov     [rdi], rax
0x180015087  test    rax, rax
0x18001508a  jnz     loc_180014EBE
0x180015090  mov     ebx, 8007000Eh
0x180015095  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001509c  xor     r12d, r12d
0x18001509f  test    rcx, rcx
0x1800150a2  jnz     loc_18001522D
0x1800150a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800150ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800150b5  mov     rcx, rax
0x1800150b8  test    rax, rax
0x1800150bb  jz      loc_18001521F
0x1800150c1  mov     rax, [rax]
0x1800150c4  mov     edx, 7F0h
0x1800150c9  mov     rax, [rax+8]
0x1800150cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150d2  test    eax, eax
0x1800150d4  jz      loc_18001521F
0x1800150da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800150e1  jmp     loc_18001522D
0x1800150e6  lea     rcx, qword_180069A90; this
0x1800150ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800150f4  cmp     [rcx+8], r12b
0x1800150f8  jz      short loc_18001511B
0x1800150fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800150ff  cmp     [rax+7CCh], ebx
0x180015105  jz      short loc_18001511B
0x180015107  mov     r9d, ebx; int
0x18001510a  mov     r8d, 37Dh; int
0x180015110  mov     rdx, r15; char *
0x180015113  mov     rcx, rax; this
0x180015116  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001511b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180015120  cmp     al, r14b
0x180015123  jb      loc_1800151FC
0x180015129  mov     edx, 3Ch ; '<'
0x18001512e  jmp     loc_1800151DE
0x180015133  lea     rcx, [rbp+cb]; this
0x180015137  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001513c  jmp     loc_18001520D
0x180015141  mov     r13d, 381h
0x180015147  lea     rcx, [rbp+cb]; this
0x18001514b  mov     r8d, r13d; int
0x18001514e  mov     rdx, r15; char *
0x180015151  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015156  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001515d  xor     r12d, r12d
0x180015160  mov     ebx, 8007000Eh
0x180015165  test    rcx, rcx
0x180015168  jnz     short loc_1800151AB
0x18001516a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015170  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015177  mov     rcx, rax
0x18001517a  test    rax, rax
0x18001517d  jz      short loc_18001519D
0x18001517f  mov     rax, [rax]
0x180015182  mov     edx, 7F0h
0x180015187  mov     rax, [rax+8]
0x18001518b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015190  test    eax, eax
0x180015192  jz      short loc_18001519D
0x180015194  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001519b  jmp     short loc_1800151AB
0x18001519d  lea     rcx, qword_180069A90; this
0x1800151a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800151ab  cmp     [rcx+8], r12b
0x1800151af  jz      short loc_1800151CF
0x1800151b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800151b6  cmp     [rax+7CCh], ebx
0x1800151bc  jz      short loc_1800151CF
0x1800151be  mov     r9d, ebx; int
0x1800151c1  mov     r8d, r13d; int
0x1800151c4  mov     rdx, r15; char *
0x1800151c7  mov     rcx, rax; this
0x1800151ca  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800151cf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800151d4  cmp     al, r14b
0x1800151d7  jb      short loc_1800151FC
0x1800151d9  mov     edx, 3Dh ; '='
0x1800151de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151e5  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x1800151ec  mov     r9, rsi
0x1800151ef  mov     [rsp+40h+var_20], ebx
0x1800151f3  mov     rcx, [rcx+10h]
0x1800151f7  call    WPP_SF_qd
0x1800151fc  lea     rcx, [rbp+cb]; this
0x180015200  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180015205  jmp     loc_180015363
0x18001520a  xor     r12d, r12d
0x18001520d  movzx   eax, word ptr [rsi+318h]
0x180015214  sub     ax, r14w
0x180015218  mov     [r13+0], ax
0x18001521d  jmp     short loc_18001528E
0x18001521f  lea     rcx, qword_180069A90; this
0x180015226  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001522d  cmp     [rcx+8], r12b
0x180015231  jz      short loc_180015258
0x180015233  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015238  test    ebx, ebx
0x18001523a  jns     short loc_180015258
0x18001523c  cmp     [rax+7CCh], ebx
0x180015242  jz      short loc_180015258
0x180015244  mov     r9d, ebx; int
0x180015247  mov     r8d, 366h; int
0x18001524d  mov     rdx, r15; char *
0x180015250  mov     rcx, rax; this
0x180015253  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015258  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001525d  cmp     al, r14b
0x180015260  jb      short loc_180015285
0x180015262  mov     edx, 3Ah ; ':'
0x180015267  mov     rcx, cs:WPP_GLOBAL_Control
0x18001526e  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x180015275  mov     r9, rsi
0x180015278  mov     [rsp+40h+var_20], ebx
0x18001527c  mov     rcx, [rcx+10h]
0x180015280  call    WPP_SF_qd
0x180015285  lea     rcx, [rbp+cb]; this
0x180015289  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001528e  test    ebx, ebx
0x180015290  jns     loc_18001538C
0x180015296  jmp     loc_180015363
0x18001529b  mov     edi, 36Bh
0x1800152a0  mov     r8d, edi; int
0x1800152a3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800152a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800152af  xor     r12d, r12d
0x1800152b2  mov     ebx, 8000FFFFh
0x1800152b7  test    rcx, rcx
0x1800152ba  jnz     short loc_1800152FD
0x1800152bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800152c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800152c9  mov     rcx, rax
0x1800152cc  test    rax, rax
0x1800152cf  jz      short loc_1800152EF
0x1800152d1  mov     rax, [rax]
0x1800152d4  mov     edx, 7F0h
0x1800152d9  mov     rax, [rax+8]
0x1800152dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152e2  test    eax, eax
0x1800152e4  jz      short loc_1800152EF
0x1800152e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800152ed  jmp     short loc_1800152FD
0x1800152ef  lea     rcx, qword_180069A90; this
0x1800152f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800152fd  cmp     [rcx+8], r12b
0x180015301  jz      short loc_180015321
0x180015303  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015308  cmp     [rax+7CCh], ebx
  ... truncated ...
```
