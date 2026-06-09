# GetPackageFromPackageFamilyName(ushort const *,Windows::Internal::StateRepository::IPackage * *)

- ea: `0x18006547c`
- end: `0x180065a03`
- name: `?GetPackageFromPackageFamilyName@@YAJPEBGPEAPEAUIPackage@StateRepository@Internal@Windows@@@Z`
- size: `1415`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::Internal::StateRepository::IPackage **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001cd70`

## callees

- `0x1800049a0`
- `0x18000c964`
- `0x18001e61c`
- `0x1800201ec`
- `0x18006547c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800654cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180065622`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800654cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180065622`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180065505`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006565c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180065505`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006565c`

## string_xrefs

- `0x180065518`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x1800655bb`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x18006566f`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x180065704`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x1800657ac`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x180065841`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x1800658e6`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GetPackageFromPackageFamilyName(
        const unsigned __int16 *a1,
        struct Windows::Internal::StateRepository::IPackage **a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rdi
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  HSTRING v21; // rbx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // [rsp+20h] [rbp-60h] BYREF
  __int64 v51; // [rsp+28h] [rbp-58h] BYREF
  __int64 v52; // [rsp+30h] [rbp-50h] BYREF
  __int64 v53; // [rsp+38h] [rbp-48h] BYREF
  int v54; // [rsp+40h] [rbp-40h] BYREF
  const unsigned __int16 *v55; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v55 = a1;
  v51 = 0;
  v50 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackageFamily", 0x2Eu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
LABEL_77:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x180065A02LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426, &v50);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v50);
    v8 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v7;
  }
  v11 = v50;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v50 + 128LL);
  v13 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v55);
  v15 = v12(v11, *(_QWORD *)(v14 + 24), &v51);
  v7 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
      (const char *)(unsigned int)v15,
      v50);
    v16 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v7;
  }
  v52 = 0;
  string = 0;
  v18 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v18 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
    goto LABEL_77;
  }
  v21 = string;
  v22 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = RoGetActivationFactory(v21, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v52);
  v7 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
      (const char *)(unsigned int)v23,
      v50);
    v24 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    return v7;
  }
  v53 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v52 + 208LL))(v52, v51, &v53);
  v7 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
      (const char *)(unsigned int)v27,
      v50);
    v28 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v29 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    return v7;
  }
  v54 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v53 + 56LL))(v53, &v54);
  v7 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
      (const char *)(unsigned int)v32,
      v50);
    v33 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    return v7;
  }
  if ( !v54 )
  {
    v7 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
      (const char *)0x80070490LL,
      v50);
    v37 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return v7;
  }
  v41 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Internal::StateRepository::IPackage **))(*(_QWORD *)v53 + 48LL))(
          v53,
          0,
          a2);
  v7 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
      (const char *)(unsigned int)v41,
      v50);
    v42 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    return v7;
  }
  v46 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  return 0;
}

```

## disassembly

