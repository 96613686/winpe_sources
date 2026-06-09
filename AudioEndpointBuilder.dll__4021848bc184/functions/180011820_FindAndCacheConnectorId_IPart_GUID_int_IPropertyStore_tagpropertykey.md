# FindAndCacheConnectorId(IPart *,_GUID,int,IPropertyStore *,_tagpropertykey)

- ea: `0x180011820`
- end: `0x180011f01`
- name: `?FindAndCacheConnectorId@@YAJPEAUIPart@@U_GUID@@HPEAUIPropertyStore@@U_tagpropertykey@@@Z`
- size: `1761`
- prototype: `__int64 __fastcall(struct IPart *, struct _GUID *, int, struct IPropertyStore *, struct _tagpropertykey *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004a344`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x180011820`
- `0x18003e920`
- `0x18003f780`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800119fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011b01`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011b84`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011bc5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c89`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011dc2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011e13`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011ee0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800119fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011b01`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011b84`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011bc5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c89`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011dc2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011e13`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011ee0`

## string_xrefs

- `0x180011aa9`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180011b2c`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180011baf`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180011bf0`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180011c73`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180011dfd`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180011e78`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180011e92`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180011eaa`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
__int64 __fastcall FindAndCacheConnectorId(
        struct IPart *a1,
        struct _GUID *a2,
        int a3,
        struct IPropertyStore *a4,
        struct _tagpropertykey *a5)
{
  int v6; // esi
  int v9; // eax
  unsigned int v10; // ebx
  HRESULT (__stdcall *GetTopologyObject)(IPart *, IDeviceTopology **); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  unsigned int i; // ebx
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // rcx
  int v21; // edi
  int v22; // eax
  unsigned int v23; // edi
  int v25; // eax
  unsigned int v26; // edi
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, struct IPart *, __int64, _QWORD); // rsi
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rbx
  int v33; // eax
  int v34; // eax
  __int64 v35; // rdx
  int *v36; // [rsp+20h] [rbp-61h]
  __int64 *v37; // [rsp+30h] [rbp-51h] BYREF
  __int64 v38; // [rsp+38h] [rbp-49h] BYREF
  int v39[2]; // [rsp+40h] [rbp-41h] BYREF
  __int64 v40; // [rsp+48h] [rbp-39h] BYREF
  __int64 v41; // [rsp+50h] [rbp-31h] BYREF
  unsigned int v42; // [rsp+58h] [rbp-29h] BYREF
  int v43; // [rsp+5Ch] [rbp-25h] BYREF
  int v44; // [rsp+60h] [rbp-21h] BYREF
  int v45; // [rsp+64h] [rbp-1Dh] BYREF
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-19h] BYREF
  __int64 v47; // [rsp+78h] [rbp-9h]
  int v48; // [rsp+80h] [rbp-1h]
  __int128 Buf1; // [rsp+88h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v6 = a3;
  v48 = a3;
  v42 = 0;
  v37 = 0;
  v41 = 0;
  v45 = 0;
  v43 = 0;
  *(_OWORD *)pvar = 0;
  v47 = 0;
  v9 = ((__int64 (__fastcall *)(struct IPart *, int *))a1->lpVtbl->GetLocalId)(a1, &v43);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34D,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v9,
      (int)v36);
    PropVariantClear(pvar);
    return v10;
  }
  GetTopologyObject = a1->lpVtbl->GetTopologyObject;
  v37 = 0;
  v12 = ((__int64 (__fastcall *)(struct IPart *, __int64 **))GetTopologyObject)(a1, &v37);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34F,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v12,
      (int)v36);
    PropVariantClear(pvar);
    if ( v37 )
      (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
    return v13;
  }
  v14 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v37 + 24))(v37, &v42);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x351,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v14,
      (int)v36);
    PropVariantClear(pvar);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
    return v15;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v42 )
      goto LABEL_19;
    Buf1 = 0;
    v44 = 0;
    v40 = 0;
    v38 = 0;
    *(_QWORD *)v39 = 0;
    v17 = *v37;
    v40 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v17 + 32))(v37, i, &v40);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35C,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v18,
        (int)v36);
      if ( *(_QWORD *)v39 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      PropVariantClear(pvar);
      if ( v37 )
        (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
      return v19;
    }
    v20 = v38;
    v38 = 0;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v21 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v40)(
            v40,
            &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9,
            &v38);
    if ( v21 < 0 )
    {
      v35 = 862;
      goto LABEL_85;
    }
    v22 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v38 + 56LL))(v38, &Buf1);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x361,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v22,
        (int)v36);
      if ( *(_QWORD *)v39 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      PropVariantClear(pvar);
      if ( v37 )
        (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
      return v23;
    }
    if ( !memcmp_0(&Buf1, a2, 0x10u) )
      break;
    if ( *(_QWORD *)v39 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
LABEL_16:
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
LABEL_18:
    ;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 32LL))(v38, &v44);
  v26 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x369,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v25,
      (int)v36);
    if ( *(_QWORD *)v39 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    PropVariantClear(pvar);
    if ( v37 )
      (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
    return v26;
  }
  if ( v44 == v43 )
  {
    if ( *(_QWORD *)v39 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_16;
  }
  if ( !v6 )
    goto LABEL_65;
  v27 = (__int64)v37;
  v28 = *(__int64 (__fastcall **)(__int64, struct IPart *, __int64, _QWORD))(*v37 + 72);
  v29 = *(_QWORD *)v39;
  *(_QWORD *)v39 = 0;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  v36 = v39;
  v30 = v28(v27, a1, v38, 0);
  v21 = v30;
  if ( v30 == -2147023728 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v39);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    v6 = v48;
    goto LABEL_18;
  }
  if ( v30 < 0 )
  {
    v35 = 888;
LABEL_85:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v21,
      (int)v36);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v39);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    goto LABEL_86;
  }
