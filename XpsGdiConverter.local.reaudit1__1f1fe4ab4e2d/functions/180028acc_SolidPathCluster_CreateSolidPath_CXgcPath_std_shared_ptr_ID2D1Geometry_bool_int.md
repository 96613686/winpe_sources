# SolidPathCluster::CreateSolidPath(CXgcPath *,std::shared_ptr<ID2D1Geometry> &,bool,int)

- ea: `0x180028acc`
- end: `0x180028f4d`
- name: `?CreateSolidPath@SolidPathCluster@@AEAA?AV?$shared_ptr@VXgcSolidPath@@@std@@PEAVCXgcPath@@AEAV?$shared_ptr@UID2D1Geometry@@@3@_NH@Z`
- size: `1153`
- prototype: `__int64 __usercall@<rax>(SolidPathCluster *this@<rcx>, char, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18002a16c`

## callees

- `0x180008830`
- `0x180008854`
- `0x18000d61c`
- `0x18000da08`
- `0x18000e0d8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e934`
- `0x18000e990`
- `0x180011b0c`
- `0x18002849c`
- `0x180028680`
- `0x180028a60`
- `0x180028acc`
- `0x180029010`
- `0x18002914c`
- `0x18002a294`
- `0x180037278`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SolidPathCluster::CreateSolidPath(
        SolidPathCluster *this,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        int a6)
{
  __int64 v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  int v15; // r15d
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v22)(_QWORD, GUID *, __int64 *); // rax
  int v23; // r15d
  int v24; // edx
  const char *v25; // r8
  int v26; // r9d
  __int64 v27; // rcx
  int v28; // r15d
  int v29; // edx
  const char *v30; // r8
  int v31; // r9d
  char v32; // r15
  __int64 v33; // r9
  SolidPathCluster *v34; // rcx
  struct IXpsOMObjectFactory *XpsFactory; // r10
  HRESULT (__stdcall *CreateSolidColorBrush)(IXpsOMObjectFactory *, const XPS_COLOR *, IXpsOMColorProfileResource *, IXpsOMSolidColorBrush **); // rax
  int v37; // esi
  int v38; // edx
  const char *v39; // r8
  int v40; // r9d
  int v41; // eax
  int v42; // eax
  char v43; // r8
  int v44; // r10d
  __int64 v45; // rax
  __int64 v46; // rax
  xpsrdr *v48; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B8h] BYREF
  xpsrdr **v50; // [rsp+58h] [rbp-B0h]
  struct _D3DCOLORVALUE *v51; // [rsp+60h] [rbp-A8h]
  _QWORD **v52; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v53[3]; // [rsp+70h] [rbp-98h] BYREF
  struct _D3DCOLORVALUE v54; // [rsp+88h] [rbp-80h] BYREF
  int v55; // [rsp+98h] [rbp-70h]
  _BYTE v56[16]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v57[16]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v58; // [rsp+C0h] [rbp-48h]
  __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 v59; // [rsp+C8h] [rbp-40h] BYREF

  v58 = a2;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v56);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v57);
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v10);
  v55 = 1;
  if ( !v11 || !(unsigned __int8)std::operator!=<ID3D11Device>(v11 + 216) )
    *((_DWORD *)this + 14) = -2147024809;
  if ( *((int *)this + 14) >= 0 )
  {
    std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(&v52);
    std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(&v52, *v12 + 16LL);
    LODWORD(v48) = 0;
    if ( a5 )
    {
      v14 = *(_QWORD *)(*(_QWORD *)this + 16LL);
      v49 = 0;
      v50 = &v48;
      v51 = (struct _D3DCOLORVALUE *)v56;
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD **, __int64, __int64 *))(*(_QWORD *)v14 + 72LL))(
              v14,
              v52,
              v13 + 104,
              &v49);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v49);
      if ( (int)v48 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v48, v16, v17, v18);
      if ( v15 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
    }
    else
    {
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v54);
      v49 = 0;
      v50 = &v48;
      v51 = &v54;
      *((_DWORD *)this + 14) = SolidPathCluster::WidenPath(this, &v52, v19 + 200, &v49);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v49);
      if ( *((int *)this + 14) >= 0 )
      {
        if ( (int)v48 >= 0 )
        {
          LODWORD(v53[1]) = 0;
          v27 = *(_QWORD *)(*(_QWORD *)this + 16LL);
          v49 = 0;
          v50 = (xpsrdr **)&v53[1];
          v51 = (struct _D3DCOLORVALUE *)v56;
          v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v27 + 72LL))(
                  v27,
                  *(_QWORD *)&v54.r,
                  a3 + 104,
                  &v49);
          detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v49);
          if ( SLODWORD(v53[1]) < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v53[1]), v29, v30, v31);
          if ( v28 < 0 )
            xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v28, v29, v30, v31);
        }
        else
        {
          *((_DWORD *)this + 14) = (_DWORD)v48;
        }
      }
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v54);
    }
    std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v52);
    if ( *((int *)this + 14) >= 0 )
    {
      std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(&v52);
      std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(&v52, v20);
      if ( (unsigned __int8)std::operator!=<ID3D11Device>(&v52) )
      {
        *((_DWORD *)this + 14) = 0;
        LODWORD(v53[1]) = 0;
        v21 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v52;
        v22 = (__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))**v52;
        v49 = 0;
        v50 = (xpsrdr **)&v53[1];
        v51 = (struct _D3DCOLORVALUE *)v57;
        v23 = (*v22)(v21, &GUID_a06f9f05_3be9_4763_98a8_094fc672e488, &v49);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v49);
        if ( SLODWORD(v53[1]) < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v53[1]), v24, v25, v26);
        if ( v23 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v23, v24, v25, v26);
      }
      else
      {
        *((_DWORD *)this + 14) = -2147467259;
      }
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v52);
      if ( *((int *)this + 14) >= 0 )
      {
        if ( a5 || (v32 = 1, !(unsigned __int8)std::operator!=<ID3D11Device>(a3 + 168)) )
          v32 = 0;
        std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(&v54);
        std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(&v54, v57);
        LOBYTE(v33) = 1;
        SolidPathCluster::GetColorFromBrush(this, &v53[1], &v54, v33);
        v54 = *(struct _D3DCOLORVALUE *)&v53[1];
        SolidPathCluster::ConvertToXpsColor(v34, &v59, &v54);
        std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v52);
        LODWORD(v53[1]) = 0;
        XpsFactory = SolidPathCluster::GetXpsFactory(this);
        CreateSolidColorBrush = XpsFactory->lpVtbl->CreateSolidColorBrush;
        v49 = 0;
        v50 = (xpsrdr **)&v53[1];
        v51 = (struct _D3DCOLORVALUE *)&v52;
        v37 = ((__int64 (__fastcall *)(struct IXpsOMObjectFactory *, __MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024 *, _QWORD, __int64 *))CreateSolidColorBrush)(
                XpsFactory,
                &v59,
                0,
                &v49);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v49);
        if ( SLODWORD(v53[1]) < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)LODWORD(v53[1]), v38, v39, v40);
        if ( v37 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v37, v38, v39, v40);
        v41 = ((__int64 (__fastcall *)(_QWORD **))(*v52)[6])(v52);
        *((_DWORD *)this + 14) = v41;
        if ( v41 >= 0 )
        {
          v53[1] = operator new(0x38u);
          v42 = std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(&v54, v56);
          v45 = XgcSolidPath::XgcSolidPath(v44, (unsigned int)&v52, v42, a4, v32, v43, a6);
          v46 = std::shared_ptr<XgcSolidPath>::shared_ptr<XgcSolidPath>(&v49, v45);
          std::shared_ptr<_devicemodeW>::operator=(a2, v46);
          std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v49);
        }
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v52);
      }
    }
  }
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v57);
  std::_Ptr_base<ID2D1RenderTarget>::_Decref(v56);
  return a2;
}

