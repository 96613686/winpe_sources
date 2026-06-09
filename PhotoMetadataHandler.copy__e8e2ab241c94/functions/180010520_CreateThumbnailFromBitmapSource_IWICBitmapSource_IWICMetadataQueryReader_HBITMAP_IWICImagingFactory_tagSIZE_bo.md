# CreateThumbnailFromBitmapSource(IWICBitmapSource *,IWICMetadataQueryReader *,HBITMAP__ * *,IWICImagingFactory *,tagSIZE,bool)

- ea: `0x180010520`
- end: `0x180010824`
- name: `?CreateThumbnailFromBitmapSource@@YAJPEAUIWICBitmapSource@@PEAUIWICMetadataQueryReader@@PEAPEAUHBITMAP__@@PEAUIWICImagingFactory@@UtagSIZE@@_N@Z`
- size: `772`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, struct IWICMetadataQueryReader *, HBITMAP *, struct IWICImagingFactory *, struct tagSIZE, bool)`
- caller_count: `3`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180010830`
- `0x18001d46c`
- `0x18001d678`

## callees

- `0x1800062c8`
- `0x180007804`
- `0x18000dce0`
- `0x18000e3d0`
- `0x18000e600`
- `0x18000e950`
- `0x18000f4b4`
- `0x18000fb40`
- `0x18000fc84`
- `0x180010520`
- `0x18001d2f8`
- `0x18001db40`
- `0x180028010`

## import_xrefs

