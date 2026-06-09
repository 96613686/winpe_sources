# MpWatchDog::WdConfigManager::Initialize(void)

- ea: `0x14008eeb0`
- end: `0x14008f94d`
- name: `?Initialize@WdConfigManager@MpWatchDog@@AEAAJXZ`
- size: `2717`
- prototype: `__int64 __fastcall(MpWatchDog::WdConfigManager *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140092ee0`
- `0x14009301c`

## callees

- `0x140012088`
- `0x1400121a8`
- `0x1400122a4`
- `0x14001263c`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d210`
- `0x140085eb4`
- `0x140085fb0`
- `0x14008ea18`
- `0x14008eeb0`
- `0x14008f9a0`
- `0x14008ffb0`
- `0x14009139c`
- `0x1400915d0`
- `0x140091ad0`
- `0x1400927d0`
- `0x140092b74`
- `0x140092cd8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14008efd9`
- `ADVAPI32!RegCloseKey` at `0x14008f120`
- `ADVAPI32!RegCloseKey` at `0x14008f131`
- `ADVAPI32!RegCloseKey` at `0x14008f67b`
- `ADVAPI32!RegCloseKey` at `0x14008f759`
- `ADVAPI32!RegCloseKey` at `0x14008f907`
- `ADVAPI32!RegCloseKey` at `0x14008f918`
- `ADVAPI32!RegCloseKey` at `0x14008efd9`
- `ADVAPI32!RegCloseKey` at `0x14008f120`
- `ADVAPI32!RegCloseKey` at `0x14008f131`
- `ADVAPI32!RegCloseKey` at `0x14008f67b`
- `ADVAPI32!RegCloseKey` at `0x14008f759`
- `ADVAPI32!RegCloseKey` at `0x14008f907`
- `ADVAPI32!RegCloseKey` at `0x14008f918`

## string_xrefs

- `0x14008f077`: `ProductAppDataPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall MpWatchDog::WdConfigManager::Initialize(MpWatchDog::WdConfigManager *this)
{
  unsigned int v2; // r15d
  struct MpWatchDog::WdSensorConfig *v3; // r12
  __int64 v4; // rcx
  int v5; // eax
  int ValueString; // r15d
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v10; // eax
  int v11; // eax
  const struct std::nothrow_t *v12; // rdx
  void **v13; // r15
  unsigned int *v14; // r9
  unsigned int v15; // r12d
  int ValueDword; // eax
  unsigned int *v17; // r9
  int v18; // eax
  unsigned int *v19; // r9
  int v20; // eax
  unsigned int *v21; // r9
  int v22; // eax
  unsigned int *v23; // r9
  int v24; // eax
  unsigned int *v25; // r9
  int v26; // ecx
  unsigned int *v27; // r9
  int v28; // ecx
  int v29; // eax
  const struct std::nothrow_t *v30; // rdx
  void **v31; // r12
  unsigned int ValueStringWithMiscConfigOverride; // eax
  __int64 v33; // rdx
  void **v34; // r12
  unsigned int v35; // eax
  int v36; // eax
  unsigned __int64 *v37; // r9
  int v38; // eax
  const struct std::nothrow_t *v39; // rdx
  unsigned int ValueULongLongFromBinary; // eax
  int ValueDwordWithMiscConfigOverride; // eax
  bool v42; // al
  const char *v43; // r9
  unsigned int v44; // esi
  unsigned int *v45; // r14
  unsigned int *v47; // [rsp+40h] [rbp-78h]
  wchar_t v48[2]; // [rsp+50h] [rbp-68h] BYREF
  HKEY v49; // [rsp+58h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-58h] BYREF
  HKEY v51; // [rsp+68h] [rbp-50h] BYREF
  void *Src; // [rsp+70h] [rbp-48h] BYREF
  wchar_t v53[4]; // [rsp+78h] [rbp-40h] BYREF

  v2 = 0;
  v3 = (MpWatchDog::WdConfigManager *)((char *)this + 32);
  v47 = (unsigned int *)((char *)this + 32);
  v4 = WPP_GLOBAL_Control;
  do
  {
    if ( (_UNKNOWN *)v4 != &WPP_GLOBAL_Control && (*(_BYTE *)(v4 + 28) & 4) != 0 )
      WPP_SF_d(*(_QWORD *)(v4 + 16), 10, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, v2);
    v5 = MpWatchDog::WdSensorConfig::PopulateMonitoredTargets(v3, 0);
    if ( v5 >= 0 )
      goto LABEL_9;
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_Dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, v2, v5);
LABEL_9:
      v4 = WPP_GLOBAL_Control;
    }
    ++v2;
    v3 = (struct MpWatchDog::WdSensorConfig *)((char *)v3 + 32);
  }
  while ( v2 < 5 );
  *(_DWORD *)v48 = 0;
  hKey = 0;
  ValueString = CommonUtil::UtilRegOpenKey(
                  (CommonUtil *)&hKey,
                  (HKEY *)0xFFFFFFFF80000002LL,
                  (const WCHAR *)&stru_140194720,
                  (const wchar_t *)1);
  if ( ValueString < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = 76;
      goto LABEL_15;
    }
    goto LABEL_16;
  }
  v10 = MpWatchDog::WdConfigManager::PopulateKillbitGatedFeatures(this, hKey);
  if ( v10 < 0
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      77,
      &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
      (unsigned int)v10);
  }
  v11 = MpWatchDog::WdConfigManager::PopulateCampConfigurations(this, (HKEY *)hKey);
  if ( v11 < 0
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      78,
      &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
      (unsigned int)v11);
  }
  v13 = (void **)((char *)this + 840);
  if ( *((_QWORD *)this + 105) )
  {
    operator delete(*v13, v12);
    *v13 = 0;
  }
  ValueString = CommonUtil::UtilRegGetValueString(hKey, L"ProductAppDataPath", (char *)this + 840, 0, 0);
  if ( ValueString >= 0 )
  {
    v49 = 0;
    v15 = CommonUtil::UtilRegOpenKey(
            (CommonUtil *)&v49,
            (HKEY *)hKey,
            (const WCHAR *)&stru_140196060,
            (const wchar_t *)1);
    if ( (int)(v15 + 0x80000000) < 0 || v15 == -2147024894 )
    {
      ValueDword = CommonUtil::UtilRegGetValueDword((CommonUtil *)v49, (HKEY)&stru_140196550, v48, v14);
      if ( ValueDword < 0 )
      {
        if ( ValueDword != -2147024894
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_Dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            82,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *(unsigned int *)this,
            ValueDword);
        }
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)this, *(__int32 *)v48);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            81,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *(unsigned int *)this);
      }
      v18 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v49, (HKEY)&stru_140196578, v48, v17);
      if ( v18 < 0 )
      {
        if ( v18 != -2147024894
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_Dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            84,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *((unsigned int *)this + 1),
            v18);
        }
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)this + 1, *(__int32 *)v48);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            83,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *((unsigned int *)this + 1));
      }
      v20 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v49, (HKEY)&stru_1401965A8, v48, v19);
      if ( v20 < 0 )
      {
        if ( v20 != -2147024894
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_Dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            86,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *((unsigned int *)this + 4),
            v20);
        }
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)this + 4, 3600000 * *(_DWORD *)v48);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            85,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *(unsigned int *)v48);
      }
      v22 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v49, (HKEY)&stru_1401965D8, v48, v21);
      if ( v22 < 0 )
      {
        if ( v22 != -2147024894
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_Dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            88,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *((unsigned int *)this + 6),
            v22);
        }
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)this + 6, *(__int32 *)v48);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            87,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *(unsigned int *)v48);
      }
      v24 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v49, (HKEY)&stru_1401965F8, v48, v23);
      if ( v24 < 0 )
      {
        if ( v24 != -2147024894
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_Dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            90,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *((unsigned int *)this + 2),
            v24);
        }
      }
      else
      {
        _InterlockedExchange((volatile __int32 *)this + 2, *(__int32 *)v48);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            89,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *((unsigned int *)this + 2));
      }
      v26 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v49, (HKEY)&stru_140196620, v48, v25);
      if ( v26 < 0 )
      {
        if ( v26 != -2147024894
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_Dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            92,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *((unsigned __int8 *)this + 12),
            v26);
        }
      }
      else
      {
        *((_BYTE *)this + 12) = *(_DWORD *)v48 != 0;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            91,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *((unsigned __int8 *)this + 12));
      }
      *((_BYTE *)this + 13) = MpWatchDog::WdConfigManager::IsKillbitGatedFeatureEnabled_Unsafe(this, 194);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          93,
          &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
          *((unsigned __int8 *)this + 13));
      v28 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v49, (HKEY)&stru_140196650, v48, v27);
      if ( v28 < 0 )
      {
        if ( v28 != -2147024894
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_Dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            95,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *((unsigned __int8 *)this + 20),
            v28);
        }
      }
      else
      {
        *((_BYTE *)this + 20) = *(_DWORD *)v48 != 0;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            94,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            *((unsigned __int8 *)this + 20));
      }
      v29 = MpWatchDog::WdConfigManager::PopulateOneDsConfigurations(this, v49, hKey);
      if ( v29 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          96,
          &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
          (unsigned int)v29);
      }
      v31 = (void **)((char *)this + 832);
      if ( *((_QWORD *)this + 104) )
      {
        operator delete(*v31, v30);
        *v31 = 0;
      }
      ValueStringWithMiscConfigOverride = MpWatchDog::UtilRegGetValueStringWithMiscConfigOverride(
                                            v49,
                                            v49,
                                            L"MdTrustedRootCertThumbPrints",
                                            (char *)this + 832);
      v33 = 0x80000000LL;
      if ( (int)(ValueStringWithMiscConfigOverride + 0x80000000) >= 0
        && ValueStringWithMiscConfigOverride != -2147024894
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          97,
          &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
          ValueStringWithMiscConfigOverride);
      }
      v34 = (void **)((char *)this + 824);
      if ( *((_QWORD *)this + 103) )
      {
        operator delete(*v34, (const struct std::nothrow_t *)v33);
        *v34 = 0;
      }
      v35 = MpWatchDog::UtilRegGetValueStringWithMiscConfigOverride(
              v49,
              v49,
              L"MdTrustedSubjectOrgs",
              (char *)this + 824);
      if ( (int)(v35 + 0x80000000) >= 0
        && v35 != -2147024894
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 98, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, v35);
      }
      v51 = 0;
      std::wstring::operator=((char *)this + 256, (void *)&::Src);
      if ( v51 )
      {
        RegCloseKey(v51);
        v51 = 0;
      }
      v36 = CommonUtil::UtilRegOpenKey(
              (CommonUtil *)&v51,
              (HKEY *)0xFFFFFFFF80000002LL,
              (const WCHAR *)&stru_140196700,
              (const wchar_t *)1);
      if ( v36 >= 0 )
      {
        Src = 0;
        v38 = CommonUtil::UtilRegGetValueString(v51, &stru_140196780, &Src, 0, 0);
        if ( v38 < 0 )
        {
          if ( v38 != -2147024894
            && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              100,
              &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
              (unsigned int)v38);
          }
        }
        else
        {
          std::wstring::operator=((char *)this + 256, Src);
        }
        if ( Src )
          operator delete(Src, v39);
      }
      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          99,
          &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
          (unsigned int)v36);
      }
      if ( v51 )
        RegCloseKey(v51);
      *(_QWORD *)v53 = 0;
      ValueULongLongFromBinary = CommonUtil::UtilRegGetValueULongLongFromBinary(
                                   (CommonUtil *)v49,
                                   (HKEY)&stru_140196788,
                                   v53,
                                   v37);
      if ( ((ValueULongLongFromBinary + 0x80000000) & 0x80000000) == 0
        && ValueULongLongFromBinary != -2147024894
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          102,
          &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
          ValueULongLongFromBinary);
      }
      *((_QWORD *)this + 31) = *(_QWORD *)v53;
      *((_BYTE *)this + 28) = 0;
      ValueDwordWithMiscConfigOverride = MpWatchDog::UtilRegGetValueDwordWithMiscConfigOverride(
                                           (CommonUtil *)v49,
                                           (HKEY *)hKey,
                                           (HKEY)&stru_1401967B8,
                                           v48);
      if ( ValueDwordWithMiscConfigOverride < 0 )
      {
        if ( ValueDwordWithMiscConfigOverride != -2147024894
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            104,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            (unsigned int)ValueDwordWithMiscConfigOverride);
        }
      }
      else
      {
        v42 = *(_DWORD *)v48 != 0;
        *((_BYTE *)this + 28) = *(_DWORD *)v48 != 0;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v43 = "enabled";
          if ( !v42 )
            v43 = "disabled";
          WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 103, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, v43);
        }
      }
      v44 = 0;
      v45 = v47;
      do
      {
        *v45 = v44;
        MpWatchDog::WdConfigManager::ReadAndUpdateSensorConfig(this, hKey, v44++);
        v45 += 8;
      }
      while ( v44 < 5 );
      if ( v49 )
        RegCloseKey(v49);
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 80, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, v15);
      if ( v49 )
        RegCloseKey(v49);
      if ( hKey )
        RegCloseKey(hKey);
      return v15;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = 79;
