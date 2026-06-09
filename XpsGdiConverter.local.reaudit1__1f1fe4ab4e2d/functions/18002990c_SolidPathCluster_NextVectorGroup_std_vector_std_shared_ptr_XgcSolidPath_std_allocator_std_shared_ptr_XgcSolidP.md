# SolidPathCluster::NextVectorGroup(std::vector<std::shared_ptr<XgcSolidPath>,std::allocator<std::shared_ptr<XgcSolidPath>>> *,std::vector<std::shared_ptr<XgcSolidPath>,std::allocator<std::shared_ptr<XgcSolidPath>>> *)

- ea: `0x18002990c`
- end: `0x180029ffa`
- name: `?NextVectorGroup@SolidPathCluster@@AEAAXPEAV?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@0@Z`
- size: `1774`
- prototype: `__int64 __fastcall(SolidPathCluster *this)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x18002a000`

## callees

- `0x180008830`
- `0x180008854`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e990`
- `0x180011b0c`
- `0x180011fb8`
- `0x180015aac`
- `0x1800184e8`
- `0x18002849c`
- `0x180028680`
- `0x180029010`
- `0x18002914c`
- `0x18002919c`
- `0x180029538`
- `0x18002976c`
- `0x18002990c`
- `0x18002a4e8`
- `0x18002a518`
- `0x180034cac`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall SolidPathCluster::NextVectorGroup(SolidPathCluster *this, __int64 a2, __int64 a3)
{
  __int64 v4; // r12
  _QWORD *v5; // rbx
  __int64 v6; // rcx
  _QWORD *v7; // rdi
  char *v8; // r8
  __m128i si128; // xmm7
  int v10; // esi
  __int64 v11; // rdx
  _BYTE *v12; // r14
  int v13; // r15d
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  int v17; // eax
  const struct D2D_RECT_F *v18; // rdx
  const char *v19; // r8
  int v20; // r9d
  int v21; // r15d
  int v22; // edx
  const char *v23; // r8
  int v24; // r9d
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  int v28; // eax
  const struct D2D_RECT_F *v29; // rdx
  const char *v30; // r8
  int v31; // r9d
  __int64 v32; // rdx
  int v33; // eax
  int v34; // edx
  const char *v35; // r8
  int v36; // r9d
  char v37; // r15
  __int64 v38; // r15
  int v39; // eax
  int v40; // edx
  const char *v41; // r8
  int v42; // r9d
  int v43; // xmm0_4
  struct IXpsOMObjectFactory *XpsFactory; // r10
  HRESULT (__stdcall *CreateSolidColorBrush)(IXpsOMObjectFactory *, const XPS_COLOR *, IXpsOMColorProfileResource *, IXpsOMSolidColorBrush **); // rax
  int v46; // r15d
  int v47; // edx
  const char *v48; // r8
  int v49; // r9d
  int v50; // eax
  int v51; // edx
  const char *v52; // r8
  int v53; // r9d
  int v54; // r14d
  int v55; // edx
  const char *v56; // r8
  int v57; // r9d
  __int64 v58; // r9
  char v59; // r8
  int v60; // r10d
  __int64 v61; // rax
  xpsrdr *v62; // [rsp+40h] [rbp-C0h] BYREF
  xpsrdr *v63; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v64[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v65[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v66[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v67[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v68; // [rsp+90h] [rbp-70h]
  _BYTE v69[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v70[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v71[16]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v72[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v73[16]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v74[16]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v75[16]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v76[2]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v77[16]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v78[16]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v79[16]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v80[16]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v81[16]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v82[8]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v83[12]; // [rsp+170h] [rbp+70h] BYREF
  __m128i v84; // [rsp+180h] [rbp+80h] BYREF
  _QWORD *v85; // [rsp+190h] [rbp+90h]
  __int128 v86; // [rsp+198h] [rbp+98h] BYREF
  __int128 v87; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v88[48]; // [rsp+1B8h] [rbp+B8h] BYREF

  if ( a2 )
  {
    v68 = a3;
    if ( a3 )
    {
      v4 = (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 4;
      v5 = *(_QWORD **)std::vector<tagRGBQUAD>::begin(a2, v82, (char *)this + 8);
      v7 = *(_QWORD **)std::vector<CCoordinate>::end(v6, &v86);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( 1 )
      {
        if ( v5 == v7 )
          return;
        v10 = *(_DWORD *)(*v5 + 52LL) + 1;
        while ( v10 < (int)v4 )
        {
          std::vector<std::shared_ptr<XgcSolidPath>>::at(v8, v10);
          std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v67);
          std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v67, v11);
          std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v65);
          std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v66);
          LODWORD(v62) = 0;
          v84.m128i_i64[0] = 0;
          v84.m128i_i64[1] = (__int64)&v62;
          v85 = v66;
          std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v69);
          v12 = (_BYTE *)v67[0];
          std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v69, v67[0] + 16LL);
          std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v70);
          std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v70, *v5 + 16LL);
          v13 = SolidPathCluster::Intersection(this, v70, v69, &v84);
          detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v84);
          if ( (int)v62 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v62, v14, v15, v16);
          if ( v13 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
          v87 = 0;
          v84 = si128;
          v85 = 0;
          v17 = (*(__int64 (__fastcall **)(_QWORD, __m128i *, __int128 *))(*(_QWORD *)v66[0] + 32LL))(
                  v66[0],
                  &v84,
                  &v87);
          if ( v17 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v17, (int)v18, v19, v20);
          if ( xpsrdr::RectEmpty((xpsrdr *)&v87, v18) )
          {
            ++v10;
            goto LABEL_12;
          }
          std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v64);
          if ( (unsigned __int8)std::operator!=<ID3D11Device>(*v5 + 32LL)
            && (unsigned __int8)std::operator!=<ID3D11Device>(v12 + 32) )
          {
            LODWORD(v62) = 0;
            v84.m128i_i64[0] = 0;
            v84.m128i_i64[1] = (__int64)&v62;
            v85 = v64;
            std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v71);
            std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v71, v12 + 32);
            std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v72);
            std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v72, *v5 + 32LL);
            v21 = SolidPathCluster::Intersection(this, v72, v71, &v84);
            detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v84);
            if ( (int)v62 < 0 )
              xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v62, v22, v23, v24);
            if ( v21 < 0 )
              xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v21, v22, v23, v24);
            goto LABEL_22;
          }
          if ( (unsigned __int8)std::operator!=<ID3D11Device>(v12 + 32) )
          {
            v27 = v26;
          }
          else if ( !(unsigned __int8)std::operator!=<ID3D11Device>(v25) )
          {
            goto LABEL_22;
          }
          std::shared_ptr<ID2D1Brush>::operator=(v64, v27);
LABEL_22:
          if ( !(unsigned __int8)std::operator!=<ID3D11Device>(v64) )
            goto LABEL_54;
          v86 = 0;
          v84 = si128;
          v85 = 0;
          v28 = (*(__int64 (__fastcall **)(_QWORD, __m128i *, __int128 *))(*(_QWORD *)v64[0] + 32LL))(
                  v64[0],
                  &v84,
                  &v86);
          if ( v28 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, (int)v29, v30, v31);
          if ( xpsrdr::RectEmpty((xpsrdr *)&v86, v29) )
          {
            ++v10;
          }
          else
          {
LABEL_54:
            if ( !v12[48] || v10 != *(_DWORD *)(*v5 + 52LL) + 1 )
              goto LABEL_35;
            LODWORD(v62) = 1065353216;
            std::vector<std::shared_ptr<XgcSolidPath>>::at((char *)this + 8, v10 - 1);
            std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v76);
            std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v76, v32);
            v33 = (*(__int64 (__fastcall **)(_QWORD, xpsrdr **))(**(_QWORD **)v12 + 40LL))(*(_QWORD *)v12, &v62);
            if ( v33 < 0 )
              xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v33, v34, v35, v36);
            v37 = 0;
            if ( *(float *)&v62 < 1.0 )
            {
              LODWORD(v86) = 1065353216;
              v38 = v76[0];
              v39 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v76[0] + 40LL))(
                      *(_QWORD *)v76[0],
                      &v86);
              if ( v39 < 0 )
                xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v39, v40, v41, v42);
              v43 = (int)v62;
              std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v73);
              std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v73, v12);
              std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v74);
              std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v74, v38);
              std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v75);
              std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v75, *v5);
              SolidPathCluster::MergeColorByRevertFillColor(this, v88, v75, v74, v73, v43);
              LODWORD(v63) = 0;
              XpsFactory = SolidPathCluster::GetXpsFactory(this);
              CreateSolidColorBrush = XpsFactory->lpVtbl->CreateSolidColorBrush;
              v84.m128i_i64[0] = 0;
              v84.m128i_i64[1] = (__int64)&v63;
              v85 = v65;
              v46 = ((__int64 (__fastcall *)(struct IXpsOMObjectFactory *, _BYTE *, _QWORD, __m128i *))CreateSolidColorBrush)(
                      XpsFactory,
                      v88,
                      0,
                      &v84);
              detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v84);
              if ( (int)v63 < 0 )
                xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v63, v47, v48, v49);
              if ( v46 < 0 )
                xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v46, v47, v48, v49);
              v37 = 1;
              v50 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v65[0] + 48LL))(v65[0]);
              if ( v50 < 0 )
                xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v50, v51, v52, v53);
            }
            std::_Ptr_base<ID2D1RenderTarget>::_Decref(v76);
            if ( !v37 )
            {
LABEL_35:
              LODWORD(v63) = 0;
              v84.m128i_i64[0] = 0;
              v84.m128i_i64[1] = (__int64)&v63;
              v85 = v65;
              std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v77);
              std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v77, v12);
              std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v78);
              std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v78, *v5);
              v54 = SolidPathCluster::MergeBrush(this);
              detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v84);
              if ( (int)v63 < 0 )
                xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v63, v55, v56, v57);
              if ( v54 < 0 )
                xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v54, v55, v56, v57);
            }
            std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v79);
            std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v79, v65);
            LOBYTE(v58) = 1;
            SolidPathCluster::GetColorFromBrush(this, v83, v79, v58);
            *(_QWORD *)&v86 = operator new(0x38u);
            std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(v80);
            std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(v80, v66);
            v61 = XgcSolidPath::XgcSolidPath(v60, (unsigned int)v65, (unsigned int)v80, (unsigned int)v64, 0, v59, v10);
            std::shared_ptr<XgcSolidPath>::shared_ptr<XgcSolidPath>(v81, v61);
            std::vector<std::shared_ptr<XgcSolidPath>>::push_back(v68, v81);
            ++v10;
            std::_Ptr_base<ID2D1RenderTarget>::_Decref(v81);
          }
          std::_Ptr_base<ID2D1RenderTarget>::_Decref(v64);
LABEL_12:
          std::_Ptr_base<ID2D1RenderTarget>::_Decref(v66);
          std::_Ptr_base<ID2D1RenderTarget>::_Decref(v65);
          std::_Ptr_base<ID2D1RenderTarget>::_Decref(v67);
          v8 = (char *)this + 8;
        }
        v5 += 2;
      }
    }
  }
}

```

