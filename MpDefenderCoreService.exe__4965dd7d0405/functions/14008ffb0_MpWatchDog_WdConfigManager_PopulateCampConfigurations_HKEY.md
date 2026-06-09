# MpWatchDog::WdConfigManager::PopulateCampConfigurations(HKEY__ *)

- ea: `0x14008ffb0`
- end: `0x140091017`
- name: `?PopulateCampConfigurations@WdConfigManager@MpWatchDog@@AEAAJPEAUHKEY__@@@Z`
- size: `4199`
- prototype: `int(MpWatchDog::WdConfigManager *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14008eeb0`

## callees

- `0x14000d758`
- `0x14000d93c`
- `0x140012088`
- `0x1400121a8`
- `0x14001263c`
- `0x140014ac8`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d1e0`
- `0x14007d210`
- `0x140083458`
- `0x14008371c`
- `0x140083d14`
- `0x140084a8c`
- `0x140084b00`
- `0x140085d38`
- `0x140085d94`
- `0x14008d1fc`
- `0x14008dcc0`
- `0x14008e9a8`
- `0x14008ea18`
- `0x14008fa7c`
- `0x14008fd14`
- `0x14008ffb0`
- `0x140091034`
- `0x140092ad4`
- `0x140092b74`
- `0x140092cd8`
- `0x1400b77f8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140090075`
- `ADVAPI32!RegCloseKey` at `0x1400900c3`
- `ADVAPI32!RegCloseKey` at `0x1400907e5`
- `ADVAPI32!RegCloseKey` at `0x140090803`
- `ADVAPI32!RegCloseKey` at `0x140090f65`
- `ADVAPI32!RegCloseKey` at `0x140090f79`
- `ADVAPI32!RegCloseKey` at `0x140090fa0`
- `ADVAPI32!RegCloseKey` at `0x140090fc7`
- `ADVAPI32!RegCloseKey` at `0x140090fdb`
- `ADVAPI32!RegCloseKey` at `0x140090075`
- `ADVAPI32!RegCloseKey` at `0x1400900c3`
- `ADVAPI32!RegCloseKey` at `0x1400907e5`
- `ADVAPI32!RegCloseKey` at `0x140090803`
- `ADVAPI32!RegCloseKey` at `0x140090f65`
- `ADVAPI32!RegCloseKey` at `0x140090f79`
- `ADVAPI32!RegCloseKey` at `0x140090fa0`
- `ADVAPI32!RegCloseKey` at `0x140090fc7`
- `ADVAPI32!RegCloseKey` at `0x140090fdb`

## string_xrefs

- `0x1400903e3`: `InstallLocation`
- `0x140090528`: `\MpSvc.dll`
- `0x140090d56`: `CachedProxy`
- `0x140090de7`: `CachedProxyBypass`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall MpWatchDog::WdConfigManager::PopulateCampConfigurations(MpWatchDog::WdConfigManager *this, HKEY *a2)
{
  HKEY v2; // r14
  MpWatchDog::WdConfigManager *v3; // rdi
  char *v4; // r13
  unsigned int *v5; // r9
  bool v6; // si
  __int64 v7; // r12
  int v8; // eax
  unsigned int *v9; // r9
  int v10; // r15d
  int ValueDword; // eax
  unsigned int *v12; // r9
  int v13; // ecx
  int v14; // eax
  unsigned int *v15; // r9
  int v16; // ecx
  int ValueString; // r15d
  __int64 v18; // rcx
  __int64 v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  int v21; // r15d
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int64 v24; // r13
  char *v25; // r9
  __int64 v26; // rax
  __int64 v27; // rax
  char *v28; // rcx
  __int16 v29; // dx
  unsigned __int64 v30; // r8
  __int64 v31; // rcx
  const wchar_t *v32; // r8
  unsigned __int64 *v33; // rdx
  unsigned __int64 **v34; // r9
  __int64 v35; // rcx
  int ModuleFileName; // eax
  const struct std::nothrow_t *v37; // rdx
  const wchar_t *v38; // r8
  __int64 v39; // rcx
  __int64 v40; // rdx
  bool v41; // sf
  unsigned int *v42; // r9
  int v43; // eax
  int v44; // eax
  int v45; // eax
  unsigned int *v46; // r9
  HKEY v47; // rcx
  int v48; // eax
  BOOL v49; // r15d
  unsigned int *v50; // r9
  int v51; // eax
  int v52; // ecx
  int v53; // eax
  int v54; // ecx
  int v55; // eax
  int v56; // eax
  unsigned int *v57; // r9
  __int64 v58; // rcx
  __int64 v59; // rdx
  int v60; // r15d
  int v61; // eax
  const struct std::nothrow_t *v62; // rdx
  __int64 v63; // r10
  int v64; // eax
  _QWORD *v65; // r15
  const struct std::nothrow_t *v66; // rdx
  int v67; // eax
  wchar_t *v68; // rdx
  const struct std::nothrow_t *v69; // rdx
  _DWORD **v70; // rdi
  const struct std::nothrow_t *v71; // rdx
  __int64 result; // rax
  __int64 v73; // [rsp+0h] [rbp-1A8h] BYREF
  MpWatchDog::WdConfigManager *v74; // [rsp+40h] [rbp-168h]
  HKEY *v75; // [rsp+48h] [rbp-160h]
  MpWatchDog::WdConfigManager *v76; // [rsp+50h] [rbp-158h]
  MpWatchDog::WdConfigManager *v77; // [rsp+58h] [rbp-150h]
  __int128 v78; // [rsp+60h] [rbp-148h] BYREF
  __m128i si128; // [rsp+70h] [rbp-138h]
  __int128 v80; // [rsp+80h] [rbp-128h] BYREF
  __m128i v81; // [rsp+90h] [rbp-118h]
  MpWatchDog *v82; // [rsp+A0h] [rbp-108h]
  MpWatchDog::WdConfigManager *v83; // [rsp+A8h] [rbp-100h]
  const std::exception *v84; // [rsp+B0h] [rbp-F8h] BYREF
  wchar_t v85[4]; // [rsp+D0h] [rbp-D8h] BYREF
  wchar_t v86[4]; // [rsp+D8h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp-C8h] BYREF
  char *v88; // [rsp+E8h] [rbp-C0h] BYREF
  HKEY v89; // [rsp+F0h] [rbp-B8h] BYREF
  HKEY v90; // [rsp+F8h] [rbp-B0h] BYREF
  void *v91; // [rsp+100h] [rbp-A8h] BYREF
  HKEY v92; // [rsp+108h] [rbp-A0h] BYREF
  HKEY v93; // [rsp+110h] [rbp-98h] BYREF
  HKEY v94; // [rsp+118h] [rbp-90h] BYREF
  void *v95; // [rsp+120h] [rbp-88h] BYREF
  unsigned __int64 *v96; // [rsp+130h] [rbp-78h] BYREF
  _QWORD v97[2]; // [rsp+138h] [rbp-70h] BYREF
  unsigned __int64 v98; // [rsp+148h] [rbp-60h]
  __int64 v99; // [rsp+150h] [rbp-58h]
  char *v100; // [rsp+158h] [rbp-50h]
  __int64 v101; // [rsp+160h] [rbp-48h]
  char *v102; // [rsp+168h] [rbp-40h]

  v2 = (HKEY)a2;
  v3 = this;
  v83 = this;
  v76 = this;
  v74 = this;
  v77 = this;
  v75 = a2;
  *(_DWORD *)v85 = 0;
  v4 = (char *)this + 192;
  *((_BYTE *)this + 288) = 0;
  hKey = 0;
  *(_DWORD *)v86 = 0;
  if ( (int)CommonUtil::UtilRegOpenKey((CommonUtil *)&hKey, a2, (const WCHAR *)&stru_140196060, (const wchar_t *)1) < 0
    || (int)CommonUtil::UtilRegGetValueDword((CommonUtil *)hKey, (HKEY)&stru_140196080, v86, v5) < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    v6 = *(_DWORD *)v86 == 1;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v6 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids);
      *((_BYTE *)v3 + 288) = 0;
      goto LABEL_14;
    }
  }
  if ( (int)MpWatchDog::ReadFeatureControlWithMiscConfigOverride(v2, 21, v85) >= 0 )
    *((_BYTE *)v3 + 288) = *(_DWORD *)v85 != 0;
LABEL_14:
  v7 = 4;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      26,
      &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
      *((unsigned __int8 *)v3 + 288));
  if ( !*((_BYTE *)v3 + 288) )
    MpWatchDog::MpCoreSvcDiagnostics::ModifyCoreServiceStatusBitfield(4u, MpWatchDog::ClearBitsFunc, L"Clear");
  v90 = 0;
  v8 = CommonUtil::UtilRegOpenKey((CommonUtil *)&v90, (HKEY *)v2, (const WCHAR *)&stru_140196240, (const wchar_t *)1);
  if ( v8 >= 0 )
  {
    ValueDword = CommonUtil::UtilRegGetValueDword((CommonUtil *)v90, (HKEY)&stru_140196258, v85, v9);
    v10 = 5;
    v13 = 5;
    if ( ValueDword >= 0 )
      v13 = *(_DWORD *)v85;
    *((_DWORD *)v3 + 54) = v13;
    v14 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v90, (HKEY)&stru_140196278, v85, v12);
    v16 = 5;
    if ( v14 >= 0 )
      v16 = *(_DWORD *)v85;
    *((_DWORD *)v3 + 55) = v16;
    if ( (int)CommonUtil::UtilRegGetValueDword((CommonUtil *)v90, (HKEY)&stru_140196290, v85, v15) >= 0 )
      v10 = *(_DWORD *)v85;
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        27,
        &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
        (unsigned int)v8);
    v10 = 5;
    *((_DWORD *)v3 + 54) = 5;
    *((_DWORD *)v3 + 55) = 5;
  }
  *((_DWORD *)v4 + 8) = v10;
  v92 = 0;
  *(_QWORD *)v4 = 0;
  if ( (int)CommonUtil::UtilRegOpenKey(
              (CommonUtil *)&v92,
              (HKEY *)v2,
              (const WCHAR *)&stru_1401962B0,
              (const wchar_t *)1) >= 0 )
  {
    *(_QWORD *)v86 = 0;
    ValueString = CommonUtil::UtilRegGetValueString(v92, L"EngineVersion", v86, 0, 0);
    if ( ValueString >= 0 )
    {
      if ( (int)MpWatchDog::UtilConvertToLongLongVersion(v4, *(_QWORD *)v86) < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v19 = 29;
          goto LABEL_39;
        }
      }
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        v19 = 28;
LABEL_39:
        WPP_SF_d(
          *(_QWORD *)(v18 + 16),
          v19,
          &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
          (unsigned int)ValueString);
      }
    }
    hKey = 0;
    v21 = CommonUtil::UtilRegGetValueString(v92, L"AVSignatureVersion", &hKey, 0, 0);
    if ( v21 >= 0 )
    {
      if ( (int)MpWatchDog::UtilConvertToLongLongVersion(v4 + 16, hKey) >= 0 )
        goto LABEL_49;
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_49;
      v23 = 31;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_49;
      v23 = 30;
    }
    WPP_SF_d(*(_QWORD *)(v22 + 16), v23, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, (unsigned int)v21);
LABEL_49:
    if ( hKey )
      operator delete(hKey, v20);
    if ( *(_QWORD *)v86 )
      operator delete(*(void **)v86, v20);
  }
  v91 = 0;
  v88 = (char *)v3 + 200;
  v82 = (MpWatchDog::WdConfigManager *)((char *)v3 + 200);
  *((_QWORD *)v3 + 25) = 0;
  v24 = -1;
  if ( (int)CommonUtil::UtilRegGetValueString(v2, L"InstallLocation", &v91, 0, 0) >= 0 )
  {
    v25 = (char *)v91;
    if ( !v91 )
      goto LABEL_86;
    v26 = -1;
    do
      ++v26;
    while ( *((_WORD *)v91 + v26) );
    if ( !v26 )
    {
LABEL_86:
      v35 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 32, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, v91);
        goto LABEL_89;
      }
      goto LABEL_90;
    }
    v27 = 0;
    if ( *(_WORD *)v91 )
    {
      v28 = (char *)v91;
      v29 = *(_WORD *)v91;
      do
      {
        if ( v29 == 92 || v29 == 47 )
          *(_WORD *)v28 = 92;
        ++v27;
        v28 = &v25[2 * v27];
        v29 = *(_WORD *)v28;
      }
      while ( *(_WORD *)v28 );
      for ( ; v27; *(_WORD *)v28 = 0 )
      {
        if ( *((_WORD *)v28 - 1) != 92 && *((_WORD *)v28 - 1) != 47 )
          break;
        --v27;
        v28 = &v25[2 * v27];
      }
    }
    v78 = 0;
    si128 = 0;
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)v91 + v30) );
    try
    {
      std::wstring::_Construct<1,wchar_t const *>(&v78, v91, v30);
      if ( (__int128 *)((char *)v3 + 296) != &v78 )
      {
        std::wstring::_Tidy_deallocate((char *)v3 + 296);
        *(_OWORD *)((char *)v3 + 296) = v78;
        *(__m128i *)((char *)v3 + 312) = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v78) = 0;
      }
      std::wstring::_Tidy_deallocate(&v78);
      v31 = *((_QWORD *)v3 + 39);
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v31) < 0xA )
        std::_Xlen_string();
      _mm_lfence();
      std::wstring::wstring(&v96, v31, L"\\MpSvc.dll", 10);
      v33 = (unsigned __int64 *)&v96;
      if ( v98 > 7 )
        v33 = v96;
      if ( (int)MpWatchDog::UtilGetFileVersion((MpWatchDog::WdConfigManager *)((char *)v3 + 200), v33, v32) < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        v34 = &v96;
        if ( v98 > 7 )
          LODWORD(v34) = (_DWORD)v96;
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          33,
          (unsigned int)&WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
          (_DWORD)v34,
          0);
      }
      std::wstring::_Tidy_deallocate(&v96);
    }
    catch ( const std::exception *v84 )
    {
      CommonUtil::HrFromStdException(v84, (const struct std::exception *)&v73);
    }
    catch ( ... )
    {
      v7 = 4;
      v24 = -1;
      v3 = v74;
      v2 = (HKEY)v75;
      v35 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids);
        goto LABEL_89;
      }
LABEL_90:
      if ( *(_QWORD *)v88 )
        goto LABEL_105;
      if ( (_UNKNOWN *)v35 != &WPP_GLOBAL_Control && (*(_BYTE *)(v35 + 28) & 2) != 0 )
        WPP_SF_(*(_QWORD *)(v35 + 16), 35, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids);
      hKey = 0;
      ModuleFileName = CommonUtil::UtilGetModuleFileName((CommonUtil *)&hKey, 0, 0);
      if ( ModuleFileName >= 0 )
      {
        ModuleFileName = MpWatchDog::UtilGetFileVersion(v82, (unsigned __int64 *)hKey, v38);
        if ( ModuleFileName < 0 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            v40 = 37;
            goto LABEL_102;
          }
        }
      }
      else
      {
        v39 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v40 = 36;
LABEL_102:
          WPP_SF_d(
            *(_QWORD *)(v39 + 16),
            v40,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            (unsigned int)ModuleFileName);
        }
      }
      if ( hKey )
        operator delete(hKey, v37);
LABEL_105:
      v41 = (int)MpWatchDog::UtilRegGetValueDwordWithMiscConfigOverride(
                   (CommonUtil *)v2,
                   (HKEY *)v2,
                   (HKEY)&stru_140194938,
                   v85) < 0;
      v43 = 0;
      if ( !v41 )
        LOBYTE(v43) = *(_DWORD *)v85 != 0;
      *((_DWORD *)v3 + 60) = v43;
      v41 = (int)CommonUtil::UtilRegGetValueDword((CommonUtil *)v2, (HKEY)&stru_140196318, v85, v42) < 0;
      v44 = 0;
      if ( !v41 )
        LOBYTE(v44) = *(_DWORD *)v85 != 0;
      *((_DWORD *)v3 + 57) = v44;
      hKey = 0;
      v45 = CommonUtil::UtilRegOpenKey(
              (CommonUtil *)&hKey,
              (HKEY *)0xFFFFFFFF80000002LL,
              (const WCHAR *)&stru_140196130,
              (const wchar_t *)1);
      v47 = hKey;
      if ( v45 >= 0
        && (*(_DWORD *)v86 = 0,
            v48 = CommonUtil::UtilRegGetValueDword((CommonUtil *)hKey, (HKEY)&stru_140196180, v86, v46),
            v47 = hKey,
            v48 >= 0) )
      {
        v49 = *(_DWORD *)v86 != 0;
        if ( hKey )
          RegCloseKey(hKey);
      }
      else
      {
        if ( v47 )
          RegCloseKey(v47);
        v49 = 0;
      }
      *((_DWORD *)v3 + 58) = v49;
      v88 = (char *)v3 + 244;
      *((_DWORD *)v3 + 61) = 0;
      v89 = 0;
      if ( (int)CommonUtil::UtilRegOpenKey(
                  (CommonUtil *)&v89,
                  (HKEY *)v2,
                  (const WCHAR *)&stru_140196338,
                  (const wchar_t *)1) >= 0 )
      {
        v51 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v89, (HKEY)&stru_140196350, v85, v50);
        v52 = 0;
        if ( v51 >= 0 )
          LOBYTE(v52) = *(_DWORD *)v85 != 0;
        *(_DWORD *)v88 = v52;
      }
      v53 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v2, (HKEY)&stru_140194970, v85, v50);
      v54 = 0;
      if ( v53 >= 0 )
        v54 = *(_DWORD *)v85;
      *((_DWORD *)v3 + 130) = v54;
      v95 = 0;
      if ( (int)MpWatchDog::UtilRegGetValueStringWithMiscConfigOverride(v2, v2, L"PartnerGUID", &v95) >= 0 )
      {
        v80 = 0;
        v81 = 0;
        do
          ++v24;
        while ( *((_WORD *)v95 + v24) );
        std::wstring::_Construct<1,wchar_t const *>(&v80, v95, v24);
        if ( (__int128 *)((char *)v3 + 528) != &v80 )
        {
          std::wstring::_Tidy_deallocate((char *)v3 + 528);
          *((_OWORD *)v3 + 33) = v80;
          *((__m128i *)v3 + 34) = v81;
          v81 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v80) = 0;
        }
        std::wstring::_Tidy_deallocate(&v80);
      }
      v55 = MpWatchDog::WdConfigManager::PopulateEcsFeatureStudyIds(v83, v2);
      if ( v55 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          39,
          &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
          (unsigned int)v55);
      }
      *((_DWORD *)v3 + 59) = 0;
      if ( *(_DWORD *)v88 )
        *((_DWORD *)v3 + 59) = (unsigned __int8)MpWatchDog::IsMsSenseOnboarded();
      *((_BYTE *)v3 + 290) = (unsigned int)MpIsWindowsServer() != 0;
      *((_BYTE *)v3 + 289) = 0;
      v94 = 0;
      v56 = CommonUtil::UtilRegOpenKey(
              (CommonUtil *)&v94,
              (HKEY *)v2,
              (const WCHAR *)&stru_140196370,
              (const wchar_t *)1);
      if ( v56 >= 0 )
      {
        *(_DWORD *)v86 = 0;
        v56 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v94, (HKEY)&stru_140196380, v86, v57);
        if ( v56 >= 0 )
        {
          *((_BYTE *)v3 + 289) = *(_DWORD *)v86 != 0;
          goto LABEL_145;
        }
        if ( v56 != -2147024894 )
        {
          v58 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            v59 = 41;
            goto LABEL_144;
          }
        }
      }
      else
      {
        v58 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v59 = 40;
LABEL_144:
          WPP_SF_d(*(_QWORD *)(v58 + 16), v59, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, (unsigned int)v56);
        }
      }
LABEL_145:
      MpWatchDog::PopulateCampConfigurationStringFromRegistry(&v89, L"SenseOrgId", (char *)v76 + 360);
      MpWatchDog::PopulateCampConfigurationStringFromRegistry(&v89, L"SenseRing", (char *)v3 + 392);
      MpWatchDog::PopulateCampConfigurationStringFromRegistry(&v89, L"SenseVersion", (char *)v3 + 424);
      v93 = 0;
      v60 = CommonUtil::UtilRegOpenKey(
              (CommonUtil *)&v93,
              (HKEY *)0xFFFFFFFF80000002LL,
              (const WCHAR *)&stru_1401963E0,
              (const wchar_t *)1);
      if ( v60 < 0 )
      {
LABEL_160:
        v63 = WPP_GLOBAL_Control;
        goto LABEL_161;
      }
      v88 = 0;
      v61 = CommonUtil::UtilRegGetValueString(v93, L"GUID", &v88, 0, 0);
      if ( v61 >= 0 )
      {
        hKey = 0;
        v64 = CommonUtil::NewSprintfA((CommonUtil *)&hKey, (char **)"%ls", v88);
        v60 = v64;
        if ( v64 >= 0 )
        {
          std::string::operator=((char *)v76 + 328);
          v63 = WPP_GLOBAL_Control;
        }
        else
        {
          v63 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              43,
              &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
              (unsigned int)v64);
            v63 = WPP_GLOBAL_Control;
          }
          v60 = 0;
        }
        if ( hKey )
        {
          operator delete(hKey, v62);
          v63 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        v63 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            42,
            &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids,
            (unsigned int)v61);
          v63 = WPP_GLOBAL_Control;
        }
        v60 = 0;
      }
      if ( v88 )
      {
        operator delete(v88, v62);
        goto LABEL_160;
      }
LABEL_161:
      if ( (int)(v60 + 0x80000000) >= 0
        && v60 != -2147024894
        && (_UNKNOWN *)v63 != &WPP_GLOBAL_Control
        && (*(_BYTE *)(v63 + 28) & 2) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(v63 + 16), 45, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, (unsigned int)v60);
      }
      *(_QWORD *)v86 = 0;
      if ( (int)CommonUtil::UtilRegGetValueString(v2, L"CachedProxy", v86, 0, 0) < 0 )
      {
        std::wstring::operator=((char *)v77 + 456, (void *)&Src);
        std::wstring::operator=((char *)v3 + 488, (void *)&Src);
      }
      else
      {
        v65 = (_QWORD *)((char *)v77 + 456);
        std::wstring::operator=((char *)v77 + 456, *(void **)v86);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          if ( *((_QWORD *)v77 + 60) > 7u )
            v65 = (_QWORD *)*v65;
          WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 46, &WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids, v65);
        }
        if ( *(_QWORD *)v86 )
        {
          operator delete(*(void **)v86, v66);
          *(_QWORD *)v86 = 0;
        }
        v67 = CommonUtil::UtilRegGetValueString(v2, L"CachedProxyBypass", v86, 0, 0);
        v68 = (wchar_t *)&Src;
        if ( v67 >= 0 )
          v68 = *(wchar_t **)v86;
        std::wstring::operator=((char *)v3 + 488, v68);
      }
      if ( *(_QWORD *)v86 )
        operator delete(*(void **)v86, v69);
      v96 = (unsigned __int64 *)122;
      v97[0] = (char *)v3 + 656;
      v97[1] = 123;
      v98 = (unsigned __int64)v3 + 660;
      v99 = 125;
      v100 = (char *)v3 + 664;
      v101 = 126;
      v102 = (char *)v3 + 668;
      v70 = (_DWORD **)v97;
      do
      {
        *(_DWORD *)v85 = 0;
        if ( (int)MpWatchDog::ReadFeatureControl(v2, *(v70 - 1), v85) >= 0 )
          **v70 = *(_DWORD *)v85;
        v70 += 2;
        --v7;
      }
      while ( v7 );
      if ( v93 )
        RegCloseKey(v93);
      if ( v94 )
        RegCloseKey(v94);
      if ( v95 )
        operator delete(v95, v71);
      if ( v89 )
        RegCloseKey(v89);
      if ( v91 )
        operator delete(v91, v71);
      if ( v92 )
        RegCloseKey(v92);
      if ( v90 )
        RegCloseKey(v90);
      result = 0;
    }
  }
LABEL_89:
  v35 = WPP_GLOBAL_Control;
  goto LABEL_90;
}

```

