# StoreApplication::GetStoreAppLanguageSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)

- ea: `0x180044e70`
- end: `0x18004545f`
- name: `?GetStoreAppLanguageSr@StoreApplication@@SAKAEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `1519`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a5f8`

## callees

- `0x18000a39c`
- `0x180018a60`
- `0x180019810`
- `0x18001d31c`
- `0x1800213f0`
- `0x180028404`
- `0x1800293b0`
- `0x180044e70`
- `0x180045468`
- `0x180045480`
- `0x180053948`
- `0x180059920`
- `0x1800679f8`
- `0x1801003f4`
- `0x180130010`

## import_xrefs

- `KERNEL32!LocaleNameToLCID` at `0x180045309`
- `KERNEL32!LocaleNameToLCID` at `0x180045309`
- `KERNEL32!RaiseException` at `0x180044f2e`
- `KERNEL32!RaiseException` at `0x180044f2e`
- `KERNEL32!SetLastError` at `0x180044f19`
- `KERNEL32!SetLastError` at `0x180045409`
- `KERNEL32!SetLastError` at `0x180045421`
- `KERNEL32!SetLastError` at `0x180044f19`
- `KERNEL32!SetLastError` at `0x180045409`
- `KERNEL32!SetLastError` at `0x180045421`

## string_xrefs

- `0x180044f02`: `Windows.Data.Xml.Dom.XmlDocument`
- `0x180044f64`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180044fb2`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18004501f`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180045072`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800450f9`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18004511d`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x180045159`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800451eb`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18004520f`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18004525a`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800452a8`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=29 #try_helpers=1
__int64 StoreApplication::GetStoreAppLanguageSr()
{
  _bstr_t::Data_t **v0; // rdx
  __int64 v1; // rbx
  int v2; // eax
  __int64 (__fastcall ***v3)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rdi
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64); // rbx
  _QWORD *v8; // rdx
  __int64 v9; // rdx
  int v10; // eax
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v12)(_QWORD, GUID *, _QWORD **); // rdi
  int v13; // eax
  _QWORD *v14; // rbx
  __int64 v15; // rdi
  int StringReference; // eax
  int v17; // edx
  unsigned int v18; // r8d
  int v19; // eax
  const char *v20; // r9
  int v21; // eax
  _QWORD *v22; // rbx
  __int64 v23; // rdi
  int v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  int v27; // eax
  const char *v28; // r9
  __int64 v29; // rbx
  __int64 (__fastcall *v30)(__int64, __int64 *); // rdi
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rbx
  int v34; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v36; // r8
  const WCHAR *p_lpName; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  _QWORD *v40; // rcx
  __int64 v41; // rcx
  _QWORD *v42; // rcx
  __int64 v43; // rcx
  __int64 (__fastcall ***v44)(_QWORD, _QWORD, _QWORD); // rcx
  int v46; // [rsp+20h] [rbp-F8h]
  HSTRING string; // [rsp+30h] [rbp-E8h] BYREF
  __int64 (__fastcall ***v48)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-E0h] BYREF
  LCID v49; // [rsp+40h] [rbp-D8h]
  __int64 v50; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+50h] [rbp-C8h] BYREF
  _QWORD *v52; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+60h] [rbp-B8h] BYREF
  _QWORD *v54; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+70h] [rbp-A8h] BYREF
  _QWORD v56[5]; // [rsp+78h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v58; // [rsp+B8h] [rbp-60h]
  __int128 lpName; // [rsp+C0h] [rbp-58h] BYREF
  __int128 v60; // [rsp+D0h] [rbp-48h]
  _QWORD v61[4]; // [rsp+E0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v56[1] = -2;
  v49 = 1033;
  lpName = 0;
  v60 = 0;
  std::wstring::_Construct_empty(&lpName);
  StoreApplication::GetStoreAppManifestXmlSr((_bstr_t::Data_t *)v61, v0, 1);
  v48 = 0;
  v53 = 0;
  if ( !g_ApiWindowsCreateStringReference )
  {
    SetLastError(0x32u);
    goto LABEL_5;
  }
  if ( (int)g_ApiWindowsCreateStringReference() < 0 )