## disassembly

```asm
0x18002990c  test    rdx, rdx
0x18002990f  jz      locret_180029FF9
0x180029915  mov     rax, rsp
0x180029918  mov     [rax+20h], rbx
0x18002991c  push    rbp
0x18002991d  push    rsi
0x18002991e  push    rdi
0x18002991f  push    r12
0x180029921  push    r13
0x180029923  push    r14
0x180029925  push    r15
0x180029927  lea     rbp, [rax-148h]
0x18002992e  sub     rsp, 210h
0x180029935  movaps  xmmword ptr [rax-48h], xmm6
0x180029939  movaps  xmmword ptr [rax-58h], xmm7
0x18002993d  mov     rax, cs:__security_cookie
0x180029944  xor     rax, rsp
0x180029947  mov     [rbp+140h+var_58], rax
0x18002994e  mov     rax, r8
0x180029951  mov     [rbp+140h+var_1B0], rax
0x180029955  mov     r9, rdx
0x180029958  mov     r13, rcx
0x18002995b  test    rax, rax
0x18002995e  jz      loc_180029FC6
0x180029964  lea     r8, [rcx+8]
0x180029968  mov     r12, [r8+8]
0x18002996c  sub     r12, [r8]
0x18002996f  sar     r12, 4
0x180029973  lea     rdx, [rbp+140h+var_D8]
0x180029977  mov     rcx, r9
0x18002997a  call    ?begin@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UtagRGBQUAD@@@std@@@std@@@2@XZ; std::vector<tagRGBQUAD>::begin(void)
0x18002997f  mov     rbx, [rax]
0x180029982  lea     rdx, [rbp+140h+var_A8]
0x180029989  call    ?end@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCCoordinate@@@std@@@std@@@2@XZ; std::vector<CCoordinate>::end(void)
0x18002998e  mov     rdi, [rax]
0x180029991  movdqa  xmm7, cs:__xmm@3f80000000000000000000003f800000
0x180029999  movss   xmm6, cs:__real@3f800000
0x1800299a1  cmp     rbx, rdi
0x1800299a4  jz      loc_180029FC6
0x1800299aa  mov     rax, [rbx]
0x1800299ad  mov     esi, [rax+34h]
0x1800299b0  inc     esi
0x1800299b2  cmp     esi, r12d
0x1800299b5  jge     loc_180029F62
0x1800299bb  movsxd  rdx, esi
0x1800299be  mov     rcx, r8
0x1800299c1  call    ?at@?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VXgcSolidPath@@@2@_K@Z; std::vector<std::shared_ptr<XgcSolidPath>>::at(unsigned __int64)
0x1800299c6  mov     rdx, rax
0x1800299c9  lea     rcx, [rbp+140h+var_1C0]
0x1800299cd  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x1800299d2  lea     rcx, [rbp+140h+var_1C0]
0x1800299d6  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x1800299db  nop
0x1800299dc  lea     rcx, [rsp+240h+var_1E0]
0x1800299e1  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800299e6  nop
0x1800299e7  lea     rcx, [rsp+240h+var_1D0]
0x1800299ec  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800299f1  nop
0x1800299f2  mov     dword ptr [rsp+240h+var_200], 0
0x1800299fa  mov     qword ptr [rbp+140h+var_C0], 0
0x180029a05  lea     rax, [rsp+240h+var_200]
0x180029a0a  mov     qword ptr [rbp+140h+var_C0+8], rax
0x180029a11  lea     rax, [rsp+240h+var_1D0]
0x180029a16  mov     [rbp+140h+var_B0], rax
0x180029a1d  lea     rcx, [rbp+140h+var_1A8]
0x180029a21  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180029a26  mov     r14, [rbp+140h+var_1C0]
0x180029a2a  lea     rdx, [r14+10h]
0x180029a2e  lea     rcx, [rbp+140h+var_1A8]
0x180029a32  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180029a37  lea     rcx, [rbp+140h+var_198]
0x180029a3b  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180029a40  mov     rdx, [rbx]
0x180029a43  add     rdx, 10h
0x180029a47  lea     rcx, [rbp+140h+var_198]
0x180029a4b  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180029a50  lea     r9, [rbp+140h+var_C0]
0x180029a57  lea     r8, [rbp+140h+var_1A8]
0x180029a5b  lea     rdx, [rbp+140h+var_198]
0x180029a5f  mov     rcx, r13
0x180029a62  call    ?Intersection@SolidPathCluster@@AEAAJV?$shared_ptr@UID2D1Geometry@@@std@@0PEAPEAUID2D1Geometry@@@Z; SolidPathCluster::Intersection(std::shared_ptr<ID2D1Geometry>,std::shared_ptr<ID2D1Geometry>,ID2D1Geometry * *)
0x180029a67  mov     r15d, eax
0x180029a6a  lea     rcx, [rbp+140h+var_C0]
0x180029a71  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180029a76  mov     ecx, dword ptr [rsp+240h+var_200]; this
0x180029a7a  test    ecx, ecx
0x180029a7c  js      loc_180029FC0
0x180029a82  test    r15d, r15d
0x180029a85  js      loc_180029FB7
0x180029a8b  xorps   xmm0, xmm0
0x180029a8e  movups  [rbp+140h+var_98], xmm0
0x180029a95  mov     rcx, [rsp+240h+var_1D0]
0x180029a9a  movups  [rbp+140h+var_C0], xmm7
0x180029aa1  mov     [rbp+140h+var_B0], 0
0x180029aac  mov     rax, [rcx]
0x180029aaf  lea     r8, [rbp+140h+var_98]
0x180029ab6  lea     rdx, [rbp+140h+var_C0]
0x180029abd  mov     rax, [rax+20h]
0x180029ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ac6  test    eax, eax
0x180029ac8  js      loc_180029FAF
0x180029ace  lea     rcx, [rbp+140h+var_98]; this
0x180029ad5  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x180029ada  test    al, al
0x180029adc  jz      short loc_180029B08
0x180029ade  inc     esi
0x180029ae0  lea     rcx, [rsp+240h+var_1D0]
0x180029ae5  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029aea  nop
0x180029aeb  lea     rcx, [rsp+240h+var_1E0]
0x180029af0  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029af5  nop
0x180029af6  lea     rcx, [rbp+140h+var_1C0]
0x180029afa  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029aff  lea     r8, [r13+8]
0x180029b03  jmp     loc_1800299B2
0x180029b08  lea     rcx, [rsp+240h+var_1F0]
0x180029b0d  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180029b12  nop
0x180029b13  mov     rdx, [rbx]
0x180029b16  add     rdx, 20h ; ' '
0x180029b1a  mov     rcx, rdx
0x180029b1d  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180029b22  test    al, al
0x180029b24  jz      loc_180029BD5
0x180029b2a  lea     rcx, [r14+20h]
0x180029b2e  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180029b33  test    al, al
0x180029b35  jz      loc_180029BD5
0x180029b3b  mov     dword ptr [rsp+240h+var_200], 0
0x180029b43  mov     qword ptr [rbp+140h+var_C0], 0
0x180029b4e  lea     rax, [rsp+240h+var_200]
0x180029b53  mov     qword ptr [rbp+140h+var_C0+8], rax
0x180029b5a  lea     rax, [rsp+240h+var_1F0]
0x180029b5f  mov     [rbp+140h+var_B0], rax
0x180029b66  lea     rcx, [rbp+140h+var_188]
0x180029b6a  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180029b6f  lea     rdx, [r14+20h]
0x180029b73  lea     rcx, [rbp+140h+var_188]
0x180029b77  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180029b7c  lea     rcx, [rbp+140h+var_178]
0x180029b80  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180029b85  mov     rdx, [rbx]
0x180029b88  add     rdx, 20h ; ' '
0x180029b8c  lea     rcx, [rbp+140h+var_178]
0x180029b90  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180029b95  lea     r9, [rbp+140h+var_C0]
0x180029b9c  lea     r8, [rbp+140h+var_188]
0x180029ba0  lea     rdx, [rbp+140h+var_178]
0x180029ba4  mov     rcx, r13
0x180029ba7  call    ?Intersection@SolidPathCluster@@AEAAJV?$shared_ptr@UID2D1Geometry@@@std@@0PEAPEAUID2D1Geometry@@@Z; SolidPathCluster::Intersection(std::shared_ptr<ID2D1Geometry>,std::shared_ptr<ID2D1Geometry>,ID2D1Geometry * *)
0x180029bac  mov     r15d, eax
0x180029baf  lea     rcx, [rbp+140h+var_C0]
0x180029bb6  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180029bbb  mov     ecx, dword ptr [rsp+240h+var_200]; this
0x180029bbf  test    ecx, ecx
0x180029bc1  js      loc_180029F6B
0x180029bc7  test    r15d, r15d
0x180029bca  jns     short loc_180029BFD
0x180029bcc  mov     ecx, r15d; this
0x180029bcf  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180029bd5  lea     rcx, [r14+20h]
0x180029bd9  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180029bde  test    al, al
0x180029be0  jz      short loc_180029BE7
0x180029be2  mov     rdx, rcx
0x180029be5  jmp     short loc_180029BF3
0x180029be7  mov     rcx, rdx
0x180029bea  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180029bef  test    al, al
0x180029bf1  jz      short loc_180029BFD
0x180029bf3  lea     rcx, [rsp+240h+var_1F0]
0x180029bf8  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x180029bfd  lea     rcx, [rsp+240h+var_1F0]
0x180029c02  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180029c07  test    al, al
0x180029c09  jz      short loc_180029C65
0x180029c0b  xorps   xmm0, xmm0
0x180029c0e  movups  [rbp+140h+var_A8], xmm0
0x180029c15  mov     rcx, [rsp+240h+var_1F0]
0x180029c1a  movups  [rbp+140h+var_C0], xmm7
0x180029c21  mov     [rbp+140h+var_B0], 0
0x180029c2c  mov     rax, [rcx]
0x180029c2f  lea     r8, [rbp+140h+var_A8]
0x180029c36  lea     rdx, [rbp+140h+var_C0]
0x180029c3d  mov     rax, [rax+20h]
0x180029c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c46  test    eax, eax
0x180029c48  js      loc_180029F71
0x180029c4e  lea     rcx, [rbp+140h+var_A8]; this
0x180029c55  call    ?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z; xpsrdr::RectEmpty(D2D_RECT_F const &)
0x180029c5a  test    al, al
0x180029c5c  jz      short loc_180029C65
0x180029c5e  inc     esi
0x180029c60  jmp     loc_180029F53
0x180029c65  cmp     byte ptr [r14+30h], 0
0x180029c6a  jz      loc_180029E1C
0x180029c70  mov     rax, [rbx]
0x180029c73  mov     ecx, [rax+34h]
0x180029c76  inc     ecx
0x180029c78  cmp     esi, ecx
0x180029c7a  jnz     loc_180029E1C
0x180029c80  mov     dword ptr [rsp+240h+var_200], 3F800000h
0x180029c88  lea     eax, [rsi-1]
0x180029c8b  movsxd  rdx, eax
0x180029c8e  lea     rcx, [r13+8]
0x180029c92  call    ?at@?$vector@V?$shared_ptr@VXgcSolidPath@@@std@@V?$allocator@V?$shared_ptr@VXgcSolidPath@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VXgcSolidPath@@@2@_K@Z; std::vector<std::shared_ptr<XgcSolidPath>>::at(unsigned __int64)
0x180029c97  mov     rdx, rax
0x180029c9a  lea     rcx, [rbp+140h+var_138]
0x180029c9e  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180029ca3  lea     rcx, [rbp+140h+var_138]
0x180029ca7  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180029cac  nop
0x180029cad  mov     rcx, [r14]
0x180029cb0  mov     rax, [rcx]
0x180029cb3  lea     rdx, [rsp+240h+var_200]
0x180029cb8  mov     rax, [rax+28h]
0x180029cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cc1  test    eax, eax
0x180029cc3  js      loc_180029F98
0x180029cc9  xor     r15b, r15b
0x180029ccc  comiss  xmm6, dword ptr [rsp+240h+var_200]
0x180029cd1  jbe     loc_180029E0A
0x180029cd7  mov     dword ptr [rbp+140h+var_A8], 3F800000h
0x180029ce1  mov     r15, [rbp+140h+var_138]
0x180029ce5  mov     rcx, [r15]
0x180029ce8  mov     rax, [rcx]
0x180029ceb  lea     rdx, [rbp+140h+var_A8]
0x180029cf2  mov     rax, [rax+28h]
0x180029cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cfb  test    eax, eax
0x180029cfd  js      loc_180029F90
0x180029d03  movss   xmm0, dword ptr [rsp+240h+var_200]
0x180029d09  lea     rcx, [rbp+140h+var_168]
0x180029d0d  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180029d12  mov     rdx, r14
0x180029d15  lea     rcx, [rbp+140h+var_168]
0x180029d19  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180029d1e  lea     rcx, [rbp+140h+var_158]
0x180029d22  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180029d27  mov     rdx, r15
0x180029d2a  lea     rcx, [rbp+140h+var_158]
0x180029d2e  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180029d33  lea     rcx, [rbp+140h+var_148]
0x180029d37  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180029d3c  mov     rdx, [rbx]
0x180029d3f  lea     rcx, [rbp+140h+var_148]
0x180029d43  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180029d48  movss   [rsp+240h+var_218], xmm0
0x180029d4e  lea     rax, [rbp+140h+var_168]
0x180029d52  mov     [rsp+240h+var_220], rax
0x180029d57  lea     r9, [rbp+140h+var_158]
0x180029d5b  lea     r8, [rbp+140h+var_148]
0x180029d5f  lea     rdx, [rbp+140h+var_88]
0x180029d66  mov     rcx, r13
0x180029d69  call    ?MergeColorByRevertFillColor@SolidPathCluster@@AEAA?AU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@V?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@00M@Z; SolidPathCluster::MergeColorByRevertFillColor(std::shared_ptr<IXpsOMSolidColorBrush>,std::shared_ptr<IXpsOMSolidColorBrush>,std::shared_ptr<IXpsOMSolidColorBrush>,float)
0x180029d6e  mov     dword ptr [rsp+240h+var_1F8], 0
0x180029d76  mov     rcx, r13; this
0x180029d79  call    ?GetXpsFactory@SolidPathCluster@@AEAAPEAUIXpsOMObjectFactory@@XZ; SolidPathCluster::GetXpsFactory(void)
0x180029d7e  mov     r10, rax
0x180029d81  mov     rcx, [rax]
0x180029d84  mov     rax, [rcx+0B8h]
0x180029d8b  mov     qword ptr [rbp+140h+var_C0], 0
0x180029d96  lea     rcx, [rsp+240h+var_1F8]
0x180029d9b  mov     qword ptr [rbp+140h+var_C0+8], rcx
0x180029da2  lea     rcx, [rsp+240h+var_1E0]
0x180029da7  mov     [rbp+140h+var_B0], rcx
0x180029dae  lea     r9, [rbp+140h+var_C0]
0x180029db5  xor     r8d, r8d
0x180029db8  lea     rdx, [rbp+140h+var_88]
0x180029dbf  mov     rcx, r10
0x180029dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dc7  mov     r15d, eax
0x180029dca  lea     rcx, [rbp+140h+var_C0]
0x180029dd1  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180029dd6  mov     ecx, dword ptr [rsp+240h+var_1F8]; this
0x180029dda  test    ecx, ecx
0x180029ddc  js      loc_180029F8A
0x180029de2  test    r15d, r15d
0x180029de5  js      loc_180029F81
0x180029deb  mov     r15b, 1
0x180029dee  mov     rcx, [rsp+240h+var_1E0]
0x180029df3  mov     rax, [rcx]
0x180029df6  movaps  xmm1, xmm6
0x180029df9  mov     rax, [rax+30h]
0x180029dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e02  test    eax, eax
0x180029e04  js      loc_180029F79
0x180029e0a  lea     rcx, [rbp+140h+var_138]
0x180029e0e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180029e13  test    r15b, r15b
0x180029e16  jnz     loc_180029EAC
0x180029e1c  mov     dword ptr [rsp+240h+var_1F8], 0
0x180029e24  mov     qword ptr [rbp+140h+var_C0], 0
0x180029e2f  lea     rax, [rsp+240h+var_1F8]
0x180029e34  mov     qword ptr [rbp+140h+var_C0+8], rax
0x180029e3b  lea     rax, [rsp+240h+var_1E0]
0x180029e40  mov     [rbp+140h+var_B0], rax
0x180029e47  lea     rcx, [rbp+140h+var_128]
  ... truncated ...
```
