# CExpression::ResolveReference(ExpressionReferenceInfo const &,CExpressionValue *)

- ea: `0x1800462c0`
- end: `0x18004658b`
- name: `?ResolveReference@CExpression@@AEBAJAEBUExpressionReferenceInfo@@PEAVCExpressionValue@@@Z`
- size: `715`
- prototype: `int(CExpression *__hidden this, const struct ExpressionReferenceInfo *, struct CExpressionValue *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801f95d0`

## callees

- `0x180042854`
- `0x180042de0`
- `0x180044dd4`
- `0x180045f10`
- `0x180045fb0`
- `0x1800462c0`
- `0x180046800`
- `0x1801527f8`
- `0x180163c00`
- `0x180169320`
- `0x180200468`
- `0x180204100`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046337`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800463ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046337`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800463ba`

## pseudocode

```c
__int64 __fastcall CExpression::ResolveReference(
        CExpression *this,
        const struct ExpressionReferenceInfo *a2,
        struct CExpressionValue *a3,
        const char *a4)
{
  __int64 v4; // rbx
  __int64 v8; // r12
  unsigned int v9; // eax
  __int64 v10; // rbp
  struct CResource *v11; // r15
  int v12; // ebp
  int v13; // r12d
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rbx
  struct CResource *v18; // rdx
  __int64 v20; // rdx
  float v21; // xmm6_4
  __int64 Elapsed; // rax
  unsigned int v23; // [rsp+20h] [rbp-48h]
  unsigned int v24; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v26; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0;
  v26 = 0;
  if ( *((_DWORD *)this + 55) || CCommonRegistryData::LogExpressionPerfStats )
  {
    v8 = *(_QWORD *)(*((_QWORD *)this + 3) + 816LL) + 128LL;
    QpcStopwatch::Start((QpcStopwatch *)&v26);
    v4 = v26;
  }
  else
  {
    v8 = 0;
  }
  v9 = *((_DWORD *)a2 + 4);
  if ( v9 >= *((_DWORD *)this + 80) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x571,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\expression.cpp",
      a4);
  v10 = *(_QWORD *)(*((_QWORD *)this + 37) + 8LL * v9);
  if ( !v10 )
    goto LABEL_21;
  if ( !g_pComposition
    || GetCurrentThreadId() != CComposition::s_compositionThreadId
    && !CTreeLock::IsLockedByCurrentThread((CComposition *)((char *)g_pComposition + 5696)) )
  {
    ModuleFailFastForHRESULT(-2003304313, retaddr);
  }
  v11 = *(struct CResource **)(v10 + 64);
  if ( v11 )
  {
    if ( v4 )
    {
      Elapsed = QpcStopwatch::GetElapsed((QpcStopwatch *)&v26);
      CExpressionPerformanceCounter::AddDurationSample(v8, 3, Elapsed);
    }
    v12 = *(_DWORD *)a2;
    v13 = *((_DWORD *)a2 + 3);
    v14 = *(unsigned int *)a2;
    LODWORD(v14) = v14 & 0x7FFFFFFF;
    v15 = (*(__int64 (__fastcall **)(struct CResource *, __int64, struct CExpressionValue *))(*(_QWORD *)v11 + 136LL))(
            v11,
            v14,
            a3);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AC,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\resource.cpp",
        (const char *)(unsigned int)v15,
        v23);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B0,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\baseexpression.cpp",
        (const char *)v16,
        v24);
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D5048, 2u, v16, 0x589u, 0);
    }
    else
    {
      if ( v12 < 0 && *((_DWORD *)a3 + 16) == 18 )
      {
        v21 = *(float *)a3;
        CExpressionValue::DestroyCurrent(a3);
        *((_DWORD *)a3 + 16) = 18;
        *(float *)a3 = v21 * 57.295776;
      }
      if ( v13 == 1 )
      {
        v20 = *((_QWORD *)this + 24);
        if ( v20 )
        {
          if ( *(_BYTE *)(v20 + 4) )
            CExpressionValue::ApplyMaskToValue(a3, (const struct SubchannelMaskInfo *)v20);
        }
      }
      v17 = *((_QWORD *)this + 23);
      if ( v17 )
      {
        if ( !g_pComposition
          || GetCurrentThreadId() != CComposition::s_compositionThreadId
          && !CTreeLock::IsLockedByCurrentThread((CComposition *)((char *)g_pComposition + 5696)) )
        {
          ModuleFailFastForHRESULT(-2003304313, retaddr);
        }
        v18 = *(struct CResource **)(v17 + 64);
      }
      else
      {
        v18 = 0;
      }
      CInteractionTrackerBase::CheckTargetsForInteractionSource(a2, v18, v11);
      return 0;
    }
  }
  else
  {
LABEL_21:
    v16 = -2147467259;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D5048, 2u, -2147467259, 0x57Cu, 0);
  }
  return v16;
}