LABEL_5:
    RaiseException(0xC000000D, 1u, 0, 0);
  v1 = v57;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v48);
  v2 = Windows::Foundation::ActivateInstance<Windows::Data::Xml::Dom::IXmlDocument>(v1, &v48);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x295,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v2,
      v46);
  v3 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v48;
  v4 = **v48;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v53);
  v5 = v4(v3, &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637, &v53);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x297,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v5,
      v46);
  v6 = v53;
  v7 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 48LL);
  v8 = v61;
  if ( v61[3] > 7u )
    v8 = (_QWORD *)v61[0];
  v56[0] = v8;
  v9 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v57, v56) + 24);
  v10 = v7(v6, v9);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x298,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v10,
      v46);
  v52 = 0;
  v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v48;
  v12 = (__int64 (__fastcall *)(_QWORD, GUID *, _QWORD **))**v48;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v52);
  v13 = v12(v11, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v52);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v13,
      v46);
  v55 = 0;
  v14 = v52;
  v15 = *v52;
  v58 = 0;
  if ( !g_ApiWindowsCreateStringReference )
    goto LABEL_57;
  StringReference = g_ApiWindowsCreateStringReference();
  if ( StringReference < 0 )
  {
LABEL_58:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v17, v18);
    return v49;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v15 + 48))(v14, v58, &v55);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x29F,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v19,
      v46);
  if ( !v55 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2A0,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      v20);
  v54 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v55 + 128LL))(v55, &v54);
  if ( v21 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v21,
      v46);
  v51 = 0;
  v22 = v54;
  v23 = *v54;
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v51);
  v58 = 0;
  if ( !g_ApiWindowsCreateStringReference )
  {
    SetLastError(0x32u);
    v24 = -2147467263;
    goto LABEL_56;
  }
  v24 = g_ApiWindowsCreateStringReference();
  if ( v24 < 0 )
  {
LABEL_56:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
LABEL_57:
    SetLastError(0x32u);
    StringReference = -2147467263;
    goto LABEL_58;
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v23 + 64))(v22, v58, &v51);
  if ( v27 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v27,
      v46);
  v29 = v51;
  if ( !v51 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2A8,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      v28);
  v50 = 0;
  string = 0;
  v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v50);
  v31 = v30(v29, &v50);
  if ( v31 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2AC,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v31,
      v46);
  v32 = v50;
  v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v50 + 152LL);
  WindowsDeleteString(string);
  string = 0;
  v34 = v33(v32, &string);
  if ( v34 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2AD,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v34,
      v46);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v36 = -1;
  do
    ++v36;
  while ( StringRawBuffer[v36] );
  std::wstring::_Assign<unsigned short>(&lpName, StringRawBuffer);
  if ( (_QWORD)v60 )
  {
    p_lpName = (const WCHAR *)&lpName;
    if ( *((_QWORD *)&v60 + 1) > 7u )
      p_lpName = (const WCHAR *)lpName;
    v49 = LocaleNameToLCID(p_lpName, 0);
  }
  WindowsDeleteString(string);
  string = 0;
  v38 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v39 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v40 = v54;
  if ( v54 )
  {
    v54 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
  }
  v41 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v42 + 16LL))(v42);
  }
  v43 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v48;
  if ( v48 )
  {
    v48 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v44)[2])(v44);
  }
  std::wstring::~wstring(v61);
  std::wstring::~wstring(&lpName);
  return v49;
}