```asm
0x18006547c  mov     [rsp-18h+arg_10], rbx
0x180065481  mov     [rsp-18h+arg_18], rsi
0x180065486  push    rbp
0x180065487  push    rdi
0x180065488  push    r14
0x18006548a  mov     rbp, rsp
0x18006548d  sub     rsp, 80h
0x180065494  mov     rax, cs:__security_cookie
0x18006549b  xor     rax, rsp
0x18006549e  mov     [rbp+var_10], rax
0x1800654a2  mov     rsi, rdx
0x1800654a5  mov     [rbp+var_38], rcx
0x1800654a9  xor     r14d, r14d
0x1800654ac  mov     [rbp+var_58], r14
0x1800654b0  mov     [rbp+var_60], r14
0x1800654b4  mov     [rbp+string], r14
0x1800654b8  lea     r9, [rbp+string]; string
0x1800654bc  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800654c0  lea     edx, [r14+2Eh]; length
0x1800654c4  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800654cb  call    cs:__imp_WindowsCreateStringReference
0x1800654d1  test    eax, eax
0x1800654d3  js      loc_1800659FB
0x1800654d9  mov     rbx, [rbp+string]
0x1800654dd  mov     rcx, [rbp+var_60]
0x1800654e1  test    rcx, rcx
0x1800654e4  jz      short loc_1800654F7
0x1800654e6  mov     [rbp+var_60], r14
0x1800654ea  mov     rax, [rcx]
0x1800654ed  mov     rax, [rax+10h]
0x1800654f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800654f6  nop
0x1800654f7  lea     r8, [rbp+var_60]
0x1800654fb  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x180065502  mov     rcx, rbx
0x180065505  call    cs:__imp_RoGetActivationFactory
0x18006550b  mov     ebx, eax
0x18006550d  test    eax, eax
0x18006550f  jns     short loc_180065565
0x180065511  mov     rcx, [rbp+18h]; this
0x180065515  mov     r9d, eax; char *
0x180065518  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18006551f  mov     edx, 3Fh ; '?'; void *
0x180065524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065529  nop
0x18006552a  mov     rcx, [rbp+var_60]
0x18006552e  test    rcx, rcx
0x180065531  jz      short loc_180065544
0x180065533  mov     [rbp+var_60], r14
0x180065537  mov     rax, [rcx]
0x18006553a  mov     rax, [rax+10h]
0x18006553e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065543  nop
0x180065544  mov     rcx, [rbp+var_58]
0x180065548  test    rcx, rcx
0x18006554b  jz      short loc_18006555E
0x18006554d  mov     [rbp+var_58], r14
0x180065551  mov     rax, [rcx]
0x180065554  mov     rax, [rax+10h]
0x180065558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006555d  nop
0x18006555e  mov     eax, ebx
0x180065560  jmp     loc_1800659CF
0x180065565  mov     rbx, [rbp+var_60]
0x180065569  mov     rax, [rbx]
0x18006556c  mov     rdi, [rax+80h]
0x180065573  mov     rcx, [rbp+var_58]
0x180065577  test    rcx, rcx
0x18006557a  jz      short loc_18006558D
0x18006557c  mov     [rbp+var_58], r14
0x180065580  mov     rax, [rcx]
0x180065583  mov     rax, [rax+10h]
0x180065587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006558c  nop
0x18006558d  lea     rdx, [rbp+var_38]
0x180065591  lea     rcx, [rbp+hstringHeader]
0x180065595  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18006559a  nop
0x18006559b  lea     r8, [rbp+var_58]
0x18006559f  mov     rdx, [rax+18h]
0x1800655a3  mov     rcx, rbx
0x1800655a6  mov     rax, rdi
0x1800655a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800655ae  mov     ebx, eax
0x1800655b0  test    eax, eax
0x1800655b2  jns     short loc_180065606
0x1800655b4  mov     rcx, [rbp+18h]; this
0x1800655b8  mov     r9d, eax; char *
0x1800655bb  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800655c2  mov     edx, 40h ; '@'; void *
0x1800655c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800655cc  nop
0x1800655cd  mov     rcx, [rbp+var_60]
0x1800655d1  test    rcx, rcx
0x1800655d4  jz      short loc_1800655E7
0x1800655d6  mov     [rbp+var_60], r14
0x1800655da  mov     rax, [rcx]
0x1800655dd  mov     rax, [rax+10h]
0x1800655e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800655e6  nop
0x1800655e7  mov     rcx, [rbp+var_58]
0x1800655eb  test    rcx, rcx
0x1800655ee  jz      short loc_180065601
0x1800655f0  mov     [rbp+var_58], r14
0x1800655f4  mov     rax, [rcx]
0x1800655f7  mov     rax, [rax+10h]
0x1800655fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065600  nop
0x180065601  jmp     loc_18006555E
0x180065606  mov     [rbp+var_50], r14
0x18006560a  mov     [rbp+string], r14
0x18006560e  lea     r9, [rbp+string]; string
0x180065612  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180065616  mov     edx, 28h ; '('; length
0x18006561b  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180065622  call    cs:__imp_WindowsCreateStringReference
0x180065628  test    eax, eax
0x18006562a  js      loc_1800659F3
0x180065630  mov     rbx, [rbp+string]
0x180065634  mov     rcx, [rbp+var_50]
0x180065638  test    rcx, rcx
0x18006563b  jz      short loc_18006564E
0x18006563d  mov     [rbp+var_50], r14
0x180065641  mov     rax, [rcx]
0x180065644  mov     rax, [rax+10h]
0x180065648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006564d  nop
0x18006564e  lea     r8, [rbp+var_50]
0x180065652  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x180065659  mov     rcx, rbx
0x18006565c  call    cs:__imp_RoGetActivationFactory
0x180065662  mov     ebx, eax
0x180065664  test    eax, eax
0x180065666  jns     short loc_1800656D4
0x180065668  mov     rcx, [rbp+18h]; this
0x18006566c  mov     r9d, eax; char *
0x18006566f  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180065676  mov     edx, 43h ; 'C'; void *
0x18006567b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065680  nop
0x180065681  mov     rcx, [rbp+var_50]
0x180065685  test    rcx, rcx
0x180065688  jz      short loc_18006569B
0x18006568a  mov     [rbp+var_50], r14
0x18006568e  mov     rax, [rcx]
0x180065691  mov     rax, [rax+10h]
0x180065695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006569a  nop
0x18006569b  mov     rcx, [rbp+var_60]
0x18006569f  test    rcx, rcx
0x1800656a2  jz      short loc_1800656B5
0x1800656a4  mov     [rbp+var_60], r14
0x1800656a8  mov     rax, [rcx]
0x1800656ab  mov     rax, [rax+10h]
0x1800656af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656b4  nop
0x1800656b5  mov     rcx, [rbp+var_58]
0x1800656b9  test    rcx, rcx
0x1800656bc  jz      short loc_1800656CF
0x1800656be  mov     [rbp+var_58], r14
0x1800656c2  mov     rax, [rcx]
0x1800656c5  mov     rax, [rax+10h]
0x1800656c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656ce  nop
0x1800656cf  jmp     loc_18006555E
0x1800656d4  mov     [rbp+var_48], r14
0x1800656d8  mov     rcx, [rbp+var_50]
0x1800656dc  mov     rax, [rcx]
0x1800656df  lea     r8, [rbp+var_48]
0x1800656e3  mov     rdx, [rbp+var_58]
0x1800656e7  mov     rax, [rax+0D0h]
0x1800656ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656f3  mov     ebx, eax
0x1800656f5  test    eax, eax
0x1800656f7  jns     loc_180065783
0x1800656fd  mov     rcx, [rbp+18h]; this
0x180065701  mov     r9d, eax; char *
0x180065704  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18006570b  mov     edx, 46h ; 'F'; void *
0x180065710  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065715  nop
0x180065716  mov     rcx, [rbp+var_48]
0x18006571a  test    rcx, rcx
0x18006571d  jz      short loc_180065730
0x18006571f  mov     [rbp+var_48], r14
0x180065723  mov     rax, [rcx]
0x180065726  mov     rax, [rax+10h]
0x18006572a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006572f  nop
0x180065730  mov     rcx, [rbp+var_50]
0x180065734  test    rcx, rcx
0x180065737  jz      short loc_18006574A
0x180065739  mov     [rbp+var_50], r14
0x18006573d  mov     rax, [rcx]
0x180065740  mov     rax, [rax+10h]
0x180065744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065749  nop
0x18006574a  mov     rcx, [rbp+var_60]
0x18006574e  test    rcx, rcx
0x180065751  jz      short loc_180065764
0x180065753  mov     [rbp+var_60], r14
0x180065757  mov     rax, [rcx]
0x18006575a  mov     rax, [rax+10h]
0x18006575e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065763  nop
0x180065764  mov     rcx, [rbp+var_58]
0x180065768  test    rcx, rcx
0x18006576b  jz      short loc_18006577E
0x18006576d  mov     [rbp+var_58], r14
0x180065771  mov     rax, [rcx]
0x180065774  mov     rax, [rax+10h]
0x180065778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006577d  nop
0x18006577e  jmp     loc_18006555E
0x180065783  mov     [rbp+var_40], r14d
0x180065787  mov     rcx, [rbp+var_48]
0x18006578b  mov     rax, [rcx]
0x18006578e  lea     rdx, [rbp+var_40]
0x180065792  mov     rax, [rax+38h]
0x180065796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006579b  mov     ebx, eax
0x18006579d  test    eax, eax
0x18006579f  jns     loc_18006582B
0x1800657a5  mov     rcx, [rbp+18h]; this
0x1800657a9  mov     r9d, eax; char *
0x1800657ac  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800657b3  mov     edx, 49h ; 'I'; void *
0x1800657b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800657bd  nop
0x1800657be  mov     rcx, [rbp+var_48]
0x1800657c2  test    rcx, rcx
0x1800657c5  jz      short loc_1800657D8
0x1800657c7  mov     [rbp+var_48], r14
0x1800657cb  mov     rax, [rcx]
0x1800657ce  mov     rax, [rax+10h]
0x1800657d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800657d7  nop
0x1800657d8  mov     rcx, [rbp+var_50]
0x1800657dc  test    rcx, rcx
0x1800657df  jz      short loc_1800657F2
0x1800657e1  mov     [rbp+var_50], r14
0x1800657e5  mov     rax, [rcx]
0x1800657e8  mov     rax, [rax+10h]
0x1800657ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800657f1  nop
0x1800657f2  mov     rcx, [rbp+var_60]
0x1800657f6  test    rcx, rcx
0x1800657f9  jz      short loc_18006580C
0x1800657fb  mov     [rbp+var_60], r14
0x1800657ff  mov     rax, [rcx]
0x180065802  mov     rax, [rax+10h]
0x180065806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006580b  nop
0x18006580c  mov     rcx, [rbp+var_58]
0x180065810  test    rcx, rcx
0x180065813  jz      short loc_180065826
0x180065815  mov     [rbp+var_58], r14
0x180065819  mov     rax, [rcx]
0x18006581c  mov     rax, [rax+10h]
0x180065820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065825  nop
0x180065826  jmp     loc_18006555E
0x18006582b  cmp     [rbp+var_40], r14d
0x18006582f  jnz     loc_1800658C0
0x180065835  mov     rcx, [rbp+18h]; this
0x180065839  mov     ebx, 80070490h
0x18006583e  mov     r9d, ebx; char *
0x180065841  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180065848  mov     edx, 4Ah ; 'J'; void *
0x18006584d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065852  nop
0x180065853  mov     rcx, [rbp+var_48]
0x180065857  test    rcx, rcx
0x18006585a  jz      short loc_18006586D
0x18006585c  mov     [rbp+var_48], r14
0x180065860  mov     rax, [rcx]
0x180065863  mov     rax, [rax+10h]
0x180065867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006586c  nop
0x18006586d  mov     rcx, [rbp+var_50]
0x180065871  test    rcx, rcx
0x180065874  jz      short loc_180065887
0x180065876  mov     [rbp+var_50], r14
0x18006587a  mov     rax, [rcx]
0x18006587d  mov     rax, [rax+10h]
0x180065881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065886  nop
0x180065887  mov     rcx, [rbp+var_60]
0x18006588b  test    rcx, rcx
0x18006588e  jz      short loc_1800658A1
0x180065890  mov     [rbp+var_60], r14
0x180065894  mov     rax, [rcx]
0x180065897  mov     rax, [rax+10h]
0x18006589b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800658a0  nop
0x1800658a1  mov     rcx, [rbp+var_58]
0x1800658a5  test    rcx, rcx
0x1800658a8  jz      short loc_1800658BB
0x1800658aa  mov     [rbp+var_58], r14
0x1800658ae  mov     rdx, [rcx]
  ... truncated ...
```
