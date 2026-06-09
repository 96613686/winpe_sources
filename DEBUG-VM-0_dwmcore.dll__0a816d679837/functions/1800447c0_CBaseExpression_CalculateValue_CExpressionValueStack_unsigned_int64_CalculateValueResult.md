# CBaseExpression::CalculateValue(CExpressionValueStack *,unsigned __int64,CalculateValueResult *)

- ea: `0x1800447c0`
- end: `0x180044dcb`
- name: `?CalculateValue@CBaseExpression@@IEAAJPEAVCExpressionValueStack@@_KPEAUCalculateValueResult@@@Z`
- size: `1547`
- prototype: `__int64 __fastcall(CBaseExpression *__hidden this, struct CExpressionValueStack *, unsigned __int64, struct CalculateValueResult *)`
- caller_count: `8`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034538`
- `0x180034970`
- `0x1800349e8`
- `0x180044580`
- `0x1800447c0`
- `0x18004c510`
- `0x18004cbd0`
- `0x18004d150`

## callees

- `0x180008e08`
- `0x180009bf8`
- `0x180042de0`
- `0x1800442e0`
- `0x180044350`
- `0x1800443b0`
- `0x1800447c0`
- `0x180044dd4`
- `0x180044e10`
- `0x180045720`
- `0x180045b20`
- `0x180049740`
- `0x1800497f4`
- `0x18004c470`
- `0x1800d5a20`
- `0x1801527f8`
- `0x1801607c0`
- `0x180163c00`
- `0x180169320`
- `0x1801fb960`
- `0x180200468`
- `0x180219e1c`
- `0x180228490`
- `0x180231ddc`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18029e011`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18029e011`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18029e01d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18029e01d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029e026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029e026`

## pseudocode