```

## disassembly

```asm
0x180028acc  mov     rax, rsp
0x180028acf  push    rbp
0x180028ad0  push    rbx
0x180028ad1  push    rsi
0x180028ad2  push    rdi
0x180028ad3  push    r12
0x180028ad5  push    r13
0x180028ad7  push    r14
0x180028ad9  push    r15
0x180028adb  lea     rbp, [rax-58h]
0x180028adf  sub     rsp, 118h
0x180028ae6  movaps  xmmword ptr [rax-58h], xmm6
0x180028aea  mov     rax, cs:__security_cookie
0x180028af1  xor     rax, rsp
0x180028af4  mov     [rbp+50h+var_60], rax
0x180028af8  mov     r12, r9
0x180028afb  mov     rdi, r8
0x180028afe  mov     r14, rdx
0x180028b01  mov     rbx, rcx
0x180028b04  mov     [rbp+50h+var_98], rdx
0x180028b08  xor     r13d, r13d
0x180028b0b  mov     [rbp+50h+var_C0], r13d
0x180028b0f  lea     rcx, [rbp+50h+var_B8]
0x180028b13  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180028b18  nop
0x180028b19  lea     rcx, [rbp+50h+var_A8]
0x180028b1d  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180028b22  nop
0x180028b23  mov     rcx, rdx
0x180028b26  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180028b2b  mov     [rbp+50h+var_C0], 1
0x180028b32  lea     rdx, [r8+0D8h]
0x180028b39  test    r8, r8
0x180028b3c  jz      short loc_180028B4A
0x180028b3e  mov     rcx, rdx
0x180028b41  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180028b46  test    al, al
0x180028b48  jnz     short loc_180028B51
0x180028b4a  mov     dword ptr [rbx+38h], 80070057h
0x180028b51  mov     sil, [rbp+50h+arg_20]
0x180028b58  cmp     [rbx+38h], r13d
0x180028b5c  jl      loc_180028F0E
0x180028b62  lea     rcx, [rsp+150h+var_F0]
0x180028b67  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180028b6c  mov     rdx, [rdx]
0x180028b6f  add     rdx, 10h
0x180028b73  lea     rcx, [rsp+150h+var_F0]
0x180028b78  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180028b7d  nop
0x180028b7e  mov     dword ptr [rsp+150h+var_110], r13d
0x180028b83  test    sil, sil
0x180028b86  jz      short loc_180028BEA
0x180028b88  mov     rax, [rbx]
0x180028b8b  mov     rcx, [rax+10h]
0x180028b8f  mov     [rsp+150h+var_108], r13
0x180028b94  lea     rax, [rsp+150h+var_110]
0x180028b99  mov     [rsp+150h+var_100], rax
0x180028b9e  lea     rax, [rbp+50h+var_B8]
0x180028ba2  mov     [rsp+150h+var_F8], rax
0x180028ba7  mov     rax, [rcx]
0x180028baa  add     r8, 68h ; 'h'
0x180028bae  lea     r9, [rsp+150h+var_108]
0x180028bb3  mov     rdx, [rsp+150h+var_F0]
0x180028bb8  mov     rax, [rax+48h]
0x180028bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bc1  mov     r15d, eax
0x180028bc4  lea     rcx, [rsp+150h+var_108]
0x180028bc9  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180028bce  mov     ecx, dword ptr [rsp+150h+var_110]; this
0x180028bd2  test    ecx, ecx
0x180028bd4  jns     short loc_180028BDC
0x180028bd6  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180028bdc  test    r15d, r15d
0x180028bdf  jns     short loc_180028C52
0x180028be1  mov     ecx, r15d; this
0x180028be4  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180028bea  lea     rcx, [rbp+50h+var_D0]
0x180028bee  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180028bf3  nop
0x180028bf4  mov     [rsp+150h+var_108], r13
0x180028bf9  lea     rax, [rsp+150h+var_110]
0x180028bfe  mov     [rsp+150h+var_100], rax
0x180028c03  lea     rax, [rbp+50h+var_D0]
0x180028c07  mov     [rsp+150h+var_F8], rax
0x180028c0c  add     r8, 0C8h
0x180028c13  lea     r9, [rsp+150h+var_108]
0x180028c18  lea     rdx, [rsp+150h+var_F0]
0x180028c1d  mov     rcx, rbx
0x180028c20  call    ?WidenPath@SolidPathCluster@@AEAAJAEBV?$shared_ptr@UID2D1Geometry@@@std@@AEBV?$shared_ptr@VCXgcPenStyle@@@3@PEAPEAUID2D1Geometry@@@Z; SolidPathCluster::WidenPath(std::shared_ptr<ID2D1Geometry> const &,std::shared_ptr<CXgcPenStyle> const &,ID2D1Geometry * *)
0x180028c25  mov     [rbx+38h], eax
0x180028c28  lea     rcx, [rsp+150h+var_108]
0x180028c2d  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180028c32  mov     eax, [rbx+38h]
0x180028c35  test    eax, eax
0x180028c37  js      short loc_180028C48
0x180028c39  mov     eax, dword ptr [rsp+150h+var_110]
0x180028c3d  test    eax, eax
0x180028c3f  jns     loc_180028CFB
0x180028c45  mov     [rbx+38h], eax
0x180028c48  lea     rcx, [rbp+50h+var_D0]
0x180028c4c  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028c51  nop
0x180028c52  lea     rcx, [rsp+150h+var_F0]
0x180028c57  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028c5c  cmp     [rbx+38h], r13d
0x180028c60  jl      loc_180028F0E
0x180028c66  test    sil, sil
0x180028c69  lea     rdx, [rdi+0A8h]
0x180028c70  jnz     short loc_180028C79
0x180028c72  lea     rdx, [rdi+0B8h]
0x180028c79  lea     rcx, [rsp+150h+var_F0]
0x180028c7e  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180028c83  lea     rcx, [rsp+150h+var_F0]
0x180028c88  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180028c8d  nop
0x180028c8e  lea     rcx, [rsp+150h+var_F0]
0x180028c93  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180028c98  test    al, al
0x180028c9a  jz      loc_180028D73
0x180028ca0  mov     [rbx+38h], r13d
0x180028ca4  mov     dword ptr [rsp+150h+var_E8+8], r13d
0x180028ca9  mov     rax, [rsp+150h+var_F0]
0x180028cae  mov     rcx, [rax]
0x180028cb1  mov     rax, [rcx]
0x180028cb4  mov     [rsp+150h+var_108], r13
0x180028cb9  lea     rdx, [rsp+150h+var_E8+8]
0x180028cbe  mov     [rsp+150h+var_100], rdx
0x180028cc3  lea     rdx, [rbp+50h+var_A8]
0x180028cc7  mov     [rsp+150h+var_F8], rdx
0x180028ccc  lea     r8, [rsp+150h+var_108]
0x180028cd1  lea     rdx, _GUID_a06f9f05_3be9_4763_98a8_094fc672e488
0x180028cd8  mov     rax, [rax]
0x180028cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ce0  mov     r15d, eax
0x180028ce3  lea     rcx, [rsp+150h+var_108]
0x180028ce8  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180028ced  mov     ecx, dword ptr [rsp+150h+var_E8+8]; this
0x180028cf1  test    ecx, ecx
0x180028cf3  jns     short loc_180028D65
0x180028cf5  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180028cfb  mov     dword ptr [rsp+150h+var_E8+8], r13d
0x180028d00  mov     rax, [rbx]
0x180028d03  mov     rcx, [rax+10h]
0x180028d07  mov     [rsp+150h+var_108], r13
0x180028d0c  lea     rax, [rsp+150h+var_E8+8]
0x180028d11  mov     [rsp+150h+var_100], rax
0x180028d16  lea     rax, [rbp+50h+var_B8]
0x180028d1a  mov     [rsp+150h+var_F8], rax
0x180028d1f  mov     rax, [rcx]
0x180028d22  lea     r8, [rdi+68h]
0x180028d26  lea     r9, [rsp+150h+var_108]
0x180028d2b  mov     rdx, qword ptr [rbp+50h+var_D0.r]
0x180028d2f  mov     rax, [rax+48h]
0x180028d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d38  mov     r15d, eax
0x180028d3b  lea     rcx, [rsp+150h+var_108]
0x180028d40  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180028d45  mov     ecx, dword ptr [rsp+150h+var_E8+8]; this
0x180028d49  test    ecx, ecx
0x180028d4b  jns     short loc_180028D53
0x180028d4d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180028d53  test    r15d, r15d
0x180028d56  jns     loc_180028C48
0x180028d5c  mov     ecx, r15d; this
0x180028d5f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180028d65  test    r15d, r15d
0x180028d68  jns     short loc_180028D7A
0x180028d6a  mov     ecx, r15d; this
0x180028d6d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180028d73  mov     dword ptr [rbx+38h], 80004005h
0x180028d7a  lea     rcx, [rsp+150h+var_F0]
0x180028d7f  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028d84  cmp     [rbx+38h], r13d
0x180028d88  jl      loc_180028F0E
0x180028d8e  test    sil, sil
0x180028d91  jnz     short loc_180028DA6
0x180028d93  lea     rcx, [rdi+0A8h]
0x180028d9a  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180028d9f  test    al, al
0x180028da1  mov     r15b, 1
0x180028da4  jnz     short loc_180028DA9
0x180028da6  mov     r15b, r13b
0x180028da9  lea     rcx, [rbp+50h+var_D0]
0x180028dad  call    ??0?$_Ptr_base@UID3D11DeviceContext@@@std@@IEAA@XZ; std::_Ptr_base<ID3D11DeviceContext>::_Ptr_base<ID3D11DeviceContext>(void)
0x180028db2  lea     rdx, [rbp+50h+var_A8]
0x180028db6  lea     rcx, [rbp+50h+var_D0]
0x180028dba  call    ??$_Copy_construct_from@UIWICImagingFactory@@@?$_Ptr_base@UIWICImagingFactory@@@std@@IEAAXAEBV?$shared_ptr@UIWICImagingFactory@@@1@@Z; std::_Ptr_base<IWICImagingFactory>::_Copy_construct_from<IWICImagingFactory>(std::shared_ptr<IWICImagingFactory> const &)
0x180028dbf  mov     r9b, 1
0x180028dc2  lea     r8, [rbp+50h+var_D0]
0x180028dc6  lea     rdx, [rsp+150h+var_E8+8]
0x180028dcb  mov     rcx, rbx
0x180028dce  call    ?GetColorFromBrush@SolidPathCluster@@AEAA?AU_D3DCOLORVALUE@@V?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@_N@Z; SolidPathCluster::GetColorFromBrush(std::shared_ptr<IXpsOMSolidColorBrush>,bool)
0x180028dd3  movups  xmm6, xmmword ptr [rsp+150h+var_E8+8]
0x180028dd8  movups  xmmword ptr [rbp+50h+var_D0.r], xmm6
0x180028ddc  lea     r8, [rbp+50h+var_D0]; struct _D3DCOLORVALUE
0x180028de0  lea     rdx, [rbp+50h+var_90]; retstr
0x180028de4  call    ?ConvertToXpsColor@SolidPathCluster@@AEAA?AU__MIDL___MIDL_itf_xpsobjectmodel_0000_0000_0024@@U_D3DCOLORVALUE@@@Z; SolidPathCluster::ConvertToXpsColor(_D3DCOLORVALUE)
0x180028de9  lea     rcx, [rsp+150h+var_F0]
0x180028dee  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180028df3  nop
0x180028df4  mov     dword ptr [rsp+150h+var_E8+8], r13d
0x180028df9  mov     rcx, rbx; this
0x180028dfc  call    ?GetXpsFactory@SolidPathCluster@@AEAAPEAUIXpsOMObjectFactory@@XZ; SolidPathCluster::GetXpsFactory(void)
0x180028e01  mov     r10, rax
0x180028e04  mov     rcx, [rax]
0x180028e07  mov     rax, [rcx+0B8h]
0x180028e0e  mov     [rsp+150h+var_108], r13
0x180028e13  lea     rcx, [rsp+150h+var_E8+8]
0x180028e18  mov     [rsp+150h+var_100], rcx
0x180028e1d  lea     rcx, [rsp+150h+var_F0]
0x180028e22  mov     [rsp+150h+var_F8], rcx
0x180028e27  lea     r9, [rsp+150h+var_108]
0x180028e2c  xor     r8d, r8d
0x180028e2f  lea     rdx, [rbp+50h+var_90]
0x180028e33  mov     rcx, r10
0x180028e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e3b  mov     esi, eax
0x180028e3d  lea     rcx, [rsp+150h+var_108]
0x180028e42  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180028e47  mov     ecx, dword ptr [rsp+150h+var_E8+8]; this
0x180028e4b  test    ecx, ecx
0x180028e4d  jns     short loc_180028E55
0x180028e4f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180028e55  test    esi, esi
0x180028e57  jns     short loc_180028E61
0x180028e59  mov     ecx, esi; this
0x180028e5b  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180028e61  mov     rcx, [rsp+150h+var_F0]
0x180028e66  mov     rax, [rcx]
0x180028e69  movss   xmm1, dword ptr [rdi+8]
0x180028e6e  mov     rax, [rax+30h]
0x180028e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e77  mov     [rbx+38h], eax
0x180028e7a  test    eax, eax
0x180028e7c  js      loc_180028F03
0x180028e82  mov     ecx, 38h ; '8'; Size
0x180028e87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028e8c  mov     r10, rax
0x180028e8f  mov     qword ptr [rsp+150h+var_E8+8], rax
0x180028e94  shufps  xmm6, xmm6, 0FFh
0x180028e98  mulss   xmm6, dword ptr [rdi+8]
0x180028e9d  movss   xmm0, cs:__real@3f800000
0x180028ea5  comiss  xmm0, xmm6
0x180028ea8  setbe   r8b
0x180028eac  lea     rdx, [rbp+50h+var_B8]
0x180028eb0  lea     rcx, [rbp+50h+var_D0]
0x180028eb4  call    ??$?0UID2D1TransformedGeometry@@$0A@@?$shared_ptr@UID2D1Geometry@@@std@@QEAA@AEBV?$shared_ptr@UID2D1TransformedGeometry@@@1@@Z; std::shared_ptr<ID2D1Geometry>::shared_ptr<ID2D1Geometry>(std::shared_ptr<ID2D1TransformedGeometry> const &)
0x180028eb9  mov     ecx, [rbp+50h+arg_28]
0x180028ebf  mov     [rsp+30h], ecx
0x180028ec3  mov     byte ptr [rsp+150h+var_128], r8b
0x180028ec8  mov     [rsp+150h+var_130], r15b
0x180028ecd  mov     r9, r12
0x180028ed0  mov     r8, rax
0x180028ed3  lea     rdx, [rsp+150h+var_F0]
0x180028ed8  mov     rcx, r10
0x180028edb  call    ??0XgcSolidPath@@QEAA@AEAV?$shared_ptr@UIXpsOMSolidColorBrush@@@std@@V?$shared_ptr@UID2D1Geometry@@@2@AEAV32@_N3H@Z; XgcSolidPath::XgcSolidPath(std::shared_ptr<IXpsOMSolidColorBrush> &,std::shared_ptr<ID2D1Geometry>,std::shared_ptr<ID2D1Geometry> &,bool,bool,int)
0x180028ee0  mov     rdx, rax
0x180028ee3  lea     rcx, [rsp+150h+var_108]
0x180028ee8  call    ??$?0VXgcSolidPath@@$0A@@?$shared_ptr@VXgcSolidPath@@@std@@QEAA@PEAVXgcSolidPath@@@Z; std::shared_ptr<XgcSolidPath>::shared_ptr<XgcSolidPath>(XgcSolidPath *)
0x180028eed  mov     rdx, rax
0x180028ef0  mov     rcx, r14
0x180028ef3  call    ??4?$shared_ptr@U_devicemodeW@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<_devicemodeW>::operator=(std::shared_ptr<_devicemodeW> &&)
0x180028ef8  lea     rcx, [rsp+150h+var_108]
0x180028efd  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028f02  nop
0x180028f03  lea     rcx, [rsp+150h+var_F0]
0x180028f08  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028f0d  nop
0x180028f0e  lea     rcx, [rbp+50h+var_A8]
0x180028f12  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028f17  nop
0x180028f18  lea     rcx, [rbp+50h+var_B8]
0x180028f1c  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180028f21  mov     rax, r14
0x180028f24  mov     rcx, [rbp+50h+var_60]
0x180028f28  xor     rcx, rsp; StackCookie
0x180028f2b  call    __security_check_cookie
0x180028f30  movaps  xmm6, [rsp+150h+var_58+8]
0x180028f38  add     rsp, 118h
0x180028f3f  pop     r15
0x180028f41  pop     r14
0x180028f43  pop     r13
0x180028f45  pop     r12
0x180028f47  pop     rdi
0x180028f48  pop     rsi
0x180028f49  pop     rbx
0x180028f4a  pop     rbp
0x180028f4b  retn
```
