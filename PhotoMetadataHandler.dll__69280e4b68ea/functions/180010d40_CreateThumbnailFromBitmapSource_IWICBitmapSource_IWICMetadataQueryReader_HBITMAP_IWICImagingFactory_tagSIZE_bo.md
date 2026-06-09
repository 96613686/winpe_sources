# CreateThumbnailFromBitmapSource(IWICBitmapSource *,IWICMetadataQueryReader *,HBITMAP__ * *,IWICImagingFactory *,tagSIZE,bool)

- ea: `0x180010d40`
- end: `0x180011043`
- name: `?CreateThumbnailFromBitmapSource@@YAJPEAUIWICBitmapSource@@PEAUIWICMetadataQueryReader@@PEAPEAUHBITMAP__@@PEAUIWICImagingFactory@@UtagSIZE@@_N@Z`
- size: `771`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, struct IWICMetadataQueryReader *, HBITMAP *, struct IWICImagingFactory *, struct tagSIZE, bool)`
- caller_count: `3`
- callee_count: `14`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180011050`
- `0x18001e230`
- `0x18001e448`

## callees

- `0x180006410`
- `0x180008b54`
- `0x18000e3a0`
- `0x18000eaac`
- `0x18000ecd0`
- `0x18000f050`
- `0x18000fc00`
- `0x180010314`
- `0x180010420`
- `0x180010d40`
- `0x180015568`
- `0x18001e0bc`
- `0x18001e940`
- `0x180029010`

## import_xrefs

- `WindowsCodecs!WICConvertBitmapSource` at `0x180010e12`
- `WindowsCodecs!WICConvertBitmapSource` at `0x180010f5f`
- `WindowsCodecs!WICConvertBitmapSource` at `0x180010e12`
- `WindowsCodecs!WICConvertBitmapSource` at `0x180010f5f`

## pseudocode

