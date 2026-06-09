# CreateSoftwareInventory(ulong,ushort * *,ushort * *)

- ea: `0x180045740`
- end: `0x1800461bb`
- name: `?CreateSoftwareInventory@@YAJKPEAPEAG0@Z`
- size: `2683`
- prototype: `__int64 __fastcall(int, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `40`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180043cc0`
- `0x1800455e0`
- `0x180066e80`

## callees

- `0x180008e58`
- `0x18000e458`
- `0x18000fb00`
- `0x18000fb70`
- `0x18000fbf4`
- `0x180016510`
- `0x180018a60`
- `0x1800197d4`
- `0x18001dbb4`
- `0x180026d38`
- `0x1800289d0`
- `0x18002bdfc`
- `0x18002d3b8`
- `0x18002d5d0`
- `0x18002d624`
- `0x18002debc`
- `0x18002ee80`
- `0x1800404c4`
- `0x1800417a8`
- `0x180045740`
- `0x1800482d0`
- `0x18004dc14`
- `0x18005198c`
- `0x180051bc0`
- `0x180052dc0`
- `0x180054c14`
- `0x1800582ac`
- `0x180059920`
- `0x18005a0ac`
- `0x18005a8bc`
- `0x18005e100`
- `0x18005f210`
- `0x180064288`
- `0x180067c64`
- `0x1800f863c`
- `0x1800ffa78`
- `0x18010273c`
- `0x1801093a0`
- `0x180125400`
- `0x180130010`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x1800460b3`
- `ntdll!EtwEventWriteNoRegistration` at `0x1800460b3`
- `KERNEL32!GetTickCount` at `0x1800457a0`
- `KERNEL32!GetTickCount` at `0x1800460dd`
- `KERNEL32!GetTickCount` at `0x1800457a0`
- `KERNEL32!GetTickCount` at `0x1800460dd`
- `OLEAUT32!__imp_VariantClear` at `0x180046065`
- `OLEAUT32!__imp_VariantClear` at `0x180046065`

## string_xrefs

- `0x180045801`: `CreateSoftwareInventory`
- `0x180045858`: `CreateSoftwareInventory`
- `0x1800458aa`: `CreateSoftwareInventory`
- `0x180045989`: `CreateSoftwareInventory`
- `0x180045a97`: `CreateSoftwareInventory`
- `0x180045ba9`: `CreateSoftwareInventory`
- `0x180045cc2`: `CreateSoftwareInventory`
- `0x1800460ce`: `CreateSoftwareInventory`
- `0x1800460fb`: `CreateSoftwareInventory`
- `0x18004589d`: `Unexpected flag(s) passed to CreateSoftwareInventory %d`
- `0x1800460ee`: `CreateSoftwareInventory elapsed time: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateSoftwareInventory(int a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  unsigned int v4; // edx
  struct THUNKS *v5; // rcx
  unsigned __int16 v6; // r8
  unsigned int v7; // edx
  int v8; // ebx
  int v10; // ebx
  Application *v11; // rax
  __int64 *v12; // rdx
  int v13; // ebx
  File *v14; // rax
  __int64 *v15; // rdx
  int v16; // ebx
  AmiFrameworkItem *v17; // rax
  __int64 *v18; // rdx
  int v19; // ebx
  AmiShortcutItem *v20; // rax
  AmiShortcutItem *v21; // rax
  __int64 *v22; // rdx
  int v23; // ebx
  int v24; // r14d
  __int64 *v25; // r12
  __int64 *v26; // rbx
  int v27; // ebx
  unsigned int v28; // ebx
  unsigned __int16 **v29; // rdi
  _bstr_t *v30; // rax
  unsigned int v31; // ebx
  __int64 v32; // rax
  int v33; // [rsp+A0h] [rbp-13E8h] BYREF
  int v34; // [rsp+A4h] [rbp-13E4h] BYREF
  unsigned int v35; // [rsp+A8h] [rbp-13E0h]
  _BYTE v36[4]; // [rsp+ACh] [rbp-13DCh] BYREF
  File *v37; // [rsp+B0h] [rbp-13D8h]
  void **v38; // [rsp+B8h] [rbp-13D0h] BYREF
  DWORD TickCount; // [rsp+C0h] [rbp-13C8h]
  unsigned __int16 **v40; // [rsp+C8h] [rbp-13C0h] BYREF
  _BYTE v41[24]; // [rsp+D0h] [rbp-13B8h] BYREF
  void **v42; // [rsp+E8h] [rbp-13A0h]
  __int64 v43; // [rsp+F0h] [rbp-1398h]
  VARIANTARG pvarg; // [rsp+1E0h] [rbp-12A8h] BYREF
  __int64 v45; // [rsp+200h] [rbp-1288h] BYREF
  _BYTE v46[80]; // [rsp+208h] [rbp-1280h] BYREF
  __int64 v47; // [rsp+258h] [rbp-1230h]
  __int16 v48; // [rsp+260h] [rbp-1228h]
  __int64 v49; // [rsp+268h] [rbp-1220h] BYREF
  __int128 v50; // [rsp+270h] [rbp-1218h]
  __int64 v51; // [rsp+280h] [rbp-1208h]
  int v52; // [rsp+288h] [rbp-1200h]
  char v53; // [rsp+28Ch] [rbp-11FCh]
  __int64 v54; // [rsp+290h] [rbp-11F8h] BYREF
  _BYTE v55[80]; // [rsp+298h] [rbp-11F0h] BYREF
  __int64 v56; // [rsp+2E8h] [rbp-11A0h]
  __int16 v57; // [rsp+2F0h] [rbp-1198h]
  __int64 v58; // [rsp+2F8h] [rbp-1190h]
  __int128 v59; // [rsp+300h] [rbp-1188h]
  __int64 v60; // [rsp+310h] [rbp-1178h]
  int v61; // [rsp+318h] [rbp-1170h]
  char v62; // [rsp+31Ch] [rbp-116Ch]
  __int64 v63; // [rsp+330h] [rbp-1158h] BYREF
  _BYTE v64[80]; // [rsp+338h] [rbp-1150h] BYREF
  __int64 v65; // [rsp+388h] [rbp-1100h]
  __int16 v66; // [rsp+390h] [rbp-10F8h]
  __int64 v67; // [rsp+398h] [rbp-10F0h]
  __int128 v68; // [rsp+3A0h] [rbp-10E8h]
  __int64 v69; // [rsp+3B0h] [rbp-10D8h]
  int v70; // [rsp+3B8h] [rbp-10D0h]
  char v71; // [rsp+3BCh] [rbp-10CCh]
  __int64 v72; // [rsp+3C0h] [rbp-10C8h] BYREF
  _BYTE v73[80]; // [rsp+3C8h] [rbp-10C0h] BYREF
  __int64 v74; // [rsp+418h] [rbp-1070h]
  __int16 v75; // [rsp+420h] [rbp-1068h]
  __int64 v76; // [rsp+428h] [rbp-1060h]
  __int128 v77; // [rsp+430h] [rbp-1058h]
  __int64 v78; // [rsp+440h] [rbp-1048h]
  int v79; // [rsp+448h] [rbp-1040h]
  char v80; // [rsp+44Ch] [rbp-103Ch]
  _BYTE v81[32]; // [rsp+450h] [rbp-1038h] BYREF
  __int64 *v82; // [rsp+470h] [rbp-1018h]
  __int64 *v83; // [rsp+478h] [rbp-1010h]

  v43 = -2;
  v40 = a3;
  v35 = 0;
  Utility::InitializeWatchdogTimer();
  TickCount = GetTickCount();
  DownlevelThunksInitEx(v5, v4);
  v34 = -2147221008;
  v33 = -2147221008;
  if ( IsWindowsVersionOrGreater(6u, 2u, v6) )
  {
    v8 = Common::AutoWinRTInitialize::Initialize(&v33);
    if ( v8 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"CreateSoftwareInventory", 662, (unsigned int)"[%#x]");
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v33);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v34);
      return (unsigned int)v8;
    }
  }
  else
  {
    v10 = Common::AutoCoInitialize::Initialize((Common::AutoCoInitialize *)&v34, v7);
    if ( v10 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"CreateSoftwareInventory", 666, (unsigned int)"[%#x]");
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v33);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v34);
      return (unsigned int)v10;
    }
  }
  if ( (a1 & 0x3727C8FC) != 0 )
    AslLogCallPrintf(
      1,
      (unsigned int)"CreateSoftwareInventory",
      671,
      (unsigned int)"Unexpected flag(s) passed to CreateSoftwareInventory %d");
  memset_0(v46, 0, 0x4Eu);
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v47 = 0;
  v45 = 0;
  v37 = (File *)operator new(0x3F0u);
  v11 = Application::Application(v37);
  v12 = &Application::ApplicationCacheProviderName;
  if ( (unsigned __int64)qword_180182A38 > 7 )
    v12 = (__int64 *)Application::ApplicationCacheProviderName;
  v13 = TelCacheProvider::Initialize(&v45, v12, v11, 0, 2, 5, 500);
  if ( v13 >= 0 )
  {
    memset_0(v64, 0, 0x4Eu);
    v66 = 0;
    v67 = 0;
    v68 = 0;
    v69 = 0;
    v70 = 0;
    v71 = 0;
    v65 = 0;
    v63 = 0;
    v37 = (File *)operator new(0x330u);
    v14 = File::File(v37);
    v15 = &File::FileCacheProviderName;
    if ( (unsigned __int64)qword_180183038 > 7 )
      v15 = (__int64 *)File::FileCacheProviderName;
    v16 = TelCacheProvider::Initialize(&v63, v15, ((unsigned __int64)v14 + 8) & -(__int64)(v14 != 0), 0, 2, 5, 500);
    if ( v16 >= 0 )
    {
      memset_0(v73, 0, 0x4Eu);
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v78 = 0;
      v79 = 0;
      v80 = 0;
      v74 = 0;
      v72 = 0;
      v37 = (File *)operator new(0x90u);
      v17 = AmiFrameworkItem::AmiFrameworkItem(v37);
      v18 = &AmiFrameworkItem::ApplicationFrameworkCacheProviderName;
      if ( (unsigned __int64)qword_180183278 > 7 )
        v18 = (__int64 *)AmiFrameworkItem::ApplicationFrameworkCacheProviderName;
      v19 = TelCacheProvider::Initialize(&v72, v18, v17, 0, 2, 5, 500);
      if ( v19 >= 0 )
      {
        memset_0(v55, 0, 0x4Eu);
        v57 = 0;
        v58 = 0;
        v59 = 0;
        v60 = 0;
        v61 = 0;
        v62 = 0;
        v56 = 0;
        v54 = 0;
        v20 = (AmiShortcutItem *)operator new(0xA8u);
        v21 = AmiShortcutItem::AmiShortcutItem(v20);
        v22 = &AmiShortcutItem::ShortcutCacheProviderName;
        if ( (unsigned __int64)qword_180183338 > 7 )
          v22 = (__int64 *)AmiShortcutItem::ShortcutCacheProviderName;
        v23 = TelCacheProvider::Initialize(&v54, v22, v21, 0, 1, 3, 100);
        if ( v23 >= 0 )
        {
          if ( (a1 & 0x200) != 0 )
          {
            v24 = 1;
          }
          else if ( (a1 & 0x100) != 0 )
          {
            v24 = 0;
          }
          else
          {
            v24 = 3 - ((a1 & 0x400400) != 0);
          }
          LODWORD(v37) = (a1 & 0x8000000) != 0;
          if ( (a1 & 0x40000000) != 0 )
          {
            LODWORD(v38) = 0;
            v25 = &Application::LastDetailedAppSent;
            v26 = &Application::LastDetailedAppSent;
            if ( (unsigned __int64)qword_180182A58 > 7 )
              v26 = (__int64 *)Application::LastDetailedAppSent;
            if ( v47 )
            {
              Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((Windows::Compat::Inventory::InventorySynchronization *)&v49);
              v27 = (*(__int64 (__fastcall **)(__int64, __int64 *, void ***))(*(_QWORD *)v47 + 72LL))(v47, v26, &v38);
              Windows::Compat::Inventory::InventorySynchronization::ReleaseLock((Windows::Compat::Inventory::InventorySynchronization *)&v49);
            }
            else
            {
              v27 = -2147467262;
            }
            TelCacheProvider::ClearData((TelCacheProvider *)&v45);
            if ( v27 >= 0 )
            {
              if ( (unsigned __int64)qword_180182A58 > 7 )
                v25 = (__int64 *)Application::LastDetailedAppSent;
              if ( v47 )
              {
                v28 = (unsigned int)v38;
                Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((Windows::Compat::Inventory::InventorySynchronization *)&v49);
                (*(void (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v47 + 96LL))(v47, v25, v28);
                Windows::Compat::Inventory::InventorySynchronization::ReleaseLock((Windows::Compat::Inventory::InventorySynchronization *)&v49);
              }
            }
          }
          std::wstring::wstring(&pvarg, &byte_1801389F0);
          ConfigSettings::ConfigSettings(
            (unsigned int)v81,
            (a1 & 0x1000 | 0x800u) >> 11,
            (unsigned int)&v45,
            (unsigned int)&v63,
            0,
            0,
            v24,
            (__int64)g_appxPackageFullName,
            (__int64)g_extractedAppxPackageFullPath,
            (__int64)g_extractedAppxManifestFullPath,
            (__int64)g_extractedAppxBundleFullPath,
            (__int64)&pvarg,
            1);
          std::wstring::~wstring(&pvarg);
          v82 = &v54;
          v83 = &v72;
          std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(v41);
          if ( (a1 & 0x480700) != 0 )
          {
            v37 = (File *)&StoreAppFinder::`vftable';
            StoreAppFinder::EnumeratePackages(v81, v41);
          }
          if ( (a1 & 3) != 0 )
          {
            v37 = (File *)&StoreAppFinder::`vftable';
            AppvAppFinder::EnumeratePackages(v81, v41);
            v38 = &StoreAppFinder::`vftable';
            ArpAppFinder::GetEvidenceFromAllArpEntries(v81, v41);
            v42 = &StoreAppFinder::`vftable';
            AppPlatformFinder::GetEvidence(v81, v41);
          }
          v29 = v40;
          pvarg.vt = 11;
          if ( v40 )
            pvarg.iVal = -1;
          else
            pvarg.iVal = 0;
          v30 = _bstr_t::_bstr_t((_bstr_t *)&v40, (const struct _variant_t *)&pvarg);
          v31 = _bstr_t::length(v30);
          _bstr_t::~_bstr_t((_bstr_t *)&v40);
          VariantClear(&pvarg);
          if ( v31 )
          {
            v32 = std::vector<Application>::vector<Application>(&pvarg, v41);
            XmlBuilder::XmlBuilder(v36, v81, v32, v29);
          }
          if ( (unsigned int)EtwEventWriteNoRegistration(AE_LOG, AE_PCA_AMI_REFRESH_COMPLETE, 0, 0) )
            AslLogCallPrintf(
              3,
              (unsigned int)"CreateSoftwareInventory",
              828,
              (unsigned int)"Failed to send ETW event [%d]");
          GetTickCount();
          AslLogCallPrintf(
            3,
            (unsigned int)"CreateSoftwareInventory",
            831,
            (unsigned int)"CreateSoftwareInventory elapsed time: %d");
          std::vector<Application>::_Tidy(v41);
          ConfigSettings::~ConfigSettings((ConfigSettings *)v81);
          TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v54);
          TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v72);
          TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v63);
          TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v45);
          Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v33);
          Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v34);
          Utility::UninitializeWatchdogTimer();
          return v35;
        }
        else
        {
          AslLogCallPrintf(1, (unsigned int)"CreateSoftwareInventory", 688, (unsigned int)"[%#x]");
          TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v54);
          TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v72);
          TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v63);
          TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v45);
          Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v33);
          Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v34);
          return (unsigned int)v23;
        }
      }
      else
      {
        AslLogCallPrintf(1, (unsigned int)"CreateSoftwareInventory", 684, (unsigned int)"[%#x]");
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v72);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v63);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v45);
        Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v33);
        Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v34);
        return (unsigned int)v19;
      }
    }
    else
    {
      AslLogCallPrintf(1, (unsigned int)"CreateSoftwareInventory", 680, (unsigned int)"[%#x]");
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v63);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v45);
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v33);
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v34);
      return (unsigned int)v16;
    }
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"CreateSoftwareInventory", 676, (unsigned int)"[%#x]");
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v45);
    Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v33);
    Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v34);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x180045740  push    rdi
