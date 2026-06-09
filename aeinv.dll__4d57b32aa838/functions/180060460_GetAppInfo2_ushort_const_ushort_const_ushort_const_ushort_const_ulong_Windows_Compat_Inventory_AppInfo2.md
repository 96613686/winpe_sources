# GetAppInfo2(ushort const *,ushort const *,ushort const *,ushort const *,ulong,Windows::Compat::Inventory::AppInfo2 *)

- ea: `0x180060460`
- end: `0x180061246`
- name: `?GetAppInfo2@@YAPEAUAppInfo2@Inventory@Compat@Windows@@PEBG000KPEAU1234@@Z`
- size: `3558`
- prototype: `struct Windows::Compat::Inventory::AppInfo2 *__fastcall(const unsigned __int16 *, wchar_t *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct Windows::Compat::Inventory::AppInfo2 *)`
- caller_count: `0`
- callee_count: `43`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b7cc`
- `0x18000ecac`
- `0x18000f700`
- `0x1800112bc`
- `0x1800118d0`
- `0x18001249c`
- `0x180012a10`
- `0x180013fc4`
- `0x1800150ac`
- `0x1800175b0`
- `0x180017968`
- `0x180018450`
- `0x1800188f4`
- `0x180018a60`
- `0x1800197d4`
- `0x18001d3ec`
- `0x18001dbb4`
- `0x18001e0d0`
- `0x1800218c0`
- `0x1800289d0`
- `0x18002b55c`
- `0x18002d3b8`
- `0x18002debc`
- `0x180030c70`
- `0x1800403ac`
- `0x1800404c4`
- `0x1800417a8`
- `0x180045480`
- `0x180046510`
- `0x180046cdc`
- `0x180052fc8`
- `0x180059920`
- `0x18005a0ac`
- `0x18005a8bc`
- `0x180060460`
- `0x180067cd8`
- `0x1800f863c`
- `0x1800f98e8`
- `0x1800ff6f4`
- `0x18010e8c8`
- `0x180125400`
- `0x18012546c`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800609bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800609bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180060f63`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180060fbe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180060f63`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180060fbe`

## string_xrefs

- `0x180060738`: `filePath `
- `0x180060754`: `arpUninstallKeyPath `
- `0x1800607f2`: `APPINFO2_CACHE_ONLY and APPINFO2_ALL_PE_FILES flags cannot be combined. [%#x]`
- `0x18006080b`: `APPINFO2_NO_FILES and APPINFO2_ALL_PE_FILES flags cannot be combined. [%#x]`

## pseudocode

