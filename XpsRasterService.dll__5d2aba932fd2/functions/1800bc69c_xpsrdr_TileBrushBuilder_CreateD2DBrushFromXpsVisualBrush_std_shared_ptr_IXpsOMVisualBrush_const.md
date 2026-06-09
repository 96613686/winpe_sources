# xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsVisualBrush(std::shared_ptr<IXpsOMVisualBrush> const &)

- ea: `0x1800bc69c`
- end: `0x1800bcbd3`
- name: `?CreateD2DBrushFromXpsVisualBrush@TileBrushBuilder@xpsrdr@@QEAAXAEBV?$shared_ptr@UIXpsOMVisualBrush@@@std@@@Z`
- size: `1335`
- prototype: `__int64 __fastcall(xpsrdr::TileBrushBuilder *this)`
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x1800b3ecc`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a7d4c`
- `0x1800a81a0`
- `0x1800a82e8`
- `0x1800a86b4`
- `0x1800a916c`
- `0x1800a9238`
- `0x1800a9398`
- `0x1800ad620`
- `0x1800ad638`
- `0x1800ad68c`
- `0x1800adcc0`
- `0x1800add10`
- `0x1800af8f4`
- `0x1800b20e8`
- `0x1800b5360`
- `0x1800bb5cc`
- `0x1800bb628`
- `0x1800bb79c`
- `0x1800bb854`
- `0x1800bc69c`
- `0x1800bcbdc`
- `0x1800bcd7c`
- `0x1800bcebc`
- `0x1800bcf68`
- `0x1800bd060`
- `0x1800bd1d0`
- `0x1800bd288`
- `0x1800c3010`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall xpsrdr::TileBrushBuilder::CreateD2DBrushFromXpsVisualBrush(
        xpsrdr::TileBrushBuilder *this,
        __int64 **a2)
{
  int v4; // eax
  int v5; // edx
  const char *v6; // r8
  int v7; // r9d
  __int64 EmptyBrushClipPair; // rax
  _QWORD *v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // edi
  int v14; // edx
  const char *v15; // r8
  int v16; // r9d
  __int64 v17; // r8
  int v18; // esi
  _QWORD *v19; // rdi
  __int64 v20; // r15
  __int64 v21; // r14
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  int v27; // edx
  const char *v28; // r8
  int v29; // r9d
  __int64 v30; // rax
  enum D2D1_EXTEND_MODE v31; // edi
  enum D2D1_EXTEND_MODE v32; // r14d
  __int64 v33; // rax
  int v34; // esi
  int v35; // edx
  const char *v36; // r8
  int v37; // r9d
  bool v38; // al
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rax
  enum D2D1_EXTEND_MODE v42[2]; // [rsp+40h] [rbp-C0h] BYREF
  enum D2D1_EXTEND_MODE v43[4]; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v44[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct D2D_RECT_F v45; // [rsp+68h] [rbp-98h] BYREF
  struct D2D_RECT_F v46; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v47[2]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v48[2]; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v49[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v50[28]; // [rsp+B8h] [rbp-48h] BYREF
  struct D2D_RECT_F v51; // [rsp+D8h] [rbp-28h] BYREF
  struct D2D1_BRUSH_PROPERTIES v52; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v53[2]; // [rsp+108h] [rbp+8h] BYREF

  if ( xpsrdr::TileBrushBuilder::ValidBoxAndPortSizes(this) )
  {
    *(_OWORD *)v44 = 0;
    *(_OWORD *)v47 = 0;
    xpsrdr::TileBrushBuilder::CreateRenderTarget(this, v44, v47);
    (*(void (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base *))(*(_QWORD *)v44[0] + 592LL))(v44[0], v47[0]);
    (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v44[0] + 256LL))(
      v44[0],
      *(unsigned int *)(*((_QWORD *)this + 4) + 88LL));
    (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v44[0] + 272LL))(
      v44[0],
      *(unsigned int *)(*((_QWORD *)this + 4) + 92LL));
    v9 = std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(&v46, v44);
    xpsrdr::TileBrushBuilder::BeginDraw(v10, v9);
    *(_OWORD *)v49 = 0;
    v42[0] = D2D1_EXTEND_MODE_CLAMP;
    v11 = *a2;
    v12 = **a2;
    *(_QWORD *)v50 = 0;
    *(_QWORD *)&v50[8] = v42;
    *(_QWORD *)&v50[16] = v49;
    v13 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(v12 + 144))(v11, v50);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v50);
    if ( v42[0] < D2D1_EXTEND_MODE_CLAMP )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v42[0], v14, v15, v16);
    if ( v13 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v13, v14, v15, v16);
    std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(&v46, v44);
    v18 = 1;
    ++*(_DWORD *)(v17 + 528);
    v19 = (_QWORD *)(v17 + 552);
    if ( *(_QWORD *)(v17 + 568) <= (unsigned __int64)(*(_QWORD *)(v17 + 584) + 1LL) )
      std::deque<std::shared_ptr<ID2D1RenderTarget>>::_Growmap(v17 + 552);
    v19[3] &= v19[2] - 1LL;
    v20 = v19[4] + v19[3];
    v21 = std::deque<std::shared_ptr<ID2D1RenderTarget>>::_Getblock(v19, v20);
    if ( !*(_QWORD *)(v19[1] + 8 * v21) )
      *(_QWORD *)(v19[1] + 8 * v21) = std::_Allocate<16,std::_Default_allocate_traits>(0x10u);
    v22 = std::_Deque_val<std::_Deque_simple_types<D2D_MATRIX_3X2_F>>::_Address_subscript(v19, v20);
    std::_Default_allocator_traits<std::allocator<std::shared_ptr<ID2D1RenderTarget>>>::construct<std::shared_ptr<ID2D1RenderTarget>,std::shared_ptr<ID2D1RenderTarget> const &>(
      v23,
      v22,
      &v46);
    ++v19[4];
    if ( *(_QWORD *)&v46.right )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v46.right);
    *(__m128i *)v50 = _mm_load_si128((const __m128i *)&_xmm);
    *(_QWORD *)&v50[16] = 0;
    std::stack<D2D_MATRIX_3X2_F>::push(*((_QWORD *)this + 4) + 488LL, v50);
    v51 = 0;
    v46 = 0;
    xpsrdr::TileBrushBuilder::GetViewboxAndViewport(this, &v51, &v46);
    v45 = 0;
    std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(v43, v44);
    xpsrdr::RasterizeVisual(*((_QWORD *)this + 4), (unsigned int)v43, 0, (__int64)&v45, 0);
    if ( *(_QWORD *)&v43[2] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v43[2]);
    std::deque<D2D_MATRIX_3X2_F>::pop_back(*((_QWORD *)this + 4) + 488LL);
    std::deque<std::shared_ptr<ID2D1RenderTarget>>::pop_back(*((_QWORD *)this + 4) + 552LL);
    v24 = std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(&v45, v44);
    xpsrdr::TileBrushBuilder::EndDraw(v25, v24);
    (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v44[0] + 592LL))(v44[0], 0);
    v26 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v47[0] + 40LL))(v47[0]);
    if ( v26 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v27, v28, v29);
    *(_QWORD *)&v45.left = 0;
    v45.right = v51.right - v51.left;
    v45.bottom = v51.bottom - v51.top;
    memset(&v52, 0, sizeof(v52));
    xpsrdr::TileBrushBuilder::PopulateBrushProperties(this, &v45, &v46, &v52);
    v42[0] = D2D1_EXTEND_MODE_CLAMP;
    v43[0] = D2D1_EXTEND_MODE_CLAMP;
    xpsrdr::TileBrushBuilder::GetExtendMode(this, v42, v43);
    v30 = *((_QWORD *)this + 4);
    if ( *(_DWORD *)(v30 + 96) || *(_DWORD *)(v30 + 88) == 1 )
      v18 = 0;
    v31 = v42[0];
    *(enum D2D1_EXTEND_MODE *)&v50[16] = v42[0];
    v32 = v43[0];
    *(enum D2D1_EXTEND_MODE *)&v50[20] = v43[0];
    *(_DWORD *)&v50[24] = v18;
    *(struct D2D_RECT_F *)v50 = v51;
    v53[0] = v51;
    *(_OWORD *)((char *)v53 + 12) = *(_OWORD *)&v50[12];
    *(_OWORD *)v48 = 0;
    v43[0] = D2D1_EXTEND_MODE_CLAMP;
    v33 = *(_QWORD *)v44[0];
    *(_QWORD *)v50 = 0;
    *(_QWORD *)&v50[8] = v43;
    *(_QWORD *)&v50[16] = v48;
    v34 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base *, _OWORD *, struct D2D1_BRUSH_PROPERTIES *, _BYTE *))(v33 + 520))(
            v44[0],
            v47[0],
            v53,
            &v52,
            v50);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v50);
    if ( v43[0] < D2D1_EXTEND_MODE_CLAMP )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v43[0], v35, v36, v37);
    if ( v34 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v34, v35, v36, v37);
    std::shared_ptr<ID2D1Brush>::operator=<ID2D1ImageBrush,0>(this, v48);
    v38 = xpsrdr::TileBrushBuilder::WillBrushTile(this, &v46);
    *(_OWORD *)v43 = 0;
    if ( v38 && (v31 == D2D1_EXTEND_MODE_CLAMP || v32 == D2D1_EXTEND_MODE_CLAMP) )
    {
      LOBYTE(v40) = v32 == D2D1_EXTEND_MODE_CLAMP;
      LOBYTE(v39) = v31 == D2D1_EXTEND_MODE_CLAMP;
      v41 = xpsrdr::TileBrushBuilder::CalculateClipRect(
              (int)this,
              (int)v50,
              v39,
              v40,
              (xpsrdr *)&v45,
              &v46,
              (__int64)&v45);
      std::shared_ptr<ID2D1Bitmap>::operator=(v43, v41);
      if ( *(_QWORD *)&v50[8] )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v50[8]);
    }
    std::shared_ptr<ID2D1Brush>::operator=((char *)this + 16, v43);
    if ( *(_QWORD *)&v43[2] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&v43[2]);
    if ( v48[1] )
      std::_Ref_count_base::_Decref(v48[1]);
    if ( v49[1] )
      std::_Ref_count_base::_Decref(v49[1]);
    if ( v47[1] )
      std::_Ref_count_base::_Decref(v47[1]);
    if ( v44[1] )
      std::_Ref_count_base::_Decref(v44[1]);
  }
  else
  {
    v42[0] = 1065353216;
    v4 = (*(__int64 (__fastcall **)(_QWORD, enum D2D1_EXTEND_MODE *))(***((_QWORD ***)this + 5) + 40LL))(
           **((_QWORD **)this + 5),
           v42);
    if ( v4 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v4, v5, v6, v7);
    EmptyBrushClipPair = xpsrdr::CreateEmptyBrushClipPair(v50, *((_QWORD *)this + 4), v42);
    std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(
      this,
      EmptyBrushClipPair);
    std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>((__int64)v50);
  }
}

