# xpsrdr::Image::CreateImage(xpsrdr::RenderState &,std::shared_ptr<IXpsOMImageResource> const &,std::shared_ptr<IXpsOMColorProfileResource> const &,bool)

- ea: `0x1800bad68`
- end: `0x1800bb340`
- name: `?CreateImage@Image@xpsrdr@@SA?AV?$shared_ptr@UImage@xpsrdr@@@std@@AEAURenderState@2@AEBV?$shared_ptr@UIXpsOMImageResource@@@4@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@4@_N@Z`
- size: `1496`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1800b3ecc`

## callees

- `0x180003180`
- `0x18000358c`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a82e8`
- `0x1800a9530`
- `0x1800aaedc`
- `0x1800adcc0`
- `0x1800b20e8`
- `0x1800b2154`
- `0x1800b8a30`
- `0x1800b9f14`
- `0x1800ba1b4`
- `0x1800ba76c`
- `0x1800baa64`
- `0x1800baae4`
- `0x1800bab9c`
- `0x1800bad68`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
xpsrdr **__fastcall xpsrdr::Image::CreateImage(xpsrdr **a1, __int64 **a2, __int64 **a3, _QWORD *a4)
{
  __int64 v8; // r8
  __int64 v9; // rax
  std::_Ref_count_base *v10; // rbx
  xpsrdr *v11; // rdx
  __int64 *v12; // rcx
  __int64 v13; // rax
  int v14; // ebx
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  int v18; // eax
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  int v22; // eax
  const char *v23; // rdx
  const char *v24; // r8
  int v25; // r9d
  xpsrdr *v26; // rcx
  GUID v27; // xmm0
  __int64 *v28; // rcx
  __int64 v29; // rax
  int v30; // ebx
  int v31; // edx
  const char *v32; // r8
  int v33; // r9d
  int v34; // eax
  int v35; // edx
  const char *v36; // r8
  int v37; // r9d
  int v38; // eax
  const char *v39; // rdx
  xpsrdr *v40; // rcx
  const char *v41; // r8
  int v42; // r9d
  __int64 v43; // rax
  int v44; // ebx
  int v45; // edx
  const char *v46; // r8
  int v47; // r9d
  int v48; // eax
  int v49; // edx
  const char *v50; // r8
  int v51; // r9d
  int v52; // eax
  int v53; // edx
  const char *v54; // r8
  int v55; // r9d
  char HasAlpha; // r13
  std::_Ref_count_base *v57; // r15
  int v58; // eax
  int v59; // edx
  const char *v60; // r8
  int v61; // r9d
  __int64 v62; // rax
  __int64 *v63; // rcx
  __int64 v64; // rax
  int v65; // r14d
  int v66; // edx
  const char *v67; // r8
  int v68; // r9d
  int v69; // eax
  int v70; // edx
  const char *v71; // r8
  int v72; // r9d
  std::_Ref_count_base *v73; // rcx
  std::_Ref_count_base *v74; // rax
  std::_Ref_count_base *v75; // rbx
  float v76; // xmm2_4
  float v77; // xmm1_4
  int v78; // eax
  int v79; // r8d
  int v80; // r9d
  int v81; // r10d
  __int64 v82; // rax
  __int64 v83; // rax
  xpsrdr *v85[2]; // [rsp+48h] [rbp-C0h] BYREF
  xpsrdr *v86[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v87; // [rsp+68h] [rbp-A0h] BYREF
  xpsrdr **v88; // [rsp+70h] [rbp-98h]
  std::_Ref_count_base **v89; // [rsp+78h] [rbp-90h]
  int v90; // [rsp+80h] [rbp-88h] BYREF
  int v91; // [rsp+84h] [rbp-84h] BYREF
  int v92; // [rsp+88h] [rbp-80h] BYREF
  double v93; // [rsp+90h] [rbp-78h] BYREF
  std::_Ref_count_base *v94[2]; // [rsp+98h] [rbp-70h] BYREF
  double v95; // [rsp+A8h] [rbp-60h] BYREF
  std::_Ref_count_base *v96[2]; // [rsp+B0h] [rbp-58h] BYREF
  std::_Ref_count_base *v97[2]; // [rsp+C0h] [rbp-48h] BYREF
  std::_Ref_count_base *v98[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v99; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v100[32]; // [rsp+F8h] [rbp-10h] BYREF

  v93 = *(double *)&a1;
  ++*((_DWORD *)a2[68] + 31);
  std::wstring::wstring(v100);
  v9 = *(_QWORD *)(v8 + 8);
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  v98[0] = *(std::_Ref_count_base **)v8;
  v98[1] = *(std::_Ref_count_base **)(v8 + 8);
  v10 = v98[1];
  xpsrdr::GetPartResourceUri(v98, v100);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  if ( *a4
    || (xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::find(
          a2 + 15,
          v85,
          v100),
        v11 = v85[0],
        (__int64 *)v85[0] == a2[16]) )
  {
    *(_OWORD *)v97 = 0;
    LODWORD(v86[0]) = 0;
    v12 = *a3;
    v13 = **a3;
    v87 = 0;
    v88 = v86;
    v89 = v97;
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v13 + 40))(v12, &v87);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v87);
    if ( SLODWORD(v86[0]) < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v86[0]), v15, v16, v17);
    if ( v14 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v14, v15, v16, v17);
    v86[0] = 0;
    v85[0] = 0;
    v18 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, _QWORD, xpsrdr **))(*(_QWORD *)v97[0] + 40LL))(
            v97[0],
            0,
            0,
            v85);
    if ( v18 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
    *(_OWORD *)v96 = 0;
    LODWORD(v86[0]) = 0;
    v22 = (*(__int64 (__fastcall **)(__int64 *, xpsrdr **))(**a3 + 56))(*a3, v86);
    if ( v22 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v22, (int)v23, v24, v25);
    *(_OWORD *)v98 = 0;
    switch ( LODWORD(v86[0]) )
    {
      case 1:
        v27 = GUID_ContainerFormatJpeg;
        break;
      case 2:
        v27 = GUID_ContainerFormatPng;
        break;
      case 3:
        v27 = GUID_ContainerFormatTiff;
        break;
      default:
        v26 = (xpsrdr *)(unsigned int)(LODWORD(v86[0]) - 4);
        if ( (unsigned int)v26 >= 2 )
          xpsrdr::ThrowLogicException(v26, v23, (int)v24);
        v27 = GUID_ContainerFormatWmp;
        break;
    }
    *(GUID *)v98 = v27;
    LODWORD(v85[0]) = 0;
    v28 = *a2;
    v29 = **a2;
    v87 = 0;
    v88 = v85;
    v89 = v96;
    v30 = (*(__int64 (__fastcall **)(__int64 *, std::_Ref_count_base **, _QWORD, __int64 *))(v29 + 56))(
            v28,
            v98,
            0,
            &v87);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v87);
    if ( SLODWORD(v85[0]) < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v85[0]), v31, v32, v33);
    if ( v30 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v30, v31, v32, v33);
    v34 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base *, _QWORD))(*(_QWORD *)v96[0] + 32LL))(
            v96[0],
            v97[0],
            0);
    if ( v34 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v34, v35, v36, v37);
    v90 = 0;
    v38 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *))(*(_QWORD *)v96[0] + 96LL))(v96[0], &v90);
    if ( v38 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v38, (int)v39, v41, v42);
    if ( !v90 )
      xpsrdr::ThrowLogicException(v40, v39, (int)v41);
    *(_OWORD *)v94 = 0;
    LODWORD(v85[0]) = 0;
    v43 = *(_QWORD *)v96[0];
    v87 = 0;
    v88 = v85;
    v89 = v94;
    v44 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, __int64 *))(v43 + 104))(v96[0], 0, &v87);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v87);
    if ( SLODWORD(v85[0]) < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v85[0]), v45, v46, v47);
    if ( v44 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v44, v45, v46, v47);
    v92 = 0;
    v91 = 0;
    v48 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *, int *))(*(_QWORD *)v94[0] + 24LL))(
            v94[0],
            &v92,
            &v91);
    if ( v48 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v48, v49, v50, v51);
    v93 = 0.0;
    v95 = 0.0;
    v52 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, double *, double *))(*(_QWORD *)v94[0] + 40LL))(
            v94[0],
            &v93,
            &v95);
    if ( v52 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v52, v53, v54, v55);
    HasAlpha = xpsrdr::ImageHasAlpha(a2, v94);
    xpsrdr::GetWICBitmap((unsigned int)v98, (_DWORD)a2, (unsigned int)v94, (_DWORD)a4);
    v99 = 0;
    v57 = v98[0];
    v58 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int128 *))(*(_QWORD *)v98[0] + 32LL))(v98[0], &v99);
    if ( v58 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v58, v59, v60, v61);
    v62 = v99 - *(_QWORD *)((char *)a2 + 100);
    if ( (__int64 *)v99 == *(__int64 **)((char *)a2 + 100) )
      v62 = *((_QWORD *)&v99 + 1) - *(_QWORD *)((char *)a2 + 108);
    if ( v62 )
    {
      *(_OWORD *)v86 = 0;
      LODWORD(v85[0]) = 0;
      v63 = *a2;
      v64 = **a2;
      v87 = 0;
      v88 = v85;
      v89 = v86;
      v65 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v64 + 80))(v63, &v87);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v87);
      if ( SLODWORD(v85[0]) < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v85[0]), v66, v67, v68);
      if ( v65 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v65, v66, v67, v68);
      v69 = (*(__int64 (__fastcall **)(xpsrdr *, std::_Ref_count_base *, __int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v86[0] + 64LL))(
              v86[0],
              v57,
              (__int64)a2 + 100,
              0,
              0,
              0,
              0);
      if ( v69 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v69, v70, v71, v72);
      v73 = v86[1];
      if ( v86[1] )
      {
        _InterlockedIncrement((volatile signed __int32 *)v86[1] + 2);
        v73 = v86[1];
      }
      v98[0] = v86[0];
      v74 = v98[1];
      v75 = v73;
      v98[1] = v73;
      if ( v74 )
      {
        std::_Ref_count_base::_Decref(v74);
        v73 = v86[1];
      }
      if ( v73 )
        std::_Ref_count_base::_Decref(v73);
    }
    else
    {
      v75 = v98[1];
    }
    v85[0] = (xpsrdr *)operator new(0x48u);
    v76 = (float)(int)(v95 + 0.5);
    v77 = (float)(int)(v93 + 0.5);
    v78 = std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(&v87, v98);
    v82 = xpsrdr::Image::Image(v81, (unsigned int)v100, v78, v80, v79, LODWORD(v77), LODWORD(v76), HasAlpha);
    std::shared_ptr<xpsrdr::Image>::shared_ptr<xpsrdr::Image>(v85, v82);
    if ( !*a4 )
    {
      v83 = xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::operator[](
              a2 + 15,
              v100);
      std::shared_ptr<ID2D1Brush>::operator=(v83, v85);
    }
    *a1 = v85[0];
    a1[1] = v85[1];
    if ( v75 )
      std::_Ref_count_base::_Decref(v75);
    if ( v94[1] )
      std::_Ref_count_base::_Decref(v94[1]);
    if ( v96[1] )
      std::_Ref_count_base::_Decref(v96[1]);
    if ( v97[1] )
      std::_Ref_count_base::_Decref(v97[1]);
  }
  else
  {
    ++*((_DWORD *)a2[68] + 32);
    std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(a1, (char *)v11 + 48);
  }
  std::wstring::_Tidy_deallocate(v100);
  return a1;
}

