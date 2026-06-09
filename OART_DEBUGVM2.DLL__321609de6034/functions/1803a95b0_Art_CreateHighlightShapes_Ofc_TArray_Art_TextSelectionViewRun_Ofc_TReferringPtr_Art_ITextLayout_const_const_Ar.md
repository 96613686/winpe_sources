# Art::CreateHighlightShapes(Ofc::TArray<Art::TextSelectionViewRun> &,Ofc::TReferringPtr<Art::ITextLayout const> const &,Art::View::Info const &,Art::TextRange const &,Art::SelectionEffectType)

- ea: `0x1803a95b0`
- end: `0x1803a9d47`
- name: `?CreateHighlightShapes@Art@@YAXAEAV?$TArray@UTextSelectionViewRun@Art@@@Ofc@@AEBV?$TReferringPtr@$$CBVITextLayout@Art@@@3@AEBUInfo@View@1@AEBUTextRange@1@W4SelectionEffectType@1@@Z`
- size: `1943`
- prototype: `__int64 __usercall@<rax>(Ofc::CArrayImpl *this@<rcx>, int)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18018e33c`
- `0x180198c98`
- `0x1803a8f34`

## callees

- `0x180052708`
- `0x1800d7d70`
- `0x180106ef0`
- `0x1801b9690`
- `0x180279050`
- `0x180337260`
- `0x1803a95b0`
- `0x1803a9d48`
- `0x1806896e0`
- `0x1806bc4f0`

## import_xrefs

- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x1803a9b6a`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x1803a9b6a`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1803a98ec`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1803a9a75`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1803a9b80`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1803a98ec`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1803a9a75`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1803a9b80`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x1803a9802`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x1803a98ac`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x1803a9a35`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x1803a9802`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x1803a98ac`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x1803a9a35`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z` at `0x1803a9886`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z` at `0x1803a9a0f`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z` at `0x1803a9886`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z` at `0x1803a9a0f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803a9d02`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803a9d02`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1803a99c9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1803a9b5a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1803a99c9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1803a9b5a`

## pseudocode