```

## disassembly

```asm
0x1800bc69c  mov     [rsp-8+arg_10], rbx
0x1800bc6a1  push    rbp
0x1800bc6a2  push    rsi
0x1800bc6a3  push    rdi
0x1800bc6a4  push    r14
0x1800bc6a6  push    r15
0x1800bc6a8  lea     rbp, [rsp-30h]
0x1800bc6ad  sub     rsp, 130h
0x1800bc6b4  mov     rax, cs:__security_cookie
0x1800bc6bb  xor     rax, rsp
0x1800bc6be  mov     [rbp+50h+var_28], rax
0x1800bc6c2  mov     rdi, rdx
0x1800bc6c5  mov     rbx, rcx
0x1800bc6c8  call    ?ValidBoxAndPortSizes@TileBrushBuilder@xpsrdr@@AEAA_NXZ; xpsrdr::TileBrushBuilder::ValidBoxAndPortSizes(void)
0x1800bc6cd  test    al, al
0x1800bc6cf  jnz     short loc_1800BC728
0x1800bc6d1  mov     [rsp+150h+var_110], 3F800000h
0x1800bc6d9  mov     rax, [rbx+28h]
0x1800bc6dd  mov     rcx, [rax]
0x1800bc6e0  mov     rax, [rcx]
0x1800bc6e3  lea     rdx, [rsp+150h+var_110]
0x1800bc6e8  mov     rax, [rax+28h]
0x1800bc6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc6f1  test    eax, eax
0x1800bc6f3  jns     short loc_1800BC6FD
0x1800bc6f5  mov     ecx, eax; this
0x1800bc6f7  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bc6fd  lea     r8, [rsp+150h+var_110]
0x1800bc702  mov     rdx, [rbx+20h]
0x1800bc706  lea     rcx, [rbp+50h+var_98]
0x1800bc70a  call    ?CreateEmptyBrushClipPair@xpsrdr@@YA?AU?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@AEAURenderState@1@PEAM@Z; xpsrdr::CreateEmptyBrushClipPair(xpsrdr::RenderState &,float *)
0x1800bc70f  mov     rdx, rax
0x1800bc712  mov     rcx, rbx
0x1800bc715  call    ??$?4U?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@$0A@@?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::operator=<std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>,0>(std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>> &&)
0x1800bc71a  lea     rcx, [rbp+50h+var_98]
0x1800bc71e  call    ??1?$pair@V?$shared_ptr@UID2D1Brush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@@std@@QEAA@XZ; std::pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>::~pair<std::shared_ptr<ID2D1Brush>,std::shared_ptr<ID2D1Geometry>>(void)
0x1800bc723  jmp     loc_1800BCBB0
0x1800bc728  xorps   xmm0, xmm0
0x1800bc72b  movdqu  xmmword ptr [rsp+150h+var_F8], xmm0
0x1800bc731  movdqu  xmmword ptr [rbp+50h+var_C8], xmm0
0x1800bc736  lea     r8, [rbp+50h+var_C8]
0x1800bc73a  lea     rdx, [rsp+150h+var_F8]
0x1800bc73f  mov     rcx, rbx
0x1800bc742  call    ?CreateRenderTarget@TileBrushBuilder@xpsrdr@@AEAAXAEAV?$shared_ptr@UID2D1DeviceContext@@@std@@AEAV?$shared_ptr@UID2D1CommandList@@@4@@Z; xpsrdr::TileBrushBuilder::CreateRenderTarget(std::shared_ptr<ID2D1DeviceContext> &,std::shared_ptr<ID2D1CommandList> &)
0x1800bc747  mov     rcx, [rsp+150h+var_F8]
0x1800bc74c  mov     rax, [rcx]
0x1800bc74f  mov     rdx, [rbp+50h+var_C8]
0x1800bc753  mov     rax, [rax+250h]
0x1800bc75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc75f  mov     rcx, [rsp+150h+var_F8]
0x1800bc764  mov     rax, [rcx]
0x1800bc767  mov     rdx, [rbx+20h]
0x1800bc76b  mov     edx, [rdx+58h]
0x1800bc76e  mov     rax, [rax+100h]
0x1800bc775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc77a  mov     rcx, [rsp+150h+var_F8]
0x1800bc77f  mov     rax, [rcx]
0x1800bc782  mov     rdx, [rbx+20h]
0x1800bc786  mov     edx, [rdx+5Ch]
0x1800bc789  mov     rax, [rax+110h]
0x1800bc790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc795  lea     rdx, [rsp+150h+var_F8]
0x1800bc79a  lea     rcx, [rsp+150h+var_D8]
0x1800bc79f  call    ??0?$shared_ptr@UID2D1Bitmap@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(std::shared_ptr<ID2D1Bitmap> const &)
0x1800bc7a4  mov     rdx, rax
0x1800bc7a7  call    ?BeginDraw@TileBrushBuilder@xpsrdr@@AEAAXV?$shared_ptr@UID2D1DeviceContext@@@std@@@Z; xpsrdr::TileBrushBuilder::BeginDraw(std::shared_ptr<ID2D1DeviceContext>)
0x1800bc7ac  xorps   xmm0, xmm0
0x1800bc7af  movdqu  xmmword ptr [rbp+50h+var_A8], xmm0
0x1800bc7b4  mov     [rsp+150h+var_110], 0
0x1800bc7bc  mov     rcx, [rdi]
0x1800bc7bf  mov     rax, [rcx]
0x1800bc7c2  mov     [rbp+50h+var_98], 0
0x1800bc7ca  lea     rdx, [rsp+150h+var_110]
0x1800bc7cf  mov     [rbp+50h+var_98+8], rdx
0x1800bc7d3  lea     rdx, [rbp+50h+var_A8]
0x1800bc7d7  mov     [rbp+50h+var_88], rdx
0x1800bc7db  lea     rdx, [rbp+50h+var_98]
0x1800bc7df  mov     rax, [rax+90h]
0x1800bc7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc7eb  mov     edi, eax
0x1800bc7ed  lea     rcx, [rbp+50h+var_98]
0x1800bc7f1  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bc7f6  mov     ecx, [rsp+150h+var_110]; this
0x1800bc7fa  test    ecx, ecx
0x1800bc7fc  jns     short loc_1800BC804
0x1800bc7fe  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bc804  test    edi, edi
0x1800bc806  jns     short loc_1800BC810
0x1800bc808  mov     ecx, edi; this
0x1800bc80a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bc810  mov     r8, [rbx+20h]
0x1800bc814  lea     rdx, [rsp+150h+var_F8]
0x1800bc819  lea     rcx, [rsp+150h+var_D8]
0x1800bc81e  call    ??0?$shared_ptr@UID2D1Bitmap@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(std::shared_ptr<ID2D1Bitmap> const &)
0x1800bc823  nop
0x1800bc824  mov     esi, 1
0x1800bc829  add     [r8+210h], esi
0x1800bc830  lea     rdi, [r8+228h]
0x1800bc837  mov     rax, [rdi+20h]
0x1800bc83b  add     rax, rsi
0x1800bc83e  cmp     [rdi+10h], rax
0x1800bc842  ja      short loc_1800BC84C
0x1800bc844  mov     rcx, rdi
0x1800bc847  call    ?_Growmap@?$deque@V?$shared_ptr@UID2D1RenderTarget@@@std@@V?$allocator@V?$shared_ptr@UID2D1RenderTarget@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::shared_ptr<ID2D1RenderTarget>>::_Growmap(unsigned __int64)
0x1800bc84c  mov     rax, [rdi+10h]
0x1800bc850  sub     rax, rsi
0x1800bc853  and     [rdi+18h], rax
0x1800bc857  mov     r15, [rdi+18h]
0x1800bc85b  add     r15, [rdi+20h]
0x1800bc85f  mov     rdx, r15
0x1800bc862  mov     rcx, rdi
0x1800bc865  call    ?_Getblock@?$deque@V?$shared_ptr@UID2D1RenderTarget@@@std@@V?$allocator@V?$shared_ptr@UID2D1RenderTarget@@@std@@@2@@std@@AEBA_J_K@Z; std::deque<std::shared_ptr<ID2D1RenderTarget>>::_Getblock(unsigned __int64)
0x1800bc86a  mov     r14, rax
0x1800bc86d  mov     rcx, [rdi+8]
0x1800bc871  cmp     qword ptr [rcx+rax*8], 0
0x1800bc876  jnz     short loc_1800BC88A
0x1800bc878  mov     ecx, 10h
0x1800bc87d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800bc882  mov     rcx, [rdi+8]
0x1800bc886  mov     [rcx+r14*8], rax
0x1800bc88a  mov     rdx, r15
0x1800bc88d  mov     rcx, rdi
0x1800bc890  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@UD2D_MATRIX_3X2_F@@@std@@@std@@QEAAPEAUD2D_MATRIX_3X2_F@@_K@Z; std::_Deque_val<std::_Deque_simple_types<D2D_MATRIX_3X2_F>>::_Address_subscript(unsigned __int64)
0x1800bc895  lea     r8, [rsp+150h+var_D8]
0x1800bc89a  mov     rdx, rax
0x1800bc89d  call    ??$construct@V?$shared_ptr@UID2D1RenderTarget@@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$shared_ptr@UID2D1RenderTarget@@@std@@@std@@@std@@SAXAEAV?$allocator@V?$shared_ptr@UID2D1RenderTarget@@@std@@@1@QEAV?$shared_ptr@UID2D1RenderTarget@@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::shared_ptr<ID2D1RenderTarget>>>::construct<std::shared_ptr<ID2D1RenderTarget>,std::shared_ptr<ID2D1RenderTarget> const &>(std::allocator<std::shared_ptr<ID2D1RenderTarget>> &,std::shared_ptr<ID2D1RenderTarget> * const,std::shared_ptr<ID2D1RenderTarget> const &)
0x1800bc8a2  add     [rdi+20h], rsi
0x1800bc8a6  mov     rcx, qword ptr [rbp+50h+var_D8.right]; this
0x1800bc8aa  test    rcx, rcx
0x1800bc8ad  jz      short loc_1800BC8B4
0x1800bc8af  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bc8b4  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x1800bc8bc  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x1800bc8c0  mov     [rbp+50h+var_88], 0
0x1800bc8c8  mov     rcx, [rbx+20h]
0x1800bc8cc  mov     edi, 1E8h
0x1800bc8d1  add     rcx, rdi
0x1800bc8d4  lea     rdx, [rbp+50h+var_98]
0x1800bc8d8  call    ?push@?$stack@UD2D_MATRIX_3X2_F@@V?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@@std@@QEAAX$$QEAUD2D_MATRIX_3X2_F@@@Z; std::stack<D2D_MATRIX_3X2_F>::push(D2D_MATRIX_3X2_F &&)
0x1800bc8dd  xorps   xmm0, xmm0
0x1800bc8e0  movups  xmmword ptr [rbp+50h+var_78.left], xmm0
0x1800bc8e4  xorps   xmm1, xmm1
0x1800bc8e7  movups  xmmword ptr [rsp+150h+var_D8.left], xmm1
0x1800bc8ec  lea     r8, [rsp+150h+var_D8]; struct D2D_RECT_F *
0x1800bc8f1  lea     rdx, [rbp+50h+var_78]; struct D2D_RECT_F *
0x1800bc8f5  mov     rcx, rbx; this
0x1800bc8f8  call    ?GetViewboxAndViewport@TileBrushBuilder@xpsrdr@@AEAAXAEAUD2D_RECT_F@@0@Z; xpsrdr::TileBrushBuilder::GetViewboxAndViewport(D2D_RECT_F &,D2D_RECT_F &)
0x1800bc8fd  xorps   xmm0, xmm0
0x1800bc900  movdqu  xmmword ptr [rsp+150h+var_E8.left], xmm0
0x1800bc906  lea     rdx, [rsp+150h+var_F8]
0x1800bc90b  lea     rcx, [rsp+150h+var_108]
0x1800bc910  call    ??0?$shared_ptr@UID2D1Bitmap@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(std::shared_ptr<ID2D1Bitmap> const &)
0x1800bc915  nop
0x1800bc916  mov     byte ptr [rsp+150h+var_120], 0
0x1800bc91b  lea     rax, [rsp+150h+var_E8]
0x1800bc920  mov     [rsp+150h+var_128], rax
0x1800bc925  mov     [rsp+150h+var_130], 0
0x1800bc92e  lea     r9, [rbp+50h+var_A8]
0x1800bc932  lea     r8, [rbp+50h+var_78]
0x1800bc936  lea     rdx, [rsp+150h+var_108]
0x1800bc93b  mov     rcx, [rbx+20h]
0x1800bc93f  call    ?RasterizeVisual@xpsrdr@@YAXAEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@AEBUD2D_RECT_F@@AEBV?$shared_ptr@UIXpsOMVisual@@@4@PEBUD2D_MATRIX_3X2_F@@V?$shared_ptr@UID2D1Geometry@@@4@_N@Z; xpsrdr::RasterizeVisual(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D_RECT_F const &,std::shared_ptr<IXpsOMVisual> const &,D2D_MATRIX_3X2_F const *,std::shared_ptr<ID2D1Geometry>,bool)
0x1800bc944  nop
0x1800bc945  mov     rcx, qword ptr [rsp+150h+var_108+8]; this
0x1800bc94a  test    rcx, rcx
0x1800bc94d  jz      short loc_1800BC954
0x1800bc94f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bc954  mov     rcx, [rbx+20h]
0x1800bc958  add     rcx, rdi
0x1800bc95b  call    ?pop_back@?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@QEAAXXZ; std::deque<D2D_MATRIX_3X2_F>::pop_back(void)
0x1800bc960  mov     rcx, [rbx+20h]
0x1800bc964  add     rcx, 228h
0x1800bc96b  call    ?pop_back@?$deque@V?$shared_ptr@UID2D1RenderTarget@@@std@@V?$allocator@V?$shared_ptr@UID2D1RenderTarget@@@std@@@2@@std@@QEAAXXZ; std::deque<std::shared_ptr<ID2D1RenderTarget>>::pop_back(void)
0x1800bc970  lea     rdx, [rsp+150h+var_F8]
0x1800bc975  lea     rcx, [rsp+150h+var_E8]
0x1800bc97a  call    ??0?$shared_ptr@UID2D1Bitmap@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ID2D1Bitmap>::shared_ptr<ID2D1Bitmap>(std::shared_ptr<ID2D1Bitmap> const &)
0x1800bc97f  mov     rdx, rax
0x1800bc982  call    ?EndDraw@TileBrushBuilder@xpsrdr@@AEAAXV?$shared_ptr@UID2D1DeviceContext@@@std@@@Z; xpsrdr::TileBrushBuilder::EndDraw(std::shared_ptr<ID2D1DeviceContext>)
0x1800bc987  mov     rcx, [rsp+150h+var_F8]
0x1800bc98c  mov     rax, [rcx]
0x1800bc98f  xor     edx, edx
0x1800bc991  mov     rax, [rax+250h]
0x1800bc998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc99d  mov     rcx, [rbp+50h+var_C8]
0x1800bc9a1  mov     rax, [rcx]
0x1800bc9a4  mov     rax, [rax+28h]
0x1800bc9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc9ad  test    eax, eax
0x1800bc9af  jns     short loc_1800BC9B9
0x1800bc9b1  mov     ecx, eax; this
0x1800bc9b3  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bc9b9  mov     qword ptr [rsp+150h+var_E8.left], 0
0x1800bc9c2  movss   xmm0, [rbp+50h+var_78.right]
0x1800bc9c7  subss   xmm0, [rbp+50h+var_78.left]
0x1800bc9cc  movss   [rsp+150h+var_E8.right], xmm0
0x1800bc9d2  movss   xmm1, [rbp+50h+var_78.bottom]
0x1800bc9d7  subss   xmm1, [rbp+50h+var_78.top]
0x1800bc9dc  movss   [rsp+150h+var_E8.bottom], xmm1
0x1800bc9e2  xorps   xmm0, xmm0
0x1800bc9e5  movups  xmmword ptr [rbp+50h+var_68.opacity], xmm0
0x1800bc9e9  movups  xmmword ptr [rbp+50h+var_68.transform+8], xmm0
0x1800bc9ed  lea     r9, [rbp+50h+var_68]; struct D2D1_BRUSH_PROPERTIES *
0x1800bc9f1  lea     r8, [rsp+150h+var_D8]; struct D2D_RECT_F *
0x1800bc9f6  lea     rdx, [rsp+150h+var_E8]; struct D2D_RECT_F *
0x1800bc9fb  mov     rcx, rbx; this
0x1800bc9fe  call    ?PopulateBrushProperties@TileBrushBuilder@xpsrdr@@AEAAXAEBUD2D_RECT_F@@0AEAUD2D1_BRUSH_PROPERTIES@@@Z; xpsrdr::TileBrushBuilder::PopulateBrushProperties(D2D_RECT_F const &,D2D_RECT_F const &,D2D1_BRUSH_PROPERTIES &)
0x1800bca03  mov     [rsp+150h+var_110], 0
0x1800bca0b  mov     [rsp+150h+var_108], 0
0x1800bca13  lea     r8, [rsp+150h+var_108]; enum D2D1_EXTEND_MODE *
0x1800bca18  lea     rdx, [rsp+150h+var_110]; enum D2D1_EXTEND_MODE *
0x1800bca1d  mov     rcx, rbx; this
0x1800bca20  call    ?GetExtendMode@TileBrushBuilder@xpsrdr@@AEAAXAEAW4D2D1_EXTEND_MODE@@0@Z; xpsrdr::TileBrushBuilder::GetExtendMode(D2D1_EXTEND_MODE &,D2D1_EXTEND_MODE &)
0x1800bca25  mov     rax, [rbx+20h]
0x1800bca29  cmp     dword ptr [rax+60h], 0
0x1800bca2d  jnz     short loc_1800BCA34
0x1800bca2f  cmp     [rax+58h], esi
0x1800bca32  jnz     short loc_1800BCA36
0x1800bca34  xor     esi, esi
0x1800bca36  movups  xmm0, xmmword ptr [rbp+50h+var_78.left]
0x1800bca3a  mov     edi, [rsp+150h+var_110]
0x1800bca3e  mov     dword ptr [rbp+50h+var_88], edi
0x1800bca41  mov     r14d, [rsp+150h+var_108]
0x1800bca46  mov     dword ptr [rbp+50h+var_88+4], r14d
0x1800bca4a  mov     [rbp+50h+var_80], esi
0x1800bca4d  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x1800bca51  movups  xmmword ptr [rbp+50h+var_48], xmm0
0x1800bca55  movups  xmm0, xmmword ptr [rbp+50h+var_98+0Ch]
0x1800bca59  movups  xmmword ptr [rbp+50h+var_48+0Ch], xmm0
0x1800bca5d  xorps   xmm1, xmm1
0x1800bca60  movdqu  xmmword ptr [rbp+50h+var_B8], xmm1
0x1800bca65  mov     [rsp+150h+var_108], 0
0x1800bca6d  mov     rcx, [rsp+150h+var_F8]
0x1800bca72  mov     rax, [rcx]
0x1800bca75  mov     [rbp+50h+var_98], 0
0x1800bca7d  lea     rdx, [rsp+150h+var_108]
0x1800bca82  mov     [rbp+50h+var_98+8], rdx
0x1800bca86  lea     rdx, [rbp+50h+var_B8]
0x1800bca8a  mov     [rbp+50h+var_88], rdx
0x1800bca8e  lea     rdx, [rbp+50h+var_98]
0x1800bca92  mov     [rsp+150h+var_130], rdx
0x1800bca97  lea     r9, [rbp+50h+var_68]
0x1800bca9b  lea     r8, [rbp+50h+var_48]
0x1800bca9f  mov     rdx, [rbp+50h+var_C8]
0x1800bcaa3  mov     rax, [rax+208h]
0x1800bcaaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcaaf  mov     esi, eax
0x1800bcab1  lea     rcx, [rbp+50h+var_98]
0x1800bcab5  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800bcaba  mov     ecx, [rsp+150h+var_108]; this
0x1800bcabe  test    ecx, ecx
0x1800bcac0  jns     short loc_1800BCAC8
0x1800bcac2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bcac8  test    esi, esi
0x1800bcaca  jns     short loc_1800BCAD4
0x1800bcacc  mov     ecx, esi; this
0x1800bcace  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800bcad4  lea     rdx, [rbp+50h+var_B8]
0x1800bcad8  mov     rcx, rbx
0x1800bcadb  call    ??$?4UID2D1ImageBrush@@$0A@@?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV?$shared_ptr@UID2D1ImageBrush@@@1@@Z; std::shared_ptr<ID2D1Brush>::operator=<ID2D1ImageBrush,0>(std::shared_ptr<ID2D1ImageBrush> const &)
0x1800bcae0  lea     rdx, [rsp+150h+var_D8]; struct D2D_RECT_F *
0x1800bcae5  mov     rcx, rbx; this
0x1800bcae8  call    ?WillBrushTile@TileBrushBuilder@xpsrdr@@AEAA_NAEBUD2D_RECT_F@@@Z; xpsrdr::TileBrushBuilder::WillBrushTile(D2D_RECT_F const &)
0x1800bcaed  xorps   xmm0, xmm0
0x1800bcaf0  movdqu  xmmword ptr [rsp+150h+var_108], xmm0
0x1800bcaf6  test    al, al
0x1800bcaf8  jz      short loc_1800BCB55
0x1800bcafa  test    edi, edi
0x1800bcafc  jz      short loc_1800BCB03
0x1800bcafe  test    r14d, r14d
0x1800bcb01  jnz     short loc_1800BCB55
0x1800bcb03  test    r14d, r14d
0x1800bcb06  setz    r9b; int
0x1800bcb0a  test    edi, edi
0x1800bcb0c  setz    r8b; int
0x1800bcb10  lea     rax, [rsp+150h+var_E8]
0x1800bcb15  mov     [rsp+150h+var_120], rax; __int64
0x1800bcb1a  lea     rax, [rsp+150h+var_D8]
0x1800bcb1f  mov     [rsp+150h+var_128], rax; struct D2D_RECT_F *
0x1800bcb24  lea     rax, [rsp+150h+var_E8]
0x1800bcb29  mov     [rsp+150h+var_130], rax; xpsrdr *
0x1800bcb2e  lea     rdx, [rbp+50h+var_98]; int
0x1800bcb32  mov     rcx, rbx; int
0x1800bcb35  call    ?CalculateClipRect@TileBrushBuilder@xpsrdr@@AEAA?AV?$shared_ptr@UID2D1Geometry@@@std@@_N0AEBUD2D_RECT_F@@11@Z; xpsrdr::TileBrushBuilder::CalculateClipRect(bool,bool,D2D_RECT_F const &,D2D_RECT_F const &,D2D_RECT_F const &)
0x1800bcb3a  mov     rdx, rax
0x1800bcb3d  lea     rcx, [rsp+150h+var_108]
0x1800bcb42  call    ??4?$shared_ptr@UID2D1Bitmap@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ID2D1Bitmap>::operator=(std::shared_ptr<ID2D1Bitmap> &&)
0x1800bcb47  mov     rcx, [rbp+50h+var_98+8]; this
0x1800bcb4b  test    rcx, rcx
0x1800bcb4e  jz      short loc_1800BCB55
0x1800bcb50  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bcb55  lea     rcx, [rbx+10h]
0x1800bcb59  lea     rdx, [rsp+150h+var_108]
0x1800bcb5e  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800bcb63  nop
0x1800bcb64  mov     rcx, qword ptr [rsp+150h+var_108+8]; this
0x1800bcb69  test    rcx, rcx
0x1800bcb6c  jz      short loc_1800BCB74
0x1800bcb6e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bcb73  nop
0x1800bcb74  mov     rcx, [rbp+50h+var_B8+8]; this
  ... truncated ...
```
