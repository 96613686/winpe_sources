# xpsrdr::Image::CreateImage(xpsrdr::RenderState &,std::shared_ptr<IXpsOMImageResource> const &,std::shared_ptr<IXpsOMColorProfileResource> const &,bool)

- ea: `0x18003edd0`
- end: `0x18003f3a2`
- name: `?CreateImage@Image@xpsrdr@@SA?AV?$shared_ptr@UImage@xpsrdr@@@std@@AEAURenderState@2@AEBV?$shared_ptr@UIXpsOMImageResource@@@4@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@4@_N@Z`
- size: `1490`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x18002ab88`
- `0x180040014`

## callees

- `0x180008830`
- `0x180008854`
- `0x18000d61c`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e130`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e5ec`
- `0x18000e990`
- `0x180011b0c`
- `0x1800184e8`
- `0x18001cf2c`
- `0x18001df50`
- `0x1800229e8`
- `0x180023fac`
- `0x1800345fc`
- `0x180036674`
- `0x1800368f0`
- `0x180036e4c`
- `0x180037278`
- `0x1800372e4`
- `0x18003eaa0`
- `0x18003eb20`
- `0x18003ebd8`
- `0x18003edd0`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall xpsrdr::Image::CreateImage(__int64 a1, __int64 **a2, __int64 **a3, __int64 a4)
{
  __int64 v8; // r8
  xpsrdr **v9; // rax
  __int64 v10; // rax
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // ebx
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  int v17; // eax
  int v18; // edx
  const char *v19; // r8
  int v20; // r9d
  int v21; // eax
  const char *v22; // rdx
  const char *v23; // r8
  int v24; // r9d
  xpsrdr *v25; // rcx
  GUID v26; // xmm0
  __int64 *v27; // rcx
  __int64 v28; // rax
  int v29; // ebx
  int v30; // edx
  const char *v31; // r8
  int v32; // r9d
  int v33; // eax
  int v34; // edx
  const char *v35; // r8
  int v36; // r9d
  int v37; // eax
  const char *v38; // rdx
  xpsrdr *v39; // rcx
  const char *v40; // r8
  int v41; // r9d
  __int64 v42; // rax
  int v43; // ebx
  int v44; // edx
  const char *v45; // r8
  int v46; // r9d
  int v47; // eax
  int v48; // edx
  const char *v49; // r8
  int v50; // r9d
  int v51; // eax
  int v52; // edx
  const char *v53; // r8
  int v54; // r9d
  char HasAlpha; // r12
  __int64 v56; // r15
  int v57; // eax
  int v58; // edx
  const char *v59; // r8
  int v60; // r9d
  __int64 v61; // rax
  __int64 *v62; // rcx
  __int64 v63; // rax
  int v64; // r14d
  int v65; // edx
  const char *v66; // r8
  int v67; // r9d
  int v68; // eax
  int v69; // edx
  const char *v70; // r8
  int v71; // r9d
  float v72; // xmm2_4
  float v73; // xmm1_4
  int v74; // r8d
  int v75; // r9d
  int v76; // r10d
  __int64 v77; // rax
  __int64 v78; // rax
  xpsrdr *v80; // [rsp+40h] [rbp-C0h] BYREF
  xpsrdr *v81[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v82; // [rsp+58h] [rbp-A8h] BYREF
  xpsrdr **v83; // [rsp+60h] [rbp-A0h]
  _QWORD *v84; // [rsp+68h] [rbp-98h]
  int v85; // [rsp+70h] [rbp-90h] BYREF
  int v86; // [rsp+74h] [rbp-8Ch] BYREF
  int v87; // [rsp+78h] [rbp-88h] BYREF
  double v88; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v89[2]; // [rsp+88h] [rbp-78h] BYREF
  double v90; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v91[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v92[3]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v93[3]; // [rsp+C8h] [rbp-38h] BYREF
  GUID v94; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v95; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v96[32]; // [rsp+100h] [rbp+0h] BYREF

  v88 = *(double *)&a1;
  ++*((_DWORD *)a2[68] + 31);
  std::wstring::wstring(v96);
  std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(&v82, v8);
  xpsrdr::GetPartResourceUri(&v82, v96);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v82);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(a4)
    || (xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::find(
          a2 + 15,
          v81,
          v96),
        v9 = (xpsrdr **)xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(
                          a2 + 15,
                          &v80),
        v81[0] == *v9) )
  {
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v92);
    LODWORD(v80) = 0;
    v11 = *a3;
    v12 = **a3;
    v82 = 0;
    v83 = &v80;
    v84 = v92;
    v13 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v12 + 40))(v11, &v82);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v82);
    if ( (int)v80 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v80, v14, v15, v16);
    if ( v13 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
    v80 = 0;
    v81[0] = 0;
    v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, xpsrdr **))(*(_QWORD *)v92[0] + 40LL))(v92[0], 0, 0, v81);
    if ( v17 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v17, v18, v19, v20);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v91);
    LODWORD(v80) = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, xpsrdr **))(**a3 + 56))(*a3, &v80);
    if ( v21 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v21, (int)v22, v23, v24);
    v94 = 0;
    switch ( (_DWORD)v80 )
    {
      case 1:
        v26 = GUID_ContainerFormatJpeg;
        break;
      case 2:
        v26 = GUID_ContainerFormatPng;
        break;
      case 3:
        v26 = GUID_ContainerFormatTiff;
        break;
      default:
        v25 = (xpsrdr *)(unsigned int)((_DWORD)v80 - 4);
        if ( (unsigned int)v25 >= 2 )
          xpsrdr::ThrowLogicException(v25, v22, (int)v23);
        v26 = GUID_ContainerFormatWmp;
        break;
    }
    v94 = v26;
    LODWORD(v81[0]) = 0;
    v27 = *a2;
    v28 = **a2;
    v82 = 0;
    v83 = v81;
    v84 = v91;
    v29 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD, __int64 *))(v28 + 56))(v27, &v94, 0, &v82);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v82);
    if ( SLODWORD(v81[0]) < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v81[0]), v30, v31, v32);
    if ( v29 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v29, v30, v31, v32);
    v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v91[0] + 32LL))(v91[0], v92[0], 0);
    if ( v33 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v33, v34, v35, v36);
    v85 = 0;
    v37 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v91[0] + 96LL))(v91[0], &v85);
    if ( v37 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v37, (int)v38, v40, v41);
    if ( !v85 )
      xpsrdr::ThrowLogicException(v39, v38, (int)v40);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v89);
    LODWORD(v81[0]) = 0;
    v42 = *(_QWORD *)v91[0];
    v82 = 0;
    v83 = v81;
    v84 = v89;
    v43 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(v42 + 104))(v91[0], 0, &v82);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v82);
    if ( SLODWORD(v81[0]) < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v81[0]), v44, v45, v46);
    if ( v43 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v43, v44, v45, v46);
    v87 = 0;
    v86 = 0;
    v47 = (*(__int64 (__fastcall **)(_QWORD, int *, int *))(*(_QWORD *)v89[0] + 24LL))(v89[0], &v87, &v86);
    if ( v47 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v47, v48, v49, v50);
    v88 = 0.0;
    v90 = 0.0;
    v51 = (*(__int64 (__fastcall **)(_QWORD, double *, double *))(*(_QWORD *)v89[0] + 40LL))(v89[0], &v88, &v90);
    if ( v51 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v51, v52, v53, v54);
    HasAlpha = xpsrdr::ImageHasAlpha(a2, v89);
    xpsrdr::GetWICBitmap((unsigned int)&v82, (_DWORD)a2, (unsigned int)v89, a4, 0);
    v95 = 0;
    v56 = v82;
    v57 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v82 + 32LL))(v82, &v95);
    if ( v57 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v57, v58, v59, v60);
    v61 = v95 - *(_QWORD *)((char *)a2 + 100);
    if ( (__int64 *)v95 == *(__int64 **)((char *)a2 + 100) )
      v61 = *((_QWORD *)&v95 + 1) - *(_QWORD *)((char *)a2 + 108);
    if ( v61 )
    {
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v94);
      LODWORD(v81[0]) = 0;
      v62 = *a2;
      v63 = **a2;
      v93[0] = 0;
      v93[1] = v81;
      v93[2] = &v94;
      v64 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(v63 + 80))(v62, v93);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v93);
      if ( SLODWORD(v81[0]) < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v81[0]), v65, v66, v67);
      if ( v64 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v64, v65, v66, v67);
      v68 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD, _QWORD, _DWORD))(**(_QWORD **)&v94.Data1
                                                                                                + 64LL))(
              *(_QWORD *)&v94.Data1,
              v56,
              (__int64)a2 + 100,
              0,
              0,
              0,
              0);
      if ( v68 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v68, v69, v70, v71);
      std::shared_ptr<ID2D1Brush>::operator=<ID2D1ImageBrush,0>(&v82, &v94);
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v94);
    }
    v81[0] = (xpsrdr *)operator new(0x48u);
    v72 = (float)(int)(v90 + 0.5);
    v73 = (float)(int)(v88 + 0.5);
    std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(&v94);
    std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(&v94, &v82);
    v77 = xpsrdr::Image::Image(
            v76,
            (unsigned int)v96,
            (unsigned int)&v94,
            v75,
            v74,
            LODWORD(v73),
            LODWORD(v72),
            HasAlpha);
    std::shared_ptr<xpsrdr::Image>::shared_ptr<xpsrdr::Image>(v81, v77);
    if ( !(unsigned __int8)std::operator!=<ID3D11Device>(a4) )
    {
      v78 = xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::operator[](
              a2 + 15,
              v96);
      std::shared_ptr<ID2D1Brush>::operator=(v78, v81);
    }
    std::shared_ptr<IWICBitmapSource>::shared_ptr<IWICBitmapSource>(a1, v81);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v81);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v82);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v89);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v91);
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(v92);
  }
  else
  {
    ++*((_DWORD *)a2[68] + 32);
    std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(a1);
    v10 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v81);
    std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(a1, v10 + 32);
  }
  std::wstring::~wstring(v96);
  return a1;
}

```

