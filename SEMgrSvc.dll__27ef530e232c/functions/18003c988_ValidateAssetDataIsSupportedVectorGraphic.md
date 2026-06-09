# ValidateAssetDataIsSupportedVectorGraphic

- ea: `0x18003c988`
- end: `0x18003ce6e`
- name: `ValidateAssetDataIsSupportedVectorGraphic`
- size: `1254`
- prototype: `__int64 __fastcall(BYTE *pInit, UINT cbInit)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003c614`

## callees

- `0x18000c964`
- `0x18000f740`
- `0x18003c988`
- `0x18009d010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18003cca2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18003cca2`
- `d2d1!__imp_D2D1CreateFactory` at `0x18003caaf`
- `d2d1!__imp_D2D1CreateFactory` at `0x18003caaf`
- `d3d11!D3D11CreateDevice` at `0x18003c9de`
- `d3d11!D3D11CreateDevice` at `0x18003c9de`

## string_xrefs

- `0x18003c9f1`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingvalidation.cpp`
- `0x18003ca4e`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingvalidation.cpp`
- `0x18003cac2`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingvalidation.cpp`
- `0x18003cb57`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingvalidation.cpp`
- `0x18003cc04`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingvalidation.cpp`
- `0x18003ccc4`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingvalidation.cpp`
- `0x18003cd96`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingvalidation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall ValidateAssetDataIsSupportedVectorGraphic(BYTE *pInit, UINT cbInit, bool *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  ID3D11Device *v8; // rcx
  int v10; // eax
  __int64 v11; // rcx
  ID3D11Device *v12; // rcx
  HRESULT v13; // eax
  void *v14; // rcx
  __int64 v15; // rcx
  ID3D11Device *v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  void *v19; // rcx
  __int64 v20; // rcx
  ID3D11Device *v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  void *v25; // rcx
  __int64 v26; // rcx
  ID3D11Device *v27; // rcx
  IStream *v28; // rax
  IStream *v29; // rdi
  __int64 v30; // rcx
  __int64 v31; // rcx
  void *v32; // rcx
  __int64 v33; // rcx
  ID3D11Device *v34; // rcx
  int v35; // eax
  int v36; // ebx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  void *v40; // rcx
  __int64 v41; // rcx
  ID3D11Device *v42; // rcx
  int pFeatureLevels; // [rsp+20h] [rbp-49h]
  ID3D11Device *ppDevice; // [rsp+50h] [rbp-19h] BYREF
  __int64 v45; // [rsp+58h] [rbp-11h] BYREF
  void *ppIFactory; // [rsp+60h] [rbp-9h] BYREF
  __int64 v47; // [rsp+68h] [rbp-1h] BYREF
  __int64 v48; // [rsp+70h] [rbp+7h] BYREF
  _QWORD v49[9]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  D2D1_FACTORY_OPTIONS pFactoryOptions; // [rsp+E8h] [rbp+7Fh] BYREF

  ppDevice = 0;
  v6 = D3D11CreateDevice(0, D3D_DRIVER_TYPE_WARP, 0, 0x20u, 0, 0, 7u, &ppDevice, 0, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingvalidation.cpp",
      (const char *)(unsigned int)v6,
      pFeatureLevels);
    v8 = ppDevice;
    if ( ppDevice )
    {
      ppDevice = 0;
      ((void (__fastcall *)(ID3D11Device *))v8->lpVtbl->Release)(v8);
    }
    return v7;
  }
  v45 = 0;
  v10 = ((__int64 (__fastcall *)(ID3D11Device *, GUID *, __int64 *))ppDevice->lpVtbl->QueryInterface)(
          ppDevice,
          &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c,
          &v45);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingvalidation.cpp",
      (const char *)(unsigned int)v10,
      pFeatureLevels);
    v11 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = ppDevice;
    if ( ppDevice )
    {
      ppDevice = 0;
      ((void (__fastcall *)(ID3D11Device *))v12->lpVtbl->Release)(v12);
    }
    return v7;
  }
  pFactoryOptions.debugLevel = D2D1_DEBUG_LEVEL_NONE;
  ppIFactory = 0;
  v13 = D2D1CreateFactory(
          D2D1_FACTORY_TYPE_SINGLE_THREADED,
          &GUID_bdc2bdd3_b96c_4de6_bdf7_99d4745454de,
          &pFactoryOptions,
          &ppIFactory);
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingvalidation.cpp",
      (const char *)(unsigned int)v13,
      pFeatureLevels);
    v14 = ppIFactory;
    if ( ppIFactory )
    {
      ppIFactory = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = ppDevice;
    if ( ppDevice )
    {
      ppDevice = 0;
      ((void (__fastcall *)(ID3D11Device *))v16->lpVtbl->Release)(v16);
    }
    return v7;
  }
  v47 = 0;
  v17 = (*(__int64 (__fastcall **)(void *, __int64, __int64 *))(*(_QWORD *)ppIFactory + 256LL))(ppIFactory, v45, &v47);
  v7 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingvalidation.cpp",
      (const char *)(unsigned int)v17,
      pFeatureLevels);
    v18 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = ppIFactory;
    if ( ppIFactory )
    {
      ppIFactory = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = ppDevice;
    if ( ppDevice )
    {
      ppDevice = 0;
      ((void (__fastcall *)(ID3D11Device *))v21->lpVtbl->Release)(v21);
    }
    return v7;
  }
  v48 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v47 + 160LL))(v47, 0, &v48);
  v7 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingvalidation.cpp",
      (const char *)(unsigned int)v22,
      pFeatureLevels);
    v23 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = ppIFactory;
    if ( ppIFactory )
    {
      ppIFactory = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = ppDevice;
    if ( ppDevice )
    {
      ppDevice = 0;
      ((void (__fastcall *)(ID3D11Device *))v27->lpVtbl->Release)(v27);
    }
    return v7;
  }
  v28 = SHCreateMemStream(pInit, cbInit);
  v29 = v28;
  v49[1] = v28;
  if ( !v28 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingvalidation.cpp",
      (const char *)0x8007000ELL,
      pFeatureLevels);
    v30 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = ppIFactory;
    if ( ppIFactory )
    {
      ppIFactory = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = ppDevice;
    if ( ppDevice )
    {
      ppDevice = 0;
      ((void (__fastcall *)(ID3D11Device *))v34->lpVtbl->Release)(v34);
    }
    return v7;
  }
  v49[0] = 0;
  v35 = (*(__int64 (__fastcall **)(__int64, IStream *, unsigned __int64, _QWORD *))(*(_QWORD *)v48 + 920LL))(
          v48,
          v28,
          _mm_unpacklo_ps((__m128)LODWORD(FLOAT_1_0), (__m128)LODWORD(FLOAT_1_0)).m128_u64[0],
          v49);
  v36 = v35;
  if ( v35 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingvalidation.cpp",
      (const char *)(unsigned int)v35,
      pFeatureLevels);
  *a3 = v36 >= 0;
  v37 = v49[0];
  if ( v49[0] )
  {
    v49[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  (*(void (__fastcall **)(IStream *))(*(_QWORD *)v29 + 16LL))(v29);
  v38 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v39 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v40 = ppIFactory;
  if ( ppIFactory )
  {
    ppIFactory = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = ppDevice;
  if ( ppDevice )
  {
    ppDevice = 0;
    ((void (__fastcall *)(ID3D11Device *))v42->lpVtbl->Release)(v42);
  }
  return 0;
}

```

## disassembly

```asm
0x18003c988  push    rbp
0x18003c98a  push    rbx
0x18003c98b  push    rsi
0x18003c98c  push    rdi
0x18003c98d  push    r14
0x18003c98f  push    r15
0x18003c991  lea     rbp, [rsp-2Fh]
0x18003c996  sub     rsp, 98h
0x18003c99d  mov     r14, r8
0x18003c9a0  mov     edi, edx
0x18003c9a2  mov     rsi, rcx
0x18003c9a5  xor     r15d, r15d
0x18003c9a8  mov     [rbp+57h+var_70], r15
0x18003c9ac  mov     [rsp+0C0h+ppImmediateContext], r15; ppImmediateContext
0x18003c9b1  mov     [rsp+0C0h+pFeatureLevel], r15; pFeatureLevel
0x18003c9b6  lea     rax, [rbp+57h+var_70]
0x18003c9ba  mov     [rsp+0C0h+ppDevice], rax; ppDevice
0x18003c9bf  mov     [rsp+0C0h+SDKVersion], 7; SDKVersion
0x18003c9c7  mov     [rsp+0C0h+FeatureLevels], r15d; FeatureLevels
0x18003c9cc  mov     [rsp+0C0h+pFeatureLevels], r15; int
0x18003c9d1  lea     r9d, [r15+20h]; Flags
0x18003c9d5  xor     r8d, r8d; Software
0x18003c9d8  lea     edx, [r15+5]; DriverType
0x18003c9dc  xor     ecx, ecx; pAdapter
0x18003c9de  call    cs:__imp_D3D11CreateDevice
0x18003c9e4  mov     ebx, eax
0x18003c9e6  test    eax, eax
0x18003c9e8  jns     short loc_18003CA23
0x18003c9ea  mov     rcx, [rbp+5Fh]; this
0x18003c9ee  mov     r9d, eax; char *
0x18003c9f1  lea     r8, aOnecoreuapDsNf_59; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003c9f8  lea     edx, [r15+2Bh]; void *
0x18003c9fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ca01  nop
0x18003ca02  mov     rcx, [rbp+57h+var_70]
0x18003ca06  test    rcx, rcx
0x18003ca09  jz      short loc_18003CA1C
0x18003ca0b  mov     [rbp+57h+var_70], r15
0x18003ca0f  mov     rax, [rcx]
0x18003ca12  mov     rax, [rax+10h]
0x18003ca16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca1b  nop
0x18003ca1c  mov     eax, ebx
0x18003ca1e  jmp     loc_18003CE5E
0x18003ca23  mov     [rbp+57h+var_68], r15
0x18003ca27  mov     rcx, [rbp+57h+var_70]
0x18003ca2b  mov     rax, [rcx]
0x18003ca2e  lea     r8, [rbp+57h+var_68]
0x18003ca32  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x18003ca39  mov     rax, [rax]
0x18003ca3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca41  mov     ebx, eax
0x18003ca43  test    eax, eax
0x18003ca45  jns     short loc_18003CA96
0x18003ca47  mov     rcx, [rbp+5Fh]; this
0x18003ca4b  mov     r9d, eax; char *
0x18003ca4e  lea     r8, aOnecoreuapDsNf_59; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003ca55  mov     edx, 2Eh ; '.'; void *
0x18003ca5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ca5f  nop
0x18003ca60  mov     rcx, [rbp+57h+var_68]
0x18003ca64  test    rcx, rcx
0x18003ca67  jz      short loc_18003CA7A
0x18003ca69  mov     [rbp+57h+var_68], r15
0x18003ca6d  mov     rax, [rcx]
0x18003ca70  mov     rax, [rax+10h]
0x18003ca74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca79  nop
0x18003ca7a  mov     rcx, [rbp+57h+var_70]
0x18003ca7e  test    rcx, rcx
0x18003ca81  jz      short loc_18003CA94
0x18003ca83  mov     [rbp+57h+var_70], r15
0x18003ca87  mov     rax, [rcx]
0x18003ca8a  mov     rax, [rax+10h]
0x18003ca8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca93  nop
0x18003ca94  jmp     short loc_18003CA1C
0x18003ca96  mov     [rbp+57h+pFactoryOptions.debugLevel], r15d
0x18003ca9a  mov     [rbp+57h+ppIFactory], r15
0x18003ca9e  lea     r9, [rbp+57h+ppIFactory]; ppIFactory
0x18003caa2  lea     r8, [rbp+57h+pFactoryOptions]; pFactoryOptions
0x18003caa6  lea     rdx, _GUID_bdc2bdd3_b96c_4de6_bdf7_99d4745454de; riid
0x18003caad  xor     ecx, ecx; factoryType
0x18003caaf  call    cs:__imp_D2D1CreateFactory
0x18003cab5  mov     ebx, eax
0x18003cab7  test    eax, eax
0x18003cab9  jns     short loc_18003CB27
0x18003cabb  mov     rcx, [rbp+5Fh]; this
0x18003cabf  mov     r9d, eax; char *
0x18003cac2  lea     r8, aOnecoreuapDsNf_59; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003cac9  mov     edx, 32h ; '2'; void *
0x18003cace  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cad3  nop
0x18003cad4  mov     rcx, [rbp+57h+ppIFactory]
0x18003cad8  test    rcx, rcx
0x18003cadb  jz      short loc_18003CAEE
0x18003cadd  mov     [rbp+57h+ppIFactory], r15
0x18003cae1  mov     rax, [rcx]
0x18003cae4  mov     rax, [rax+10h]
0x18003cae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003caed  nop
0x18003caee  mov     rcx, [rbp+57h+var_68]
0x18003caf2  test    rcx, rcx
0x18003caf5  jz      short loc_18003CB08
0x18003caf7  mov     [rbp+57h+var_68], r15
0x18003cafb  mov     rax, [rcx]
0x18003cafe  mov     rax, [rax+10h]
0x18003cb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb07  nop
0x18003cb08  mov     rcx, [rbp+57h+var_70]
0x18003cb0c  test    rcx, rcx
0x18003cb0f  jz      short loc_18003CB22
0x18003cb11  mov     [rbp+57h+var_70], r15
0x18003cb15  mov     rax, [rcx]
0x18003cb18  mov     rax, [rax+10h]
0x18003cb1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb21  nop
0x18003cb22  jmp     loc_18003CA1C
0x18003cb27  mov     [rbp+57h+var_58], r15
0x18003cb2b  mov     rcx, [rbp+57h+ppIFactory]
0x18003cb2f  mov     rax, [rcx]
0x18003cb32  lea     r8, [rbp+57h+var_58]
0x18003cb36  mov     rdx, [rbp+57h+var_68]
0x18003cb3a  mov     rax, [rax+100h]
0x18003cb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb46  mov     ebx, eax
0x18003cb48  test    eax, eax
0x18003cb4a  jns     loc_18003CBD6
0x18003cb50  mov     rcx, [rbp+5Fh]; this
0x18003cb54  mov     r9d, eax; char *
0x18003cb57  lea     r8, aOnecoreuapDsNf_59; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003cb5e  mov     edx, 35h ; '5'; void *
0x18003cb63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb68  nop
0x18003cb69  mov     rcx, [rbp+57h+var_58]
0x18003cb6d  test    rcx, rcx
0x18003cb70  jz      short loc_18003CB83
0x18003cb72  mov     [rbp+57h+var_58], r15
0x18003cb76  mov     rax, [rcx]
0x18003cb79  mov     rax, [rax+10h]
0x18003cb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb82  nop
0x18003cb83  mov     rcx, [rbp+57h+ppIFactory]
0x18003cb87  test    rcx, rcx
0x18003cb8a  jz      short loc_18003CB9D
0x18003cb8c  mov     [rbp+57h+ppIFactory], r15
0x18003cb90  mov     rax, [rcx]
0x18003cb93  mov     rax, [rax+10h]
0x18003cb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb9c  nop
0x18003cb9d  mov     rcx, [rbp+57h+var_68]
0x18003cba1  test    rcx, rcx
0x18003cba4  jz      short loc_18003CBB7
0x18003cba6  mov     [rbp+57h+var_68], r15
0x18003cbaa  mov     rax, [rcx]
0x18003cbad  mov     rax, [rax+10h]
0x18003cbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbb6  nop
0x18003cbb7  mov     rcx, [rbp+57h+var_70]
0x18003cbbb  test    rcx, rcx
0x18003cbbe  jz      short loc_18003CBD1
0x18003cbc0  mov     [rbp+57h+var_70], r15
0x18003cbc4  mov     rax, [rcx]
0x18003cbc7  mov     rax, [rax+10h]
0x18003cbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbd0  nop
0x18003cbd1  jmp     loc_18003CA1C
0x18003cbd6  mov     [rbp+57h+var_50], r15
0x18003cbda  mov     rcx, [rbp+57h+var_58]
0x18003cbde  mov     rax, [rcx]
0x18003cbe1  lea     r8, [rbp+57h+var_50]
0x18003cbe5  xor     edx, edx
0x18003cbe7  mov     rax, [rax+0A0h]
0x18003cbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbf3  mov     ebx, eax
0x18003cbf5  test    eax, eax
0x18003cbf7  jns     loc_18003CC9D
0x18003cbfd  mov     rcx, [rbp+5Fh]; this
0x18003cc01  mov     r9d, eax; char *
0x18003cc04  lea     r8, aOnecoreuapDsNf_59; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003cc0b  mov     edx, 38h ; '8'; void *
0x18003cc10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cc15  nop
0x18003cc16  mov     rcx, [rbp+57h+var_50]
0x18003cc1a  test    rcx, rcx
0x18003cc1d  jz      short loc_18003CC30
0x18003cc1f  mov     [rbp+57h+var_50], r15
0x18003cc23  mov     rax, [rcx]
0x18003cc26  mov     rax, [rax+10h]
0x18003cc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc2f  nop
0x18003cc30  mov     rcx, [rbp+57h+var_58]
0x18003cc34  test    rcx, rcx
0x18003cc37  jz      short loc_18003CC4A
0x18003cc39  mov     [rbp+57h+var_58], r15
0x18003cc3d  mov     rax, [rcx]
0x18003cc40  mov     rax, [rax+10h]
0x18003cc44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc49  nop
0x18003cc4a  mov     rcx, [rbp+57h+ppIFactory]
0x18003cc4e  test    rcx, rcx
0x18003cc51  jz      short loc_18003CC64
0x18003cc53  mov     [rbp+57h+ppIFactory], r15
0x18003cc57  mov     rax, [rcx]
0x18003cc5a  mov     rax, [rax+10h]
0x18003cc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc63  nop
0x18003cc64  mov     rcx, [rbp+57h+var_68]
0x18003cc68  test    rcx, rcx
0x18003cc6b  jz      short loc_18003CC7E
0x18003cc6d  mov     [rbp+57h+var_68], r15
0x18003cc71  mov     rax, [rcx]
0x18003cc74  mov     rax, [rax+10h]
0x18003cc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc7d  nop
0x18003cc7e  mov     rcx, [rbp+57h+var_70]
0x18003cc82  test    rcx, rcx
0x18003cc85  jz      short loc_18003CC98
0x18003cc87  mov     [rbp+57h+var_70], r15
0x18003cc8b  mov     rax, [rcx]
0x18003cc8e  mov     rax, [rax+10h]
0x18003cc92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc97  nop
0x18003cc98  jmp     loc_18003CA1C
0x18003cc9d  mov     edx, edi; cbInit
0x18003cc9f  mov     rcx, rsi; pInit
0x18003cca2  call    cs:__imp_SHCreateMemStream
0x18003cca8  mov     rdi, rax
0x18003ccab  mov     [rbp+57h+var_40], rax
0x18003ccaf  test    rax, rax
0x18003ccb2  jnz     loc_18003CD5B
0x18003ccb8  mov     rcx, [rbp+5Fh]; this
0x18003ccbc  mov     ebx, 8007000Eh
0x18003ccc1  mov     r9d, ebx; char *
0x18003ccc4  lea     r8, aOnecoreuapDsNf_59; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003cccb  lea     edx, [rax+3Ch]; void *
0x18003ccce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ccd3  nop
0x18003ccd4  mov     rcx, [rbp+57h+var_50]
0x18003ccd8  test    rcx, rcx
0x18003ccdb  jz      short loc_18003CCEE
0x18003ccdd  mov     [rbp+57h+var_50], r15
0x18003cce1  mov     rax, [rcx]
0x18003cce4  mov     rax, [rax+10h]
0x18003cce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cced  nop
0x18003ccee  mov     rcx, [rbp+57h+var_58]
0x18003ccf2  test    rcx, rcx
0x18003ccf5  jz      short loc_18003CD08
0x18003ccf7  mov     [rbp+57h+var_58], r15
0x18003ccfb  mov     rax, [rcx]
0x18003ccfe  mov     rax, [rax+10h]
0x18003cd02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd07  nop
0x18003cd08  mov     rcx, [rbp+57h+ppIFactory]
0x18003cd0c  test    rcx, rcx
0x18003cd0f  jz      short loc_18003CD22
0x18003cd11  mov     [rbp+57h+ppIFactory], r15
0x18003cd15  mov     rax, [rcx]
0x18003cd18  mov     rax, [rax+10h]
0x18003cd1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd21  nop
0x18003cd22  mov     rcx, [rbp+57h+var_68]
0x18003cd26  test    rcx, rcx
0x18003cd29  jz      short loc_18003CD3C
0x18003cd2b  mov     [rbp+57h+var_68], r15
0x18003cd2f  mov     rax, [rcx]
0x18003cd32  mov     rax, [rax+10h]
0x18003cd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd3b  nop
0x18003cd3c  mov     rcx, [rbp+57h+var_70]
0x18003cd40  test    rcx, rcx
0x18003cd43  jz      short loc_18003CD56
0x18003cd45  mov     [rbp+57h+var_70], r15
0x18003cd49  mov     rdx, [rcx]
0x18003cd4c  mov     rax, [rdx+10h]
0x18003cd50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd55  nop
0x18003cd56  jmp     loc_18003CA1C
0x18003cd5b  mov     [rbp+57h+var_48], r15
0x18003cd5f  mov     rcx, [rbp+57h+var_50]
0x18003cd63  mov     rax, [rcx]
0x18003cd66  movss   xmm0, cs:__real@3f800000
0x18003cd6e  lea     r9, [rbp+57h+var_48]
0x18003cd72  unpcklps xmm0, xmm0
0x18003cd75  movq    r8, xmm0
0x18003cd7a  mov     rdx, rdi
0x18003cd7d  mov     rax, [rax+398h]
0x18003cd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd89  mov     ebx, eax
0x18003cd8b  mov     rcx, [rbp+5Fh]; this
0x18003cd8f  test    eax, eax
0x18003cd91  jns     short loc_18003CDA7
0x18003cd93  mov     r9d, eax; char *
0x18003cd96  lea     r8, aOnecoreuapDsNf_59; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003cd9d  mov     edx, 40h ; '@'; void *
0x18003cda2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003cda7  shr     ebx, 1Fh
0x18003cdaa  xor     bl, 1
0x18003cdad  mov     [r14], bl
  ... truncated ...
```
