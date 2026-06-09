# SolidPathCluster::MergeColorByRevertFillColor(std::shared_ptr<IXpsOMSolidColorBrush>,std::shared_ptr<IXpsOMSolidColorBrush>,std::shared_ptr<IXpsOMSolidColorBrush>,float)

- ea: `0x18002976c`
- end: `0x180029906`
- name: `?MergeColorByRevertFillColor@SolidPathCluster@@AEAA?AU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@V?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@00M@Z`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002990c`

## callees

- `0x18000da08`
- `0x18000e0d8`
- `0x180011b0c`
- `0x18002875c`
- `0x180028a60`
- `0x180029010`
- `0x18002976c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 *__fastcall SolidPathCluster::MergeColorByRevertFillColor(
        _QWORD *a1,
        struct __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 *a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        float a6)
{
  _QWORD *v10; // r8
  SolidPathCluster *v11; // rcx
  SolidPathCluster *v12; // rcx
  float a; // xmm1_4
  SolidPathCluster *v14; // rcx
  SolidPathCluster *v15; // rcx
  struct _D3DCOLORVALUE v17; // [rsp+28h] [rbp-49h] BYREF
  struct _D3DCOLORVALUE v18; // [rsp+38h] [rbp-39h] BYREF
  struct _D3DCOLORVALUE v19; // [rsp+48h] [rbp-29h] BYREF
  struct _D3DCOLORVALUE v20; // [rsp+58h] [rbp-19h] BYREF
  struct _D3DCOLORVALUE v21; // [rsp+68h] [rbp-9h] BYREF
  struct _D3DCOLORVALUE v22; // [rsp+78h] [rbp+7h] BYREF

  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(&v17);
  std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(&v17, v10);
  SolidPathCluster::GetColorFromBrush(a1, (__int64)&v21, &v17, 1);
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(&v18);
  std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(&v18, a4);
  SolidPathCluster::GetColorFromBrush(a1, (__int64)&v17, &v18, a6 >= 1.0);
  std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(&v18);
  std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(&v18, a5);
  SolidPathCluster::GetColorFromBrush(a1, (__int64)&v19, &v18, a6 >= 1.0);
  v20 = v17;
  SolidPathCluster::BlendColor(v11, &v18, &v20, &v19);
  a = v17.a;
  if ( a6 < 1.0 )
  {
    v18.a = v18.a * a6;
    a = v17.a * a6;
  }
  v17.a = a / (float)(a - 1.0);
  v20 = v17;
  v19 = v18;
  v21 = *SolidPathCluster::BlendColor(v12, &v18, &v21, &v20);
  v21 = *SolidPathCluster::BlendColor(v14, &v22, &v21, &v19);
  SolidPathCluster::ConvertToXpsColor(v15, a2, &v21);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(a3);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(a4);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(a5);
  return a2;
}