## disassembly

```asm
0x18003edd0  mov     rax, rsp
0x18003edd3  push    rbp
0x18003edd4  push    rbx
0x18003edd5  push    rsi
0x18003edd6  push    rdi
0x18003edd7  push    r12
0x18003edd9  push    r13
0x18003eddb  push    r14
0x18003eddd  push    r15
0x18003eddf  lea     rbp, [rsp-48h]
0x18003ede4  sub     rsp, 148h
0x18003edeb  movaps  xmmword ptr [rax-58h], xmm6
0x18003edef  mov     rax, cs:__security_cookie
0x18003edf6  xor     rax, rsp
0x18003edf9  mov     [rbp+80h+var_60], rax
0x18003edfd  mov     r13, r9
0x18003ee00  mov     r14, r8
0x18003ee03  mov     rdi, rdx
0x18003ee06  mov     rsi, rcx
0x18003ee09  mov     [rbp+80h+var_100], rcx
0x18003ee0d  xor     r15d, r15d
0x18003ee10  mov     rax, [rdx+220h]
0x18003ee17  inc     dword ptr [rax+7Ch]
0x18003ee1a  lea     rcx, [rbp+80h+var_80]
0x18003ee1e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003ee23  nop
0x18003ee24  mov     rdx, r8
0x18003ee27  lea     rcx, [rsp+180h+var_128]
0x18003ee2c  call    ??$?0UID2D1TransformedGeometry@@$0A@@?$shared_ptr@UID2D1Geometry@@@std@@QEAA@AEBV?$shared_ptr@UID2D1TransformedGeometry@@@1@@Z; std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(std::shared_ptr<ID2D1TransformedGeometry> const &)
0x18003ee31  nop
0x18003ee32  lea     rdx, [rbp+80h+var_80]
0x18003ee36  lea     rcx, [rsp+180h+var_128]
0x18003ee3b  call    ?GetPartResourceUri@xpsrdr@@YAXAEBV?$shared_ptr@UIXpsOMPart@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; xpsrdr::GetPartResourceUri(std::shared_ptr<IXpsOMPart> const &,std::wstring &)
0x18003ee40  nop
0x18003ee41  lea     rcx, [rsp+180h+var_128]
0x18003ee46  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x18003ee4b  mov     rcx, r13
0x18003ee4e  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18003ee53  test    al, al
0x18003ee55  jnz     short loc_18003EEB1
0x18003ee57  lea     r8, [rbp+80h+var_80]
0x18003ee5b  lea     rdx, [rsp+180h+var_138]
0x18003ee60  lea     rcx, [rdi+78h]
0x18003ee64  call    ?find@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::find(std::wstring const &)
0x18003ee69  lea     rdx, [rsp+180h+var_140]
0x18003ee6e  lea     rcx, [rdi+78h]
0x18003ee72  call    ?end@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@XZ; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::end(void)
0x18003ee77  mov     rcx, [rax]
0x18003ee7a  cmp     [rsp+180h+var_138], rcx
0x18003ee7f  jz      short loc_18003EEB1
0x18003ee81  mov     rcx, [rdi+220h]
0x18003ee88  inc     dword ptr [rcx+80h]
0x18003ee8e  mov     rcx, rsi
0x18003ee91  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x18003ee96  lea     rcx, [rsp+180h+var_138]
0x18003ee9b  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18003eea0  lea     rdx, [rax+20h]
0x18003eea4  mov     rcx, rsi
0x18003eea7  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x18003eeac  jmp     loc_18003F36E
0x18003eeb1  lea     rcx, [rbp+80h+var_D0]
0x18003eeb5  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003eeba  nop
0x18003eebb  mov     dword ptr [rsp+180h+var_140], r15d
0x18003eec0  mov     rcx, [r14]
0x18003eec3  mov     rax, [rcx]
0x18003eec6  mov     [rsp+180h+var_128], r15
0x18003eecb  lea     rdx, [rsp+180h+var_140]
0x18003eed0  mov     [rsp+180h+var_120], rdx
0x18003eed5  lea     rdx, [rbp+80h+var_D0]
0x18003eed9  mov     [rsp+180h+var_118], rdx
0x18003eede  lea     rdx, [rsp+180h+var_128]
0x18003eee3  mov     rax, [rax+28h]
0x18003eee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eeec  mov     ebx, eax
0x18003eeee  lea     rcx, [rsp+180h+var_128]
0x18003eef3  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003eef8  mov     ecx, dword ptr [rsp+180h+var_140]; this
0x18003eefc  test    ecx, ecx
0x18003eefe  jns     short loc_18003EF06
0x18003ef00  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003ef06  test    ebx, ebx
0x18003ef08  jns     short loc_18003EF12
0x18003ef0a  mov     ecx, ebx; this
0x18003ef0c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003ef12  mov     [rsp+180h+var_140], r15
0x18003ef17  mov     [rsp+180h+var_138], r15
0x18003ef1c  mov     rcx, [rbp+80h+var_D0]
0x18003ef20  mov     rax, [rcx]
0x18003ef23  lea     r9, [rsp+180h+var_138]
0x18003ef28  xor     r8d, r8d
0x18003ef2b  mov     rdx, r15
0x18003ef2e  mov     rax, [rax+28h]
0x18003ef32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef37  test    eax, eax
0x18003ef39  jns     short loc_18003EF43
0x18003ef3b  mov     ecx, eax; this
0x18003ef3d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003ef43  lea     rcx, [rbp+80h+var_E0]
0x18003ef47  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003ef4c  nop
0x18003ef4d  mov     dword ptr [rsp+180h+var_140], r15d
0x18003ef52  mov     rcx, [r14]
0x18003ef55  mov     rax, [rcx]
0x18003ef58  lea     rdx, [rsp+180h+var_140]
0x18003ef5d  mov     rax, [rax+38h]
0x18003ef61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef66  test    eax, eax
0x18003ef68  jns     short loc_18003EF72
0x18003ef6a  mov     ecx, eax; this
0x18003ef6c  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003ef72  xorps   xmm0, xmm0
0x18003ef75  movups  [rbp+80h+var_A0], xmm0
0x18003ef79  mov     ecx, dword ptr [rsp+180h+var_140]
0x18003ef7d  sub     ecx, 1
0x18003ef80  jz      short loc_18003EFB7
0x18003ef82  sub     ecx, 1
0x18003ef85  jz      short loc_18003EFAE
0x18003ef87  sub     ecx, 1
0x18003ef8a  jz      short loc_18003EFA5
0x18003ef8c  sub     ecx, 1; this
0x18003ef8f  jz      short loc_18003EF9C
0x18003ef91  cmp     ecx, 1
0x18003ef94  jz      short loc_18003EF9C
0x18003ef96  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003ef9c  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatWmp.Data1
0x18003efa3  jmp     short loc_18003EFBE
0x18003efa5  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatTiff.Data1
0x18003efac  jmp     short loc_18003EFBE
0x18003efae  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatPng.Data1
0x18003efb5  jmp     short loc_18003EFBE
0x18003efb7  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatJpeg.Data1
0x18003efbe  movdqu  [rbp+80h+var_A0], xmm0
0x18003efc3  mov     dword ptr [rsp+180h+var_138], r15d
0x18003efc8  mov     rcx, [rdi]
0x18003efcb  mov     rax, [rcx]
0x18003efce  mov     [rsp+180h+var_128], r15
0x18003efd3  lea     rdx, [rsp+180h+var_138]
0x18003efd8  mov     [rsp+180h+var_120], rdx
0x18003efdd  lea     rdx, [rbp+80h+var_E0]
0x18003efe1  mov     [rsp+180h+var_118], rdx
0x18003efe6  lea     r9, [rsp+180h+var_128]
0x18003efeb  xor     r8d, r8d
0x18003efee  lea     rdx, [rbp+80h+var_A0]
0x18003eff2  mov     rax, [rax+38h]
0x18003eff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003effb  mov     ebx, eax
0x18003effd  lea     rcx, [rsp+180h+var_128]
0x18003f002  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003f007  mov     ecx, dword ptr [rsp+180h+var_138]; this
0x18003f00b  test    ecx, ecx
0x18003f00d  jns     short loc_18003F015
0x18003f00f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f015  test    ebx, ebx
0x18003f017  jns     short loc_18003F021
0x18003f019  mov     ecx, ebx; this
0x18003f01b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f021  mov     rcx, [rbp+80h+var_E0]
0x18003f025  mov     rax, [rcx]
0x18003f028  xor     r8d, r8d
0x18003f02b  mov     rdx, [rbp+80h+var_D0]
0x18003f02f  mov     rax, [rax+20h]
0x18003f033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f038  test    eax, eax
0x18003f03a  jns     short loc_18003F044
0x18003f03c  mov     ecx, eax; this
0x18003f03e  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f044  mov     [rsp+180h+var_110], r15d
0x18003f049  mov     rcx, [rbp+80h+var_E0]
0x18003f04d  mov     rax, [rcx]
0x18003f050  lea     rdx, [rsp+180h+var_110]
0x18003f055  mov     rax, [rax+60h]
0x18003f059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f05e  test    eax, eax
0x18003f060  jns     short loc_18003F06A
0x18003f062  mov     ecx, eax; this
0x18003f064  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f06a  cmp     [rsp+180h+var_110], r15d
0x18003f06f  ja      short loc_18003F077
0x18003f071  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003f077  lea     rcx, [rbp+80h+var_F8]
0x18003f07b  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003f080  nop
0x18003f081  mov     dword ptr [rsp+180h+var_138], r15d
0x18003f086  mov     rcx, [rbp+80h+var_E0]
0x18003f08a  mov     rax, [rcx]
0x18003f08d  mov     [rsp+180h+var_128], r15
0x18003f092  lea     rdx, [rsp+180h+var_138]
0x18003f097  mov     [rsp+180h+var_120], rdx
0x18003f09c  lea     rdx, [rbp+80h+var_F8]
0x18003f0a0  mov     [rsp+180h+var_118], rdx
0x18003f0a5  lea     r8, [rsp+180h+var_128]
0x18003f0aa  xor     edx, edx
0x18003f0ac  mov     rax, [rax+68h]
0x18003f0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0b5  mov     ebx, eax
0x18003f0b7  lea     rcx, [rsp+180h+var_128]
0x18003f0bc  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003f0c1  mov     ecx, dword ptr [rsp+180h+var_138]; this
0x18003f0c5  test    ecx, ecx
0x18003f0c7  jns     short loc_18003F0CF
0x18003f0c9  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f0cf  test    ebx, ebx
0x18003f0d1  jns     short loc_18003F0DB
0x18003f0d3  mov     ecx, ebx; this
0x18003f0d5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f0db  mov     [rsp+180h+var_108], r15d
0x18003f0e0  mov     [rsp+180h+var_10C], r15d
0x18003f0e5  mov     rcx, [rbp+80h+var_F8]
0x18003f0e9  mov     rax, [rcx]
0x18003f0ec  lea     r8, [rsp+180h+var_10C]
0x18003f0f1  lea     rdx, [rsp+180h+var_108]
0x18003f0f6  mov     rax, [rax+18h]
0x18003f0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0ff  test    eax, eax
0x18003f101  jns     short loc_18003F10B
0x18003f103  mov     ecx, eax; this
0x18003f105  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f10b  xorps   xmm6, xmm6
0x18003f10e  movsd   [rbp+80h+var_100], xmm6
0x18003f113  movsd   [rbp+80h+var_E8], xmm6
0x18003f118  mov     rcx, [rbp+80h+var_F8]
0x18003f11c  mov     rax, [rcx]
0x18003f11f  lea     r8, [rbp+80h+var_E8]
0x18003f123  lea     rdx, [rbp+80h+var_100]
0x18003f127  mov     rax, [rax+28h]
0x18003f12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f130  test    eax, eax
0x18003f132  jns     short loc_18003F13C
0x18003f134  mov     ecx, eax; this
0x18003f136  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f13c  lea     rdx, [rbp+80h+var_F8]
0x18003f140  mov     rcx, rdi
0x18003f143  call    ?ImageHasAlpha@xpsrdr@@YA_NAEAURenderState@1@AEBV?$shared_ptr@UIWICBitmapFrameDecode@@@std@@@Z; xpsrdr::ImageHasAlpha(xpsrdr::RenderState &,std::shared_ptr<IWICBitmapFrameDecode> const &)
0x18003f148  mov     r12b, al
0x18003f14b  mov     byte ptr [rsp+180h+var_160], r15b
0x18003f150  mov     r9, r13
0x18003f153  lea     r8, [rbp+80h+var_F8]
0x18003f157  mov     rdx, rdi
0x18003f15a  lea     rcx, [rsp+180h+var_128]
0x18003f15f  call    ?GetWICBitmap@xpsrdr@@YA?AV?$shared_ptr@UIWICBitmapSource@@@std@@AEAURenderState@1@AEBV?$shared_ptr@UIWICBitmapFrameDecode@@@3@AEBV?$shared_ptr@UIXpsOMColorProfileResource@@@3@_N@Z; xpsrdr::GetWICBitmap(xpsrdr::RenderState &,std::shared_ptr<IWICBitmapFrameDecode> const &,std::shared_ptr<IXpsOMColorProfileResource> const &,bool)
0x18003f164  nop
0x18003f165  xorps   xmm0, xmm0
0x18003f168  movups  [rbp+80h+var_90], xmm0
0x18003f16c  mov     r15, [rsp+180h+var_128]
0x18003f171  mov     rcx, [r15]
0x18003f174  mov     rax, [rcx+20h]
0x18003f178  lea     rdx, [rbp+80h+var_90]
0x18003f17c  mov     rcx, r15
0x18003f17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f184  test    eax, eax
0x18003f186  jns     short loc_18003F190
0x18003f188  mov     ecx, eax; this
0x18003f18a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f190  mov     rax, qword ptr [rbp+80h+var_90]
0x18003f194  sub     rax, [rdi+64h]
0x18003f198  jnz     short loc_18003F1A2
0x18003f19a  mov     rax, qword ptr [rbp+80h+var_90+8]
0x18003f19e  sub     rax, [rdi+6Ch]
0x18003f1a2  test    rax, rax
0x18003f1a5  jz      loc_18003F266
0x18003f1ab  lea     rcx, [rbp+80h+var_A0]
0x18003f1af  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003f1b4  nop
0x18003f1b5  mov     dword ptr [rsp+180h+var_138], 0
0x18003f1bd  mov     rcx, [rdi]
0x18003f1c0  mov     rax, [rcx]
0x18003f1c3  mov     [rbp+80h+var_B8], 0
0x18003f1cb  lea     rdx, [rsp+180h+var_138]
0x18003f1d0  mov     [rbp+80h+var_B0], rdx
0x18003f1d4  lea     rdx, [rbp+80h+var_A0]
0x18003f1d8  mov     [rbp+80h+var_A8], rdx
0x18003f1dc  lea     rdx, [rbp+80h+var_B8]
0x18003f1e0  mov     rax, [rax+50h]
0x18003f1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1e9  mov     r14d, eax
0x18003f1ec  lea     rcx, [rbp+80h+var_B8]
0x18003f1f0  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003f1f5  mov     ecx, dword ptr [rsp+180h+var_138]; this
0x18003f1f9  test    ecx, ecx
0x18003f1fb  jns     short loc_18003F203
0x18003f1fd  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f203  test    r14d, r14d
0x18003f206  jns     short loc_18003F211
0x18003f208  mov     ecx, r14d; this
0x18003f20b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003f211  mov     rcx, qword ptr [rbp+80h+var_A0]
0x18003f215  mov     rax, [rcx]
0x18003f218  mov     [rsp+180h+var_150], 0
0x18003f220  movsd   [rsp+180h+var_158], xmm6
0x18003f226  mov     [rsp+180h+var_160], 0
0x18003f22f  xor     r9d, r9d
0x18003f232  lea     r8, [rdi+64h]
0x18003f236  mov     rdx, r15
0x18003f239  mov     rax, [rax+40h]
0x18003f23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f242  test    eax, eax
0x18003f244  jns     short loc_18003F24E
0x18003f246  mov     ecx, eax; this
0x18003f248  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
  ... truncated ...
```
