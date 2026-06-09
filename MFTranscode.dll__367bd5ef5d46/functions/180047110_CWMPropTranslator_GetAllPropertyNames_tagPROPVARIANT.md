# CWMPropTranslator::GetAllPropertyNames(tagPROPVARIANT *)

- ea: `0x180047110`
- end: `0x180047459`
- name: `?GetAllPropertyNames@CWMPropTranslator@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `841`
- prototype: `__int64 __fastcall(CWMPropTranslator *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x1800469b0`
- `0x180046efc`
- `0x180047110`
- `0x180048d88`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047418`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047418`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800471a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047294`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047390`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800471a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047294`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047390`

## pseudocode

```c
__int64 __fastcall CWMPropTranslator::GetAllPropertyNames(CWMPropTranslator *this, struct tagPROPVARIANT *a2)
{
  unsigned int v4; // esi
  __int64 v5; // rdx
  int v6; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  unsigned int v11; // eax
  LPVOID *p_pData; // r14
  __int64 v13; // rdx
  void *v14; // rcx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  char *v18; // r15
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v24[4]; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v25[3]; // [rsp+34h] [rbp-3Ch] BYREF
  unsigned __int64 v26[2]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v27; // [rsp+50h] [rbp-20h] BYREF
  int v28; // [rsp+60h] [rbp-10h]

  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  v4 = 0;
  v28 = 0;
  memset(v25, 0, sizeof(v25));
  v27 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v24, "CWMPropTranslator::GetAllPropertyNames", 556);
  v6 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1), v25);
  if ( v6 >= 0 )
  {
    v11 = v25[0];
    if ( !v25[0] )
      goto LABEL_45;
    a2->vt = 4127;
    p_pData = (LPVOID *)&a2->bstrblobVal.pData;
    a2->bstrblobVal.pData = 0;
    v26[0] = 0;
    v6 = ULongLongMult(v11, 8u, v26);
    if ( v6 >= 0 )
      v6 = CTCoAllocPolicy::Alloc(v14, 1u, v26[0], (void **)&a2->bstrblobVal.pData);
    if ( v6 >= 0 )
    {
      v18 = (char *)*p_pData;
      a2->lVal = 0;
      while ( 1 )
      {
        if ( v4 >= v25[0] )
        {
          if ( !a2->lVal )
          {
            CoTaskMemFree(*p_pData);
            *(_OWORD *)&a2->vt = 0;
            a2->bstrblobVal.pData = 0;
          }
          goto LABEL_45;
        }
        v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(**((_QWORD **)this + 1) + 32LL))(
               *((_QWORD *)this + 1),
               v4,
               &v27);
        if ( v6 < 0 )
          break;
        if ( (unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find((char *)this + 392, &v27, &v25[1], v26) )
        {
          (*(void (__fastcall **)(_QWORD, __int64 *, char *, _QWORD))(**(_QWORD **)&v25[1] + 104LL))(
            *(_QWORD *)&v25[1],
            MF_MD_NAME,
            v18,
            0);
          v18 += 8;
          ++a2->lVal;
        }
        ++v4;
      }
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CWMPropTranslator::GetAllPropertyNames", 568, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 32;
        goto LABEL_12;
      }
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
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
        if ( *((_DWORD *)v17 + 499) != v6 )
          CallStackContext::TraceFailure(v17, "CWMPropTranslator::GetAllPropertyNames", 561, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 31;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
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
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v9 + 499) != v6 )
        CallStackContext::TraceFailure(v9, "CWMPropTranslator::GetAllPropertyNames", 556, v6);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 30;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids,
        (char *)this - 8,
        v6);
    }
  }
