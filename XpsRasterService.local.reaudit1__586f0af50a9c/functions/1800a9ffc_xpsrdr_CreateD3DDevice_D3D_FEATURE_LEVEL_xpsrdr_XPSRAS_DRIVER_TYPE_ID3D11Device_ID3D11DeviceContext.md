# xpsrdr::CreateD3DDevice(D3D_FEATURE_LEVEL *,xpsrdr::XPSRAS_DRIVER_TYPE *,ID3D11Device * *,ID3D11DeviceContext * *)

- ea: `0x1800a9ffc`
- end: `0x1800aa372`
- name: `?CreateD3DDevice@xpsrdr@@YAJPEAW4D3D_FEATURE_LEVEL@@PEAW4XPSRAS_DRIVER_TYPE@1@PEAPEAUID3D11Device@@PEAPEAUID3D11DeviceContext@@@Z`
- size: `886`
- prototype: `__int64 __fastcall(D3D_FEATURE_LEVEL *pFeatureLevel, enum D3D_FEATURE_LEVEL *, enum xpsrdr::XPSRAS_DRIVER_TYPE *, struct ID3D11Device **, struct ID3D11DeviceContext **)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800a4190`
- `0x1800ac0f4`
- `0x1800ad308`

## callees

- `0x180003180`
- `0x1800a2c1c`
- `0x1800a5230`
- `0x1800a9ffc`
- `0x1800ab338`
- `0x1800ab70c`
- `0x1800b20e8`
- `0x1800b2154`
- `0x1800c3010`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x1800aa0eb`
- `d3d11!D3D11CreateDevice` at `0x1800aa180`
- `d3d11!D3D11CreateDevice` at `0x1800aa222`
- `d3d11!D3D11CreateDevice` at `0x1800aa2ce`
- `d3d11!D3D11CreateDevice` at `0x1800aa0eb`
- `d3d11!D3D11CreateDevice` at `0x1800aa180`
- `d3d11!D3D11CreateDevice` at `0x1800aa222`
- `d3d11!D3D11CreateDevice` at `0x1800aa2ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall xpsrdr::CreateD3DDevice(
        D3D_FEATURE_LEVEL *pFeatureLevel,
        enum D3D_FEATURE_LEVEL *a2,
        std::_Ref_count_base **a3,
        struct ID3D11Device **a4)
{
  HRESULT v8; // ebx
  struct ID3D11Device *v9; // rdx
  HRESULT Device; // ebx
  HRESULT v11; // ebx
  struct ID3D11Device *v12; // rdx
  const char *v13; // r8
  int v14; // r9d
  const char *v15; // rdx
  xpsrdr *v16; // rcx
  int v17; // r8d
  HRESULT v18; // ebx
  int v19; // edx
  const char *v20; // r8
  int v21; // r9d
  std::_Ref_count_base *v22; // rcx
  std::_Ref_count_base *v23; // rcx
  int v25; // [rsp+50h] [rbp-69h] BYREF
  int v26; // [rsp+54h] [rbp-65h] BYREF
  ID3D11DeviceContext *ppImmediateContext; // [rsp+58h] [rbp-61h] BYREF
  int *v28; // [rsp+60h] [rbp-59h]
  std::_Ref_count_base **v29; // [rsp+68h] [rbp-51h]
  std::_Ref_count_base *v30[2]; // [rsp+70h] [rbp-49h] BYREF
  std::_Ref_count_base *v31[2]; // [rsp+80h] [rbp-39h] BYREF
  ID3D11DeviceContext *v32; // [rsp+90h] [rbp-29h] BYREF
  int *v33; // [rsp+98h] [rbp-21h]
  std::_Ref_count_base **v34; // [rsp+A0h] [rbp-19h]
  D3D_FEATURE_LEVEL ppDevice[2]; // [rsp+A8h] [rbp-11h] BYREF
  int *v36; // [rsp+B0h] [rbp-9h]
  std::_Ref_count_base **v37; // [rsp+B8h] [rbp-1h]
  D3D_FEATURE_LEVEL pFeatureLevels[4]; // [rsp+C0h] [rbp+7h] BYREF

