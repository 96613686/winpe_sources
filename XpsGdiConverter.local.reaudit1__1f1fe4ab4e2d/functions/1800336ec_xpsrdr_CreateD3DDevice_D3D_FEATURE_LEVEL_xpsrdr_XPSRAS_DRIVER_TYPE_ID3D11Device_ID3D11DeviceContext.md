# xpsrdr::CreateD3DDevice(D3D_FEATURE_LEVEL *,xpsrdr::XPSRAS_DRIVER_TYPE *,ID3D11Device * *,ID3D11DeviceContext * *)

- ea: `0x1800336ec`
- end: `0x180033a6a`
- name: `?CreateD3DDevice@xpsrdr@@YAJPEAW4D3D_FEATURE_LEVEL@@PEAW4XPSRAS_DRIVER_TYPE@1@PEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@@Z`
- size: `894`
- prototype: `__int64 __fastcall(D3D_FEATURE_LEVEL *pFeatureLevel, enum D3D_FEATURE_LEVEL *, enum xpsrdr::XPSRAS_DRIVER_TYPE *, struct ID3D11Device **, struct ID3D11DeviceContext **)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003c42c`
- `0x18003d420`

## callees

- `0x180008830`
- `0x18000d7f8`
- `0x18000e15c`
- `0x18000e4c4`
- `0x180011b0c`
- `0x1800336ec`
- `0x180034a44`
- `0x180034d90`
- `0x180037278`
- `0x1800372e4`
- `0x18004a010`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x1800337e2`
- `d3d11!D3D11CreateDevice` at `0x180033877`
- `d3d11!D3D11CreateDevice` at `0x180033919`
- `d3d11!D3D11CreateDevice` at `0x1800339c5`
- `d3d11!D3D11CreateDevice` at `0x1800337e2`
- `d3d11!D3D11CreateDevice` at `0x180033877`
- `d3d11!D3D11CreateDevice` at `0x180033919`
- `d3d11!D3D11CreateDevice` at `0x1800339c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::CreateD3DDevice(
        D3D_FEATURE_LEVEL *pFeatureLevel,
        enum D3D_FEATURE_LEVEL *a2,
        xpsrdr **a3,
        struct ID3D11Device **a4)
{
  xpsrdr *v8; // rcx
  HRESULT v9; // ebx
  struct ID3D11Device *v10; // rdx
  HRESULT Device; // ebx
  HRESULT v12; // ebx
  struct ID3D11Device *v13; // rdx
  const char *v14; // r8
  int v15; // r9d
  const char *v16; // rdx
  xpsrdr *v17; // rcx
  int v18; // r8d
  HRESULT v19; // ebx
  int v20; // edx
  const char *v21; // r8
  int v22; // r9d
  xpsrdr *v23; // rcx
  struct ID3D11Device *v24; // rax
  int v26; // [rsp+50h] [rbp-69h] BYREF
  int v27; // [rsp+54h] [rbp-65h] BYREF
  ID3D11DeviceContext *ppImmediateContext; // [rsp+58h] [rbp-61h] BYREF
  int *v29; // [rsp+60h] [rbp-59h]
  xpsrdr **v30; // [rsp+68h] [rbp-51h]
  xpsrdr *v31[2]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v32[16]; // [rsp+80h] [rbp-39h] BYREF
  ID3D11DeviceContext *v33; // [rsp+90h] [rbp-29h] BYREF
  int *v34; // [rsp+98h] [rbp-21h]
  xpsrdr **v35; // [rsp+A0h] [rbp-19h]
  D3D_FEATURE_LEVEL ppDevice[2]; // [rsp+A8h] [rbp-11h] BYREF
  int *v37; // [rsp+B0h] [rbp-9h]
  xpsrdr **v38; // [rsp+B8h] [rbp-1h]
  D3D_FEATURE_LEVEL pFeatureLevels[4]; // [rsp+C0h] [rbp+7h] BYREF