## disassembly

```asm
0x14008ffb0  mov     r11, rsp
0x14008ffb3  mov     [r11+18h], rbx
0x14008ffb7  mov     [r11+20h], rsi
0x14008ffbb  push    rdi
0x14008ffbc  push    r12
0x14008ffbe  push    r13
0x14008ffc0  push    r14
0x14008ffc2  push    r15
0x14008ffc4  sub     rsp, 180h
0x14008ffcb  mov     rax, cs:__security_cookie
0x14008ffd2  xor     rax, rsp
0x14008ffd5  mov     [rsp+1A8h+var_38], rax
0x14008ffdd  mov     r14, rdx
0x14008ffe0  mov     rdi, rcx
0x14008ffe3  mov     [rsp+1A8h+var_100], rcx
0x14008ffeb  mov     [rsp+1A8h+var_158], rcx
0x14008fff0  mov     [rsp+1A8h+var_168], rcx
0x14008fff5  mov     [rsp+1A8h+var_150], rcx
0x14008fffa  mov     [rsp+1A8h+var_160], rdx
0x14008ffff  xor     ebx, ebx
0x140090001  mov     dword ptr [rsp+1A8h+var_D8], ebx
0x140090008  lea     r13, [rcx+0C0h]
0x14009000f  mov     [r13+60h], bl
0x140090013  mov     [r11-0C8h], rbx
0x14009001a  mov     dword ptr [rsp+1A8h+var_D0], ebx
0x140090021  lea     r9d, [rbx+1]; wchar_t *
0x140090025  lea     r8, stru_140196060; HKEY
0x14009002c  lea     rcx, [r11-0C8h]; this
0x140090033  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x140090038  test    eax, eax
0x14009003a  js      short loc_1400900B6
0x14009003c  lea     r8, [rsp+1A8h+var_D0]; wchar_t *
0x140090044  lea     rdx, stru_140196080; HKEY
0x14009004b  mov     rcx, [rsp+1A8h+hKey]; this
0x140090053  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)
0x140090058  test    eax, eax
0x14009005a  js      short loc_1400900B6
0x14009005c  cmp     dword ptr [rsp+1A8h+var_D0], 1
0x140090064  setz    sil
0x140090068  mov     rcx, [rsp+1A8h+hKey]; hKey
0x140090070  test    rcx, rcx
0x140090073  jz      short loc_14009007B
0x140090075  call    cs:__imp_RegCloseKey
0x14009007b  test    sil, sil
0x14009007e  jz      short loc_1400900C9
0x140090080  lea     rsi, WPP_GLOBAL_Control
0x140090087  mov     rcx, cs:WPP_GLOBAL_Control
0x14009008e  cmp     rcx, rsi
0x140090091  jz      short loc_1400900AE
0x140090093  test    byte ptr [rcx+1Ch], 2
0x140090097  jz      short loc_1400900AE
0x140090099  mov     edx, 19h
0x14009009e  lea     r8, WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids
0x1400900a5  mov     rcx, [rcx+10h]
0x1400900a9  call    WPP_SF_
0x1400900ae  mov     [rdi+120h], bl
0x1400900b4  jmp     short loc_1400900F9
0x1400900b6  mov     rcx, [rsp+1A8h+hKey]; hKey
0x1400900be  test    rcx, rcx
0x1400900c1  jz      short loc_1400900C9
0x1400900c3  call    cs:__imp_RegCloseKey
0x1400900c9  lea     r8, [rsp+1A8h+var_D8]
0x1400900d1  mov     edx, 15h
0x1400900d6  mov     rcx, r14
0x1400900d9  call    ?ReadFeatureControlWithMiscConfigOverride@MpWatchDog@@YAJPEAUHKEY__@@W4FeatureControlEnum@@PEAK@Z; MpWatchDog::ReadFeatureControlWithMiscConfigOverride(HKEY__ *,FeatureControlEnum,ulong *)
0x1400900de  lea     rsi, WPP_GLOBAL_Control
0x1400900e5  test    eax, eax
0x1400900e7  js      short loc_1400900F9
0x1400900e9  cmp     dword ptr [rsp+1A8h+var_D8], ebx
0x1400900f0  setnz   al
0x1400900f3  mov     [rdi+120h], al
0x1400900f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140090100  mov     r12d, 4
0x140090106  cmp     rcx, rsi
0x140090109  jz      short loc_14009012E
0x14009010b  test    [rcx+1Ch], r12b
0x14009010f  jz      short loc_14009012E
0x140090111  movzx   r9d, byte ptr [rdi+120h]
0x140090119  lea     edx, [r12+16h]
0x14009011e  lea     r8, WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids
0x140090125  mov     rcx, [rcx+10h]
0x140090129  call    WPP_SF_d
0x14009012e  cmp     [rdi+120h], bl
0x140090134  jnz     short loc_14009014C
0x140090136  lea     r8, aClear; "Clear"
0x14009013d  lea     rdx, MpWatchDog__ClearBitsFunc; unsigned int (*)(unsigned int, unsigned int)
0x140090144  mov     ecx, r12d; unsigned int
0x140090147  call    ?ModifyCoreServiceStatusBitfield@MpCoreSvcDiagnostics@MpWatchDog@@CAJKP6AKKK@ZPEB_W@Z; MpWatchDog::MpCoreSvcDiagnostics::ModifyCoreServiceStatusBitfield(ulong,ulong (*)(ulong,ulong),wchar_t const *)
0x14009014c  mov     [rsp+1A8h+var_B0], rbx
0x140090154  mov     r9d, 1; wchar_t *
0x14009015a  lea     r8, stru_140196240; HKEY
0x140090161  mov     rdx, r14; HKEY *
0x140090164  lea     rcx, [rsp+1A8h+var_B0]; this
0x14009016c  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x140090171  test    eax, eax
0x140090173  jns     short loc_1400901B8
0x140090175  mov     rcx, cs:WPP_GLOBAL_Control
0x14009017c  cmp     rcx, rsi
0x14009017f  jz      short loc_14009019F
0x140090181  test    byte ptr [rcx+1Ch], 1
0x140090185  jz      short loc_14009019F
0x140090187  mov     edx, 1Bh
0x14009018c  mov     r9d, eax
0x14009018f  lea     r8, WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids
0x140090196  mov     rcx, [rcx+10h]
0x14009019a  call    WPP_SF_d
0x14009019f  mov     r15d, 5
0x1400901a5  mov     [rdi+0D8h], r15d
0x1400901ac  mov     [rdi+0DCh], r15d
0x1400901b3  jmp     loc_140090243
0x1400901b8  lea     r8, [rsp+1A8h+var_D8]; wchar_t *
0x1400901c0  lea     rdx, stru_140196258; HKEY
0x1400901c7  mov     rcx, [rsp+1A8h+var_B0]; this
0x1400901cf  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)
0x1400901d4  mov     r15d, 5
0x1400901da  mov     ecx, r15d
0x1400901dd  test    eax, eax
0x1400901df  cmovns  ecx, dword ptr [rsp+1A8h+var_D8]
0x1400901e7  mov     [rdi+0D8h], ecx
0x1400901ed  lea     r8, [rsp+1A8h+var_D8]; wchar_t *
0x1400901f5  lea     rdx, stru_140196278; HKEY
0x1400901fc  mov     rcx, [rsp+1A8h+var_B0]; this
0x140090204  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)
0x140090209  mov     ecx, r15d
0x14009020c  test    eax, eax
0x14009020e  cmovns  ecx, dword ptr [rsp+1A8h+var_D8]
0x140090216  mov     [rdi+0DCh], ecx
0x14009021c  lea     r8, [rsp+1A8h+var_D8]; wchar_t *
0x140090224  lea     rdx, stru_140196290; HKEY
0x14009022b  mov     rcx, [rsp+1A8h+var_B0]; this
0x140090233  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)
0x140090238  test    eax, eax
0x14009023a  cmovns  r15d, dword ptr [rsp+1A8h+var_D8]
0x140090243  mov     [r13+20h], r15d
0x140090247  mov     [rsp+1A8h+var_A0], rbx
0x14009024f  mov     [r13+0], rbx
0x140090253  mov     r9d, 1; wchar_t *
0x140090259  lea     r8, stru_1401962B0; HKEY
0x140090260  mov     rdx, r14; HKEY *
0x140090263  lea     rcx, [rsp+1A8h+var_A0]; this
0x14009026b  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x140090270  test    eax, eax
0x140090272  js      loc_1400903B1
0x140090278  mov     qword ptr [rsp+1A8h+var_D0], rbx
0x140090280  mov     qword ptr [rsp+1A8h+var_188], rbx
0x140090285  xor     r9d, r9d
0x140090288  lea     r8, [rsp+1A8h+var_D0]
0x140090290  lea     rdx, aEngineversion; "EngineVersion"
0x140090297  mov     rcx, [rsp+1A8h+var_A0]
0x14009029f  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x1400902a4  mov     r15d, eax
0x1400902a7  test    eax, eax
0x1400902a9  jns     short loc_1400902C4
0x1400902ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400902b2  cmp     rcx, rsi
0x1400902b5  jz      short loc_140090302
0x1400902b7  test    byte ptr [rcx+1Ch], 2
0x1400902bb  jz      short loc_140090302
0x1400902bd  mov     edx, 1Ch
0x1400902c2  jmp     short loc_1400902EF
0x1400902c4  mov     rdx, qword ptr [rsp+1A8h+var_D0]
0x1400902cc  mov     rcx, r13
0x1400902cf  call    MpWatchDog__UtilConvertToLongLongVersion
0x1400902d4  test    eax, eax
0x1400902d6  jns     short loc_140090302
0x1400902d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400902df  cmp     rcx, rsi
0x1400902e2  jz      short loc_140090302
0x1400902e4  test    byte ptr [rcx+1Ch], 2
0x1400902e8  jz      short loc_140090302
0x1400902ea  mov     edx, 1Dh
0x1400902ef  mov     r9d, r15d
0x1400902f2  lea     r8, WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids
0x1400902f9  mov     rcx, [rcx+10h]
0x1400902fd  call    WPP_SF_d
0x140090302  mov     [rsp+1A8h+hKey], rbx
0x14009030a  mov     qword ptr [rsp+1A8h+var_188], rbx
0x14009030f  xor     r9d, r9d
0x140090312  lea     r8, [rsp+1A8h+hKey]
0x14009031a  lea     rdx, aAvsignaturever; "AVSignatureVersion"
0x140090321  mov     rcx, [rsp+1A8h+var_A0]
0x140090329  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x14009032e  mov     r15d, eax
0x140090331  test    eax, eax
0x140090333  jns     short loc_14009034E
0x140090335  mov     rcx, cs:WPP_GLOBAL_Control
0x14009033c  cmp     rcx, rsi
0x14009033f  jz      short loc_14009038D
0x140090341  test    byte ptr [rcx+1Ch], 2
0x140090345  jz      short loc_14009038D
0x140090347  mov     edx, 1Eh
0x14009034c  jmp     short loc_14009037A
0x14009034e  lea     rcx, [r13+10h]
0x140090352  mov     rdx, [rsp+1A8h+hKey]
0x14009035a  call    MpWatchDog__UtilConvertToLongLongVersion
0x14009035f  test    eax, eax
0x140090361  jns     short loc_14009038D
0x140090363  mov     rcx, cs:WPP_GLOBAL_Control
0x14009036a  cmp     rcx, rsi
0x14009036d  jz      short loc_14009038D
0x14009036f  test    byte ptr [rcx+1Ch], 2
0x140090373  jz      short loc_14009038D
0x140090375  mov     edx, 1Fh
0x14009037a  mov     r9d, r15d
0x14009037d  lea     r8, WPP_a86b7f7117903db554f70d7d098d55d9_Traceguids
0x140090384  mov     rcx, [rcx+10h]
0x140090388  call    WPP_SF_d
0x14009038d  mov     rcx, [rsp+1A8h+hKey]; void *
0x140090395  test    rcx, rcx
0x140090398  jz      short loc_14009039F
0x14009039a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14009039f  mov     rcx, qword ptr [rsp+1A8h+var_D0]; void *
0x1400903a7  test    rcx, rcx
0x1400903aa  jz      short loc_1400903B1
0x1400903ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400903b1  mov     [rsp+1A8h+var_A8], rbx
0x1400903b9  lea     rax, [rdi+0C8h]
0x1400903c0  mov     [rsp+1A8h+var_C0], rax
0x1400903c8  mov     [rsp+1A8h+var_108], rax
0x1400903d0  mov     [rax], rbx
0x1400903d3  mov     qword ptr [rsp+1A8h+var_188], rbx; unsigned int
0x1400903d8  xor     r9d, r9d
0x1400903db  lea     r8, [rsp+1A8h+var_A8]
0x1400903e3  lea     rdx, aInstalllocatio; "InstallLocation"
0x1400903ea  mov     rcx, r14
0x1400903ed  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x1400903f2  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400903f6  test    eax, eax
0x1400903f8  js      loc_140090663
0x1400903fe  mov     r9, [rsp+1A8h+var_A8]
0x140090406  test    r9, r9
0x140090409  jz      loc_14009063C
0x14009040f  mov     rax, r13
0x140090412  inc     rax
0x140090415  cmp     [r9+rax*2], bx
0x14009041a  jnz     short loc_140090412
0x14009041c  test    rax, rax
0x14009041f  jz      loc_14009063C
0x140090425  mov     rax, rbx
0x140090428  cmp     [r9], bx
0x14009042c  jz      short loc_14009047E
0x14009042e  mov     rcx, r9
0x140090431  movzx   edx, word ptr [r9]
0x140090435  mov     r10d, 5Ch ; '\'
0x14009043b  lea     r8d, [r10-2Dh]
0x14009043f  cmp     dx, r10w
0x140090443  jz      short loc_14009044B
0x140090445  cmp     dx, r8w
0x140090449  jnz     short loc_14009044F
0x14009044b  mov     [rcx], r10w
0x14009044f  inc     rax
0x140090452  lea     rcx, [r9+rax*2]
0x140090456  movzx   edx, word ptr [rcx]
0x140090459  test    dx, dx
0x14009045c  jnz     short loc_14009043F
0x14009045e  test    rax, rax
0x140090461  jz      short loc_14009047E
0x140090463  cmp     [rcx-2], r10w
0x140090468  jz      short loc_140090471
0x14009046a  cmp     [rcx-2], r8w
0x14009046f  jnz     short loc_14009047E
0x140090471  sub     rax, 1
0x140090475  lea     rcx, [r9+rax*2]
0x140090479  mov     [rcx], bx
0x14009047c  jnz     short loc_140090463
0x14009047e  xorps   xmm0, xmm0
0x140090481  movups  [rsp+1A8h+var_148], xmm0
0x140090486  xorps   xmm1, xmm1
0x140090489  movdqu  [rsp+1A8h+var_138], xmm1
0x14009048f  mov     rdx, [rsp+1A8h+var_A8]
0x140090497  mov     r8, r13
0x14009049a  inc     r8
0x14009049d  cmp     [rdx+r8*2], bx
0x1400904a2  jnz     short loc_14009049A
0x1400904a4  lea     rcx, [rsp+1A8h+var_148]
0x1400904a9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400904ae  lea     r15, [rdi+128h]
0x1400904b5  lea     rax, [rsp+1A8h+var_148]
0x1400904ba  cmp     r15, rax
0x1400904bd  jz      short loc_1400904ED
0x1400904bf  mov     rcx, r15
0x1400904c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400904c7  movups  xmm0, [rsp+1A8h+var_148]
0x1400904cc  movups  xmmword ptr [r15], xmm0
0x1400904d0  movups  xmm1, [rsp+1A8h+var_138]
0x1400904d5  movups  xmmword ptr [r15+10h], xmm1
0x1400904da  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1400904e2  movdqu  [rsp+1A8h+var_138], xmm0
0x1400904e8  mov     word ptr [rsp+1A8h+var_148], bx
0x1400904ed  lea     rcx, [rsp+1A8h+var_148]
0x1400904f2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400904f7  mov     rcx, [r15+10h]
0x1400904fb  mov     rax, 7FFFFFFFFFFFFFFEh
0x140090505  sub     rax, rcx
0x140090508  cmp     rax, 0Ah
0x14009050c  jb      loc_140091010
0x140090512  lfence
0x140090515  cmp     qword ptr [r15+18h], 7
0x14009051a  jbe     short loc_14009051F
0x14009051c  mov     r15, [r15]
  ... truncated ...
```