  if ( !pFeatureLevel || !a2 || !a3 || !a4 )
    return 2147500035LL;
  *(_OWORD *)v30 = 0;
  *(_OWORD *)v31 = 0;
  ppImmediateContext = 0;
  if ( xpsrdr::ShouldForceWarp((xpsrdr *)pFeatureLevel) )
  {
    v25 = 0;
    v28 = &v25;
    v29 = v31;
    v32 = 0;
    v33 = &v25;
    v34 = v30;
    v18 = D3D11CreateDevice(
            0,
            D3D_DRIVER_TYPE_WARP,
            0,
            0x21u,
            0,
            0,
            7u,
            (ID3D11Device **)&v32,
            pFeatureLevel,
            &ppImmediateContext);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v32);
    detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&ppImmediateContext);
    if ( v25 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v25, v19, v20, v21);
    if ( v18 < 0 )
      xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v18, v19, v20, v21);
    goto LABEL_21;
  }
  v26 = 0;
  pFeatureLevels[0] = D3D_FEATURE_LEVEL_11_0;
  pFeatureLevels[1] = D3D_FEATURE_LEVEL_10_1;
  pFeatureLevels[2] = D3D_FEATURE_LEVEL_10_0;
  v28 = &v26;
  v29 = v31;
  *(_QWORD *)ppDevice = 0;
  v36 = &v26;
  v37 = v30;
  v8 = D3D11CreateDevice(
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
  if ( v8 < 0 || !xpsrdr::IsTrulyHWDevice(v30[0], v9) || !v30[0] )
  {
    *(_QWORD *)ppDevice = 0;
    v36 = &v26;
    v37 = v31;
    ppImmediateContext = 0;
    v28 = &v26;
    v29 = v30;
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
      LODWORD(v36) = 37120;
      v25 = 0;
      v32 = 0;
      v33 = &v25;
      v34 = v31;
      ppImmediateContext = 0;
      v28 = &v25;
      v29 = v30;
      v11 = D3D11CreateDevice(
              0,
              D3D_DRIVER_TYPE_HARDWARE,
              0,
              0x29u,
              ppDevice,
              3u,
              7u,
              (ID3D11Device **)&ppImmediateContext,
              pFeatureLevel,
              &v32);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&ppImmediateContext);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(&v32);
      if ( v25 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v25, (int)v12, v13, v14);
      if ( v11 < 0 )
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v11, (int)v12, v13, v14);
      if ( !xpsrdr::IsTrulyHWDevice(v30[0], v12) )
        xpsrdr::ThrowLogicException(v16, v15, v17);
      goto LABEL_16;
    }
LABEL_21:
    *a2 = 2;
    goto LABEL_22;
  }
LABEL_16:
  *a2 = 1;
LABEL_22:
  v22 = v30[0];
  *a3 = v30[0];
  (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v22 + 8LL))(v22);
  v23 = v31[0];
  *a4 = (struct ID3D11Device *)v31[0];
  (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v23 + 8LL))(v23);
  if ( v31[1] )
    std::_Ref_count_base::_Decref(v31[1]);
  if ( v30[1] )
    std::_Ref_count_base::_Decref(v30[1]);
  return 0;
}