LABEL_15:
      WPP_SF_d(*(_QWORD *)(v7 + 16), v8, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, (unsigned int)ValueString);
    }
LABEL_16:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)ValueString;
  }
}

```

## disassembly

```asm
0x14008eeb0  mov     [rsp+arg_8], rbx
0x14008eeb5  mov     [rsp+arg_10], rsi
0x14008eeba  push    rdi
0x14008eebb  push    r12
0x14008eebd  push    r13
0x14008eebf  push    r14
0x14008eec1  push    r15
0x14008eec3  sub     rsp, 90h
0x14008eeca  mov     rax, cs:__security_cookie
0x14008eed1  xor     rax, rsp
0x14008eed4  mov     [rsp+0B8h+var_38], rax
0x14008eedc  mov     rdi, rcx
0x14008eedf  mov     [rsp+0B8h+var_88], rcx
0x14008eee4  mov     [rsp+0B8h+var_80], rcx
0x14008eee9  xor     ebx, ebx
0x14008eeeb  mov     r15d, ebx
0x14008eeee  lea     r12, [rcx+20h]
0x14008eef2  mov     [rsp+0B8h+var_78], r12
0x14008eef7  lea     rsi, WPP_GLOBAL_Control
0x14008eefe  lea     r14, WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids
0x14008ef05  mov     r13b, 2
0x14008ef08  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ef0f  cmp     rcx, rsi
0x14008ef12  jz      short loc_14008EF2E
0x14008ef14  test    byte ptr [rcx+1Ch], 4
0x14008ef18  jz      short loc_14008EF2E
0x14008ef1a  mov     edx, 0Ah
0x14008ef1f  mov     r9d, r15d
0x14008ef22  mov     r8, r14
0x14008ef25  mov     rcx, [rcx+10h]
0x14008ef29  call    WPP_SF_d
0x14008ef2e  xor     edx, edx; wchar_t *
0x14008ef30  mov     rcx, r12; struct MpWatchDog::WdSensorConfig *
0x14008ef33  call    ?PopulateMonitoredTargets@WdSensorConfig@MpWatchDog@@SAJPEAV12@PEB_W@Z; MpWatchDog::WdSensorConfig::PopulateMonitoredTargets(MpWatchDog::WdSensorConfig *,wchar_t const *)
0x14008ef38  test    eax, eax
0x14008ef3a  jns     short loc_14008EF66
0x14008ef3c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ef43  cmp     rcx, rsi
0x14008ef46  jz      short loc_14008EF6D
0x14008ef48  test    [rcx+1Ch], r13b
0x14008ef4c  jz      short loc_14008EF6D
0x14008ef4e  mov     edx, 0Bh
0x14008ef53  mov     [rsp+0B8h+var_98], eax; unsigned int
0x14008ef57  mov     r9d, r15d
0x14008ef5a  mov     r8, r14
0x14008ef5d  mov     rcx, [rcx+10h]
0x14008ef61  call    WPP_SF_Dd
0x14008ef66  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ef6d  inc     r15d
0x14008ef70  add     r12, 20h ; ' '
0x14008ef74  cmp     r15d, 5
0x14008ef78  jb      short loc_14008EF0F
0x14008ef7a  mov     dword ptr [rsp+0B8h+var_68], ebx
0x14008ef7e  mov     [rsp+0B8h+hKey], rbx
0x14008ef83  mov     r9d, 1; wchar_t *
0x14008ef89  lea     r8, stru_140194720; HKEY
0x14008ef90  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x14008ef97  lea     rcx, [rsp+0B8h+hKey]; this
0x14008ef9c  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x14008efa1  mov     r15d, eax
0x14008efa4  test    eax, eax
0x14008efa6  jns     short loc_14008EFE7
0x14008efa8  mov     rcx, cs:WPP_GLOBAL_Control
0x14008efaf  cmp     rcx, rsi
0x14008efb2  jz      short loc_14008EFCF
0x14008efb4  test    byte ptr [rcx+1Ch], 1
0x14008efb8  jz      short loc_14008EFCF
0x14008efba  mov     edx, 4Ch ; 'L'
0x14008efbf  mov     r9d, r15d
0x14008efc2  mov     r8, r14
0x14008efc5  mov     rcx, [rcx+10h]
0x14008efc9  call    WPP_SF_d
0x14008efce  nop
0x14008efcf  mov     rcx, [rsp+0B8h+hKey]; hKey
0x14008efd4  test    rcx, rcx
0x14008efd7  jz      short loc_14008EFDF
0x14008efd9  call    cs:__imp_RegCloseKey
0x14008efdf  mov     eax, r15d
0x14008efe2  jmp     loc_14008F920
0x14008efe7  mov     rdx, [rsp+0B8h+hKey]; HKEY
0x14008efec  mov     rcx, rdi; this
0x14008efef  call    ?PopulateKillbitGatedFeatures@WdConfigManager@MpWatchDog@@AEAAJPEAUHKEY__@@@Z; MpWatchDog::WdConfigManager::PopulateKillbitGatedFeatures(HKEY__ *)
0x14008eff4  test    eax, eax
0x14008eff6  jns     short loc_14008F01E
0x14008eff8  mov     rcx, cs:WPP_GLOBAL_Control
0x14008efff  cmp     rcx, rsi
0x14008f002  jz      short loc_14008F01E
0x14008f004  test    [rcx+1Ch], r13b
0x14008f008  jz      short loc_14008F01E
0x14008f00a  mov     edx, 4Dh ; 'M'
0x14008f00f  mov     r9d, eax
0x14008f012  mov     r8, r14
0x14008f015  mov     rcx, [rcx+10h]
0x14008f019  call    WPP_SF_d
0x14008f01e  mov     rdx, [rsp+0B8h+hKey]; HKEY
0x14008f023  mov     rcx, rdi; this
0x14008f026  call    ?PopulateCampConfigurations@WdConfigManager@MpWatchDog@@AEAAJPEAUHKEY__@@@Z; MpWatchDog::WdConfigManager::PopulateCampConfigurations(HKEY__ *)
0x14008f02b  test    eax, eax
0x14008f02d  jns     short loc_14008F055
0x14008f02f  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f036  cmp     rcx, rsi
0x14008f039  jz      short loc_14008F055
0x14008f03b  test    [rcx+1Ch], r13b
0x14008f03f  jz      short loc_14008F055
0x14008f041  mov     edx, 4Eh ; 'N'
0x14008f046  mov     r9d, eax
0x14008f049  mov     r8, r14
0x14008f04c  mov     rcx, [rcx+10h]
0x14008f050  call    WPP_SF_d
0x14008f055  lea     r15, [rdi+348h]
0x14008f05c  cmp     [r15], rbx
0x14008f05f  jz      short loc_14008F06C
0x14008f061  mov     rcx, [r15]; void *
0x14008f064  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008f069  mov     [r15], rbx
0x14008f06c  mov     qword ptr [rsp+0B8h+var_98], rbx; unsigned int
0x14008f071  xor     r9d, r9d
0x14008f074  mov     r8, r15
0x14008f077  lea     rdx, aProductappdata; "ProductAppDataPath"
0x14008f07e  mov     rcx, [rsp+0B8h+hKey]
0x14008f083  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x14008f088  mov     r15d, eax
0x14008f08b  test    eax, eax
0x14008f08d  jns     short loc_14008F0B3
0x14008f08f  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f096  cmp     rcx, rsi
0x14008f099  jz      loc_14008EFCF
0x14008f09f  test    byte ptr [rcx+1Ch], 1
0x14008f0a3  jz      loc_14008EFCF
0x14008f0a9  mov     edx, 4Fh ; 'O'
0x14008f0ae  jmp     loc_14008EFBF
0x14008f0b3  mov     [rsp+0B8h+var_60], rbx
0x14008f0b8  mov     r9d, 1; wchar_t *
0x14008f0be  lea     r8, stru_140196060; HKEY
0x14008f0c5  mov     rdx, [rsp+0B8h+hKey]; HKEY *
0x14008f0ca  lea     rcx, [rsp+0B8h+var_60]; this
0x14008f0cf  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x14008f0d4  mov     r12d, eax
0x14008f0d7  mov     eax, 80000000h
0x14008f0dc  lea     ecx, [r12+rax]
0x14008f0e0  mov     r15d, 80070002h
0x14008f0e6  test    eax, ecx
0x14008f0e8  jnz     short loc_14008F13F
0x14008f0ea  cmp     r12d, r15d
0x14008f0ed  jz      short loc_14008F13F
0x14008f0ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f0f6  cmp     rcx, rsi
0x14008f0f9  jz      short loc_14008F116
0x14008f0fb  test    byte ptr [rcx+1Ch], 1
0x14008f0ff  jz      short loc_14008F116
0x14008f101  mov     edx, 50h ; 'P'
0x14008f106  mov     r9d, r12d
0x14008f109  mov     r8, r14
0x14008f10c  mov     rcx, [rcx+10h]
0x14008f110  call    WPP_SF_d
0x14008f115  nop
0x14008f116  mov     rcx, [rsp+0B8h+var_60]; hKey
0x14008f11b  test    rcx, rcx
0x14008f11e  jz      short loc_14008F127
0x14008f120  call    cs:__imp_RegCloseKey
0x14008f126  nop
0x14008f127  mov     rcx, [rsp+0B8h+hKey]; hKey
0x14008f12c  test    rcx, rcx
0x14008f12f  jz      short loc_14008F137
0x14008f131  call    cs:__imp_RegCloseKey
0x14008f137  mov     eax, r12d
0x14008f13a  jmp     loc_14008F920
0x14008f13f  lea     r8, [rsp+0B8h+var_68]; wchar_t *
0x14008f144  lea     rdx, stru_140196550; HKEY
0x14008f14b  mov     rcx, [rsp+0B8h+var_60]; this
0x14008f150  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)
0x14008f155  test    eax, eax
0x14008f157  js      short loc_14008F18F
0x14008f159  mov     eax, dword ptr [rsp+0B8h+var_68]
0x14008f15d  xchg    eax, [rdi]
0x14008f15f  mov     rax, cs:WPP_GLOBAL_Control
0x14008f166  cmp     rax, rsi
0x14008f169  jz      short loc_14008F1C6
0x14008f16b  test    byte ptr [rax+1Ch], 4
0x14008f16f  jz      short loc_14008F1C6
0x14008f171  mov     r9d, [rdi]
0x14008f174  nop
0x14008f175  mov     edx, 51h ; 'Q'
0x14008f17a  mov     r8, r14
0x14008f17d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f184  mov     rcx, [rcx+10h]
0x14008f188  call    WPP_SF_d
0x14008f18d  jmp     short loc_14008F1C6
0x14008f18f  cmp     eax, r15d
0x14008f192  jz      short loc_14008F1C6
0x14008f194  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f19b  cmp     rcx, rsi
0x14008f19e  jz      short loc_14008F1C6
0x14008f1a0  test    [rcx+1Ch], r13b
0x14008f1a4  jz      short loc_14008F1C6
0x14008f1a6  mov     r9d, [rdi]
0x14008f1a9  nop
0x14008f1aa  mov     edx, 52h ; 'R'
0x14008f1af  mov     [rsp+0B8h+var_98], eax
0x14008f1b3  mov     r8, r14
0x14008f1b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f1bd  mov     rcx, [rcx+10h]
0x14008f1c1  call    WPP_SF_Dd
0x14008f1c6  lea     r8, [rsp+0B8h+var_68]; wchar_t *
0x14008f1cb  lea     rdx, stru_140196578; HKEY
0x14008f1d2  mov     rcx, [rsp+0B8h+var_60]; this
0x14008f1d7  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)
0x14008f1dc  test    eax, eax
0x14008f1de  js      short loc_14008F218
0x14008f1e0  mov     eax, dword ptr [rsp+0B8h+var_68]
0x14008f1e4  xchg    eax, [rdi+4]
0x14008f1e7  mov     rax, cs:WPP_GLOBAL_Control
0x14008f1ee  cmp     rax, rsi
0x14008f1f1  jz      short loc_14008F250
0x14008f1f3  test    byte ptr [rax+1Ch], 4
0x14008f1f7  jz      short loc_14008F250
0x14008f1f9  mov     r9d, [rdi+4]
0x14008f1fd  nop
0x14008f1fe  mov     edx, 53h ; 'S'
0x14008f203  mov     r8, r14
0x14008f206  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f20d  mov     rcx, [rcx+10h]
0x14008f211  call    WPP_SF_d
0x14008f216  jmp     short loc_14008F250
0x14008f218  cmp     eax, r15d
0x14008f21b  jz      short loc_14008F250
0x14008f21d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f224  cmp     rcx, rsi
0x14008f227  jz      short loc_14008F250
0x14008f229  test    [rcx+1Ch], r13b
0x14008f22d  jz      short loc_14008F250
0x14008f22f  mov     r9d, [rdi+4]
0x14008f233  nop
0x14008f234  mov     edx, 54h ; 'T'
0x14008f239  mov     [rsp+0B8h+var_98], eax
0x14008f23d  mov     r8, r14
0x14008f240  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f247  mov     rcx, [rcx+10h]
0x14008f24b  call    WPP_SF_Dd
0x14008f250  lea     r8, [rsp+0B8h+var_68]; wchar_t *
0x14008f255  lea     rdx, stru_1401965A8; HKEY
0x14008f25c  mov     rcx, [rsp+0B8h+var_60]; this
0x14008f261  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)
0x14008f266  test    eax, eax
0x14008f268  js      short loc_14008F29F
0x14008f26a  imul    eax, dword ptr [rsp+0B8h+var_68], 36EE80h
0x14008f272  xchg    eax, [rdi+10h]
0x14008f275  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f27c  cmp     rcx, rsi
0x14008f27f  jz      short loc_14008F2D7
0x14008f281  test    byte ptr [rcx+1Ch], 4
0x14008f285  jz      short loc_14008F2D7
0x14008f287  mov     edx, 55h ; 'U'
0x14008f28c  mov     r9d, dword ptr [rsp+0B8h+var_68]
0x14008f291  mov     r8, r14
0x14008f294  mov     rcx, [rcx+10h]
0x14008f298  call    WPP_SF_d
0x14008f29d  jmp     short loc_14008F2D7
0x14008f29f  cmp     eax, r15d
0x14008f2a2  jz      short loc_14008F2D7
0x14008f2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f2ab  cmp     rcx, rsi
0x14008f2ae  jz      short loc_14008F2D7
0x14008f2b0  test    [rcx+1Ch], r13b
0x14008f2b4  jz      short loc_14008F2D7
0x14008f2b6  mov     r9d, [rdi+10h]
0x14008f2ba  nop
0x14008f2bb  mov     edx, 56h ; 'V'
0x14008f2c0  mov     [rsp+0B8h+var_98], eax
0x14008f2c4  mov     r8, r14
0x14008f2c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f2ce  mov     rcx, [rcx+10h]
0x14008f2d2  call    WPP_SF_Dd
0x14008f2d7  lea     r8, [rsp+0B8h+var_68]; wchar_t *
0x14008f2dc  lea     rdx, stru_1401965D8; HKEY
0x14008f2e3  mov     rcx, [rsp+0B8h+var_60]; this
0x14008f2e8  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)
0x14008f2ed  test    eax, eax
0x14008f2ef  js      short loc_14008F322
0x14008f2f1  mov     eax, dword ptr [rsp+0B8h+var_68]
0x14008f2f5  xchg    eax, [rdi+18h]
0x14008f2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f2ff  cmp     rcx, rsi
0x14008f302  jz      short loc_14008F35A
0x14008f304  test    byte ptr [rcx+1Ch], 4
0x14008f308  jz      short loc_14008F35A
0x14008f30a  mov     edx, 57h ; 'W'
0x14008f30f  mov     r9d, dword ptr [rsp+0B8h+var_68]
0x14008f314  mov     r8, r14
0x14008f317  mov     rcx, [rcx+10h]
0x14008f31b  call    WPP_SF_d
0x14008f320  jmp     short loc_14008F35A
0x14008f322  cmp     eax, r15d
0x14008f325  jz      short loc_14008F35A
0x14008f327  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f32e  cmp     rcx, rsi
0x14008f331  jz      short loc_14008F35A
0x14008f333  test    [rcx+1Ch], r13b
0x14008f337  jz      short loc_14008F35A
0x14008f339  mov     r9d, [rdi+18h]
  ... truncated ...
```