```

## disassembly

```asm
0x18002976c  mov     rax, rsp
0x18002976f  mov     [rax+8], rbx
0x180029773  mov     [rax+20h], r9
0x180029777  mov     [rax+18h], r8
0x18002977b  push    rbp
0x18002977c  push    rsi
0x18002977d  push    rdi
0x18002977e  push    r14
0x180029780  push    r15
0x180029782  lea     rbp, [rax-4Fh]
0x180029786  sub     rsp, 90h
0x18002978d  movaps  xmmword ptr [rax-38h], xmm7
0x180029791  mov     r14, r9
0x180029794  mov     r15, r8
0x180029797  mov     rsi, rdx
0x18002979a  mov     rdi, rcx
0x18002979d  lea     rcx, [rbp+47h+var_90]
0x1800297a1  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x1800297a6  mov     rdx, r8
0x1800297a9  lea     rcx, [rbp+47h+var_90]
0x1800297ad  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x1800297b2  mov     r9b, 1
0x1800297b5  lea     r8, [rbp+47h+var_90]
0x1800297b9  lea     rdx, [rbp+47h+var_50]
0x1800297bd  mov     rcx, rdi
0x1800297c0  call    ?GetColorFromBrush@SolidPathCluster@@AEAA?AU_D3DCOLORVALUE@@V?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@_N@Z; SolidPathCluster::GetColorFromBrush(std::shared_ptr<IXpsOMSolidColorBrush>,bool)
0x1800297c5  movss   xmm7, cs:__real@3f800000
0x1800297cd  comiss  xmm7, [rbp+47h+arg_28]
0x1800297d1  setbe   bl
0x1800297d4  lea     rcx, [rbp+47h+var_80]
0x1800297d8  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x1800297dd  mov     rdx, r14
0x1800297e0  lea     rcx, [rbp+47h+var_80]
0x1800297e4  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x1800297e9  mov     r9b, bl
0x1800297ec  lea     r8, [rbp+47h+var_80]
0x1800297f0  lea     rdx, [rbp+47h+var_90]
0x1800297f4  mov     rcx, rdi
0x1800297f7  call    ?GetColorFromBrush@SolidPathCluster@@AEAA?AU_D3DCOLORVALUE@@V?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@_N@Z; SolidPathCluster::GetColorFromBrush(std::shared_ptr<IXpsOMSolidColorBrush>,bool)
0x1800297fc  lea     rcx, [rbp+47h+var_80]
0x180029800  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180029805  mov     rdx, [rbp+47h+arg_20]
0x180029809  lea     rcx, [rbp+47h+var_80]
0x18002980d  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180029812  mov     r9b, bl
0x180029815  lea     r8, [rbp+47h+var_80]
0x180029819  lea     rdx, [rbp+47h+var_70]
0x18002981d  mov     rcx, rdi
0x180029820  call    ?GetColorFromBrush@SolidPathCluster@@AEAA?AU_D3DCOLORVALUE@@V?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@_N@Z; SolidPathCluster::GetColorFromBrush(std::shared_ptr<IXpsOMSolidColorBrush>,bool)
0x180029825  movups  xmm0, xmmword ptr [rbp+47h+var_70.r]
0x180029829  movdqa  xmmword ptr [rbp+47h+var_70.r], xmm0
0x18002982e  movups  xmm1, [rbp+47h+var_90]
0x180029832  movups  xmmword ptr [rbp+47h+var_60.r], xmm1
0x180029836  lea     r9, [rbp+47h+var_70]; struct _D3DCOLORVALUE
0x18002983a  lea     r8, [rbp+47h+var_60]; struct _D3DCOLORVALUE
0x18002983e  lea     rdx, [rbp+47h+var_80]; retstr
0x180029842  call    ?BlendColor@SolidPathCluster@@AEAA?AU_D3DCOLORVALUE@@U2@0@Z; SolidPathCluster::BlendColor(_D3DCOLORVALUE,_D3DCOLORVALUE)
0x180029847  movss   xmm1, dword ptr [rbp+47h+var_90+0Ch]
0x18002984c  test    bl, bl
0x18002984e  jnz     short loc_180029864
0x180029850  movss   xmm0, [rbp+47h+var_80.a]
0x180029855  mulss   xmm0, [rbp+47h+arg_28]
0x18002985a  movss   [rbp+47h+var_80.a], xmm0
0x18002985f  mulss   xmm1, [rbp+47h+arg_28]
0x180029864  movaps  xmm0, xmm1
0x180029867  subss   xmm0, xmm7
0x18002986b  divss   xmm1, xmm0
0x18002986f  movss   dword ptr [rbp+47h+var_90+0Ch], xmm1
0x180029874  movups  xmm0, [rbp+47h+var_90]
0x180029878  movups  xmmword ptr [rbp+47h+var_60.r], xmm0
0x18002987c  movups  xmm1, xmmword ptr [rbp+47h+var_50.r]
0x180029880  movdqa  xmmword ptr [rbp+47h+var_50.r], xmm1
0x180029885  movups  xmm0, xmmword ptr [rbp+47h+var_80.r]
0x180029889  movups  xmmword ptr [rbp+47h+var_70.r], xmm0
0x18002988d  lea     r9, [rbp+47h+var_60]; struct _D3DCOLORVALUE
0x180029891  lea     r8, [rbp+47h+var_50]; struct _D3DCOLORVALUE
0x180029895  lea     rdx, [rbp+47h+var_80]; retstr
0x180029899  call    ?BlendColor@SolidPathCluster@@AEAA?AU_D3DCOLORVALUE@@U2@0@Z; SolidPathCluster::BlendColor(_D3DCOLORVALUE,_D3DCOLORVALUE)
0x18002989e  movups  xmm0, xmmword ptr [rax]
0x1800298a1  movdqu  xmmword ptr [rbp+47h+var_50.r], xmm0
0x1800298a6  lea     r9, [rbp+47h+var_70]; struct _D3DCOLORVALUE
0x1800298aa  lea     r8, [rbp+47h+var_50]; struct _D3DCOLORVALUE
0x1800298ae  lea     rdx, [rbp+47h+var_40]; retstr
0x1800298b2  call    ?BlendColor@SolidPathCluster@@AEAA?AU_D3DCOLORVALUE@@U2@0@Z; SolidPathCluster::BlendColor(_D3DCOLORVALUE,_D3DCOLORVALUE)
0x1800298b7  movups  xmm0, xmmword ptr [rax]
0x1800298ba  movdqu  xmmword ptr [rbp+47h+var_50.r], xmm0
0x1800298bf  lea     r8, [rbp+47h+var_50]; struct _D3DCOLORVALUE
0x1800298c3  mov     rdx, rsi; retstr
0x1800298c6  call    ?ConvertToXpsColor@SolidPathCluster@@AEAA?AU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@U_D3DCOLORVALUE@@@Z; SolidPathCluster::ConvertToXpsColor(_D3DCOLORVALUE)
0x1800298cb  nop
0x1800298cc  mov     rcx, r15
0x1800298cf  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800298d4  nop
0x1800298d5  mov     rcx, r14
0x1800298d8  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800298dd  nop
0x1800298de  mov     rcx, [rbp+47h+arg_20]
0x1800298e2  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800298e7  mov     rax, rsi
0x1800298ea  lea     r11, [rsp+0B0h+var_20]
0x1800298f2  mov     rbx, [r11+30h]
0x1800298f6  movaps  xmm7, xmmword ptr [r11-10h]
0x1800298fb  mov     rsp, r11
0x1800298fe  pop     r15
0x180029900  pop     r14
0x180029902  pop     rdi
0x180029903  pop     rsi
0x180029904  pop     rbp
0x180029905  retn
```