```c
__int64 __fastcall CreateThumbnailFromBitmapSource(
        struct IWICBitmapSource *a1,
        struct IWICMetadataQueryReader *a2,
        HBITMAP *a3,
        struct IWICImagingFactory *a4,
        struct tagSIZE a5,
        bool a6)
{
  HRESULT v10; // esi
  struct IWICBitmapSource *v11; // rbx
  char v12; // r15
  struct IWICBitmapSource *v13; // rdi
  unsigned int v15; // [rsp+40h] [rbp-38h] BYREF
  IWICBitmapSource *pISrc; // [rsp+48h] [rbp-30h] BYREF
  struct IWICBitmapFrameDecode *v17; // [rsp+50h] [rbp-28h] BYREF
  struct IWICColorTransform *v18; // [rsp+58h] [rbp-20h] BYREF
  IWICBitmapSource *ppIDst[3]; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v20; // [rsp+C0h] [rbp+48h] BYREF

  v15 = 0;
  v20 = 0;
  ATL::CComPtrBase<IWICBitmapSource>::CComPtrBase<IWICBitmapSource>(&pISrc, a1);
  v10 = -2147024809;
  if ( a1 )
  {
    v11 = pISrc;
    if ( pISrc )
    {
      v10 = ((__int64 (__fastcall *)(IWICBitmapSource *, unsigned int *, unsigned int *))pISrc->lpVtbl->GetSize)(
              pISrc,
              &v15,
              &v20);
      if ( v10 >= 0 )
      {
        *(double *)&v18 = 0.0;
        *(double *)&v17 = 0.0;
        GetResolutionDefaulted(v11, (double *)&v18, (double *)&v17);
        NormalizeResolution((double *)&v18, (double *)&v17);
        v12 = 0;
        if ( (unsigned __int8)IsDefaultPixelFormatHDR(a1) && (unsigned __int8)CanConvertToSDR(a1) )
        {
          ppIDst[0] = 0;
          v10 = WICConvertBitmapSource(&GUID_WICPixelFormat32bppBGRA, v11, ppIDst);
          if ( v10 >= 0 )
          {
            ATL::CComPtr<IWICBitmapSource>::operator=(&pISrc, ppIDst);
            v12 = 1;
            v11 = pISrc;
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppIDst);
        }
        if ( v15 && v20 )
        {
          if ( v15 > a5.cx || v20 > a5.cy || *(double *)&v18 != *(double *)&v17 )
          {
            ppIDst[0] = 0;
            v10 = ResizeIWICBitmap(v11, a4, &a5, *(double *)&v18, *(double *)&v17, a6, ppIDst);
            if ( v10 >= 0 )
            {
              ATL::CComPtr<IWICBitmapSource>::operator=(&pISrc, ppIDst);
              v11 = pISrc;
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppIDst);
          }
          if ( a2 )
          {
            ppIDst[0] = 0;
            v10 = WICCreateCachedOrientedBitmapSource(a4, v11, a2, ppIDst);
            if ( v10 >= 0 )
            {
              v13 = ppIDst[0];
              v10 = ((__int64 (__fastcall *)(IWICBitmapSource *, unsigned int *, unsigned int *))ppIDst[0]->lpVtbl->GetSize)(
                      ppIDst[0],
                      &v15,
                      &v20);
              if ( v10 >= 0 )
              {
                GetResolutionDefaulted(v13, (double *)&v18, (double *)&v17);
                NormalizeResolution((double *)&v18, (double *)&v17);
                ATL::CComPtr<IWICBitmapSource>::operator=(&pISrc, ppIDst);
                v11 = pISrc;
              }
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppIDst);
          }
          if ( v10 >= 0 )
          {
            if ( v12 )
              goto LABEL_27;
            ppIDst[0] = 0;
            v10 = WICConvertBitmapSource(&GUID_WICPixelFormat32bppBGRA, v11, ppIDst);
            if ( v10 >= 0 )
            {
              ATL::CComPtr<IWICBitmapSource>::operator=(&pISrc, ppIDst);
              v11 = pISrc;
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppIDst);
            if ( v10 >= 0 )
            {
LABEL_27:
              *(double *)&v17 = 0.0;
              if ( ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *, struct IWICBitmapFrameDecode **))a1->lpVtbl->QueryInterface)(
                     a1,
                     &GUID_3b16811b_6a43_4ec9_a813_3d930c13b940,
                     &v17) >= 0 )
              {
                *(double *)&v18 = 0.0;
                if ( (int)GetsRGBTransformer(v17, v11, a4, &v18) >= 0 )
                {
                  ppIDst[0] = 0;
                  if ( (int)ATL::CComPtrBase<IWICColorTransform>::QueryInterface<IWICBitmapSource>(&v18, ppIDst) >= 0 )
                  {
                    ATL::CComPtr<IWICBitmapSource>::operator=(&pISrc, ppIDst);
                    v11 = pISrc;
                  }
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppIDst);
                }
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
              v10 = ConvertIWICBitmapSourceTo32bppHBITMAP(v11, a3);
            }
          }
        }
        else
        {
          v10 = -2147418113;
        }
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&pISrc);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180010d40  push    rbp
0x180010d42  push    rbx
0x180010d43  push    rsi
0x180010d44  push    rdi
0x180010d45  push    r12
0x180010d47  push    r13
0x180010d49  push    r14
0x180010d4b  push    r15
0x180010d4d  mov     rbp, rsp
0x180010d50  sub     rsp, 78h
0x180010d54  mov     r12, r9
0x180010d57  mov     r13, r8
0x180010d5a  mov     rdi, rdx
0x180010d5d  mov     r14, rcx
0x180010d60  mov     [rbp+var_38], 0
0x180010d67  mov     [rbp+arg_0], 0
0x180010d6e  mov     rdx, rcx
0x180010d71  lea     rcx, [rbp+pISrc]
0x180010d75  call    ??0?$CComPtrBase@UIWICBitmapSource@@@ATL@@IEAA@PEAUIWICBitmapSource@@@Z; ATL::CComPtrBase<IWICBitmapSource>::CComPtrBase<IWICBitmapSource>(IWICBitmapSource *)
0x180010d7a  nop
0x180010d7b  mov     esi, 80070057h
0x180010d80  test    r14, r14
0x180010d83  jz      loc_180011026
0x180010d89  mov     rbx, [rbp+pISrc]
0x180010d8d  test    rbx, rbx
0x180010d90  jz      loc_180011026
0x180010d96  mov     rax, [rbx]
0x180010d99  lea     r8, [rbp+arg_0]
0x180010d9d  lea     rdx, [rbp+var_38]
0x180010da1  mov     rcx, rbx
0x180010da4  mov     rax, [rax+18h]
0x180010da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dad  mov     esi, eax
0x180010daf  test    eax, eax
0x180010db1  js      loc_180011026
0x180010db7  xorps   xmm0, xmm0
0x180010dba  movsd   [rbp+var_20], xmm0
0x180010dbf  movsd   [rbp+var_28], xmm0
0x180010dc4  lea     r8, [rbp+var_28]; double *
0x180010dc8  lea     rdx, [rbp+var_20]; double *
0x180010dcc  mov     rcx, rbx; struct IWICBitmapSource *
0x180010dcf  call    ?GetResolutionDefaulted@@YAXPEAUIWICBitmapSource@@PEAN1@Z; GetResolutionDefaulted(IWICBitmapSource *,double *,double *)
0x180010dd4  lea     rdx, [rbp+var_28]; double *
0x180010dd8  lea     rcx, [rbp+var_20]; double *
0x180010ddc  call    ?NormalizeResolution@@YAXPEAN0@Z; NormalizeResolution(double *,double *)
0x180010de1  xor     r15b, r15b
0x180010de4  mov     rcx, r14
0x180010de7  call    IsDefaultPixelFormatHDR
0x180010dec  test    al, al
0x180010dee  jz      short loc_180010E41
0x180010df0  mov     rcx, r14
0x180010df3  call    CanConvertToSDR
0x180010df8  test    al, al
0x180010dfa  jz      short loc_180010E41
0x180010dfc  mov     [rbp+ppIDst], 0
0x180010e04  lea     r8, [rbp+ppIDst]; ppIDst
0x180010e08  mov     rdx, rbx; pISrc
0x180010e0b  lea     rcx, GUID_WICPixelFormat32bppBGRA; dstFormat
0x180010e12  call    cs:__imp_WICConvertBitmapSource
0x180010e19  nop     dword ptr [rax+rax+00h]
0x180010e1e  mov     esi, eax
0x180010e20  test    eax, eax
0x180010e22  js      short loc_180010E38
0x180010e24  lea     rdx, [rbp+ppIDst]
0x180010e28  lea     rcx, [rbp+pISrc]
0x180010e2c  call    ??4?$CComPtr@UIWICBitmapSource@@@ATL@@QEAAPEAUIWICBitmapSource@@AEBV01@@Z; ATL::CComPtr<IWICBitmapSource>::operator=(ATL::CComPtr<IWICBitmapSource> const &)
0x180010e31  mov     r15b, 1
0x180010e34  mov     rbx, [rbp+pISrc]
0x180010e38  lea     rcx, [rbp+ppIDst]
0x180010e3c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010e41  mov     eax, [rbp+var_38]
0x180010e44  test    eax, eax
0x180010e46  jz      loc_180011021
0x180010e4c  mov     ecx, [rbp+arg_0]
0x180010e4f  test    ecx, ecx
0x180010e51  jz      loc_180011021
0x180010e57  movsd   xmm3, [rbp+var_20]; double
0x180010e5c  movsd   xmm0, [rbp+var_28]
0x180010e61  cmp     eax, [rbp+arg_20.cx]
0x180010e64  ja      short loc_180010E73
0x180010e66  cmp     ecx, [rbp+arg_20.cy]
0x180010e69  ja      short loc_180010E73
0x180010e6b  ucomisd xmm3, xmm0
0x180010e6f  jp      short loc_180010E73
0x180010e71  jz      short loc_180010EC1
0x180010e73  mov     [rbp+ppIDst], 0
0x180010e7b  movzx   eax, [rbp+arg_28]
0x180010e7f  lea     rcx, [rbp+ppIDst]
0x180010e83  mov     [rsp+78h+var_48], rcx; struct IWICBitmapSource **
0x180010e88  mov     [rsp+78h+var_50], eax; int
0x180010e8c  movsd   [rsp+78h+var_58], xmm0; double
0x180010e92  lea     r8, [rbp+arg_20]; struct tagSIZE *
0x180010e96  mov     rdx, r12; struct IWICImagingFactory *
0x180010e99  mov     rcx, rbx; struct IWICBitmapSource *
0x180010e9c  call    ?ResizeIWICBitmap@@YAJPEAUIWICBitmapSource@@PEAUIWICImagingFactory@@PEBUtagSIZE@@NNHPEAPEAU1@@Z; ResizeIWICBitmap(IWICBitmapSource *,IWICImagingFactory *,tagSIZE const *,double,double,int,IWICBitmapSource * *)
0x180010ea1  mov     esi, eax
0x180010ea3  test    eax, eax
0x180010ea5  js      short loc_180010EB8
0x180010ea7  lea     rdx, [rbp+ppIDst]
0x180010eab  lea     rcx, [rbp+pISrc]
0x180010eaf  call    ??4?$CComPtr@UIWICBitmapSource@@@ATL@@QEAAPEAUIWICBitmapSource@@AEBV01@@Z; ATL::CComPtr<IWICBitmapSource>::operator=(ATL::CComPtr<IWICBitmapSource> const &)
0x180010eb4  mov     rbx, [rbp+pISrc]
0x180010eb8  lea     rcx, [rbp+ppIDst]
0x180010ebc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010ec1  test    rdi, rdi
0x180010ec4  jz      short loc_180010F3E
0x180010ec6  mov     [rbp+ppIDst], 0
0x180010ece  lea     r9, [rbp+ppIDst]; struct IWICBitmapSource **
0x180010ed2  mov     r8, rdi; struct IWICMetadataQueryReader *
0x180010ed5  mov     rdx, rbx; struct IWICBitmapSource *
0x180010ed8  mov     rcx, r12; struct IWICImagingFactory *
0x180010edb  call    ?WICCreateCachedOrientedBitmapSource@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAUIWICMetadataQueryReader@@PEAPEAU2@@Z; WICCreateCachedOrientedBitmapSource(IWICImagingFactory *,IWICBitmapSource *,IWICMetadataQueryReader *,IWICBitmapSource * *)
0x180010ee0  mov     esi, eax
0x180010ee2  test    eax, eax
0x180010ee4  js      short loc_180010F35
0x180010ee6  mov     rdi, [rbp+ppIDst]
0x180010eea  mov     rax, [rdi]
0x180010eed  lea     r8, [rbp+arg_0]
0x180010ef1  lea     rdx, [rbp+var_38]
0x180010ef5  mov     rcx, rdi
0x180010ef8  mov     rax, [rax+18h]
0x180010efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f01  mov     esi, eax
0x180010f03  test    eax, eax
0x180010f05  js      short loc_180010F35
0x180010f07  lea     r8, [rbp+var_28]; double *
0x180010f0b  lea     rdx, [rbp+var_20]; double *
0x180010f0f  mov     rcx, rdi; struct IWICBitmapSource *
0x180010f12  call    ?GetResolutionDefaulted@@YAXPEAUIWICBitmapSource@@PEAN1@Z; GetResolutionDefaulted(IWICBitmapSource *,double *,double *)
0x180010f17  lea     rdx, [rbp+var_28]; double *
0x180010f1b  lea     rcx, [rbp+var_20]; double *
0x180010f1f  call    ?NormalizeResolution@@YAXPEAN0@Z; NormalizeResolution(double *,double *)
0x180010f24  lea     rdx, [rbp+ppIDst]
0x180010f28  lea     rcx, [rbp+pISrc]
0x180010f2c  call    ??4?$CComPtr@UIWICBitmapSource@@@ATL@@QEAAPEAUIWICBitmapSource@@AEBV01@@Z; ATL::CComPtr<IWICBitmapSource>::operator=(ATL::CComPtr<IWICBitmapSource> const &)
0x180010f31  mov     rbx, [rbp+pISrc]
0x180010f35  lea     rcx, [rbp+ppIDst]
0x180010f39  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010f3e  xor     edi, edi
0x180010f40  test    esi, esi
0x180010f42  js      loc_180011026
0x180010f48  test    r15b, r15b
0x180010f4b  jnz     short loc_180010F93
0x180010f4d  mov     [rbp+ppIDst], rdi
0x180010f51  lea     r8, [rbp+ppIDst]; ppIDst
0x180010f55  mov     rdx, rbx; pISrc
0x180010f58  lea     rcx, GUID_WICPixelFormat32bppBGRA; dstFormat
0x180010f5f  call    cs:__imp_WICConvertBitmapSource
0x180010f66  nop     dword ptr [rax+rax+00h]
0x180010f6b  mov     esi, eax
0x180010f6d  test    eax, eax
0x180010f6f  js      short loc_180010F82
0x180010f71  lea     rdx, [rbp+ppIDst]
0x180010f75  lea     rcx, [rbp+pISrc]
0x180010f79  call    ??4?$CComPtr@UIWICBitmapSource@@@ATL@@QEAAPEAUIWICBitmapSource@@AEBV01@@Z; ATL::CComPtr<IWICBitmapSource>::operator=(ATL::CComPtr<IWICBitmapSource> const &)
0x180010f7e  mov     rbx, [rbp+pISrc]
0x180010f82  lea     rcx, [rbp+ppIDst]
0x180010f86  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010f8b  test    esi, esi
0x180010f8d  js      loc_180011026
0x180010f93  mov     [rbp+var_28], rdi
0x180010f97  mov     rax, [r14]
0x180010f9a  lea     r8, [rbp+var_28]
0x180010f9e  lea     rdx, _GUID_3b16811b_6a43_4ec9_a813_3d930c13b940
0x180010fa5  mov     rcx, r14
0x180010fa8  mov     rax, [rax]
0x180010fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fb0  test    eax, eax
0x180010fb2  js      short loc_180011009
0x180010fb4  mov     [rbp+var_20], rdi
0x180010fb8  lea     r9, [rbp+var_20]; struct IWICColorTransform **
0x180010fbc  mov     r8, r12; struct IWICImagingFactory *
0x180010fbf  mov     rdx, rbx; struct IWICBitmapSource *
0x180010fc2  mov     rcx, [rbp+var_28]; struct IWICBitmapFrameDecode *
0x180010fc6  call    ?GetsRGBTransformer@@YAJPEAUIWICBitmapFrameDecode@@PEAUIWICBitmapSource@@PEAUIWICImagingFactory@@PEAPEAUIWICColorTransform@@@Z; GetsRGBTransformer(IWICBitmapFrameDecode *,IWICBitmapSource *,IWICImagingFactory *,IWICColorTransform * *)
0x180010fcb  test    eax, eax
0x180010fcd  js      short loc_180010FFF
0x180010fcf  mov     [rbp+ppIDst], rdi
0x180010fd3  lea     rdx, [rbp+ppIDst]
0x180010fd7  lea     rcx, [rbp+var_20]
0x180010fdb  call    ??$QueryInterface@UIWICBitmapSource@@@?$CComPtrBase@UIWICColorTransform@@@ATL@@QEBAJPEAPEAUIWICBitmapSource@@@Z; ATL::CComPtrBase<IWICColorTransform>::QueryInterface<IWICBitmapSource>(IWICBitmapSource * *)
0x180010fe0  test    eax, eax
0x180010fe2  js      short loc_180010FF5
0x180010fe4  lea     rdx, [rbp+ppIDst]
0x180010fe8  lea     rcx, [rbp+pISrc]
0x180010fec  call    ??4?$CComPtr@UIWICBitmapSource@@@ATL@@QEAAPEAUIWICBitmapSource@@AEBV01@@Z; ATL::CComPtr<IWICBitmapSource>::operator=(ATL::CComPtr<IWICBitmapSource> const &)
0x180010ff1  mov     rbx, [rbp+pISrc]
0x180010ff5  lea     rcx, [rbp+ppIDst]
0x180010ff9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010ffe  nop
0x180010fff  lea     rcx, [rbp+var_20]
0x180011003  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180011008  nop
0x180011009  lea     rcx, [rbp+var_28]
0x18001100d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180011012  mov     rdx, r13; HBITMAP *
0x180011015  mov     rcx, rbx; struct IWICBitmapSource *
0x180011018  call    ?ConvertIWICBitmapSourceTo32bppHBITMAP@@YAJPEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; ConvertIWICBitmapSourceTo32bppHBITMAP(IWICBitmapSource *,HBITMAP__ * *)
0x18001101d  mov     esi, eax
0x18001101f  jmp     short loc_180011026
0x180011021  mov     esi, 8000FFFFh
0x180011026  lea     rcx, [rbp+pISrc]
0x18001102a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001102f  mov     eax, esi
0x180011031  add     rsp, 78h
0x180011035  pop     r15
0x180011037  pop     r14
0x180011039  pop     r13
0x18001103b  pop     r12
0x18001103d  pop     rdi
0x18001103e  pop     rsi
0x18001103f  pop     rbx
0x180011040  pop     rbp
0x180011041  retn
```