LABEL_45:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180047110  mov     [rsp-38h+arg_10], rbx
0x180047115  push    rbp
0x180047116  push    rsi
0x180047117  push    rdi
0x180047118  push    r12
0x18004711a  push    r13
0x18004711c  push    r14
0x18004711e  push    r15
0x180047120  mov     rbp, rsp
0x180047123  sub     rsp, 70h
0x180047127  mov     rax, cs:__security_cookie
0x18004712e  xor     rax, rsp
0x180047131  mov     [rbp+var_8], rax
0x180047135  xorps   xmm0, xmm0
0x180047138  lea     r15, aCwmproptransla_8; "CWMPropTranslator::GetAllPropertyNames"
0x18004713f  xor     eax, eax
0x180047141  mov     rdi, rdx
0x180047144  movups  xmmword ptr [rdx], xmm0
0x180047147  mov     [rdx+10h], rax
0x18004714b  mov     r12, rcx
0x18004714e  xor     esi, esi
0x180047150  mov     [rbp+var_10], eax
0x180047153  mov     r14d, 22Ch
0x180047159  mov     dword ptr [rbp+var_3C], esi
0x18004715c  mov     rdx, r15; char *
0x18004715f  mov     qword ptr [rbp+var_3C+4], rsi
0x180047163  mov     r8d, r14d; int
0x180047166  lea     rcx, [rbp+var_40]; this
0x18004716a  movups  [rbp+var_20], xmm0
0x18004716e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180047173  lea     r13, [r12-8]
0x180047178  mov     rcx, [r13+10h]
0x18004717c  lea     rdx, [rbp+var_3C]
0x180047180  mov     rax, [rcx]
0x180047183  mov     rax, [rax+18h]
0x180047187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004718c  mov     ebx, eax
0x18004718e  test    eax, eax
0x180047190  jns     loc_18004723C
0x180047196  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004719d  test    rcx, rcx
0x1800471a0  jnz     short loc_1800471E3
0x1800471a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800471a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800471af  mov     rcx, rax
0x1800471b2  test    rax, rax
0x1800471b5  jz      short loc_1800471D5
0x1800471b7  mov     rax, [rax]
0x1800471ba  mov     edx, 7F0h
0x1800471bf  mov     rax, [rax+8]
0x1800471c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471c8  test    eax, eax
0x1800471ca  jz      short loc_1800471D5
0x1800471cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800471d3  jmp     short loc_1800471E3
0x1800471d5  lea     rcx, qword_180069A90; this
0x1800471dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800471e3  cmp     [rcx+8], sil
0x1800471e7  jz      short loc_180047207
0x1800471e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800471ee  cmp     [rax+7CCh], ebx
0x1800471f4  jz      short loc_180047207
0x1800471f6  mov     r9d, ebx; int
0x1800471f9  mov     r8d, r14d; int
0x1800471fc  mov     rdx, r15; char *
0x1800471ff  mov     rcx, rax; this
0x180047202  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180047207  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004720c  cmp     al, 1
0x18004720e  jb      loc_18004742A
0x180047214  mov     edx, 1Eh
0x180047219  mov     rcx, cs:WPP_GLOBAL_Control
0x180047220  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x180047227  mov     r9, r13
0x18004722a  mov     [rsp+70h+var_50], ebx
0x18004722e  mov     rcx, [rcx+10h]
0x180047232  call    WPP_SF_qd
0x180047237  jmp     loc_18004742A
0x18004723c  mov     eax, dword ptr [rbp+var_3C]
0x18004723f  test    eax, eax
0x180047241  jz      loc_18004742A
0x180047247  mov     word ptr [rdi], 101Fh
0x18004724c  lea     r14, [rdi+10h]
0x180047250  mov     ecx, eax; unsigned __int64
0x180047252  mov     [r14], rsi
0x180047255  lea     r8, [rbp+var_30]; unsigned __int64 *
0x180047259  mov     [rbp+var_30], rsi
0x18004725d  mov     edx, 8; unsigned __int64
0x180047262  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180047267  mov     ebx, eax
0x180047269  test    eax, eax
0x18004726b  js      short loc_180047280
0x18004726d  mov     r8, [rbp+var_30]; unsigned __int64
0x180047271  mov     r9, r14; void **
0x180047274  mov     edx, 1; unsigned int
0x180047279  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18004727e  mov     ebx, eax
0x180047280  test    ebx, ebx
0x180047282  jns     loc_180047313
0x180047288  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004728f  test    rcx, rcx
0x180047292  jnz     short loc_1800472D5
0x180047294  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004729a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800472a1  mov     rcx, rax
0x1800472a4  test    rax, rax
0x1800472a7  jz      short loc_1800472C7
0x1800472a9  mov     rax, [rax]
0x1800472ac  mov     edx, 7F0h
0x1800472b1  mov     rax, [rax+8]
0x1800472b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472ba  test    eax, eax
0x1800472bc  jz      short loc_1800472C7
0x1800472be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800472c5  jmp     short loc_1800472D5
0x1800472c7  lea     rcx, qword_180069A90; this
0x1800472ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800472d5  cmp     [rcx+8], sil
0x1800472d9  jz      short loc_1800472FC
0x1800472db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800472e0  cmp     [rax+7CCh], ebx
0x1800472e6  jz      short loc_1800472FC
0x1800472e8  mov     r9d, ebx; int
0x1800472eb  mov     r8d, 231h; int
0x1800472f1  mov     rdx, r15; char *
0x1800472f4  mov     rcx, rax; this
0x1800472f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800472fc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047301  cmp     al, 1
0x180047303  jb      loc_18004742A
0x180047309  mov     edx, 1Fh
0x18004730e  jmp     loc_180047219
0x180047313  mov     r15, [r14]
0x180047316  mov     [rdi+8], esi
0x180047319  cmp     esi, dword ptr [rbp+var_3C]
0x18004731c  jnb     loc_18004740F
0x180047322  mov     rcx, [r12+8]
0x180047327  lea     r8, [rbp+var_20]
0x18004732b  mov     edx, esi
0x18004732d  mov     rax, [rcx]
0x180047330  mov     rax, [rax+20h]
0x180047334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047339  mov     ebx, eax
0x18004733b  test    eax, eax
0x18004733d  js      short loc_180047384
0x18004733f  lea     rcx, [r12+188h]
0x180047347  lea     r9, [rbp+var_30]
0x18004734b  lea     r8, [rbp+var_3C+4]
0x18004734f  lea     rdx, [rbp+var_20]
0x180047353  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x180047358  test    eax, eax
0x18004735a  jz      short loc_180047380
0x18004735c  mov     rcx, qword ptr [rbp+var_3C+4]
0x180047360  lea     rdx, MF_MD_NAME
0x180047367  xor     r9d, r9d
0x18004736a  mov     r8, r15
0x18004736d  mov     rax, [rcx]
0x180047370  mov     rax, [rax+68h]
0x180047374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047379  add     r15, 8
0x18004737d  inc     dword ptr [rdi+8]
0x180047380  inc     esi
0x180047382  jmp     short loc_180047319
0x180047384  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004738b  test    rcx, rcx
0x18004738e  jnz     short loc_1800473D1
0x180047390  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180047396  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004739d  mov     rcx, rax
0x1800473a0  test    rax, rax
0x1800473a3  jz      short loc_1800473C3
0x1800473a5  mov     rax, [rax]
0x1800473a8  mov     edx, 7F0h
0x1800473ad  mov     rax, [rax+8]
0x1800473b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473b6  test    eax, eax
0x1800473b8  jz      short loc_1800473C3
0x1800473ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800473c1  jmp     short loc_1800473D1
0x1800473c3  lea     rcx, qword_180069A90; this
0x1800473ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800473d1  cmp     byte ptr [rcx+8], 0
0x1800473d5  jz      short loc_1800473FC
0x1800473d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800473dc  cmp     [rax+7CCh], ebx
0x1800473e2  jz      short loc_1800473FC
0x1800473e4  mov     r9d, ebx; int
0x1800473e7  lea     rdx, aCwmproptransla_8; "CWMPropTranslator::GetAllPropertyNames"
0x1800473ee  mov     r8d, 238h; int
0x1800473f4  mov     rcx, rax; this
0x1800473f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800473fc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047401  cmp     al, 1
0x180047403  jb      short loc_18004742A
0x180047405  mov     edx, 20h ; ' '
0x18004740a  jmp     loc_180047219
0x18004740f  cmp     dword ptr [rdi+8], 0
0x180047413  jnz     short loc_18004742A
0x180047415  mov     rcx, [r14]; pv
0x180047418  call    cs:__imp_CoTaskMemFree
0x18004741e  xorps   xmm0, xmm0
0x180047421  xor     eax, eax
0x180047423  movups  xmmword ptr [rdi], xmm0
0x180047426  mov     [rdi+10h], rax
0x18004742a  lea     rcx, [rbp+var_40]; this
0x18004742e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180047433  mov     eax, ebx
0x180047435  mov     rcx, [rbp+var_8]
0x180047439  xor     rcx, rsp; StackCookie
0x18004743c  call    __security_check_cookie
0x180047441  mov     rbx, [rsp+70h+arg_10]
0x180047449  add     rsp, 70h
0x18004744d  pop     r15
0x18004744f  pop     r14
0x180047451  pop     r13
0x180047453  pop     r12
0x180047455  pop     rdi
0x180047456  pop     rsi
0x180047457  pop     rbp
0x180047458  retn
```
