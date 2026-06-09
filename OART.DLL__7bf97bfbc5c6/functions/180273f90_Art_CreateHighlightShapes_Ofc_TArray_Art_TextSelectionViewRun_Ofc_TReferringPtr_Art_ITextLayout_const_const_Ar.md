# Art::CreateHighlightShapes(Ofc::TArray<Art::TextSelectionViewRun> &,Ofc::TReferringPtr<Art::ITextLayout const> const &,Art::View::Info const &,Art::TextRange const &,Art::SelectionEffectType)

- ea: `0x180273f90`
- end: `0x180274727`
- name: `?CreateHighlightShapes@Art@@YAXAEAV?$TArray@UTextSelectionViewRun@Art@@@Ofc@@AEBV?$TReferringPtr@$$CBVITextLayout@Art@@@3@AEBUInfo@View@1@AEBUTextRange@1@W4SelectionEffectType@1@@Z`
- size: `1943`
- prototype: `__int64 __usercall@<rax>(Ofc::CArrayImpl *this@<rcx>, int)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18026d760`
- `0x1802aad40`
- `0x1802ab530`

## callees

- `0x18002e9cc`
- `0x180071720`
- `0x180273900`
- `0x180273f90`
- `0x180274728`
- `0x180274b20`
- `0x180275540`
- `0x18028ef00`
- `0x18066e684`
- `0x1806a5084`

## import_xrefs

- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x18027454c`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@AEBUColor@GEL@@@Z` at `0x18027454c`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1802742cc`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x18027445f`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x180274562`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1802742cc`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x18027445f`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x180274562`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x1802741e2`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x18027428c`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x18027441f`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x1802741e2`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x18027428c`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x18027441f`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z` at `0x180274266`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z` at `0x1802743f9`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z` at `0x180274266`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z` at `0x1802743f9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802746e2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802746e2`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802743b3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18027453c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802743b3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18027453c`

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
      v44 = xmmword_180B82960;
LABEL_50:
      v52 = v44;
      goto LABEL_11;
    case 4:
      v44 = xmmword_180C3DA58;
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
      SelectionColor = (__int128 *)sub_18066E684(&si128, v34, v35);
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
0x180273f90  mov     rax, rsp
0x180273f93  mov     [rax+8], rbx
0x180273f97  mov     [rax+10h], rsi
0x180273f9b  mov     [rax+18h], rdi
0x180273f9f  push    rbp
0x180273fa0  push    r12
0x180273fa2  push    r13
0x180273fa4  push    r14
0x180273fa6  push    r15
0x180273fa8  lea     rbp, [rax-138h]
0x180273faf  sub     rsp, 210h
0x180273fb6  movaps  xmmword ptr [rax-38h], xmm6
0x180273fba  movaps  xmmword ptr [rax-48h], xmm7
0x180273fbe  mov     rbx, r8
0x180273fc1  mov     rsi, rdx
0x180273fc4  mov     r14, rcx
0x180273fc7  mov     rax, [r9]
0x180273fca  mov     [rbp+130h+arg_18], rax
0x180273fd1  shr     rax, 20h
0x180273fd5  xor     r12d, r12d
0x180273fd8  mov     rcx, [rdx]; this
0x180273fdb  test    eax, eax
0x180273fdd  jle     loc_18027468B
0x180273fe3  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180273fe8  mov     r8, rax
0x180273feb  mov     rcx, [rax]
0x180273fee  mov     rax, [rcx+0D0h]
0x180273ff5  lea     rdx, [rbp+130h+arg_18]
0x180273ffc  mov     rcx, r8
0x180273fff  call    cs:__guard_dispatch_icall_fptr
0x180274005  movzx   eax, al
0x180274008  test    eax, eax
0x18027400a  jz      loc_18027464A
0x180274010  mov     rcx, [rsi]; this
0x180274013  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180274018  mov     r10, rax
0x18027401b  mov     rcx, [rax]
0x18027401e  mov     rax, [rcx+138h]
0x180274025  mov     rcx, [rbx+70h]
0x180274029  movups  xmm1, xmmword ptr [rcx+80h]
0x180274030  movss   xmm0, dword ptr [rcx+7Ch]
0x180274035  cvtps2pd xmm0, xmm0
0x180274038  movaps  xmm2, xmm1
0x18027403b  unpckhpd xmm2, xmm1
0x18027403f  mulsd   xmm2, xmm0
0x180274043  divsd   xmm2, cs:__real@412be7c000000000
0x18027404b  movss   xmm0, dword ptr [rcx+78h]
0x180274050  cvtps2pd xmm0, xmm0
0x180274053  mulsd   xmm0, xmm1
0x180274057  divsd   xmm0, cs:__real@412be7c000000000
0x18027405f  movsd   [rsp+230h+var_1F0], xmm0
0x180274065  movsd   [rsp+230h+var_1E8], xmm2
0x18027406b  mov     dil, 1
0x18027406e  mov     [rsp+230h+var_210], dil
0x180274073  lea     r9, [rbp+130h+arg_18]
0x18027407a  lea     r8, [rsp+230h+var_1F0]
0x18027407f  lea     rdx, [rsp+230h+var_1F8]
0x180274084  mov     rcx, r10
0x180274087  call    cs:__guard_dispatch_icall_fptr
0x18027408d  mov     r15, [rax]
0x180274090  mov     [rax], r12
0x180274093  mov     [rbp+130h+var_140], r15
0x180274097  mov     rcx, [rsp+230h+var_1F8]
0x18027409c  test    rcx, rcx
0x18027409f  jz      short loc_1802740AE
0x1802740a1  mov     rax, [rcx]
0x1802740a4  mov     rax, [rax+8]
0x1802740a8  call    cs:__guard_dispatch_icall_fptr
0x1802740ae  mov     rax, [rbx+68h]
0x1802740b2  movss   xmm7, dword ptr [rax+7Ch]
0x1802740b7  cvtps2pd xmm7, xmm7
0x1802740ba  mulsd   xmm7, qword ptr [rax+88h]
0x1802740c2  divsd   xmm7, cs:__real@412be7c000000000
0x1802740ca  mov     rax, [rbx+60h]
0x1802740ce  movss   xmm6, dword ptr [rax+78h]
0x1802740d3  cvtps2pd xmm6, xmm6
0x1802740d6  mulsd   xmm6, qword ptr [rax+80h]
0x1802740de  divsd   xmm6, cs:__real@412be7c000000000
0x1802740e6  mov     rcx, [rsi]; this
0x1802740e9  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1802740ee  mov     r8, rax
0x1802740f1  mov     rcx, [rax]
0x1802740f4  mov     rax, [rcx+148h]
0x1802740fb  lea     rdx, [rbp+130h+var_108]
0x1802740ff  mov     rcx, r8
0x180274102  call    cs:__guard_dispatch_icall_fptr
0x180274108  mov     rbx, rax
0x18027410b  mov     rcx, [rsi]; this
0x18027410e  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180274113  lea     rdx, [rbp+130h+var_D8]
0x180274117  mov     rcx, rax
0x18027411a  call    ?GetLayoutToHostMatrix@ITextLayout@Art@@QEBA?AU?$TAffine3x3@N@Math@@XZ; Art::ITextLayout::GetLayoutToHostMatrix(void)
0x18027411f  mov     rdx, rax
0x180274122  lea     rcx, [rbp+130h+var_A8]
0x180274129  call    ??$Inverse@N@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@@Z; Math::Inverse<double>(Math::TAffine3x3<double> const &)
0x18027412e  mov     r8, rbx
0x180274131  mov     rdx, rax
0x180274134  lea     rcx, [rbp+130h+var_78]
0x18027413b  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU10@0@Z; Math::operator*<double,double,double>(Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const &)
0x180274140  movaps  xmm5, xmm7
0x180274143  mulsd   xmm5, qword ptr [rax+28h]
0x180274148  movaps  xmm4, xmm6
0x18027414b  mulsd   xmm4, qword ptr [rax+20h]
0x180274150  movsd   xmm3, qword ptr [rax+18h]
0x180274155  movsd   xmm2, qword ptr [rax+10h]
0x18027415a  movsd   xmm1, qword ptr [rax+8]
0x18027415f  movaps  xmm0, xmm6
0x180274162  mulsd   xmm0, qword ptr [rax]
0x180274166  movsd   [rbp+130h+var_138], xmm0
0x18027416b  mulsd   xmm1, xmm7
0x18027416f  movsd   [rbp+130h+var_130], xmm1
0x180274174  mulsd   xmm6, xmm2
0x180274178  movsd   [rbp+130h+var_128], xmm6
0x18027417d  mulsd   xmm3, xmm7
0x180274181  movsd   [rbp+130h+var_120], xmm3
0x180274186  movsd   [rbp+130h+var_118], xmm4
0x18027418b  movsd   [rbp+130h+var_110], xmm5
0x180274190  mov     rax, [r15]
0x180274193  lea     r8, [rbp+130h+var_138]
0x180274197  lea     rdx, [rsp+230h+var_200]
0x18027419c  mov     rcx, r15
0x18027419f  mov     rax, [rax+80h]
0x1802741a6  call    cs:__guard_dispatch_icall_fptr
0x1802741ac  mov     rsi, [rax]
0x1802741af  mov     [rax], r12
0x1802741b2  mov     rax, [r15]
0x1802741b5  mov     rcx, r15
0x1802741b8  mov     rax, [rax+8]
0x1802741bc  call    cs:__guard_dispatch_icall_fptr
0x1802741c2  mov     [rbp+130h+var_140], rsi
0x1802741c6  mov     rcx, [rsp+230h+var_200]
0x1802741cb  test    rcx, rcx
0x1802741ce  jz      short loc_1802741DD
0x1802741d0  mov     rax, [rcx]
0x1802741d3  mov     rax, [rax+8]
0x1802741d7  call    cs:__guard_dispatch_icall_fptr
0x1802741dd  lea     rcx, [rsp+230h+var_1B8]
0x1802741e2  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ; Gfx::IFigureStyle::Create(void)
0x1802741e8  nop
0x1802741e9  xorps   xmm0, xmm0
0x1802741ec  movups  [rsp+230h+var_1E0+8], xmm0
0x1802741f1  mov     ecx, [rbp+130h+arg_20]
0x1802741f7  sub     ecx, 1
0x1802741fa  jnz     loc_180274675
0x180274200  lea     rcx, [rsp+230h+var_1D0+8]
0x180274205  call    ?GetSelectionColor@Art@@YA?AUColor@GEL@@XZ; Art::GetSelectionColor(void)
0x18027420a  mov     dil, r12b
0x18027420d  movups  xmm0, xmmword ptr [rax]
0x180274210  movdqu  [rsp+230h+var_1E0+8], xmm0
0x180274216  mov     [rsp+230h+var_1F0], r12
0x18027421b  mov     dword ptr [rsp+230h+var_1E8], r12d
0x180274220  mov     r15d, 80000000h
0x180274226  mov     dword ptr [rsp+230h+var_1E8+4], r15d
0x18027422b  lea     rcx, [rsp+230h+var_1F0]
0x180274230  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x180274235  mov     rcx, 3FC3333333333333h
0x18027423f  mov     [rax], rcx
0x180274242  lea     rcx, [rsp+230h+var_1F0]
0x180274247  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x18027424c  mov     r13, 3FE0000000000000h
0x180274256  mov     [rax], r13
0x180274259  movsd   xmm1, cs:__real@4010000000000000
0x180274261  lea     rcx, [rsp+230h+var_200]
0x180274266  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z; GEL::IPen::Create(double)
0x18027426c  nop
0x18027426d  mov     rcx, [rsp+230h+var_200]
0x180274272  mov     rax, [rcx]
0x180274275  lea     rdx, [rsp+230h+var_1F0]
0x18027427a  mov     rax, [rax+88h]
0x180274281  call    cs:__guard_dispatch_icall_fptr
0x180274287  lea     rcx, [rsp+230h+var_1E0]
0x18027428c  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ; Gfx::IFigureStyle::Create(void)
0x180274292  nop
0x180274293  mov     rcx, qword ptr [rsp+230h+var_1E0]
0x180274298  mov     rax, [rcx]
0x18027429b  movdqa  xmm0, cs:__xmm@3e99999a3f8000003f8000003f800000
0x1802742a3  movups  xmmword ptr [rsp+230h+var_1D0+8], xmm0
0x1802742a8  lea     r8, [rsp+230h+var_1D0+8]
0x1802742ad  mov     rdx, [rsp+230h+var_200]
0x1802742b2  mov     rax, [rax+70h]
0x1802742b6  call    cs:__guard_dispatch_icall_fptr
0x1802742bc  xor     r9d, r9d
0x1802742bf  mov     r8, qword ptr [rsp+230h+var_1E0]
0x1802742c4  mov     rdx, rsi
0x1802742c7  lea     rcx, [rsp+230h+var_1F8]
0x1802742cc  call    cs:__imp_?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z; Gfx::IFigureShapeBuilder::Create(GEL::IPath const &,Gfx::IFigureStyle *,Gfx::IEffectParams const *)
0x1802742d2  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1802742da  movups  [rbp+130h+var_1B0], xmm0
0x1802742de  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1802742e6  movups  [rbp+130h+var_1A0], xmm1
0x1802742ea  xorps   xmm0, xmm0
0x1802742ed  movups  [rbp+130h+var_190], xmm0
0x1802742f1  mov     rax, [rbp+130h+arg_18]
0x1802742f8  mov     [rbp+130h+var_180], rax
0x1802742fc  mov     rbx, [rsp+230h+var_1F8]
0x180274301  mov     [rbp+130h+var_178], rbx
0x180274305  test    rbx, rbx
0x180274308  jz      short loc_180274319
0x18027430a  mov     rax, [rbx]
0x18027430d  mov     rcx, rbx
0x180274310  mov     rax, [rax]
0x180274313  call    cs:__guard_dispatch_icall_fptr
0x180274319  mov     [rbp+130h+var_170], r12w
0x18027431e  mov     [rbp+130h+var_16E], r12b
0x180274322  mov     [rbp+130h+var_168], r12d
0x180274326  xorps   xmm0, xmm0
0x180274329  movups  [rbp+130h+var_160], xmm0
0x18027432d  mov     [rbp+130h+var_150], r12b
0x180274331  mov     [rbp+130h+var_148], dil
0x180274335  lea     rdx, [rbp+130h+var_1B0]; struct Art::TextViewRun *
0x180274339  mov     rcx, r14; this
0x18027433c  call    ??$Add@UTextSelectionViewRun@Art@@@?$TArray@UTextSelectionViewRun@Art@@@Ofc@@QEAAXAEBUTextSelectionViewRun@Art@@@Z; Ofc::TArray<Art::TextSelectionViewRun>::Add<Art::TextSelectionViewRun>(Art::TextSelectionViewRun const &)
0x180274341  test    rbx, rbx
0x180274344  jz      short loc_180274361
0x180274346  nop     word ptr [rax+rax+00000000h]
0x180274350  mov     rax, [rbx]
0x180274353  mov     rcx, rbx
0x180274356  mov     rax, [rax+8]
0x18027435a  call    cs:__guard_dispatch_icall_fptr
0x180274360  nop
0x180274361  mov     rcx, [rsp+230h+var_1F8]
0x180274366  test    rcx, rcx
0x180274369  jz      short loc_180274379
0x18027436b  mov     rax, [rcx]
0x18027436e  mov     rax, [rax+8]
0x180274372  call    cs:__guard_dispatch_icall_fptr
0x180274378  nop
0x180274379  mov     rcx, qword ptr [rsp+230h+var_1E0]
0x18027437e  test    rcx, rcx
0x180274381  jz      short loc_180274391
0x180274383  mov     rax, [rcx]
0x180274386  mov     rax, [rax+8]
0x18027438a  call    cs:__guard_dispatch_icall_fptr
0x180274390  nop
0x180274391  mov     rcx, [rsp+230h+var_200]
0x180274396  test    rcx, rcx
0x180274399  jz      short loc_1802743A9
0x18027439b  mov     rax, [rcx]
0x18027439e  mov     rax, [rax+8]
0x1802743a2  call    cs:__guard_dispatch_icall_fptr
0x1802743a8  nop
0x1802743a9  mov     rcx, [rsp+230h+var_1F0]
0x1802743ae  test    rcx, rcx
0x1802743b1  jz      short loc_1802743B9
0x1802743b3  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1802743b9  mov     [rsp+230h+var_1F0], r12
0x1802743be  mov     dword ptr [rsp+230h+var_1E8], r12d
0x1802743c3  mov     dword ptr [rsp+230h+var_1E8+4], r15d
0x1802743c8  lea     rcx, [rsp+230h+var_1F0]
0x1802743cd  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x1802743d2  mov     rcx, 3FC47AE147AE147Bh
0x1802743dc  mov     [rax], rcx
0x1802743df  lea     rcx, [rsp+230h+var_1F0]
0x1802743e4  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x1802743e9  mov     [rax], r13
0x1802743ec  movsd   xmm1, cs:__real@4000000000000000
0x1802743f4  lea     rcx, [rsp+230h+var_1E0]
0x1802743f9  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@N@Z; GEL::IPen::Create(double)
0x1802743ff  nop
0x180274400  mov     rcx, qword ptr [rsp+230h+var_1E0]
0x180274405  mov     rax, [rcx]
0x180274408  lea     rdx, [rsp+230h+var_1F0]
0x18027440d  mov     rax, [rax+88h]
0x180274414  call    cs:__guard_dispatch_icall_fptr
0x18027441a  lea     rcx, [rsp+230h+var_200]
0x18027441f  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ; Gfx::IFigureStyle::Create(void)
0x180274425  nop
0x180274426  mov     rcx, [rsp+230h+var_200]
0x18027442b  mov     rax, [rcx]
0x18027442e  movdqa  xmm0, cs:__xmm@3ecccccd3f8000003f8000003f800000
0x180274436  movups  xmmword ptr [rsp+230h+var_1D0+8], xmm0
0x18027443b  lea     r8, [rsp+230h+var_1D0+8]
0x180274440  mov     rdx, qword ptr [rsp+230h+var_1E0]
0x180274445  mov     rax, [rax+70h]
0x180274449  call    cs:__guard_dispatch_icall_fptr
0x18027444f  xor     r9d, r9d
0x180274452  mov     r8, [rsp+230h+var_200]
0x180274457  mov     rdx, rsi
0x18027445a  lea     rcx, [rsp+230h+var_1F8]
0x18027445f  call    cs:__imp_?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z; Gfx::IFigureShapeBuilder::Create(GEL::IPath const &,Gfx::IFigureStyle *,Gfx::IEffectParams const *)
0x180274465  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x18027446d  movups  [rbp+130h+var_1B0], xmm0
0x180274471  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x180274479  movups  [rbp+130h+var_1A0], xmm1
0x18027447d  xorps   xmm0, xmm0
0x180274480  movups  [rbp+130h+var_190], xmm0
0x180274484  mov     rax, [rbp+130h+arg_18]
0x18027448b  mov     [rbp+130h+var_180], rax
0x18027448f  mov     rbx, [rsp+230h+var_1F8]
0x180274494  mov     [rbp+130h+var_178], rbx
0x180274498  test    rbx, rbx
0x18027449b  jz      short loc_1802744AC
0x18027449d  mov     rax, [rbx]
0x1802744a0  mov     rcx, rbx
0x1802744a3  mov     rax, [rax]
0x1802744a6  call    cs:__guard_dispatch_icall_fptr
0x1802744ac  mov     [rbp+130h+var_170], r12w
0x1802744b1  mov     [rbp+130h+var_16E], r12b
0x1802744b5  mov     [rbp+130h+var_168], r12d
0x1802744b9  xorps   xmm0, xmm0
  ... truncated ...
```