```c
__int64 __fastcall Art::CreateHighlightShapes(
        Ofc::CArrayImpl *this,
        Ofc::CProxyPtrImpl **a2,
        _QWORD *a3,
        __int64 *a4,
        int a5)
{
  Ofc::CProxyPtrImpl *v8; // rcx
  void *v9; // rax
  __int64 result; // rax
  void *v11; // r10
  __int64 (__fastcall *v12)(void *, __int64 *, double *, __int64 *, char); // rax
  __int64 v13; // rcx
  __m128d v14; // xmm1
  double v15; // xmm2_8
  char v16; // di
  __int64 *v17; // rax
  __int64 v18; // r15
  double v19; // xmm7_8
  double v20; // xmm6_8
  void *v21; // rax
  __int64 v22; // rbx
  void *v23; // rax
  __int64 LayoutToHostMatrix; // rax
  __int64 v25; // rax
  double *v26; // rax
  double v27; // xmm5_8
  double v28; // xmm4_8
  double v29; // xmm3_8
  double v30; // xmm2_8
  double v31; // xmm1_8
  __int64 *v32; // rax
  __int64 v33; // rsi
  __int64 v34; // rdx
  __int64 v35; // r8
  __int128 *SelectionColor; // rax
  __int64 v37; // rax
  __int64 v38; // rbx
  void *v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rbx
  void *v42; // rdx
  __int64 v43; // rbx
  __int128 v44; // xmm0
  void *Checked; // rax
  int v46; // eax
  __int64 *v47; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+40h] [rbp-C8h] BYREF
  double v49; // [rsp+48h] [rbp-C0h] BYREF
  double v50; // [rsp+50h] [rbp-B8h]
  __int64 *v51; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v52; // [rsp+60h] [rbp-A8h] BYREF
  __m128i si128; // [rsp+70h] [rbp-98h] BYREF
  __int64 v54; // [rsp+80h] [rbp-88h] BYREF
  __m128i v55; // [rsp+88h] [rbp-80h] BYREF
  __m128i v56; // [rsp+98h] [rbp-70h]
  __int128 v57; // [rsp+A8h] [rbp-60h]
  __int64 v58; // [rsp+B8h] [rbp-50h]
  __int64 v59; // [rsp+C0h] [rbp-48h]
  __int16 v60; // [rsp+C8h] [rbp-40h]
  char v61; // [rsp+CAh] [rbp-3Eh]
  int v62; // [rsp+D0h] [rbp-38h]
  __int128 v63; // [rsp+D8h] [rbp-30h]
  char v64; // [rsp+E8h] [rbp-20h]
  char v65; // [rsp+F0h] [rbp-18h]
  __int64 v66; // [rsp+F8h] [rbp-10h]
  double v67[6]; // [rsp+100h] [rbp-8h] BYREF
  char v68[48]; // [rsp+130h] [rbp+28h] BYREF
  char v69[48]; // [rsp+160h] [rbp+58h] BYREF
  char v70[48]; // [rsp+190h] [rbp+88h] BYREF
  char v71[88]; // [rsp+1C0h] [rbp+B8h] BYREF
  __int64 v72; // [rsp+260h] [rbp+158h] BYREF

  v72 = *a4;
  v8 = *a2;
  if ( SHIDWORD(v72) <= 0 )
  {
    Checked = Ofc::CProxyPtrImpl::GetChecked(v8);
    v46 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)Checked + 200LL))(Checked);
    if ( (int)v72 <= v46 )
      goto LABEL_4;
    result = 0;
  }
  else
  {
    v9 = Ofc::CProxyPtrImpl::GetChecked(v8);
    result = (*(unsigned __int8 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v9 + 208LL))(v9, &v72);
  }
  if ( !(_DWORD)result )
    return result;
LABEL_4:
  v11 = Ofc::CProxyPtrImpl::GetChecked(*a2);
  v12 = *(__int64 (__fastcall **)(void *, __int64 *, double *, __int64 *, char))(*(_QWORD *)v11 + 312LL);
  v13 = a3[14];
  v14 = *(__m128d *)(v13 + 128);
  v15 = _mm_unpackhi_pd(v14, v14).m128d_f64[0] * *(float *)(v13 + 124) / 914400.0;
  v49 = *(float *)(v13 + 120) * v14.m128d_f64[0] / 914400.0;
  v50 = v15;
  v16 = 1;
  v17 = (__int64 *)v12(v11, &v48, &v49, &v72, 1);
  v18 = *v17;
  *v17 = 0;
  v66 = v18;
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
  v19 = *(float *)(a3[13] + 124LL) * *(double *)(a3[13] + 136LL) / 914400.0;
  v20 = *(float *)(a3[12] + 120LL) * *(double *)(a3[12] + 128LL) / 914400.0;
  v21 = Ofc::CProxyPtrImpl::GetChecked(*a2);
  v22 = (*(__int64 (__fastcall **)(void *, char *))(*(_QWORD *)v21 + 328LL))(v21, v68);
  v23 = Ofc::CProxyPtrImpl::GetChecked(*a2);
  LayoutToHostMatrix = Art::ITextLayout::GetLayoutToHostMatrix(v23, v69);
  v25 = Math::Inverse<double>(v70, LayoutToHostMatrix);
  v26 = (double *)Math::operator*<double,double,double>(v71, v25, v22);
  v27 = v19 * v26[5];
  v28 = v20 * v26[4];
  v29 = v26[3];
  v30 = v26[2];
  v31 = v26[1];
  v67[0] = v20 * *v26;
  v67[1] = v31 * v19;
  v67[2] = v20 * v30;
  v67[3] = v29 * v19;
  v67[4] = v28;
  v67[5] = v27;
  v32 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64 **, double *))(*(_QWORD *)v18 + 128LL))(v18, &v47, v67);
  v33 = *v32;
  *v32 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  v66 = v33;
  if ( v47 )
    (*(void (__fastcall **)(__int64 *))(*v47 + 8))(v47);
  Gfx::IFigureStyle::Create(&v54);
  v52 = 0;
  switch ( a5 )
  {
    case 1:
      SelectionColor = (__int128 *)Art::GetSelectionColor(&si128);
      v16 = 0;
LABEL_10:
      v52 = *SelectionColor;
LABEL_11:
      v49 = 0.0;
      v50 = -0.0;
      *(_QWORD *)Ofc::CArrayImpl::NewTop<double>(&v49) = 0x3FC3333333333333LL;
      *(_QWORD *)Ofc::CArrayImpl::NewTop<double>(&v49) = 0x3FE0000000000000LL;
      GEL::IPen::Create(&v47);
      (*(void (__fastcall **)(__int64 *, double *))(*v47 + 136))(v47, &v49);
      Gfx::IFigureStyle::Create(&v51);
      v37 = *v51;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      (*(void (__fastcall **)(__int64 *, __int64 *, __m128i *))(v37 + 112))(v51, v47, &si128);
      Gfx::IFigureShapeBuilder::Create(&v48, v33, v51, 0);
      v55 = _mm_load_si128((const __m128i *)&_xmm);
      v56 = _mm_load_si128((const __m128i *)&_xmm);
      v57 = 0;
      v58 = v72;
      v38 = v48;
      v59 = v48;
      if ( v48 )
        (**(void (__fastcall ***)(__int64))v48)(v48);
      v60 = 0;
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      v65 = v16;
      Ofc::TArray<Art::TextSelectionViewRun>::Add<Art::TextSelectionViewRun>(this, (struct Art::TextViewRun *)&v55);
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
      if ( v51 )
        (*(void (__fastcall **)(__int64 *))(*v51 + 8))(v51);
      if ( v47 )
        (*(void (__fastcall **)(__int64 *))(*v47 + 8))(v47);
      if ( v49 != 0.0 )
        Mso::Memory::Free(*(Mso::Memory **)&v49, v39);
      v49 = 0.0;
      v50 = -0.0;
      *(_QWORD *)Ofc::CArrayImpl::NewTop<double>(&v49) = 0x3FC47AE147AE147BLL;
      *(_QWORD *)Ofc::CArrayImpl::NewTop<double>(&v49) = 0x3FE0000000000000LL;
      GEL::IPen::Create(&v51);
      (*(void (__fastcall **)(__int64 *, double *))(*v51 + 136))(v51, &v49);
      Gfx::IFigureStyle::Create(&v47);
      v40 = *v47;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      (*(void (__fastcall **)(__int64 *, __int64 *, __m128i *))(v40 + 112))(v47, v51, &si128);
      Gfx::IFigureShapeBuilder::Create(&v48, v33, v47, 0);
      v55 = _mm_load_si128((const __m128i *)&_xmm);
      v56 = _mm_load_si128((const __m128i *)&_xmm);
      v57 = 0;
      v58 = v72;
      v41 = v48;
      v59 = v48;
      if ( v48 )
        (**(void (__fastcall ***)(__int64))v48)(v48);
      v60 = 0;
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      v65 = v16;
      Ofc::TArray<Art::TextSelectionViewRun>::Add<Art::TextSelectionViewRun>(this, (struct Art::TextViewRun *)&v55);
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
      if ( v47 )
        (*(void (__fastcall **)(__int64 *))(*v47 + 8))(v47);
      if ( v51 )
        (*(void (__fastcall **)(__int64 *))(*v51 + 8))(v51);
      if ( v49 != 0.0 )
        Mso::Memory::Free(*(Mso::Memory **)&v49, v42);
      Gfx::IFigureStyle::Create(&v47, &v52);
      Gfx::IFigureShapeBuilder::Create(&v48, v33, v47, 0);
      v55 = _mm_load_si128((const __m128i *)&_xmm);
      v56 = _mm_load_si128((const __m128i *)&_xmm);
      v57 = 0;
      v58 = v72;
      v43 = v48;
      v59 = v48;
      if ( v48 )
        (**(void (__fastcall ***)(__int64))v48)(v48);
      v60 = 0;
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      v65 = v16;
      result = Ofc::TArray<Art::TextSelectionViewRun>::Add<Art::TextSelectionViewRun>(
                 this,
                 (struct Art::TextViewRun *)&v55);
      if ( v43 )
        result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
      if ( v48 )
        result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
      if ( v47 )
        result = (*(__int64 (__fastcall **)(__int64 *))(*v47 + 8))(v47);
      goto LABEL_43;
    case 2:
    case 3:
      v44 = xmmword_180C14838;
LABEL_50:
      v52 = v44;
      goto LABEL_11;
    case 4:
      v44 = xmmword_180C474F8;
      goto LABEL_50;
    case 5:
      v35 = 0;
      LOBYTE(v34) = 2;
      goto LABEL_65;
    case 6:
      v35 = 0;
      goto LABEL_68;
    case 7:
      v35 = 0;
      goto LABEL_63;
    case 8:
      LOBYTE(v35) = 1;
LABEL_68:
      v34 = 0;
      goto LABEL_65;
    case 9:
      LOBYTE(v35) = 1;
LABEL_63:
      LOBYTE(v34) = 1;
LABEL_65:
      SelectionColor = (__int128 *)sub_1806896E0(&si128, v34, v35);
      goto LABEL_10;
  }
  result = MsoShipAssertTagProc(3743879);
LABEL_43:
  if ( v54 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v54 + 8LL))(v54);
  if ( v33 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
  return result;
}

```