```c
struct Windows::Compat::Inventory::AppInfo2 *__fastcall GetAppInfo2(
        const unsigned __int16 *a1,
        wchar_t *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        struct Windows::Compat::Inventory::AppInfo2 *a6)
{
  char *v10; // rbx
  const char *v11; // r9
  int v12; // r8d
  Application *v13; // rax
  const unsigned __int16 *v14; // rdx
  File *v15; // rax
  const unsigned __int16 *v16; // rdx
  __int64 v17; // r8
  const struct File *v18; // rsi
  struct File *v19; // r12
  _QWORD *v20; // rdx
  unsigned __int64 v21; // r14
  wchar_t **v22; // rsi
  int i; // eax
  __int64 v24; // r9
  _QWORD *v25; // rcx
  wchar_t *v26; // r8
  __int64 v27; // rdx
  const struct ConfigSettings *v28; // rdx
  __int64 v29; // rax
  unsigned int v30; // r9d
  ArpApplication *v31; // rax
  __int64 v32; // rax
  wchar_t **v33; // rdx
  __int64 ApplicationFromCache; // rsi
  __int64 v35; // rdi
  __int64 v36; // rax
  struct File **v37; // rdx
  __int64 v38; // rax
  struct File **v39; // rdx
  File *v40; // r15
  __int64 v41; // rsi
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  File *v46; // rsi
  __int64 v47; // rax
  unsigned int v48; // r9d
  ArpApplication *v49; // rax
  int v51; // [rsp+20h] [rbp-18A8h]
  Application *v52; // [rsp+A8h] [rbp-1820h] BYREF
  File *v53; // [rsp+B0h] [rbp-1818h]
  __int64 v54; // [rsp+B8h] [rbp-1810h] BYREF
  Application *AppInfo2; // [rsp+C0h] [rbp-1808h]
  __int64 v56; // [rsp+C8h] [rbp-1800h]
  struct File *v57[2]; // [rsp+1C0h] [rbp-1708h] BYREF
  __int64 v58; // [rsp+1D0h] [rbp-16F8h]
  unsigned __int64 v59; // [rsp+1D8h] [rbp-16F0h]
  wchar_t *String1[2]; // [rsp+1E0h] [rbp-16E8h] BYREF
  __int64 v61; // [rsp+1F0h] [rbp-16D8h]
  unsigned __int64 v62; // [rsp+1F8h] [rbp-16D0h]
  _BYTE v63[32]; // [rsp+200h] [rbp-16C8h] BYREF
  _BYTE v64[32]; // [rsp+220h] [rbp-16A8h] BYREF
  __int64 v65; // [rsp+240h] [rbp-1688h] BYREF
  _BYTE v66[80]; // [rsp+248h] [rbp-1680h] BYREF
  __int64 v67; // [rsp+298h] [rbp-1630h]
  __int16 v68; // [rsp+2A0h] [rbp-1628h]
  __int64 v69; // [rsp+2A8h] [rbp-1620h]
  __int128 v70; // [rsp+2B0h] [rbp-1618h]
  __int64 v71; // [rsp+2C0h] [rbp-1608h]
  int v72; // [rsp+2C8h] [rbp-1600h]
  char v73; // [rsp+2CCh] [rbp-15FCh]
  _BYTE v74[32]; // [rsp+2D0h] [rbp-15F8h] BYREF
  _BYTE v75[32]; // [rsp+2F0h] [rbp-15D8h] BYREF
  __int64 v76; // [rsp+310h] [rbp-15B8h] BYREF
  _BYTE v77[80]; // [rsp+318h] [rbp-15B0h] BYREF
  __int64 v78; // [rsp+368h] [rbp-1560h]
  __int16 v79; // [rsp+370h] [rbp-1558h]
  __int64 v80; // [rsp+378h] [rbp-1550h]
  __int128 v81; // [rsp+380h] [rbp-1548h]
  __int64 v82; // [rsp+390h] [rbp-1538h]
  int v83; // [rsp+398h] [rbp-1530h]
  char v84; // [rsp+39Ch] [rbp-152Ch]
  _BYTE v85[240]; // [rsp+3A0h] [rbp-1528h] BYREF
  _BYTE v86[56]; // [rsp+490h] [rbp-1438h] BYREF
  _QWORD v87[4]; // [rsp+4C8h] [rbp-1400h] BYREF
  _BYTE v88[32]; // [rsp+4E8h] [rbp-13E0h] BYREF
  _QWORD v89[39]; // [rsp+508h] [rbp-13C0h] BYREF
  _QWORD v90[584]; // [rsp+640h] [rbp-1288h] BYREF

  v56 = -2;
  v10 = 0;
  LODWORD(v54) = 0;
  memset_0(v77, 0, 0x4Eu);
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v78 = 0;
  v76 = 0;
  memset_0(v66, 0, 0x4Eu);
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v67 = 0;
  v65 = 0;
  LODWORD(v52) = a5 & 2;
  std::wstring::wstring(v63, &byte_1801389F0);
  std::wstring::wstring(v64, &byte_1801389F0);
  std::wstring::wstring(v75, &byte_1801389F0);
  std::wstring::wstring(v74, &byte_1801389F0);
  std::wstring::wstring(v57, &byte_1801389F0);
  ConfigSettings::ConfigSettings(
    (unsigned int)v85,
    (_DWORD)v52 != 0 ? 2 : 0,
    (unsigned int)&v65,
    (unsigned int)&v76,
    0,
    0,
    3,
    (__int64)v57,
    (__int64)v74,
    (__int64)v75,
    (__int64)v64,
    (__int64)v63,
    0);
  std::wstring::~wstring(v57);
  std::wstring::~wstring(v74);
  std::wstring::~wstring(v75);
  std::wstring::~wstring(v64);
  std::wstring::~wstring(v63);
  if ( a1 && (a2 || a3 || a4 || a6) || a2 && (a3 || a4 || a6) || a3 && (a4 || a6) || a4 && a6 )
  {
    AslLogCallPrintf(1, (unsigned int)"GetAppInfo2", 1310, (unsigned int)"Too many arguments: %hs%hs%hs%hs%hs[%#x]");
    goto LABEL_125;
  }
  if ( (a5 & 0xFFFFFFF0) != 0 )
  {
    v11 = "Invalid flag detected. [%#x]";
    v12 = 1316;
LABEL_18:
    AslLogCallPrintf(1, (unsigned int)"GetAppInfo2", v12, (_DWORD)v11);
    goto LABEL_125;
  }
  if ( (a5 & 3) == 3 )
  {
    v11 = "APPINFO2_CACHE_ONLY and APPINFO2_ALL_PE_FILES flags cannot be combined. [%#x]";
    v12 = 1323;
    goto LABEL_18;
  }
  if ( (a5 & 6) == 6 )
  {
    v11 = "APPINFO2_NO_FILES and APPINFO2_ALL_PE_FILES flags cannot be combined. [%#x]";
    v12 = 1330;
    goto LABEL_18;
  }
  if ( a6 )
  {
    if ( a6 != (struct Windows::Compat::Inventory::AppInfo2 *)8 )
      (**((void (__fastcall ***)(char *, __int64))a6 - 1))((char *)a6 - 8, 1);
    goto LABEL_125;
  }
  AppInfo2 = (Application *)operator new(0x3F0u);
  v13 = Application::Application(AppInfo2);
  v14 = (const unsigned __int16 *)&Application::ApplicationCacheProviderName;
  if ( (unsigned __int64)qword_180182A38 > 7 )
    v14 = (const unsigned __int16 *)Application::ApplicationCacheProviderName;
  if ( (int)TelCacheProvider::Initialize(&v65, v14, (__int64)v13, 0, 3, 0, 0) >= 0 )
  {
    AppInfo2 = 0;
    v53 = (File *)operator new(0x330u);
    v15 = File::File(v53);
    v16 = (const unsigned __int16 *)&File::FileCacheProviderName;
    if ( (unsigned __int64)qword_180183038 > 7 )
      v16 = (const unsigned __int16 *)File::FileCacheProviderName;
    if ( (int)TelCacheProvider::Initialize(&v76, v16, ((unsigned __int64)v15 + 8) & -(__int64)(v15 != 0), 0, 3, 0, 0) >= 0 )
    {
      Application::ForceFullAppScan = (a5 & 2) != 0;
      std::wstring::wstring(String1);
      if ( a1 && *a1 )
      {
        v17 = -1;
        do
          ++v17;
        while ( a1[v17] );
        std::wstring::_Assign<unsigned short>(String1, a1);
      }
      if ( a3 && *a3 )
      {
        File::GetFilesFromCache(v57, v85);
        v18 = v57[0];
        v19 = v57[1];
        while ( v18 != v19 )
        {
          File::File((File *)v86, v18);
          v20 = v89;
          if ( v89[3] > 7u )
            v20 = (_QWORD *)v89[0];
          if ( !(unsigned int)_o__wcsicmp(a3, v20) )
          {
            std::wstring::operator=(String1, v88);
            File::~File((File *)v86);
            break;
          }
          File::~File((File *)v86);
          v18 = (const struct File *)((char *)v18 + 816);
        }
        std::vector<File>::_Tidy(v57);
      }
      if ( a4 && *a4 )
      {
        std::wstring::wstring(v63, a4);
        File::File((File *)v86, (struct ConfigSettings *)v85);
        std::wstring::~wstring(v63);
        std::wstring::operator=(String1, v88);
        File::~File((File *)v86);
      }
      if ( !v61 && (!a2 || !*a2) )
      {
        AslLogCallPrintf(3, (unsigned int)"GetAppInfo2", 1383, (unsigned int)"Unable to find requested app.");
        std::wstring::~wstring(String1);
        goto LABEL_125;
      }
      if ( !(unsigned int)std::wstring::compare(String1, L"0000f519feec486de87ed73cb92d3cac802400000000") )
      {
        AslLogCallPrintf(3, (unsigned int)"GetAppInfo2", 1389, (unsigned int)"System Program ID, no corresponding app.");
        std::wstring::~wstring(String1);
        goto LABEL_125;
      }
      v21 = v62;
      if ( v61 )
      {
        if ( v62 <= 7 )
        {
          v22 = String1;
        }
        else
        {
          v22 = (wchar_t **)String1[0];
          if ( !String1[0] )
          {
LABEL_65:
            AslLogCallPrintf(
              3,
              (unsigned int)"GetAppInfo2",
              1395,
              (unsigned int)"Orphan Program ID, no corresponding app.");
            std::wstring::~wstring(String1);
            goto LABEL_125;
          }
        }
        if ( !*(_WORD *)v22
          || !wcscmp_0((const wchar_t *)v22, L"0000da39a3ee5e6b4b0d3255bfef95601890afd80709")
          || *((_WORD *)v22 + 3) == 51
          || *((_WORD *)v22 + 3) == 54 )
        {
          goto LABEL_65;
        }
      }
      if ( !(_DWORD)v52 )
      {
        Application::Application((Application *)v86);
        for ( i = TelCacheProvider::GetFirstItem((TelCacheProvider *)&v65, (struct IAmiInventoryItem *)v86);
              ;
              i = TelCacheProvider::GetNextItem((TelCacheProvider *)&v65, (struct IAmiInventoryItem *)v86) )
        {
          if ( i < 0 )
            goto LABEL_86;
          v24 = v61;
          if ( v61 )
          {
            v26 = (wchar_t *)String1;
            if ( v62 > 7 )
              v26 = String1[0];
            v25 = v87;
            if ( v87[3] > 7u )
              v25 = (_QWORD *)v87[0];
            v27 = v87[2];
          }
          else
          {
            v24 = -1;
            do
              ++v24;
            while ( a2[v24] );
            v25 = v90;
            if ( v90[3] > 7u )
              v25 = (_QWORD *)v90[0];
            v26 = a2;
            v27 = v90[2];
          }
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v25, v27, v26, v24, v51) )
            break;
        }
        if ( !Application::IsValid((Application *)v86, v28) )
        {
LABEL_86:
          AslLogCallPrintf(1, (unsigned int)"GetAppInfo2", 1428, (unsigned int)"Unable to find requested app. [%#x]");
          Application::~Application((Application *)v86);
          std::wstring::~wstring(String1);
          goto LABEL_125;
        }
        if ( (a5 & 4) == 0 )
        {
          v29 = std::wstring::wstring(v63, v87);
          File::GetFilesFromCache(v57, v85, v29);
          Application::SetFiles((Application *)v86);
        }
        AppInfo2 = Application::CreateAppInfo2((Application *)v86);
        Application::~Application((Application *)v86);
        goto LABEL_123;
      }
      v52 = 0;
      if ( !v61 )
      {
        if ( !a2 || !*a2 )
        {
LABEL_122:
          wistd::unique_ptr<Application,wistd::default_delete<Application>>::reset(&v52, 0);
LABEL_123:
          std::wstring::~wstring(String1);
          if ( AppInfo2 )
            v10 = (char *)AppInfo2 + 8;
          goto LABEL_125;
        }
        std::wstring::wstring(v63, a2);
        MsiApplication::GetMsiProductCode(v57, v63);
        std::wstring::~wstring(v63);
        if ( v58 )
        {
          v53 = (File *)operator new(0x410u);
          std::wstring::wstring(v64, a2);
          LODWORD(v54) = v54 | 1;
          v32 = MsiApplication::MsiApplication(v53);
          wistd::unique_ptr<Application,wistd::default_delete<Application>>::reset(&v52, v32);
          std::wstring::~wstring(v64);
        }
        else
        {
          v53 = (File *)operator new(0x3F0u);
          v31 = ArpApplication::ArpApplication(v53, (const struct ConfigSettings *)v85, a2, v30);
          wistd::unique_ptr<Application,wistd::default_delete<Application>>::reset(&v52, v31);
        }
        std::wstring::~wstring(v57);
LABEL_120:
        if ( v52 )
          AppInfo2 = Application::CreateAppInfo2(v52);
        goto LABEL_122;
      }
      v33 = String1;
      if ( v21 > 7 )
        v33 = (wchar_t **)String1[0];
      std::wstring::wstring(v63, v33);
      ApplicationFromCache = Application::GetApplicationFromCache(v63);
      v54 = ApplicationFromCache;
      std::wstring::~wstring(v63);
      if ( !ApplicationFromCache )
      {
        AslLogCallPrintf(1, (unsigned int)"GetAppInfo2", 1453, (unsigned int)"Unable to find requested app. [%#x]");
        wistd::unique_ptr<Application,wistd::default_delete<Application>>::reset(&v54, 0);
        wistd::unique_ptr<Application,wistd::default_delete<Application>>::reset(&v52, 0);
        std::wstring::~wstring(String1);
        goto LABEL_125;
      }
      v35 = ApplicationFromCache + 16;
      v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(ApplicationFromCache + 16) + 64LL))(ApplicationFromCache + 16);
      if ( (unsigned int)std::wstring::compare(v36, &Application::ApplicationSourceMsi) )
      {
        v43 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 64LL))(ApplicationFromCache + 16);
        if ( (unsigned int)std::wstring::compare(v43, &Application::ApplicationSourceAddRemoveProgram)
          && (v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 64LL))(ApplicationFromCache + 16),
              (unsigned int)std::wstring::compare(v44, &Application::ApplicationSourceAddRemoveProgramPerUser))
          && (v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 64LL))(ApplicationFromCache + 16),
              (unsigned int)std::wstring::compare(v45, Application::ApplicationSourceClickOnce)) )
        {
          (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 64LL))(ApplicationFromCache + 16);
          AslLogCallPrintf(1, (unsigned int)"GetAppInfo2", 1484, (unsigned int)"App is an unsupported source: %ls");
        }
        else
        {
          v46 = (File *)operator new(0x3F0u);
          v53 = v46;
          v47 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 88LL))(v35);
          if ( *(_QWORD *)(v47 + 24) > 7u )
            v47 = *(_QWORD *)v47;
          v49 = ArpApplication::ArpApplication(
                  v46,
                  (const struct ConfigSettings *)v85,
                  (const unsigned __int16 *)v47,
                  v48);
          wistd::unique_ptr<Application,wistd::default_delete<Application>>::reset(&v52, v49);
        }
        goto LABEL_119;
      }
      std::wstring::wstring(v57, ApplicationFromCache + 432);
      v37 = v57;
      if ( v59 > 7 )
        v37 = (struct File **)v57[0];
      if ( (unsigned int)_o__wcsnicmp(L"HKEY_LOCAL_MACHINE", v37, 18) )
      {
        v39 = v57;
        if ( v59 > 7 )
          v39 = (struct File **)v57[0];
        if ( (unsigned int)_o__wcsnicmp(L"HKEY_USERS", v39, 10) )
          goto LABEL_108;
        v38 = std::wstring::substr(v57, v63, 11, v58);
      }
      else
      {
        v38 = std::wstring::substr(v57, v63, 19, v58);
      }
      std::wstring::operator=(v57, v38);
      std::wstring::~wstring(v63);
LABEL_108:
      v40 = (File *)operator new(0x410u);
      v53 = v40;
      if ( *(_QWORD *)(ApplicationFromCache + 296) )
        v41 = **(_QWORD **)(ApplicationFromCache + 288) + 32LL;
      else
        v41 = ApplicationFromCache + 304;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 96LL))(v35);
      v42 = MsiApplication::MsiApplication(v40, (__int64)v57, v41);
      wistd::unique_ptr<Application,wistd::default_delete<Application>>::reset(&v52, v42);
      std::wstring::~wstring(v57);
LABEL_119:
      wistd::unique_ptr<Application,wistd::default_delete<Application>>::reset(&v54, 0);
      goto LABEL_120;
    }
  }
LABEL_125:
  ConfigSettings::~ConfigSettings((ConfigSettings *)v85);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v65);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v76);
  return (struct Windows::Compat::Inventory::AppInfo2 *)v10;
}

```