  if ( pFeatureLevel && a2 && a3 && a4 )
  {
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v31);
    std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(v32);
    ppImmediateContext = 0;
    if ( xpsrdr::ShouldForceWarp(v8) )
    {
      v26 = 0;
      v29 = &v26;
      v30 = (xpsrdr **)v32;
      v33 = 0;
      v34 = &v26;
      v35 = v31;
      v19 = D3D11CreateDevice(
              0,
              D3D_DRIVER_TYPE_WARP,
              0,
              0x21u,
              0,
              0,
              7u,
              (ID3D11Device **)&v33,
              pFeatureLevel,
              &ppImmediateContext);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v33);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&ppImmediateContext);
      if ( v26 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, v20, v21, v22);
      if ( v19 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v19, v20, v21, v22);
    }
    else
    {
      v27 = 0;
      pFeatureLevels[0] = D3D_FEATURE_LEVEL_11_0;
      pFeatureLevels[1] = D3D_FEATURE_LEVEL_10_1;
      pFeatureLevels[2] = D3D_FEATURE_LEVEL_10_0;
      v29 = &v27;
      v30 = (xpsrdr **)v32;
      *(_QWORD *)ppDevice = 0;
      v37 = &v27;
      v38 = v31;
      v9 = D3D11CreateDevice(
             0,
             D3D_DRIVER_TYPE_HARDWARE,
             0,
             0x29u,
             pFeatureLevels,
             3u,
             7u,
             (ID3D11Device **)ppDevice,
             pFeatureLevel,
             &ppImmediateContext);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(ppDevice);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&ppImmediateContext);
      if ( v9 >= 0 && xpsrdr::IsTrulyHWDevice(v31[0], v10) && v31[0] )
      {
LABEL_16:
        *a2 = 1;
LABEL_22:
        v23 = v31[0];
        *a3 = v31[0];
        (*(void (__fastcall **)(xpsrdr *))(*(_QWORD *)v23 + 8LL))(v23);
        v24 = (struct ID3D11Device *)std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(v32);
        *a4 = v24;
        ((void (__fastcall *)(struct ID3D11Device *))v24->lpVtbl->AddRef)(v24);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v32);
        std::_Ptr_base<ID2D1RenderTarget>::_Decref(v31);
        return 0;
      }
      *(_QWORD *)ppDevice = 0;
      v37 = &v27;
      v38 = (xpsrdr **)v32;
      ppImmediateContext = 0;
      v29 = &v27;
      v30 = v31;
      Device = D3D11CreateDevice(
                 0,
                 D3D_DRIVER_TYPE_WARP,
                 0,
                 0x21u,
                 0,
                 0,
                 7u,
                 (ID3D11Device **)&ppImmediateContext,
                 pFeatureLevel,
                 (ID3D11DeviceContext **)ppDevice);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&ppImmediateContext);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(ppDevice);
      if ( Device < 0 )
      {
        ppDevice[0] = D3D_FEATURE_LEVEL_9_3;
        ppDevice[1] = D3D_FEATURE_LEVEL_9_2;
        LODWORD(v37) = 37120;
        v26 = 0;
        v33 = 0;
        v34 = &v26;
        v35 = (xpsrdr **)v32;
        ppImmediateContext = 0;
        v29 = &v26;
        v30 = v31;
        v12 = D3D11CreateDevice(
                0,
                D3D_DRIVER_TYPE_HARDWARE,
                0,
                0x29u,
                ppDevice,
                3u,
                7u,
                (ID3D11Device **)&ppImmediateContext,
                pFeatureLevel,
                &v33);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&ppImmediateContext);
        detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v33);
        if ( v26 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v26, (int)v13, v14, v15);
        if ( v12 < 0 )
          xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v12, (int)v13, v14, v15);
        if ( !xpsrdr::IsTrulyHWDevice(v31[0], v13) )
          xpsrdr::ThrowLogicException(v17, v16, v18);
        goto LABEL_16;
      }
    }
    *a2 = 2;
    goto LABEL_22;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800336ec  push    rbp