## disassembly

```asm
0x1803a95b0  mov     rax, rsp
0x1803a95b3  mov     [rax+8], rbx
0x1803a95b7  mov     [rax+10h], rsi
0x1803a95bb  mov     [rax+18h], rdi
0x1803a95bf  push    rbp
0x1803a95c0  push    r12
0x1803a95c2  push    r13
0x1803a95c4  push    r14
0x1803a95c6  push    r15
0x1803a95c8  lea     rbp, [rax-138h]
0x1803a95cf  sub     rsp, 210h
0x1803a95d6  movaps  xmmword ptr [rax-38h], xmm6
0x1803a95da  movaps  xmmword ptr [rax-48h], xmm7
0x1803a95de  mov     rbx, r8
0x1803a95e1  mov     rsi, rdx
0x1803a95e4  mov     r14, rcx
0x1803a95e7  mov     rax, [r9]
0x1803a95ea  mov     [rbp+130h+arg_18], rax
0x1803a95f1  shr     rax, 20h
0x1803a95f5  xor     r12d, r12d
0x1803a95f8  mov     rcx, [rdx]; this
0x1803a95fb  test    eax, eax
0x1803a95fd  jle     loc_1803A9CAB
0x1803a9603  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803a9608  mov     r8, rax
0x1803a960b  mov     rcx, [rax]
0x1803a960e  mov     rax, [rcx+0D0h]
0x1803a9615  lea     rdx, [rbp+130h+arg_18]
0x1803a961c  mov     rcx, r8
0x1803a961f  call    cs:__guard_dispatch_icall_fptr
0x1803a9625  movzx   eax, al
0x1803a9628  test    eax, eax
0x1803a962a  jz      loc_1803A9C6A
0x1803a9630  mov     rcx, [rsi]; this
0x1803a9633  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803a9638  mov     r10, rax
0x1803a963b  mov     rcx, [rax]
0x1803a963e  mov     rax, [rcx+138h]
0x1803a9645  mov     rcx, [rbx+70h]
0x1803a9649  movups  xmm1, xmmword ptr [rcx+80h]
0x1803a9650  movss   xmm0, dword ptr [rcx+7Ch]
0x1803a9655  cvtps2pd xmm0, xmm0
0x1803a9658  movaps  xmm2, xmm1
0x1803a965b  unpckhpd xmm2, xmm1
0x1803a965f  mulsd   xmm2, xmm0
0x1803a9663  divsd   xmm2, cs:__real@412be7c000000000
0x1803a966b  movss   xmm0, dword ptr [rcx+78h]
0x1803a9670  cvtps2pd xmm0, xmm0
0x1803a9673  mulsd   xmm0, xmm1
0x1803a9677  divsd   xmm0, cs:__real@412be7c000000000
0x1803a967f  movsd   [rsp+230h+var_1F0], xmm0
0x1803a9685  movsd   [rsp+230h+var_1E8], xmm2
0x1803a968b  mov     dil, 1
0x1803a968e  mov     [rsp+230h+var_210], dil
0x1803a9693  lea     r9, [rbp+130h+arg_18]
0x1803a969a  lea     r8, [rsp+230h+var_1F0]
0x1803a969f  lea     rdx, [rsp+230h+var_1F8]
0x1803a96a4  mov     rcx, r10
0x1803a96a7  call    cs:__guard_dispatch_icall_fptr
0x1803a96ad  mov     r15, [rax]
0x1803a96b0  mov     [rax], r12
0x1803a96b3  mov     [rbp+130h+var_140], r15
0x1803a96b7  mov     rcx, [rsp+230h+var_1F8]
0x1803a96bc  test    rcx, rcx
0x1803a96bf  jz      short loc_1803A96CE
0x1803a96c1  mov     rax, [rcx]
0x1803a96c4  mov     rax, [rax+8]
0x1803a96c8  call    cs:__guard_dispatch_icall_fptr
0x1803a96ce  mov     rax, [rbx+68h]
0x1803a96d2  movss   xmm7, dword ptr [rax+7Ch]
0x1803a96d7  cvtps2pd xmm7, xmm7
0x1803a96da  mulsd   xmm7, qword ptr [rax+88h]
0x1803a96e2  divsd   xmm7, cs:__real@412be7c000000000
0x1803a96ea  mov     rax, [rbx+60h]
0x1803a96ee  movss   xmm6, dword ptr [rax+78h]
0x1803a96f3  cvtps2pd xmm6, xmm6
0x1803a96f6  mulsd   xmm6, qword ptr [rax+80h]
0x1803a96fe  divsd   xmm6, cs:__real@412be7c000000000
0x1803a9706  mov     rcx, [rsi]; this
0x1803a9709  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803a970e  mov     r8, rax
0x1803a9711  mov     rcx, [rax]
0x1803a9714  mov     rax, [rcx+148h]
0x1803a971b  lea     rdx, [rbp+130h+var_108]
0x1803a971f  mov     rcx, r8
0x1803a9722  call    cs:__guard_dispatch_icall_fptr
0x1803a9728  mov     rbx, rax
0x1803a972b  mov     rcx, [rsi]; this
0x1803a972e  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803a9733  lea     rdx, [rbp+130h+var_D8]
0x1803a9737  mov     rcx, rax
0x1803a973a  call    ?GetLayoutToHostMatrix@ITextLayout@Art@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Art::ITextLayout::GetLayoutToHostMatrix(void)
0x1803a973f  mov     rdx, rax
0x1803a9742  lea     rcx, [rbp+130h+var_A8]
0x1803a9749  call    ??$Inverse@N@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@@Z; Math::Inverse<double>(Math::TAffine3x3<double> const &)
0x1803a974e  mov     r8, rbx
0x1803a9751  mov     rdx, rax
0x1803a9754  lea     rcx, [rbp+130h+var_78]
0x1803a975b  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x1803a9760  movaps  xmm5, xmm7
0x1803a9763  mulsd   xmm5, qword ptr [rax+28h]
0x1803a9768  movaps  xmm4, xmm6
0x1803a976b  mulsd   xmm4, qword ptr [rax+20h]
0x1803a9770  movsd   xmm3, qword ptr [rax+18h]
0x1803a9775  movsd   xmm2, qword ptr [rax+10h]
0x1803a977a  movsd   xmm1, qword ptr [rax+8]
0x1803a977f  movaps  xmm0, xmm6
0x1803a9782  mulsd   xmm0, qword ptr [rax]
0x1803a9786  movsd   [rbp+130h+var_138], xmm0
0x1803a978b  mulsd   xmm1, xmm7
0x1803a978f  movsd   [rbp+130h+var_130], xmm1
0x1803a9794  mulsd   xmm6, xmm2
0x1803a9798  movsd   [rbp+130h+var_128], xmm6
0x1803a979d  mulsd   xmm3, xmm7
0x1803a97a1  movsd   [rbp+130h+var_120], xmm3
0x1803a97a6  movsd   [rbp+130h+var_118], xmm4
0x1803a97ab  movsd   [rbp+130h+var_110], xmm5
0x1803a97b0  mov     rax, [r15]
0x1803a97b3  lea     r8, [rbp+130h+var_138]
0x1803a97b7  lea     rdx, [rsp+230h+var_200]
0x1803a97bc  mov     rcx, r15
0x1803a97bf  mov     rax, [rax+80h]
0x1803a97c6  call    cs:__guard_dispatch_icall_fptr
0x1803a97cc  mov     rsi, [rax]
0x1803a97cf  mov     [rax], r12
0x1803a97d2  mov     rax, [r15]
0x1803a97d5  mov     rcx, r15
0x1803a97d8  mov     rax, [rax+8]
0x1803a97dc  call    cs:__guard_dispatch_icall_fptr
0x1803a97e2  mov     [rbp+130h+var_140], rsi
0x1803a97e6  mov     rcx, [rsp+230h+var_200]
0x1803a97eb  test    rcx, rcx
0x1803a97ee  jz      short loc_1803A97FD
0x1803a97f0  mov     rax, [rcx]
0x1803a97f3  mov     rax, [rax+8]
0x1803a97f7  call    cs:__guard_dispatch_icall_fptr
0x1803a97fd  lea     rcx, [rsp+230h+var_1B8]
0x1803a9802  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ; Gfx::IFigureStyle::Create(void)
0x1803a9808  nop
0x1803a9809  xorps   xmm0, xmm0
0x1803a980c  movups  [rsp+230h+var_1E0+8], xmm0
0x1803a9811  mov     ecx, [rbp+130h+arg_20]
0x1803a9817  sub     ecx, 1
0x1803a981a  jnz     loc_1803A9C95
0x1803a9820  lea     rcx, [rsp+230h+var_1D0+8]
0x1803a9825  call    ?GetSelectionColor@Art@@YA?AUColor@GEL@@XZ; Art::GetSelectionColor(void)
0x1803a982a  mov     dil, r12b
0x1803a982d  movups  xmm0, xmmword ptr [rax]
0x1803a9830  movdqu  [rsp+230h+var_1E0+8], xmm0
0x1803a9836  mov     [rsp+230h+var_1F0], r12
0x1803a983b  mov     dword ptr [rsp+230h+var_1E8], r12d
0x1803a9840  mov     r15d, 80000000h
0x1803a9846  mov     dword ptr [rsp+230h+var_1E8+4], r15d
0x1803a984b  lea     rcx, [rsp+230h+var_1F0]
0x1803a9850  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x1803a9855  mov     rcx, 3FC3333333333333h
0x1803a985f  mov     [rax], rcx
0x1803a9862  lea     rcx, [rsp+230h+var_1F0]
0x1803a9867  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x1803a986c  mov     r13, 3FE0000000000000h
0x1803a9876  mov     [rax], r13
0x1803a9879  movsd   xmm1, cs:__real@4010000000000000
0x1803a9881  lea     rcx, [rsp+230h+var_200]
0x1803a9886  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z; GEL::IPen::Create(double)
0x1803a988c  nop
0x1803a988d  mov     rcx, [rsp+230h+var_200]
0x1803a9892  mov     rax, [rcx]
0x1803a9895  lea     rdx, [rsp+230h+var_1F0]
0x1803a989a  mov     rax, [rax+88h]
0x1803a98a1  call    cs:__guard_dispatch_icall_fptr
0x1803a98a7  lea     rcx, [rsp+230h+var_1E0]
0x1803a98ac  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ; Gfx::IFigureStyle::Create(void)
0x1803a98b2  nop
0x1803a98b3  mov     rcx, qword ptr [rsp+230h+var_1E0]
0x1803a98b8  mov     rax, [rcx]
0x1803a98bb  movdqa  xmm0, cs:__xmm@3e99999a3f8000003f8000003f800000
0x1803a98c3  movups  xmmword ptr [rsp+230h+var_1D0+8], xmm0
0x1803a98c8  lea     r8, [rsp+230h+var_1D0+8]
0x1803a98cd  mov     rdx, [rsp+230h+var_200]
0x1803a98d2  mov     rax, [rax+70h]
0x1803a98d6  call    cs:__guard_dispatch_icall_fptr
0x1803a98dc  xor     r9d, r9d
0x1803a98df  mov     r8, qword ptr [rsp+230h+var_1E0]
0x1803a98e4  mov     rdx, rsi
0x1803a98e7  lea     rcx, [rsp+230h+var_1F8]
0x1803a98ec  call    cs:__imp_?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z; Gfx::IFigureShapeBuilder::Create(GEL::IPath const &,Gfx::IFigureStyle *,Gfx::IEffectParams const *)
0x1803a98f2  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1803a98fa  movups  [rbp+130h+var_1B0], xmm0
0x1803a98fe  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1803a9906  movups  [rbp+130h+var_1A0], xmm1
0x1803a990a  xorps   xmm0, xmm0
0x1803a990d  movups  [rbp+130h+var_190], xmm0
0x1803a9911  mov     rax, [rbp+130h+arg_18]
0x1803a9918  mov     [rbp+130h+var_180], rax
0x1803a991c  mov     rbx, [rsp+230h+var_1F8]
0x1803a9921  mov     [rbp+130h+var_178], rbx
0x1803a9925  test    rbx, rbx
0x1803a9928  jz      short loc_1803A9939
0x1803a992a  mov     rax, [rbx]
0x1803a992d  mov     rcx, rbx
0x1803a9930  mov     rax, [rax]
0x1803a9933  call    cs:__guard_dispatch_icall_fptr
0x1803a9939  mov     [rbp+130h+var_170], r12w
0x1803a993e  mov     [rbp+130h+var_16E], r12b
0x1803a9942  mov     [rbp+130h+var_168], r12d
0x1803a9946  xorps   xmm0, xmm0
0x1803a9949  movups  [rbp+130h+var_160], xmm0
0x1803a994d  mov     [rbp+130h+var_150], r12b
0x1803a9951  mov     [rbp+130h+var_148], dil
0x1803a9955  lea     rdx, [rbp+130h+var_1B0]; struct Art::TextViewRun *
0x1803a9959  mov     rcx, r14; this
0x1803a995c  call    ??$Add@UTextSelectionViewRun@Art@@@?$TArray@UTextSelectionViewRun@Art@@@Ofc@@QEAAXAEBUTextSelectionViewRun@Art@@@Z; Ofc::TArray<Art::TextSelectionViewRun>::Add<Art::TextSelectionViewRun>(Art::TextSelectionViewRun const &)
0x1803a9961  test    rbx, rbx
0x1803a9964  jz      short loc_1803A9977
0x1803a9966  mov     rax, [rbx]
0x1803a9969  mov     rcx, rbx
0x1803a996c  mov     rax, [rax+8]
0x1803a9970  call    cs:__guard_dispatch_icall_fptr
0x1803a9976  nop
0x1803a9977  mov     rcx, [rsp+230h+var_1F8]
0x1803a997c  test    rcx, rcx
0x1803a997f  jz      short loc_1803A998F
0x1803a9981  mov     rax, [rcx]
0x1803a9984  mov     rax, [rax+8]
0x1803a9988  call    cs:__guard_dispatch_icall_fptr
0x1803a998e  nop
0x1803a998f  mov     rcx, qword ptr [rsp+230h+var_1E0]
0x1803a9994  test    rcx, rcx
0x1803a9997  jz      short loc_1803A99A7
0x1803a9999  mov     rax, [rcx]
0x1803a999c  mov     rax, [rax+8]
0x1803a99a0  call    cs:__guard_dispatch_icall_fptr
0x1803a99a6  nop
0x1803a99a7  mov     rcx, [rsp+230h+var_200]
0x1803a99ac  test    rcx, rcx
0x1803a99af  jz      short loc_1803A99BF
0x1803a99b1  mov     rax, [rcx]
0x1803a99b4  mov     rax, [rax+8]
0x1803a99b8  call    cs:__guard_dispatch_icall_fptr
0x1803a99be  nop
0x1803a99bf  mov     rcx, [rsp+230h+var_1F0]
0x1803a99c4  test    rcx, rcx
0x1803a99c7  jz      short loc_1803A99CF
0x1803a99c9  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1803a99cf  mov     [rsp+230h+var_1F0], r12
0x1803a99d4  mov     dword ptr [rsp+230h+var_1E8], r12d
0x1803a99d9  mov     dword ptr [rsp+230h+var_1E8+4], r15d
0x1803a99de  lea     rcx, [rsp+230h+var_1F0]
0x1803a99e3  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x1803a99e8  mov     rcx, 3FC47AE147AE147Bh
0x1803a99f2  mov     [rax], rcx
0x1803a99f5  lea     rcx, [rsp+230h+var_1F0]
0x1803a99fa  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x1803a99ff  mov     [rax], r13
0x1803a9a02  movsd   xmm1, cs:__real@4000000000000000
0x1803a9a0a  lea     rcx, [rsp+230h+var_1E0]
0x1803a9a0f  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z; GEL::IPen::Create(double)
0x1803a9a15  nop
0x1803a9a16  mov     rcx, qword ptr [rsp+230h+var_1E0]
0x1803a9a1b  mov     rax, [rcx]
0x1803a9a1e  lea     rdx, [rsp+230h+var_1F0]
0x1803a9a23  mov     rax, [rax+88h]
0x1803a9a2a  call    cs:__guard_dispatch_icall_fptr
0x1803a9a30  lea     rcx, [rsp+230h+var_200]
0x1803a9a35  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ; Gfx::IFigureStyle::Create(void)
0x1803a9a3b  nop
0x1803a9a3c  mov     rcx, [rsp+230h+var_200]
0x1803a9a41  mov     rax, [rcx]
0x1803a9a44  movdqa  xmm0, cs:__xmm@3ecccccd3f8000003f8000003f800000
0x1803a9a4c  movups  xmmword ptr [rsp+230h+var_1D0+8], xmm0
0x1803a9a51  lea     r8, [rsp+230h+var_1D0+8]
0x1803a9a56  mov     rdx, qword ptr [rsp+230h+var_1E0]
0x1803a9a5b  mov     rax, [rax+70h]
0x1803a9a5f  call    cs:__guard_dispatch_icall_fptr
0x1803a9a65  xor     r9d, r9d
0x1803a9a68  mov     r8, [rsp+230h+var_200]
0x1803a9a6d  mov     rdx, rsi
0x1803a9a70  lea     rcx, [rsp+230h+var_1F8]
0x1803a9a75  call    cs:__imp_?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z; Gfx::IFigureShapeBuilder::Create(GEL::IPath const &,Gfx::IFigureStyle *,Gfx::IEffectParams const *)
0x1803a9a7b  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1803a9a83  movups  [rbp+130h+var_1B0], xmm0
0x1803a9a87  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1803a9a8f  movups  [rbp+130h+var_1A0], xmm1
0x1803a9a93  xorps   xmm0, xmm0
0x1803a9a96  movups  [rbp+130h+var_190], xmm0
0x1803a9a9a  mov     rax, [rbp+130h+arg_18]
0x1803a9aa1  mov     [rbp+130h+var_180], rax
0x1803a9aa5  mov     rbx, [rsp+230h+var_1F8]
0x1803a9aaa  mov     [rbp+130h+var_178], rbx
0x1803a9aae  test    rbx, rbx
0x1803a9ab1  jz      short loc_1803A9AC2
0x1803a9ab3  mov     rax, [rbx]
0x1803a9ab6  mov     rcx, rbx
0x1803a9ab9  mov     rax, [rax]
0x1803a9abc  call    cs:__guard_dispatch_icall_fptr
0x1803a9ac2  mov     [rbp+130h+var_170], r12w
0x1803a9ac7  mov     [rbp+130h+var_16E], r12b
0x1803a9acb  mov     [rbp+130h+var_168], r12d
0x1803a9acf  xorps   xmm0, xmm0
0x1803a9ad2  movups  [rbp+130h+var_160], xmm0
  ... truncated ...
```
