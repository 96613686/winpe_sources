# CWMPropTranslator::AddLanguage(ushort const *,ushort *)

- ea: `0x180207df0`
- end: `0x1802083b3`
- name: `?AddLanguage@CWMPropTranslator@@AEAAJPEBGPEAG@Z`
- size: `1475`
- prototype: `int(CWMPropTranslator *__hidden this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180241b70`

## callees

- `0x18002c9ac`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18012d968`
- `0x180207df0`
- `0x1802796e4`
- `0x180279758`
- `0x18027a218`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18020837a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18020837a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180207ec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180207ec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18020806d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18020806d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180207f38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180207f8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18020809d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180208165`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802082bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180207f38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180207f8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18020809d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180208165`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802082bc`

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
  __int64 v11; // r8
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v22; // rdx
  int v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // r8
  void *v26; // r9
  LPVOID v27; // rax
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  PROPVARIANT *pvar; // [rsp+30h] [rbp-10h]
  SIZE_T cb; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int64 v46; // [rsp+98h] [rbp+58h] BYREF

  v46 = 0;
  v4 = (PROPVARIANT *)((char *)this + 784);
  pvar = v4;
  if ( !*(_WORD *)v4 )
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
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v11);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMPropTranslator::AddLanguage", 864, v10);
    }
    if ( !g_wppLevels )
    {
LABEL_59:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
LABEL_60:
      if ( v10 >= 0 )
        return (unsigned int)v10;
      goto LABEL_73;
    }
    v22 = 57;
LABEL_58:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids, this, v10);
    goto LABEL_59;
  }
  if ( *(_WORD *)v4 != 4127 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&cb, "CWMPropTranslator::AddLanguage", 875);
    v40 = (__int64 *)CallStackTracing::s_wpInstance;
    v10 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39);
      CallStackTracing::s_wpInstance = v41;
      if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
      {
        v40 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v40 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v40 + 8) )
    {
      v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
      if ( *((_DWORD *)v42 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v42, "CWMPropTranslator::AddLanguage", 875, -2147418113);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        &WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids,
        this,
        -2147418113);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
    v7 = (_QWORD *)((char *)this + 800);
    goto LABEL_73;
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&cb, "CWMPropTranslator::AddLanguage", 870);
  v23 = *((_DWORD *)this + 198);
  v7 = (_QWORD *)((char *)this + 800);
  *((_QWORD *)this + 100) = 0;
  cb = 0;
  v10 = ULongLongMult((unsigned int)(v23 + 1), 8u, &cb);
  if ( v10 < 0 )
  {
LABEL_27:
    v28 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
      CallStackTracing::s_wpInstance = v29;
      if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
      {
        v28 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v28 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v28 + 8) )
    {
      v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
      if ( *((_DWORD *)v37 + 499) != v10 )
        CallStackContext::TraceFailure(v37, "CWMPropTranslator::AddLanguage", 870, v10);
    }
    if ( !g_wppLevels )
      goto LABEL_59;
    v22 = 58;
    goto LABEL_58;
  }
  v27 = CoTaskMemRealloc(v26, cb);
  *v7 = v27;
  if ( !v27 )
  {
    v10 = -2147024882;
    goto LABEL_27;
  }
LABEL_5:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
  v10 = StringCbLengthW(a2, 0x104u, &v46);
  if ( v10 < 0 )
  {
LABEL_50:
    *a3 = *((_WORD *)this + 396) - 1;
    goto LABEL_60;
  }
  v12 = v46;
  *(_QWORD *)(*v7 + 8LL * *((unsigned int *)this + 198)) = CoTaskMemAlloc(v46 + 2);
  v13 = *(unsigned __int16 **)(*v7 + 8LL * *((unsigned int *)this + 198));
  if ( !v13 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&cb, "CWMPropTranslator::AddLanguage", 897);
    v34 = (__int64 *)CallStackTracing::s_wpInstance;
    v10 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33);
      CallStackTracing::s_wpInstance = v35;
      if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v34 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v34 + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)v36 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v36, "CWMPropTranslator::AddLanguage", 897, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_49;
    v31 = 61;
    goto LABEL_48;
  }
  v14 = StringCbCopyW(v13, v12 + 2, a2);
  ++*((_DWORD *)this + 198);
  v10 = v14;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&cb, "CWMPropTranslator::AddLanguage", 893);
  if ( v10 >= 0 )
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
    goto LABEL_50;
  }
  v17 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)v30 + 499) != v10 )
      CallStackContext::TraceFailure(v30, "CWMPropTranslator::AddLanguage", 893, v10);
  }
  if ( !g_wppLevels )
    goto LABEL_49;
  v31 = 60;