```

## disassembly

```asm
0x180044e70  mov     r11, rsp
0x180044e73  push    rdi
0x180044e74  sub     rsp, 110h
0x180044e7b  mov     qword ptr [r11-98h], 0FFFFFFFFFFFFFFFEh
0x180044e86  mov     [r11+10h], rbx
0x180044e8a  mov     [r11+18h], rsi
0x180044e8e  mov     rax, cs:__security_cookie
0x180044e95  xor     rax, rsp
0x180044e98  mov     [rsp+118h+var_18], rax
0x180044ea0  mov     rdx, rcx
0x180044ea3  mov     [rsp+118h+var_D8], 409h
0x180044eab  xorps   xmm0, xmm0
0x180044eae  movups  xmmword ptr [r11-58h], xmm0
0x180044eb3  xorps   xmm1, xmm1
0x180044eb6  movdqu  xmmword ptr [r11-48h], xmm1
0x180044ebc  lea     rcx, [r11-58h]
0x180044ec0  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180044ec5  nop
0x180044ec6  mov     r8b, 1
0x180044ec9  lea     rcx, [rsp+118h+var_38]
0x180044ed1  call    ?GetStoreAppManifestXmlSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@_N@Z; StoreApplication::GetStoreAppManifestXmlSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,bool)
0x180044ed6  nop
0x180044ed7  xor     esi, esi
0x180044ed9  mov     [rsp+118h+var_E0], rsi
0x180044ede  mov     [rsp+118h+var_B8], rsi
0x180044ee3  mov     rax, cs:?g_ApiWindowsCreateStringReference@@3P6A_JXZEA; __int64 (*g_ApiWindowsCreateStringReference)(void)
0x180044eea  test    rax, rax
0x180044eed  jz      short loc_180044F14
0x180044eef  lea     r9, [rsp+118h+var_78]
0x180044ef7  lea     r8, [rsp+118h+var_70]
0x180044eff  lea     edx, [rsi+20h]
0x180044f02  lea     rcx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x180044f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f0e  test    eax, eax
0x180044f10  js      short loc_180044F1F
0x180044f12  jmp     short loc_180044F35
0x180044f14  mov     ecx, 32h ; '2'; dwErrCode
0x180044f19  call    cs:__imp_SetLastError
0x180044f1f  xor     r9d, r9d; lpArguments
0x180044f22  xor     r8d, r8d; nNumberOfArguments
0x180044f25  lea     edx, [r9+1]; dwExceptionFlags
0x180044f29  mov     ecx, 0C000000Dh; dwExceptionCode
0x180044f2e  call    cs:__imp_RaiseException
0x180044f34  nop
0x180044f35  mov     rbx, [rsp+118h+var_78]
0x180044f3d  lea     rcx, [rsp+118h+var_E0]
0x180044f42  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180044f47  lea     rdx, [rsp+118h+var_E0]
0x180044f4c  mov     rcx, rbx
0x180044f4f  call    ??$ActivateInstance@UIXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIXmlDocument@Dom@Xml@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Xml::Dom::IXmlDocument>(HSTRING__ *,Windows::Data::Xml::Dom::IXmlDocument * *)
0x180044f54  nop
0x180044f55  mov     rcx, [rsp+118h]; this
0x180044f5d  test    eax, eax
0x180044f5f  jns     short loc_180044F76
0x180044f61  mov     r9d, eax; char *
0x180044f64  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180044f6b  mov     edx, 295h; void *
0x180044f70  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180044f76  mov     rbx, [rsp+118h+var_E0]
0x180044f7b  mov     rax, [rbx]
0x180044f7e  mov     rdi, [rax]
0x180044f81  lea     rcx, [rsp+118h+var_B8]
0x180044f86  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180044f8b  lea     r8, [rsp+118h+var_B8]
0x180044f90  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x180044f97  mov     rcx, rbx
0x180044f9a  mov     rax, rdi
0x180044f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044fa2  nop
0x180044fa3  mov     rcx, [rsp+118h]; this
0x180044fab  test    eax, eax
0x180044fad  jns     short loc_180044FC3
0x180044faf  mov     r9d, eax; char *
0x180044fb2  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180044fb9  mov     edx, 297h; void *
0x180044fbe  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180044fc3  mov     rdi, [rsp+118h+var_B8]
0x180044fc8  mov     rax, [rdi]
0x180044fcb  mov     rbx, [rax+30h]
0x180044fcf  lea     rdx, [rsp+118h+var_38]
0x180044fd7  cmp     [rsp+118h+var_20], 7
0x180044fe0  cmova   rdx, [rsp+118h+var_38]
0x180044fe9  mov     [rsp+118h+var_A0], rdx
0x180044fee  lea     rdx, [rsp+118h+var_A0]
0x180044ff3  lea     rcx, [rsp+118h+var_78]
0x180044ffb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180045000  nop
0x180045001  mov     rdx, [rax+18h]
0x180045005  mov     rcx, rdi
0x180045008  mov     rax, rbx
0x18004500b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045010  mov     rcx, [rsp+118h]; this
0x180045018  test    eax, eax
0x18004501a  jns     short loc_180045031
0x18004501c  mov     r9d, eax; char *
0x18004501f  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180045026  mov     edx, 298h; void *
0x18004502b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180045031  mov     [rsp+118h+var_C0], rsi
0x180045036  mov     rbx, [rsp+118h+var_E0]
0x18004503b  mov     rax, [rbx]
0x18004503e  mov     rdi, [rax]
0x180045041  lea     rcx, [rsp+118h+var_C0]
0x180045046  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18004504b  lea     r8, [rsp+118h+var_C0]
0x180045050  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x180045057  mov     rcx, rbx
0x18004505a  mov     rax, rdi
0x18004505d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045062  nop
0x180045063  mov     rcx, [rsp+118h]; this
0x18004506b  test    eax, eax
0x18004506d  jns     short loc_180045083
0x18004506f  mov     r9d, eax; char *
0x180045072  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180045079  mov     edx, 29Bh; void *
0x18004507e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180045083  mov     [rsp+118h+var_A8], rsi
0x180045088  mov     rbx, [rsp+118h+var_C0]
0x18004508d  mov     rdi, [rbx]
0x180045090  mov     [rsp+118h+var_60], rsi
0x180045098  mov     rax, cs:?g_ApiWindowsCreateStringReference@@3P6A_JXZEA; __int64 (*g_ApiWindowsCreateStringReference)(void)
0x18004509f  test    rax, rax
0x1800450a2  jz      loc_18004541C
0x1800450a8  lea     r9, [rsp+118h+var_60]
0x1800450b0  lea     r8, [rsp+118h+var_78]
0x1800450b8  mov     edx, 54h ; 'T'
0x1800450bd  lea     rcx, aLocalNamePacka; "/*[local-name()='Package']/*[local-name"...
0x1800450c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450c9  test    eax, eax
0x1800450cb  js      loc_18004542C
0x1800450d1  lea     r8, [rsp+118h+var_A8]
0x1800450d6  mov     rdx, [rsp+118h+var_60]
0x1800450de  mov     rcx, rbx
0x1800450e1  mov     rax, [rdi+30h]
0x1800450e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450ea  mov     rcx, [rsp+118h]; this
0x1800450f2  test    eax, eax
0x1800450f4  jns     short loc_18004510B
0x1800450f6  mov     r9d, eax; char *
0x1800450f9  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180045100  mov     edx, 29Fh; void *
0x180045105  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004510b  mov     rax, [rsp+118h]
0x180045113  mov     rcx, [rsp+118h+var_A8]
0x180045118  test    rcx, rcx
0x18004511b  jnz     short loc_180045131
0x18004511d  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180045124  mov     edx, 2A0h; void *
0x180045129  mov     rcx, rax; this
0x18004512c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180045131  mov     [rsp+118h+var_B0], rsi
0x180045136  mov     rax, [rcx]
0x180045139  lea     rdx, [rsp+118h+var_B0]
0x18004513e  mov     rax, [rax+80h]
0x180045145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004514a  mov     rcx, [rsp+118h]; this
0x180045152  test    eax, eax
0x180045154  jns     short loc_18004516A
0x180045156  mov     r9d, eax; char *
0x180045159  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180045160  mov     edx, 2A3h; void *
0x180045165  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004516a  mov     [rsp+118h+var_C8], rsi
0x18004516f  mov     rbx, [rsp+118h+var_B0]
0x180045174  mov     rdi, [rbx]
0x180045177  lea     rcx, [rsp+118h+var_C8]
0x18004517c  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x180045181  nop
0x180045182  mov     [rsp+118h+var_60], rsi
0x18004518a  mov     rax, cs:?g_ApiWindowsCreateStringReference@@3P6A_JXZEA; __int64 (*g_ApiWindowsCreateStringReference)(void)
0x180045191  test    rax, rax
0x180045194  jz      loc_180045404
0x18004519a  lea     r9, [rsp+118h+var_60]
0x1800451a2  lea     r8, [rsp+118h+var_78]
0x1800451aa  mov     edx, 8
0x1800451af  lea     rcx, aLanguage; "Language"
0x1800451b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451bb  test    eax, eax
0x1800451bd  js      loc_180045414
0x1800451c3  lea     r8, [rsp+118h+var_C8]
0x1800451c8  mov     rdx, [rsp+118h+var_60]
0x1800451d0  mov     rcx, rbx
0x1800451d3  mov     rax, [rdi+40h]
0x1800451d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451dc  mov     rcx, [rsp+118h]; this
0x1800451e4  test    eax, eax
0x1800451e6  jns     short loc_1800451FD
0x1800451e8  mov     r9d, eax; char *
0x1800451eb  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800451f2  mov     edx, 2A7h; void *
0x1800451f7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800451fd  mov     rcx, [rsp+118h]; this
0x180045205  mov     rbx, [rsp+118h+var_C8]
0x18004520a  test    rbx, rbx
0x18004520d  jnz     short loc_180045220
0x18004520f  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180045216  mov     edx, 2A8h; void *
0x18004521b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180045220  mov     [rsp+118h+var_D0], rsi
0x180045225  mov     [rsp+118h+string], rsi
0x18004522a  mov     rax, [rbx]
0x18004522d  mov     rdi, [rax+30h]
0x180045231  lea     rcx, [rsp+118h+var_D0]
0x180045236  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18004523b  lea     rdx, [rsp+118h+var_D0]
0x180045240  mov     rcx, rbx
0x180045243  mov     rax, rdi
0x180045246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004524b  mov     rcx, [rsp+118h]; this
0x180045253  test    eax, eax
0x180045255  jns     short loc_18004526B
0x180045257  mov     r9d, eax; char *
0x18004525a  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x180045261  mov     edx, 2ACh; void *
0x180045266  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004526b  mov     rdi, [rsp+118h+var_D0]
0x180045270  mov     rax, [rdi]
0x180045273  mov     rbx, [rax+98h]
0x18004527a  mov     rcx, [rsp+118h+string]; string
0x18004527f  call    WindowsDeleteString
0x180045284  mov     [rsp+118h+string], rsi
0x180045289  lea     rdx, [rsp+118h+string]
0x18004528e  mov     rcx, rdi
0x180045291  mov     rax, rbx
0x180045294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045299  mov     rcx, [rsp+118h]; this
0x1800452a1  test    eax, eax
0x1800452a3  jns     short loc_1800452B9
0x1800452a5  mov     r9d, eax; char *
0x1800452a8  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x1800452af  mov     edx, 2ADh; void *
0x1800452b4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800452b9  xor     edx, edx; length
0x1800452bb  mov     rcx, [rsp+118h+string]; string
0x1800452c0  call    WindowsGetStringRawBuffer
0x1800452c5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800452c9  inc     r8
0x1800452cc  cmp     [rax+r8*2], si
0x1800452d1  jnz     short loc_1800452C9
0x1800452d3  mov     rdx, rax
0x1800452d6  lea     rcx, [rsp+118h+lpName]
0x1800452de  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800452e3  cmp     [rsp+118h+var_48], rsi
0x1800452eb  jbe     short loc_180045313
0x1800452ed  lea     rcx, [rsp+118h+lpName]
0x1800452f5  cmp     [rsp+118h+var_40], 7
0x1800452fe  cmova   rcx, qword ptr [rsp+118h+lpName]; lpName
0x180045307  xor     edx, edx; dwFlags
0x180045309  call    cs:__imp_LocaleNameToLCID
0x18004530f  mov     [rsp+118h+var_D8], eax
0x180045313  mov     rcx, [rsp+118h+string]; string
0x180045318  call    WindowsDeleteString
0x18004531d  mov     [rsp+118h+string], rsi
0x180045322  mov     rcx, [rsp+118h+var_D0]
0x180045327  test    rcx, rcx
0x18004532a  jz      short loc_18004533E
0x18004532c  mov     [rsp+118h+var_D0], rsi
0x180045331  mov     rax, [rcx]
0x180045334  mov     rax, [rax+10h]
0x180045338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004533d  nop
0x18004533e  mov     rcx, [rsp+118h+var_C8]
0x180045343  test    rcx, rcx
0x180045346  jz      short loc_18004535A
0x180045348  mov     [rsp+118h+var_C8], rsi
0x18004534d  mov     rax, [rcx]
0x180045350  mov     rax, [rax+10h]
0x180045354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045359  nop
0x18004535a  mov     rcx, [rsp+118h+var_B0]
0x18004535f  test    rcx, rcx
0x180045362  jz      short loc_180045376
0x180045364  mov     [rsp+118h+var_B0], rsi
0x180045369  mov     rax, [rcx]
0x18004536c  mov     rax, [rax+10h]
0x180045370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045375  nop
0x180045376  mov     rcx, [rsp+118h+var_A8]
0x18004537b  test    rcx, rcx
0x18004537e  jz      short loc_180045392
0x180045380  mov     [rsp+118h+var_A8], rsi
0x180045385  mov     rax, [rcx]
0x180045388  mov     rax, [rax+10h]
0x18004538c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045391  nop
0x180045392  mov     rcx, [rsp+118h+var_C0]
0x180045397  test    rcx, rcx
0x18004539a  jz      short loc_1800453AE
0x18004539c  mov     [rsp+118h+var_C0], rsi
0x1800453a1  mov     rax, [rcx]
0x1800453a4  mov     rax, [rax+10h]
0x1800453a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453ad  nop
0x1800453ae  mov     rcx, [rsp+118h+var_B8]
0x1800453b3  test    rcx, rcx
0x1800453b6  jz      short loc_1800453CA
0x1800453b8  mov     [rsp+118h+var_B8], rsi
0x1800453bd  mov     rax, [rcx]
0x1800453c0  mov     rax, [rax+10h]
  ... truncated ...
```
