# xgc::CDeviceContext::SelectFont(std::shared_ptr<IXpsOMGlyphs> const &,std::shared_ptr<IDWriteFontFace> const &,xgc::GDIFonts &,xgc::SqmDWordCounter &,bool &)

- ea: `0x1800211f4`
- end: `0x1800217ec`
- name: `?SelectFont@CDeviceContext@xgc@@QEAA_NAEBV?$shared_ptr@UIXpsOMGlyphs@@@std@@AEBV?$shared_ptr@UIDWriteFontFace@@@4@AEAVGDIFonts@2@AEAUSqmDWordCounter@2@AEA_N@Z`
- size: `1528`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002bcf0`

## callees

- `0x180008830`
- `0x1800093c4`
- `0x180009de0`
- `0x18000d960`
- `0x18000e4c4`
- `0x180011b2c`
- `0x180011e88`
- `0x18001bcb4`
- `0x18001cf50`
- `0x18001dff0`
- `0x18001e570`
- `0x18001ec70`
- `0x1800211f4`
- `0x180022748`
- `0x180023470`
- `0x180023514`
- `0x180023e0c`
- `0x18002cc64`
- `0x180037278`
- `0x18004a010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180021620`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180021620`
- `KERNEL32!GetLastError` at `0x18002176d`
- `KERNEL32!GetLastError` at `0x1800217c8`
- `KERNEL32!GetLastError` at `0x18002176d`
- `KERNEL32!GetLastError` at `0x1800217c8`
- `GDI32!GetTextFaceW` at `0x1800215c7`
- `GDI32!GetTextFaceW` at `0x1800215f1`
- `GDI32!GetTextFaceW` at `0x1800215c7`
- `GDI32!GetTextFaceW` at `0x1800215f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall xgc::CDeviceContext::SelectFont(
        __int64 a1,
        const struct D2D_MATRIX_3X2_F *a2,
        _QWORD *a3,
        __int64 a4,
        _DWORD *a5,
        _BYTE *a6)
{
  _DWORD *v9; // r8
  bool v10; // si
  float *v11; // r15
  __int64 **v12; // rdx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // ebx
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  int (__fastcall **v19)(std::_Ref_count_base *, GUID *, LPWSTR *); // rax
  char v20; // bl
  struct tagLOGFONTW *v21; // r8
  char v22; // si
  int v23; // edx
  const char *v24; // r8
  int v25; // eax
  int v26; // edx
  const char *v27; // r8
  int v28; // r9d
  int v29; // eax
  int v30; // edx
  const char *v31; // r8
  int v32; // r9d
  int v33; // eax
  int v34; // edx
  const char *v35; // r8
  int v36; // r9d
  BYTE lfItalic; // al
  int v38; // eax
  int v39; // edx
  HFONT *v40; // rcx
  const char *v41; // r8
  int v42; // r9d
  __int16 v43; // ax
  char v44; // dl
  char v45; // al
  int v46; // eax
  int v47; // r9d
  int TextFaceW; // eax
  int v49; // esi
  size_t v50; // rax
  bool v51; // zf
  __int64 v52; // rax
  __int64 v53; // rdx
  unsigned __int64 v54; // rcx
  const wchar_t *v55; // rax
  wchar_t *v56; // r9
  int v57; // r8d
  const wchar_t *v58; // rdi
  int v59; // r10d
  unsigned __int64 v60; // r11
  wchar_t **v61; // rax
  wchar_t **v62; // r9
  signed int v64; // eax
  int v65; // edx
  const char *v66; // r8
  int v67; // r9d
  signed int LastError; // eax
  int v69; // edx
  const char *v70; // r8
  int v71; // r9d
  _BYTE v72[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v73; // [rsp+34h] [rbp-CCh] BYREF
  xpsrdr *v74; // [rsp+38h] [rbp-C8h] BYREF
  float v75; // [rsp+40h] [rbp-C0h] BYREF
  int v76; // [rsp+44h] [rbp-BCh] BYREF
  int v77; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR lpName; // [rsp+50h] [rbp-B0h] BYREF
  xpsrdr **v79; // [rsp+58h] [rbp-A8h]
  std::_Ref_count_base **v80; // [rsp+60h] [rbp-A0h]
  std::_Ref_count_base *v81[2]; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v82[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v83; // [rsp+88h] [rbp-78h]
  wchar_t *S2[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v85; // [rsp+A0h] [rbp-60h]
  __int64 v86; // [rsp+A8h] [rbp-58h]
  wchar_t *S1[2]; // [rsp+B0h] [rbp-50h] BYREF
  size_t N; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v89; // [rsp+C8h] [rbp-38h]
  LOGFONTW v90; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v91[96]; // [rsp+130h] [rbp+30h] BYREF

  v83 = a4;
  v9 = a5;
  v10 = 0;
  LODWORD(v74) = 0;
  *a6 = 0;
  v11 = (float *)(a1 + 40);
  if ( *(float *)(a1 + 40) < 0.0
    || *(float *)(a1 + 52) < 0.0
    || !xgc::IsIsotropicScaleOrTranslation((xgc *)(a1 + 40), a2) )
  {
    ++*v9;
    return 0;
  }
  *(_OWORD *)v81 = 0;
  LODWORD(v74) = 0;
  v13 = *v12;
  v14 = **v12;
  lpName = 0;
  v79 = &v74;
  v80 = v81;
  v15 = (*(__int64 (__fastcall **)(__int64 *, LPWSTR *))(v14 + 368))(v13, &lpName);
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&lpName);
  if ( (int)v74 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v74, v16, v17, v18);
  if ( v15 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
  memset_0(&v90, 0, sizeof(v90));
  memset_0(v91, 0, 0x5Cu);
  *(_OWORD *)v82 = 0;
  v19 = *(int (__fastcall ***)(std::_Ref_count_base *, GUID *, LPWSTR *))v81[0];
  lpName = 0;
  v79 = (xpsrdr **)((char *)&v74 + 4);
  v80 = v82;
  v20 = 1;
  v74 = (xpsrdr *)1;
  if ( (*v19)(v81[0], &GUID_f46f0ccb_ff7f_4884_9a78_33f68af18961, &lpName) >= 0 )
    v10 = SHIDWORD(v74) >= 0;
  detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&lpName);
  if ( v10
    && v82[0]
    && (*(int (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v82[0] + 24LL))(v82[0], v91) >= 0 )
  {
    v22 = 1;
    xgc::CopyLogFont((xgc *)v91, (struct win_dox::XPS_LOGFONT *)&v90, v21);
  }
  else
  {
    v22 = 0;
    v46 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LOGFONTW *))(**(_QWORD **)(a1 + 120) + 40LL))(
            *(_QWORD *)(a1 + 120),
            *a3,
            &v90);
    if ( v46 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v46, v23, v24, v47);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 27), v23, (_DWORD)v24, (unsigned int)v90.lfFaceName, v22);
  v75 = 0.0;
  v25 = (*(__int64 (__fastcall **)(_QWORD, float *))(**(_QWORD **)&a2->m11 + 352LL))(*(_QWORD *)&a2->m11, &v75);
  if ( v25 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v25, v26, v27, v28);
  v90.lfHeight = -(int)((float)((float)((float)(*(float *)(a1 + 52) + *v11) * 0.5) * v75) + 0.5);
  v77 = 0;
  v29 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)&a2->m11 + 304LL))(*(_QWORD *)&a2->m11, &v77);
  if ( v29 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v29, v30, v31, v32);
  v76 = 0;
  v33 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)&a2->m11 + 320LL))(*(_QWORD *)&a2->m11, &v76);
  if ( v33 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v33, v34, v35, v36);
  lfItalic = v90.lfItalic;
  if ( ((v76 - 2) & 0xFFFFFFFD) == 0 )
    lfItalic = 1;
  v90.lfItalic = lfItalic;
  if ( v77 )
  {
    if ( lfItalic )
    {
LABEL_36:
      if ( v82[1] )
        std::_Ref_count_base::_Decref(v82[1]);
      if ( v81[1] )
        std::_Ref_count_base::_Decref(v81[1]);
      return 0;
    }
    v90.lfOrientation = 900;
  }
  *(_WORD *)&v90.lfQuality = 2;
  v73 = 0;
  v38 = (*(__int64 (__fastcall **)(_QWORD, __int16 *))(**(_QWORD **)&a2->m11 + 384LL))(*(_QWORD *)&a2->m11, &v73);
  if ( v38 < 0 )
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v38, v39, v41, v42);
  v43 = v73;
  if ( v73 == -1 )
  {
    v43 = 0;
    v73 = 0;
  }
  v44 = 0;
  v72[0] = 0;
  if ( *(_BYTE *)(a1 + 322) || v22 )
  {
    v45 = 0;
  }
  else
  {
    v45 = xgc::GDIFonts::InstallFont(v83, v81, (unsigned int)v43, v90.lfFaceName, v72);
    v44 = v72[0];
  }
  *a6 = v45;
  if ( v44 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, &WPP_e356bbb79c923e760b944825cbe30f92_Traceguids);
    goto LABEL_36;
  }
  xgc::GDIResourceSelector<xgc::GDIResources<HFONT__ *,tagLOGFONTW>,xgc::FontFactory>::operator()(
    v40,
    a1,
    a1 + 256,
    &v90);
  if ( !*(_BYTE *)(a1 + 322) && !v22 )
  {
    TextFaceW = GetTextFaceW(*(HDC *)(a1 + 32), 0, 0);
    v49 = TextFaceW;
    if ( TextFaceW <= 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v69, v70, v71);
    }
    std::vector<unsigned short>::vector<unsigned short>(&lpName, TextFaceW);
    if ( GetTextFaceW(*(HDC *)(a1 + 32), v49, lpName) <= 0 )
    {
      v64 = GetLastError();
      if ( v64 > 0 )
        v64 = (unsigned __int16)v64 | 0x80070000;
      if ( v64 >= 0 )
        v64 = -2147467259;
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v64, v65, v66, v67);
    }
    std::wstring::wstring(S1, lpName, (char *)v79 - 2);
    v50 = wcsnlen(v90.lfFaceName, 0x20u);
    v51 = 2 * v50 == 0;
    v52 = 2 * v50;
    *(_OWORD *)S2 = 0;
    v53 = 0;
    v85 = 0;
    v86 = 0;
    if ( v51 )
    {
      v54 = 7;
      v86 = 7;
      LOWORD(S2[0]) = 0;
    }
    else
    {
      std::wstring::_Construct<1,wchar_t *>(S2, v90.lfFaceName, v52 >> 1);
      v54 = v86;
      v53 = v85;
    }
    v55 = (const wchar_t *)S2;
    v56 = S2[0];
    if ( v54 > 7 )
      v55 = S2[0];
    v57 = N;
    v58 = (const wchar_t *)S1;
    v59 = (int)S1[0];
    v60 = v89;
    if ( v89 > 7 )
      v58 = S1[0];
    if ( N == v53 )
    {
      if ( !N || !wmemcmp(v58, v55, N) )
      {
LABEL_62:
        std::wstring::_Tidy_deallocate(S2);
        std::wstring::_Tidy_deallocate(S1);
        std::vector<unsigned short>::_Tidy(&lpName);
        goto LABEL_63;
      }
      v60 = v89;
      v59 = (int)S1[0];
      v54 = v86;
      v56 = S2[0];
    }
    v20 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0 )
    {
      v61 = S2;
      if ( v54 > 7 )
        v61 = (wchar_t **)v56;
      v62 = S1;
      if ( v60 > 7 )
        LODWORD(v62) = v59;
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 27), (_DWORD)WPP_GLOBAL_Control, v57, (_DWORD)v62, (__int64)v61);
    }
    goto LABEL_62;
  }
LABEL_63:
  if ( v82[1] )
    std::_Ref_count_base::_Decref(v82[1]);
  if ( v81[1] )
    std::_Ref_count_base::_Decref(v81[1]);
  return v20;
}

```