## disassembly

```asm
0x180060460  push    rbx
0x180060462  push    rsi
0x180060463  push    rdi
0x180060464  push    r12
0x180060466  push    r13
0x180060468  push    r14
0x18006046a  push    r15
0x18006046c  mov     eax, 1890h
0x180060471  call    _alloca_probe
0x180060476  sub     rsp, rax
0x180060479  mov     [rsp+18C8h+var_1800], 0FFFFFFFFFFFFFFFEh
0x180060485  mov     rax, cs:__security_cookie
0x18006048c  xor     rax, rsp
0x18006048f  mov     [rsp+18C8h+var_48], rax
0x180060497  mov     r14, r9
0x18006049a  mov     r15, r8
0x18006049d  mov     rdi, rdx
0x1800604a0  mov     r12, rcx
0x1800604a3  mov     rsi, [rsp+18C8h+arg_28]
0x1800604ab  xor     ebx, ebx
0x1800604ad  mov     dword ptr [rsp+18C8h+var_1810], ebx
0x1800604b4  lea     r13d, [rbx+4Eh]
0x1800604b8  mov     r8d, r13d; Size
0x1800604bb  xor     edx, edx; Val
0x1800604bd  lea     rcx, [rsp+18C8h+var_15B0]; void *
0x1800604c5  call    memset_0
0x1800604ca  mov     [rsp+18C8h+var_1558], bx
0x1800604d2  mov     [rsp+18C8h+var_1550], rbx
0x1800604da  xorps   xmm0, xmm0
0x1800604dd  movdqa  [rsp+18C8h+var_1548], xmm0
0x1800604e6  mov     [rsp+18C8h+var_1538], rbx
0x1800604ee  mov     [rsp+18C8h+var_1530], ebx
0x1800604f5  mov     [rsp+18C8h+var_152C], bl
0x1800604fc  mov     [rsp+18C8h+var_1560], rbx
0x180060504  mov     [rsp+18C8h+var_15B8], rbx
0x18006050c  mov     r8d, r13d; Size
0x18006050f  xor     edx, edx; Val
0x180060511  lea     rcx, [rsp+18C8h+var_1680]; void *
0x180060519  call    memset_0
0x18006051e  mov     [rsp+18C8h+var_1628], bx
0x180060526  mov     [rsp+18C8h+var_1620], rbx
0x18006052e  xorps   xmm0, xmm0
0x180060531  movdqa  [rsp+18C8h+var_1618], xmm0
0x18006053a  mov     [rsp+18C8h+var_1608], rbx
0x180060542  mov     [rsp+18C8h+var_1600], ebx
0x180060549  mov     [rsp+18C8h+var_15FC], bl
0x180060550  mov     [rsp+18C8h+var_1630], rbx
0x180060558  mov     [rsp+18C8h+var_1688], rbx
0x180060560  mov     r13d, [rsp+18C8h+arg_20]
0x180060568  mov     eax, r13d
0x18006056b  and     eax, 2
0x18006056e  mov     dword ptr [rsp+18C8h+var_1820], eax
0x180060575  setnz   [rsp+18C8h+var_1828]
0x18006057d  lea     rdx, byte_1801389F0
0x180060584  lea     rcx, [rsp+18C8h+var_16C8]
0x18006058c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180060591  nop
0x180060592  lea     rdx, byte_1801389F0
0x180060599  lea     rcx, [rsp+18C8h+var_16A8]
0x1800605a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800605a6  nop
0x1800605a7  lea     rdx, byte_1801389F0
0x1800605ae  lea     rcx, [rsp+18C8h+var_15D8]
0x1800605b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800605bb  nop
0x1800605bc  lea     rdx, byte_1801389F0
0x1800605c3  lea     rcx, [rsp+18C8h+var_15F8]
0x1800605cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800605d0  nop
0x1800605d1  lea     rdx, byte_1801389F0
0x1800605d8  lea     rcx, [rsp+18C8h+var_1708]
0x1800605e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800605e5  nop
0x1800605e6  mov     eax, dword ptr [rsp+18C8h+var_1820]
0x1800605ed  neg     eax
0x1800605ef  sbb     edx, edx
0x1800605f1  and     edx, 2
0x1800605f4  mov     [rsp+18C8h+var_1830], bl
0x1800605fb  mov     [rsp+18C8h+var_1838], 1
0x180060603  mov     [rsp+18C8h+var_1848], bl
0x18006060a  mov     [rsp+18C8h+var_1850], bl
0x18006060e  mov     [rsp+18C8h+var_1858], 1
0x180060613  mov     [rsp+18C8h+var_1868], bl
0x180060617  lea     rax, [rsp+18C8h+var_16C8]
0x18006061f  mov     [rsp+18C8h+var_1870], rax
0x180060624  lea     rax, [rsp+18C8h+var_16A8]
0x18006062c  mov     [rsp+18C8h+var_1878], rax
0x180060631  lea     rax, [rsp+18C8h+var_15D8]
0x180060639  mov     [rsp+18C8h+var_1880], rax
0x18006063e  lea     rax, [rsp+18C8h+var_15F8]
0x180060646  mov     [rsp+18C8h+var_1888], rax
0x18006064b  lea     rax, [rsp+18C8h+var_1708]
0x180060653  mov     [rsp+18C8h+var_1890], rax
0x180060658  mov     dword ptr [rsp+18C8h+var_1898], 3
0x180060660  mov     byte ptr [rsp+18C8h+var_18A0], bl
0x180060664  mov     byte ptr [rsp+18C8h+var_18A8], bl
0x180060668  lea     r9, [rsp+18C8h+var_15B8]
0x180060670  lea     r8, [rsp+18C8h+var_1688]
0x180060678  lea     rcx, [rsp+18C8h+var_1528]
0x180060680  call    ??0ConfigSettings@@QEAA@W4FileInventoryMode@@PEAVTelCacheProvider@@1_N2W4StoreAppEnumType@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@4444_N5555555@Z; ConfigSettings::ConfigSettings(FileInventoryMode,TelCacheProvider *,TelCacheProvider *,bool,bool,StoreAppEnumType,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,bool,bool,bool,bool,bool,bool)
0x180060685  nop
0x180060686  lea     rcx, [rsp+18C8h+var_1708]
0x18006068e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060693  nop
0x180060694  lea     rcx, [rsp+18C8h+var_15F8]
0x18006069c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800606a1  nop
0x1800606a2  lea     rcx, [rsp+18C8h+var_15D8]
0x1800606aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800606af  nop
0x1800606b0  lea     rcx, [rsp+18C8h+var_16A8]
0x1800606b8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800606bd  nop
0x1800606be  lea     rcx, [rsp+18C8h+var_16C8]
0x1800606c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800606cb  test    r12, r12
0x1800606ce  jz      short loc_1800606E4
0x1800606d0  test    rdi, rdi
0x1800606d3  jnz     short loc_180060719
0x1800606d5  test    r15, r15
0x1800606d8  jnz     short loc_180060719
0x1800606da  test    r14, r14
0x1800606dd  jnz     short loc_180060719
0x1800606df  test    rsi, rsi
0x1800606e2  jnz     short loc_18006071E
0x1800606e4  test    rdi, rdi
0x1800606e7  jz      short loc_1800606F8
0x1800606e9  test    r15, r15
0x1800606ec  jnz     short loc_180060719
0x1800606ee  test    r14, r14
0x1800606f1  jnz     short loc_180060719
0x1800606f3  test    rsi, rsi
0x1800606f6  jnz     short loc_18006071E
0x1800606f8  test    r15, r15
0x1800606fb  jz      short loc_180060707
0x1800606fd  test    r14, r14
0x180060700  jnz     short loc_180060719
0x180060702  test    rsi, rsi
0x180060705  jnz     short loc_18006071E
0x180060707  test    r14, r14
0x18006070a  jz      loc_1800607B4
0x180060710  test    rsi, rsi
0x180060713  jz      loc_1800607B4
0x180060719  test    rsi, rsi
0x18006071c  jz      short loc_18006072E
0x18006071e  lea     r10, aAppinfo2tofree; "appInfo2ToFree "
0x180060725  lea     rcx, dword_18013AE3C
0x18006072c  jmp     short loc_180060738
0x18006072e  lea     rcx, dword_18013AE3C
0x180060735  mov     r10, rcx
0x180060738  lea     r9, aFilepath; "filePath "
0x18006073f  test    r14, r14
0x180060742  cmovz   r9, rcx
0x180060746  lea     r8, aFileid; "fileId "
0x18006074d  test    r15, r15
0x180060750  cmovz   r8, rcx
0x180060754  lea     rdx, aArpuninstallke; "arpUninstallKeyPath "
0x18006075b  test    rdi, rdi
0x18006075e  cmovz   rdx, rcx
0x180060762  lea     rax, aProgramid_0; "programId "
0x180060769  test    r12, r12
0x18006076c  cmovz   rax, rcx
0x180060770  mov     dword ptr [rsp+18C8h+var_1880], 80070057h
0x180060778  mov     [rsp+18C8h+var_1888], r10
0x18006077d  mov     [rsp+18C8h+var_1890], r9
0x180060782  mov     [rsp+18C8h+var_1898], r8
0x180060787  mov     [rsp+18C8h+var_18A0], rdx
0x18006078c  mov     [rsp+18C8h+var_18A8], rax
0x180060791  lea     r9, aTooManyArgumen; "Too many arguments: %hs%hs%hs%hs%hs[%#x"...
0x180060798  mov     r8d, 51Eh
0x18006079e  lea     rdx, aGetappinfo2_0; "GetAppInfo2"
0x1800607a5  mov     ecx, 1
0x1800607aa  call    AslLogCallPrintf
0x1800607af  jmp     loc_1800611F4
0x1800607b4  test    r13d, 0FFFFFFF0h
0x1800607bb  jz      short loc_1800607E8
0x1800607bd  lea     r9, aInvalidFlagDet; "Invalid flag detected. [%#x]"
0x1800607c4  mov     r8d, 524h
0x1800607ca  mov     dword ptr [rsp+18C8h+var_18A8], 80070057h
0x1800607d2  lea     rdx, aGetappinfo2_0; "GetAppInfo2"
0x1800607d9  mov     ecx, 1
0x1800607de  call    AslLogCallPrintf
0x1800607e3  jmp     loc_1800611F4
0x1800607e8  mov     eax, r13d
0x1800607eb  and     eax, 3
0x1800607ee  cmp     al, 3
0x1800607f0  jnz     short loc_180060801
0x1800607f2  lea     r9, aAppinfo2CacheO; "APPINFO2_CACHE_ONLY and APPINFO2_ALL_PE"...
0x1800607f9  mov     r8d, 52Bh
0x1800607ff  jmp     short loc_1800607CA
0x180060801  mov     eax, r13d
0x180060804  and     eax, 6
0x180060807  cmp     al, 6
0x180060809  jnz     short loc_18006081A
0x18006080b  lea     r9, aAppinfo2NoFile; "APPINFO2_NO_FILES and APPINFO2_ALL_PE_F"...
0x180060812  mov     r8d, 532h
0x180060818  jmp     short loc_1800607CA
0x18006081a  test    rsi, rsi
0x18006081d  jz      short loc_180060841
0x18006081f  lea     rcx, [rsi-8]
0x180060823  test    rcx, rcx
0x180060826  jz      loc_1800611F4
0x18006082c  mov     rax, [rcx]
0x18006082f  mov     edx, 1
0x180060834  mov     rax, [rax]
0x180060837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006083c  jmp     loc_1800611F4
0x180060841  mov     ecx, 3F0h; Size
0x180060846  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006084b  mov     [rsp+18C8h+var_1808], rax
0x180060853  mov     rcx, rax; this
0x180060856  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x18006085b  nop
0x18006085c  lea     rdx, ?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x180060863  cmp     cs:qword_180182A38, 7
0x18006086b  cmova   rdx, cs:?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x180060873  mov     dword ptr [rsp+18C8h+var_1898], ebx
0x180060877  mov     dword ptr [rsp+18C8h+var_18A0], ebx
0x18006087b  mov     esi, 3
0x180060880  mov     dword ptr [rsp+18C8h+var_18A8], esi
0x180060884  xor     r9d, r9d
0x180060887  mov     r8, rax
0x18006088a  lea     rcx, [rsp+18C8h+var_1688]
0x180060892  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180060897  test    eax, eax
0x180060899  js      loc_1800611F4
0x18006089f  mov     [rsp+18C8h+var_1808], rbx
0x1800608a7  and     r13d, 4
0x1800608ab  mov     ecx, 330h; Size
0x1800608b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800608b5  mov     [rsp+18C8h+var_1818], rax
0x1800608bd  mov     rcx, rax; this
0x1800608c0  call    ??0File@@QEAA@XZ; File::File(void)
0x1800608c5  nop
0x1800608c6  lea     rcx, [rax+8]
0x1800608ca  neg     rax
0x1800608cd  sbb     r8, r8
0x1800608d0  and     r8, rcx
0x1800608d3  lea     rdx, ?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x1800608da  cmp     cs:qword_180183038, 7
0x1800608e2  cmova   rdx, cs:?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x1800608ea  mov     dword ptr [rsp+18C8h+var_1898], ebx
0x1800608ee  mov     dword ptr [rsp+18C8h+var_18A0], ebx
0x1800608f2  mov     dword ptr [rsp+18C8h+var_18A8], esi
0x1800608f6  xor     r9d, r9d
0x1800608f9  lea     rcx, [rsp+18C8h+var_15B8]
0x180060901  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180060906  test    eax, eax
0x180060908  js      loc_1800611F4
0x18006090e  mov     al, [rsp+18C8h+var_1828]
0x180060915  mov     cs:?ForceFullAppScan@Application@@1_NA, al; bool Application::ForceFullAppScan
0x18006091b  lea     rcx, [rsp+18C8h+String1]
0x180060923  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180060928  nop
0x180060929  test    r12, r12
0x18006092c  jz      short loc_180060953
0x18006092e  cmp     [r12], bx
0x180060933  jz      short loc_180060953
0x180060935  or      r8, 0FFFFFFFFFFFFFFFFh
0x180060939  inc     r8
0x18006093c  cmp     [r12+r8*2], bx
0x180060941  jnz     short loc_180060939
0x180060943  mov     rdx, r12
0x180060946  lea     rcx, [rsp+18C8h+String1]
0x18006094e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180060953  test    r15, r15
0x180060956  jz      loc_180060A03
0x18006095c  cmp     [r15], bx
0x180060960  jz      loc_180060A03
0x180060966  lea     rdx, [rsp+18C8h+var_1528]
0x18006096e  lea     rcx, [rsp+18C8h+var_1708]
0x180060976  call    ?GetFilesFromCache@File@@SA?AV?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEBVConfigSettings@@@Z; File::GetFilesFromCache(ConfigSettings const &)
0x18006097b  nop
0x18006097c  mov     rsi, [rsp+18C8h+var_1708]
0x180060984  mov     r12, [rsp+18C8h+var_1700]
0x18006098c  cmp     rsi, r12
0x18006098f  jz      short loc_1800609F1
0x180060991  mov     rdx, rsi; struct File *
0x180060994  lea     rcx, [rsp+18C8h+var_1438]; this
0x18006099c  call    ??0File@@QEAA@AEBV0@@Z; File::File(File const &)
0x1800609a1  nop
0x1800609a2  lea     rdx, [rsp+18C8h+var_13C0]
0x1800609aa  cmp     [rsp+18C8h+var_13A8], 7
0x1800609b3  cmova   rdx, [rsp+18C8h+var_13C0]
0x1800609bc  mov     rcx, r15
0x1800609bf  call    cs:__imp__o__wcsicmp
0x1800609c5  test    eax, eax
0x1800609c7  jnz     loc_180060B22
0x1800609cd  lea     rdx, [rsp+18C8h+var_13E0]
0x1800609d5  lea     rcx, [rsp+18C8h+String1]
0x1800609dd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800609e2  nop
0x1800609e3  lea     rcx, [rsp+18C8h+var_1438]; this
0x1800609eb  call    ??1File@@UEAA@XZ; File::~File(void)
0x1800609f0  nop
0x1800609f1  lea     rcx, [rsp+18C8h+var_1708]
0x1800609f9  call    ?_Tidy@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAXXZ; std::vector<File>::_Tidy(void)
0x1800609fe  mov     esi, 3
0x180060a03  test    r14, r14
0x180060a06  jz      short loc_180060A6D
  ... truncated ...
```
