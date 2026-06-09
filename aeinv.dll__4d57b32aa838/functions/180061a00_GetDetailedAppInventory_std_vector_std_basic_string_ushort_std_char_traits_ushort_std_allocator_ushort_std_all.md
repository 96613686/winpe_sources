# GetDetailedAppInventory(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,ushort * *)

- ea: `0x180061a00`
- end: `0x180062999`
- name: `?GetDetailedAppInventory@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0PEAPEAG@Z`
- size: `3993`
- prototype: ``
- caller_count: `0`
- callee_count: `57`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000b364`
- `0x18000b7cc`
- `0x18000dfc4`
- `0x18000e06c`
- `0x18000ecac`
- `0x1800118d0`
- `0x180016510`
- `0x180018300`
- `0x1800188f4`
- `0x180018a60`
- `0x1800197d4`
- `0x18001dbb4`
- `0x18001e0d0`
- `0x180026d38`
- `0x1800289d0`
- `0x18002b55c`
- `0x18002bdfc`
- `0x18002d3b8`
- `0x18002d580`
- `0x18002d5d0`
- `0x18002debc`
- `0x18002ee80`
- `0x180034908`
- `0x180034ff0`
- `0x18003e070`
- `0x1800403ac`
- `0x1800404c4`
- `0x1800417a8`
- `0x180046510`
- `0x18004662c`
- `0x18004db50`
- `0x18004dc14`
- `0x18004f3c4`
- `0x18004f820`
- `0x18005005c`
- `0x18005169c`
- `0x18005198c`
- `0x180051bc0`
- `0x180052dc0`
- `0x180052f28`
- `0x180054154`
- `0x180056140`
- `0x180059920`
- `0x18005a0ac`
- `0x18005a8bc`
- `0x18005d690`
- `0x18005e100`
- `0x180061a00`
- `0x180064288`
- `0x180067c64`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180062083`
- `KERNEL32!LoadLibraryW` at `0x180062083`
- `KERNEL32!GetCurrentThread` at `0x180061a5a`
- `KERNEL32!GetCurrentThread` at `0x180062923`
- `KERNEL32!GetCurrentThread` at `0x180061a5a`
- `KERNEL32!GetCurrentThread` at `0x180062923`
- `KERNEL32!QueryThreadCycleTime` at `0x180061a6b`
- `KERNEL32!QueryThreadCycleTime` at `0x180062934`
- `KERNEL32!QueryThreadCycleTime` at `0x180061a6b`
- `KERNEL32!QueryThreadCycleTime` at `0x180062934`
- `KERNEL32!GetTickCount` at `0x180061ad4`
- `KERNEL32!GetTickCount` at `0x180062879`
- `KERNEL32!GetTickCount` at `0x180061ad4`
- `KERNEL32!GetTickCount` at `0x180062879`
- `KERNEL32!GetProcAddress` at `0x1800620a0`
- `KERNEL32!GetProcAddress` at `0x1800620a0`
- `OLEAUT32!__imp_VariantClear` at `0x18006283f`
- `OLEAUT32!__imp_VariantClear` at `0x18006283f`

## string_xrefs