```

## disassembly

```asm
0x1800bad68  mov     rax, rsp
0x1800bad6b  push    rbp
0x1800bad6c  push    rbx
0x1800bad6d  push    rsi
0x1800bad6e  push    rdi
0x1800bad6f  push    r12
0x1800bad71  push    r13
0x1800bad73  push    r14
0x1800bad75  push    r15
0x1800bad77  lea     rbp, [rax-78h]
0x1800bad7b  sub     rsp, 138h
0x1800bad82  movaps  xmmword ptr [rax-58h], xmm6
0x1800bad86  mov     rax, cs:__security_cookie
0x1800bad8d  xor     rax, rsp
0x1800bad90  mov     [rbp+70h+var_60], rax
0x1800bad94  mov     r12, r9
0x1800bad97  mov     r14, r8
0x1800bad9a  mov     rdi, rdx
0x1800bad9d  mov     rsi, rcx
0x1800bada0  mov     [rbp+70h+var_E8], rcx
0x1800bada4  xor     r15d, r15d
0x1800bada7  mov     rax, [rdx+220h]
0x1800badae  inc     dword ptr [rax+7Ch]
0x1800badb1  lea     rcx, [rbp+70h+var_80]
0x1800badb5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800badba  nop
0x1800badbb  mov     rax, [r8+8]
0x1800badbf  test    rax, rax
0x1800badc2  jz      short loc_1800BADC8
0x1800badc4  lock inc dword ptr [rax+8]
0x1800badc8  mov     rax, [r8]
0x1800badcb  mov     [rbp+70h+var_A0], rax
0x1800badcf  mov     rbx, [r8+8]
0x1800badd3  mov     [rbp+70h+var_A0+8], rbx
0x1800badd7  lea     rdx, [rbp+70h+var_80]
0x1800baddb  lea     rcx, [rbp+70h+var_A0]
0x1800baddf  call    ?GetPartResourceUri@xpsrdr@@YAXAEBV?$shared_ptr@UIXpsOMPart@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; xpsrdr::GetPartResourceUri(std::shared_ptr<IXpsOMPart> const &,std::wstring &)
0x1800bade4  nop
0x1800bade5  test    rbx, rbx
0x1800bade8  jz      short loc_1800BADF2
0x1800badea  mov     rcx, rbx; this
0x1800baded  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800badf2  cmp     [r12], r15
0x1800badf6  jnz     short loc_1800BAE36
0x1800badf8  lea     r8, [rbp+70h+var_80]
0x1800badfc  lea     rdx, [rsp+170h+var_130]
0x1800bae01  lea     rcx, [rdi+78h]
0x1800bae05  call    ?find@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::find(std::wstring const &)
0x1800bae0a  mov     rdx, [rsp+170h+var_130]
0x1800bae0f  cmp     rdx, [rdi+80h]
0x1800bae16  jz      short loc_1800BAE36
0x1800bae18  mov     rcx, [rdi+220h]
0x1800bae1f  inc     dword ptr [rcx+80h]
0x1800bae25  add     rdx, 30h ; '0'
0x1800bae29  mov     rcx, rsi
0x1800bae2c  call    ??0?$shared_ptr@UID2D1Bitmap@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(std::shared_ptr<ID2D1Bitmap> const &)
0x1800bae31  jmp     loc_1800BB30C
0x1800bae36  xorps   xmm0, xmm0
0x1800bae39  movdqu  xmmword ptr [rbp+70h+var_B8], xmm0
0x1800bae3e  mov     dword ptr [rsp+170h+var_128+8], r15d
0x1800bae43  mov     rcx, [r14]
0x1800bae46  mov     rax, [rcx]
0x1800bae49  mov     [rsp+170h+var_110], r15
0x1800bae4e  lea     rdx, [rsp+170h+var_128+8]
0x1800bae53  mov     [rsp+170h+var_108], rdx
0x1800bae58  lea     rdx, [rbp+70h+var_B8]
0x1800bae5c  mov     qword ptr [rsp+170h+var_100], rdx
0x1800bae61  lea     rdx, [rsp+170h+var_110]
0x1800bae66  mov     rax, [rax+28h]
0x1800bae6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae6f  mov     ebx, eax
0x1800bae71  lea     rcx, [rsp+170h+var_110]
0x1800bae76  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bae7b  mov     ecx, dword ptr [rsp+170h+var_128+8]; this
0x1800bae7f  test    ecx, ecx
0x1800bae81  jns     short loc_1800BAE89
0x1800bae83  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bae89  test    ebx, ebx
0x1800bae8b  jns     short loc_1800BAE95
0x1800bae8d  mov     ecx, ebx; this
0x1800bae8f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bae95  mov     [rsp+170h+var_128+8], r15
0x1800bae9a  mov     [rsp+170h+var_130], r15
0x1800bae9f  mov     rcx, [rbp+70h+var_B8]
0x1800baea3  mov     rax, [rcx]
0x1800baea6  lea     r9, [rsp+170h+var_130]
0x1800baeab  xor     r8d, r8d
0x1800baeae  mov     rdx, r15
0x1800baeb1  mov     rax, [rax+28h]
0x1800baeb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baeba  test    eax, eax
0x1800baebc  jns     short loc_1800BAEC6
0x1800baebe  mov     ecx, eax; this
0x1800baec0  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800baec6  xorps   xmm0, xmm0
0x1800baec9  movdqu  xmmword ptr [rbp+70h+var_C8], xmm0
0x1800baece  mov     dword ptr [rsp+170h+var_128+8], r15d
0x1800baed3  mov     rcx, [r14]
0x1800baed6  mov     rax, [rcx]
0x1800baed9  lea     rdx, [rsp+170h+var_128+8]
0x1800baede  mov     rax, [rax+38h]
0x1800baee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baee7  test    eax, eax
0x1800baee9  jns     short loc_1800BAEF3
0x1800baeeb  mov     ecx, eax; this
0x1800baeed  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800baef3  xorps   xmm0, xmm0
0x1800baef6  movups  xmmword ptr [rbp+70h+var_A0], xmm0
0x1800baefa  mov     ecx, dword ptr [rsp+170h+var_128+8]
0x1800baefe  sub     ecx, 1
0x1800baf01  jz      short loc_1800BAF38
0x1800baf03  sub     ecx, 1
0x1800baf06  jz      short loc_1800BAF2F
0x1800baf08  sub     ecx, 1
0x1800baf0b  jz      short loc_1800BAF26
0x1800baf0d  sub     ecx, 1; this
0x1800baf10  jz      short loc_1800BAF1D
0x1800baf12  cmp     ecx, 1
0x1800baf15  jz      short loc_1800BAF1D
0x1800baf17  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800baf1d  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatWmp.Data1
0x1800baf24  jmp     short loc_1800BAF3F
0x1800baf26  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatTiff.Data1
0x1800baf2d  jmp     short loc_1800BAF3F
0x1800baf2f  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatPng.Data1
0x1800baf36  jmp     short loc_1800BAF3F
0x1800baf38  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatJpeg.Data1
0x1800baf3f  movdqu  xmmword ptr [rbp+70h+var_A0], xmm0
0x1800baf44  mov     dword ptr [rsp+170h+var_130], r15d
0x1800baf49  mov     rcx, [rdi]
0x1800baf4c  mov     rax, [rcx]
0x1800baf4f  mov     [rsp+170h+var_110], r15
0x1800baf54  lea     rdx, [rsp+170h+var_130]
0x1800baf59  mov     [rsp+170h+var_108], rdx
0x1800baf5e  lea     rdx, [rbp+70h+var_C8]
0x1800baf62  mov     qword ptr [rsp+170h+var_100], rdx
0x1800baf67  lea     r9, [rsp+170h+var_110]
0x1800baf6c  xor     r8d, r8d
0x1800baf6f  lea     rdx, [rbp+70h+var_A0]
0x1800baf73  mov     rax, [rax+38h]
0x1800baf77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baf7c  mov     ebx, eax
0x1800baf7e  lea     rcx, [rsp+170h+var_110]
0x1800baf83  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800baf88  mov     ecx, dword ptr [rsp+170h+var_130]; this
0x1800baf8c  test    ecx, ecx
0x1800baf8e  jns     short loc_1800BAF96
0x1800baf90  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800baf96  test    ebx, ebx
0x1800baf98  jns     short loc_1800BAFA2
0x1800baf9a  mov     ecx, ebx; this
0x1800baf9c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bafa2  mov     rcx, [rbp+70h+var_C8]
0x1800bafa6  mov     rax, [rcx]
0x1800bafa9  xor     r8d, r8d
0x1800bafac  mov     rdx, [rbp+70h+var_B8]
0x1800bafb0  mov     rax, [rax+20h]
0x1800bafb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bafb9  test    eax, eax
0x1800bafbb  jns     short loc_1800BAFC5
0x1800bafbd  mov     ecx, eax; this
0x1800bafbf  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bafc5  mov     [rsp+170h+var_F8], r15d
0x1800bafca  mov     rcx, [rbp+70h+var_C8]
0x1800bafce  mov     rax, [rcx]
0x1800bafd1  lea     rdx, [rsp+170h+var_F8]
0x1800bafd6  mov     rax, [rax+60h]
0x1800bafda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bafdf  test    eax, eax
0x1800bafe1  jns     short loc_1800BAFEB
0x1800bafe3  mov     ecx, eax; this
0x1800bafe5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bafeb  cmp     [rsp+170h+var_F8], r15d
0x1800baff0  ja      short loc_1800BAFF8
0x1800baff2  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800baff8  xorps   xmm0, xmm0
0x1800baffb  movdqu  xmmword ptr [rbp+70h+var_E0], xmm0
0x1800bb000  mov     dword ptr [rsp+170h+var_130], r15d
0x1800bb005  mov     rcx, [rbp+70h+var_C8]
0x1800bb009  mov     rax, [rcx]
0x1800bb00c  mov     [rsp+170h+var_110], r15
0x1800bb011  lea     rdx, [rsp+170h+var_130]
0x1800bb016  mov     [rsp+170h+var_108], rdx
0x1800bb01b  lea     rdx, [rbp+70h+var_E0]
0x1800bb01f  mov     qword ptr [rsp+170h+var_100], rdx
0x1800bb024  lea     r8, [rsp+170h+var_110]
0x1800bb029  xor     edx, edx
0x1800bb02b  mov     rax, [rax+68h]
0x1800bb02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb034  mov     ebx, eax
0x1800bb036  lea     rcx, [rsp+170h+var_110]
0x1800bb03b  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bb040  mov     ecx, dword ptr [rsp+170h+var_130]; this
0x1800bb044  test    ecx, ecx
0x1800bb046  jns     short loc_1800BB04E
0x1800bb048  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bb04e  test    ebx, ebx
0x1800bb050  jns     short loc_1800BB05A
0x1800bb052  mov     ecx, ebx; this
0x1800bb054  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bb05a  mov     [rbp+70h+var_F0], r15d
0x1800bb05e  mov     [rsp+170h+var_F4], r15d
0x1800bb063  mov     rcx, [rbp+70h+var_E0]
0x1800bb067  mov     rax, [rcx]
0x1800bb06a  lea     r8, [rsp+170h+var_F4]
0x1800bb06f  lea     rdx, [rbp+70h+var_F0]
0x1800bb073  mov     rax, [rax+18h]
0x1800bb077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb07c  test    eax, eax
0x1800bb07e  jns     short loc_1800BB088
0x1800bb080  mov     ecx, eax; this
0x1800bb082  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bb088  xorps   xmm6, xmm6
0x1800bb08b  movsd   [rbp+70h+var_E8], xmm6
0x1800bb090  movsd   [rbp+70h+var_D0], xmm6
0x1800bb095  mov     rcx, [rbp+70h+var_E0]
0x1800bb099  mov     rax, [rcx]
0x1800bb09c  lea     r8, [rbp+70h+var_D0]
0x1800bb0a0  lea     rdx, [rbp+70h+var_E8]
0x1800bb0a4  mov     rax, [rax+28h]
0x1800bb0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb0ad  test    eax, eax
0x1800bb0af  jns     short loc_1800BB0B9
0x1800bb0b1  mov     ecx, eax; this
0x1800bb0b3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bb0b9  lea     rdx, [rbp+70h+var_E0]
0x1800bb0bd  mov     rcx, rdi
0x1800bb0c0  call    ?ImageHasAlpha@xpsrdr@@YA_NAEAURenderState@1@AEBV?$shared_ptr@UIWICBitmapFrameDecode@@@std@@@Z; xpsrdr::ImageHasAlpha(xpsrdr::RenderState &,std::shared_ptr<IWICBitmapFrameDecode> const &)
0x1800bb0c5  mov     r13b, al
0x1800bb0c8  mov     r9, r12
0x1800bb0cb  lea     r8, [rbp+70h+var_E0]
0x1800bb0cf  mov     rdx, rdi
0x1800bb0d2  lea     rcx, [rbp+70h+var_A0]
0x1800bb0d6  call    ?GetWICBitmap@xpsrdr@@YA?AV?$shared_ptr@UIWICBitmapSource@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIWICBitmapFrameDecode@@@3@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@3@_N@Z; xpsrdr::GetWICBitmap(xpsrdr::RenderState &,std::shared_ptr<IWICBitmapFrameDecode> const &,std::shared_ptr<IXpsOMColorProfileResource> const &,bool)
0x1800bb0db  nop
0x1800bb0dc  xorps   xmm0, xmm0
0x1800bb0df  movups  [rbp+70h+var_90], xmm0
0x1800bb0e3  mov     r15, [rbp+70h+var_A0]
0x1800bb0e7  mov     rcx, [r15]
0x1800bb0ea  mov     rax, [rcx+20h]
0x1800bb0ee  lea     rdx, [rbp+70h+var_90]
0x1800bb0f2  mov     rcx, r15
0x1800bb0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb0fa  xor     r14d, r14d
0x1800bb0fd  test    eax, eax
0x1800bb0ff  jns     short loc_1800BB109
0x1800bb101  mov     ecx, eax; this
0x1800bb103  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bb109  mov     rax, qword ptr [rbp+70h+var_90]
0x1800bb10d  sub     rax, [rdi+64h]
0x1800bb111  jnz     short loc_1800BB11B
0x1800bb113  mov     rax, qword ptr [rbp+70h+var_90+8]
0x1800bb117  sub     rax, [rdi+6Ch]
0x1800bb11b  test    rax, rax
0x1800bb11e  jz      loc_1800BB207
0x1800bb124  xorps   xmm0, xmm0
0x1800bb127  movdqu  xmmword ptr [rsp+170h+var_128+8], xmm0
0x1800bb12d  mov     dword ptr [rsp+170h+var_130], r14d
0x1800bb132  mov     rcx, [rdi]
0x1800bb135  mov     rax, [rcx]
0x1800bb138  mov     [rsp+170h+var_110], r14
0x1800bb13d  lea     rdx, [rsp+170h+var_130]
0x1800bb142  mov     [rsp+170h+var_108], rdx
0x1800bb147  lea     rdx, [rsp+170h+var_128+8]
0x1800bb14c  mov     qword ptr [rsp+170h+var_100], rdx
0x1800bb151  lea     rdx, [rsp+170h+var_110]
0x1800bb156  mov     rax, [rax+50h]
0x1800bb15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb15f  mov     r14d, eax
0x1800bb162  lea     rcx, [rsp+170h+var_110]
0x1800bb167  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bb16c  mov     ecx, dword ptr [rsp+170h+var_130]; this
0x1800bb170  test    ecx, ecx
0x1800bb172  jns     short loc_1800BB17A
0x1800bb174  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bb17a  test    r14d, r14d
0x1800bb17d  jns     short loc_1800BB188
0x1800bb17f  mov     ecx, r14d; this
0x1800bb182  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bb188  mov     rcx, [rsp+170h+var_128+8]
0x1800bb18d  mov     rax, [rcx]
0x1800bb190  xor     r14d, r14d
0x1800bb193  mov     dword ptr [rsp+170h+var_140], r14d
0x1800bb198  movsd   qword ptr [rsp+170h+var_148], xmm6
0x1800bb19e  mov     [rsp+170h+var_150], r14
0x1800bb1a3  xor     r9d, r9d
0x1800bb1a6  lea     r8, [rdi+64h]
0x1800bb1aa  mov     rdx, r15
0x1800bb1ad  mov     rax, [rax+40h]
0x1800bb1b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb1b6  test    eax, eax
0x1800bb1b8  jns     short loc_1800BB1C2
0x1800bb1ba  mov     ecx, eax; this
0x1800bb1bc  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bb1c2  mov     rcx, [rsp+170h+var_118]
0x1800bb1c7  test    rcx, rcx
0x1800bb1ca  jz      short loc_1800BB1D5
0x1800bb1cc  lock inc dword ptr [rcx+8]
0x1800bb1d0  mov     rcx, [rsp+170h+var_118]
0x1800bb1d5  mov     rax, [rsp+170h+var_128+8]
  ... truncated ...
```