0x180045742  push    r12
0x180045744  push    r13
0x180045746  push    r14
0x180045748  push    r15
0x18004574a  mov     eax, 1460h
0x18004574f  call    _alloca_probe
0x180045754  sub     rsp, rax
0x180045757  mov     [rsp+1488h+var_1398], 0FFFFFFFFFFFFFFFEh
0x180045763  mov     [rsp+1488h+arg_8], rbx
0x18004576b  mov     [rsp+1488h+arg_18], rsi
0x180045773  mov     rax, cs:__security_cookie
0x18004577a  xor     rax, rsp
0x18004577d  mov     [rsp+1488h+var_38], rax
0x180045785  mov     [rsp+1488h+var_13C0], r8
0x18004578d  mov     esi, ecx
0x18004578f  xor     r13d, r13d
0x180045792  mov     [rsp+1488h+var_13E0], r13d
0x18004579a  call    ?InitializeWatchdogTimer@Utility@@SA_NXZ; Utility::InitializeWatchdogTimer(void)
0x18004579f  nop
0x1800457a0  call    cs:__imp_GetTickCount
0x1800457a6  mov     [rsp+1488h+var_13C8], eax
0x1800457ad  call    ?DownlevelThunksInitEx@@YAHPEAUTHUNKS@@K@Z; DownlevelThunksInitEx(THUNKS *,ulong)
0x1800457b2  mov     eax, 800401F0h
0x1800457b7  mov     [rsp+1488h+var_13E4], eax
0x1800457be  mov     [rsp+1488h+var_13E8], eax
0x1800457c5  lea     r15d, [r13+2]
0x1800457c9  mov     edx, r15d; unsigned __int16
0x1800457cc  lea     ecx, [r13+6]; unsigned __int16
0x1800457d0  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800457d5  test    al, al
0x1800457d7  jz      short loc_180045834
0x1800457d9  lea     rcx, [rsp+1488h+var_13E8]
0x1800457e1  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x1800457e6  mov     ebx, eax
0x1800457e8  test    eax, eax
0x1800457ea  jns     loc_18004588C
0x1800457f0  mov     [rsp+1488h+var_1468], eax
0x1800457f4  lea     r9, asc_18013E640; "[%#x]"
0x1800457fb  mov     r8d, 296h
0x180045801  lea     rdx, aCreatesoftware_0; "CreateSoftwareInventory"
0x180045808  lea     ecx, [r13+1]
0x18004580c  call    AslLogCallPrintf
0x180045811  nop
0x180045812  lea     rcx, [rsp+1488h+var_13E8]; this
0x18004581a  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x18004581f  nop
0x180045820  lea     rcx, [rsp+1488h+var_13E4]; this
0x180045828  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x18004582d  mov     eax, ebx
0x18004582f  jmp     loc_18004618D
0x180045834  lea     rcx, [rsp+1488h+var_13E4]; this
0x18004583c  call    ?Initialize@AutoCoInitialize@Common@@QEAAJK@Z; Common::AutoCoInitialize::Initialize(ulong)
0x180045841  mov     ebx, eax
0x180045843  test    eax, eax
0x180045845  jns     short loc_18004588C
0x180045847  mov     [rsp+1488h+var_1468], eax
0x18004584b  lea     r9, asc_18013E640; "[%#x]"
0x180045852  mov     r8d, 29Ah
0x180045858  lea     rdx, aCreatesoftware_0; "CreateSoftwareInventory"
0x18004585f  mov     ecx, 1
0x180045864  call    AslLogCallPrintf
0x180045869  nop
0x18004586a  lea     rcx, [rsp+1488h+var_13E8]; this
0x180045872  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180045877  nop
0x180045878  lea     rcx, [rsp+1488h+var_13E4]; this
0x180045880  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180045885  mov     eax, ebx
0x180045887  jmp     loc_18004618D
0x18004588c  mov     edi, 1
0x180045891  test    esi, 3727C8FCh
0x180045897  jz      short loc_1800458B8
0x180045899  mov     [rsp+1488h+var_1468], esi
0x18004589d  lea     r9, aUnexpectedFlag; "Unexpected flag(s) passed to CreateSoft"...
0x1800458a4  mov     r8d, 29Fh
0x1800458aa  lea     rdx, aCreatesoftware_0; "CreateSoftwareInventory"
0x1800458b1  mov     ecx, edi
0x1800458b3  call    AslLogCallPrintf
0x1800458b8  mov     r14d, 4Eh ; 'N'
0x1800458be  mov     r8d, r14d; Size
0x1800458c1  xor     edx, edx; Val
0x1800458c3  lea     rcx, [rsp+1488h+var_1280]; void *
0x1800458cb  call    memset_0
0x1800458d0  mov     [rsp+1488h+var_1228], r13w
0x1800458d9  mov     [rsp+1488h+var_1220], r13
0x1800458e1  xorps   xmm0, xmm0
0x1800458e4  movdqa  [rsp+1488h+var_1218], xmm0
0x1800458ed  mov     [rsp+1488h+var_1208], r13
0x1800458f5  mov     [rsp+1488h+var_1200], r13d
0x1800458fd  mov     [rsp+1488h+var_11FC], r13b
0x180045905  mov     [rsp+1488h+var_1230], r13
0x18004590d  mov     [rsp+1488h+var_1288], r13
0x180045915  mov     ecx, 3F0h; Size
0x18004591a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004591f  mov     [rsp+1488h+var_13D8], rax
0x180045927  mov     rcx, rax; this
0x18004592a  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x18004592f  nop
0x180045930  lea     rdx, ?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x180045937  cmp     cs:qword_180182A38, 7
0x18004593f  cmova   rdx, cs:?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x180045947  mov     r12d, 1F4h
0x18004594d  mov     [rsp+1488h+var_1458], r12d
0x180045952  mov     [rsp+1488h+var_1460], 5
0x18004595a  mov     [rsp+1488h+var_1468], r15d
0x18004595f  xor     r9d, r9d
0x180045962  mov     r8, rax
0x180045965  lea     rcx, [rsp+1488h+var_1288]
0x18004596d  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180045972  mov     ebx, eax
0x180045974  test    eax, eax
0x180045976  jns     short loc_1800459C8
0x180045978  mov     [rsp+1488h+var_1468], eax
0x18004597c  lea     r9, asc_18013E640; "[%#x]"
0x180045983  mov     r8d, 2A4h
0x180045989  lea     rdx, aCreatesoftware_0; "CreateSoftwareInventory"
0x180045990  mov     ecx, edi
0x180045992  call    AslLogCallPrintf
0x180045997  nop
0x180045998  lea     rcx, [rsp+1488h+var_1288]; this
0x1800459a0  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x1800459a5  nop
0x1800459a6  lea     rcx, [rsp+1488h+var_13E8]; this
0x1800459ae  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x1800459b3  nop
0x1800459b4  lea     rcx, [rsp+1488h+var_13E4]; this
0x1800459bc  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x1800459c1  mov     eax, ebx
0x1800459c3  jmp     loc_18004618D
0x1800459c8  mov     r8, r14; Size
0x1800459cb  xor     edx, edx; Val
0x1800459cd  lea     rcx, [rsp+1488h+var_1150]; void *
0x1800459d5  call    memset_0
0x1800459da  mov     [rsp+1488h+var_10F8], r13w
0x1800459e3  mov     [rsp+1488h+var_10F0], r13
0x1800459eb  xorps   xmm0, xmm0
0x1800459ee  movdqa  [rsp+1488h+var_10E8], xmm0
0x1800459f7  mov     [rsp+1488h+var_10D8], r13
0x1800459ff  mov     [rsp+1488h+var_10D0], r13d
0x180045a07  mov     [rsp+1488h+var_10CC], r13b
0x180045a0f  mov     [rsp+1488h+var_1100], r13
0x180045a17  mov     [rsp+1488h+var_1158], r13
0x180045a1f  mov     ecx, 330h; Size
0x180045a24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045a29  mov     [rsp+1488h+var_13D8], rax
0x180045a31  mov     rcx, rax; this
0x180045a34  call    ??0File@@QEAA@XZ; File::File(void)
0x180045a39  nop
0x180045a3a  lea     rcx, [rax+8]
0x180045a3e  neg     rax
0x180045a41  sbb     r8, r8
0x180045a44  and     r8, rcx
0x180045a47  lea     rdx, ?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x180045a4e  cmp     cs:qword_180183038, 7
0x180045a56  cmova   rdx, cs:?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x180045a5e  mov     [rsp+1488h+var_1458], r12d
0x180045a63  mov     [rsp+1488h+var_1460], 5
0x180045a6b  mov     [rsp+1488h+var_1468], r15d
0x180045a70  xor     r9d, r9d
0x180045a73  lea     rcx, [rsp+1488h+var_1158]
0x180045a7b  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180045a80  mov     ebx, eax
0x180045a82  test    eax, eax
0x180045a84  jns     short loc_180045AE4
0x180045a86  mov     [rsp+1488h+var_1468], eax
0x180045a8a  lea     r9, asc_18013E640; "[%#x]"
0x180045a91  mov     r8d, 2A8h
0x180045a97  lea     rdx, aCreatesoftware_0; "CreateSoftwareInventory"
0x180045a9e  mov     ecx, edi
0x180045aa0  call    AslLogCallPrintf
0x180045aa5  nop
0x180045aa6  lea     rcx, [rsp+1488h+var_1158]; this
0x180045aae  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180045ab3  nop
0x180045ab4  lea     rcx, [rsp+1488h+var_1288]; this
0x180045abc  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180045ac1  nop
0x180045ac2  lea     rcx, [rsp+1488h+var_13E8]; this
0x180045aca  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180045acf  nop
0x180045ad0  lea     rcx, [rsp+1488h+var_13E4]; this
0x180045ad8  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180045add  mov     eax, ebx
0x180045adf  jmp     loc_18004618D
0x180045ae4  mov     r8, r14; Size
0x180045ae7  xor     edx, edx; Val
0x180045ae9  lea     rcx, [rsp+1488h+var_10C0]; void *
0x180045af1  call    memset_0
0x180045af6  mov     [rsp+1488h+var_1068], r13w
0x180045aff  mov     [rsp+1488h+var_1060], r13
0x180045b07  xorps   xmm0, xmm0
0x180045b0a  movdqa  [rsp+1488h+var_1058], xmm0
0x180045b13  mov     [rsp+1488h+var_1048], r13
0x180045b1b  mov     [rsp+1488h+var_1040], r13d
0x180045b23  mov     [rsp+1488h+var_103C], r13b
0x180045b2b  mov     [rsp+1488h+var_1070], r13
0x180045b33  mov     [rsp+1488h+var_10C8], r13
0x180045b3b  mov     ecx, 90h; Size
0x180045b40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045b45  mov     [rsp+1488h+var_13D8], rax
0x180045b4d  mov     rcx, rax; this
0x180045b50  call    ??0AmiFrameworkItem@@QEAA@XZ; AmiFrameworkItem::AmiFrameworkItem(void)
0x180045b55  nop
0x180045b56  lea     rdx, ?ApplicationFrameworkCacheProviderName@AmiFrameworkItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiFrameworkItem::ApplicationFrameworkCacheProviderName
0x180045b5d  cmp     cs:qword_180183278, 7
0x180045b65  cmova   rdx, cs:?ApplicationFrameworkCacheProviderName@AmiFrameworkItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiFrameworkItem::ApplicationFrameworkCacheProviderName
0x180045b6d  mov     [rsp+1488h+var_1458], r12d
0x180045b72  mov     [rsp+1488h+var_1460], 5
0x180045b7a  mov     [rsp+1488h+var_1468], r15d
0x180045b7f  xor     r9d, r9d
0x180045b82  mov     r8, rax
0x180045b85  lea     rcx, [rsp+1488h+var_10C8]
0x180045b8d  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180045b92  mov     ebx, eax
0x180045b94  test    eax, eax
0x180045b96  jns     short loc_180045C04
0x180045b98  mov     [rsp+1488h+var_1468], eax
0x180045b9c  lea     r9, asc_18013E640; "[%#x]"
0x180045ba3  mov     r8d, 2ACh
0x180045ba9  lea     rdx, aCreatesoftware_0; "CreateSoftwareInventory"
0x180045bb0  mov     ecx, edi
0x180045bb2  call    AslLogCallPrintf
0x180045bb7  nop
0x180045bb8  lea     rcx, [rsp+1488h+var_10C8]; this
0x180045bc0  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180045bc5  nop
0x180045bc6  lea     rcx, [rsp+1488h+var_1158]; this
0x180045bce  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180045bd3  nop
0x180045bd4  lea     rcx, [rsp+1488h+var_1288]; this
0x180045bdc  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180045be1  nop
0x180045be2  lea     rcx, [rsp+1488h+var_13E8]; this
0x180045bea  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180045bef  nop
0x180045bf0  lea     rcx, [rsp+1488h+var_13E4]; this
0x180045bf8  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180045bfd  mov     eax, ebx
0x180045bff  jmp     loc_18004618D
0x180045c04  mov     r8, r14; Size
0x180045c07  xor     edx, edx; Val
0x180045c09  lea     rcx, [rsp+1488h+var_11F0]; void *
0x180045c11  call    memset_0
0x180045c16  mov     [rsp+1488h+var_1198], r13w
0x180045c1f  mov     [rsp+1488h+var_1190], r13
0x180045c27  xorps   xmm0, xmm0
0x180045c2a  movdqa  [rsp+1488h+var_1188], xmm0
0x180045c33  mov     [rsp+1488h+var_1178], r13
0x180045c3b  mov     [rsp+1488h+var_1170], r13d
0x180045c43  mov     [rsp+1488h+var_116C], r13b
0x180045c4b  mov     [rsp+1488h+var_11A0], r13
0x180045c53  mov     [rsp+1488h+var_11F8], r13
0x180045c5b  mov     ecx, 0A8h; Size
0x180045c60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045c65  mov     rcx, rax; this
0x180045c68  call    ??0AmiShortcutItem@@QEAA@XZ; AmiShortcutItem::AmiShortcutItem(void)
0x180045c6d  lea     rdx, ?ShortcutCacheProviderName@AmiShortcutItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiShortcutItem::ShortcutCacheProviderName
0x180045c74  cmp     cs:qword_180183338, 7
0x180045c7c  cmova   rdx, cs:?ShortcutCacheProviderName@AmiShortcutItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiShortcutItem::ShortcutCacheProviderName
0x180045c84  mov     [rsp+1488h+var_1458], 64h ; 'd'
0x180045c8c  mov     [rsp+1488h+var_1460], 3
0x180045c94  mov     [rsp+1488h+var_1468], edi
0x180045c98  xor     r9d, r9d
0x180045c9b  mov     r8, rax
0x180045c9e  lea     rcx, [rsp+1488h+var_11F8]
0x180045ca6  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180045cab  mov     ebx, eax
0x180045cad  test    eax, eax
0x180045caf  jns     short loc_180045D2B
0x180045cb1  mov     [rsp+1488h+var_1468], eax
0x180045cb5  lea     r9, asc_18013E640; "[%#x]"
0x180045cbc  mov     r8d, 2B0h
0x180045cc2  lea     rdx, aCreatesoftware_0; "CreateSoftwareInventory"
0x180045cc9  mov     ecx, edi
0x180045ccb  call    AslLogCallPrintf
0x180045cd0  nop
0x180045cd1  lea     rcx, [rsp+1488h+var_11F8]; this
0x180045cd9  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180045cde  nop
0x180045cdf  lea     rcx, [rsp+1488h+var_10C8]; this
0x180045ce7  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180045cec  nop
0x180045ced  lea     rcx, [rsp+1488h+var_1158]; this
0x180045cf5  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180045cfa  nop
0x180045cfb  lea     rcx, [rsp+1488h+var_1288]; this
0x180045d03  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180045d08  nop
0x180045d09  lea     rcx, [rsp+1488h+var_13E8]; this
0x180045d11  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180045d16  nop
0x180045d17  lea     rcx, [rsp+1488h+var_13E4]; this
0x180045d1f  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180045d24  mov     eax, ebx
0x180045d26  jmp     loc_18004618D
0x180045d2b  bt      esi, 9
0x180045d2f  jnb     short loc_180045D36
0x180045d31  mov     r14d, edi
0x180045d34  jmp     short loc_180045D51
  ... truncated ...
```