```

## disassembly

```asm
0x1800a9ffc  push    rbp
0x1800a9ffe  push    rbx
0x1800a9fff  push    rsi
0x1800aa000  push    rdi
0x1800aa001  push    r13
0x1800aa003  push    r14
0x1800aa005  push    r15
0x1800aa007  lea     rbp, [rsp-27h]
0x1800aa00c  sub     rsp, 0E0h
0x1800aa013  mov     rax, cs:__security_cookie
0x1800aa01a  xor     rax, rsp
0x1800aa01d  mov     [rbp+57h+var_40], rax
0x1800aa021  mov     r15, r9
0x1800aa024  mov     r14, r8
0x1800aa027  mov     rdi, rdx
0x1800aa02a  mov     rsi, rcx
0x1800aa02d  xor     r13d, r13d
0x1800aa030  test    rcx, rcx
0x1800aa033  jz      loc_1800AA34F
0x1800aa039  test    rdx, rdx
0x1800aa03c  jz      loc_1800AA34F
0x1800aa042  test    r8, r8
0x1800aa045  jz      loc_1800AA34F
0x1800aa04b  test    r9, r9
0x1800aa04e  jz      loc_1800AA34F
0x1800aa054  xorps   xmm0, xmm0
0x1800aa057  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x1800aa05c  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x1800aa061  call    ?ShouldForceWarp@xpsrdr@@YA_NXZ; xpsrdr::ShouldForceWarp(void)
0x1800aa066  mov     [rbp+57h+var_B8], r13
0x1800aa06a  xor     r8d, r8d; Software
0x1800aa06d  xor     ecx, ecx; pAdapter
0x1800aa06f  test    al, al
0x1800aa071  jnz     loc_1800AA273
0x1800aa077  mov     dword ptr [rbp+57h+var_C0+4], r13d
0x1800aa07b  mov     [rbp+57h+var_50], 0B000h
0x1800aa082  mov     [rbp+57h+var_4C], 0A100h
0x1800aa089  mov     [rbp+57h+var_48], 0A000h
0x1800aa090  lea     rax, [rbp+57h+var_C0+4]
0x1800aa094  mov     [rbp+57h+var_B0], rax
0x1800aa098  lea     rax, [rbp+57h+var_90]
0x1800aa09c  mov     [rbp+57h+var_A8], rax
0x1800aa0a0  mov     qword ptr [rbp+57h+var_68], r13
0x1800aa0a4  lea     rax, [rbp+57h+var_C0+4]
0x1800aa0a8  mov     [rbp+57h+var_60], rax
0x1800aa0ac  lea     rax, [rbp+57h+var_A0]
0x1800aa0b0  mov     [rbp+57h+var_58], rax
0x1800aa0b4  lea     rax, [rbp+57h+var_B8]
0x1800aa0b8  mov     [rsp+110h+ppImmediateContext], rax; ppImmediateContext
0x1800aa0bd  mov     [rsp+110h+pFeatureLevel], rsi; pFeatureLevel
0x1800aa0c2  lea     rax, [rbp+57h+var_68]
0x1800aa0c6  mov     [rsp+110h+ppDevice], rax; ppDevice
0x1800aa0cb  mov     [rsp+110h+SDKVersion], 7; SDKVersion
0x1800aa0d3  mov     [rsp+110h+FeatureLevels], 3; FeatureLevels
0x1800aa0db  lea     rax, [rbp+57h+var_50]
0x1800aa0df  mov     [rsp+110h+pFeatureLevels], rax; pFeatureLevels
0x1800aa0e4  lea     r9d, [r13+29h]; Flags
0x1800aa0e8  lea     edx, [rcx+1]; DriverType
0x1800aa0eb  call    cs:__imp_D3D11CreateDevice
0x1800aa0f1  mov     ebx, eax
0x1800aa0f3  lea     rcx, [rbp+57h+var_68]
0x1800aa0f7  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa0fc  lea     rcx, [rbp+57h+var_B8]
0x1800aa100  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa105  test    ebx, ebx
0x1800aa107  js      short loc_1800AA120
0x1800aa109  mov     rcx, [rbp+57h+var_A0]; this
0x1800aa10d  call    ?IsTrulyHWDevice@xpsrdr@@YA_NPEAUID3D11Device@@@Z; xpsrdr::IsTrulyHWDevice(ID3D11Device *)
0x1800aa112  test    al, al
0x1800aa114  jz      short loc_1800AA120
0x1800aa116  cmp     [rbp+57h+var_A0], r13
0x1800aa11a  jnz     loc_1800AA268
0x1800aa120  mov     qword ptr [rbp+57h+var_68], r13
0x1800aa124  lea     rax, [rbp+57h+var_C0+4]
0x1800aa128  mov     [rbp+57h+var_60], rax
0x1800aa12c  lea     rax, [rbp+57h+var_90]
0x1800aa130  mov     [rbp+57h+var_58], rax
0x1800aa134  mov     [rbp+57h+var_B8], r13
0x1800aa138  lea     rax, [rbp+57h+var_C0+4]
0x1800aa13c  mov     [rbp+57h+var_B0], rax
0x1800aa140  lea     rax, [rbp+57h+var_A0]
0x1800aa144  mov     [rbp+57h+var_A8], rax
0x1800aa148  lea     rax, [rbp+57h+var_68]
0x1800aa14c  mov     [rsp+110h+ppImmediateContext], rax; ppImmediateContext
0x1800aa151  mov     [rsp+110h+pFeatureLevel], rsi; pFeatureLevel
0x1800aa156  lea     rax, [rbp+57h+var_B8]
0x1800aa15a  mov     [rsp+110h+ppDevice], rax; ppDevice
0x1800aa15f  mov     [rsp+110h+SDKVersion], 7; SDKVersion
0x1800aa167  mov     [rsp+110h+FeatureLevels], r13d; FeatureLevels
0x1800aa16c  mov     [rsp+110h+pFeatureLevels], r13; pFeatureLevels
0x1800aa171  mov     r9d, 21h ; '!'; Flags
0x1800aa177  xor     r8d, r8d; Software
0x1800aa17a  lea     edx, [r9-1Ch]; DriverType
0x1800aa17e  xor     ecx, ecx; pAdapter
0x1800aa180  call    cs:__imp_D3D11CreateDevice
0x1800aa186  mov     ebx, eax
0x1800aa188  lea     rcx, [rbp+57h+var_B8]
0x1800aa18c  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa191  lea     rcx, [rbp+57h+var_68]
0x1800aa195  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa19a  test    ebx, ebx
0x1800aa19c  jns     loc_1800AA301
0x1800aa1a2  mov     [rbp+57h+var_68], 9300h
0x1800aa1a9  mov     [rbp+57h+var_68+4], 9200h
0x1800aa1b0  mov     dword ptr [rbp+57h+var_60], 9100h
0x1800aa1b7  mov     dword ptr [rbp+57h+var_C0], r13d
0x1800aa1bb  mov     [rbp+57h+var_80], r13
0x1800aa1bf  lea     rax, [rbp+57h+var_C0]
0x1800aa1c3  mov     [rbp+57h+var_78], rax
0x1800aa1c7  lea     rax, [rbp+57h+var_90]
0x1800aa1cb  mov     [rbp+57h+var_70], rax
0x1800aa1cf  mov     [rbp+57h+var_B8], r13
0x1800aa1d3  lea     rax, [rbp+57h+var_C0]
0x1800aa1d7  mov     [rbp+57h+var_B0], rax
0x1800aa1db  lea     rax, [rbp+57h+var_A0]
0x1800aa1df  mov     [rbp+57h+var_A8], rax
0x1800aa1e3  lea     rax, [rbp+57h+var_80]
0x1800aa1e7  mov     [rsp+110h+ppImmediateContext], rax; ppImmediateContext
0x1800aa1ec  mov     [rsp+110h+pFeatureLevel], rsi; pFeatureLevel
0x1800aa1f1  lea     rax, [rbp+57h+var_B8]
0x1800aa1f5  mov     [rsp+110h+ppDevice], rax; ppDevice
0x1800aa1fa  mov     [rsp+110h+SDKVersion], 7; SDKVersion
0x1800aa202  mov     [rsp+110h+FeatureLevels], 3; FeatureLevels
0x1800aa20a  lea     rax, [rbp+57h+var_68]
0x1800aa20e  mov     [rsp+110h+pFeatureLevels], rax; pFeatureLevels
0x1800aa213  mov     r9d, 29h ; ')'; Flags
0x1800aa219  xor     r8d, r8d; Software
0x1800aa21c  lea     edx, [r9-28h]; DriverType
0x1800aa220  xor     ecx, ecx; pAdapter
0x1800aa222  call    cs:__imp_D3D11CreateDevice
0x1800aa228  mov     ebx, eax
0x1800aa22a  lea     rcx, [rbp+57h+var_B8]
0x1800aa22e  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa233  lea     rcx, [rbp+57h+var_80]
0x1800aa237  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa23c  mov     ecx, dword ptr [rbp+57h+var_C0]; this
0x1800aa23f  test    ecx, ecx
0x1800aa241  jns     short loc_1800AA249
0x1800aa243  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa249  test    ebx, ebx
0x1800aa24b  jns     short loc_1800AA255
0x1800aa24d  mov     ecx, ebx; this
0x1800aa24f  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa255  mov     rcx, [rbp+57h+var_A0]; this
0x1800aa259  call    ?IsTrulyHWDevice@xpsrdr@@YA_NPEAUID3D11Device@@@Z; xpsrdr::IsTrulyHWDevice(ID3D11Device *)
0x1800aa25e  test    al, al
0x1800aa260  jnz     short loc_1800AA268
0x1800aa262  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x1800aa268  mov     dword ptr [rdi], 1
0x1800aa26e  jmp     loc_1800AA307
0x1800aa273  mov     dword ptr [rbp+57h+var_C0], r13d
0x1800aa277  lea     rax, [rbp+57h+var_C0]
0x1800aa27b  mov     [rbp+57h+var_B0], rax
0x1800aa27f  lea     rax, [rbp+57h+var_90]
0x1800aa283  mov     [rbp+57h+var_A8], rax
0x1800aa287  mov     [rbp+57h+var_80], r13
0x1800aa28b  lea     rax, [rbp+57h+var_C0]
0x1800aa28f  mov     [rbp+57h+var_78], rax
0x1800aa293  lea     rax, [rbp+57h+var_A0]
0x1800aa297  mov     [rbp+57h+var_70], rax
0x1800aa29b  lea     rax, [rbp+57h+var_B8]
0x1800aa29f  mov     [rsp+110h+ppImmediateContext], rax; ppImmediateContext
0x1800aa2a4  mov     [rsp+110h+pFeatureLevel], rsi; pFeatureLevel
0x1800aa2a9  lea     rax, [rbp+57h+var_80]
0x1800aa2ad  mov     [rsp+110h+ppDevice], rax; ppDevice
0x1800aa2b2  mov     [rsp+110h+SDKVersion], 7; SDKVersion
0x1800aa2ba  mov     [rsp+110h+FeatureLevels], r13d; FeatureLevels
0x1800aa2bf  mov     [rsp+110h+pFeatureLevels], r13; pFeatureLevels
0x1800aa2c4  mov     r9d, 21h ; '!'; Flags
0x1800aa2ca  lea     edx, [r9-1Ch]; DriverType
0x1800aa2ce  call    cs:__imp_D3D11CreateDevice
0x1800aa2d4  mov     ebx, eax
0x1800aa2d6  lea     rcx, [rbp+57h+var_80]
0x1800aa2da  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa2df  lea     rcx, [rbp+57h+var_B8]
0x1800aa2e3  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800aa2e8  mov     ecx, dword ptr [rbp+57h+var_C0]; this
0x1800aa2eb  test    ecx, ecx
0x1800aa2ed  jns     short loc_1800AA2F5
0x1800aa2ef  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa2f5  test    ebx, ebx
0x1800aa2f7  jns     short loc_1800AA301
0x1800aa2f9  mov     ecx, ebx; this
0x1800aa2fb  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800aa301  mov     dword ptr [rdi], 2
0x1800aa307  mov     rcx, [rbp+57h+var_A0]
0x1800aa30b  mov     [r14], rcx
0x1800aa30e  mov     rax, [rcx]
0x1800aa311  mov     rax, [rax+8]
0x1800aa315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa31a  mov     rcx, [rbp+57h+var_90]
0x1800aa31e  mov     [r15], rcx
0x1800aa321  mov     rax, [rcx]
0x1800aa324  mov     rax, [rax+8]
0x1800aa328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa32d  nop
0x1800aa32e  mov     rcx, [rbp+57h+var_90+8]; this
0x1800aa332  test    rcx, rcx
0x1800aa335  jz      short loc_1800AA33D
0x1800aa337  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800aa33c  nop
0x1800aa33d  mov     rcx, [rbp+57h+var_A0+8]; this
0x1800aa341  test    rcx, rcx
0x1800aa344  jz      short loc_1800AA34B
0x1800aa346  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800aa34b  xor     eax, eax
0x1800aa34d  jmp     short loc_1800AA354
0x1800aa34f  mov     eax, 80004003h
0x1800aa354  mov     rcx, [rbp+57h+var_40]
0x1800aa358  xor     rcx, rsp; StackCookie
0x1800aa35b  call    __security_check_cookie
0x1800aa360  add     rsp, 0E0h
0x1800aa367  pop     r15
0x1800aa369  pop     r14
0x1800aa36b  pop     r13
0x1800aa36d  pop     rdi
0x1800aa36e  pop     rsi
0x1800aa36f  pop     rbx
0x1800aa370  pop     rbp
0x1800aa371  retn
```
