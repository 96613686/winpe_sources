# AppxAllUserStore::Internal::RestoreRegistryData(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,bool)

- ea: `0x180035bc8`
- end: `0x18003648f`
- name: `?RestoreRegistryData@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1_N@Z`
- size: `2247`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *__hidden this, struct AppxAllUserStore::BasicLogFile *, struct AppxAllUserStore::BasicLogFile *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180035140`

## callees

- `0x180001a70`
- `0x1800036d4`
- `0x180004920`
- `0x180004968`
- `0x1800066dc`
- `0x180006d40`
- `0x18000d6a0`
- `0x180012c3c`
- `0x180016d5c`
- `0x180016e70`
- `0x180017330`
- `0x180017cd0`
- `0x180017f18`
- `0x180017f50`
- `0x180018248`
- `0x180019ee0`
- `0x18001b3f0`
- `0x1800334f4`
- `0x180035bc8`
- `0x1800469e8`

## string_xrefs

- `0x180035fc5`: `Config`
- `0x180035d5a`: `GetAllUserApplicationsPath failed, 0x%0x.`
- `0x180035ce5`: `LoadSoftwareHiveAndOpenKeyForSystemRoot dst failed, 0x%0x.`
- `0x180035eeb`: `Open applications key at target failed, 0x%0x.`
- `0x180035de6`: `CopyRegSubkeyTree failed, 0x%0x.`
- `0x180036072`: `CopyRegSubkeyTree failed, 0x%0x.`
- `0x1800361d0`: `CopyRegSubkeyTree failed, 0x%0x.`
- `0x1800362fd`: `CopyRegSubkeyTree failed, 0x%0x.`
- `0x180035bf6`: `In RestoreRegistryData %ls %ls %u.`
- `0x180035c73`: `LoadSoftwareHiveAndOpenKeyForSystemRoot src failed, 0x%0x.`
- `0x180035da2`: `Copying subtree %ls.`
- `0x18003602c`: `Copying subtree %ls.`
- `0x18003618d`: `Copying subtree %ls.`
- `0x1800362ba`: `Copying subtree %ls.`
- `0x180035e20`: `GetAllUserStorePathfailed, 0x%0x`
- `0x180035e8f`: `AppxAllUserStore path: %ls`
- `0x180035f90`: `DeleteValue %ls 0x%0x.`
- `0x180035fe2`: `GetConfigPath failed, 0x%0x.`
- `0x180036088`: `Overriding config SetupPhase for Language Overlay Packages`
- `0x180036106`: `GetUupProductsPath failed, 0x%0x.`
- `0x1800361e9`: `UupProducts key doesn't exist -- nothing to copy.`
- `0x180036233`: `GetPinnedPath failed, 0x%0x.`
- `0x180036316`: `Pinned key doesn't exist -- nothing to copy.`
- `0x1800363cf`: `ProcessDeletedKeySubtree hit 0x%0x.`
- `0x1800363e9`: `DeletedAllUserPackages folder not found.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::RestoreRegistryData(
        AppxAllUserStore::Internal *this,
        struct AppxAllUserStore::BasicLogFile *a2,
        struct AppxAllUserStore::BasicLogFile *a3,
        const unsigned __int16 *a4)
{
  char v4; // r14
  int v8; // eax
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  int v12; // eax
  struct Common::StringBuffer *v13; // r9
  int v14; // eax
  int AllUserChildStorePath; // eax
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  int v19; // eax
  struct Common::StringBuffer *v20; // r9
  int v21; // eax
  int v22; // eax
  int v23; // eax
  struct AppxAllUserStore::BasicLogFile *v24; // r8
  LSTATUS v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  unsigned int v29; // edi
  int v30; // eax
  struct Common::StringBuffer *v31; // r9
  int v32; // eax
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  struct Common::StringBuffer *v38; // r9
  int v39; // eax
  struct Common::StringBuffer *v40; // r9
  int v41; // eax
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // eax
  int v45; // eax
  int v46; // eax
  struct Common::StringBuffer *v47; // r9
  int v48; // eax
  int v49; // eax
  int v50; // eax
  unsigned int v51; // ebx
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // eax
  unsigned int v57; // edi
  const struct _tlgProvider_t *v58; // rax
  __int64 v59; // r8
  __int64 v60; // r9
  int v61; // eax
  __int64 v62; // rdx
  int v64; // [rsp+20h] [rbp-E0h]
  struct Common::RegistryKey *v65; // [rsp+20h] [rbp-E0h]
  struct Common::RegistryKey *v66; // [rsp+30h] [rbp-D0h]
  struct Common::RegistryKey *v67; // [rsp+30h] [rbp-D0h]
  HKEY v68; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v69; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR v72[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v73; // [rsp+70h] [rbp-90h]
  struct AppxAllUserStore::BasicLogFile *v74[2]; // [rsp+78h] [rbp-88h] BYREF
  int v75; // [rsp+88h] [rbp-78h]
  LPCWSTR lpSubKey[2]; // [rsp+90h] [rbp-70h] BYREF
  int v77; // [rsp+A0h] [rbp-60h]
  struct AppxAllUserStore::BasicLogFile *v78[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v79; // [rsp+B8h] [rbp-48h]
  struct AppxAllUserStore::BasicLogFile *v80[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v81; // [rsp+D0h] [rbp-30h]
  const unsigned __int16 *v82; // [rsp+D8h] [rbp-28h] BYREF
  const unsigned __int16 *v83; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v84[4]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int v85[4]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]
  unsigned int v87; // [rsp+178h] [rbp+78h] BYREF

  v4 = (char)a4;
  v8 = AppxAllUserStore::BasicLogFile::WriteMsg(
         this,
         L"In RestoreRegistryData %ls %ls %u.",
         a2,
         a3,
         (unsigned __int8)a4);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x765,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v8);
  hKey = 0;
  *(_OWORD *)v85 = 0;
  *(_OWORD *)v84 = 0;
  v9 = AppxAllUserStore::Internal::LoadSoftwareHiveAndOpenKeyForSystemRoot(
         this,
         a2,
         L"APPX_HIVE_RESTORE_SRC_ALIAS_SOFTWARE",
         0x20019u,
         (unsigned int)v85,
         &hKey,
         v66);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v68 = 0;
    v12 = AppxAllUserStore::Internal::LoadSoftwareHiveAndOpenKeyForSystemRoot(
            this,
            a3,
            L"APPX_HIVE_RESTORE_DST_ALIAS_SOFTWARE",
            0xF003Fu,
            (unsigned int)v84,
            &v68,
            v67);
    v10 = v12;
    if ( v12 < 0 )
    {
      v14 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"LoadSoftwareHiveAndOpenKeyForSystemRoot dst failed, 0x%0x.",
              (unsigned int)v12);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x785,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v14);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x785,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)v10,
        (int)v65);
      goto LABEL_11;
    }
    v73 = 0;
    *(_OWORD *)v72 = 0;
    AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                              (AppxAllUserStore *)L"Applications",
                              0,
                              (unsigned int *)v72,
                              v13);
    v10 = AllUserChildStorePath;
    if ( AllUserChildStorePath < 0 )
    {
      v16 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"GetAllUserApplicationsPath failed, 0x%0x.",
              (unsigned int)AllUserChildStorePath);
      v17 = 1930;
LABEL_14:
      if ( v16 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v17,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v16);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)v10,
        (int)v65);
      goto LABEL_17;
    }
    v18 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Copying subtree %ls.", v72[1]);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x78C,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v18);
    v19 = AppxAllUserStore::Internal::CopyRegSubkeyTree(
            this,
            (struct AppxAllUserStore::BasicLogFile *)v72[1],
            (Common::RegistryKey *)&hKey,
            (struct Common::RegistryKey *)&v68);
    v10 = v19;
    if ( v19 < 0 )
    {
      v16 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"CopyRegSubkeyTree failed, 0x%0x.", (unsigned int)v19);
      v17 = 1935;
      goto LABEL_14;
    }
    v77 = 0;
    *(_OWORD *)lpSubKey = 0;
    v21 = AppxAllUserStore::GetAllUserChildStorePath(0, 0, (unsigned int *)lpSubKey, v20);
    v10 = v21;
    if ( v21 < 0 )
    {
      v22 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"GetAllUserStorePathfailed, 0x%0x", (unsigned int)v21);
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x793,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v22);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x793,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)v10,
        (int)v65);
      goto LABEL_26;
    }
    phkResult = 0;
    if ( Common::RegistryKey::Open(&phkResult, hKey, lpSubKey[1], 0x20019u) >= 0 )
    {
      v23 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"AppxAllUserStore path: %ls", v72[1]);
      if ( v23 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x799,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v23);
      AppxAllUserStore::Internal::LogAllSubKeys((AppxAllUserStore::Internal *)&phkResult, this, v24);
    }
    v69 = 0;
    v25 = Common::RegistryKey::Open(&v69, v68, v72[1], 0x2001Fu);
    v10 = v25;
    if ( v25 < 0 )
    {
      v26 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"Open applications key at target failed, 0x%0x.",
              (unsigned int)v25);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7A7,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v26);
      if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
        McTemplateU0zd_EventWriteTransfer(v27, AppxAllUserStoreOpenKeyError, v72[1], v10);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A7,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)v10,
        (int)v65);
      goto LABEL_37;
    }
    v28 = Common::RegistryKey::DeleteValue((Common::RegistryKey *)&v69, L"IUIPolicyChecked");
    v29 = v28;
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7AB,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v28);
    v30 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"DeleteValue %ls 0x%0x.", L"IUIPolicyChecked", v29);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7AC,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v30);
    v75 = 0;
    *(_OWORD *)v74 = 0;
    v32 = AppxAllUserStore::GetAllUserChildStorePath((AppxAllUserStore *)L"Config", 0, (unsigned int *)v74, v31);
    v10 = v32;
    if ( v32 < 0 )
    {
      v33 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"GetConfigPath failed, 0x%0x.", (unsigned int)v32);
      v34 = 1969;
LABEL_44:
      if ( v33 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v34,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v33);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)v10,
        (int)v65);
      goto LABEL_47;
    }
    v35 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Copying subtree %ls.", v74[1]);
    if ( v35 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7B3,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v35);
    v36 = AppxAllUserStore::Internal::CopyRegSubkeyTree(
            this,
            v74[1],
            (Common::RegistryKey *)&hKey,
            (struct Common::RegistryKey *)&v68);
    v10 = v36;
    if ( v36 < 0 )
    {
      v33 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"CopyRegSubkeyTree failed, 0x%0x.", (unsigned int)v36);
      v34 = 1974;
      goto LABEL_44;
    }
    v37 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Overriding config SetupPhase for Language Overlay Packages");
    if ( v37 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7B9,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v37);
    v39 = AppxAllUserStore::Internal::ResetLanguageOverlaySetupPhaseIfPresent(
            this,
            (struct AppxAllUserStore::BasicLogFile *)&v68,
            (struct Common::RegistryKey *)v74,
            v38);
    v10 = v39;
    if ( v39 < 0 )
    {
      v33 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"ResetLanguageOverlaySetupPhaseIfPresent failed, 0x%0x.",
              (unsigned int)v39);
      v34 = 1980;
      goto LABEL_44;
    }
    v79 = 0;
    *(_OWORD *)v78 = 0;
    v41 = AppxAllUserStore::GetAllUserChildStorePath((AppxAllUserStore *)L"UupProducts", 0, (unsigned int *)v78, v40);
    v10 = v41;
    if ( v41 < 0 )
    {
      v42 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"GetUupProductsPath failed, 0x%0x.", (unsigned int)v41);
      v43 = 1987;
LABEL_58:
      if ( v42 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v43,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v42);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v43,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)v10,
        (int)v65);
LABEL_61:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v78);
LABEL_47:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v74);
LABEL_37:
      Common::RegistryKey::~RegistryKey(&v69);
      Common::RegistryKey::~RegistryKey(&phkResult);
LABEL_26:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
LABEL_17:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v72);
LABEL_11:
      Common::RegistryKey::~RegistryKey(&v68);
      goto LABEL_96;
    }
    LOBYTE(v87) = 0;
    v44 = Common::RegistryKey::KeyExists(hKey, (const unsigned __int16 *)v78[1], (bool *)&v87);
    v10 = v44;
    if ( v44 < 0 )
    {
      v42 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"KeyExists(uupProductsKey) failed, 0x%0x.",
              (unsigned int)v44);
      v43 = 1991;
      goto LABEL_58;
    }
    if ( (_BYTE)v87 )
    {
      v45 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Copying subtree %ls.", v78[1]);
      if ( v45 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7CA,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v45);
      v46 = AppxAllUserStore::Internal::CopyRegSubkeyTree(
              this,
              v78[1],
              (Common::RegistryKey *)&hKey,
              (struct Common::RegistryKey *)&v68);
      v10 = v46;
      if ( v46 < 0 )
      {
        v42 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"CopyRegSubkeyTree failed, 0x%0x.", (unsigned int)v46);
        v43 = 1997;
        goto LABEL_58;
      }
    }
    else
    {
      v48 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"UupProducts key doesn't exist -- nothing to copy.");
      if ( v48 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7D1,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v48);
    }
    v81 = 0;
    *(_OWORD *)v80 = 0;
    v49 = AppxAllUserStore::GetAllUserChildStorePath((AppxAllUserStore *)L"Pinned", 0, (unsigned int *)v80, v47);
    v10 = v49;
    if ( v49 < 0 )
    {
      v50 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"GetPinnedPath failed, 0x%0x.", (unsigned int)v49);
      v51 = 2007;
LABEL_73:
      if ( v50 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v51,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v50);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v51,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)v10,
        (int)v65);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v80);
      goto LABEL_61;
    }
    LOBYTE(v87) = 0;
    v52 = Common::RegistryKey::KeyExists(hKey, (const unsigned __int16 *)v80[1], (bool *)&v87);
    v10 = v52;
    if ( v52 < 0 )
    {
      v50 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"KeyExists(pinnedKey) failed, 0x%0x.", (unsigned int)v52);
      v51 = 2011;
      goto LABEL_73;
    }
    if ( (_BYTE)v87 )
    {
      v53 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Copying subtree %ls.", v80[1]);
      if ( v53 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7DE,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v53);
      v54 = AppxAllUserStore::Internal::CopyRegSubkeyTree(
              this,
              v80[1],
              (Common::RegistryKey *)&hKey,
              (struct Common::RegistryKey *)&v68);
      v10 = v54;
      if ( v54 < 0 )
      {
        v50 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"CopyRegSubkeyTree failed, 0x%0x.", (unsigned int)v54);
        v51 = 2017;
        goto LABEL_73;
      }
    }
    else
    {
      v55 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Pinned key doesn't exist -- nothing to copy.");
      if ( v55 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7E5,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v55);
    }
    if ( v4 )
    {
      v56 = AppxAllUserStore::Internal::ProcessDeletedKeySubtree(
              this,
              a3,
              (const unsigned __int16 *)&hKey,
              (struct Common::RegistryKey *)&v68,
              v65);
      v57 = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7ED,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v56);
        v58 = AppxAllUserStoreTelemetry::Provider();
        if ( *(_DWORD *)v58 > 5u )
        {
          if ( (unsigned __int8)tlgKeywordOn(v58, 0x400000000000LL, v58) )
          {
            v82 = (const unsigned __int16 *)a3;
            v83 = (const unsigned __int16 *)a2;
            v87 = v57;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v59,
              (__int64)byte_18005D075,
              v59,
              v60,
              (__int64)&v87,
              &v83,
              &v82);
          }
        }
      }
      v61 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"ProcessDeletedKeySubtree hit 0x%0x.", v57);
      if ( v61 >= 0 )
        goto LABEL_95;
      v62 = 2041;
    }
    else
    {
      v61 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"DeletedAllUserPackages folder not found.");
      if ( v61 >= 0 )
      {
LABEL_95:
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v80);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v78);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v74);
        Common::RegistryKey::~RegistryKey(&v69);
        Common::RegistryKey::~RegistryKey(&phkResult);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v72);
        Common::RegistryKey::~RegistryKey(&v68);
        v10 = 0;
        goto LABEL_96;
      }
      v62 = 2045;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v62,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v61);
    goto LABEL_95;
  }
  v11 = AppxAllUserStore::BasicLogFile::WriteMsg(
          this,
          L"LoadSoftwareHiveAndOpenKeyForSystemRoot src failed, 0x%0x.",
          (unsigned int)v9);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x778,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v11);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x778,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
    (const char *)v10,
    v64);
LABEL_96:
  Common::RegistryKey::~RegistryKey(&hKey);
  AppxAllUserStore::AutoRegLoadHive::~AutoRegLoadHive((AppxAllUserStore::AutoRegLoadHive *)v84);
  AppxAllUserStore::AutoRegLoadHive::~AutoRegLoadHive((AppxAllUserStore::AutoRegLoadHive *)v85);
  return v10;
}

```

