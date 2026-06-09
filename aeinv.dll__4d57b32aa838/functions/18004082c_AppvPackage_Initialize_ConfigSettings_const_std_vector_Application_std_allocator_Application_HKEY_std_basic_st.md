# AppvPackage::Initialize(ConfigSettings const &,std::vector<Application,std::allocator<Application>> &,HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004082c`
- end: `0x1800416be`
- name: `?Initialize@AppvPackage@@QEAAXAEBVConfigSettings@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@33@Z`
- size: `3730`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002d624`

## callees

- `0x18000b364`
- `0x18000b7cc`
- `0x18000f3b4`
- `0x18000f950`
- `0x1800118d0`
- `0x1800150ac`
- `0x1800176e0`
- `0x180017724`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x180034ff0`
- `0x1800404c4`
- `0x18004082c`
- `0x1800416c4`
- `0x1800417a8`
- `0x1800419c8`
- `0x180041d4c`
- `0x180041ef8`
- `0x180044c88`
- `0x180045480`
- `0x18004e6b4`
- `0x180059920`
- `0x18005d690`
- `0x180102fe4`
- `0x180103024`
- `0x18010309c`
- `0x1801034a0`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18004109a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18004109a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180040982`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180040bf0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180040982`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180040bf0`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180040c5e`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180040c5e`
- `XmlLite!CreateXmlReader` at `0x180040a70`
- `XmlLite!CreateXmlReader` at `0x180040a70`

## string_xrefs

- `0x180040a3f`: `\AppxManifest.xml`
- `0x180040fa5`: `InstallDate`
- `0x180040c82`: `SHCreateStreamOnFileEx failed for %ws [%#x]`
- `0x180040a7e`: `CreateXmlReader failed: [%#x]`
- `0x180040cbf`: `IXmlReader->SetInput failed: [%#x]`
- `0x1800412b2`: `IXmlReader->SetInput failed: [%#x]`
- `0x180040ff7`: `Failed to get InstallDate node: [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall AppvPackage::Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v8; // rdx
  __int64 v9; // rax
  const unsigned __int16 *v10; // rdx
  const wchar_t *v11; // rdx
  wchar_t *v12; // rcx
  wchar_t *v13; // rbx
  __int64 RegValueString; // rax
  const char *v15; // r9
  int v16; // r8d
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  const WCHAR *v19; // rcx
  int v20; // ebx
  _WORD *v21; // rcx
  __int64 *v22; // rcx
  __int64 *v23; // rcx
  __int64 *v24; // rcx
  _WORD *v25; // rcx
  __int64 *v26; // rcx
  int v27; // ebx
  int v28; // ebx
  int v29; // ebx
  int v30; // ebx
  int v31; // ebx
  _QWORD *v32; // rcx
  __int64 v33; // rax
  const char *v34; // r9
  int v35; // r8d
  int v36; // ecx
  int v37; // ebx
  _WORD *v38; // rcx
  __int64 *v39; // rcx
  __int64 *v40; // rcx
  int v41; // ebx
  int v42; // ebx
  int v43; // ebx
  const char *v44; // r9
  int v45; // r8d
  __int64 v46; // rax
  void *ppvObject; // [rsp+58h] [rbp-B0h] BYREF
  IStream *ppstm; // [rsp+60h] [rbp-A8h] BYREF
  wchar_t *Context; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-98h]
  __int64 v52; // [rsp+78h] [rbp-90h]
  __int64 v53; // [rsp+80h] [rbp-88h]
  __int64 v54; // [rsp+88h] [rbp-80h]
  __int64 v55; // [rsp+90h] [rbp-78h]
  WCHAR v56[16]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v57[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v58; // [rsp+C8h] [rbp-40h]
  unsigned __int64 v59; // [rsp+D0h] [rbp-38h]
  _QWORD v60[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v61; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v62; // [rsp+F0h] [rbp-18h]
  __int64 v63[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v64; // [rsp+108h] [rbp+0h]
  unsigned __int64 v65; // [rsp+110h] [rbp+8h]
  _BYTE v66[32]; // [rsp+118h] [rbp+10h] BYREF
  wchar_t *String[4]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v68[32]; // [rsp+158h] [rbp+50h] BYREF
  LPCWSTR pszFile[4]; // [rsp+178h] [rbp+70h] BYREF
  _QWORD v70[3]; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int64 v71; // [rsp+1B0h] [rbp+A8h]
  _BYTE v72[16]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 v73; // [rsp+1C8h] [rbp+C0h]
  __int64 v74[4]; // [rsp+1D8h] [rbp+D0h] BYREF
  unsigned __int16 *v75[4]; // [rsp+1F8h] [rbp+F0h] BYREF
  WCHAR v76[16]; // [rsp+218h] [rbp+110h] BYREF
  __int64 v77[4]; // [rsp+238h] [rbp+130h] BYREF
  _BYTE v78[8]; // [rsp+258h] [rbp+150h] BYREF
  _BYTE v79[72]; // [rsp+260h] [rbp+158h] BYREF
  _BYTE v80[32]; // [rsp+2A8h] [rbp+1A0h] BYREF
  _BYTE v81[32]; // [rsp+2C8h] [rbp+1C0h] BYREF
  void **v82; // [rsp+2E8h] [rbp+1E0h] BYREF
  void **v83; // [rsp+2F0h] [rbp+1E8h]
  void **v84; // [rsp+2F8h] [rbp+1F0h]
  _BYTE v85[40]; // [rsp+320h] [rbp+218h] BYREF
  __int64 v86; // [rsp+358h] [rbp+250h]
  _BYTE v87[72]; // [rsp+6D8h] [rbp+5D0h] BYREF
  __int64 v88; // [rsp+720h] [rbp+618h]

  v55 = -2;
  v52 = a2;
  v53 = a6;
  v54 = a7;
  std::wstring::wstring(v60);
  std::wstring::wstring(String);
  std::operator+<unsigned short>(v76, v8, L"\\Catalog");
  v9 = std::operator+<unsigned short>(v68, a6, L"/");
  std::operator+<unsigned short>(v75, v9, a7);
  std::wstring::~wstring(v68);
  std::wstring::wstring(v72);
  AmiPackageIdItem::AmiPackageIdItem((AmiPackageIdItem *)v78);
  v10 = (const unsigned __int16 *)v75;
  if ( v75[3] > (unsigned __int16 *)7 )
    v10 = v75[0];
  AmiPackageIdItem::SetItemKey((AmiPackageIdItem *)v78, v10);
  if ( (int)TelCacheProvider::GetItem(
              (TelCacheProvider *)AppvPackage::m_packageIdLookupStore,
              (struct IAmiInventoryItem *)v78,
              0) >= 0 )
  {
    Context = 0;
    std::wstring::operator=(String, v79);
    v11 = (const wchar_t *)&AppvPackage::m_programIdDelimiter;
    if ( (unsigned __int64)qword_180183408 > 7 )
      v11 = AppvPackage::m_programIdDelimiter;
    v12 = (wchar_t *)String;
    if ( String[3] > (wchar_t *)7 )
      v12 = String[0];
    v13 = wcstok_s(v12, v11, &Context);
    if ( !v13 )
      goto LABEL_103;
    Application::Application((Application *)v87);
    std::wstring::wstring(v56, v13);
    Application::GetApplicationFromCache((struct IAmiInventoryItem *)v87);
    std::wstring::~wstring(v56);
    if ( v88 )
    {
      do
      {
        v17 = -1;
        do
          ++v17;
        while ( v13[v17] );
        std::wstring::_Assign<unsigned short>(v60, v13);
        Application::Application((Application *)&v82);
        v82 = &EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
        v83 = &AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        v84 = &SteamApplication::`vftable';
        Application::GetApplicationFromCache((struct IAmiInventoryItem *)&v82);
        if ( v86 )
        {
          AslLogCallPrintf(
            3,
            (unsigned int)"AppvPackage::Initialize",
            340,
            (unsigned int)"AppvApp >>>>>>>>>>> %ws, %ws, %ws, %d");
          if ( *(_QWORD *)(a3 + 8) == *(_QWORD *)(a3 + 16) )
          {
            std::vector<Application>::_Emplace_reallocate<Application const &>(a3, *(_QWORD *)(a3 + 8), &v82);
          }
          else
          {
            Application::Application(*(Application **)(a3 + 8), (const struct Application *)&v82);
            *(_QWORD *)(a3 + 8) += 1008LL;
          }
        }
        v18 = (const wchar_t *)&AppvPackage::m_programIdDelimiter;
        if ( (unsigned __int64)qword_180183408 > 7 )
          v18 = AppvPackage::m_programIdDelimiter;
        v13 = wcstok_s(0, v18, &Context);
        v82 = &EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
        v83 = &AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
        v84 = &SteamApplication::`vftable';
        Application::~Application((Application *)&v82);
      }
      while ( v13 );
      Application::~Application((Application *)v87);
      goto LABEL_103;
    }
    Application::~Application((Application *)v87);
  }
  std::wstring::wstring(v56, L"Folder");
  RegValueString = Utility::GetRegValueString((__int64)v68, HKEY_LOCAL_MACHINE, v76, v56);
  std::wstring::operator=(v72, RegValueString);
  std::wstring::~wstring(v68);
  std::wstring::~wstring(v56);
  if ( !v73 )
    goto LABEL_103;
  std::operator+<unsigned short>(pszFile, v72, L"\\AppxManifest.xml");
  ppstm = 0;
  ppvObject = 0;
  if ( CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0) )
  {
    v15 = "CreateXmlReader failed: [%#x]";
    v16 = 374;
LABEL_14:
    AslLogCallPrintf(3, (unsigned int)"AppvPackage::Initialize", v16, (_DWORD)v15);
    goto LABEL_102;
  }
  v19 = (const WCHAR *)pszFile;
  if ( pszFile[3] > (LPCWSTR)7 )
    v19 = pszFile[0];
  if ( SHCreateStreamOnFileEx(v19, 0, 0, 0, 0, &ppstm) )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"AppvPackage::Initialize",
      381,
      (unsigned int)"SHCreateStreamOnFileEx failed for %ws [%#x]");
    goto LABEL_102;
  }
  if ( (*(unsigned int (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm) )
  {
    v15 = "IXmlReader->SetInput failed: [%#x]";
    v16 = 388;
    goto LABEL_14;
  }
  std::wstring::wstring(v66);
  std::wstring::wstring(v57);
  std::wstring::wstring(v63);
  std::wstring::wstring(v74);
  std::wstring::wstring(v70);
  std::wstring::wstring(v77);
  LODWORD(v51) = 0;
  while ( 1 )
  {
    std::wstring::wstring(v56, L"AssetIntelligenceProperties");
    v20 = AppvPackage::AdvanceToElementNode(ppvObject, v56);
    std::wstring::~wstring(v56);
    if ( v20 )
      break;
    v61 = 0;
    v21 = v60;
    if ( v62 > 7 )
      v21 = (_WORD *)v60[0];
    *v21 = 0;
    v58 = 0;
    v22 = v57;
    if ( v59 > 7 )
      v22 = (__int64 *)v57[0];
    *(_WORD *)v22 = 0;
    v64 = 0;
    v23 = v63;
    if ( v65 > 7 )
      v23 = (__int64 *)v63[0];
    *(_WORD *)v23 = 0;
    v74[2] = 0;
    v24 = v74;
    if ( v74[3] > 7uLL )
      v24 = (__int64 *)v74[0];
    *(_WORD *)v24 = 0;
    v70[2] = 0;
    v25 = v70;
    if ( v71 > 7 )
      v25 = (_WORD *)v70[0];
    *v25 = 0;
    v77[2] = 0;
    v26 = v77;
    if ( v77[3] > 7uLL )
      v26 = (__int64 *)v77[0];
    *(_WORD *)v26 = 0;
    std::wstring::wstring(v56, L"ProductName");
    v27 = AppvPackage::AdvanceToElementNode(ppvObject, v56);
    std::wstring::~wstring(v56);
    if ( v27 )
    {
      v34 = "No app name found";
      v35 = 426;
      v36 = 1;
      goto LABEL_68;
    }
    AppvPackage::GetChildTextNodeValue(ppvObject, v66);
    std::wstring::operator=(v57, v66);
    if ( !v58 )
    {
      v34 = "Name value is empty";
      v35 = 419;
      v36 = 3;
LABEL_68:
      AslLogCallPrintf(v36, (unsigned int)"AppvPackage::Initialize", v35, (_DWORD)v34);
      goto LABEL_101;
    }
    LODWORD(v51) = v51 + 1;
    std::wstring::wstring(v56, L"ProductVersion");
    v28 = AppvPackage::AdvanceToElementNode(ppvObject, v56);
    std::wstring::~wstring(v56);
    if ( v28 )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"AppvPackage::Initialize",
        439,
        (unsigned int)"Failed to get ProductVersion node: [%#x]");
    }
    else
    {
      AppvPackage::GetChildTextNodeValue(ppvObject, v66);
      std::wstring::operator=(v63, v66);
    }
    std::wstring::wstring(v56, L"Publisher");
    v29 = AppvPackage::AdvanceToElementNode(ppvObject, v56);
    std::wstring::~wstring(v56);
    if ( v29 )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"AppvPackage::Initialize",
        451,
        (unsigned int)"Failed to get Publisher node: [%#x]");
    }
    else
    {
      AppvPackage::GetChildTextNodeValue(ppvObject, v66);
      std::wstring::operator=(v74, v66);
    }
    std::wstring::wstring(v56, L"Language");
    v30 = AppvPackage::AdvanceToElementNode(ppvObject, v56);
    std::wstring::~wstring(v56);
    if ( v30 )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"AppvPackage::Initialize",
        465,
        (unsigned int)"Failed to get Language node: [%#x]");
    }
    else
    {
      AppvPackage::GetChildTextNodeValue(ppvObject, v66);
      std::wstring::operator=(v70, v66);
    }
    std::wstring::wstring(v56, L"InstallDate");
    v31 = AppvPackage::AdvanceToElementNode(ppvObject, v56);
    std::wstring::~wstring(v56);
    if ( v31 )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"AppvPackage::Initialize",
        477,
        (unsigned int)"Failed to get InstallDate node: [%#x]");
    }
    else
    {
      AppvPackage::GetChildTextNodeValue(ppvObject, v66);
      std::wstring::operator=(v77, v66);
    }
    AslLogCallPrintf(
      3,
      (unsigned int)"AppvPackage::Initialize",
      480,
      (unsigned int)"AppvApp >>>>>>>>>>> %ws, %ws, %ws, %ws");
    v32 = v70;
    if ( v71 > 7 )
      v32 = (_QWORD *)v70[0];
    LODWORD(Context) = _o__wtoi(v32);
    v33 = std::operator+<unsigned short>(v56, v53, L"/");
    std::operator+<unsigned short>(v68, v33, v54);
    AppvApplication::AppvApplication(
      (Application *)&v82,
      (__int64)v57,
      (__int64)v63,
      (__int64)v74,
      (__int64)&Context,
      (__int64)v77);
    std::wstring::~wstring(v68);
    std::wstring::~wstring(v56);
    if ( v86 )
    {
      if ( *(_QWORD *)(a3 + 8) == *(_QWORD *)(a3 + 16) )
      {
        std::vector<Application>::_Emplace_reallocate<Application const &>(a3, *(_QWORD *)(a3 + 8), &v82);
      }
      else
      {
        Application::Application(*(Application **)(a3 + 8), (const struct Application *)&v82);
        *(_QWORD *)(a3 + 8) += 1008LL;
      }
      std::operator+<unsigned short>(v80, v85, &AppvPackage::m_programIdDelimiter);
      std::wstring::_Append<unsigned short>(String);
      std::wstring::~wstring(v80);
    }
    v82 = &EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
    v83 = &AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
    v84 = &SteamApplication::`vftable';
    Application::~Application((Application *)&v82);
  }
  if ( (_DWORD)v51 )
    goto LABEL_100;
  AslLogCallPrintf(
    3,
    (unsigned int)"AppvPackage::Initialize",
    504,
    (unsigned int)"Failed to find the <appv:AssetIntelligenceProperties> node.");
  Context = 0;
  if ( (*(unsigned int (__fastcall **)(IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0) )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"AppvPackage::Initialize",
      510,
      (unsigned int)"IStream::Seek failed for %ws [%#x]");
    goto LABEL_101;
  }
  (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject + 24LL))(ppvObject, 0);
  if ( (*(unsigned int (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm) )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"AppvPackage::Initialize",
      518,
      (unsigned int)"IXmlReader->SetInput failed: [%#x]");
    goto LABEL_101;
  }
  std::wstring::wstring(v56);
  while ( 1 )
  {
    std::wstring::wstring(v68, L"Application");
    v37 = AppvPackage::AdvanceToElementNode(ppvObject, v68);
    std::wstring::~wstring(v68);
    if ( v37 )
      break;
    v61 = 0;
    v38 = v60;
    if ( v62 > 7 )
      v38 = (_WORD *)v60[0];
    *v38 = 0;
    v58 = 0;
    v39 = v57;
    if ( v59 > 7 )
      v39 = (__int64 *)v57[0];
    *(_WORD *)v39 = 0;
    v64 = 0;
    v40 = v63;
    if ( v65 > 7 )
      v40 = (__int64 *)v63[0];
    *(_WORD *)v40 = 0;
    std::wstring::wstring(v68, L"VisualElements");
    v41 = AppvPackage::AdvanceToElementNode(ppvObject, v68);
    std::wstring::~wstring(v68);
    if ( v41 )
    {
      v44 = "Failed to get the <Application><VisualElements> node: [%#x]";
      v45 = 567;
    }
    else
    {
      std::wstring::wstring(v68, L"Name");
      v42 = AppvPackage::AdvanceToElementNode(ppvObject, v68);
      std::wstring::~wstring(v68);
      if ( v42 )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"AppvPackage::Initialize",
          550,
          (unsigned int)"Failed to get the <Application><VisualElements><Name> node: [%#x]");
      }
      else
      {
        AppvPackage::GetChildTextNodeValue(ppvObject, v66);
        std::wstring::operator=(v57, v66);
        if ( !v58 )
        {
          AslLogCallPrintf(1, (unsigned int)"AppvPackage::Initialize", 544, (unsigned int)"No app name found");
          std::wstring::~wstring(v56);
          goto LABEL_101;
        }
      }
      std::wstring::wstring(v68, L"Version");
      v43 = AppvPackage::AdvanceToElementNode(ppvObject, v68);
      std::wstring::~wstring(v68);
      if ( !v43 )
      {
        AppvPackage::GetChildTextNodeValue(ppvObject, v66);
        std::wstring::operator=(v63, v66);
        goto LABEL_93;
      }
      v44 = "Failed to get the <Application><VisualElements><Version> node: [%#x]";
      v45 = 562;
    }
    AslLogCallPrintf(3, (unsigned int)"AppvPackage::Initialize", v45, (_DWORD)v44);