## disassembly

```asm
0x1800211f4  push    rbp
0x1800211f6  push    rbx
0x1800211f7  push    rsi
0x1800211f8  push    rdi
0x1800211f9  push    r12
0x1800211fb  push    r13
0x1800211fd  push    r14
0x1800211ff  push    r15
0x180021201  lea     rbp, [rsp-0A8h]
0x180021209  sub     rsp, 1A8h
0x180021210  mov     rax, cs:__security_cookie
0x180021217  xor     rax, rsp
0x18002121a  mov     [rbp+0E0h+var_50], rax
0x180021221  mov     [rbp+0E0h+var_158], r9
0x180021225  mov     r12, r8
0x180021228  mov     r14, rdx
0x18002122b  mov     rdi, rcx
0x18002122e  mov     r8, [rbp+0E0h+arg_20]
0x180021235  mov     r13, [rbp+0E0h+arg_28]
0x18002123c  xor     esi, esi
0x18002123e  mov     dword ptr [rsp+1E0h+var_1A8], esi
0x180021242  mov     [r13+0], sil
0x180021246  lea     r15, [rcx+28h]
0x18002124a  xorps   xmm0, xmm0
0x18002124d  comiss  xmm0, dword ptr [r15]
0x180021251  ja      loc_180021740
0x180021257  comiss  xmm0, dword ptr [rcx+34h]
0x18002125b  ja      loc_180021740
0x180021261  mov     rcx, r15; this
0x180021264  call    ?IsIsotropicScaleOrTranslation@xgc@@YA_NAEBUD2D_MATRIX_3X2_F@@@Z; xgc::IsIsotropicScaleOrTranslation(D2D_MATRIX_3X2_F const &)
0x180021269  test    al, al
0x18002126b  jz      loc_180021740
0x180021271  xorps   xmm0, xmm0
0x180021274  movdqu  xmmword ptr [rsp+1E0h+var_178], xmm0
0x18002127a  mov     dword ptr [rsp+1E0h+var_1A8], esi
0x18002127e  mov     rcx, [rdx]
0x180021281  mov     rax, [rcx]
0x180021284  mov     [rsp+1E0h+lpName], rsi
0x180021289  lea     rdx, [rsp+1E0h+var_1A8]
0x18002128e  mov     [rsp+1E0h+var_188], rdx
0x180021293  lea     rdx, [rsp+1E0h+var_178]
0x180021298  mov     [rsp+1E0h+var_180], rdx
0x18002129d  lea     rdx, [rsp+1E0h+lpName]
0x1800212a2  mov     rax, [rax+170h]
0x1800212a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212ae  mov     ebx, eax
0x1800212b0  lea     rcx, [rsp+1E0h+lpName]
0x1800212b5  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800212ba  mov     ecx, dword ptr [rsp+1E0h+var_1A8]; this
0x1800212be  test    ecx, ecx
0x1800212c0  js      loc_18002179A
0x1800212c6  test    ebx, ebx
0x1800212c8  js      loc_1800217A0
0x1800212ce  lea     ebx, [rsi+5Ch]
0x1800212d1  mov     r8d, ebx; Size
0x1800212d4  xor     edx, edx; Val
0x1800212d6  lea     rcx, [rbp+0E0h+var_110]; void *
0x1800212da  call    memset_0
0x1800212df  mov     r8d, ebx; Size
0x1800212e2  xor     edx, edx; Val
0x1800212e4  lea     rcx, [rbp+0E0h+var_B0]; void *
0x1800212e8  call    memset_0
0x1800212ed  xorps   xmm0, xmm0
0x1800212f0  movdqu  xmmword ptr [rsp+1E0h+var_168], xmm0
0x1800212f6  mov     dword ptr [rsp+1E0h+var_1A8+4], esi
0x1800212fa  mov     rcx, [rsp+1E0h+var_178]
0x1800212ff  mov     rax, [rcx]
0x180021302  mov     [rsp+1E0h+lpName], rsi
0x180021307  lea     rdx, [rsp+1E0h+var_1A8+4]
0x18002130c  mov     [rsp+1E0h+var_188], rdx
0x180021311  lea     rdx, [rsp+1E0h+var_168]
0x180021316  mov     [rsp+1E0h+var_180], rdx
0x18002131b  lea     ebx, [rsi+1]
0x18002131e  mov     dword ptr [rsp+1E0h+var_1A8], ebx
0x180021322  lea     r8, [rsp+1E0h+lpName]
0x180021327  lea     rdx, _GUID_f46f0ccb_ff7f_4884_9a78_33f68af18961
0x18002132e  mov     rax, [rax]
0x180021331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021336  test    eax, eax
0x180021338  js      short loc_180021343
0x18002133a  cmp     dword ptr [rsp+1E0h+var_1A8+4], esi
0x18002133e  jl      short loc_180021343
0x180021340  mov     sil, bl
0x180021343  lea     rcx, [rsp+1E0h+lpName]
0x180021348  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18002134d  test    sil, sil
0x180021350  jz      loc_180021503
0x180021356  mov     rcx, [rsp+1E0h+var_168]
0x18002135b  test    rcx, rcx
0x18002135e  jz      loc_180021503
0x180021364  mov     rax, [rcx]
0x180021367  lea     rdx, [rbp+0E0h+var_B0]
0x18002136b  mov     rax, [rax+18h]
0x18002136f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021374  test    eax, eax
0x180021376  js      loc_180021503
0x18002137c  mov     sil, bl
0x18002137f  lea     rdx, [rbp+0E0h+var_110]; struct win_dox::XPS_LOGFONT *
0x180021383  lea     rcx, [rbp+0E0h+var_B0]; this
0x180021387  call    ?CopyLogFont@xgc@@YAXAEAUXPS_LOGFONT@win_dox@@AEAUtagLOGFONTW@@@Z; xgc::CopyLogFont(win_dox::XPS_LOGFONT &,tagLOGFONTW &)
0x18002138c  xor     r12d, r12d
0x18002138f  lea     rax, WPP_GLOBAL_Control
0x180021396  mov     rcx, cs:WPP_GLOBAL_Control
0x18002139d  cmp     rcx, rax
0x1800213a0  jz      short loc_1800213C3
0x1800213a2  test    byte ptr [rcx+0E4h], 4
0x1800213a9  jz      short loc_1800213C3
0x1800213ab  movzx   eax, sil
0x1800213af  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800213b3  lea     r9, [rbp+0E0h+Source]
0x1800213b7  mov     rcx, [rcx+0D8h]
0x1800213be  call    WPP_SF_Sd
0x1800213c3  mov     [rsp+1E0h+var_1A0], 0
0x1800213cb  mov     rcx, [r14]
0x1800213ce  mov     rax, [rcx]
0x1800213d1  lea     rdx, [rsp+1E0h+var_1A0]
0x1800213d6  mov     rax, [rax+160h]
0x1800213dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213e2  test    eax, eax
0x1800213e4  js      loc_1800217A8
0x1800213ea  movss   xmm0, dword ptr [rdi+34h]
0x1800213ef  addss   xmm0, dword ptr [r15]
0x1800213f4  mulss   xmm0, cs:__real@3f000000
0x1800213fc  mulss   xmm0, [rsp+1E0h+var_1A0]
0x180021402  cvtps2pd xmm0, xmm0
0x180021405  addsd   xmm0, cs:__real@3fe0000000000000
0x18002140d  cvttsd2si eax, xmm0
0x180021411  neg     eax
0x180021413  mov     [rbp+0E0h+var_110], eax
0x180021416  mov     [rsp+1E0h+var_198], r12d
0x18002141b  mov     rcx, [r14]
0x18002141e  mov     rax, [rcx]
0x180021421  lea     rdx, [rsp+1E0h+var_198]
0x180021426  mov     rax, [rax+130h]
0x18002142d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021432  test    eax, eax
0x180021434  js      loc_1800217B0
0x18002143a  mov     [rsp+1E0h+var_19C], r12d
0x18002143f  mov     rcx, [r14]
0x180021442  mov     rax, [rcx]
0x180021445  lea     rdx, [rsp+1E0h+var_19C]
0x18002144a  mov     rax, [rax+140h]
0x180021451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021456  test    eax, eax
0x180021458  js      loc_1800217B8
0x18002145e  mov     eax, [rsp+1E0h+var_19C]
0x180021462  add     eax, 0FFFFFFFEh
0x180021465  test    eax, 0FFFFFFFDh
0x18002146a  movzx   eax, [rbp+0E0h+var_FC]
0x18002146e  cmovz   eax, ebx
0x180021471  mov     [rbp+0E0h+var_FC], al
0x180021474  cmp     [rsp+1E0h+var_198], r12d
0x180021479  jz      short loc_18002148A
0x18002147b  test    al, al
0x18002147d  jnz     loc_18002156E
0x180021483  mov     [rbp+0E0h+var_104], 384h
0x18002148a  mov     [rbp+0E0h+var_F6], 2
0x180021490  mov     [rsp+1E0h+var_1AC], r12w
0x180021496  mov     rcx, [r14]
0x180021499  mov     rax, [rcx]
0x18002149c  lea     rdx, [rsp+1E0h+var_1AC]
0x1800214a1  mov     rax, [rax+180h]
0x1800214a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214ad  test    eax, eax
0x1800214af  js      loc_1800217C0
0x1800214b5  movzx   eax, [rsp+1E0h+var_1AC]
0x1800214ba  cmp     ax, 0FFFFh
0x1800214be  jnz     short loc_1800214C8
0x1800214c0  mov     eax, r12d
0x1800214c3  mov     [rsp+1E0h+var_1AC], ax
0x1800214c8  mov     dl, r12b
0x1800214cb  mov     [rsp+1E0h+var_1B0], dl
0x1800214cf  cmp     [rdi+142h], r12b
0x1800214d6  jnz     short loc_18002152E
0x1800214d8  test    sil, sil
0x1800214db  jnz     short loc_18002152E
0x1800214dd  movsx   r8d, ax
0x1800214e1  lea     rax, [rsp+1E0h+var_1B0]
0x1800214e6  mov     [rsp+1E0h+var_1C0], rax
0x1800214eb  lea     r9, [rbp+0E0h+Source]
0x1800214ef  lea     rdx, [rsp+1E0h+var_178]
0x1800214f4  mov     rcx, [rbp+0E0h+var_158]
0x1800214f8  call    ?InstallFont@GDIFonts@xgc@@QEAA_NAEBV?$shared_ptr@UIXpsOMFontResource@@@std@@IAEAY0CA@_WAEA_N@Z; xgc::GDIFonts::InstallFont(std::shared_ptr<IXpsOMFontResource> const &,uint,wchar_t (&)[32],bool &)
0x1800214fd  mov     dl, [rsp+1E0h+var_1B0]
0x180021501  jmp     short loc_180021531
0x180021503  xor     sil, sil
0x180021506  mov     rcx, [rdi+78h]
0x18002150a  mov     rax, [rcx]
0x18002150d  lea     r8, [rbp+0E0h+var_110]
0x180021511  mov     rdx, [r12]
0x180021515  mov     rax, [rax+28h]
0x180021519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002151e  xor     r12d, r12d
0x180021521  test    eax, eax
0x180021523  js      loc_180021792
0x180021529  jmp     loc_18002138F
0x18002152e  mov     al, r12b
0x180021531  mov     [r13+0], al
0x180021535  test    dl, dl
0x180021537  jz      short loc_180021595
0x180021539  mov     rcx, cs:WPP_GLOBAL_Control
0x180021540  lea     rax, WPP_GLOBAL_Control
0x180021547  cmp     rcx, rax
0x18002154a  jz      short loc_18002156E
0x18002154c  test    byte ptr [rcx+0E4h], 8
0x180021553  jz      short loc_18002156E
0x180021555  mov     edx, 0Dh
0x18002155a  lea     r8, WPP_e356bbb79c923e760b944825cbe30f92_Traceguids
0x180021561  mov     rcx, [rcx+0D8h]
0x180021568  call    WPP_SF_
0x18002156d  nop
0x18002156e  mov     rcx, [rbp+0E0h+var_168+8]; this
0x180021572  test    rcx, rcx
0x180021575  jz      short loc_18002157D
0x180021577  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002157c  nop
0x18002157d  mov     rcx, [rsp+1E0h+var_178+8]; this
0x180021582  test    rcx, rcx
0x180021585  jz      loc_180021748
0x18002158b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021590  jmp     loc_180021748
0x180021595  lea     r8, [rdi+100h]
0x18002159c  lea     r9, [rbp+0E0h+var_110]
0x1800215a0  mov     rdx, rdi
0x1800215a3  call    ??R?$GDIResourceSelector@U?$GDIResources@PEAUHFONT__@@UtagLOGFONTW@@@xgc@@UFontFactory@2@@xgc@@QEAAXAEAVCDeviceContext@1@AEAU?$GDIResources@PEAUHFONT__@@UtagLOGFONTW@@@1@AEAUtagLOGFONTW@@@Z; xgc::GDIResourceSelector<xgc::GDIResources<HFONT__ *,tagLOGFONTW>,xgc::FontFactory>::operator()(xgc::CDeviceContext &,xgc::GDIResources<HFONT__ *,tagLOGFONTW> &,tagLOGFONTW &)
0x1800215a8  cmp     [rdi+142h], r12b
0x1800215af  jnz     loc_18002171E
0x1800215b5  test    sil, sil
0x1800215b8  jnz     loc_18002171E
0x1800215be  xor     r8d, r8d; lpName
0x1800215c1  xor     edx, edx; c
0x1800215c3  mov     rcx, [rdi+20h]; hdc
0x1800215c7  call    cs:__imp_GetTextFaceW
0x1800215cd  movsxd  rsi, eax
0x1800215d0  test    eax, eax
0x1800215d2  jle     loc_1800217C8
0x1800215d8  mov     rdx, rsi
0x1800215db  lea     rcx, [rsp+1E0h+lpName]
0x1800215e0  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x1800215e5  nop
0x1800215e6  mov     r8, [rsp+1E0h+lpName]; lpName
0x1800215eb  mov     edx, esi; c
0x1800215ed  mov     rcx, [rdi+20h]; hdc
0x1800215f1  call    cs:__imp_GetTextFaceW
0x1800215f7  test    eax, eax
0x1800215f9  jle     loc_18002176D
0x1800215ff  mov     r8, [rsp+1E0h+var_188]
0x180021604  add     r8, 0FFFFFFFFFFFFFFFEh
0x180021608  mov     rdx, [rsp+1E0h+lpName]
0x18002160d  lea     rcx, [rbp+0E0h+S1]
0x180021611  call    ??$?0V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@_W@std@@@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@_W@std@@@std@@@1@0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<wchar_t>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<wchar_t>>>,std::allocator<wchar_t> const &)
0x180021616  nop
0x180021617  mov     edx, 20h ; ' '; MaxCount
0x18002161c  lea     rcx, [rbp+0E0h+Source]; Source
0x180021620  call    cs:__imp_wcsnlen
0x180021626  mov     esi, 7
0x18002162b  add     rax, rax
0x18002162e  xorps   xmm0, xmm0
0x180021631  movups  xmmword ptr [rbp+0E0h+S2], xmm0
0x180021635  mov     rdx, r12
0x180021638  mov     [rbp+0E0h+var_140], rdx
0x18002163c  mov     [rbp+0E0h+var_138], r12
0x180021640  jnz     short loc_18002164F
0x180021642  mov     ecx, esi
0x180021644  mov     [rbp+0E0h+var_138], rcx
0x180021648  mov     word ptr [rbp+0E0h+S2], r12w
0x18002164d  jmp     short loc_18002166A
0x18002164f  sar     rax, 1
0x180021652  mov     r8, rax
0x180021655  lea     rdx, [rbp+0E0h+Source]
0x180021659  lea     rcx, [rbp+0E0h+S2]
0x18002165d  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180021662  mov     rcx, [rbp+0E0h+var_138]
0x180021666  mov     rdx, [rbp+0E0h+var_140]
0x18002166a  lea     rax, [rbp+0E0h+S2]
0x18002166e  mov     r9, [rbp+0E0h+S2]
0x180021672  cmp     rcx, rsi
0x180021675  cmova   rax, r9
0x180021679  mov     r8, [rbp+0E0h+N]; N
0x18002167d  lea     rdi, [rbp+0E0h+S1]
0x180021681  mov     r10, [rbp+0E0h+S1]
0x180021685  mov     r11, [rbp+0E0h+var_118]
0x180021689  cmp     r11, rsi
0x18002168c  cmova   rdi, r10
0x180021690  cmp     r8, rdx
0x180021693  jnz     short loc_1800216B9
0x180021695  test    r8, r8
0x180021698  jz      short loc_1800216FF
0x18002169a  mov     rdx, rax; S2
0x18002169d  mov     rcx, rdi; S1
0x1800216a0  call    wmemcmp
0x1800216a5  test    eax, eax
0x1800216a7  jz      short loc_1800216FF
0x1800216a9  mov     r11, [rbp+0E0h+var_118]
0x1800216ad  mov     r10, [rbp+0E0h+S1]
0x1800216b1  mov     rcx, [rbp+0E0h+var_138]
0x1800216b5  mov     r9, [rbp+0E0h+S2]
0x1800216b9  mov     bl, r12b
0x1800216bc  mov     rdx, cs:WPP_GLOBAL_Control
0x1800216c3  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
