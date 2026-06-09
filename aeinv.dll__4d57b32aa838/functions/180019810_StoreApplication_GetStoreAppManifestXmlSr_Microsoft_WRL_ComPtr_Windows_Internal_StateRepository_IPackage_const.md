# StoreApplication::GetStoreAppManifestXmlSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,bool)

- ea: `0x180019810`
- end: `0x180019ed5`
- name: `?GetStoreAppManifestXmlSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@_N@Z`
- size: `1733`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a5f8`
- `0x180044e70`

## callees

- `0x18000a39c`
- `0x180017250`
- `0x180018568`
- `0x180018a60`
- `0x180018ff4`
- `0x180019810`
- `0x18001bb44`
- `0x18001bb78`
- `0x180025340`
- `0x180025c5c`
- `0x1800293b0`
- `0x1800402b4`
- `0x1800404c4`
- `0x180040500`
- `0x180045480`
- `0x18004826c`
- `0x1800487ac`
- `0x180053948`
- `0x180059920`
- `0x1800679f8`
- `0x180130010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180019dc7`
- `KERNEL32!SetLastError` at `0x180019ec2`
- `KERNEL32!SetLastError` at `0x180019dc7`
- `KERNEL32!SetLastError` at `0x180019ec2`
- `ole32!CoCreateInstance` at `0x180019aa0`
- `ole32!CoCreateInstance` at `0x180019aa0`

## string_xrefs

- `0x1800198d1`: `Windows.Internal.StateRepository.AppxManifest`
- `0x180019d4f`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180019d64`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180019d79`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180019db0`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180019e80`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180019ea0`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
_bstr_t::Data_t *__fastcall StoreApplication::GetStoreAppManifestXmlSr(
        _bstr_t::Data_t *a1,
        _bstr_t::Data_t **a2,
        char a3)
{
  int StringReference; // eax
  int v7; // edx
  unsigned int v8; // r8d
  __int64 v9; // rbx
  int ActivationFactory; // eax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _bstr_t::Data_t *, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD *); // rsi
  HSTRING v17; // rbx
  int v18; // eax
  __int64 StringRawBuffer; // rax
  __int64 v20; // r8
  _bstr_t::Data_t *v21; // rbx
  __int64 v22; // rdi
  HRESULT v23; // eax
  LPVOID v24; // rbx
  void (__fastcall *v25)(LPVOID, __int64, __int16 *); // rdi
  const unsigned __int16 *v26; // rdx
  _bstr_t *v27; // rax
  __int64 v28; // rdx
  LPVOID v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  HSTRING v32; // rcx
  _bstr_t::Data_t *v34; // rbx
  __int64 StoreAppManifestPathFromPackageSr; // rdi
  __int64 v36; // rbx
  __int64 XmlFromFileSr; // rbx
  __int64 v38; // rcx
  __int64 v39; // rcx
  int v40; // [rsp+28h] [rbp-E0h]
  int v41; // [rsp+28h] [rbp-E0h]
  char v42; // [rsp+38h] [rbp-D0h] BYREF
  __int16 v43; // [rsp+3Ch] [rbp-CCh] BYREF
  _bstr_t::Data_t *v44; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v48[3]; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v49; // [rsp+78h] [rbp-90h] BYREF
  __int128 v50; // [rsp+88h] [rbp-80h]
  __int128 v51; // [rsp+98h] [rbp-70h] BYREF
  __int128 v52; // [rsp+A8h] [rbp-60h]
  _BYTE v53[24]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-38h]
  _BYTE v55[32]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v56[32]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v48[2] = -2;
  v44 = a1;
  v49 = 0;
  v50 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(&v49);
  v51 = 0;
  v52 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(&v51);
  v42 = 0;
  v48[0] = 0;
  v45 = 0;
  v46 = 0;
  v54 = 0;
  if ( !g_ApiWindowsCreateStringReference )
  {
    SetLastError(0x32u);
    StringReference = -2147467263;
    goto LABEL_73;
  }
  StringReference = g_ApiWindowsCreateStringReference();
  if ( StringReference < 0 )
  {
LABEL_73:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v7, v8);
    JUMPOUT(0x180019ED4LL);
  }
  v9 = v54;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v45);
  ActivationFactory = RoGetActivationFactory(v9, &GUID_5fc148b1_ad6b_4d3d_b11d_e881979c15f4, &v45);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x691,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v40);
  v11 = (*(__int64 (__fastcall **)(__int64, _bstr_t::Data_t *, char *))(*(_QWORD *)v45 + 56LL))(v45, *a2, &v42);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x694,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v11,
      v40);
  if ( v42 && a3 )
  {
    v12 = v45;
    v13 = *(__int64 (__fastcall **)(__int64, _bstr_t::Data_t *, __int64 *))(*(_QWORD *)v45 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v46);
    v14 = v13(v12, *a2, &v46);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x698,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v14,
        v40);
    v15 = v46;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v46 + 80LL);
    v17 = (HSTRING)v48[0];
    if ( v48[0] )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v44);
      WindowsDeleteString(v17);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v44);
    }
    v48[0] = 0;
    v18 = v16(v15, v48);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x69A,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v18,
        v40);
    if ( g_ApiWindowsGetStringRawBuffer )
    {
      StringRawBuffer = g_ApiWindowsGetStringRawBuffer();
    }
    else
    {
      SetLastError(0x32u);
      StringRawBuffer = 0;
    }
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(StringRawBuffer + 2 * v20) );
    std::wstring::_Assign<unsigned short>(&v49, StringRawBuffer);
  }
  else
  {
    v34 = *a2;
    v44 = *a2;
    if ( a3 )
    {
      if ( v34 )
        (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v34 + 8LL))(v34);
      StoreAppManifestPathFromPackageSr = StoreApplication::GetStoreAppManifestPathFromPackageSr(v53, &v44, 1);
      if ( &v51 != (__int128 *)StoreAppManifestPathFromPackageSr )
      {
        std::wstring::_Tidy_deallocate(&v51);
        v51 = *(_OWORD *)StoreAppManifestPathFromPackageSr;
        v52 = *(_OWORD *)(StoreAppManifestPathFromPackageSr + 16);
        *(_QWORD *)(StoreAppManifestPathFromPackageSr + 16) = 0;
        *(_QWORD *)(StoreAppManifestPathFromPackageSr + 24) = 7;
        *(_WORD *)StoreAppManifestPathFromPackageSr = 0;
      }
      std::wstring::~wstring(v53);
      if ( v34 )
        (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v34 + 16LL))(v34);
      v36 = StoreApplication::LoadXmlFromFileSr(v53, &v51);
      if ( &v49 != (__int128 *)v36 )
      {
        std::wstring::_Tidy_deallocate(&v49);
        v49 = *(_OWORD *)v36;
        v50 = *(_OWORD *)(v36 + 16);
        *(_QWORD *)(v36 + 16) = 0;
        *(_QWORD *)(v36 + 24) = 7;
        *(_WORD *)v36 = 0;
      }
    }
    else
    {
      if ( v34 )
        (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v34 + 8LL))(v34);
      StoreApplication::GetStoreAppManifestPathFromPackageSr(v53, &v44, 2);
      if ( v34 )
        (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v34 + 16LL))(v34);
      XmlFromFileSr = StoreApplication::LoadXmlFromFileSr(v55, v53);
      if ( &v49 != (__int128 *)XmlFromFileSr )
      {
        std::wstring::_Tidy_deallocate(&v49);
        v49 = *(_OWORD *)XmlFromFileSr;
        v50 = *(_OWORD *)(XmlFromFileSr + 16);
        *(_QWORD *)(XmlFromFileSr + 16) = 0;
        *(_QWORD *)(XmlFromFileSr + 24) = 7;
        *(_WORD *)XmlFromFileSr = 0;
      }
      std::wstring::~wstring(v55);
    }
    std::wstring::~wstring(v53);
  }
  if ( (_QWORD)v50 )
  {
    if ( !(_QWORD)v52 )
    {
      v44 = *a2;
      v21 = v44;
      if ( v44 )
        (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v44 + 8LL))(v44);
      v22 = StoreApplication::GetStoreAppManifestPathFromPackageSr(v55, &v44, 1);
      if ( &v51 != (__int128 *)v22 )
      {
        std::wstring::_Tidy_deallocate(&v51);
        v51 = *(_OWORD *)v22;
        v52 = *(_OWORD *)(v22 + 16);
        *(_QWORD *)(v22 + 16) = 0;
        *(_QWORD *)(v22 + 24) = 7;
        *(_WORD *)v22 = 0;
      }
      std::wstring::~wstring(v55);
      if ( v21 )
        (*(void (__fastcall **)(_bstr_t::Data_t *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v43 = 0;
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&ppv);
    v23 = CoCreateInstance(
            &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
            0,
            1u,
            &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
            &ppv);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6B7,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v23,
        v41);
    v24 = ppv;
    v25 = *(void (__fastcall **)(LPVOID, __int64, __int16 *))(*(_QWORD *)ppv + 520LL);
    v26 = (const unsigned __int16 *)&v49;
    if ( *((_QWORD *)&v50 + 1) > 7u )
      v26 = (const unsigned __int16 *)v49;
    v27 = _bstr_t::_bstr_t((_bstr_t *)&v44, v26);
    if ( *(_QWORD *)v27 )
      v28 = **(_QWORD **)v27;
    else
      v28 = 0;
    v25(v24, v28, &v43);
    if ( v44 )
      _bstr_t::Data_t::Release(v44);
    if ( v43 != -1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6B9,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)0xC00CE225LL,
        v41);
    StoreApplication::TransformAndLocalizeManifestXml((__int64)v56, (__int64 *)&ppv, (__int64)&v51, a3);
    std::wstring::wstring(a1, v56);
    std::wstring::~wstring(v56);
    v29 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = (HSTRING)v48[0];
    if ( v48[0] )
LABEL_39:
      WindowsDeleteString(v32);
  }
  else
  {
    std::wstring::wstring(a1, &byte_1801389F0);
    v38 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v32 = (HSTRING)v48[0];
    if ( v48[0] )
      goto LABEL_39;
  }
  std::wstring::~wstring(&v51);
  std::wstring::~wstring(&v49);
  return a1;
}