LABEL_48:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, &WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids, this, v10);
LABEL_49:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&cb);
LABEL_73:
  if ( *((_DWORD *)this + 198) )
  {
    CMFPropVariant::Clear(pvar);
  }
  else
  {
    CoTaskMemFree(pvar[2]);
    *v7 = 0;
    *(_WORD *)pvar = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180207df0  mov     [rsp-38h+arg_8], rbx
0x180207df5  push    rbp
0x180207df6  push    rsi
0x180207df7  push    rdi
0x180207df8  push    r12
0x180207dfa  push    r13
0x180207dfc  push    r14
0x180207dfe  push    r15
0x180207e00  mov     rbp, rsp
0x180207e03  sub     rsp, 40h
0x180207e07  xor     ebx, ebx
0x180207e09  lea     r15, aCwmproptransla_9; "CWMPropTranslator::AddLanguage"
0x180207e10  mov     rsi, rcx
0x180207e13  mov     [rbp+arg_18], rbx
0x180207e17  add     rcx, 310h
0x180207e1e  mov     r12, rdx
0x180207e21  mov     r13, r8
0x180207e24  mov     [rbp+pvar], rcx
0x180207e28  mov     rdx, r15; char *
0x180207e2b  cmp     [rcx], bx
0x180207e2e  jnz     loc_180208016
0x180207e34  mov     r8d, 360h; int
0x180207e3a  lea     rcx, [rbp+cb]; this
0x180207e3e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180207e43  lea     r14d, [rbx+1]
0x180207e47  mov     [rbp+cb], rbx
0x180207e4b  lea     rdi, [rsi+320h]
0x180207e52  mov     ecx, r14d; unsigned __int64
0x180207e55  lea     r8, [rbp+cb]; unsigned __int64 *
0x180207e59  mov     [rdi], rbx
0x180207e5c  lea     edx, [rbx+8]; unsigned __int64
0x180207e5f  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180207e64  mov     ebx, eax
0x180207e66  test    eax, eax
0x180207e68  js      loc_180207F7D
0x180207e6e  mov     r8, [rbp+cb]; unsigned __int64
0x180207e72  mov     r9, rdi; void **
0x180207e75  mov     edx, r14d; unsigned int
0x180207e78  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180207e7d  mov     ebx, eax
0x180207e7f  test    eax, eax
0x180207e81  js      loc_180207F7D
0x180207e87  mov     word ptr [rsi+310h], 101Fh
0x180207e90  mov     dword ptr [rsi+318h], 0
0x180207e9a  lea     rcx, [rbp+cb]; this
0x180207e9e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180207ea3  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x180207ea7  mov     edx, 104h; unsigned __int64
0x180207eac  mov     rcx, r12; unsigned __int16 *
0x180207eaf  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180207eb4  mov     ebx, eax
0x180207eb6  test    eax, eax
0x180207eb8  js      loc_18020820B
0x180207ebe  mov     rbx, [rbp+arg_18]
0x180207ec2  lea     rcx, [rbx+2]; cb
0x180207ec6  call    cs:__imp_CoTaskMemAlloc
0x180207ecd  nop     dword ptr [rax+rax+00h]
0x180207ed2  mov     rcx, [rdi]
0x180207ed5  mov     r8d, [rsi+318h]
0x180207edc  mov     [rcx+r8*8], rax
0x180207ee0  mov     ecx, [rsi+318h]
0x180207ee6  mov     rax, [rdi]
0x180207ee9  mov     rcx, [rax+rcx*8]; unsigned __int16 *
0x180207eed  test    rcx, rcx
0x180207ef0  jz      loc_18020813C
0x180207ef6  mov     r8, r12; unsigned __int16 *
0x180207ef9  lea     rdx, [rbx+2]; unsigned __int64
0x180207efd  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180207f02  add     [rsi+318h], r14d
0x180207f09  lea     rcx, [rbp+cb]; this
0x180207f0d  mov     r8d, 37Dh; int
0x180207f13  mov     rdx, r15; char *
0x180207f16  mov     ebx, eax
0x180207f18  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180207f1d  xor     r12d, r12d
0x180207f20  test    ebx, ebx
0x180207f22  jns     loc_18020812E
0x180207f28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180207f2f  test    rcx, rcx
0x180207f32  jnz     loc_1802080F0
0x180207f38  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180207f3f  nop     dword ptr [rax+rax+00h]
0x180207f44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180207f4b  mov     rcx, rax
0x180207f4e  test    rax, rax
0x180207f51  jz      loc_1802080E2
0x180207f57  mov     rax, [rax]
0x180207f5a  mov     edx, 7F0h
0x180207f5f  mov     rax, [rax+8]
0x180207f63  call    cs:__guard_dispatch_icall_fptr
0x180207f69  test    eax, eax
0x180207f6b  jz      loc_1802080E2
0x180207f71  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180207f78  jmp     loc_1802080F0
0x180207f7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180207f84  xor     r12d, r12d
0x180207f87  test    rcx, rcx
0x180207f8a  jnz     short loc_180207FD4
0x180207f8c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180207f93  nop     dword ptr [rax+rax+00h]
0x180207f98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180207f9f  mov     rcx, rax
0x180207fa2  test    rax, rax
0x180207fa5  jz      short loc_180207FC6
0x180207fa7  mov     rax, [rax]
0x180207faa  mov     edx, 7F0h
0x180207faf  mov     rax, [rax+8]
0x180207fb3  call    cs:__guard_dispatch_icall_fptr
0x180207fb9  test    eax, eax
0x180207fbb  jz      short loc_180207FC6
0x180207fbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180207fc4  jmp     short loc_180207FD4
0x180207fc6  lea     rcx, qword_1803CE250; this
0x180207fcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180207fd4  cmp     [rcx+8], r12b
0x180207fd8  jz      short loc_180207FFF
0x180207fda  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180207fdf  test    ebx, ebx
0x180207fe1  jns     short loc_180207FFF
0x180207fe3  cmp     [rax+7CCh], ebx
0x180207fe9  jz      short loc_180207FFF
0x180207feb  mov     r9d, ebx; int
0x180207fee  mov     r8d, 360h; int
0x180207ff4  mov     rdx, r15; char *
0x180207ff7  mov     rcx, rax; this
0x180207ffa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180207fff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180208006  jb      loc_180208285
0x18020800c  mov     edx, 39h ; '9'
0x180208011  jmp     loc_180208267
0x180208016  mov     eax, 101Fh
0x18020801b  cmp     [rcx], ax
0x18020801e  lea     rcx, [rbp+cb]; this
0x180208022  jnz     loc_18020829B
0x180208028  mov     r8d, 366h; int
0x18020802e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180208033  mov     ecx, [rsi+318h]
0x180208039  lea     rdi, [rsi+320h]
0x180208040  mov     r9, [rdi]
0x180208043  lea     r8, [rbp+cb]; unsigned __int64 *
0x180208047  mov     r14d, 1
0x18020804d  mov     [rdi], rbx
0x180208050  add     ecx, r14d; unsigned __int64
0x180208053  mov     [rbp+cb], rbx
0x180208057  lea     edx, [r14+7]; unsigned __int64
0x18020805b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180208060  mov     ebx, eax
0x180208062  test    eax, eax
0x180208064  js      short loc_18020808A
0x180208066  mov     rdx, [rbp+cb]; cb
0x18020806a  mov     rcx, r9; pv
0x18020806d  call    cs:__imp_CoTaskMemRealloc
0x180208074  nop     dword ptr [rax+rax+00h]
0x180208079  mov     [rdi], rax
0x18020807c  test    rax, rax
0x18020807f  jnz     loc_180207E9A
0x180208085  mov     ebx, 8007000Eh
0x18020808a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180208091  xor     r12d, r12d
0x180208094  test    rcx, rcx
0x180208097  jnz     loc_18020822E
0x18020809d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802080a4  nop     dword ptr [rax+rax+00h]
0x1802080a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802080b0  mov     rcx, rax
0x1802080b3  test    rax, rax
0x1802080b6  jz      loc_180208220
0x1802080bc  mov     rax, [rax]
0x1802080bf  mov     edx, 7F0h
0x1802080c4  mov     rax, [rax+8]
0x1802080c8  call    cs:__guard_dispatch_icall_fptr
0x1802080ce  test    eax, eax
0x1802080d0  jz      loc_180208220
0x1802080d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802080dd  jmp     loc_18020822E
0x1802080e2  lea     rcx, qword_1803CE250; this
0x1802080e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802080f0  cmp     [rcx+8], r12b
0x1802080f4  jz      short loc_180208117
0x1802080f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802080fb  cmp     [rax+7CCh], ebx
0x180208101  jz      short loc_180208117
0x180208103  mov     r9d, ebx; int
0x180208106  mov     r8d, 37Dh; int
0x18020810c  mov     rdx, r15; char *
0x18020810f  mov     rcx, rax; this
0x180208112  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180208117  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18020811e  jb      loc_1802081FD
0x180208124  mov     edx, 3Ch ; '<'
0x180208129  jmp     loc_1802081DF
0x18020812e  lea     rcx, [rbp+cb]; this
0x180208132  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180208137  jmp     loc_18020820E
0x18020813c  mov     r13d, 381h
0x180208142  lea     rcx, [rbp+cb]; this
0x180208146  mov     r8d, r13d; int
0x180208149  mov     rdx, r15; char *
0x18020814c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180208151  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180208158  xor     r12d, r12d
0x18020815b  mov     ebx, 8007000Eh
0x180208160  test    rcx, rcx
0x180208163  jnz     short loc_1802081AD
0x180208165  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18020816c  nop     dword ptr [rax+rax+00h]
0x180208171  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180208178  mov     rcx, rax
0x18020817b  test    rax, rax
0x18020817e  jz      short loc_18020819F
0x180208180  mov     rax, [rax]
0x180208183  mov     edx, 7F0h
0x180208188  mov     rax, [rax+8]
0x18020818c  call    cs:__guard_dispatch_icall_fptr
0x180208192  test    eax, eax
0x180208194  jz      short loc_18020819F
0x180208196  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18020819d  jmp     short loc_1802081AD
0x18020819f  lea     rcx, qword_1803CE250; this
0x1802081a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802081ad  cmp     [rcx+8], r12b
0x1802081b1  jz      short loc_1802081D1
0x1802081b3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802081b8  cmp     [rax+7CCh], ebx
0x1802081be  jz      short loc_1802081D1
0x1802081c0  mov     r9d, ebx; int
0x1802081c3  mov     r8d, r13d; int
0x1802081c6  mov     rdx, r15; char *
0x1802081c9  mov     rcx, rax; this
0x1802081cc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802081d1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1802081d8  jb      short loc_1802081FD
0x1802081da  mov     edx, 3Dh ; '='
0x1802081df  mov     rcx, cs:WPP_GLOBAL_Control
0x1802081e6  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x1802081ed  mov     r9, rsi
0x1802081f0  mov     [rsp+40h+var_20], ebx
0x1802081f4  mov     rcx, [rcx+10h]
0x1802081f8  call    WPP_SF_qD
0x1802081fd  lea     rcx, [rbp+cb]; this
0x180208201  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180208206  jmp     loc_180208369
0x18020820b  xor     r12d, r12d
0x18020820e  movzx   eax, word ptr [rsi+318h]
0x180208215  sub     ax, r14w
0x180208219  mov     [r13+0], ax
0x18020821e  jmp     short loc_18020828E
0x180208220  lea     rcx, qword_1803CE250; this
0x180208227  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18020822e  cmp     [rcx+8], r12b
0x180208232  jz      short loc_180208259
0x180208234  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180208239  test    ebx, ebx
0x18020823b  jns     short loc_180208259
0x18020823d  cmp     [rax+7CCh], ebx
0x180208243  jz      short loc_180208259
0x180208245  mov     r9d, ebx; int
0x180208248  mov     r8d, 366h; int
0x18020824e  mov     rdx, r15; char *
0x180208251  mov     rcx, rax; this
0x180208254  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180208259  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180208260  jb      short loc_180208285
0x180208262  mov     edx, 3Ah ; ':'
0x180208267  mov     rcx, cs:WPP_GLOBAL_Control
0x18020826e  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x180208275  mov     r9, rsi
0x180208278  mov     [rsp+40h+var_20], ebx
0x18020827c  mov     rcx, [rcx+10h]
0x180208280  call    WPP_SF_qD
0x180208285  lea     rcx, [rbp+cb]; this
0x180208289  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18020828e  test    ebx, ebx
0x180208290  jns     loc_180208398
0x180208296  jmp     loc_180208369
0x18020829b  mov     edi, 36Bh
0x1802082a0  mov     r8d, edi; int
0x1802082a3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802082a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802082af  xor     r12d, r12d
0x1802082b2  mov     ebx, 8000FFFFh
0x1802082b7  test    rcx, rcx
0x1802082ba  jnz     short loc_180208304
0x1802082bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802082c3  nop     dword ptr [rax+rax+00h]
0x1802082c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802082cf  mov     rcx, rax
0x1802082d2  test    rax, rax
0x1802082d5  jz      short loc_1802082F6
0x1802082d7  mov     rax, [rax]
0x1802082da  mov     edx, 7F0h
0x1802082df  mov     rax, [rax+8]
0x1802082e3  call    cs:__guard_dispatch_icall_fptr
0x1802082e9  test    eax, eax
0x1802082eb  jz      short loc_1802082F6
0x1802082ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802082f4  jmp     short loc_180208304
0x1802082f6  lea     rcx, qword_1803CE250; this
0x1802082fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180208304  cmp     [rcx+8], r12b
  ... truncated ...
```