```c
__int64 __fastcall CBaseExpression::CalculateValue(
        CBaseExpression *this,
        struct CExpressionValueStack *a2,
        __int64 a3,
        struct CalculateValueResult *a4)
{
  unsigned int v4; // esi
  __int64 v5; // rbx
  __int64 v6; // rbp
  struct CalculateValueResult *v7; // r12
  __int64 v8; // r15
  int v11; // r13d
  CBaseExpression *v12; // rsi
  int Property; // eax
  CBaseExpression *v14; // rcx
  struct CExpressionValue *v15; // r15
  bool v16; // r12
  int v17; // r15d
  bool v18; // zf
  __int64 v20; // rbp
  __int64 v21; // rax
  CBaseExpression **v22; // rsi
  _QWORD *v23; // rsi
  _QWORD *v24; // rbx
  CExpressionManager *i; // r15
  __int64 v26; // rdx
  __int64 v27; // rcx
  CResource *TargetResource; // rax
  struct CResource *v29; // rsi
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdx
  int v33; // eax
  int v34; // eax
  CBaseExpression **v35; // r12
  unsigned __int64 v36; // r15
  __int64 Elapsed; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // eax
  HANDLE EventW; // rsi
  unsigned int v42; // [rsp+20h] [rbp-118h]
  unsigned int v43; // [rsp+20h] [rbp-118h]
  char v44; // [rsp+30h] [rbp-108h]
  __int64 v45; // [rsp+38h] [rbp-100h] BYREF
  CBaseExpression *v46; // [rsp+40h] [rbp-F8h]
  __int64 v47; // [rsp+48h] [rbp-F0h] BYREF
  CBaseExpression *v48; // [rsp+50h] [rbp-E8h]
  __int64 v49; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v50; // [rsp+60h] [rbp-D8h]
  struct CalculateValueResult *v51; // [rsp+68h] [rbp-D0h]
  WCHAR Name[64]; // [rsp+70h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v4 = 0;
  v51 = a4;
  v5 = 0;
  v50 = a3;
  v6 = 0;
  v47 = 0;
  v7 = a4;
  v8 = a3;
  v45 = 0;
  if ( *((_QWORD *)this + 21) == a3 )
    goto LABEL_28;
  if ( *((_DWORD *)this + 55) || CCommonRegistryData::LogExpressionPerfStats )
  {
    v12 = (CBaseExpression *)((char *)this + 24);
    v20 = *(_QWORD *)(*((_QWORD *)this + 3) + 816LL);
    QpcStopwatch::Start((QpcStopwatch *)&v47);
    v11 = *((_DWORD *)this + 56);
    v46 = v12;
    v6 = v20 + 128;
    if ( v6 )
    {
      QpcStopwatch::Start((QpcStopwatch *)&v45);
      v5 = v45;
    }
    v44 = 1;
  }
  else
  {
    v11 = *((_DWORD *)this + 56);
    v12 = (CBaseExpression *)((char *)this + 24);
    v46 = (CBaseExpression *)((char *)this + 24);
    v44 = 0;
  }
  if ( (*((_BYTE *)this + 216) & 0x10) == 0 )
  {
    v21 = *(_QWORD *)v12;
    v22 = (CBaseExpression **)*((_QWORD *)this + 29);
    if ( v22 != *((CBaseExpression ***)this + 30) )
    {
      v35 = (CBaseExpression **)*((_QWORD *)this + 30);
      v36 = *(_QWORD *)(v21 + 880);
      do
      {
        v48 = *v22;
        v49 = 0;
        v34 = CBaseExpression::CalculateValue(v48, a2, v36, (struct CalculateValueResult *)&v49);
        if ( v34 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x31C,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\baseexpression.cpp",
            (const char *)(unsigned int)v34,
            v42);
        CBaseExpression::EnsureExpressionIsUnregistered(v48);
        ++v22;
      }
      while ( v22 != v35 );
      v8 = v50;
      v7 = v51;
    }
    *((_BYTE *)this + 216) |= 0x10u;
  }
  if ( !v11 )
    *((_DWORD *)this + 56) = 4;
  if ( *((_DWORD *)a2 + 24) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x442,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\baseexpression.cpp",
      (const char *)a4);
  Property = (*(__int64 (__fastcall **)(CBaseExpression *, struct CExpressionValueStack *, struct CalculateValueResult *))(*(_QWORD *)this + 224LL))(
               this,
               a2,
               v7);
  v4 = Property;
  if ( Property < 0 )
  {
    v43 = 1092;
    goto LABEL_32;
  }
  *((_QWORD *)this + 21) = v8;
  if ( *((_BYTE *)v7 + 1) )
    goto LABEL_28;
  if ( v5 )
  {
    Elapsed = QpcStopwatch::GetElapsed((QpcStopwatch *)&v45);
    CExpressionPerformanceCounter::AddDurationSample(v6, 1, Elapsed);
    v5 = 0;
    v45 = 0;
  }
  v14 = v46;
  if ( v44 )
  {
    if ( (*((_BYTE *)this + 216) & 2) != 0 )
    {
      v32 = *(_QWORD *)(*(_QWORD *)v46 + 816LL);
      v33 = *((_DWORD *)this + 55);
      ++*(_DWORD *)(v32 + 420);
      if ( v33 )
        ++*(_DWORD *)(v32 + 424);
    }
  }
  if ( *((_DWORD *)a2 + 24) == 1 )
  {
    v15 = *(struct CExpressionValue **)a2;
    if ( *(_DWORD *)(*(_QWORD *)a2 + 64LL) != *((_DWORD *)this + 38) )
    {
      CBaseExpression::EnsureExpressionIsUnregistered(this);
      v4 = -2147467259;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4FD0, 2u, -2147467259, 0x46Au, 0);
      goto LABEL_28;
    }
    if ( CBaseExpression::IsExpressionValueValid(v14, *(const struct CExpressionValue **)a2) )
    {
LABEL_17:
      if ( v6 )
      {
        QpcStopwatch::Start((QpcStopwatch *)&v45);
        v5 = v45;
      }
      if ( *((_DWORD *)v15 + 16) != *((_DWORD *)this + 38) )
      {
        v4 = -2147024809;
        v17 = -2147024809;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024809, 0x25Au, 0);
LABEL_79:
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4FD0, 2u, v17, 0x492u, 0);
        goto LABEL_28;
      }
      v16 = 0;
      if ( *((_DWORD *)this + 55) )
        v16 = (unsigned __int8)CExpressionValue::operator==((char *)this + 80, v15) == 0;
      CExpressionValue::CopyFrom((CBaseExpression *)((char *)this + 80), v15);
      if ( v16 )
      {
        CBaseExpression::LogSetOutputValue(this);
        v40 = StringCchPrintfW(Name, 0x3Cu, L"DwmExpression_SetValue_%d", *((unsigned int *)this + 55));
        v17 = v40;
        if ( v40 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v40, 0x281u, 0);
LABEL_78:
          v4 = v17;
          goto LABEL_79;
        }
        EventW = CreateEventW(0, 1, 0, Name);
        SetEvent(EventW);
        CloseHandle(EventW);
      }
      if ( (*((_BYTE *)this + 216) & 3) != 3 || (v17 = CBaseExpression::SetOutputValueOnTarget(this), v17 >= 0) )
      {
        if ( v5 )
        {
          v38 = QpcStopwatch::GetElapsed((QpcStopwatch *)&v45);
          CExpressionPerformanceCounter::AddDurationSample(v6, 5, v38);
        }
        v4 = 0;
        goto LABEL_28;
      }
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v17, 0x291u, 0);
      goto LABEL_78;
    }
    v29 = CBaseExpression::ResolveTargetNoRef(this);
    if ( !v29 )
    {
      v4 = -2147024782;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4FD0, 2u, -2147024782, 0x474u, 0);
      goto LABEL_28;
    }
    v15 = CExpressionValueStack::PushStackValue(a2);
    v30 = *((_DWORD *)a2 + 24);
    if ( v30 )
      *((_DWORD *)a2 + 24) = v30 - 1;
    Property = CResource::TranslateAndGetProperty(v29, *((unsigned int *)this + 45), v15);
    v4 = Property;
    if ( Property < 0 )
    {
      v43 = 1147;
    }
    else
    {
      v31 = *((_QWORD *)this + 24);
      if ( !v31
        || !*(_BYTE *)(v31 + 4)
        || (Property = CExpressionValue::ApplyMaskToValue(v15, (const struct SubchannelMaskInfo *)v31),
            v4 = Property,
            Property >= 0) )
      {
        if ( *((_DWORD *)v15 + 16) != *((_DWORD *)this + 38) )
        {
          v4 = -2147024809;
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4FD0, 2u, -2147024809, 0x486u, 0);
          goto LABEL_28;
        }
        goto LABEL_17;
      }
      v43 = 1153;
    }
LABEL_32:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4FD0, 2u, Property, v43, 0);
    goto LABEL_28;
  }
  v23 = (_QWORD *)*((_QWORD *)this + 33);
  v24 = (_QWORD *)*((_QWORD *)this + 32);
  for ( i = *(CExpressionManager **)(*(_QWORD *)v14 + 816LL); v24 != v23; ++v24 )
  {
    TargetResource = (CResource *)CWeakReference<CGdiSpriteBitmap>::GetTargetResource(*v24);
    if ( TargetResource )
      CResource::RemoveAnimationProducer(TargetResource, this);
  }
  v26 = *((_QWORD *)this + 33);
  v27 = *((_QWORD *)this + 32);
  if ( v27 != v26 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(v27, v26);
    *((_QWORD *)this + 33) = *((_QWORD *)this + 32);
  }
  if ( (*((_BYTE *)this + 216) & 0x20) != 0 )
  {
    if ( (*((_BYTE *)this + 217) & 1) != 0 )
      CExpressionManager::EnsureAutoCompleteOnOccludedAnimationRemoved(i, this);
    CExpressionManager::UnregisterExpression(i, this);
    *((_BYTE *)this + 216) &= ~0x20u;
  }
  v4 = -2147467259;
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D4FD0, 2u, -2147467259, 0x461u, 0);
LABEL_28:
  v18 = v47 == 0;
  *((_DWORD *)a2 + 24) = 0;
  if ( !v18 )
  {
    v39 = QpcStopwatch::GetElapsed((QpcStopwatch *)&v47);
    CExpressionPerformanceCounter::AddDurationSample(v6, 0, v39);
  }
  return v4;
}

```