LABEL_65:
  v31 = v38;
  v32 = v38;
  v41 = v38;
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
    v31 = v38;
  }
  if ( *(_QWORD *)v39 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 16LL))(*(_QWORD *)v39);
    v31 = v38;
  }
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v32 )
  {
    v33 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 32LL))(v32, &v45);
    v21 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x384,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v33,
        (int)v36);
    }
    else
    {
      LOWORD(pvar[0]) = 19;
      LODWORD(pvar[1]) = v45;
      v34 = ((__int64 (__fastcall *)(struct IPropertyStore *, struct _tagpropertykey *, PROPVARIANT *))a4->lpVtbl->SetValue)(
              a4,
              a5,
              pvar);
      v21 = v34;
      if ( v34 >= 0 )
      {
        PropVariantClear(pvar);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        if ( v37 )
          (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x389,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v34,
        (int)v36);
    }
LABEL_86:
    PropVariantClear(pvar);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
    return (unsigned int)v21;
  }
LABEL_19:
  PropVariantClear(pvar);
  if ( v37 )
    (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
  return 2147943568LL;
}

```

## disassembly

```asm
0x180011820  mov     [rsp-8+arg_8], rbx
0x180011825  push    rbp
0x180011826  push    rsi
0x180011827  push    rdi
0x180011828  push    r12
0x18001182a  push    r13
0x18001182c  push    r14
0x18001182e  push    r15
0x180011830  lea     rbp, [rsp-1Fh]
0x180011835  sub     rsp, 0A0h
0x18001183c  mov     rax, cs:__security_cookie
0x180011843  xor     rax, rsp
0x180011846  mov     [rbp+4Fh+var_38], rax
0x18001184a  mov     r12, r9
0x18001184d  mov     esi, r8d
0x180011850  mov     [rbp+4Fh+var_50], r8d
0x180011854  mov     r15, rdx
0x180011857  mov     r14, rcx
0x18001185a  mov     r13, [rbp+4Fh+arg_20]
0x18001185e  xor     edi, edi
0x180011860  mov     [rbp+4Fh+var_78], edi
0x180011863  mov     [rbp+4Fh+var_A0], rdi
0x180011867  mov     [rbp+4Fh+var_80], rdi
0x18001186b  mov     [rbp+4Fh+var_6C], edi
0x18001186e  mov     [rbp+4Fh+var_74], edi
0x180011871  xorps   xmm0, xmm0
0x180011874  xor     eax, eax
0x180011876  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x18001187a  mov     [rbp+4Fh+var_58], rax
0x18001187e  mov     rax, [rcx]
0x180011881  lea     rdx, [rbp+4Fh+var_74]
0x180011885  mov     rax, [rax+20h]
0x180011889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001188e  mov     ebx, eax
0x180011890  test    eax, eax
0x180011892  js      loc_180011BA8
0x180011898  mov     rax, [r14]
0x18001189b  mov     rbx, [rax+60h]
0x18001189f  mov     rcx, [rbp+4Fh+var_A0]
0x1800118a3  mov     [rbp+4Fh+var_A0], rdi
0x1800118a7  test    rcx, rcx
0x1800118aa  jz      short loc_1800118B9
0x1800118ac  mov     rdx, [rcx]
0x1800118af  mov     rax, [rdx+10h]
0x1800118b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118b8  nop
0x1800118b9  lea     rdx, [rbp+4Fh+var_A0]
0x1800118bd  mov     rcx, r14
0x1800118c0  mov     rax, rbx
0x1800118c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c8  mov     ebx, eax
0x1800118ca  test    eax, eax
0x1800118cc  js      loc_180011C6C
0x1800118d2  mov     rcx, [rbp+4Fh+var_A0]
0x1800118d6  mov     rax, [rcx]
0x1800118d9  lea     rdx, [rbp+4Fh+var_78]
0x1800118dd  mov     rax, [rax+18h]
0x1800118e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e6  mov     ebx, eax
0x1800118e8  test    eax, eax
0x1800118ea  js      loc_180011DF6
0x1800118f0  mov     ebx, edi
0x1800118f2  cmp     ebx, [rbp+4Fh+var_78]
0x1800118f5  jnb     loc_1800119FA
0x1800118fb  xorps   xmm0, xmm0
0x1800118fe  movups  [rbp+4Fh+Buf1], xmm0
0x180011902  mov     [rbp+4Fh+var_70], edi
0x180011905  mov     [rbp+4Fh+var_88], rdi
0x180011909  mov     [rbp+4Fh+var_98], rdi
0x18001190d  mov     qword ptr [rbp+4Fh+var_90], rdi
0x180011911  mov     rcx, [rbp+4Fh+var_A0]
0x180011915  mov     rax, [rcx]
0x180011918  mov     [rbp+4Fh+var_88], rdi
0x18001191c  lea     r8, [rbp+4Fh+var_88]
0x180011920  mov     edx, ebx
0x180011922  mov     rax, [rax+20h]
0x180011926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001192b  mov     edi, eax
0x18001192d  test    eax, eax
0x18001192f  js      loc_180011B25
0x180011935  mov     rcx, [rbp+4Fh+var_98]
0x180011939  mov     [rbp+4Fh+var_98], 0
0x180011941  test    rcx, rcx
0x180011944  jz      short loc_180011953
0x180011946  mov     rax, [rcx]
0x180011949  mov     rax, [rax+10h]
0x18001194d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011952  nop
0x180011953  mov     rcx, [rbp+4Fh+var_88]
0x180011957  mov     rax, [rcx]
0x18001195a  lea     r8, [rbp+4Fh+var_98]
0x18001195e  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x180011965  mov     rax, [rax]
0x180011968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001196d  mov     edi, eax
0x18001196f  test    eax, eax
0x180011971  js      loc_180011EA5
0x180011977  mov     rcx, [rbp+4Fh+var_98]
0x18001197b  mov     rax, [rcx]
0x18001197e  lea     rdx, [rbp+4Fh+Buf1]
0x180011982  mov     rax, [rax+38h]
0x180011986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001198b  mov     edi, eax
0x18001198d  test    eax, eax
0x18001198f  js      loc_180011AA2
0x180011995  mov     r8d, 10h; Size
0x18001199b  mov     rdx, r15; Buf2
0x18001199e  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x1800119a2  call    memcmp_0
0x1800119a7  test    eax, eax
0x1800119a9  jz      loc_180011A47
0x1800119af  mov     rcx, qword ptr [rbp+4Fh+var_90]
0x1800119b3  test    rcx, rcx
0x1800119b6  jz      short loc_1800119C5
0x1800119b8  mov     rax, [rcx]
0x1800119bb  mov     rax, [rax+10h]
0x1800119bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119c4  nop
0x1800119c5  mov     rcx, [rbp+4Fh+var_98]
0x1800119c9  test    rcx, rcx
0x1800119cc  jz      short loc_1800119DB
0x1800119ce  mov     rax, [rcx]
0x1800119d1  mov     rax, [rax+10h]
0x1800119d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119da  nop
0x1800119db  mov     rcx, [rbp+4Fh+var_88]
0x1800119df  test    rcx, rcx
0x1800119e2  jz      short loc_1800119F1
0x1800119e4  mov     rax, [rcx]
0x1800119e7  mov     rax, [rax+10h]
0x1800119eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119f0  nop
0x1800119f1  inc     ebx
0x1800119f3  xor     edi, edi
0x1800119f5  jmp     loc_1800118F2
0x1800119fa  lea     rcx, [rbp+4Fh+pvar]; pvar
0x1800119fe  call    cs:__imp_PropVariantClear
0x180011a04  nop
0x180011a05  mov     rcx, [rbp+4Fh+var_A0]
0x180011a09  test    rcx, rcx
0x180011a0c  jz      short loc_180011A1B
0x180011a0e  mov     rdx, [rcx]
0x180011a11  mov     rax, [rdx+10h]
0x180011a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a1a  nop
0x180011a1b  mov     eax, 80070490h
0x180011a20  mov     rcx, [rbp+4Fh+var_38]
0x180011a24  xor     rcx, rsp; StackCookie
0x180011a27  call    __security_check_cookie
0x180011a2c  mov     rbx, [rsp+0D0h+arg_8]
0x180011a34  add     rsp, 0A0h
0x180011a3b  pop     r15
0x180011a3d  pop     r14
0x180011a3f  pop     r13
0x180011a41  pop     r12
0x180011a43  pop     rdi
0x180011a44  pop     rsi
0x180011a45  pop     rbp
0x180011a46  retn
0x180011a47  mov     rcx, [rbp+4Fh+var_98]
0x180011a4b  mov     rax, [rcx]
0x180011a4e  lea     rdx, [rbp+4Fh+var_70]
0x180011a52  mov     rax, [rax+20h]
0x180011a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a5b  mov     edi, eax
0x180011a5d  test    eax, eax
0x180011a5f  js      loc_180011BE9
0x180011a65  mov     eax, [rbp+4Fh+var_74]
0x180011a68  cmp     [rbp+4Fh+var_70], eax
0x180011a6b  jnz     loc_180011CAD
0x180011a71  mov     rcx, qword ptr [rbp+4Fh+var_90]
0x180011a75  test    rcx, rcx
0x180011a78  jz      short loc_180011A87
0x180011a7a  mov     rax, [rcx]
0x180011a7d  mov     rax, [rax+10h]
0x180011a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a86  nop
0x180011a87  mov     rcx, [rbp+4Fh+var_98]
0x180011a8b  test    rcx, rcx
0x180011a8e  jz      short loc_180011A9D
0x180011a90  mov     rax, [rcx]
0x180011a93  mov     rax, [rax+10h]
0x180011a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a9c  nop
0x180011a9d  jmp     loc_1800119DB
0x180011aa2  mov     rcx, [rbp+57h]; this
0x180011aa6  mov     r9d, edi; char *
0x180011aa9  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180011ab0  mov     edx, 361h; void *
0x180011ab5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011aba  nop
0x180011abb  mov     rcx, qword ptr [rbp+4Fh+var_90]
0x180011abf  test    rcx, rcx
0x180011ac2  jz      short loc_180011AD1
0x180011ac4  mov     rax, [rcx]
0x180011ac7  mov     rax, [rax+10h]
0x180011acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ad0  nop
0x180011ad1  mov     rcx, [rbp+4Fh+var_98]
0x180011ad5  test    rcx, rcx
0x180011ad8  jz      short loc_180011AE7
0x180011ada  mov     rax, [rcx]
0x180011add  mov     rax, [rax+10h]
0x180011ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ae6  nop
0x180011ae7  mov     rcx, [rbp+4Fh+var_88]
0x180011aeb  test    rcx, rcx
0x180011aee  jz      short loc_180011AFD
0x180011af0  mov     rax, [rcx]
0x180011af3  mov     rax, [rax+10h]
0x180011af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011afc  nop
0x180011afd  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180011b01  call    cs:__imp_PropVariantClear
0x180011b07  nop
0x180011b08  mov     rcx, [rbp+4Fh+var_A0]
0x180011b0c  test    rcx, rcx
0x180011b0f  jz      short loc_180011B1E
0x180011b11  mov     rax, [rcx]
0x180011b14  mov     rax, [rax+10h]
0x180011b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b1d  nop
0x180011b1e  mov     eax, edi
0x180011b20  jmp     loc_180011A20
0x180011b25  mov     rcx, [rbp+57h]; this
0x180011b29  mov     r9d, edi; char *
0x180011b2c  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180011b33  mov     edx, 35Ch; void *
0x180011b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b3d  nop
0x180011b3e  mov     rcx, qword ptr [rbp+4Fh+var_90]
0x180011b42  test    rcx, rcx
0x180011b45  jz      short loc_180011B54
0x180011b47  mov     rax, [rcx]
0x180011b4a  mov     rax, [rax+10h]
0x180011b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b53  nop
0x180011b54  mov     rcx, [rbp+4Fh+var_98]
0x180011b58  test    rcx, rcx
0x180011b5b  jz      short loc_180011B6A
0x180011b5d  mov     rax, [rcx]
0x180011b60  mov     rax, [rax+10h]
0x180011b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b69  nop
0x180011b6a  mov     rcx, [rbp+4Fh+var_88]
0x180011b6e  test    rcx, rcx
0x180011b71  jz      short loc_180011B80
0x180011b73  mov     rax, [rcx]
0x180011b76  mov     rax, [rax+10h]
0x180011b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b7f  nop
0x180011b80  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180011b84  call    cs:__imp_PropVariantClear
0x180011b8a  nop
0x180011b8b  mov     rcx, [rbp+4Fh+var_A0]
0x180011b8f  test    rcx, rcx
0x180011b92  jz      short loc_180011BA1
0x180011b94  mov     rax, [rcx]
0x180011b97  mov     rax, [rax+10h]
0x180011b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ba0  nop
0x180011ba1  mov     eax, edi
0x180011ba3  jmp     loc_180011A20
0x180011ba8  mov     rcx, [rbp+57h]; this
0x180011bac  mov     r9d, ebx; char *
0x180011baf  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180011bb6  mov     edx, 34Dh; void *
0x180011bbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bc0  nop
0x180011bc1  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180011bc5  call    cs:__imp_PropVariantClear
0x180011bcb  nop
0x180011bcc  mov     rcx, [rbp+4Fh+var_A0]
0x180011bd0  test    rcx, rcx
0x180011bd3  jz      short loc_180011BE2
0x180011bd5  mov     rax, [rcx]
0x180011bd8  mov     rax, [rax+10h]
0x180011bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011be1  nop
0x180011be2  mov     eax, ebx
0x180011be4  jmp     loc_180011A20
0x180011be9  mov     rcx, [rbp+57h]; this
0x180011bed  mov     r9d, edi; char *
0x180011bf0  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180011bf7  mov     edx, 369h; void *
0x180011bfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c01  nop
0x180011c02  mov     rcx, qword ptr [rbp+4Fh+var_90]
0x180011c06  test    rcx, rcx
0x180011c09  jz      short loc_180011C18
0x180011c0b  mov     rax, [rcx]
0x180011c0e  mov     rax, [rax+10h]
0x180011c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c17  nop
0x180011c18  mov     rcx, [rbp+4Fh+var_98]
0x180011c1c  test    rcx, rcx
0x180011c1f  jz      short loc_180011C2E
0x180011c21  mov     rax, [rcx]
0x180011c24  mov     rax, [rax+10h]
0x180011c28  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