0x1800336ee  push    rbx
0x1800336ef  push    rsi
0x1800336f0  push    rdi
0x1800336f1  push    r13
0x1800336f3  push    r14
0x1800336f5  push    r15
0x1800336f7  lea     rbp, [rsp-27h]
0x1800336fc  sub     rsp, 0E0h
0x180033703  mov     rax, cs:__security_cookie
0x18003370a  xor     rax, rsp
0x18003370d  mov     [rbp+57h+var_40], rax
0x180033711  mov     r15, r9
0x180033714  mov     r14, r8
0x180033717  mov     rdi, rdx
0x18003371a  mov     rsi, rcx
0x18003371d  xor     r13d, r13d
0x180033720  test    rcx, rcx
0x180033723  jz      loc_180033A47
0x180033729  test    rdx, rdx
0x18003372c  jz      loc_180033A47
0x180033732  test    r8, r8
0x180033735  jz      loc_180033A47
0x18003373b  test    r9, r9
0x18003373e  jz      loc_180033A47
0x180033744  lea     rcx, [rbp+57h+var_A0]
0x180033748  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18003374d  nop
0x18003374e  lea     rcx, [rbp+57h+var_90]
0x180033752  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180033757  nop
0x180033758  call    ?ShouldForceWarp@xpsrdr@@YA_NXZ; xpsrdr::ShouldForceWarp(void)
0x18003375d  mov     [rbp+57h+var_B8], r13
0x180033761  xor     r8d, r8d; Software
0x180033764  xor     ecx, ecx; pAdapter
0x180033766  test    al, al
0x180033768  jnz     loc_18003396A
0x18003376e  mov     dword ptr [rbp+57h+var_C0+4], r13d
0x180033772  mov     [rbp+57h+var_50], 0B000h
0x180033779  mov     [rbp+57h+var_4C], 0A100h
0x180033780  mov     [rbp+57h+var_48], 0A000h
0x180033787  lea     rax, [rbp+57h+var_C0+4]
0x18003378b  mov     [rbp+57h+var_B0], rax
0x18003378f  lea     rax, [rbp+57h+var_90]
0x180033793  mov     [rbp+57h+var_A8], rax
0x180033797  mov     qword ptr [rbp+57h+var_68], r13
0x18003379b  lea     rax, [rbp+57h+var_C0+4]
0x18003379f  mov     [rbp+57h+var_60], rax
0x1800337a3  lea     rax, [rbp+57h+var_A0]
0x1800337a7  mov     [rbp+57h+var_58], rax
0x1800337ab  lea     rax, [rbp+57h+var_B8]
0x1800337af  mov     [rsp+110h+ppImmediateContext], rax; ppImmediateContext
0x1800337b4  mov     [rsp+110h+pFeatureLevel], rsi; pFeatureLevel
0x1800337b9  lea     rax, [rbp+57h+var_68]
0x1800337bd  mov     [rsp+110h+ppDevice], rax; ppDevice
0x1800337c2  mov     [rsp+110h+SDKVersion], 7; SDKVersion
0x1800337ca  mov     [rsp+110h+FeatureLevels], 3; FeatureLevels
0x1800337d2  lea     rax, [rbp+57h+var_50]
0x1800337d6  mov     [rsp+110h+pFeatureLevels], rax; pFeatureLevels
0x1800337db  lea     r9d, [r13+29h]; Flags
0x1800337df  lea     edx, [rcx+1]; DriverType
0x1800337e2  call    cs:__imp_D3D11CreateDevice
0x1800337e8  mov     ebx, eax
0x1800337ea  lea     rcx, [rbp+57h+var_68]
0x1800337ee  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800337f3  lea     rcx, [rbp+57h+var_B8]
0x1800337f7  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800337fc  test    ebx, ebx
0x1800337fe  js      short loc_180033817
0x180033800  mov     rcx, [rbp+57h+var_A0]; this
0x180033804  call    ?IsTrulyHWDevice@xpsrdr@@YA_NPEAUID3D11Device@@@Z; xpsrdr::IsTrulyHWDevice(ID3D11Device *)
0x180033809  test    al, al
0x18003380b  jz      short loc_180033817
0x18003380d  cmp     [rbp+57h+var_A0], r13
0x180033811  jnz     loc_18003395F
0x180033817  mov     qword ptr [rbp+57h+var_68], r13
0x18003381b  lea     rax, [rbp+57h+var_C0+4]
0x18003381f  mov     [rbp+57h+var_60], rax
0x180033823  lea     rax, [rbp+57h+var_90]
0x180033827  mov     [rbp+57h+var_58], rax
0x18003382b  mov     [rbp+57h+var_B8], r13
0x18003382f  lea     rax, [rbp+57h+var_C0+4]
0x180033833  mov     [rbp+57h+var_B0], rax
0x180033837  lea     rax, [rbp+57h+var_A0]
0x18003383b  mov     [rbp+57h+var_A8], rax
0x18003383f  lea     rax, [rbp+57h+var_68]
0x180033843  mov     [rsp+110h+ppImmediateContext], rax; ppImmediateContext
0x180033848  mov     [rsp+110h+pFeatureLevel], rsi; pFeatureLevel
0x18003384d  lea     rax, [rbp+57h+var_B8]
0x180033851  mov     [rsp+110h+ppDevice], rax; ppDevice
0x180033856  mov     [rsp+110h+SDKVersion], 7; SDKVersion
0x18003385e  mov     [rsp+110h+FeatureLevels], r13d; FeatureLevels
0x180033863  mov     [rsp+110h+pFeatureLevels], r13; pFeatureLevels
0x180033868  mov     r9d, 21h ; '!'; Flags
0x18003386e  xor     r8d, r8d; Software
0x180033871  lea     edx, [r9-1Ch]; DriverType
0x180033875  xor     ecx, ecx; pAdapter
0x180033877  call    cs:__imp_D3D11CreateDevice
0x18003387d  mov     ebx, eax
0x18003387f  lea     rcx, [rbp+57h+var_B8]
0x180033883  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180033888  lea     rcx, [rbp+57h+var_68]
0x18003388c  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180033891  test    ebx, ebx
0x180033893  jns     loc_1800339F8
0x180033899  mov     [rbp+57h+var_68], 9300h
0x1800338a0  mov     [rbp+57h+var_68+4], 9200h
0x1800338a7  mov     dword ptr [rbp+57h+var_60], 9100h
0x1800338ae  mov     dword ptr [rbp+57h+var_C0], r13d
0x1800338b2  mov     [rbp+57h+var_80], r13
0x1800338b6  lea     rax, [rbp+57h+var_C0]
0x1800338ba  mov     [rbp+57h+var_78], rax
0x1800338be  lea     rax, [rbp+57h+var_90]
0x1800338c2  mov     [rbp+57h+var_70], rax
0x1800338c6  mov     [rbp+57h+var_B8], r13
0x1800338ca  lea     rax, [rbp+57h+var_C0]
0x1800338ce  mov     [rbp+57h+var_B0], rax
0x1800338d2  lea     rax, [rbp+57h+var_A0]
0x1800338d6  mov     [rbp+57h+var_A8], rax
0x1800338da  lea     rax, [rbp+57h+var_80]
0x1800338de  mov     [rsp+110h+ppImmediateContext], rax; ppImmediateContext
0x1800338e3  mov     [rsp+110h+pFeatureLevel], rsi; pFeatureLevel
0x1800338e8  lea     rax, [rbp+57h+var_B8]
0x1800338ec  mov     [rsp+110h+ppDevice], rax; ppDevice
0x1800338f1  mov     [rsp+110h+SDKVersion], 7; SDKVersion
0x1800338f9  mov     [rsp+110h+FeatureLevels], 3; FeatureLevels
0x180033901  lea     rax, [rbp+57h+var_68]
0x180033905  mov     [rsp+110h+pFeatureLevels], rax; pFeatureLevels
0x18003390a  mov     r9d, 29h ; ')'; Flags
0x180033910  xor     r8d, r8d; Software
0x180033913  lea     edx, [r9-28h]; DriverType
0x180033917  xor     ecx, ecx; pAdapter
0x180033919  call    cs:__imp_D3D11CreateDevice
0x18003391f  mov     ebx, eax
0x180033921  lea     rcx, [rbp+57h+var_B8]
0x180033925  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x18003392a  lea     rcx, [rbp+57h+var_80]
0x18003392e  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x180033933  mov     ecx, dword ptr [rbp+57h+var_C0]; this
0x180033936  test    ecx, ecx
0x180033938  jns     short loc_180033940
0x18003393a  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x180033940  test    ebx, ebx
0x180033942  jns     short loc_18003394C
0x180033944  mov     ecx, ebx; this
0x180033946  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18003394c  mov     rcx, [rbp+57h+var_A0]; this
0x180033950  call    ?IsTrulyHWDevice@xpsrdr@@YA_NPEAUID3D11Device@@@Z; xpsrdr::IsTrulyHWDevice(ID3D11Device *)
0x180033955  test    al, al
0x180033957  jnz     short loc_18003395F
0x180033959  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x18003395f  mov     dword ptr [rdi], 1
0x180033965  jmp     loc_1800339FE
0x18003396a  mov     dword ptr [rbp+57h+var_C0], r13d
0x18003396e  lea     rax, [rbp+57h+var_C0]
0x180033972  mov     [rbp+57h+var_B0], rax
0x180033976  lea     rax, [rbp+57h+var_90]
0x18003397a  mov     [rbp+57h+var_A8], rax
0x18003397e  mov     [rbp+57h+var_80], r13
0x180033982  lea     rax, [rbp+57h+var_C0]
0x180033986  mov     [rbp+57h+var_78], rax
0x18003398a  lea     rax, [rbp+57h+var_A0]
0x18003398e  mov     [rbp+57h+var_70], rax
0x180033992  lea     rax, [rbp+57h+var_B8]
0x180033996  mov     [rsp+110h+ppImmediateContext], rax; ppImmediateContext
0x18003399b  mov     [rsp+110h+pFeatureLevel], rsi; pFeatureLevel
0x1800339a0  lea     rax, [rbp+57h+var_80]
0x1800339a4  mov     [rsp+110h+ppDevice], rax; ppDevice
0x1800339a9  mov     [rsp+110h+SDKVersion], 7; SDKVersion
0x1800339b1  mov     [rsp+110h+FeatureLevels], r13d; FeatureLevels
0x1800339b6  mov     [rsp+110h+pFeatureLevels], r13; pFeatureLevels
0x1800339bb  mov     r9d, 21h ; '!'; Flags
0x1800339c1  lea     edx, [r9-1Ch]; DriverType
0x1800339c5  call    cs:__imp_D3D11CreateDevice
0x1800339cb  mov     ebx, eax
0x1800339cd  lea     rcx, [rbp+57h+var_80]
0x1800339d1  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800339d6  lea     rcx, [rbp+57h+var_B8]
0x1800339da  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800339df  mov     ecx, dword ptr [rbp+57h+var_C0]; this
0x1800339e2  test    ecx, ecx
0x1800339e4  jns     short loc_1800339EC
0x1800339e6  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800339ec  test    ebx, ebx
0x1800339ee  jns     short loc_1800339F8
0x1800339f0  mov     ecx, ebx; this
0x1800339f2  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800339f8  mov     dword ptr [rdi], 2
0x1800339fe  mov     rcx, [rbp+57h+var_A0]
0x180033a02  mov     [r14], rcx
0x180033a05  mov     rax, [rcx]
0x180033a08  mov     rax, [rax+8]
0x180033a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a11  lea     rcx, [rbp+57h+var_90]
0x180033a15  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x180033a1a  mov     rdx, rax
0x180033a1d  mov     [r15], rax
0x180033a20  mov     rcx, [rax]
0x180033a23  mov     rax, [rcx+8]
0x180033a27  mov     rcx, rdx
0x180033a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a2f  nop
0x180033a30  lea     rcx, [rbp+57h+var_90]
0x180033a34  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180033a39  nop
0x180033a3a  lea     rcx, [rbp+57h+var_A0]
0x180033a3e  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180033a43  xor     eax, eax
0x180033a45  jmp     short loc_180033A4C
0x180033a47  mov     eax, 80004003h
0x180033a4c  mov     rcx, [rbp+57h+var_40]
0x180033a50  xor     rcx, rsp; StackCookie
0x180033a53  call    __security_check_cookie
0x180033a58  add     rsp, 0E0h
0x180033a5f  pop     r15
0x180033a61  pop     r14
0x180033a63  pop     r13
0x180033a65  pop     rdi
0x180033a66  pop     rsi
0x180033a67  pop     rbx
0x180033a68  pop     rbp
0x180033a69  retn
```