## disassembly

```asm
0x1800447c0  push    rbx
0x1800447c2  push    rbp
0x1800447c3  push    rsi
0x1800447c4  push    rdi
0x1800447c5  push    r12
0x1800447c7  push    r14
0x1800447c9  push    r15
0x1800447cb  sub     rsp, 100h
0x1800447d2  mov     rax, cs:__security_cookie
0x1800447d9  xor     rax, rsp
0x1800447dc  mov     [rsp+138h+var_48], rax
0x1800447e4  xor     esi, esi
0x1800447e6  mov     [rsp+138h+var_D0], r9
0x1800447eb  xor     ebx, ebx
0x1800447ed  mov     [rsp+138h+var_D8], r8
0x1800447f2  xor     ebp, ebp
0x1800447f4  mov     [rsp+138h+var_F0], rsi
0x1800447f9  mov     r12, r9
0x1800447fc  mov     r15, r8
0x1800447ff  mov     r14, rdx
0x180044802  mov     rdi, rcx
0x180044805  mov     [rsp+138h+var_100], rbx
0x18004480a  cmp     [rcx+0A8h], r8
0x180044811  jz      loc_180044968
0x180044817  mov     [rsp+138h+arg_10], r13
0x18004481f  cmp     [rcx+0DCh], ebx
0x180044825  jnz     loc_1800449CD
0x18004482b  cmp     cs:?LogExpressionPerfStats@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B, bl; details::CRegistryKey<bool,bool> const CCommonRegistryData::LogExpressionPerfStats
0x180044831  jnz     loc_1800449CD
0x180044837  mov     r13d, [rcx+0E0h]
0x18004483e  lea     rsi, [rcx+18h]
0x180044842  mov     [rsp+138h+var_F8], rsi
0x180044847  mov     [rsp+138h+var_108], bl
0x18004484b  test    byte ptr [rdi+0D8h], 10h
0x180044852  jz      loc_180044A2F
0x180044858  test    r13d, r13d
0x18004485b  mov     r13, [rsp+138h+arg_10]
0x180044863  jz      loc_180044A20
0x180044869  cmp     dword ptr [r14+60h], 0
0x18004486e  jnz     loc_180044A06
0x180044874  mov     rax, [rdi]
0x180044877  mov     r8, r12
0x18004487a  mov     rdx, r14
0x18004487d  mov     rcx, rdi
0x180044880  mov     rax, [rax+0E0h]
0x180044887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004488c  mov     esi, eax
0x18004488e  test    eax, eax
0x180044890  js      loc_1800449A0
0x180044896  mov     [rdi+0A8h], r15
0x18004489d  cmp     byte ptr [r12+1], 0
0x1800448a3  jnz     loc_180044968
0x1800448a9  test    rbx, rbx
0x1800448ac  jnz     loc_180044C50
0x1800448b2  cmp     [rsp+138h+var_108], 0
0x1800448b7  mov     rcx, [rsp+138h+var_F8]; this
0x1800448bc  jnz     loc_180044C76
0x1800448c2  mov     eax, [r14+60h]
0x1800448c6  cmp     eax, 1
0x1800448c9  jnz     loc_180044A5C
0x1800448cf  dec     eax
0x1800448d1  lea     rdx, [rax+rax*8]
0x1800448d5  mov     rax, [r14]
0x1800448d8  lea     r15, [rax+rdx*8]
0x1800448dc  mov     eax, [rdi+98h]
0x1800448e2  cmp     [r15+40h], eax
0x1800448e6  jnz     loc_180044CB0
0x1800448ec  mov     rdx, r15; struct CExpressionValue *
0x1800448ef  call    ?IsExpressionValueValid@CBaseExpression@@AEAA_NPEBVCExpressionValue@@@Z; CBaseExpression::IsExpressionValueValid(CExpressionValue const *)
0x1800448f4  test    al, al
0x1800448f6  jz      loc_180044AFB
0x1800448fc  test    rbp, rbp
0x1800448ff  jnz     loc_180044D32
0x180044905  mov     eax, [rdi+98h]
0x18004490b  cmp     [r15+40h], eax
0x18004490f  jnz     loc_180044D46
0x180044915  xor     r12b, r12b
0x180044918  lea     rsi, [rdi+50h]
0x18004491c  cmp     dword ptr [rdi+0DCh], 0
0x180044923  jnz     loc_180044BB0
0x180044929  mov     rdx, r15; struct CExpressionValue *
0x18004492c  mov     rcx, rsi; this
0x18004492f  call    ?CopyFrom@CExpressionValue@@QEAAXAEBV1@@Z; CExpressionValue::CopyFrom(CExpressionValue const &)
0x180044934  test    r12b, r12b
0x180044937  jnz     loc_18029DFD6
0x18004493d  movzx   eax, byte ptr [rdi+0D8h]
0x180044944  and     al, 3
0x180044946  cmp     al, 3
0x180044948  jnz     short loc_18004495D
0x18004494a  mov     rcx, rdi; this
0x18004494d  call    ?SetOutputValueOnTarget@CBaseExpression@@IEAAJXZ; CBaseExpression::SetOutputValueOnTarget(void)
0x180044952  mov     r15d, eax
0x180044955  test    eax, eax
0x180044957  js      loc_180044D77
0x18004495d  test    rbx, rbx
0x180044960  jnz     loc_180044D90
0x180044966  xor     esi, esi
0x180044968  cmp     [rsp+138h+var_F0], 0
0x18004496e  mov     dword ptr [r14+60h], 0
0x180044976  jnz     loc_180044DAF
0x18004497c  mov     eax, esi
0x18004497e  mov     rcx, [rsp+138h+var_48]
0x180044986  xor     rcx, rsp; StackCookie
0x180044989  call    __security_check_cookie
0x18004498e  add     rsp, 100h
0x180044995  pop     r15
0x180044997  pop     r14
0x180044999  pop     r12
0x18004499b  pop     rdi
0x18004499c  pop     rsi
0x18004499d  pop     rbp
0x18004499e  pop     rbx
0x18004499f  retn
0x1800449a0  mov     [rsp+138h+var_110], 0; void *
0x1800449a9  mov     [rsp+138h+var_118], 444h; unsigned int
0x1800449b1  mov     r9d, eax; int
0x1800449b4  mov     r8d, 2; unsigned int
0x1800449ba  lea     rdx, dword_1802D4FD0; int *
0x1800449c1  mov     ecx, 14h; unsigned int
0x1800449c6  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800449cb  jmp     short loc_180044968
0x1800449cd  mov     rax, [rcx+18h]
0x1800449d1  lea     rsi, [rcx+18h]
0x1800449d5  lea     rcx, [rsp+138h+var_F0]; this
0x1800449da  mov     rbp, [rax+330h]
0x1800449e1  call    ?Start@QpcStopwatch@@QEAAXXZ; QpcStopwatch::Start(void)
0x1800449e6  mov     r13d, [rdi+0E0h]
0x1800449ed  mov     [rsp+138h+var_F8], rsi
0x1800449f2  sub     rbp, 0FFFFFFFFFFFFFF80h
0x1800449f6  jnz     loc_180044C31
0x1800449fc  mov     [rsp+138h+var_108], 1
0x180044a01  jmp     loc_18004484B
0x180044a06  mov     rcx, [rsp+138h]; this
0x180044a0e  lea     r8, aOnecoreuapWind_172; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x180044a15  mov     edx, 442h; void *
0x180044a1a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180044a20  mov     dword ptr [rdi+0E0h], 4
0x180044a2a  jmp     loc_180044869
0x180044a2f  mov     rax, [rsi]
0x180044a32  mov     rsi, [rdi+0E8h]
0x180044a39  mov     rcx, [rax+370h]
0x180044a40  mov     rax, [rdi+0F0h]
0x180044a47  cmp     rsi, rax
0x180044a4a  jnz     loc_180044C45
0x180044a50  or      byte ptr [rdi+0D8h], 10h
0x180044a57  jmp     loc_180044858
0x180044a5c  mov     rax, [rcx]
0x180044a5f  mov     rsi, [rdi+108h]
0x180044a66  mov     rbx, [rdi+100h]
0x180044a6d  mov     r15, [rax+330h]
0x180044a74  cmp     rbx, rsi
0x180044a77  jnz     short loc_180044AB7
0x180044a79  mov     rdx, [rdi+108h]
0x180044a80  mov     rcx, [rdi+100h]
0x180044a87  cmp     rcx, rdx
0x180044a8a  jnz     loc_180044C98
0x180044a90  test    byte ptr [rdi+0D8h], 20h
0x180044a97  jnz     short loc_180044AD3
0x180044a99  mov     esi, 80004005h
0x180044a9e  mov     [rsp+138h+var_110], 0
0x180044aa7  mov     r9d, esi
0x180044aaa  mov     [rsp+138h+var_118], 461h
0x180044ab2  jmp     loc_1800449B4
0x180044ab7  mov     rcx, [rbx]
0x180044aba  call    ?GetTargetResource@?$CWeakReference@VCGdiSpriteBitmap@@@@QEBAPEAVCGdiSpriteBitmap@@XZ; CWeakReference<CGdiSpriteBitmap>::GetTargetResource(void)
0x180044abf  test    rax, rax
0x180044ac2  jnz     loc_180044C88
0x180044ac8  add     rbx, 8
0x180044acc  cmp     rbx, rsi
0x180044acf  jz      short loc_180044A79
0x180044ad1  jmp     short loc_180044AB7
0x180044ad3  test    byte ptr [rdi+0D9h], 1
0x180044ada  jz      short loc_180044AE7
0x180044adc  mov     rdx, rdi; struct CBaseExpression *
0x180044adf  mov     rcx, r15; this
0x180044ae2  call    ?EnsureAutoCompleteOnOccludedAnimationRemoved@CExpressionManager@@QEAAXPEAVCBaseExpression@@@Z; CExpressionManager::EnsureAutoCompleteOnOccludedAnimationRemoved(CBaseExpression *)
0x180044ae7  mov     rdx, rdi; struct CBaseExpression *
0x180044aea  mov     rcx, r15; this
0x180044aed  call    ?UnregisterExpression@CExpressionManager@@QEAAXPEAVCBaseExpression@@@Z; CExpressionManager::UnregisterExpression(CBaseExpression *)
0x180044af2  and     byte ptr [rdi+0D8h], 0DFh
0x180044af9  jmp     short loc_180044A99
0x180044afb  mov     rcx, rdi; this
0x180044afe  call    ?ResolveTargetNoRef@CBaseExpression@@IEBAPEAVCResource@@XZ; CBaseExpression::ResolveTargetNoRef(void)
0x180044b03  mov     rsi, rax
0x180044b06  test    rax, rax
0x180044b09  jz      loc_180044CD6
0x180044b0f  mov     rcx, r14; this
0x180044b12  call    ?PushStackValue@CExpressionValueStack@@QEAAPEAVCExpressionValue@@XZ; CExpressionValueStack::PushStackValue(void)
0x180044b17  mov     r15, rax
0x180044b1a  mov     eax, [r14+60h]
0x180044b1e  test    eax, eax
0x180044b20  jz      short loc_180044B28
0x180044b22  dec     eax
0x180044b24  mov     [r14+60h], eax
0x180044b28  mov     edx, [rdi+0B4h]
0x180044b2e  mov     r8, r15
0x180044b31  mov     rcx, rsi
0x180044b34  call    ?TranslateAndGetProperty@CResource@@QEAAJUDCOMPOSITION_PROPERTY_REFERENCE@@PEAVCExpressionValue@@@Z; CResource::TranslateAndGetProperty(DCOMPOSITION_PROPERTY_REFERENCE,CExpressionValue *)
0x180044b39  mov     esi, eax
0x180044b3b  test    eax, eax
0x180044b3d  js      loc_180044D1C
0x180044b43  mov     rdx, [rdi+0C0h]; struct SubchannelMaskInfo *
0x180044b4a  test    rdx, rdx
0x180044b4d  jz      short loc_180044B59
0x180044b4f  cmp     byte ptr [rdx+4], 0
0x180044b53  ja      loc_180044CF4
0x180044b59  mov     eax, [rdi+98h]
0x180044b5f  cmp     [r15+40h], eax
0x180044b63  jz      loc_1800448FC
0x180044b69  mov     esi, 80070057h
0x180044b6e  mov     [rsp+138h+var_110], 0
0x180044b77  mov     r9d, esi
0x180044b7a  mov     [rsp+138h+var_118], 486h
0x180044b82  jmp     loc_1800449B4
0x180044b87  mov     rax, [rcx]
0x180044b8a  mov     rdx, [rax+330h]
0x180044b91  mov     eax, [rdi+0DCh]
0x180044b97  inc     dword ptr [rdx+1A4h]
0x180044b9d  test    eax, eax
0x180044b9f  jz      loc_1800448C2
0x180044ba5  inc     dword ptr [rdx+1A8h]
0x180044bab  jmp     loc_1800448C2
0x180044bb0  mov     rdx, r15
0x180044bb3  mov     rcx, rsi
0x180044bb6  call    ??8CExpressionValue@@QEBA_NAEBV0@@Z; CExpressionValue::operator==(CExpressionValue const &)
0x180044bbb  test    al, al
0x180044bbd  jnz     loc_180044929
0x180044bc3  mov     r12b, 1
0x180044bc6  jmp     loc_180044929
0x180044bcb  mov     rax, [rsi]
0x180044bce  lea     r9, [rsp+138h+var_E0]; struct CalculateValueResult *
0x180044bd3  mov     rcx, rax; this
0x180044bd6  mov     [rsp+138h+var_E8], rax
0x180044bdb  mov     r8, r15; unsigned __int64
0x180044bde  mov     [rsp+138h+var_E0], 0
0x180044be7  mov     rdx, r14; struct CExpressionValueStack *
0x180044bea  call    ?CalculateValue@CBaseExpression@@IEAAJPEAVCExpressionValueStack@@_KPEAUCalculateValueResult@@@Z; CBaseExpression::CalculateValue(CExpressionValueStack *,unsigned __int64,CalculateValueResult *)
0x180044bef  test    eax, eax
0x180044bf1  jns     short loc_180044C0F
0x180044bf3  mov     rcx, [rsp+138h]; this
0x180044bfb  lea     r8, aOnecoreuapWind_172; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x180044c02  mov     r9d, eax; char *
0x180044c05  mov     edx, 31Ch; void *
0x180044c0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044c0f  mov     rcx, [rsp+138h+var_E8]; this
0x180044c14  call    ?EnsureExpressionIsUnregistered@CBaseExpression@@QEAAXXZ; CBaseExpression::EnsureExpressionIsUnregistered(void)
0x180044c19  add     rsi, 8
0x180044c1d  cmp     rsi, r12
0x180044c20  jnz     short loc_180044BCB
0x180044c22  mov     r15, [rsp+138h+var_D8]
0x180044c27  mov     r12, [rsp+138h+var_D0]
0x180044c2c  jmp     loc_180044A50
0x180044c31  lea     rcx, [rsp+138h+var_100]; this
0x180044c36  call    ?Start@QpcStopwatch@@QEAAXXZ; QpcStopwatch::Start(void)
0x180044c3b  mov     rbx, [rsp+138h+var_100]
0x180044c40  jmp     loc_1800449FC
0x180044c45  mov     r12, rax
0x180044c48  mov     r15, rcx
0x180044c4b  jmp     loc_180044BCB
0x180044c50  lea     rcx, [rsp+138h+var_100]; this
0x180044c55  call    ?GetElapsed@QpcStopwatch@@QEAA_JXZ; QpcStopwatch::GetElapsed(void)
0x180044c5a  mov     r8, rax
0x180044c5d  mov     edx, 1
0x180044c62  mov     rcx, rbp
0x180044c65  call    ?AddDurationSample@CExpressionPerformanceCounter@@QEAAXW4ExpressionPerformanceLabel@@_J@Z; CExpressionPerformanceCounter::AddDurationSample(ExpressionPerformanceLabel,__int64)
0x180044c6a  xor     ebx, ebx
0x180044c6c  mov     [rsp+138h+var_100], rbx
0x180044c71  jmp     loc_1800448B2
0x180044c76  test    byte ptr [rdi+0D8h], 2
0x180044c7d  jz      loc_1800448C2
0x180044c83  jmp     loc_180044B87
0x180044c88  mov     rdx, rdi; struct CBaseExpression *
0x180044c8b  mov     rcx, rax; this
0x180044c8e  call    ?RemoveAnimationProducer@CResource@@QEAAXPEAVCBaseExpression@@@Z; CResource::RemoveAnimationProducer(CBaseExpression *)
0x180044c93  jmp     loc_180044AC8
0x180044c98  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> *,wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>> &)
0x180044c9d  mov     rax, [rdi+100h]
0x180044ca4  mov     [rdi+108h], rax
0x180044cab  jmp     loc_180044A90
0x180044cb0  mov     rcx, rdi; this
0x180044cb3  call    ?EnsureExpressionIsUnregistered@CBaseExpression@@QEAAXXZ; CBaseExpression::EnsureExpressionIsUnregistered(void)
0x180044cb8  mov     esi, 80004005h
0x180044cbd  mov     [rsp+138h+var_110], 0
0x180044cc6  mov     r9d, esi
0x180044cc9  mov     [rsp+138h+var_118], 46Ah
0x180044cd1  jmp     loc_1800449B4
0x180044cd6  mov     esi, 80070072h
0x180044cdb  mov     [rsp+138h+var_110], 0
0x180044ce4  mov     r9d, esi
0x180044ce7  mov     [rsp+138h+var_118], 474h
0x180044cef  jmp     loc_1800449B4
0x180044cf4  mov     rcx, r15; this
0x180044cf7  call    ?ApplyMaskToValue@CExpressionValue@@QEAAJPEBVSubchannelMaskInfo@@@Z; CExpressionValue::ApplyMaskToValue(SubchannelMaskInfo const *)
0x180044cfc  mov     esi, eax
0x180044cfe  test    eax, eax
0x180044d00  jns     loc_180044B59
0x180044d06  mov     [rsp+138h+var_110], 0
0x180044d0f  mov     [rsp+138h+var_118], 481h
0x180044d17  jmp     loc_1800449B1
0x180044d1c  mov     [rsp+138h+var_110], 0
  ... truncated ...
```