LABEL_93:
    LODWORD(Context) = 0;
    v46 = std::operator+<unsigned short>(v68, v53, L"/");
    std::operator+<unsigned short>(v80, v46, v54);
    AppvApplication::AppvApplication(
      (Application *)&v82,
      (__int64)v57,
      (__int64)v63,
      (__int64)v56,
      (__int64)&Context,
      (__int64)v56);
    std::wstring::~wstring(v80);
    std::wstring::~wstring(v68);
    if ( v86 )
    {
      if ( *(_QWORD *)(a3 + 8) == *(_QWORD *)(a3 + 16) )
      {
        std::vector<Application>::_Emplace_reallocate<Application const &>(a3, *(_QWORD *)(a3 + 8), &v82);
      }
      else
      {
        Application::Application(*(Application **)(a3 + 8), (const struct Application *)&v82);
        *(_QWORD *)(a3 + 8) += 1008LL;
      }
      std::operator+<unsigned short>(v81, v85, &AppvPackage::m_programIdDelimiter);
      std::wstring::_Append<unsigned short>(String);
      std::wstring::~wstring(v81);
    }
    v82 = &EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
    v83 = &AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
    v84 = &SteamApplication::`vftable';
    Application::~Application((Application *)&v82);
  }
  std::wstring::~wstring(v56);
LABEL_100:
  std::wstring::operator=(v79, String);
  TelCacheProvider::AddItem((TelCacheProvider *)AppvPackage::m_packageIdLookupStore, (struct IAmiInventoryItem *)v78);
LABEL_101:
  std::wstring::~wstring(v77);
  std::wstring::~wstring(v70);
  std::wstring::~wstring(v74);
  std::wstring::~wstring(v63);
  std::wstring::~wstring(v57);
  std::wstring::~wstring(v66);
LABEL_102:
  wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(&ppvObject);
  wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(&ppstm);
  std::wstring::~wstring(pszFile);
LABEL_103:
  AmiPackageIdItem::~AmiPackageIdItem((AmiPackageIdItem *)v78);
  std::wstring::~wstring(v72);
  std::wstring::~wstring(v75);
  std::wstring::~wstring(v76);
  std::wstring::~wstring(String);
  return std::wstring::~wstring(v60);
}

```