- `WindowsCodecs!WICConvertBitmapSource` at `0x1800105f2`
- `WindowsCodecs!WICConvertBitmapSource` at `0x180010739`
- `WindowsCodecs!WICConvertBitmapSource` at `0x1800105f2`
- `WindowsCodecs!WICConvertBitmapSource` at `0x180010739`

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
                  if ( ((__int64 (__fastcall *)(struct IWICColorTransform *, GUID *, IWICBitmapSource **))v18->lpVtbl->QueryInterface)(
                         v18,
                         &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
                         ppIDst) >= 0 )
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
0x180010520  push    rbp
0x180010522  push    rbx
0x180010523  push    rsi
0x180010524  push    rdi
0x180010525  push    r12
0x180010527  push    r13
0x180010529  push    r14
0x18001052b  push    r15
0x18001052d  mov     rbp, rsp
0x180010530  sub     rsp, 78h
0x180010534  mov     r12, r9
0x180010537  mov     r13, r8
0x18001053a  mov     rdi, rdx
0x18001053d  mov     r14, rcx
0x180010540  mov     [rbp+var_38], 0
0x180010547  mov     [rbp+arg_0], 0
0x18001054e  mov     rdx, rcx
0x180010551  lea     rcx, [rbp+pISrc]
0x180010555  call    ??0?$CComPtrBase@UIWICBitmapSource@@@ATL@@IEAA@PEAUIWICBitmapSource@@@Z; ATL::CComPtrBase<IWICBitmapSource>::CComPtrBase<IWICBitmapSource>(IWICBitmapSource *)
0x18001055a  nop
0x18001055b  mov     esi, 80070057h
0x180010560  test    r14, r14
0x180010563  jz      loc_180010808
0x180010569  mov     rbx, [rbp+pISrc]
0x18001056d  test    rbx, rbx
0x180010570  jz      loc_180010808
0x180010576  mov     rax, [rbx]
0x180010579  lea     r8, [rbp+arg_0]
0x18001057d  lea     rdx, [rbp+var_38]
0x180010581  mov     rcx, rbx
0x180010584  mov     rax, [rax+18h]
0x180010588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001058d  mov     esi, eax
0x18001058f  test    eax, eax
0x180010591  js      loc_180010808
0x180010597  xorps   xmm0, xmm0
0x18001059a  movsd   [rbp+var_20], xmm0
0x18001059f  movsd   [rbp+var_28], xmm0
0x1800105a4  lea     r8, [rbp+var_28]; double *
0x1800105a8  lea     rdx, [rbp+var_20]; double *
0x1800105ac  mov     rcx, rbx; struct IWICBitmapSource *
0x1800105af  call    ?GetResolutionDefaulted@@YAXPEAUIWICBitmapSource@@PEAN1@Z; GetResolutionDefaulted(IWICBitmapSource *,double *,double *)
0x1800105b4  lea     rdx, [rbp+var_28]; double *
0x1800105b8  lea     rcx, [rbp+var_20]; double *
0x1800105bc  call    ?NormalizeResolution@@YAXPEAN0@Z; NormalizeResolution(double *,double *)
0x1800105c1  xor     r15b, r15b
0x1800105c4  mov     rcx, r14
0x1800105c7  call    IsDefaultPixelFormatHDR
0x1800105cc  test    al, al
0x1800105ce  jz      short loc_18001061B
0x1800105d0  mov     rcx, r14
0x1800105d3  call    CanConvertToSDR
0x1800105d8  test    al, al
0x1800105da  jz      short loc_18001061B
0x1800105dc  mov     [rbp+ppIDst], 0
0x1800105e4  lea     r8, [rbp+ppIDst]; ppIDst
0x1800105e8  mov     rdx, rbx; pISrc
0x1800105eb  lea     rcx, GUID_WICPixelFormat32bppBGRA; dstFormat
0x1800105f2  call    cs:__imp_WICConvertBitmapSource
0x1800105f8  mov     esi, eax
0x1800105fa  test    eax, eax
0x1800105fc  js      short loc_180010612
0x1800105fe  lea     rdx, [rbp+ppIDst]
0x180010602  lea     rcx, [rbp+pISrc]
0x180010606  call    ??4?$CComPtr@UIWICBitmapSource@@@ATL@@QEAAPEAUIWICBitmapSource@@AEBV01@@Z; ATL::CComPtr<IWICBitmapSource>::operator=(ATL::CComPtr<IWICBitmapSource> const &)
0x18001060b  mov     r15b, 1
0x18001060e  mov     rbx, [rbp+pISrc]
0x180010612  lea     rcx, [rbp+ppIDst]
0x180010616  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001061b  mov     eax, [rbp+var_38]
0x18001061e  test    eax, eax
0x180010620  jz      loc_180010803
0x180010626  mov     ecx, [rbp+arg_0]
0x180010629  test    ecx, ecx
0x18001062b  jz      loc_180010803
0x180010631  movsd   xmm3, [rbp+var_20]; double
0x180010636  movsd   xmm0, [rbp+var_28]
0x18001063b  cmp     eax, [rbp+arg_20.cx]
0x18001063e  ja      short loc_18001064D
0x180010640  cmp     ecx, [rbp+arg_20.cy]
0x180010643  ja      short loc_18001064D
0x180010645  ucomisd xmm3, xmm0
0x180010649  jp      short loc_18001064D
0x18001064b  jz      short loc_18001069B
0x18001064d  mov     [rbp+ppIDst], 0
0x180010655  movzx   eax, [rbp+arg_28]
0x180010659  lea     rcx, [rbp+ppIDst]
0x18001065d  mov     [rsp+78h+var_48], rcx; struct IWICBitmapSource **
0x180010662  mov     [rsp+78h+var_50], eax; int
0x180010666  movsd   [rsp+78h+var_58], xmm0; double
0x18001066c  lea     r8, [rbp+arg_20]; struct tagSIZE *
0x180010670  mov     rdx, r12; struct IWICImagingFactory *
0x180010673  mov     rcx, rbx; struct IWICBitmapSource *
0x180010676  call    ?ResizeIWICBitmap@@YAJPEAUIWICBitmapSource@@PEAUIWICImagingFactory@@PEBUtagSIZE@@NNHPEAPEAU1@@Z; ResizeIWICBitmap(IWICBitmapSource *,IWICImagingFactory *,tagSIZE const *,double,double,int,IWICBitmapSource * *)
0x18001067b  mov     esi, eax
0x18001067d  test    eax, eax
0x18001067f  js      short loc_180010692
0x180010681  lea     rdx, [rbp+ppIDst]
0x180010685  lea     rcx, [rbp+pISrc]
0x180010689  call    ??4?$CComPtr@UIWICBitmapSource@@@ATL@@QEAAPEAUIWICBitmapSource@@AEBV01@@Z; ATL::CComPtr<IWICBitmapSource>::operator=(ATL::CComPtr<IWICBitmapSource> const &)
0x18001068e  mov     rbx, [rbp+pISrc]
0x180010692  lea     rcx, [rbp+ppIDst]
0x180010696  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001069b  test    rdi, rdi
0x18001069e  jz      short loc_180010718
0x1800106a0  mov     [rbp+ppIDst], 0
0x1800106a8  lea     r9, [rbp+ppIDst]; struct IWICBitmapSource **
0x1800106ac  mov     r8, rdi; struct IWICMetadataQueryReader *
0x1800106af  mov     rdx, rbx; struct IWICBitmapSource *
0x1800106b2  mov     rcx, r12; struct IWICImagingFactory *
0x1800106b5  call    ?WICCreateCachedOrientedBitmapSource@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAUIWICMetadataQueryReader@@PEAPEAU2@@Z; WICCreateCachedOrientedBitmapSource(IWICImagingFactory *,IWICBitmapSource *,IWICMetadataQueryReader *,IWICBitmapSource * *)
0x1800106ba  mov     esi, eax
0x1800106bc  test    eax, eax
0x1800106be  js      short loc_18001070F
0x1800106c0  mov     rdi, [rbp+ppIDst]
0x1800106c4  mov     rax, [rdi]
0x1800106c7  lea     r8, [rbp+arg_0]
0x1800106cb  lea     rdx, [rbp+var_38]
0x1800106cf  mov     rcx, rdi
0x1800106d2  mov     rax, [rax+18h]
0x1800106d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106db  mov     esi, eax
0x1800106dd  test    eax, eax
0x1800106df  js      short loc_18001070F
0x1800106e1  lea     r8, [rbp+var_28]; double *
0x1800106e5  lea     rdx, [rbp+var_20]; double *
0x1800106e9  mov     rcx, rdi; struct IWICBitmapSource *
0x1800106ec  call    ?GetResolutionDefaulted@@YAXPEAUIWICBitmapSource@@PEAN1@Z; GetResolutionDefaulted(IWICBitmapSource *,double *,double *)
0x1800106f1  lea     rdx, [rbp+var_28]; double *
0x1800106f5  lea     rcx, [rbp+var_20]; double *
0x1800106f9  call    ?NormalizeResolution@@YAXPEAN0@Z; NormalizeResolution(double *,double *)
0x1800106fe  lea     rdx, [rbp+ppIDst]
0x180010702  lea     rcx, [rbp+pISrc]
0x180010706  call    ??4?$CComPtr@UIWICBitmapSource@@@ATL@@QEAAPEAUIWICBitmapSource@@AEBV01@@Z; ATL::CComPtr<IWICBitmapSource>::operator=(ATL::CComPtr<IWICBitmapSource> const &)
0x18001070b  mov     rbx, [rbp+pISrc]
0x18001070f  lea     rcx, [rbp+ppIDst]
0x180010713  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010718  xor     edi, edi
0x18001071a  test    esi, esi
0x18001071c  js      loc_180010808
0x180010722  test    r15b, r15b
0x180010725  jnz     short loc_180010767
0x180010727  mov     [rbp+ppIDst], rdi
0x18001072b  lea     r8, [rbp+ppIDst]; ppIDst
0x18001072f  mov     rdx, rbx; pISrc
0x180010732  lea     rcx, GUID_WICPixelFormat32bppBGRA; dstFormat
0x180010739  call    cs:__imp_WICConvertBitmapSource
0x18001073f  mov     esi, eax
0x180010741  test    eax, eax
0x180010743  js      short loc_180010756
0x180010745  lea     rdx, [rbp+ppIDst]
0x180010749  lea     rcx, [rbp+pISrc]
0x18001074d  call    ??4?$CComPtr@UIWICBitmapSource@@@ATL@@QEAAPEAUIWICBitmapSource@@AEBV01@@Z; ATL::CComPtr<IWICBitmapSource>::operator=(ATL::CComPtr<IWICBitmapSource> const &)
0x180010752  mov     rbx, [rbp+pISrc]
0x180010756  lea     rcx, [rbp+ppIDst]
0x18001075a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001075f  test    esi, esi
0x180010761  js      loc_180010808
0x180010767  mov     [rbp+var_28], rdi
0x18001076b  mov     rax, [r14]
0x18001076e  lea     r8, [rbp+var_28]
0x180010772  lea     rdx, _GUID_3b16811b_6a43_4ec9_a813_3d930c13b940
0x180010779  mov     rcx, r14
0x18001077c  mov     rax, [rax]
0x18001077f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010784  test    eax, eax
0x180010786  js      short loc_1800107EB
0x180010788  mov     [rbp+var_20], rdi
0x18001078c  lea     r9, [rbp+var_20]; struct IWICColorTransform **
0x180010790  mov     r8, r12; struct IWICImagingFactory *
0x180010793  mov     rdx, rbx; struct IWICBitmapSource *
0x180010796  mov     rcx, [rbp+var_28]; struct IWICBitmapFrameDecode *
0x18001079a  call    ?GetsRGBTransformer@@YAJPEAUIWICBitmapFrameDecode@@PEAUIWICBitmapSource@@PEAUIWICImagingFactory@@PEAPEAUIWICColorTransform@@@Z; GetsRGBTransformer(IWICBitmapFrameDecode *,IWICBitmapSource *,IWICImagingFactory *,IWICColorTransform * *)
0x18001079f  test    eax, eax
0x1800107a1  js      short loc_1800107E1
0x1800107a3  mov     [rbp+ppIDst], rdi
0x1800107a7  mov     rcx, [rbp+var_20]
0x1800107ab  mov     rax, [rcx]
0x1800107ae  lea     r8, [rbp+ppIDst]
0x1800107b2  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x1800107b9  mov     rax, [rax]
0x1800107bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107c1  nop
0x1800107c2  test    eax, eax
0x1800107c4  js      short loc_1800107D7
0x1800107c6  lea     rdx, [rbp+ppIDst]
0x1800107ca  lea     rcx, [rbp+pISrc]
0x1800107ce  call    ??4?$CComPtr@UIWICBitmapSource@@@ATL@@QEAAPEAUIWICBitmapSource@@AEBV01@@Z; ATL::CComPtr<IWICBitmapSource>::operator=(ATL::CComPtr<IWICBitmapSource> const &)
0x1800107d3  mov     rbx, [rbp+pISrc]
0x1800107d7  lea     rcx, [rbp+ppIDst]
0x1800107db  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800107e0  nop
0x1800107e1  lea     rcx, [rbp+var_20]
0x1800107e5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800107ea  nop
0x1800107eb  lea     rcx, [rbp+var_28]
0x1800107ef  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800107f4  mov     rdx, r13; HBITMAP *
0x1800107f7  mov     rcx, rbx; struct IWICBitmapSource *
0x1800107fa  call    ?ConvertIWICBitmapSourceTo32bppHBITMAP@@YAJPEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; ConvertIWICBitmapSourceTo32bppHBITMAP(IWICBitmapSource *,HBITMAP__ * *)
0x1800107ff  mov     esi, eax
0x180010801  jmp     short loc_180010808
0x180010803  mov     esi, 8000FFFFh
0x180010808  lea     rcx, [rbp+pISrc]
0x18001080c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010811  mov     eax, esi
0x180010813  add     rsp, 78h
0x180010817  pop     r15
0x180010819  pop     r14
0x18001081b  pop     r13
0x18001081d  pop     r12
0x18001081f  pop     rdi
0x180010820  pop     rsi
0x180010821  pop     rbx
0x180010822  pop     rbp
0x180010823  retn
```
