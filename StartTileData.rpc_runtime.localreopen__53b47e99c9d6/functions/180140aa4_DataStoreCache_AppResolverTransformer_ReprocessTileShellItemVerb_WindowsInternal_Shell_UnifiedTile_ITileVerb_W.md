# DataStoreCache::AppResolverTransformer::ReprocessTileShellItemVerb(WindowsInternal::Shell::UnifiedTile::ITileVerb *,WindowsInternal::Shell::UnifiedTile::IUnifiedTile *,DataStoreCache::IDataStorePropertyBag *,WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *,WindowsInternal::Shell::UnifiedTile::ITileVerb * *)

- ea: `0x180140aa4`
- end: `0x18014121c`
- name: `?ReprocessTileShellItemVerb@AppResolverTransformer@DataStoreCache@@AEAAJPEAUITileVerb@UnifiedTile@Shell@WindowsInternal@@PEAUIUnifiedTile@456@PEAUIDataStorePropertyBag@2@PEAUIVerbEnumerationArgs@456@PEAPEAU3456@@Z`
- size: `1912`
- prototype: `__int64 __fastcall(DataStoreCache::AppResolverTransformer *__hidden this, struct WindowsInternal::Shell::UnifiedTile::ITileVerb *, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *, struct DataStoreCache::IDataStorePropertyBag *, struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *, struct WindowsInternal::Shell::UnifiedTile::ITileVerb **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18013f6a0`

## callees

- `0x18000ce94`
- `0x180015960`
- `0x18001aca4`
- `0x18003153c`
- `0x18003429c`
- `0x1800385d0`
- `0x18004ffc0`
- `0x1800be128`
- `0x180118dcc`
- `0x18011b860`
- `0x180121374`
- `0x18012500c`
- `0x18012771c`
- `0x180140aa4`
- `0x180201e50`
- `0x18031ce04`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140bac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140bf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140c29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014100a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801410e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801411b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801411d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140bac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140bf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140c29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014100a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801410e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801411b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801411d2`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180140f11`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180140f11`

## string_xrefs

- `0x180140b0c`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x180140b6f`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x180140bda`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x180140c58`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x180140ff5`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x180140e3b`: `OpenFileLocation`
- `0x18014115a`: `TaskbarPin`
- `0x180140cce`: `Uninstall`
- `0x180140ee8`: `Uninstall`
- `0x180141188`: `TaskbarUnpin`
- `0x180140ca3`: `Feature.Uninstall`
- `0x180140d19`: `shellcommon\shell\Tiles\UnifiedTileModel\inc\TileVerbWrapper.h`
- `0x180141042`: `shellcommon\shell\Tiles\UnifiedTileModel\inc\TileVerbWrapper.h`

## pseudocode