- `0x18006207c`: `devinv.dll`
- `0x180062125`: `Failed to find ProgramId: %ws in the cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=45 #try_helpers=1
__int64 __fastcall GetDetailedAppInventory(__int64 *a1, __int64 *a2, __int64 a3)
{
  int v5; // r13d
  HANDLE CurrentThread; // rax
  unsigned int v8; // edx
  struct THUNKS *v9; // rcx
  unsigned __int16 v10; // r8
  unsigned int v11; // edx
  int v12; // ebx
  int v13; // ebx
  Application *v14; // rax
  const unsigned __int16 *v15; // rdx
  int v16; // ebx
  File *v17; // rax
  const unsigned __int16 *v18; // rdx
  int v19; // ebx
  AmiFrameworkItem *v20; // rax
  const unsigned __int16 *v21; // rdx
  int v22; // ebx
  FARPROC ProcAddress; // r14
  HMODULE LibraryW; // rax
  __int64 v25; // rsi
  __int64 v26; // r12
  const struct ConfigSettings *v27; // rdx
  struct File **v28; // rax
  __int64 v29; // rdx
  const struct File *v30; // rbx
  struct File *v31; // rdi
  __int64 v32; // rax
  __int64 v33; // rdx
  _QWORD *v34; // rdx
  _QWORD *v35; // rcx
  _QWORD *v36; // rax
  __int64 v37; // r8
  __int64 v38; // r14
  __int64 v39; // r15
  __int64 v40; // r8
  __int128 i; // rdi
  _QWORD *v42; // rbx
  _QWORD *v43; // rax
  __int64 v44; // r9
  __int64 v45; // rdx
  char v46; // bl
  __int64 v47; // rax
  __int64 v48; // r8
  const struct File *v49; // rbx
  struct File *v50; // rdi
  __int64 v51; // rdi
  _bstr_t *v52; // rax
  unsigned int v53; // ebx
  const struct Application **v54; // rax
  HANDLE v55; // rax
  __int64 v56; // [rsp+20h] [rbp-20D8h]
  int v57; // [rsp+A0h] [rbp-2058h] BYREF
  int v58; // [rsp+A4h] [rbp-2054h] BYREF
  char v59[8]; // [rsp+A8h] [rbp-2050h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-2048h] BYREF
  __int64 v61; // [rsp+B8h] [rbp-2040h] BYREF
  File *v62; // [rsp+C0h] [rbp-2038h] BYREF
  Application *v63[2]; // [rsp+C8h] [rbp-2030h] BYREF
  Application *v64; // [rsp+D8h] [rbp-2020h]
  DWORD TickCount; // [rsp+E0h] [rbp-2018h]
  unsigned __int64 v66; // [rsp+E8h] [rbp-2010h] BYREF
  unsigned __int64 CycleTime[32]; // [rsp+F0h] [rbp-2008h] BYREF
  VARIANTARG pvarg; // [rsp+1F0h] [rbp-1F08h] BYREF
  struct File *v69[4]; // [rsp+210h] [rbp-1EE8h] BYREF
  struct File *v70[2]; // [rsp+230h] [rbp-1EC8h] BYREF
  __int64 v71; // [rsp+240h] [rbp-1EB8h]
  struct File *v72[2]; // [rsp+250h] [rbp-1EA8h] BYREF
  __int64 v73; // [rsp+260h] [rbp-1E98h]
  _BYTE v74[32]; // [rsp+270h] [rbp-1E88h] BYREF
  _BYTE v75[32]; // [rsp+290h] [rbp-1E68h] BYREF
  __int64 v76[4]; // [rsp+2B0h] [rbp-1E48h] BYREF
  __int64 v77; // [rsp+2D0h] [rbp-1E28h] BYREF
  char v78[80]; // [rsp+2D8h] [rbp-1E20h] BYREF
  __int64 v79; // [rsp+328h] [rbp-1DD0h]
  __int16 v80; // [rsp+330h] [rbp-1DC8h]
  __int64 v81; // [rsp+338h] [rbp-1DC0h]
  __int128 v82; // [rsp+340h] [rbp-1DB8h]
  __int64 v83; // [rsp+350h] [rbp-1DA8h]
  int v84; // [rsp+358h] [rbp-1DA0h]
  char v85; // [rsp+35Ch] [rbp-1D9Ch]
  __int64 v86; // [rsp+360h] [rbp-1D98h] BYREF
  char v87[80]; // [rsp+368h] [rbp-1D90h] BYREF
  __int64 v88; // [rsp+3B8h] [rbp-1D40h]
  __int16 v89; // [rsp+3C0h] [rbp-1D38h]
  __int64 v90; // [rsp+3C8h] [rbp-1D30h]
  __int128 v91; // [rsp+3D0h] [rbp-1D28h]
  __int64 v92; // [rsp+3E0h] [rbp-1D18h]
  int v93; // [rsp+3E8h] [rbp-1D10h]
  char v94; // [rsp+3ECh] [rbp-1D0Ch]
  __int64 v95; // [rsp+3F0h] [rbp-1D08h] BYREF
  char v96[80]; // [rsp+3F8h] [rbp-1D00h] BYREF
  __int64 v97; // [rsp+448h] [rbp-1CB0h]
  __int16 v98; // [rsp+450h] [rbp-1CA8h]
  __int64 v99; // [rsp+458h] [rbp-1CA0h]
  __int128 v100; // [rsp+460h] [rbp-1C98h]
  __int64 v101; // [rsp+470h] [rbp-1C88h]
  int v102; // [rsp+478h] [rbp-1C80h]
  char v103; // [rsp+47Ch] [rbp-1C7Ch]
  _BYTE v104[240]; // [rsp+480h] [rbp-1C78h] BYREF
  _BYTE v105[40]; // [rsp+570h] [rbp-1B88h] BYREF
  __int64 *v106; // [rsp+598h] [rbp-1B60h]
  _BYTE v107[24]; // [rsp+660h] [rbp-1A98h] BYREF
  _BYTE v108[32]; // [rsp+678h] [rbp-1A80h] BYREF
  char v109; // [rsp+698h] [rbp-1A60h] BYREF
  char v110[552]; // [rsp+720h] [rbp-19D8h] BYREF
  __int64 v111[12]; // [rsp+948h] [rbp-17B0h] BYREF
  char v112[32]; // [rsp+9A8h] [rbp-1750h] BYREF
  char v113[32]; // [rsp+9C8h] [rbp-1730h] BYREF
  _QWORD v114[4]; // [rsp+9E8h] [rbp-1710h] BYREF
  _QWORD v115[9]; // [rsp+A08h] [rbp-16F0h] BYREF
  _BYTE v116[24]; // [rsp+A50h] [rbp-16A8h] BYREF
  _QWORD v117[3]; // [rsp+A68h] [rbp-1690h] BYREF
  unsigned __int64 v118; // [rsp+A80h] [rbp-1678h]
  _QWORD v119[87]; // [rsp+AC8h] [rbp-1630h] BYREF
  _BYTE v120[816]; // [rsp+D80h] [rbp-1378h] BYREF
  _BYTE v121[24]; // [rsp+10B0h] [rbp-1048h] BYREF
  __int64 *v122; // [rsp+10C8h] [rbp-1030h] BYREF
  char v123[3696]; // [rsp+1240h] [rbp-EB8h] BYREF

  CycleTime[1] = -2;
  v61 = a3;
  v5 = 0;
  CycleTime[0] = 0;
  v66 = 0;
  CurrentThread = GetCurrentThread();
  QueryThreadCycleTime(CurrentThread, CycleTime);
  if ( a1[1] == *a1 && a2[1] == *a2 )
  {
    AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventory", 305, (unsigned int)"No IDs provided [0x%08x]");
    AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventory", 306, (unsigned int)"[%#x]");
    return 2147942487LL;
  }
  TickCount = GetTickCount();
  DownlevelThunksInitEx(v9, v8);
  v57 = -2147221008;
  v58 = -2147221008;
  if ( IsWindowsVersionOrGreater(6u, 2u, v10) )
  {
    v12 = Common::AutoWinRTInitialize::Initialize(&v58);
    if ( v12 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventory", 318, (unsigned int)"[%#x]");
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v58);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v57);
      return (unsigned int)v12;
    }
  }
  else
  {
    v13 = Common::AutoCoInitialize::Initialize((Common::AutoCoInitialize *)&v57, v11);
    if ( v13 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventory", 322, (unsigned int)"[%#x]");
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v58);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v57);
      return (unsigned int)v13;
    }
  }
  memset_0(v78, 0, 0x4Eu);
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v79 = 0;
  v77 = 0;
  v62 = (File *)operator new(0x3F0u);
  v14 = Application::Application(v62);
  v15 = (const unsigned __int16 *)&Application::ApplicationCacheProviderName;
  if ( (unsigned __int64)qword_180182A38 > 7 )
    v15 = (const unsigned __int16 *)Application::ApplicationCacheProviderName;
  v16 = TelCacheProvider::Initialize(&v77, v15, (__int64)v14, 0, 2, 5u, 0x1F4u);
  if ( v16 >= 0 )
  {
    memset_0(v87, 0, 0x4Eu);
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v88 = 0;
    v86 = 0;
    v62 = (File *)operator new(0x330u);
    v17 = File::File(v62);
    v18 = (const unsigned __int16 *)&File::FileCacheProviderName;
    if ( (unsigned __int64)qword_180183038 > 7 )
      v18 = (const unsigned __int16 *)File::FileCacheProviderName;
    v19 = TelCacheProvider::Initialize(&v86, v18, ((unsigned __int64)v17 + 8) & -(__int64)(v17 != 0), 0, 2, 5u, 0x1F4u);
    if ( v19 >= 0 )
    {
      memset_0(v96, 0, 0x4Eu);
      v98 = 0;
      v99 = 0;
      v100 = 0;
      v101 = 0;
      v102 = 0;
      v103 = 0;
      v97 = 0;
      v95 = 0;
      v62 = (File *)operator new(0x90u);
      v20 = AmiFrameworkItem::AmiFrameworkItem(v62);
      v21 = (const unsigned __int16 *)&AmiFrameworkItem::ApplicationFrameworkCacheProviderName;
      if ( (unsigned __int64)qword_180183278 > 7 )
        v21 = (const unsigned __int16 *)AmiFrameworkItem::ApplicationFrameworkCacheProviderName;
      v22 = TelCacheProvider::Initialize(&v95, v21, (__int64)v20, 0, 2, 5u, 0x1F4u);
      if ( v22 >= 0 )
      {
        std::wstring::wstring(v74, &byte_1801389F0);
        std::wstring::wstring(&pvarg, &byte_1801389F0);
        std::wstring::wstring(v70, &byte_1801389F0);
        std::wstring::wstring(v72, &byte_1801389F0);
        std::wstring::wstring(v69, &byte_1801389F0);
        ConfigSettings::ConfigSettings(
          (unsigned int)v105,
          2,
          (unsigned int)&v77,
          (unsigned int)&v86,
          0,
          0,
          3,
          (__int64)v69,
          (__int64)v72,
          (__int64)v70,
          (__int64)&pvarg,
          (__int64)v74,
          1);
        std::wstring::~wstring(v69);
        std::wstring::~wstring(v72);
        std::wstring::~wstring(v70);
        std::wstring::~wstring(&pvarg);
        std::wstring::~wstring(v74);
        v106 = &v95;
        *(_OWORD *)v63 = 0;
        v64 = 0;
        ProcAddress = 0;
        LibraryW = LoadLibraryW(L"devinv.dll");
        v62 = (File *)LibraryW;
        if ( LibraryW )
          ProcAddress = GetProcAddress(LibraryW, "GetAndSendSigningInfo");
        v25 = *a1;
        v26 = a1[1];
        while ( v25 != v26 )
        {
          std::wstring::wstring(v69, v25);
          Application::Application((Application *)v121);
          Application::GetApplicationFromCache((struct IAmiInventoryItem *)v121);
          if ( Application::IsValid((Application *)v121, v27) )
          {
            memset(&pvarg, 0, sizeof(pvarg));
            *(_OWORD *)v72 = 0;
            v73 = 0;
            v29 = *v122;
            v60 = *v122;
            while ( !*(_BYTE *)(v29 + 25) )
            {
              File::File((File *)v107, (const struct File *)(v29 + 32));
              if ( (IRecordInfo *)pvarg.llVal == pvarg.pRecInfo )
              {
                std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&pvarg, pvarg.llVal, v108);
              }
              else
              {
                std::wstring::wstring(pvarg.llVal, v108);
                pvarg.llVal += 32LL;
              }
              File::~File((File *)v107);
              std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<File>>,std::_Iterator_base0>::operator++(&v60);
              v29 = v60;
            }
            File::GetFilesFromPaths((__int64)v70, (const struct ConfigSettings *)v105, (int)v69, 0, (__int64)v72);
            std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::clear(&v122);
            v30 = v70[0];
            v31 = v70[1];
            while ( v30 != v31 )
            {
              File::File((File *)v120, v30);
              Application::SetFile((Application *)v121, (const struct File *)v120);
              File::~File((File *)v120);
              v30 = (const struct File *)((char *)v30 + 816);
            }
            v32 = Application::ComputeProgramInstanceId((__int64)v121, (__int64)v76);
            std::wstring::operator=(v123, v32);
            std::wstring::~wstring(v76);
            if ( ProcAddress )
            {
              v33 = *v122;
              v60 = *v122;
              while ( !*(_BYTE *)(v33 + 25) )
              {
                File::File((File *)v116, (const struct File *)(v33 + 32));
                v34 = v119;
                if ( v119[3] > 7u )
                  v34 = (_QWORD *)v119[0];
                v35 = v117;
                if ( v118 > 7 )
                  v35 = (_QWORD *)v117[0];
                v5 = ((__int64 (__fastcall *)(_QWORD *, _QWORD *, const unsigned __int16 *, const unsigned __int16 *))ProcAddress)(
                       v35,
                       v34,
                       &byte_1801389F0,
                       &byte_1801389F0);
                if ( v5 < 0 )
                {
                  v36 = v117;
                  if ( v118 > 7 )
                    LODWORD(v36) = v117[0];
                  LODWORD(v56) = (_DWORD)v36;
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"GetDetailedAppInventory",
                    406,
                    (unsigned int)"Failed to send FileSigning data for: %ws [0x%08x]");
                }
                File::~File((File *)v116);
                std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<File>>,std::_Iterator_base0>::operator++(&v60);
                v33 = v60;
              }
            }
            AmiFrameworkItem::AmiFrameworkItem((struct IAmiInventoryItem *)v104);
            AmiFrameworkItem::SendFrameworkEvent((AmiFrameworkItem *)v104);
            if ( v63[1] == v64 )
            {
              std::vector<Application>::_Emplace_reallocate<Application const &>(v63, v63[1], v121);
            }
            else
            {
              Application::Application(v63[1], (const struct Application *)v121, v37);
              v63[1] = (Application *)((char *)v63[1] + 1008);
            }
            AmiFrameworkItem::~AmiFrameworkItem((AmiFrameworkItem *)v104);
            std::vector<File>::_Tidy(v70);
            std::vector<std::wstring>::_Tidy(v72);
            std::vector<std::wstring>::_Tidy(&pvarg);
          }
          else
          {
            v28 = v69;
            if ( v69[3] > (struct File *)7 )
              LODWORD(v28) = v69[0];
            LODWORD(v56) = (_DWORD)v28;
            AslLogCallPrintf(
              1,
              (unsigned int)"GetDetailedAppInventory",
              375,
              (unsigned int)"Failed to find ProgramId: %ws in the cache");
          }
          Application::~Application((Application *)v121);
          std::wstring::~wstring(v69);
          v25 += 32;
        }
        if ( (a2[1] - *a2) >> 5 )
        {
          ConfigSettings::ConfigSettings(v104, 5, &v77, &v86);
          Application::GetApplicationsFromCache(&pvarg, v104);
          v38 = *a2;
          v39 = a2[1];
          while ( v38 != v39 )
          {
            std::wstring::wstring(v76, v38);
            for ( i = *(_OWORD *)&pvarg.vt; (_QWORD)i != *((_QWORD *)&i + 1); *(_QWORD *)&i = i + 1008 )
            {
              Application::Application((Application *)v107, (const struct Application *)i, v40);
              v42 = (_QWORD *)Utility::ToLower((__int64)v74, v111);
              v43 = (_QWORD *)Utility::ToLower((__int64)v75, v76);
              v44 = v42[2];
              if ( v42[3] > 7u )
                v42 = (_QWORD *)*v42;
              v45 = v43[2];
              if ( v43[3] > 7u )
                v43 = (_QWORD *)*v43;
              v46 = std::_Traits_equal<std::char_traits<unsigned short>>(v43, v45, v42, v44, v56);
              std::wstring::~wstring(v75);
              std::wstring::~wstring(v74);
              if ( v46 )
              {
                if ( v114[2] )
                {
                  StoreApplication::GetStoreAppManifestXml((__int64)v74, v114, 1);
                  std::wstring::operator=(v112, v74);
                  std::wstring::~wstring(v74);
                }
                if ( v115[2] )
                {
                  StoreApplication::GetStoreAppManifestXml((__int64)v74, v115, 0);
                  std::wstring::operator=(v113, v74);
                  std::wstring::~wstring(v74);
                }
                std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::clear(v108);
                std::wstring::wstring(v75, v110);
                *(_OWORD *)v70 = 0;
                v71 = 0;
                v47 = std::vector<std::wstring>::vector<std::wstring>(v69, v70);
                File::SearchForPeFiles(
                  (__int64)v72,
                  (const struct ConfigSettings *)v105,
                  (__int64)v75,
                  v47,
                  v56,
                  (int)&v109,
                  0);
                v49 = v72[0];
                v50 = v72[1];
                while ( v49 != v50 )
                {
                  File::File((File *)v120, v49);
                  Application::SetFile((Application *)v107, (const struct File *)v120);
                  File::~File((File *)v120);
                  v49 = (const struct File *)((char *)v49 + 816);
                }
                if ( v63[1] == v64 )
                {
                  std::vector<Application>::_Emplace_reallocate<Application const &>(v63, v63[1], v107);
                }
                else
                {
                  Application::Application(v63[1], (const struct Application *)v107, v48);
                  v63[1] = (Application *)((char *)v63[1] + 1008);
                }
                std::vector<File>::_Tidy(v72);
                std::vector<std::wstring>::_Tidy(v70);
                std::wstring::~wstring(v75);
                Application::~Application((Application *)v107);
                break;
              }
              Application::~Application((Application *)v107);
            }
            std::wstring::~wstring(v76);
            v38 += 32;
          }
          std::vector<Application>::_Tidy(&pvarg);
          ConfigSettings::~ConfigSettings((ConfigSettings *)v104);
        }
        v51 = v61;
        pvarg.vt = 11;
        if ( v61 )
          pvarg.iVal = -1;
        else
          pvarg.iVal = 0;
        v52 = _bstr_t::_bstr_t((_bstr_t *)&v61, (const struct _variant_t *)&pvarg);
        v53 = _bstr_t::length(v52);
        _bstr_t::~_bstr_t((_bstr_t *)&v61);
        VariantClear(&pvarg);
        if ( v53 )
        {
          v54 = (const struct Application **)std::vector<Application>::vector<Application>(v69, v63);
          XmlBuilder::XmlBuilder((__int64)v59, (__int64)v105, v54, v51);
        }
        GetTickCount();
        AslLogCallPrintf(
          3,
          (unsigned int)"GetDetailedAppInventory",
          472,
          (unsigned int)"GetDetailedAppInventory elapsed time: %d");
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v62);
        std::vector<Application>::_Tidy(v63);
        ConfigSettings::~ConfigSettings((ConfigSettings *)v105);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v95);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v86);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v77);
        Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v58);
        Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v57);
        v55 = GetCurrentThread();
        QueryThreadCycleTime(v55, &v66);
        AslTelemetryTrackMetric(
          qword_1801822A0,
          "AppInv_Detailed_Cpu_mCycles",
          (unsigned int)((v66 - CycleTime[0]) / 0xF4240));
        return (unsigned int)v5;
      }
      else
      {
        AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventory", 335, (unsigned int)"[%#x]");
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v95);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v86);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v77);
        Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v58);
        Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v57);
        return (unsigned int)v22;
      }
    }
    else
    {
      AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventory", 331, (unsigned int)"[%#x]");
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v86);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v77);
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v58);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v57);
      return (unsigned int)v19;
    }
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"GetDetailedAppInventory", 327, (unsigned int)"[%#x]");
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v77);
    Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v58);
    Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v57);
    return (unsigned int)v16;
  }
}

```