```

## disassembly

```asm
0x180019810  mov     rax, rsp
0x180019813  push    rbp
0x180019814  push    rsi
0x180019815  push    rdi
0x180019816  push    r12
0x180019818  push    r13
0x18001981a  push    r14
0x18001981c  push    r15
0x18001981e  lea     rbp, [rax-58h]
0x180019822  sub     rsp, 120h
0x180019829  mov     qword ptr [rsp+150h+var_E8], 0FFFFFFFFFFFFFFFEh
0x180019832  mov     [rax+18h], rbx
0x180019836  mov     rax, cs:__security_cookie
0x18001983d  xor     rax, rsp
0x180019840  mov     [rbp+50h+var_40], rax
0x180019844  mov     r12b, r8b
0x180019847  mov     r14, rdx
0x18001984a  mov     r15, rcx
0x18001984d  mov     [rsp+150h+var_118], rcx
0x180019852  xor     r13d, r13d
0x180019855  xorps   xmm0, xmm0
0x180019858  movups  xmmword ptr [rsp+150h+var_E8+8], xmm0
0x18001985d  mov     qword ptr [rbp+50h+var_D0], r13
0x180019861  mov     qword ptr [rbp+50h+var_D0+8], r13
0x180019865  xor     r8d, r8d
0x180019868  lea     rdx, byte_1801389F0
0x18001986f  lea     rcx, [rsp+150h+var_E8+8]
0x180019874  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019879  nop
0x18001987a  xorps   xmm0, xmm0
0x18001987d  movups  [rbp+50h+var_C0], xmm0
0x180019881  mov     qword ptr [rbp+50h+var_B0], r13
0x180019885  mov     qword ptr [rbp+50h+var_B0+8], r13
0x180019889  xor     r8d, r8d
0x18001988c  lea     rdx, byte_1801389F0
0x180019893  lea     rcx, [rbp+50h+var_C0]
0x180019897  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001989c  nop
0x18001989d  mov     byte ptr [rsp+150h+var_120], r13b
0x1800198a2  mov     [rsp+58h], r13
0x1800198a7  mov     [rsp+150h+var_110], r13
0x1800198ac  mov     [rsp+150h+var_108], r13
0x1800198b1  mov     [rbp+50h+var_88], r13
0x1800198b5  mov     rax, cs:?g_ApiWindowsCreateStringReference@@3P6A_JXZEA; __int64 (*g_ApiWindowsCreateStringReference)(void)
0x1800198bc  test    rax, rax
0x1800198bf  jz      loc_180019EBD
0x1800198c5  lea     r9, [rbp+50h+var_88]
0x1800198c9  lea     r8, [rbp+50h+var_A0]
0x1800198cd  lea     edx, [r13+2Dh]
0x1800198d1  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_AppxManifest@@3QBGB; "Windows.Internal.StateRepository.AppxMa"...
0x1800198d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198dd  test    eax, eax
0x1800198df  js      loc_180019ECD
0x1800198e5  mov     rbx, [rbp+50h+var_88]
0x1800198e9  lea     rcx, [rsp+150h+var_110]
0x1800198ee  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800198f3  lea     r8, [rsp+150h+var_110]
0x1800198f8  lea     rdx, _GUID_5fc148b1_ad6b_4d3d_b11d_e881979c15f4
0x1800198ff  mov     rcx, rbx
0x180019902  call    RoGetActivationFactory
0x180019907  nop
0x180019908  mov     rcx, [rbp+58h]; this
0x18001990c  test    eax, eax
0x18001990e  js      loc_180019D4C
0x180019914  mov     rcx, [rsp+150h+var_110]
0x180019919  mov     rax, [rcx]
0x18001991c  lea     r8, [rsp+150h+var_120]
0x180019921  mov     rdx, [r14]
0x180019924  mov     rax, [rax+38h]
0x180019928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001992d  mov     rcx, [rbp+58h]; this
0x180019931  test    eax, eax
0x180019933  js      loc_180019D61
0x180019939  lea     esi, [r13+7]
0x18001993d  cmp     byte ptr [rsp+150h+var_120], r13b
0x180019942  jz      loc_180019BED
0x180019948  test    r12b, r12b
0x18001994b  jz      loc_180019BED
0x180019951  mov     rdi, [rsp+150h+var_110]
0x180019956  mov     rax, [rdi]
0x180019959  mov     rbx, [rax+58h]
0x18001995d  lea     rcx, [rsp+150h+var_108]
0x180019962  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180019967  lea     r8, [rsp+150h+var_108]
0x18001996c  mov     rdx, [r14]
0x18001996f  mov     rcx, rdi
0x180019972  mov     rax, rbx
0x180019975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001997a  mov     rcx, [rbp+58h]; this
0x18001997e  test    eax, eax
0x180019980  js      loc_180019D76
0x180019986  mov     rdi, [rsp+150h+var_108]
0x18001998b  mov     rax, [rdi]
0x18001998e  mov     rsi, [rax+50h]
0x180019992  mov     rbx, [rsp+58h]
0x180019997  test    rbx, rbx
0x18001999a  jnz     loc_180019D8B
0x1800199a0  mov     [rsp+58h], r13
0x1800199a5  lea     rdx, [rsp+58h]
0x1800199aa  mov     rcx, rdi
0x1800199ad  mov     rax, rsi
0x1800199b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199b5  mov     rcx, [rbp+58h]; this
0x1800199b9  test    eax, eax
0x1800199bb  js      loc_180019DAD
0x1800199c1  mov     rax, cs:?g_ApiWindowsGetStringRawBuffer@@3P6A_JXZEA; __int64 (*g_ApiWindowsGetStringRawBuffer)(void)
0x1800199c8  test    rax, rax
0x1800199cb  jz      loc_180019DC2
0x1800199d1  xor     edx, edx
0x1800199d3  mov     rcx, [rsp+58h]
0x1800199d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199dd  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800199e1  inc     r8
0x1800199e4  cmp     [rax+r8*2], r13w
0x1800199e9  jnz     short loc_1800199E1
0x1800199eb  mov     rdx, rax
0x1800199ee  lea     rcx, [rsp+150h+var_E8+8]
0x1800199f3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800199f8  mov     esi, 7
0x1800199fd  cmp     qword ptr [rbp+50h+var_D0], r13
0x180019a01  jz      loc_180019CEB
0x180019a07  cmp     qword ptr [rbp+50h+var_B0], r13
0x180019a0b  jnz     short loc_180019A6D
0x180019a0d  mov     rbx, [r14]
0x180019a10  mov     [rsp+150h+var_118], rbx
0x180019a15  test    rbx, rbx
0x180019a18  jz      short loc_180019A2A
0x180019a1a  mov     rax, [rbx]
0x180019a1d  mov     rcx, rbx
0x180019a20  mov     rax, [rax+8]
0x180019a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a29  nop
0x180019a2a  mov     r8d, 1
0x180019a30  lea     rdx, [rsp+150h+var_118]
0x180019a35  lea     rcx, [rbp+50h+var_80]
0x180019a39  call    ?GetStoreAppManifestPathFromPackageSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@W4ManifestType@@@Z; StoreApplication::GetStoreAppManifestPathFromPackageSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,ManifestType)
0x180019a3e  mov     rdi, rax
0x180019a41  lea     rax, [rbp+50h+var_C0]
0x180019a45  cmp     rax, rdi
0x180019a48  jnz     loc_180019E54
0x180019a4e  lea     rcx, [rbp+50h+var_80]
0x180019a52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019a57  nop
0x180019a58  test    rbx, rbx
0x180019a5b  jz      short loc_180019A6D
0x180019a5d  mov     rax, [rbx]
0x180019a60  mov     rcx, rbx
0x180019a63  mov     rax, [rax+10h]
0x180019a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a6c  nop
0x180019a6d  mov     word ptr [rsp+150h+var_120+4], r13w
0x180019a73  mov     [rsp+150h+ppv], r13
0x180019a78  lea     rcx, [rsp+150h+ppv]
0x180019a7d  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180019a82  lea     rax, [rsp+150h+ppv]
0x180019a87  mov     [rsp+20h], rax; int
0x180019a8c  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180019a93  xor     edx, edx; pUnkOuter
0x180019a95  lea     r8d, [rdx+1]; dwClsContext
0x180019a99  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180019aa0  call    cs:__imp_CoCreateInstance
0x180019aa6  mov     rcx, [rbp+58h]; this
0x180019aaa  test    eax, eax
0x180019aac  js      loc_180019E7D
0x180019ab2  mov     rbx, [rsp+150h+ppv]
0x180019ab7  mov     rax, [rbx]
0x180019aba  mov     rdi, [rax+208h]
0x180019ac1  lea     rdx, [rsp+150h+var_E8+8]
0x180019ac6  cmp     qword ptr [rbp+50h+var_D0+8], rsi
0x180019aca  cmova   rdx, qword ptr [rsp+150h+var_E8+8]; unsigned __int16 *
0x180019ad0  lea     rcx, [rsp+150h+var_118]; this
0x180019ad5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180019ada  nop
0x180019adb  mov     rdx, [rax]
0x180019ade  test    rdx, rdx
0x180019ae1  jz      loc_180019E92
0x180019ae7  mov     rdx, [rdx]
0x180019aea  lea     r8, [rsp+150h+var_120+4]
0x180019aef  mov     rcx, rbx
0x180019af2  mov     rax, rdi
0x180019af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019afa  nop
0x180019afb  mov     rcx, [rsp+150h+var_118]; this
0x180019b00  test    rcx, rcx
0x180019b03  jz      short loc_180019B0A
0x180019b05  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x180019b0a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019b0e  cmp     word ptr [rsp+150h+var_120+4], ax
0x180019b13  setz    al
0x180019b16  mov     rcx, [rbp+58h]; this
0x180019b1a  test    al, al
0x180019b1c  jz      loc_180019E9A
0x180019b22  mov     r9b, r12b
0x180019b25  lea     r8, [rbp+50h+var_C0]
0x180019b29  lea     rdx, [rsp+150h+ppv]
0x180019b2e  lea     rcx, [rbp+50h+var_60]
0x180019b32  call    ?TransformAndLocalizeManifestXml@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIXMLDOMDocument@@@WRL@Microsoft@@AEBV23@_N@Z; StoreApplication::TransformAndLocalizeManifestXml(Microsoft::WRL::ComPtr<IXMLDOMDocument> const &,std::wstring const &,bool)
0x180019b37  lea     rdx, [rbp+50h+var_60]
0x180019b3b  mov     rcx, r15
0x180019b3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180019b43  lea     rcx, [rbp+50h+var_60]
0x180019b47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019b4c  nop
0x180019b4d  mov     rcx, [rsp+150h+ppv]
0x180019b52  test    rcx, rcx
0x180019b55  jz      short loc_180019B69
0x180019b57  mov     [rsp+150h+ppv], r13
0x180019b5c  mov     rax, [rcx]
0x180019b5f  mov     rax, [rax+10h]
0x180019b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b68  nop
0x180019b69  mov     rcx, [rsp+150h+var_108]
0x180019b6e  test    rcx, rcx
0x180019b71  jz      short loc_180019B85
0x180019b73  mov     [rsp+150h+var_108], r13
0x180019b78  mov     rax, [rcx]
0x180019b7b  mov     rax, [rax+10h]
0x180019b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b84  nop
0x180019b85  mov     rcx, [rsp+150h+var_110]
0x180019b8a  test    rcx, rcx
0x180019b8d  jz      short loc_180019BA1
0x180019b8f  mov     [rsp+150h+var_110], r13
0x180019b94  mov     rax, [rcx]
0x180019b97  mov     rax, [rax+10h]
0x180019b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ba0  nop
0x180019ba1  mov     rcx, [rsp+58h]; string
0x180019ba6  test    rcx, rcx
0x180019ba9  jnz     loc_180019EB2
0x180019baf  lea     rcx, [rbp+50h+var_C0]
0x180019bb3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019bb8  nop
0x180019bb9  lea     rcx, [rsp+150h+var_E8+8]
0x180019bbe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019bc3  mov     rax, r15
0x180019bc6  mov     rcx, [rbp+50h+var_40]
0x180019bca  xor     rcx, rsp; StackCookie
0x180019bcd  call    __security_check_cookie
0x180019bd2  mov     rbx, [rsp+150h+arg_10]
0x180019bda  add     rsp, 120h
0x180019be1  pop     r15
0x180019be3  pop     r14
0x180019be5  pop     r13
0x180019be7  pop     r12
0x180019be9  pop     rdi
0x180019bea  pop     rsi
0x180019beb  pop     rbp
0x180019bec  retn
0x180019bed  mov     rbx, [r14]
0x180019bf0  mov     [rsp+150h+var_118], rbx
0x180019bf5  test    r12b, r12b
0x180019bf8  jz      loc_180019C82
0x180019bfe  test    rbx, rbx
0x180019c01  jz      short loc_180019C13
0x180019c03  mov     rax, [rbx]
0x180019c06  mov     rcx, rbx
0x180019c09  mov     rax, [rax+8]
0x180019c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c12  nop
0x180019c13  mov     r8d, 1
0x180019c19  lea     rdx, [rsp+150h+var_118]
0x180019c1e  lea     rcx, [rbp+50h+var_A0]
0x180019c22  call    ?GetStoreAppManifestPathFromPackageSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@W4ManifestType@@@Z; StoreApplication::GetStoreAppManifestPathFromPackageSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,ManifestType)
0x180019c27  mov     rdi, rax
0x180019c2a  lea     rax, [rbp+50h+var_C0]
0x180019c2e  cmp     rax, rdi
0x180019c31  jnz     loc_180019DD5
0x180019c37  lea     rcx, [rbp+50h+var_A0]
0x180019c3b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019c40  nop
0x180019c41  test    rbx, rbx
0x180019c44  jz      short loc_180019C56
0x180019c46  mov     rax, [rbx]
0x180019c49  mov     rcx, rbx
0x180019c4c  mov     rax, [rax+10h]
0x180019c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c55  nop
0x180019c56  lea     rdx, [rbp+50h+var_C0]
0x180019c5a  lea     rcx, [rbp+50h+var_A0]
0x180019c5e  call    ?LoadXmlFromFileSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; StoreApplication::LoadXmlFromFileSr(std::wstring const &)
0x180019c63  mov     rbx, rax
0x180019c66  lea     rax, [rsp+150h+var_E8+8]
0x180019c6b  cmp     rax, rbx
0x180019c6e  jnz     loc_180019DFE
0x180019c74  lea     rcx, [rbp+50h+var_A0]
0x180019c78  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019c7d  jmp     loc_1800199FD
0x180019c82  test    rbx, rbx
0x180019c85  jz      short loc_180019C97
0x180019c87  mov     rax, [rbx]
0x180019c8a  mov     rcx, rbx
0x180019c8d  mov     rax, [rax+8]
0x180019c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c96  nop
0x180019c97  mov     r8d, 2
0x180019c9d  lea     rdx, [rsp+150h+var_118]
0x180019ca2  lea     rcx, [rbp+50h+var_A0]
0x180019ca6  call    ?GetStoreAppManifestPathFromPackageSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@W4ManifestType@@@Z; StoreApplication::GetStoreAppManifestPathFromPackageSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,ManifestType)
0x180019cab  nop
  ... truncated ...
```