## disassembly

```asm
0x180035bc8  push    rbp
0x180035bca  push    rbx
0x180035bcb  push    rsi
0x180035bcc  push    rdi
0x180035bcd  push    r12
0x180035bcf  push    r13
0x180035bd1  push    r14
0x180035bd3  push    r15
0x180035bd5  lea     rbp, [rsp-18h]
0x180035bda  sub     rsp, 118h
0x180035be1  movzx   r14d, r9b
0x180035be5  mov     rsi, r8
0x180035be8  mov     r9, r8
0x180035beb  mov     dword ptr [rsp+150h+var_130], r14d; int
0x180035bf0  mov     r8, rdx
0x180035bf3  mov     r15, rdx
0x180035bf6  lea     rdx, aInRestoreregis; "In RestoreRegistryData %ls %ls %u."
0x180035bfd  mov     rbx, rcx
0x180035c00  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035c05  xor     r12d, r12d
0x180035c08  lea     r13, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180035c0f  test    eax, eax
0x180035c11  jns     short loc_180035C27
0x180035c13  mov     rcx, [rbp+58h]; this
0x180035c17  mov     r9d, eax; char *
0x180035c1a  mov     r8, r13; unsigned int
0x180035c1d  mov     edx, 765h; void *
0x180035c22  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035c27  lea     rax, [rsp+150h+hKey]
0x180035c2c  mov     [rsp+150h+hKey], r12
0x180035c31  mov     [rsp+150h+var_128], rax; phkResult
0x180035c36  lea     r8, aAppxHiveRestor; "APPX_HIVE_RESTORE_SRC_ALIAS_SOFTWARE"
0x180035c3d  lea     rax, [rbp+50h+var_58]
0x180035c41  xorps   xmm0, xmm0
0x180035c44  xorps   xmm1, xmm1
0x180035c47  mov     [rsp+150h+var_130], rax; int
0x180035c4c  mov     r9d, 20019h; samDesired
0x180035c52  mov     rdx, r15; struct AppxAllUserStore::BasicLogFile *
0x180035c55  mov     rcx, rbx; this
0x180035c58  movdqu  xmmword ptr [rbp+50h+var_58], xmm0
0x180035c5d  movdqu  xmmword ptr [rbp+50h+var_68], xmm1
0x180035c62  call    ?LoadSoftwareHiveAndOpenKeyForSystemRoot@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1KAEAVAutoRegLoadHive@2@AEAVRegistryKey@Common@@@Z; AppxAllUserStore::Internal::LoadSoftwareHiveAndOpenKeyForSystemRoot(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,ulong,AppxAllUserStore::AutoRegLoadHive &,Common::RegistryKey &)
0x180035c67  mov     edi, eax
0x180035c69  mov     rcx, rbx; this
0x180035c6c  test    eax, eax
0x180035c6e  jns     short loc_180035CAF
0x180035c70  mov     r8d, eax
0x180035c73  lea     rdx, aLoadsoftwarehi; "LoadSoftwareHiveAndOpenKeyForSystemRoot"...
0x180035c7a  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035c7f  mov     ebx, 778h
0x180035c84  test    eax, eax
0x180035c86  jns     short loc_180035C99
0x180035c88  mov     rcx, [rbp+58h]; this
0x180035c8c  mov     r9d, eax; char *
0x180035c8f  mov     r8, r13; unsigned int
0x180035c92  mov     edx, ebx; void *
0x180035c94  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035c99  mov     rcx, [rbp+58h]; this
0x180035c9d  mov     r9d, edi; char *
0x180035ca0  mov     r8, r13; unsigned int
0x180035ca3  mov     edx, ebx; void *
0x180035ca5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035caa  jmp     loc_18003645D
0x180035caf  lea     rax, [rsp+150h+var_110]
0x180035cb4  mov     [rsp+150h+var_110], r12
0x180035cb9  mov     [rsp+150h+var_128], rax; phkResult
0x180035cbe  lea     r8, aAppxHiveRestor_0; "APPX_HIVE_RESTORE_DST_ALIAS_SOFTWARE"
0x180035cc5  lea     rax, [rbp+50h+var_68]
0x180035cc9  mov     r9d, 0F003Fh; samDesired
0x180035ccf  mov     rdx, rsi; struct AppxAllUserStore::BasicLogFile *
0x180035cd2  mov     [rsp+150h+var_130], rax; int
0x180035cd7  call    ?LoadSoftwareHiveAndOpenKeyForSystemRoot@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1KAEAVAutoRegLoadHive@2@AEAVRegistryKey@Common@@@Z; AppxAllUserStore::Internal::LoadSoftwareHiveAndOpenKeyForSystemRoot(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,ulong,AppxAllUserStore::AutoRegLoadHive &,Common::RegistryKey &)
0x180035cdc  mov     edi, eax
0x180035cde  test    eax, eax
0x180035ce0  jns     short loc_180035D2E
0x180035ce2  mov     r8d, eax
0x180035ce5  lea     rdx, aLoadsoftwarehi_0; "LoadSoftwareHiveAndOpenKeyForSystemRoot"...
0x180035cec  mov     rcx, rbx; this
0x180035cef  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035cf4  mov     ebx, 785h
0x180035cf9  test    eax, eax
0x180035cfb  jns     short loc_180035D0E
0x180035cfd  mov     rcx, [rbp+58h]; this
0x180035d01  mov     r9d, eax; char *
0x180035d04  mov     r8, r13; unsigned int
0x180035d07  mov     edx, ebx; void *
0x180035d09  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035d0e  mov     rcx, [rbp+58h]; this
0x180035d12  mov     r9d, edi; char *
0x180035d15  mov     r8, r13; unsigned int
0x180035d18  mov     edx, ebx; void *
0x180035d1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d1f  lea     rcx, [rsp+150h+var_110]; this
0x180035d24  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180035d29  jmp     loc_18003645D
0x180035d2e  xorps   xmm0, xmm0
0x180035d31  mov     [rsp+150h+var_E0], r12d
0x180035d36  lea     r8, [rsp+150h+var_F0]; bool
0x180035d3b  xor     edx, edx; unsigned __int16 *
0x180035d3d  lea     rcx, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x180035d44  movups  xmmword ptr [rsp+150h+var_F0], xmm0
0x180035d49  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x180035d4e  mov     edi, eax
0x180035d50  mov     rcx, rbx; this
0x180035d53  test    eax, eax
0x180035d55  jns     short loc_180035D9D
0x180035d57  mov     r8d, eax
0x180035d5a  lea     rdx, aGetalluserappl; "GetAllUserApplicationsPath failed, 0x%0"...
0x180035d61  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035d66  mov     ebx, 78Ah
0x180035d6b  test    eax, eax
0x180035d6d  jns     short loc_180035D80
0x180035d6f  mov     rcx, [rbp+58h]; this
0x180035d73  mov     r9d, eax; char *
0x180035d76  mov     r8, r13; unsigned int
0x180035d79  mov     edx, ebx; void *
0x180035d7b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035d80  mov     rcx, [rbp+58h]; this
0x180035d84  mov     r9d, edi; char *
0x180035d87  mov     r8, r13; unsigned int
0x180035d8a  mov     edx, ebx; void *
0x180035d8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035d91  lea     rcx, [rsp+150h+var_F0]; this
0x180035d96  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180035d9b  jmp     short loc_180035D1F
0x180035d9d  mov     r8, [rsp+150h+var_F0+8]
0x180035da2  lea     rdx, aCopyingSubtree; "Copying subtree %ls."
0x180035da9  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035dae  test    eax, eax
0x180035db0  jns     short loc_180035DC6
0x180035db2  mov     rcx, [rbp+58h]; this
0x180035db6  mov     r9d, eax; char *
0x180035db9  mov     r8, r13; unsigned int
0x180035dbc  mov     edx, 78Ch; void *
0x180035dc1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035dc6  mov     rdx, [rsp+150h+var_F0+8]; struct AppxAllUserStore::BasicLogFile *
0x180035dcb  lea     r9, [rsp+150h+var_110]; struct Common::RegistryKey *
0x180035dd0  lea     r8, [rsp+150h+hKey]; unsigned __int16 *
0x180035dd5  mov     rcx, rbx; this
0x180035dd8  call    ?CopyRegSubkeyTree@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBGAEAVRegistryKey@Common@@2@Z; AppxAllUserStore::Internal::CopyRegSubkeyTree(AppxAllUserStore::BasicLogFile &,ushort const *,Common::RegistryKey &,Common::RegistryKey &)
0x180035ddd  mov     edi, eax
0x180035ddf  test    eax, eax
0x180035de1  jns     short loc_180035DFF
0x180035de3  mov     r8d, eax
0x180035de6  lea     rdx, aCopyregsubkeyt; "CopyRegSubkeyTree failed, 0x%0x."
0x180035ded  mov     rcx, rbx; this
0x180035df0  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035df5  mov     ebx, 78Fh
0x180035dfa  jmp     loc_180035D6B
0x180035dff  xorps   xmm0, xmm0
0x180035e02  mov     [rbp+50h+var_B0], r12d
0x180035e06  lea     r8, [rbp+50h+lpSubKey]; bool
0x180035e0a  xor     edx, edx; unsigned __int16 *
0x180035e0c  xor     ecx, ecx; this
0x180035e0e  movups  xmmword ptr [rbp+50h+lpSubKey], xmm0
0x180035e12  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x180035e17  mov     edi, eax
0x180035e19  test    eax, eax
0x180035e1b  jns     short loc_180035E68
0x180035e1d  mov     r8d, eax
0x180035e20  lea     rdx, aGetalluserstor; "GetAllUserStorePathfailed, 0x%0x"
0x180035e27  mov     rcx, rbx; this
0x180035e2a  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035e2f  mov     ebx, 793h
0x180035e34  test    eax, eax
0x180035e36  jns     short loc_180035E49
0x180035e38  mov     rcx, [rbp+58h]; this
0x180035e3c  mov     r9d, eax; char *
0x180035e3f  mov     r8, r13; unsigned int
0x180035e42  mov     edx, ebx; void *
0x180035e44  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035e49  mov     rcx, [rbp+58h]; this
0x180035e4d  mov     r9d, edi; char *
0x180035e50  mov     r8, r13; unsigned int
0x180035e53  mov     edx, ebx; void *
0x180035e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035e5a  lea     rcx, [rbp+50h+lpSubKey]; this
0x180035e5e  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180035e63  jmp     loc_180035D91
0x180035e68  mov     r8, [rbp+50h+lpSubKey+8]; lpSubKey
0x180035e6c  lea     rcx, [rsp+150h+phkResult]; phkResult
0x180035e71  mov     rdx, [rsp+150h+hKey]; hKey
0x180035e76  mov     r9d, 20019h; samDesired
0x180035e7c  mov     [rsp+150h+phkResult], r12
0x180035e81  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180035e86  test    eax, eax
0x180035e88  js      short loc_180035EC3
0x180035e8a  mov     r8, [rsp+150h+var_F0+8]
0x180035e8f  lea     rdx, aAppxallusersto_0; "AppxAllUserStore path: %ls"
0x180035e96  mov     rcx, rbx; this
0x180035e99  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035e9e  test    eax, eax
0x180035ea0  jns     short loc_180035EB6
0x180035ea2  mov     rcx, [rbp+58h]; this
0x180035ea6  mov     r9d, eax; char *
0x180035ea9  mov     r8, r13; unsigned int
0x180035eac  mov     edx, 799h; void *
0x180035eb1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035eb6  mov     rdx, rbx; struct Common::RegistryKey *
0x180035eb9  lea     rcx, [rsp+150h+phkResult]; this
0x180035ebe  call    ?LogAllSubKeys@Internal@AppxAllUserStore@@YAXAEAVRegistryKey@Common@@AEAVBasicLogFile@2@@Z; AppxAllUserStore::Internal::LogAllSubKeys(Common::RegistryKey &,AppxAllUserStore::BasicLogFile &)
0x180035ec3  mov     r8, [rsp+150h+var_F0+8]; lpSubKey
0x180035ec8  lea     rcx, [rsp+150h+var_108]; phkResult
0x180035ecd  mov     rdx, [rsp+150h+var_110]; hKey
0x180035ed2  mov     r9d, 2001Fh; samDesired
0x180035ed8  mov     [rsp+150h+var_108], r12
0x180035edd  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180035ee2  mov     edi, eax
0x180035ee4  test    eax, eax
0x180035ee6  jns     short loc_180035F5B
0x180035ee8  mov     r8d, eax
0x180035eeb  lea     rdx, aOpenApplicatio; "Open applications key at target failed,"...
0x180035ef2  mov     rcx, rbx; this
0x180035ef5  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035efa  mov     ebx, 7A7h
0x180035eff  test    eax, eax
0x180035f01  jns     short loc_180035F14
0x180035f03  mov     rcx, [rbp+58h]; this
0x180035f07  mov     r9d, eax; char *
0x180035f0a  mov     r8, r13; unsigned int
0x180035f0d  mov     edx, ebx; void *
0x180035f0f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035f14  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r12b
0x180035f1b  jge     short loc_180035F31
0x180035f1d  mov     r8, [rsp+150h+var_F0+8]
0x180035f22  lea     rdx, AppxAllUserStoreOpenKeyError
0x180035f29  mov     r9d, edi
0x180035f2c  call    McTemplateU0zd_EventWriteTransfer
0x180035f31  mov     rcx, [rbp+58h]; this
0x180035f35  mov     r9d, edi; char *
0x180035f38  mov     r8, r13; unsigned int
0x180035f3b  mov     edx, ebx; void *
0x180035f3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035f42  lea     rcx, [rsp+150h+var_108]; this
0x180035f47  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180035f4c  lea     rcx, [rsp+150h+phkResult]; this
0x180035f51  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180035f56  jmp     loc_180035E5A
0x180035f5b  lea     rdx, aIuipolicycheck_0; "IUIPolicyChecked"
0x180035f62  lea     rcx, [rsp+150h+var_108]; this
0x180035f67  call    ?DeleteValue@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteValue(ushort const *)
0x180035f6c  mov     edi, eax
0x180035f6e  test    eax, eax
0x180035f70  jns     short loc_180035F86
0x180035f72  mov     rcx, [rbp+58h]; this
0x180035f76  mov     r9d, eax; char *
0x180035f79  mov     r8, r13; unsigned int
0x180035f7c  mov     edx, 7ABh; void *
0x180035f81  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035f86  mov     r9d, edi
0x180035f89  lea     r8, aIuipolicycheck_0; "IUIPolicyChecked"
0x180035f90  lea     rdx, aDeletevalueLs0; "DeleteValue %ls 0x%0x."
0x180035f97  mov     rcx, rbx; this
0x180035f9a  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035f9f  test    eax, eax
0x180035fa1  jns     short loc_180035FB7
0x180035fa3  mov     rcx, [rbp+58h]; this
0x180035fa7  mov     r9d, eax; char *
0x180035faa  mov     r8, r13; unsigned int
0x180035fad  mov     edx, 7ACh; void *
0x180035fb2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035fb7  xorps   xmm0, xmm0
0x180035fba  mov     [rbp+50h+var_C8], r12d
0x180035fbe  lea     r8, [rsp+150h+var_D8]; bool
0x180035fc3  xor     edx, edx; unsigned __int16 *
0x180035fc5  lea     rcx, ?applicationsConfigString@AppxAllUserStore@@3QBGB; "Config"
0x180035fcc  movups  xmmword ptr [rsp+150h+var_D8], xmm0
0x180035fd1  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x180035fd6  mov     edi, eax
0x180035fd8  mov     rcx, rbx; this
0x180035fdb  test    eax, eax
0x180035fdd  jns     short loc_180036028
0x180035fdf  mov     r8d, eax
0x180035fe2  lea     rdx, aGetconfigpathF; "GetConfigPath failed, 0x%0x."
0x180035fe9  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035fee  mov     ebx, 7B1h
0x180035ff3  test    eax, eax
0x180035ff5  jns     short loc_180036008
0x180035ff7  mov     rcx, [rbp+58h]; this
0x180035ffb  mov     r9d, eax; char *
0x180035ffe  mov     r8, r13; unsigned int
0x180036001  mov     edx, ebx; void *
0x180036003  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180036008  mov     rcx, [rbp+58h]; this
0x18003600c  mov     r9d, edi; char *
0x18003600f  mov     r8, r13; unsigned int
0x180036012  mov     edx, ebx; void *
0x180036014  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036019  lea     rcx, [rsp+150h+var_D8]; this
0x18003601e  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180036023  jmp     loc_180035F42
0x180036028  mov     r8, [rbp+50h+var_D8+8]
0x18003602c  lea     rdx, aCopyingSubtree; "Copying subtree %ls."
0x180036033  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180036038  test    eax, eax
0x18003603a  jns     short loc_180036050
0x18003603c  mov     rcx, [rbp+58h]; this
0x180036040  mov     r9d, eax; char *
0x180036043  mov     r8, r13; unsigned int
0x180036046  mov     edx, 7B3h; void *
  ... truncated ...
```