## disassembly

```asm
0x180061a00  push    rbx
0x180061a02  push    rsi
0x180061a03  push    rdi
0x180061a04  push    r12
0x180061a06  push    r13
0x180061a08  push    r14
0x180061a0a  push    r15
0x180061a0c  mov     eax, 20C0h
0x180061a11  call    _alloca_probe
0x180061a16  sub     rsp, rax
0x180061a19  mov     [rsp+20F8h+var_2000], 0FFFFFFFFFFFFFFFEh
0x180061a25  mov     rax, cs:__security_cookie
0x180061a2c  xor     rax, rsp
0x180061a2f  mov     [rsp+20F8h+var_48], rax
0x180061a37  mov     [rsp+20F8h+var_2040], r8
0x180061a3f  mov     r15, rdx
0x180061a42  mov     rdi, rcx
0x180061a45  xor     esi, esi
0x180061a47  mov     r13d, esi
0x180061a4a  mov     [rsp+20F8h+CycleTime], rsi
0x180061a52  mov     [rsp+20F8h+var_2010], rsi
0x180061a5a  call    cs:__imp_GetCurrentThread
0x180061a60  mov     rcx, rax; ThreadHandle
0x180061a63  lea     rdx, [rsp+20F8h+CycleTime]; CycleTime
0x180061a6b  call    cs:__imp_QueryThreadCycleTime
0x180061a71  nop
0x180061a72  mov     rax, [rdi+8]
0x180061a76  cmp     rax, [rdi]
0x180061a79  jnz     short loc_180061AD4
0x180061a7b  mov     rax, [r15+8]
0x180061a7f  cmp     rax, [r15]
0x180061a82  jnz     short loc_180061AD4
0x180061a84  mov     dword ptr [rsp+20F8h+var_20D8], 57h ; 'W'
0x180061a8c  lea     r9, aNoIdsProvided0; "No IDs provided [0x%08x]"
0x180061a93  mov     r8d, 131h
0x180061a99  lea     rdx, aGetdetailedapp_4; "GetDetailedAppInventory"
0x180061aa0  lea     ecx, [rsi+1]
0x180061aa3  call    AslLogCallPrintf
0x180061aa8  mov     ebx, 80070057h
0x180061aad  mov     dword ptr [rsp+20F8h+var_20D8], ebx
0x180061ab1  lea     r9, asc_18013E640; "[%#x]"
0x180061ab8  mov     r8d, 132h
0x180061abe  lea     rdx, aGetdetailedapp_4; "GetDetailedAppInventory"
0x180061ac5  lea     ecx, [rsi+1]
0x180061ac8  call    AslLogCallPrintf
0x180061acd  mov     eax, ebx
0x180061acf  jmp     loc_180062974
0x180061ad4  call    cs:__imp_GetTickCount
0x180061ada  mov     [rsp+20F8h+var_2018], eax
0x180061ae1  call    ?DownlevelThunksInitEx@@YAHPEAUTHUNKS@@K@Z; DownlevelThunksInitEx(THUNKS *,ulong)
0x180061ae6  mov     eax, 800401F0h
0x180061aeb  mov     [rsp+20F8h+var_2058], eax
0x180061af2  mov     [rsp+20F8h+var_2054], eax
0x180061af9  mov     edx, 2; unsigned __int16
0x180061afe  lea     ecx, [rdx+4]; unsigned __int16
0x180061b01  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180061b06  test    al, al
0x180061b08  jz      short loc_180061B66
0x180061b0a  lea     rcx, [rsp+20F8h+var_2054]
0x180061b12  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x180061b17  mov     ebx, eax
0x180061b19  test    eax, eax
0x180061b1b  jns     loc_180061BBE
0x180061b21  mov     dword ptr [rsp+20F8h+var_20D8], eax
0x180061b25  lea     r9, asc_18013E640; "[%#x]"
0x180061b2c  mov     r8d, 13Eh
0x180061b32  lea     rdx, aGetdetailedapp_4; "GetDetailedAppInventory"
0x180061b39  mov     ecx, 1
0x180061b3e  call    AslLogCallPrintf
0x180061b43  nop
0x180061b44  lea     rcx, [rsp+20F8h+var_2054]; this
0x180061b4c  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180061b51  nop
0x180061b52  lea     rcx, [rsp+20F8h+var_2058]; this
0x180061b5a  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180061b5f  mov     eax, ebx
0x180061b61  jmp     loc_180062974
0x180061b66  lea     rcx, [rsp+20F8h+var_2058]; this
0x180061b6e  call    ?Initialize@AutoCoInitialize@Common@@QEAAJK@Z; Common::AutoCoInitialize::Initialize(ulong)
0x180061b73  mov     ebx, eax
0x180061b75  test    eax, eax
0x180061b77  jns     short loc_180061BBE
0x180061b79  mov     dword ptr [rsp+20F8h+var_20D8], eax
0x180061b7d  lea     r9, asc_18013E640; "[%#x]"
0x180061b84  mov     r8d, 142h
0x180061b8a  lea     rdx, aGetdetailedapp_4; "GetDetailedAppInventory"
0x180061b91  mov     ecx, 1
0x180061b96  call    AslLogCallPrintf
0x180061b9b  nop
0x180061b9c  lea     rcx, [rsp+20F8h+var_2054]; this
0x180061ba4  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180061ba9  nop
0x180061baa  lea     rcx, [rsp+20F8h+var_2058]; this
0x180061bb2  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180061bb7  mov     eax, ebx
0x180061bb9  jmp     loc_180062974
0x180061bbe  mov     r14d, 4Eh ; 'N'
0x180061bc4  mov     r8d, r14d; Size
0x180061bc7  xor     edx, edx; Val
0x180061bc9  lea     rcx, [rsp+20F8h+var_1E20]; void *
0x180061bd1  call    memset_0
0x180061bd6  mov     [rsp+20F8h+var_1DC8], si
0x180061bde  mov     [rsp+20F8h+var_1DC0], rsi
0x180061be6  xorps   xmm0, xmm0
0x180061be9  movdqa  [rsp+20F8h+var_1DB8], xmm0
0x180061bf2  mov     [rsp+20F8h+var_1DA8], rsi
0x180061bfa  mov     [rsp+20F8h+var_1DA0], esi
0x180061c01  mov     [rsp+20F8h+var_1D9C], sil
0x180061c09  mov     [rsp+20F8h+var_1DD0], rsi
0x180061c11  mov     [rsp+20F8h+var_1E28], rsi
0x180061c19  mov     ecx, 3F0h; Size
0x180061c1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061c23  mov     [rsp+20F8h+var_2038], rax
0x180061c2b  mov     rcx, rax; this
0x180061c2e  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x180061c33  nop
0x180061c34  lea     rdx, ?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x180061c3b  cmp     cs:qword_180182A38, 7
0x180061c43  cmova   rdx, cs:?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x180061c4b  mov     r12d, 1F4h
0x180061c51  mov     [rsp+20F8h+var_20C8], r12d
0x180061c56  mov     dword ptr [rsp+20F8h+var_20D0], 5
0x180061c5e  mov     dword ptr [rsp+20F8h+var_20D8], 2
0x180061c66  xor     r9d, r9d
0x180061c69  mov     r8, rax
0x180061c6c  lea     rcx, [rsp+20F8h+var_1E28]
0x180061c74  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180061c79  mov     ebx, eax
0x180061c7b  test    eax, eax
0x180061c7d  jns     short loc_180061CD1
0x180061c7f  mov     dword ptr [rsp+20F8h+var_20D8], eax
0x180061c83  lea     r9, asc_18013E640; "[%#x]"
0x180061c8a  mov     r8d, 147h
0x180061c90  lea     rdx, aGetdetailedapp_4; "GetDetailedAppInventory"
0x180061c97  lea     ecx, [r14-4Dh]
0x180061c9b  call    AslLogCallPrintf
0x180061ca0  nop
0x180061ca1  lea     rcx, [rsp+20F8h+var_1E28]; this
0x180061ca9  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180061cae  nop
0x180061caf  lea     rcx, [rsp+20F8h+var_2054]; this
0x180061cb7  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180061cbc  nop
0x180061cbd  lea     rcx, [rsp+20F8h+var_2058]; this
0x180061cc5  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180061cca  mov     eax, ebx
0x180061ccc  jmp     loc_180062974
0x180061cd1  mov     r8, r14; Size
0x180061cd4  xor     edx, edx; Val
0x180061cd6  lea     rcx, [rsp+20F8h+var_1D90]; void *
0x180061cde  call    memset_0
0x180061ce3  mov     [rsp+20F8h+var_1D38], si
0x180061ceb  mov     [rsp+20F8h+var_1D30], rsi
0x180061cf3  xorps   xmm0, xmm0
0x180061cf6  movdqa  [rsp+20F8h+var_1D28], xmm0
0x180061cff  mov     [rsp+20F8h+var_1D18], rsi
0x180061d07  mov     [rsp+20F8h+var_1D10], esi
0x180061d0e  mov     [rsp+20F8h+var_1D0C], sil
0x180061d16  mov     [rsp+20F8h+var_1D40], rsi
0x180061d1e  mov     [rsp+20F8h+var_1D98], rsi
0x180061d26  mov     ecx, 330h; Size
0x180061d2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061d30  mov     [rsp+20F8h+var_2038], rax
0x180061d38  mov     rcx, rax; this
0x180061d3b  call    ??0File@@QEAA@XZ; File::File(void)
0x180061d40  mov     rcx, rax
0x180061d43  add     rax, 8
0x180061d47  neg     rcx
0x180061d4a  sbb     r8, r8
0x180061d4d  and     r8, rax
0x180061d50  lea     rdx, ?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x180061d57  cmp     cs:qword_180183038, 7
0x180061d5f  cmova   rdx, cs:?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x180061d67  mov     [rsp+20F8h+var_20C8], r12d
0x180061d6c  mov     dword ptr [rsp+20F8h+var_20D0], 5
0x180061d74  mov     dword ptr [rsp+20F8h+var_20D8], 2
0x180061d7c  xor     r9d, r9d
0x180061d7f  lea     rcx, [rsp+20F8h+var_1D98]
0x180061d87  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180061d8c  mov     ebx, eax
0x180061d8e  test    eax, eax
0x180061d90  jns     short loc_180061DF3
0x180061d92  mov     dword ptr [rsp+20F8h+var_20D8], eax
0x180061d96  lea     r9, asc_18013E640; "[%#x]"
0x180061d9d  mov     r8d, 14Bh
0x180061da3  lea     rdx, aGetdetailedapp_4; "GetDetailedAppInventory"
0x180061daa  mov     ecx, 1
0x180061daf  call    AslLogCallPrintf
0x180061db4  nop
0x180061db5  lea     rcx, [rsp+20F8h+var_1D98]; this
0x180061dbd  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180061dc2  nop
0x180061dc3  lea     rcx, [rsp+20F8h+var_1E28]; this
0x180061dcb  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180061dd0  nop
0x180061dd1  lea     rcx, [rsp+20F8h+var_2054]; this
0x180061dd9  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180061dde  nop
0x180061ddf  lea     rcx, [rsp+20F8h+var_2058]; this
0x180061de7  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180061dec  mov     eax, ebx
0x180061dee  jmp     loc_180062974
0x180061df3  mov     r8, r14; Size
0x180061df6  xor     edx, edx; Val
0x180061df8  lea     rcx, [rsp+20F8h+var_1D00]; void *
0x180061e00  call    memset_0
0x180061e05  mov     [rsp+20F8h+var_1CA8], si
0x180061e0d  mov     [rsp+20F8h+var_1CA0], rsi
0x180061e15  xorps   xmm0, xmm0
0x180061e18  movdqa  [rsp+20F8h+var_1C98], xmm0
0x180061e21  mov     [rsp+20F8h+var_1C88], rsi
0x180061e29  mov     [rsp+20F8h+var_1C80], esi
0x180061e30  mov     [rsp+20F8h+var_1C7C], sil
0x180061e38  mov     [rsp+20F8h+var_1CB0], rsi
0x180061e40  mov     [rsp+20F8h+var_1D08], rsi
0x180061e48  mov     ecx, 90h; Size
0x180061e4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061e52  mov     [rsp+20F8h+var_2038], rax
0x180061e5a  mov     rcx, rax; this
0x180061e5d  call    ??0AmiFrameworkItem@@QEAA@XZ; AmiFrameworkItem::AmiFrameworkItem(void)
0x180061e62  nop
0x180061e63  lea     rdx, ?ApplicationFrameworkCacheProviderName@AmiFrameworkItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiFrameworkItem::ApplicationFrameworkCacheProviderName
0x180061e6a  cmp     cs:qword_180183278, 7
0x180061e72  cmova   rdx, cs:?ApplicationFrameworkCacheProviderName@AmiFrameworkItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiFrameworkItem::ApplicationFrameworkCacheProviderName
0x180061e7a  mov     [rsp+20F8h+var_20C8], r12d
0x180061e7f  mov     dword ptr [rsp+20F8h+var_20D0], 5
0x180061e87  mov     r14d, 2
0x180061e8d  mov     dword ptr [rsp+20F8h+var_20D8], r14d
0x180061e92  xor     r9d, r9d
0x180061e95  mov     r8, rax
0x180061e98  lea     rcx, [rsp+20F8h+var_1D08]
0x180061ea0  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180061ea5  mov     ebx, eax
0x180061ea7  test    eax, eax
0x180061ea9  jns     short loc_180061F19
0x180061eab  mov     dword ptr [rsp+20F8h+var_20D8], eax
0x180061eaf  lea     r9, asc_18013E640; "[%#x]"
0x180061eb6  mov     r8d, 14Fh
0x180061ebc  lea     rdx, aGetdetailedapp_4; "GetDetailedAppInventory"
0x180061ec3  lea     ecx, [r14-1]
0x180061ec7  call    AslLogCallPrintf
0x180061ecc  nop
0x180061ecd  lea     rcx, [rsp+20F8h+var_1D08]; this
0x180061ed5  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180061eda  nop
0x180061edb  lea     rcx, [rsp+20F8h+var_1D98]; this
0x180061ee3  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180061ee8  nop
0x180061ee9  lea     rcx, [rsp+20F8h+var_1E28]; this
0x180061ef1  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180061ef6  nop
0x180061ef7  lea     rcx, [rsp+20F8h+var_2054]; this
0x180061eff  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180061f04  nop
0x180061f05  lea     rcx, [rsp+20F8h+var_2058]; this
0x180061f0d  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180061f12  mov     eax, ebx
0x180061f14  jmp     loc_180062974
0x180061f19  lea     rbx, byte_1801389F0
0x180061f20  mov     rdx, rbx
0x180061f23  lea     rcx, [rsp+20F8h+var_1E88]
0x180061f2b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180061f30  nop
0x180061f31  mov     rdx, rbx
0x180061f34  lea     rcx, [rsp+20F8h+pvarg]
0x180061f3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180061f41  nop
0x180061f42  mov     rdx, rbx
0x180061f45  lea     rcx, [rsp+20F8h+var_1EC8]
0x180061f4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180061f52  nop
0x180061f53  mov     rdx, rbx
0x180061f56  lea     rcx, [rsp+20F8h+var_1EA8]
0x180061f5e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180061f63  nop
0x180061f64  mov     rdx, rbx
0x180061f67  lea     rcx, [rsp+20F8h+var_1EE8]
0x180061f6f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180061f74  nop
0x180061f75  mov     [rsp+20F8h+var_2060], sil
0x180061f7d  mov     [rsp+20F8h+var_2068], 1
0x180061f85  mov     [rsp+20F8h+var_2078], 1
0x180061f8d  mov     [rsp+20F8h+var_2080], 1
0x180061f92  mov     [rsp+20F8h+var_2088], sil
0x180061f97  mov     [rsp+20F8h+var_2098], 1
0x180061f9c  lea     rax, [rsp+20F8h+var_1E88]
0x180061fa4  mov     [rsp+20F8h+var_20A0], rax
0x180061fa9  lea     rax, [rsp+20F8h+pvarg]
0x180061fb1  mov     [rsp+20F8h+var_20A8], rax
0x180061fb6  lea     rax, [rsp+20F8h+var_1EC8]
0x180061fbe  mov     [rsp+20F8h+var_20B0], rax
0x180061fc3  lea     rax, [rsp+20F8h+var_1EA8]
0x180061fcb  mov     [rsp+20F8h+var_20B8], rax
0x180061fd0  lea     rax, [rsp+20F8h+var_1EE8]
0x180061fd8  mov     [rsp+20F8h+var_20C0], rax
0x180061fdd  mov     [rsp+20F8h+var_20C8], 3
0x180061fe5  mov     byte ptr [rsp+20F8h+var_20D0], sil
0x180061fea  mov     byte ptr [rsp+20F8h+var_20D8], sil
0x180061fef  lea     r9, [rsp+20F8h+var_1D98]
0x180061ff7  lea     r8, [rsp+20F8h+var_1E28]
  ... truncated ...
```