```

## disassembly

```asm
0x1800462c0  push    rbx
0x1800462c2  push    rsi
0x1800462c3  push    rdi
0x1800462c4  push    r12
0x1800462c6  push    r14
0x1800462c8  sub     rsp, 40h
0x1800462cc  xor     ebx, ebx
0x1800462ce  mov     r14, r8
0x1800462d1  mov     rsi, rdx
0x1800462d4  mov     rdi, rcx
0x1800462d7  mov     [rsp+68h+arg_0], rbx
0x1800462dc  cmp     [rcx+0DCh], ebx
0x1800462e2  jnz     loc_180046480
0x1800462e8  cmp     cs:?LogExpressionPerfStats@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B, bl; details::CRegistryKey<bool,bool> const CCommonRegistryData::LogExpressionPerfStats
0x1800462ee  jnz     loc_180046480
0x1800462f4  xor     r12d, r12d
0x1800462f7  mov     eax, [rsi+10h]
0x1800462fa  cmp     eax, [rdi+140h]
0x180046300  jnb     loc_1800464A3
0x180046306  mov     ecx, eax
0x180046308  mov     [rsp+68h+arg_8], rbp
0x18004630d  mov     rax, [rdi+128h]
0x180046314  mov     [rsp+68h+arg_10], r15
0x18004631c  mov     rbp, [rax+rcx*8]
0x180046320  test    rbp, rbp
0x180046323  jz      loc_18004640A
0x180046329  cmp     cs:?g_pComposition@@3PEAVCComposition@@EA, 0; CComposition * g_pComposition
0x180046331  jz      loc_1800463FA
0x180046337  call    cs:__imp_GetCurrentThreadId
0x18004633d  cmp     eax, cs:?s_compositionThreadId@CComposition@@0KA; ulong CComposition::s_compositionThreadId
0x180046343  jnz     loc_1800463DF
0x180046349  mov     r15, [rbp+40h]
0x18004634d  test    r15, r15
0x180046350  jz      loc_18004640A
0x180046356  test    rbx, rbx
0x180046359  jnz     loc_18004656C
0x18004635f  mov     rax, [r15]
0x180046362  mov     r8, r14
0x180046365  mov     ebp, [rsi]
0x180046367  mov     rcx, r15
0x18004636a  mov     r12d, [rsi+0Ch]
0x18004636e  mov     edx, ebp
0x180046370  btr     edx, 1Fh
0x180046374  mov     rax, [rax+88h]
0x18004637b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046380  mov     ebx, eax
0x180046382  test    eax, eax
0x180046384  js      loc_1800464BA
0x18004638a  test    ebp, ebp
0x18004638c  js      loc_180046529
0x180046392  cmp     r12d, 1
0x180046396  jz      loc_180046502
0x18004639c  mov     rbx, [rdi+0B8h]
0x1800463a3  test    rbx, rbx
0x1800463a6  jz      loc_180046565
0x1800463ac  cmp     cs:?g_pComposition@@3PEAVCComposition@@EA, 0; CComposition * g_pComposition
0x1800463b4  jz      loc_180046470
0x1800463ba  call    cs:__imp_GetCurrentThreadId
0x1800463c0  cmp     eax, cs:?s_compositionThreadId@CComposition@@0KA; ulong CComposition::s_compositionThreadId
0x1800463c6  jnz     loc_180046455
0x1800463cc  mov     rdx, [rbx+40h]; struct CResource *
0x1800463d0  mov     r8, r15; struct CResource *
0x1800463d3  mov     rcx, rsi; struct ExpressionReferenceInfo *
0x1800463d6  call    ?CheckTargetsForInteractionSource@CInteractionTrackerBase@@SAXPEBUExpressionReferenceInfo@@PEAVCResource@@1@Z; CInteractionTrackerBase::CheckTargetsForInteractionSource(ExpressionReferenceInfo const *,CResource *,CResource *)
0x1800463db  xor     ebx, ebx
0x1800463dd  jmp     short loc_18004643A
0x1800463df  mov     rcx, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x1800463e6  add     rcx, 1640h; this
0x1800463ed  call    ?IsLockedByCurrentThread@CTreeLock@@QEBA_NXZ; CTreeLock::IsLockedByCurrentThread(void)
0x1800463f2  test    al, al
0x1800463f4  jnz     loc_180046349
0x1800463fa  mov     rdx, [rsp+68h]; void *
0x1800463ff  mov     ecx, 88980087h; int
0x180046404  call    ModuleFailFastForHRESULT
0x18004640a  mov     [rsp+68h+var_40], 0; void *
0x180046413  mov     ebx, 80004005h
0x180046418  mov     [rsp+68h+var_48], 57Ch; unsigned int
0x180046420  mov     r9d, ebx; int
0x180046423  lea     rdx, qword_1802D5048; int *
0x18004642a  mov     r8d, 2; unsigned int
0x180046430  mov     ecx, 14h; unsigned int
0x180046435  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18004643a  mov     rbp, [rsp+68h+arg_8]
0x18004643f  mov     eax, ebx
0x180046441  mov     r15, [rsp+68h+arg_10]
0x180046449  add     rsp, 40h
0x18004644d  pop     r14
0x18004644f  pop     r12
0x180046451  pop     rdi
0x180046452  pop     rsi
0x180046453  pop     rbx
0x180046454  retn
0x180046455  mov     rcx, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x18004645c  add     rcx, 1640h; this
0x180046463  call    ?IsLockedByCurrentThread@CTreeLock@@QEBA_NXZ; CTreeLock::IsLockedByCurrentThread(void)
0x180046468  test    al, al
0x18004646a  jnz     loc_1800463CC
0x180046470  mov     rdx, [rsp+68h]; void *
0x180046475  mov     ecx, 88980087h; int
0x18004647a  call    ModuleFailFastForHRESULT
0x180046480  mov     rax, [rcx+18h]
0x180046484  lea     rcx, [rsp+68h+arg_0]; this
0x180046489  mov     r12, [rax+330h]
0x180046490  sub     r12, 0FFFFFFFFFFFFFF80h
0x180046494  call    ?Start@QpcStopwatch@@QEAAXXZ; QpcStopwatch::Start(void)
0x180046499  mov     rbx, [rsp+68h+arg_0]
0x18004649e  jmp     loc_1800462F7
0x1800464a3  mov     rcx, [rsp+68h]; this
0x1800464a8  lea     r8, aOnecoreuapWind_88; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x1800464af  mov     edx, 571h; void *
0x1800464b4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800464ba  mov     rcx, [rsp+68h]; this
0x1800464bf  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x1800464c6  mov     r9d, ebx; char *
0x1800464c9  mov     edx, 2ACh; void *
0x1800464ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800464d3  mov     rcx, [rsp+68h]; this
0x1800464d8  lea     r8, aOnecoreuapWind_172; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x1800464df  mov     r9d, ebx; char *
0x1800464e2  mov     edx, 7B0h; void *
0x1800464e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800464ec  mov     [rsp+68h+var_40], 0
0x1800464f5  mov     [rsp+68h+var_48], 589h
0x1800464fd  jmp     loc_180046420
0x180046502  mov     rdx, [rdi+0C0h]; struct SubchannelMaskInfo *
0x180046509  test    rdx, rdx
0x18004650c  jz      loc_18004639C
0x180046512  cmp     byte ptr [rdx+4], 0
0x180046516  jbe     loc_18004639C
0x18004651c  mov     rcx, r14; this
0x18004651f  call    ?ApplyMaskToValue@CExpressionValue@@QEAAJPEBVSubchannelMaskInfo@@@Z; CExpressionValue::ApplyMaskToValue(SubchannelMaskInfo const *)
0x180046524  jmp     loc_18004639C
0x180046529  cmp     dword ptr [r14+40h], 12h
0x18004652e  jnz     loc_180046392
0x180046534  movaps  [rsp+68h+var_38], xmm6
0x180046539  mov     rcx, r14; this
0x18004653c  movss   xmm6, dword ptr [r14]
0x180046541  call    ?DestroyCurrent@CExpressionValue@@AEAAXXZ; CExpressionValue::DestroyCurrent(void)
0x180046546  mulss   xmm6, cs:__real@42652ee0
0x18004654e  mov     dword ptr [r14+40h], 12h
0x180046556  movss   dword ptr [r14], xmm6
0x18004655b  movaps  xmm6, [rsp+68h+var_38]
0x180046560  jmp     loc_180046392
0x180046565  xor     edx, edx
0x180046567  jmp     loc_1800463D0
0x18004656c  lea     rcx, [rsp+68h+arg_0]; this
0x180046571  call    ?GetElapsed@QpcStopwatch@@QEAA_JXZ; QpcStopwatch::GetElapsed(void)
0x180046576  mov     r8, rax
0x180046579  mov     edx, 3
0x18004657e  mov     rcx, r12
0x180046581  call    ?AddDurationSample@CExpressionPerformanceCounter@@QEAAXW4ExpressionPerformanceLabel@@_J@Z; CExpressionPerformanceCounter::AddDurationSample(ExpressionPerformanceLabel,__int64)
0x180046586  jmp     loc_18004635F
```
