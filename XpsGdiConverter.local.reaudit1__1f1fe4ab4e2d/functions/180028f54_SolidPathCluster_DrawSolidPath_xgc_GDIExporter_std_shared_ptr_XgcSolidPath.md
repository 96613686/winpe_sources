# SolidPathCluster::DrawSolidPath(xgc::GDIExporter *,std::shared_ptr<XgcSolidPath>)

- ea: `0x180028f54`
- end: `0x180029008`
- name: `?DrawSolidPath@SolidPathCluster@@QEAAXPEAVGDIExporter@xgc@@V?$shared_ptr@VXgcSolidPath@@@std@@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002a000`

## callees

- `0x18000d61c`
- `0x18000e990`
- `0x180011b0c`
- `0x180026c28`
- `0x180026c5c`
- `0x180026f94`
- `0x180027dfc`
- `0x180027ed4`
- `0x180028f54`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
double __fastcall SolidPathCluster::DrawSolidPath(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rcx
  struct D2D_MATRIX_3X2_F v7; // [rsp+20h] [rbp-28h] BYREF

  *(__m128i *)&v7.m11 = _mm_load_si128((const __m128i *)&_xmm);
  *(_QWORD *)&v7.m[2][0] = 0;
  xgc::CDeviceContext::PushTransform(*(struct D2D_MATRIX_3X2_F **)(a2 + 8), &v7);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(*a3 + 32LL) )
    xgc::GDIExporter::PushClip(a2, v5);
  std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(&v7, *a3);
  xgc::GDIExporter::FillPath(a2, *a3 + 16LL, &v7);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v7);
  if ( (unsigned __int8)std::operator!=<ID3D11Device>(*a3 + 32LL) )
    xgc::CDeviceContext::Restore(*(xgc::CDeviceContext **)(a2 + 8));
  xgc::CDeviceContext::PopTransform(*(xgc::CDeviceContext **)(a2 + 8));
  return std::_Ptr_base<ID2D1RenderTarget>::_Decref(a3);
}

```

## disassembly

```asm
0x180028f54  mov     rax, rsp
0x180028f57  mov     [rax+8], rbx
0x180028f5b  mov     [rax+18h], r8
0x180028f5f  push    rdi
0x180028f60  sub     rsp, 40h
0x180028f64  mov     rdi, r8
0x180028f67  mov     rbx, rdx
0x180028f6a  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x180028f72  movups  xmmword ptr [rax-28h], xmm0
0x180028f76  mov     qword ptr [rax-18h], 0
0x180028f7e  lea     rdx, [rax-28h]; struct D2D_MATRIX_3X2_F *
0x180028f82  mov     rcx, [rbx+8]; this
0x180028f86  call    ?PushTransform@CDeviceContext@xgc@@QEAAXAEBUD2D_MATRIX_3X2_F@@@Z; xgc::CDeviceContext::PushTransform(D2D_MATRIX_3X2_F const &)
0x180028f8b  mov     rcx, [rdi]
0x180028f8e  add     rcx, 20h ; ' '
0x180028f92  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180028f97  test    al, al
0x180028f99  jz      short loc_180028FA6
0x180028f9b  mov     rdx, rcx
0x180028f9e  mov     rcx, rbx
0x180028fa1  call    ?PushClip@GDIExporter@xgc@@QEAAXAEBV?$shared_ptr@UID2D1Geometry@@@std@@@Z; xgc::GDIExporter::PushClip(std::shared_ptr<ID2D1Geometry> const &)
0x180028fa6  mov     rdx, [rdi]
0x180028fa9  lea     rcx, [rsp+48h+var_28]
0x180028fae  call    ??$?0UID2D1TransformedGeometry@@$0A@@?$shared_ptr@UID2D1Geometry@@@std@@QEAA@AEBV?$shared_ptr@UID2D1TransformedGeometry@@@1@@Z; std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(std::shared_ptr<ID2D1TransformedGeometry> const &)
0x180028fb3  nop
0x180028fb4  mov     rdx, [rdi]
0x180028fb7  add     rdx, 10h
0x180028fbb  lea     r8, [rsp+48h+var_28]
0x180028fc0  mov     rcx, rbx
0x180028fc3  call    ?FillPath@GDIExporter@xgc@@AEAAXAEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBV?$shared_ptr@UIXpsOMBrush@@@4@@Z; xgc::GDIExporter::FillPath(std::shared_ptr<ID2D1Geometry> const &,std::shared_ptr<IXpsOMBrush> const &)
0x180028fc8  nop
0x180028fc9  lea     rcx, [rsp+48h+var_28]
0x180028fce  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028fd3  mov     rcx, [rdi]
0x180028fd6  add     rcx, 20h ; ' '
0x180028fda  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180028fdf  test    al, al
0x180028fe1  jz      short loc_180028FEC
0x180028fe3  mov     rcx, [rbx+8]; this
0x180028fe7  call    ?Restore@CDeviceContext@xgc@@QEAAXXZ; xgc::CDeviceContext::Restore(void)
0x180028fec  mov     rcx, [rbx+8]; this
0x180028ff0  call    ?PopTransform@CDeviceContext@xgc@@QEAAXXZ; xgc::CDeviceContext::PopTransform(void)
0x180028ff5  nop
0x180028ff6  mov     rcx, rdi
0x180028ff9  mov     rbx, [rsp+48h+arg_0]
0x180028ffe  add     rsp, 40h
0x180029002  pop     rdi
0x180029003  jmp     ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
```