```c
__int64 __fastcall DataStoreCache::AppResolverTransformer::ReprocessTileShellItemVerb(
        DataStoreCache::AppResolverTransformer *this,
        struct WindowsInternal::Shell::UnifiedTile::ITileVerb *a2,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *a3,
        struct DataStoreCache::IDataStorePropertyBag *a4,
        struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *a5,
        struct WindowsInternal::Shell::UnifiedTile::ITileVerb **a6)
{
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *v12; // rdi
  __int64 (__fastcall *v13)(WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *, HSTRING *); // rbx
  int v14; // eax
  HSTRING v15; // rcx
  WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *v16; // rdi
  __int64 (__fastcall *v17)(WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *, HSTRING *); // rbx
  int UninstallVerb; // eax
  __int64 v19; // rdx
  unsigned __int64 v20; // r9
  char v21; // bl
  int v22; // eax
  bool v23; // al
  WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *v24; // rbx
  WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *v25; // rbx
  unsigned int v26; // ecx
  int v27; // r8d
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, HSTRING, HSTRING *); // rbx
  int v30; // eax
  __int64 v31; // rdx
  unsigned __int64 v32; // r9
  int v33; // eax
  WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *v34; // rbx
  WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *v35; // rbx
  struct WindowsInternal::Shell::UnifiedTile::ITileVerb *v36; // rax
  int v38; // [rsp+20h] [rbp-C9h]
  HSTRING v39; // [rsp+30h] [rbp-B9h] BYREF
  HSTRING string; // [rsp+38h] [rbp-B1h] BYREF
  WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *v41; // [rsp+40h] [rbp-A9h] BYREF
  bool v42[8]; // [rsp+48h] [rbp-A1h] BYREF
  HSTRING v43; // [rsp+50h] [rbp-99h] BYREF
  WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *v44; // [rsp+58h] [rbp-91h] BYREF
  int v45; // [rsp+60h] [rbp-89h] BYREF
  HSTRING v46; // [rsp+68h] [rbp-81h] BYREF
  HSTRING v47; // [rsp+70h] [rbp-79h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-71h] BYREF
  HSTRING v49; // [rsp+90h] [rbp-59h]
  HSTRING_HEADER v50; // [rsp+98h] [rbp-51h] BYREF
  HSTRING v51; // [rsp+B0h] [rbp-39h]
  HSTRING_HEADER v52; // [rsp+B8h] [rbp-31h] BYREF
  HSTRING v53; // [rsp+D0h] [rbp-19h]
  HSTRING_HEADER v54; // [rsp+D8h] [rbp-11h] BYREF
  HSTRING v55; // [rsp+F0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+4Fh]

  v43 = (HSTRING)a2;
  v45 = 0;
  v9 = (*(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *, int *))(*(_QWORD *)a5 + 48LL))(
         a5,
         &v45);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v44 = 0;
    v42[0] = (v45 & 2) != 0;
    v46 = (HSTRING)*((_QWORD *)this + 32);
    Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::TileVerbSeparator>::InternalRelease(&v44);
    v11 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper,WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper,WindowsInternal::Shell::UnifiedTile::ITileVerb * &,HSTRING__ *,bool>(
            &v44,
            &v43,
            &v46,
            v42);
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x436,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
        (const char *)(unsigned int)v11,
        v38);
LABEL_62:
      Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::TileVerbSeparator>::InternalRelease(&v44);
      return v10;
    }
    v41 = v44;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v41);
    string = 0;
    v12 = v41;
    v13 = *(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *, HSTRING *))(*(_QWORD *)v41 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v14 = v13(v12, &string);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43E,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
        (const char *)(unsigned int)v14,
        v38);
LABEL_7:
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      goto LABEL_62;
    }
    v15 = string;
    if ( string )
    {
LABEL_61:
      v36 = v41;
      v41 = 0;
      *a6 = v36;
      WindowsDeleteString(v15);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      v10 = 0;
      goto LABEL_62;
    }
    v39 = 0;
    v16 = v41;
    v17 = *(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper *, HSTRING *))(*(_QWORD *)v41 + 64LL);
    WindowsDeleteString(0);
    v39 = 0;
    UninstallVerb = v17(v16, &v39);
    v10 = UninstallVerb;
    if ( UninstallVerb < 0 )
    {
      v19 = 1093;
LABEL_11:
      v20 = (unsigned int)UninstallVerb;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
        (const char *)v20,
        v38);
LABEL_13:
      WindowsDeleteString(v39);
      v39 = 0;
      goto LABEL_7;
    }
    v21 = 0;
    v50.Reserved.Reserved1 = this;
    *(_QWORD *)&v50.Reserved.Reserved2[8] = &v41;
    *(_QWORD *)&v50.Reserved.Reserved2[16] = a3;
    v51 = (HSTRING)a5;
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Feature.Uninstall", 0x12u, 0x11u);
    if ( DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v39, v49) )
    {
      UninstallVerb = Microsoft::WRL::Wrappers::HString::Set(
                        (Microsoft::WRL::Wrappers::HString *)&v39,
                        L"Uninstall",
                        9u);
      v10 = UninstallVerb;
      if ( UninstallVerb < 0 )
      {
        v19 = 1124;
        goto LABEL_11;
      }
      v46 = v39;
      v22 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v44 + 10, &v46);
      v10 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x59,
          (unsigned int)"shellcommon\\shell\\Tiles\\UnifiedTileModel\\inc\\TileVerbWrapper.h",
          (const char *)(unsigned int)v22,
          v38);
        v20 = v10;
        v19 = 1125;
        goto LABEL_12;
      }
      v21 = 1;
    }
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Open", 5u, 4u);
    if ( DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v39, v49) )
    {
      UninstallVerb = _lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_::operator()(&v50, 0);
      v10 = UninstallVerb;
      if ( UninstallVerb < 0 )
      {
        v19 = 1131;
        goto LABEL_11;
      }
      goto LABEL_60;
    }
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"RunAs", 6u, 5u);
    if ( DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v39, v49) )
    {
      UninstallVerb = _lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_::operator()(&v50, 1);
      v10 = UninstallVerb;
      if ( UninstallVerb < 0 )
      {
        v19 = 1135;
        goto LABEL_11;
      }
      goto LABEL_60;
    }
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"RunAsUser", 0xAu, 9u);
    if ( DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v39, v49) )
    {
      UninstallVerb = _lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_::operator()(&v50, 2);
      v10 = UninstallVerb;
      if ( UninstallVerb < 0 )
      {
        v19 = 1139;
        goto LABEL_11;
      }
      goto LABEL_60;
    }
    v49 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"OpenFileLocation", 0x11u, 0x10u);
    v23 = DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v39, v49);
    v49 = 0;
    if ( v23 )
    {
      v24 = v44;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        &WindowsInternal::Shell::UnifiedTile::VerbGlyphs::SegoeMDL2Assets::OpenFileLocation,
        2u,
        1u);
      UninstallVerb = WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper::put_Glyph(v24, v49);
      v10 = UninstallVerb;
      if ( UninstallVerb < 0 )
      {
        v19 = 1143;
        goto LABEL_11;
      }
      v25 = v44;
      v49 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Segoe Fluent Icons", 0x13u, 0x12u);
      UninstallVerb = WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper::put_GlyphFontFamily(v25, v49);
      v10 = UninstallVerb;
      if ( UninstallVerb < 0 )
      {
        v19 = 1144;
        goto LABEL_11;
      }
      goto LABEL_60;
    }
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Uninstall", 0xAu, 9u);
    if ( DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v39, v49) )
    {
      if ( !(unsigned int)SHWindowsPolicy(POLID_NoUninstallFromStart) )
      {
        v46 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(struct DataStoreCache::IDataStorePropertyBag *, _GUID **, HSTRING *))(*(_QWORD *)a4 + 32LL))(
               a4,
               &DataStoreCache::AppResolverProperties::UninstallCommand,
               &v46)
          && v46
          && *(_WORD *)v46 )
        {
          UninstallVerb = _lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_::operator()(&v50, 16);
          v10 = UninstallVerb;
          if ( UninstallVerb < 0 )
          {
            v19 = 1156;
            goto LABEL_11;
          }
          goto LABEL_60;
        }
        if ( EnterpriseFeatureControl::IsFeatureEnabled(v26) )
        {
          LOBYTE(v27) = v21;
          UninstallVerb = DataStoreCache::AppResolverTransformer::CreateUninstallVerb(
                            (_DWORD)this,
                            (_DWORD)a5,
                            v27,
                            (_DWORD)a4,
                            (__int64)&v41);
          v10 = UninstallVerb;
          if ( UninstallVerb < 0 )
          {
            v19 = 1163;
            goto LABEL_11;
          }
          goto LABEL_60;
        }
        v43 = 0;
        v28 = *((_QWORD *)this + 31);
        v29 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v28 + 48LL);
        WindowsDeleteString(0);
        v43 = 0;
        v30 = v29(v28, v39, &v43);
        v10 = v30;
        if ( v30 < 0 )
        {
          v31 = 1171;
LABEL_46:
          v32 = (unsigned int)v30;
LABEL_47:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v31,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
            (const char *)v32,
            v38);
          WindowsDeleteString(v43);
          v43 = 0;
          goto LABEL_13;
        }
        v47 = v43;
        v33 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v44 + 11, &v47);
        v10 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5E,
            (unsigned int)"shellcommon\\shell\\Tiles\\UnifiedTileModel\\inc\\TileVerbWrapper.h",
            (const char *)(unsigned int)v33,
            v38);
          v32 = v10;
          v31 = 1172;
          goto LABEL_47;
        }
        v34 = v44;
        v49 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          &WindowsInternal::Shell::UnifiedTile::VerbGlyphs::SegoeMDL2Assets::Uninstall,
          2u,
          1u);
        v30 = WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper::put_Glyph(v34, v49);
        v10 = v30;
        if ( v30 < 0 )
        {
          v31 = 1175;
          goto LABEL_46;
        }
        v35 = v44;
        v49 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Segoe Fluent Icons", 0x13u, 0x12u);
        v30 = WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper::put_GlyphFontFamily(v35, v49);
        v10 = v30;
        if ( v30 < 0 )
        {
          v31 = 1176;
          goto LABEL_46;
        }
        WindowsDeleteString(v43);
LABEL_60:
        WindowsDeleteString(v39);
        v15 = string;
        goto LABEL_61;
      }
    }
    else
    {
      v49 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"StartPin", 9u, 8u);
      if ( !DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v39, v49) )
      {
        v51 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v50, L"StartUnpin", 0xBu, 0xAu);
        if ( !DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v39, v51) )
        {
          v53 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v52, L"TaskbarPin", 0xBu, 0xAu);
          if ( !DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v39, v53) )
          {
            v55 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v54, L"TaskbarUnpin", 0xDu, 0xCu);
            if ( !DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(v39, v55) )
              goto LABEL_60;
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    goto LABEL_60;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x42E,
    (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
    (const char *)(unsigned int)v9,
    v38);
  return v10;
}

```