## disassembly

```asm
0x18004082c  mov     rax, rsp
0x18004082f  push    rbp
0x180040830  push    rsi
0x180040831  push    rdi
0x180040832  push    r12
0x180040834  push    r13
0x180040836  push    r14
0x180040838  push    r15
0x18004083a  lea     rbp, [rax-0A08h]
0x180040841  sub     rsp, 0AD0h
0x180040848  mov     [rbp+0A00h+var_A78], 0FFFFFFFFFFFFFFFEh
0x180040850  mov     [rax+8], rbx
0x180040854  mov     rax, cs:__security_cookie
0x18004085b  xor     rax, rsp
0x18004085e  mov     [rbp+0A00h+var_40], rax
0x180040865  mov     r14, r8
0x180040868  mov     rdi, rdx
0x18004086b  mov     [rsp+0B00h+var_A90], rdx
0x180040870  mov     rdx, [rbp+0A00h+arg_20]
0x180040877  mov     rbx, [rbp+0A00h+arg_28]
0x18004087e  mov     [rsp+0B00h+var_A88], rbx
0x180040883  mov     rsi, [rbp+0A00h+arg_30]
0x18004088a  mov     [rbp+0A00h+var_A80], rsi
0x18004088e  lea     rcx, [rbp+0A00h+var_A30]
0x180040892  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180040897  nop
0x180040898  lea     rcx, [rbp+0A00h+String]
0x18004089c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800408a1  nop
0x1800408a2  lea     r8, aCatalog; "\\Catalog"
0x1800408a9  lea     rcx, [rbp+0A00h+var_8F0]
0x1800408b0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800408b5  nop
0x1800408b6  lea     r8, asc_18013A024; "/"
0x1800408bd  mov     rdx, rbx
0x1800408c0  lea     rcx, [rbp+0A00h+var_9B0]
0x1800408c4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800408c9  nop
0x1800408ca  mov     r8, rsi
0x1800408cd  mov     rdx, rax
0x1800408d0  lea     rcx, [rbp+0A00h+var_910]
0x1800408d7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800408dc  nop
0x1800408dd  lea     rcx, [rbp+0A00h+var_9B0]
0x1800408e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800408e6  lea     rcx, [rbp+0A00h+var_950]
0x1800408ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800408f2  nop
0x1800408f3  lea     rcx, [rbp+0A00h+var_8B0]; this
0x1800408fa  call    ??0AmiPackageIdItem@@QEAA@XZ; AmiPackageIdItem::AmiPackageIdItem(void)
0x1800408ff  nop
0x180040900  lea     rdx, [rbp+0A00h+var_910]
0x180040907  cmp     [rbp+0A00h+var_8F8], 7
0x18004090f  cmova   rdx, [rbp+0A00h+var_910]; unsigned __int16 *
0x180040917  lea     rcx, [rbp+0A00h+var_8B0]; this
0x18004091e  call    ?SetItemKey@AmiPackageIdItem@@UEAAKPEBG@Z; AmiPackageIdItem::SetItemKey(ushort const *)
0x180040923  xor     r8d, r8d; bool
0x180040926  lea     rdx, [rbp+0A00h+var_8B0]; struct IAmiInventoryItem *
0x18004092d  lea     rcx, ?m_packageIdLookupStore@AppvPackage@@2VTelCacheProvider@@A; this
0x180040934  call    ?GetItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@_N@Z; TelCacheProvider::GetItem(IAmiInventoryItem *,bool)
0x180040939  xor     esi, esi
0x18004093b  test    eax, eax
0x18004093d  js      loc_1800409E4
0x180040943  mov     [rsp+0B00h+Context], rsi
0x180040948  lea     rdx, [rbp+0A00h+var_8A8]
0x18004094f  lea     rcx, [rbp+0A00h+String]
0x180040953  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180040958  lea     rdx, ?m_programIdDelimiter@AppvPackage@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AppvPackage::m_programIdDelimiter
0x18004095f  cmp     cs:qword_180183408, 7
0x180040967  cmova   rdx, cs:?m_programIdDelimiter@AppvPackage@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; Delimiter
0x18004096f  lea     rcx, [rbp+0A00h+String]
0x180040973  cmp     [rbp+0A00h+var_9B8], 7
0x180040978  cmova   rcx, [rbp+0A00h+String]; String
0x18004097d  lea     r8, [rsp+0B00h+Context]; Context
0x180040982  call    cs:__imp_wcstok_s
0x180040988  mov     rbx, rax
0x18004098b  test    rax, rax
0x18004098e  jz      loc_18004164D
0x180040994  lea     rcx, [rbp+0A00h+var_430]; this
0x18004099b  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x1800409a0  nop
0x1800409a1  mov     rdx, rbx
0x1800409a4  lea     rcx, [rbp+0A00h+var_A70]
0x1800409a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800409ad  nop
0x1800409ae  lea     r8, [rbp+0A00h+var_A70]
0x1800409b2  mov     rdx, rdi
0x1800409b5  lea     rcx, [rbp+0A00h+var_430]; struct IAmiInventoryItem *
0x1800409bc  call    ?GetApplicationFromCache@Application@@QEAAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::GetApplicationFromCache(ConfigSettings const &,std::wstring const &)
0x1800409c1  nop
0x1800409c2  lea     rcx, [rbp+0A00h+var_A70]
0x1800409c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800409cb  cmp     [rbp+0A00h+var_3E8], rsi
0x1800409d2  jnz     loc_180040AA5
0x1800409d8  lea     rcx, [rbp+0A00h+var_430]; this
0x1800409df  call    ??1Application@@UEAA@XZ; Application::~Application(void)
0x1800409e4  lea     rdx, aFolder; "Folder"
0x1800409eb  lea     rcx, [rbp+0A00h+var_A70]
0x1800409ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800409f4  nop
0x1800409f5  lea     r9, [rbp+0A00h+var_A70]
0x1800409f9  lea     r8, [rbp+0A00h+var_8F0]
0x180040a00  mov     rdx, 0FFFFFFFF80000002h
0x180040a07  lea     rcx, [rbp+0A00h+var_9B0]
0x180040a0b  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x180040a10  mov     rdx, rax
0x180040a13  lea     rcx, [rbp+0A00h+var_950]
0x180040a1a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180040a1f  lea     rcx, [rbp+0A00h+var_9B0]
0x180040a23  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040a28  nop
0x180040a29  lea     rcx, [rbp+0A00h+var_A70]
0x180040a2d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040a32  cmp     [rbp+0A00h+var_940], rsi
0x180040a39  jz      loc_18004164D
0x180040a3f  lea     r8, aAppxmanifestXm_0; "\\AppxManifest.xml"
0x180040a46  lea     rdx, [rbp+0A00h+var_950]
0x180040a4d  lea     rcx, [rbp+0A00h+pszFile]
0x180040a51  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180040a56  nop
0x180040a57  mov     [rsp+0B00h+var_AA8], rsi
0x180040a5c  mov     [rsp+0B00h+ppvObject], rsi
0x180040a61  xor     r8d, r8d; pMalloc
0x180040a64  lea     rdx, [rsp+0B00h+ppvObject]; ppvObject
0x180040a69  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180040a70  call    cs:__imp_CreateXmlReader
0x180040a76  test    eax, eax
0x180040a78  jz      loc_180040C36
0x180040a7e  lea     r9, aCreatexmlreade_0; "CreateXmlReader failed: [%#x]"
0x180040a85  mov     r8d, 176h
0x180040a8b  mov     dword ptr [rsp+0B00h+pstmTemplate], eax
0x180040a8f  lea     rdx, aAppvpackageIni; "AppvPackage::Initialize"
0x180040a96  mov     ecx, 3
0x180040a9b  call    AslLogCallPrintf
0x180040aa0  jmp     loc_18004162D
0x180040aa5  lea     r15, ??_7EpicGamesApplication@@6BIAmiInventoryTelemetryItem@@@; const EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'}
0x180040aac  lea     r12, ??_7AppvApplication@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x180040ab3  lea     r13, ??_7SteamApplication@@6B@; const SteamApplication::`vftable'
0x180040aba  lea     rdi, aAppvpackageIni; "AppvPackage::Initialize"
0x180040ac1  mov     esi, 3
0x180040ac6  xor     eax, eax
0x180040ac8  or      r8, 0FFFFFFFFFFFFFFFFh
0x180040acc  inc     r8
0x180040acf  cmp     [rbx+r8*2], ax
0x180040ad4  jnz     short loc_180040ACC
0x180040ad6  mov     rdx, rbx
0x180040ad9  lea     rcx, [rbp+0A00h+var_A30]
0x180040add  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180040ae2  lea     rcx, [rbp+0A00h+var_820]; this
0x180040ae9  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x180040aee  nop
0x180040aef  mov     [rbp+0A00h+var_820], r15
0x180040af6  mov     [rbp+0A00h+var_818], r12
0x180040afd  mov     [rbp+0A00h+var_810], r13
0x180040b04  lea     r8, [rbp+0A00h+var_A30]
0x180040b08  mov     rdx, [rsp+0B00h+var_A90]
0x180040b0d  lea     rcx, [rbp+0A00h+var_820]; struct IAmiInventoryItem *
0x180040b14  call    ?GetApplicationFromCache@Application@@QEAAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::GetApplicationFromCache(ConfigSettings const &,std::wstring const &)
0x180040b19  nop
0x180040b1a  cmp     [rbp+0A00h+var_7B0], 0
0x180040b22  jz      loc_180040BD2
0x180040b28  mov     edx, [rbp+0A00h+var_650]
0x180040b2e  lea     r8, [rbp+0A00h+var_780]
0x180040b35  cmp     [rbp+0A00h+var_768], 7
0x180040b3d  cmova   r8, [rbp+0A00h+var_780]
0x180040b45  lea     rcx, [rbp+0A00h+var_7A0]
0x180040b4c  cmp     [rbp+0A00h+var_788], 7
0x180040b54  cmova   rcx, [rbp+0A00h+var_7A0]
0x180040b5c  lea     rax, [rbp+0A00h+var_7C0]
0x180040b63  cmp     [rbp+0A00h+var_7A8], 7
0x180040b6b  cmova   rax, [rbp+0A00h+var_7C0]
0x180040b73  mov     dword ptr [rsp+0B00h+var_AC8], edx
0x180040b77  mov     [rsp+0B00h+var_AD0], r8
0x180040b7c  mov     [rsp+0B00h+ppstm], rcx
0x180040b81  mov     [rsp+0B00h+pstmTemplate], rax
0x180040b86  lea     r9, aAppvappWsWsWsD; "AppvApp >>>>>>>>>>> %ws, %ws, %ws, %d"
0x180040b8d  mov     r8d, 154h
0x180040b93  mov     rdx, rdi
0x180040b96  mov     ecx, esi
0x180040b98  call    AslLogCallPrintf
0x180040b9d  mov     rax, [r14+8]
0x180040ba1  cmp     rax, [r14+10h]
0x180040ba5  jz      short loc_180040BC0
0x180040ba7  lea     rdx, [rbp+0A00h+var_820]; struct Application *
0x180040bae  mov     rcx, rax; this
0x180040bb1  call    ??0Application@@QEAA@AEBV0@@Z; Application::Application(Application const &)
0x180040bb6  add     qword ptr [r14+8], 3F0h
0x180040bbe  jmp     short loc_180040BD2
0x180040bc0  lea     r8, [rbp+0A00h+var_820]
0x180040bc7  mov     rdx, rax
0x180040bca  mov     rcx, r14
0x180040bcd  call    ??$_Emplace_reallocate@AEBVApplication@@@?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@AEAAPEAVApplication@@QEAV2@AEBV2@@Z; std::vector<Application>::_Emplace_reallocate<Application const &>(Application * const,Application const &)
0x180040bd2  lea     rdx, ?m_programIdDelimiter@AppvPackage@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AppvPackage::m_programIdDelimiter
0x180040bd9  cmp     cs:qword_180183408, 7
0x180040be1  cmova   rdx, cs:?m_programIdDelimiter@AppvPackage@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; Delimiter
0x180040be9  lea     r8, [rsp+0B00h+Context]; Context
0x180040bee  xor     ecx, ecx; String
0x180040bf0  call    cs:__imp_wcstok_s
0x180040bf6  mov     rbx, rax
0x180040bf9  mov     [rbp+0A00h+var_820], r15
0x180040c00  mov     [rbp+0A00h+var_818], r12
0x180040c07  mov     [rbp+0A00h+var_810], r13
0x180040c0e  lea     rcx, [rbp+0A00h+var_820]; this
0x180040c15  call    ??1Application@@UEAA@XZ; Application::~Application(void)
0x180040c1a  xor     eax, eax
0x180040c1c  test    rbx, rbx
0x180040c1f  jnz     loc_180040AC8
0x180040c25  lea     rcx, [rbp+0A00h+var_430]; this
0x180040c2c  call    ??1Application@@UEAA@XZ; Application::~Application(void)
0x180040c31  jmp     loc_18004164D
0x180040c36  lea     rcx, [rbp+0A00h+pszFile]
0x180040c3a  cmp     [rbp+0A00h+var_978], 7
0x180040c42  cmova   rcx, [rbp+0A00h+pszFile]; pszFile
0x180040c47  lea     rax, [rsp+0B00h+var_AA8]
0x180040c4c  mov     [rsp+0B00h+ppstm], rax; ppstm
0x180040c51  mov     [rsp+0B00h+pstmTemplate], rsi; pstmTemplate
0x180040c56  xor     r9d, r9d; fCreate
0x180040c59  xor     r8d, r8d; dwAttributes
0x180040c5c  xor     edx, edx; grfMode
0x180040c5e  call    cs:__imp_SHCreateStreamOnFileEx
0x180040c64  test    eax, eax
0x180040c66  jz      short loc_180040CA5
0x180040c68  lea     rcx, [rbp+0A00h+pszFile]
0x180040c6c  cmp     [rbp+0A00h+var_978], 7
0x180040c74  cmova   rcx, [rbp+0A00h+pszFile]
0x180040c79  mov     dword ptr [rsp+0B00h+ppstm], eax
0x180040c7d  mov     [rsp+0B00h+pstmTemplate], rcx
0x180040c82  lea     r9, aShcreatestream; "SHCreateStreamOnFileEx failed for %ws ["...
0x180040c89  mov     r8d, 17Dh
0x180040c8f  lea     rdx, aAppvpackageIni; "AppvPackage::Initialize"
0x180040c96  mov     ecx, 3
0x180040c9b  call    AslLogCallPrintf
0x180040ca0  jmp     loc_18004162D
0x180040ca5  mov     rcx, [rsp+0B00h+ppvObject]
0x180040caa  mov     rax, [rcx]
0x180040cad  mov     rdx, [rsp+0B00h+var_AA8]
0x180040cb2  mov     rax, [rax+18h]
0x180040cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cbb  test    eax, eax
0x180040cbd  jz      short loc_180040CD1
0x180040cbf  lea     r9, aIxmlreaderSeti; "IXmlReader->SetInput failed: [%#x]"
0x180040cc6  mov     r8d, 184h
0x180040ccc  jmp     loc_180040A8B
0x180040cd1  lea     rcx, [rbp+0A00h+var_9F0]
0x180040cd5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180040cda  nop
0x180040cdb  lea     rcx, [rbp+0A00h+var_A50]
0x180040cdf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180040ce4  nop
0x180040ce5  lea     rcx, [rbp+0A00h+var_A10]
0x180040ce9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180040cee  nop
0x180040cef  lea     rcx, [rbp+0A00h+var_930]
0x180040cf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180040cfb  nop
0x180040cfc  lea     rcx, [rbp+0A00h+var_970]
0x180040d03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180040d08  nop
0x180040d09  lea     rcx, [rbp+0A00h+var_8D0]
0x180040d10  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180040d15  nop
0x180040d16  mov     dword ptr [rsp+0B00h+var_A98], esi
0x180040d1a  lea     r15, ??_7EpicGamesApplication@@6BIAmiInventoryTelemetryItem@@@; const EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'}
0x180040d21  lea     r12, ??_7AppvApplication@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x180040d28  lea     r13, ??_7SteamApplication@@6B@; const SteamApplication::`vftable'
0x180040d2f  lea     rdi, aAppvpackageIni; "AppvPackage::Initialize"
0x180040d36  mov     esi, 3
0x180040d3b  lea     rdx, aAssetintellige; "AssetIntelligenceProperties"
0x180040d42  lea     rcx, [rbp+0A00h+var_A70]
0x180040d46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040d4b  nop
0x180040d4c  lea     rdx, [rbp+0A00h+var_A70]
0x180040d50  mov     rcx, [rsp+0B00h+ppvObject]
0x180040d55  call    ?AdvanceToElementNode@AppvPackage@@SAJPEAUIXmlReader@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AppvPackage::AdvanceToElementNode(IXmlReader *,std::wstring const &)
0x180040d5a  mov     ebx, eax
0x180040d5c  lea     rcx, [rbp+0A00h+var_A70]
0x180040d60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040d65  xor     edx, edx
0x180040d67  test    ebx, ebx
0x180040d69  jnz     loc_180041206
0x180040d6f  mov     [rbp+0A00h+var_A20], rdx
0x180040d73  lea     rcx, [rbp+0A00h+var_A30]
0x180040d77  cmp     [rbp+0A00h+var_A18], 7
0x180040d7c  cmova   rcx, [rbp+0A00h+var_A30]
0x180040d81  mov     [rcx], dx
0x180040d84  mov     [rbp+0A00h+var_A40], rdx
0x180040d88  lea     rcx, [rbp+0A00h+var_A50]
0x180040d8c  cmp     [rbp+0A00h+var_A38], 7
0x180040d91  cmova   rcx, [rbp+0A00h+var_A50]
0x180040d96  mov     [rcx], dx
0x180040d99  mov     [rbp+0A00h+var_A00], rdx
0x180040d9d  lea     rcx, [rbp+0A00h+var_A10]
0x180040da1  cmp     [rbp+0A00h+var_9F8], 7
0x180040da6  cmova   rcx, [rbp+0A00h+var_A10]
0x180040dab  mov     [rcx], dx
0x180040dae  mov     [rbp+0A00h+var_920], rdx
0x180040db5  lea     rcx, [rbp+0A00h+var_930]
0x180040dbc  cmp     [rbp+0A00h+var_918], 7
0x180040dc4  cmova   rcx, [rbp+0A00h+var_930]
0x180040dcc  mov     [rcx], dx
  ... truncated ...
```