## disassembly

```asm
0x180140aa4  mov     [rsp-8+arg_10], rbx
0x180140aa9  push    rbp
0x180140aaa  push    rsi
0x180140aab  push    rdi
0x180140aac  push    r12
0x180140aae  push    r13
0x180140ab0  push    r14
0x180140ab2  push    r15
0x180140ab4  lea     rbp, [rsp-17h]
0x180140ab9  sub     rsp, 100h
0x180140ac0  mov     rax, cs:__security_cookie
0x180140ac7  xor     rax, rsp
0x180140aca  mov     [rbp+47h+var_38], rax
0x180140ace  mov     r15, r9
0x180140ad1  mov     r14, r8
0x180140ad4  mov     rsi, rcx
0x180140ad7  mov     [rsp+130h+var_E0], rdx
0x180140adc  mov     r12, [rbp+47h+arg_20]
0x180140ae0  mov     r13, [rbp+47h+arg_28]
0x180140ae4  xor     edi, edi
0x180140ae6  mov     [rsp+130h+var_D0], edi
0x180140aea  mov     rax, [r12]
0x180140aee  lea     rdx, [rsp+130h+var_D0]
0x180140af3  mov     rcx, r12
0x180140af6  mov     rax, [rax+30h]
0x180140afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140aff  mov     ebx, eax
0x180140b01  test    eax, eax
0x180140b03  jns     short loc_180140B22
0x180140b05  mov     rcx, [rbp+4Fh]; this
0x180140b09  mov     r9d, eax; char *
0x180140b0c  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x180140b13  mov     edx, 42Eh; void *
0x180140b18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180140b1d  jmp     loc_1801411F3
0x180140b22  mov     [rsp+130h+var_D8], rdi
0x180140b27  mov     eax, [rsp+130h+var_D0]
0x180140b2b  shr     eax, 1
0x180140b2d  and     al, 1
0x180140b2f  mov     [rsp+130h+var_E8], al
0x180140b33  mov     rax, [rsi+100h]
0x180140b3a  mov     [rsp+130h+var_C8], rax
0x180140b3f  lea     rcx, [rsp+130h+var_D8]
0x180140b44  call    ?InternalRelease@?$ComPtr@VTileVerbSeparator@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::TileVerbSeparator>::InternalRelease(void)
0x180140b49  lea     r9, [rsp+130h+var_E8]
0x180140b4e  lea     r8, [rsp+130h+var_C8]
0x180140b53  lea     rdx, [rsp+130h+var_E0]
0x180140b58  lea     rcx, [rsp+130h+var_D8]
0x180140b5d  call    ??$MakeAndInitialize@VTileVerbWrapper@Private@UnifiedTile@Shell@WindowsInternal@@V12345@AEAPEAUITileVerb@345@PEAUHSTRING__@@_N@Details@WRL@Microsoft@@YAJPEAPEAVTileVerbWrapper@Private@UnifiedTile@Shell@WindowsInternal@@AEAPEAUITileVerb@567@$$QEAPEAUHSTRING__@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper,WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper,WindowsInternal::Shell::UnifiedTile::ITileVerb * &,HSTRING__ *,bool>(WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper * *,WindowsInternal::Shell::UnifiedTile::ITileVerb * &,HSTRING__ * &&,bool &&)
0x180140b62  mov     ebx, eax
0x180140b64  test    eax, eax
0x180140b66  jns     short loc_180140B85
0x180140b68  mov     rcx, [rbp+4Fh]; this
0x180140b6c  mov     r9d, eax; char *
0x180140b6f  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x180140b76  mov     edx, 436h; void *
0x180140b7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180140b80  jmp     loc_1801411E9
0x180140b85  mov     rax, [rsp+130h+var_D8]
0x180140b8a  mov     [rsp+130h+var_F0], rax
0x180140b8f  lea     rcx, [rsp+130h+var_F0]
0x180140b94  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180140b99  mov     [rsp+130h+string], rdi
0x180140b9e  mov     rdi, [rsp+130h+var_F0]
0x180140ba3  mov     rax, [rdi]
0x180140ba6  mov     rbx, [rax+38h]
0x180140baa  xor     ecx, ecx; string
0x180140bac  call    cs:__imp_WindowsDeleteString
0x180140bb2  mov     [rsp+130h+string], 0
0x180140bbb  lea     rdx, [rsp+130h+string]
0x180140bc0  mov     rcx, rdi
0x180140bc3  mov     rax, rbx
0x180140bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140bcb  mov     ebx, eax
0x180140bcd  xor     edi, edi
0x180140bcf  test    eax, eax
0x180140bd1  jns     short loc_180140C0A
0x180140bd3  mov     rcx, [rbp+4Fh]; this
0x180140bd7  mov     r9d, eax; char *
0x180140bda  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x180140be1  mov     edx, 43Eh; void *
0x180140be6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180140beb  mov     rcx, [rsp+130h+string]; string
0x180140bf0  call    cs:__imp_WindowsDeleteString
0x180140bf6  mov     [rsp+130h+string], rdi
0x180140bfb  lea     rcx, [rsp+130h+var_F0]
0x180140c00  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180140c05  jmp     loc_1801411E9
0x180140c0a  mov     rcx, [rsp+130h+string]; string
0x180140c0f  test    rcx, rcx
0x180140c12  jnz     loc_1801411C4
0x180140c18  mov     [rsp+130h+var_100], rdi
0x180140c1d  mov     rdi, [rsp+130h+var_F0]
0x180140c22  mov     rax, [rdi]
0x180140c25  mov     rbx, [rax+40h]
0x180140c29  call    cs:__imp_WindowsDeleteString
0x180140c2f  mov     [rsp+130h+var_100], 0
0x180140c38  lea     rdx, [rsp+130h+var_100]
0x180140c3d  mov     rcx, rdi
0x180140c40  mov     rax, rbx
0x180140c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140c48  mov     ebx, eax
0x180140c4a  xor     edi, edi
0x180140c4c  test    eax, eax
0x180140c4e  jns     short loc_180140C7D
0x180140c50  mov     edx, 445h; void *
0x180140c55  mov     r9d, eax; char *
0x180140c58  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x180140c5f  mov     rcx, [rbp+4Fh]; this
0x180140c63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180140c68  mov     rcx, [rsp+130h+var_100]; string
0x180140c6d  call    cs:__imp_WindowsDeleteString
0x180140c73  mov     [rsp+130h+var_100], rdi
0x180140c78  jmp     loc_180140BEB
0x180140c7d  mov     bl, dil
0x180140c80  mov     qword ptr [rbp+47h+var_98.Reserved], rsi
0x180140c84  lea     rax, [rsp+130h+var_F0]
0x180140c89  mov     qword ptr [rbp+47h+var_98.Reserved+8], rax
0x180140c8d  mov     qword ptr [rbp+47h+var_98.Reserved+10h], r14
0x180140c91  mov     [rbp+47h+var_80], r12
0x180140c95  mov     [rbp+47h+var_A0], rdi
0x180140c99  mov     r9d, 11h; unsigned int
0x180140c9f  lea     r8d, [r9+1]; unsigned int
0x180140ca3  lea     rdx, ?FeatureUninstall@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "Feature.Uninstall"
0x180140caa  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x180140cae  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180140cb3  mov     rdx, [rbp+47h+var_A0]; HSTRING
0x180140cb7  mov     rcx, [rsp+130h+var_100]; HSTRING
0x180140cbc  call    ?AreStringsEqualCaseInsensitive@AppResolverTransformer@DataStoreCache@@CA_NPEAUHSTRING__@@0@Z; DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(HSTRING__ *,HSTRING__ *)
0x180140cc1  mov     r14d, 9
0x180140cc7  test    al, al
0x180140cc9  jz      short loc_180140D39
0x180140ccb  mov     r8d, r14d; unsigned int
0x180140cce  lea     rdx, ?Uninstall@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "Uninstall"
0x180140cd5  lea     rcx, [rsp+130h+var_100]; this
0x180140cda  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180140cdf  mov     ebx, eax
0x180140ce1  test    eax, eax
0x180140ce3  jns     short loc_180140CEF
0x180140ce5  mov     edx, 464h
0x180140cea  jmp     loc_180140C55
0x180140cef  mov     rax, [rsp+130h+var_100]
0x180140cf4  mov     [rsp+130h+var_C8], rax
0x180140cf9  mov     rcx, [rsp+130h+var_D8]
0x180140cfe  add     rcx, 50h ; 'P'; newString
0x180140d02  lea     rdx, [rsp+130h+var_C8]; HSTRING *
0x180140d07  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180140d0c  mov     ebx, eax
0x180140d0e  test    eax, eax
0x180140d10  jns     short loc_180140D37
0x180140d12  mov     rcx, [rbp+4Fh]; this
0x180140d16  mov     r9d, eax; char *
0x180140d19  lea     r8, aShellcommonShe_65; "shellcommon\\shell\\Tiles\\UnifiedTileM"...
0x180140d20  mov     edx, 59h ; 'Y'; void *
0x180140d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180140d2a  mov     r9d, ebx
0x180140d2d  mov     edx, 465h
0x180140d32  jmp     loc_180140C58
0x180140d37  mov     bl, 1
0x180140d39  mov     [rbp+47h+var_A0], rdi
0x180140d3d  mov     r9d, 4; unsigned int
0x180140d43  lea     r8d, [r9+1]; unsigned int
0x180140d47  lea     rdx, ?Open@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "Open"
0x180140d4e  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x180140d52  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180140d57  mov     rdx, [rbp+47h+var_A0]; HSTRING
0x180140d5b  mov     rcx, [rsp+130h+var_100]; HSTRING
0x180140d60  call    ?AreStringsEqualCaseInsensitive@AppResolverTransformer@DataStoreCache@@CA_NPEAUHSTRING__@@0@Z; DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(HSTRING__ *,HSTRING__ *)
0x180140d65  test    al, al
0x180140d67  jz      short loc_180140D88
0x180140d69  xor     edx, edx
0x180140d6b  lea     rcx, [rbp+47h+var_98]
0x180140d6f  call    ??R_lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_@@QEBAJW4ActivationOptions@UnifiedTile@Shell@WindowsInternal@@@Z; _lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_::operator()(WindowsInternal::Shell::UnifiedTile::ActivationOptions)
0x180140d74  mov     ebx, eax
0x180140d76  test    eax, eax
0x180140d78  jns     loc_1801411B4
0x180140d7e  mov     edx, 46Bh
0x180140d83  jmp     loc_180140C55
0x180140d88  mov     [rbp+47h+var_A0], rdi
0x180140d8c  mov     r9d, 5; unsigned int
0x180140d92  lea     r8d, [r9+1]; unsigned int
0x180140d96  lea     rdx, ?RunAsAdmin@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "RunAs"
0x180140d9d  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x180140da1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180140da6  mov     rdx, [rbp+47h+var_A0]; HSTRING
0x180140daa  mov     rcx, [rsp+130h+var_100]; HSTRING
0x180140daf  call    ?AreStringsEqualCaseInsensitive@AppResolverTransformer@DataStoreCache@@CA_NPEAUHSTRING__@@0@Z; DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(HSTRING__ *,HSTRING__ *)
0x180140db4  test    al, al
0x180140db6  jz      short loc_180140DDA
0x180140db8  mov     edx, 1
0x180140dbd  lea     rcx, [rbp+47h+var_98]
0x180140dc1  call    ??R_lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_@@QEBAJW4ActivationOptions@UnifiedTile@Shell@WindowsInternal@@@Z; _lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_::operator()(WindowsInternal::Shell::UnifiedTile::ActivationOptions)
0x180140dc6  mov     ebx, eax
0x180140dc8  test    eax, eax
0x180140dca  jns     loc_1801411B4
0x180140dd0  mov     edx, 46Fh
0x180140dd5  jmp     loc_180140C55
0x180140dda  mov     [rbp+47h+var_A0], rdi
0x180140dde  mov     r9d, r14d; unsigned int
0x180140de1  mov     r14d, 0Ah
0x180140de7  mov     r8d, r14d; unsigned int
0x180140dea  lea     rdx, ?RunAsUser@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "RunAsUser"
0x180140df1  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x180140df5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180140dfa  mov     rdx, [rbp+47h+var_A0]; HSTRING
0x180140dfe  mov     rcx, [rsp+130h+var_100]; HSTRING
0x180140e03  call    ?AreStringsEqualCaseInsensitive@AppResolverTransformer@DataStoreCache@@CA_NPEAUHSTRING__@@0@Z; DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(HSTRING__ *,HSTRING__ *)
0x180140e08  test    al, al
0x180140e0a  jz      short loc_180140E2D
0x180140e0c  lea     edx, [r14-8]
0x180140e10  lea     rcx, [rbp+47h+var_98]
0x180140e14  call    ??R_lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_@@QEBAJW4ActivationOptions@UnifiedTile@Shell@WindowsInternal@@@Z; _lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_::operator()(WindowsInternal::Shell::UnifiedTile::ActivationOptions)
0x180140e19  mov     ebx, eax
0x180140e1b  test    eax, eax
0x180140e1d  jns     loc_1801411B4
0x180140e23  mov     edx, 473h
0x180140e28  jmp     loc_180140C55
0x180140e2d  mov     [rbp+47h+var_A0], rdi
0x180140e31  mov     r9d, 10h; unsigned int
0x180140e37  lea     r8d, [r9+1]; unsigned int
0x180140e3b  lea     rdx, ?OpenFileLocation@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "OpenFileLocation"
0x180140e42  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x180140e46  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180140e4b  mov     rdx, [rbp+47h+var_A0]; HSTRING
0x180140e4f  mov     rcx, [rsp+130h+var_100]; HSTRING
0x180140e54  call    ?AreStringsEqualCaseInsensitive@AppResolverTransformer@DataStoreCache@@CA_NPEAUHSTRING__@@0@Z; DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(HSTRING__ *,HSTRING__ *)
0x180140e59  mov     [rbp+47h+var_A0], rdi
0x180140e5d  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x180140e61  test    al, al
0x180140e63  jz      short loc_180140EDF
0x180140e65  mov     rbx, [rsp+130h+var_D8]
0x180140e6a  mov     r9d, 1; unsigned int
0x180140e70  lea     r8d, [r9+1]; unsigned int
0x180140e74  lea     rdx, ?OpenFileLocation@SegoeMDL2Assets@VerbGlyphs@UnifiedTile@Shell@WindowsInternal@@3QBGB; sourceString
0x180140e7b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180140e80  mov     rdx, [rbp+47h+var_A0]; HSTRING
0x180140e84  mov     rcx, rbx; this
0x180140e87  call    ?put_Glyph@TileVerbWrapper@Private@UnifiedTile@Shell@WindowsInternal@@QEAAJPEAUHSTRING__@@@Z; WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper::put_Glyph(HSTRING__ *)
0x180140e8c  mov     ebx, eax
0x180140e8e  test    eax, eax
0x180140e90  jns     short loc_180140E9C
0x180140e92  mov     edx, 477h
0x180140e97  jmp     loc_180140C55
0x180140e9c  mov     rbx, [rsp+130h+var_D8]
0x180140ea1  mov     [rbp+47h+var_A0], rdi
0x180140ea5  mov     r9d, 12h; unsigned int
0x180140eab  lea     r8d, [r9+1]; unsigned int
0x180140eaf  lea     rdx, ?FontFamily@SegoeMDL2Assets@VerbGlyphs@UnifiedTile@Shell@WindowsInternal@@3QBGB; "Segoe Fluent Icons"
0x180140eb6  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x180140eba  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180140ebf  mov     rdx, [rbp+47h+var_A0]; HSTRING
0x180140ec3  mov     rcx, rbx; this
0x180140ec6  call    ?put_GlyphFontFamily@TileVerbWrapper@Private@UnifiedTile@Shell@WindowsInternal@@QEAAJPEAUHSTRING__@@@Z; WindowsInternal::Shell::UnifiedTile::Private::TileVerbWrapper::put_GlyphFontFamily(HSTRING__ *)
0x180140ecb  mov     ebx, eax
0x180140ecd  test    eax, eax
0x180140ecf  jns     loc_1801411B4
0x180140ed5  mov     edx, 478h
0x180140eda  jmp     loc_180140C55
0x180140edf  mov     r9d, 9; unsigned int
0x180140ee5  mov     r8d, r14d; unsigned int
0x180140ee8  lea     rdx, ?Uninstall@VerbCanonicalNames@UnifiedTile@Shell@WindowsInternal@@3QBGB; "Uninstall"
0x180140eef  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180140ef4  mov     rdx, [rbp+47h+var_A0]; HSTRING
0x180140ef8  mov     rcx, [rsp+130h+var_100]; HSTRING
0x180140efd  call    ?AreStringsEqualCaseInsensitive@AppResolverTransformer@DataStoreCache@@CA_NPEAUHSTRING__@@0@Z; DataStoreCache::AppResolverTransformer::AreStringsEqualCaseInsensitive(HSTRING__ *,HSTRING__ *)
0x180140f02  test    al, al
0x180140f04  jz      loc_1801410EB
0x180140f0a  lea     rcx, POLID_NoUninstallFromStart
0x180140f11  call    cs:__imp_SHWindowsPolicy
0x180140f17  test    eax, eax
0x180140f19  jnz     loc_1801411AA
0x180140f1f  mov     [rsp+130h+var_C8], rdi
0x180140f24  mov     rax, [r15]
0x180140f27  lea     r8, [rsp+130h+var_C8]
0x180140f2c  lea     rdx, ?UninstallCommand@AppResolverProperties@DataStoreCache@@3U?$DataStoreProperty@PEBG@2@B; DataStoreCache::DataStoreProperty<ushort const *> const DataStoreCache::AppResolverProperties::UninstallCommand
0x180140f33  mov     rcx, r15
0x180140f36  mov     rax, [rax+20h]
0x180140f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140f3f  test    al, al
0x180140f41  jz      short loc_180140F74
0x180140f43  mov     rax, [rsp+130h+var_C8]
0x180140f48  test    rax, rax
0x180140f4b  jz      short loc_180140F74
0x180140f4d  cmp     [rax], di
0x180140f50  jz      short loc_180140F74
0x180140f52  mov     edx, 10h
0x180140f57  lea     rcx, [rbp+47h+var_98]
0x180140f5b  call    ??R_lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_@@QEBAJW4ActivationOptions@UnifiedTile@Shell@WindowsInternal@@@Z; _lambda_5fbf2217ca9b1eb7aa2f7658d64aed42_::operator()(WindowsInternal::Shell::UnifiedTile::ActivationOptions)
0x180140f60  mov     ebx, eax
0x180140f62  test    eax, eax
0x180140f64  jns     loc_1801411B4
0x180140f6a  mov     edx, 484h
0x180140f6f  jmp     loc_180140C55
0x180140f74  call    ?IsFeatureEnabled@EnterpriseFeatureControl@@SA_NK@Z; EnterpriseFeatureControl::IsFeatureEnabled(ulong)
0x180140f79  test    al, al
0x180140f7b  jz      short loc_180140FAC
0x180140f7d  lea     rax, [rsp+130h+var_F0]
0x180140f82  mov     qword ptr [rsp+130h+var_110], rax
0x180140f87  mov     r9, r15
0x180140f8a  mov     r8b, bl
  ... truncated ...
```
