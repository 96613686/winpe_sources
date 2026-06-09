# SystemSettings::BatteryUsageHandlers::AppListEntry2::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x18004ce90`
- end: `0x18004ddab`
- name: `?GetProperty@AppListEntry2@BatteryUsageHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `3867`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::AppListEntry2 *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800043d8`
- `0x180004cfc`
- `0x18000a13c`
- `0x18000a8fc`
- `0x18000e7f0`
- `0x18000fa78`
- `0x1800171c0`
- `0x1800177e0`
- `0x180017834`
- `0x180019b4c`
- `0x18001e360`
- `0x18001e4a0`
- `0x180023c30`
- `0x18002aab0`
- `0x18003cedc`
- `0x180042ef0`
- `0x180043770`
- `0x18004a55c`
- `0x18004a5bc`
- `0x18004cccc`
- `0x18004ce90`
- `0x18004ded8`
- `0x18004df48`
- `0x18004e044`
- `0x18004e11c`
- `0x18004e210`
- `0x18004e7dc`
- `0x18004e8e4`
- `0x1800513a4`
- `0x18005a010`

## import_xrefs

- `SHCORE!CreateRandomAccessStreamOnFile` at `0x18004d14b`
- `SHCORE!CreateRandomAccessStreamOnFile` at `0x18004d14b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d81a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d81a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d883`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d546`

## string_xrefs

- `0x18004dc10`: `SettingsPageInstalledApps`
- `0x18004dbd7`: `SettingsPageSystemComponents`
- `0x18004dc7b`: `SystemSettings_StorageSense_HiddenSystemComponentsAdvancedPageLink`
- `0x18004dd1f`: `SystemSettings_StorageSense_HiddenSystemComponentsAdvancedPageLink`
- `0x18004dcb4`: `SystemSettings_StorageSense_HiddenAppAdvancedPageLink`
- `0x18004dd51`: `SystemSettings_StorageSense_HiddenAppAdvancedPageLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
int __fastcall SystemSettings::BatteryUsageHandlers::AppListEntry2::GetProperty(
        SystemSettings::BatteryUsageHandlers::AppListEntry2 *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  bool IsHstringEqual; // al
  const unsigned __int16 *v7; // r8
  int v8; // eax
  const char *v9; // r9
  int v10; // ebx
  int result; // eax
  const unsigned __int16 *v12; // r8
  int v13; // eax
  int v14; // ebx
  const unsigned __int16 *v15; // r8
  int Double; // eax
  int v17; // ebx
  const unsigned __int16 *v18; // r8
  int Boolean; // eax
  int v20; // ebx
  const unsigned __int16 *v21; // r8
  int v22; // eax
  int v23; // ebx
  __int64 v24; // rdx
  const unsigned __int16 *v25; // r8
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  const unsigned __int16 *v29; // rax
  int v30; // eax
  int v31; // ebx
  __int64 v32; // rdx
  const unsigned __int16 *v33; // r8
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rax
  int v38; // eax
  int v39; // ebx
  int v40; // eax
  int v41; // ebx
  const unsigned __int16 *v42; // r8
  int UInt32; // eax
  int v44; // ebx
  const unsigned __int16 *v45; // r8
  __int64 v46; // rax
  __int64 v47; // rdx
  unsigned __int8 v48; // cl
  int v49; // eax
  int v50; // ebx
  const unsigned __int16 *v51; // r8
  unsigned __int16 *v52; // r15
  int ResourceString; // eax
  SystemSettings::BatteryUsageHandlers::AppListEntry2 *v54; // rcx
  int v55; // edi
  int v56; // eax
  SystemSettings::BatteryUsageHandlers::AppListEntry2 *v57; // rcx
  int v58; // edi
  int v59; // eax
  int v60; // edi
  int v61; // eax
  SystemSettings::BatteryUsageHandlers::AppListEntry2 *v62; // rcx
  int v63; // edi
  int v64; // eax
  SystemSettings::BatteryUsageHandlers::AppListEntry2 *v65; // rcx
  int v66; // edi
  int v67; // eax
  int v68; // ebx
  unsigned int StringRawBuffer; // ebx
  PCWSTR v70; // rax
  int v71; // eax
  int v72; // ebx
  int v73; // eax
  int v74; // ebx
  const unsigned __int16 *v75; // r8
  int v76; // eax
  int v77; // ebx
  const unsigned __int16 *v78; // r8
  int v79; // eax
  int v80; // ebx
  SystemSettings::BatteryUsageHandlers::AppListEntry2 *v81; // rcx
  const unsigned __int16 *v82; // r8
  SystemSettings::BatteryUsageHandlers::AppListEntry2 *v83; // rcx
  const unsigned __int16 *v84; // r8
  const unsigned __int16 *v85; // r8
  const unsigned __int16 *CurrentPolicyDescriptionString; // rax
  int v87; // eax
  int v88; // ebx
  const unsigned __int16 *v89; // r8
  bool IsBackgroundTasksControlUserConfigurable; // al
  unsigned __int8 v91; // cl
  int v92; // eax
  int v93; // ebx
  const unsigned __int16 *v94; // r8
  __int64 v95; // r8
  SystemSettings::BatteryUsageHandlers::AppIdentity *v96; // rax
  __int64 v97; // rcx
  int PackageFamilyNameFromAppIdentity; // ebx
  const unsigned __int16 *v99; // r8
  unsigned __int8 IsSystemManaged; // al
  int v101; // eax
  int v102; // ebx
  const unsigned __int16 *v103; // r8
  unsigned __int8 IsBackgroundTasksPolicyManageable; // al
  int v105; // eax
  int v106; // ebx
  const unsigned __int16 *v107; // r8
  __int64 v108; // rax
  __int64 PackageFullNameFromFamilyName; // rax
  int TaskPolicy; // eax
  int v111; // ebx
  int v112; // eax
  int v113; // ebx
  const unsigned __int16 *v114; // r8
  unsigned __int8 v115; // al
  int v116; // eax
  int v117; // ebx
  const unsigned __int16 *v118; // r8
  unsigned __int8 v119; // al
  int v120; // eax
  int v121; // ebx
  const unsigned __int16 *v122; // r8
  __int64 v123; // rax
  __int64 v124; // rcx
  char DoesFriendlyNameCollide; // al
  const unsigned __int16 *v126; // rcx
  int v127; // eax
  int v128; // ebx
  __int64 v129; // rdx
  const unsigned __int16 *v130; // r8
  const unsigned __int16 *v131; // rax
  SystemSettings::BatteryUsageHandlers::AppListEntry2 *v132; // rcx
  int v133; // eax
  int v134; // ebx
  int v135; // eax
  int v136; // ebx
  __int64 v137; // rdx
  const unsigned __int16 *v138; // r8
  const unsigned __int16 *v139; // rax
  SystemSettings::BatteryUsageHandlers::AppListEntry2 *v140; // rcx
  int v141; // eax
  int v142; // ebx
  int v143; // eax
  int v144; // ebx
  __int64 v145; // rdx
  const unsigned __int16 *v146; // r8
  const unsigned __int16 *v147; // rax
  SystemSettings::BatteryUsageHandlers::AppListEntry2 *v148; // rcx
  int v149; // eax
  int v150; // ebx
  int v151; // eax
  int v152; // ebx
  __int64 v153; // rdx
  __int64 v154; // r8
  const unsigned __int16 *v155; // rax
  SystemSettings::BatteryUsageHandlers::AppListEntry2 *v156; // rcx
  int v157; // eax
  int v158; // ebx
  int v159; // eax
  int v160; // ebx
  int v161; // [rsp+20h] [rbp-B8h]
  int v162; // [rsp+20h] [rbp-B8h]
  HSTRING string; // [rsp+40h] [rbp-98h] BYREF
  HSTRING v164; // [rsp+48h] [rbp-90h] BYREF
  unsigned __int16 *v165[2]; // [rsp+50h] [rbp-88h] BYREF
  __int64 v166; // [rsp+60h] [rbp-78h]
  HSTRING v167; // [rsp+70h] [rbp-68h] BYREF
  HSTRING v168; // [rsp+78h] [rbp-60h] BYREF
  _BYTE v169[88]; // [rsp+80h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  *a3 = 0;
  IsHstringEqual = SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800652A0, (const unsigned __int16 *)a3);
  try
  {
    if ( IsHstringEqual )
    {
      v8 = (*(__int64 (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry2 *, struct IInspectable **))(*(_QWORD *)this + 224LL))(
             this,
             a3);
      v10 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x191,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v8,
          v161);
        return v10;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180067F38, v7) )
    {
      v13 = (*(__int64 (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry2 *, struct IInspectable **))(*(_QWORD *)this + 232LL))(
              this,
              a3);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x195,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v13,
          v161);
        return v14;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069778, v12) )
    {
      Double = SystemSettings::DataModel::PropValueHelper::CreateDouble(*((double *)this + 36), a3);
      v17 = Double;
      if ( Double < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19B,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)Double,
          v161);
        return v17;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069760, v15) )
    {
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 392), a3);
      v20 = Boolean;
      if ( Boolean < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19F,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)Boolean,
          v161);
        return v20;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800697A8, v18) )
    {
      v22 = SystemSettings::DataModel::PropValueHelper::CreateDouble(*((double *)this + 36), a3);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A3,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v22,
          v161);
        return v23;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069790, v21) )
    {
      v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 248, v24, v25);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                              v26,
                              *((_QWORD *)this + 33),
                              &word_180065238,
                              0) )
        return -2147467259;
      v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                        (char *)this + 248,
                                        v27,
                                        v28);
      v30 = SystemSettings::DataModel::PropValueHelper::CreateString(v29, a3);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AE,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v30,
          v161);
        return v31;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069800, v25) )
    {
      v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 248, v32, v33);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                              v34,
                              *((_QWORD *)this + 33),
                              &word_180065238,
                              0) )
        return -2147467259;
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      v37 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 248, v35, v36);
      v38 = CreateRandomAccessStreamOnFile(v37, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &string);
      v39 = v38;
      if ( v38 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B8,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v38,
          v161);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
        return v39;
      }
      v40 = (**(__int64 (__fastcall ***)(HSTRING, GUID *, struct IInspectable **))string)(
              string,
              &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
              a3);
      v41 = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BA,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v40,
          v161);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
        return v41;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800697E0, v33) )
    {
      UInt32 = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                 *((unsigned __int8 *)this + 283)
               | ((*((unsigned __int8 *)this + 282)
                 | (((*((unsigned __int8 *)this + 280) << 8) | (unsigned int)*((unsigned __int8 *)this + 281)) << 8)) << 8),
                 a3);
      v44 = UInt32;
      if ( UInt32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C0,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)UInt32,
          v161);
        return v44;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069840, v42) )
    {
      v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 248, (char *)this + 248, v45);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                              v46,
                              *(_QWORD *)(v47 + 16),
                              &word_180065238,
                              0)
        || (v48 = 1, *((_DWORD *)this + 96)) )
      {
        v48 = 0;
      }
      v49 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v48, a3);
      v50 = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C5,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v49,
          v161);
        return v50;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069E50, v45) )
    {
      v52 = (unsigned __int16 *)operator new[](0x200u);
      v164 = 0;
      v168 = 0;
      v167 = 0;
      string = 0;
      *(_OWORD *)v165 = 0;
      v166 = 0;
      ResourceString = SystemSettings::DataModel::BatteryUsageHelper::GetResourceString(0x2415u);
      v55 = ResourceString;
      if ( ResourceString < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CE,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)ResourceString,
          v161);
        std::vector<unsigned short>::_Tidy(v165);
        return v55;
      }
      v56 = SystemSettings::BatteryUsageHandlers::AppListEntry2::formatAppUsagePercentage(
              v54,
              *((double *)this + 38),
              v165[0],
              &v164);
      v58 = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CF,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v56,
          v161);
        std::vector<unsigned short>::_Tidy(v165);
        return v58;
      }
      if ( v165[0] != v165[1] )
        v165[1] = v165[0];
      v59 = SystemSettings::BatteryUsageHandlers::AppListEntry2::formatAppUsageTime(
              v57,
              (double)*((int *)this + 79) / 3600000.0,
              &v168);
      v60 = v59;
      if ( v59 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D2,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v59,
          v161);
        std::vector<unsigned short>::_Tidy(v165);
        return v60;
      }
      if ( v165[0] != v165[1] )
        v165[1] = v165[0];
      v61 = SystemSettings::DataModel::BatteryUsageHelper::GetResourceString(0x2416u);
      v63 = v61;
      if ( v61 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D6,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v61,
          v161);
        std::vector<unsigned short>::_Tidy(v165);
        return v63;
      }
      v64 = SystemSettings::BatteryUsageHandlers::AppListEntry2::formatAppUsagePercentage(
              v62,
              *((double *)this + 37),
              v165[0],
              &v167);
      v66 = v64;
      if ( v64 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D7,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v64,
          v161);
        std::vector<unsigned short>::_Tidy(v165);
        return v66;
      }
      if ( v165[0] != v165[1] )
        v165[1] = v165[0];
      v67 = SystemSettings::BatteryUsageHandlers::AppListEntry2::formatAppUsageTime(
              v65,
              (double)*((int *)this + 78) / 3600000.0,
              &string);
      v68 = v67;
      if ( v67 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DB,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v67,
          v161);
        std::vector<unsigned short>::_Tidy(v165);
        return v68;
      }
      WindowsGetStringRawBuffer(string, 0);
      WindowsGetStringRawBuffer(v167, 0);
      StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(v168, 0);
      v70 = WindowsGetStringRawBuffer(v164, 0);
      v162 = StringRawBuffer;
      v71 = StringCchPrintfW(v52, 0x100u, L"%s %s %s %s", v70);
      v72 = v71;
      if ( v71 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EF,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v71,
          v162);
        std::vector<unsigned short>::_Tidy(v165);
        return v72;
      }
      v73 = SystemSettings::DataModel::PropValueHelper::CreateString(v52, a3);
      v74 = v73;
      if ( v73 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F1,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v73,
          v162);
        std::vector<unsigned short>::_Tidy(v165);
        return v74;
      }
      std::vector<unsigned short>::_Tidy(v165);
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069820, v51) )
    {
      v76 = SystemSettings::DataModel::PropValueHelper::CreateDouble(*((double *)this + 37), a3);
      v77 = v76;
      if ( v76 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F8,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v76,
          v161);
        return v77;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069880, v75) )
    {
      v79 = SystemSettings::DataModel::PropValueHelper::CreateDouble(*((double *)this + 38), a3);
      v80 = v79;
      if ( v79 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1FE,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v79,
          v161);
        return v80;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069860, v78) )
    {
      v164 = 0;
      result = SystemSettings::BatteryUsageHandlers::AppListEntry2::formatAppUsageTime(
                 v81,
                 (double)*((int *)this + 78) / 3600000.0,
                 &v164);
      if ( result < 0 )
        return result;
      result = SystemSettings::DataModel::PropValueHelper::CreateString(v164, a3);
      if ( result < 0 )
        return result;
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800698D0, v82) )
    {
      v164 = 0;
      result = SystemSettings::BatteryUsageHandlers::AppListEntry2::formatAppUsageTime(
                 v83,
                 (double)*((int *)this + 79) / 3600000.0,
                 &v164);
      if ( result >= 0 )
      {
        result = SystemSettings::DataModel::PropValueHelper::CreateString(v164, a3);
        if ( result >= 0 )
          return 0;
      }
    }
    else
    {
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069920, v84) )
      {
        CurrentPolicyDescriptionString = SystemSettings::BatteryUsageHandlers::AppListEntry2::GetCurrentPolicyDescriptionString(this);
        v87 = SystemSettings::DataModel::PropValueHelper::CreateString(CurrentPolicyDescriptionString, a3);
        v88 = v87;
        if ( v87 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x21A,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v87,
            v161);
          return v88;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069980, v85) )
      {
        if ( !SystemSettings::BatteryUsageHandlers::AppListEntry2::IsAppManagementOptionsSupported(this)
          || (IsBackgroundTasksControlUserConfigurable = SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksControlUserConfigurable(this),
              v91 = 1,
              !IsBackgroundTasksControlUserConfigurable) )
        {
          v91 = 0;
        }
        v92 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v91, a3);
        v93 = v92;
        if ( v92 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x225,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v92,
            v161);
          return v93;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069950, v89) )
      {
        WindowsDeleteString(0);
        string = 0;
        v96 = SystemSettings::BatteryUsageHandlers::AppIdentity::AppIdentity(
                (SystemSettings::BatteryUsageHandlers::AppIdentity *)v169,
                (SystemSettings::BatteryUsageHandlers::AppListEntry2 *)((char *)this + 352),
                v95);
        PackageFamilyNameFromAppIdentity = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFamilyNameFromAppIdentity(
                                             v97,
                                             v96,
                                             &string);
        if ( PackageFamilyNameFromAppIdentity < 0
          || (PackageFamilyNameFromAppIdentity = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3),
              PackageFamilyNameFromAppIdentity < 0) )
        {
          WindowsDeleteString(string);
          return PackageFamilyNameFromAppIdentity;
        }
        WindowsDeleteString(string);
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069A40, v94) )
      {
        IsSystemManaged = SystemSettings::BatteryUsageHandlers::AppListEntry2::IsSystemManaged(this);
        v101 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsSystemManaged, a3);
        v102 = v101;
        if ( v101 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x232,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v101,
            v161);
          return v102;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069A00, v99) )
      {
        IsBackgroundTasksPolicyManageable = SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksPolicyManageable(this);
        v105 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsBackgroundTasksPolicyManageable, a3);
        v106 = v105;
        if ( v105 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x238,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v105,
            v161);
          return v106;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069AC8, v103) )
      {
        LODWORD(string) = 0;
        v108 = std::wstring::wstring((__int64)v165, (__int64)this + 352, (__int64)v107);
        PackageFullNameFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(
                                          &SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2,
                                          v169,
                                          v108);
        TaskPolicy = SystemSettings::BatteryUsageHandlers::GetTaskPolicy(PackageFullNameFromFamilyName, &string);
        v111 = TaskPolicy;
        if ( TaskPolicy < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23F,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)TaskPolicy,
            v161);
          return v111;
        }
        v112 = SystemSettings::DataModel::PropValueHelper::CreateBoolean((_DWORD)string == 3, a3);
        v113 = v112;
        if ( v112 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x241,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v112,
            v161);
          return v113;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069A70, v107) )
      {
        v115 = SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksControlUserConfigurable(this);
        v116 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v115, a3);
        v117 = v116;
        if ( v116 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24E,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v116,
            v161);
          return v117;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069B20, v114) )
      {
        v119 = SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksControlUserConfigurable(this);
        v120 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v119, a3);
        v121 = v120;
        if ( v120 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x254,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v120,
            v161);
          return v121;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069AE8, v118) )
      {
        v123 = std::wstring::wstring((__int64)v169, (__int64)this + 320, (__int64)v122);
        DoesFriendlyNameCollide = SystemSettings::BatteryUsageHandlers::FriendlyNameCollisionTracker::DoesFriendlyNameCollide(
                                    v124,
                                    v123);
        v126 = L"SystemSettings_BatterySaver_UsagePageFriendlyNameCollision";
        if ( !DoesFriendlyNameCollide )
          v126 = L"SystemSettings_BatterySaver_UsagePageNoFriendlyNameCollision";
        v127 = SystemSettings::DataModel::PropValueHelper::CreateString(v126, a3);
        v128 = v127;
        if ( v127 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25E,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v127,
            v161);
          return v128;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180068990, v122) )
      {
        v164 = 0;
        v131 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                           (char *)this + 320,
                                           v129,
                                           v130);
        v133 = SystemSettings::BatteryUsageHandlers::AppListEntry2::formatAppUsagePercentage(
                 v132,
                 *((double *)this + 36),
                 v131,
                 &v164);
        v134 = v133;
        if ( v133 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x266,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v133,
            v161);
          return v134;
        }
        v135 = SystemSettings::DataModel::PropValueHelper::CreateString(v164, a3);
        v136 = v135;
        if ( v135 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26E,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v135,
            v161);
          return v136;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069EC8, v130) )
      {
        v139 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                           (char *)this + 352,
                                           v137,
                                           v138);
        if ( SystemSettings::BatteryUsageHandlers::AppListEntry2::IsAppSystemComponent(v140, v139) )
        {
          v141 = SystemSettings::DataModel::PropValueHelper::CreateString(L"SettingsPageSystemComponents", a3);
          v142 = v141;
          if ( v141 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x275,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
              (const char *)(unsigned int)v141,
              v161);
            return v142;
          }
        }
        else
        {
          v143 = SystemSettings::DataModel::PropValueHelper::CreateString(L"SettingsPageInstalledApps", a3);
          v144 = v143;
          if ( v143 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x279,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
              (const char *)(unsigned int)v143,
              v161);
            return v144;
          }
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069FF8, v138) )
      {
        v147 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                           (char *)this + 352,
                                           v145,
                                           v146);
        if ( SystemSettings::BatteryUsageHandlers::AppListEntry2::IsAppSystemComponent(v148, v147) )
        {
          v149 = SystemSettings::DataModel::PropValueHelper::CreateString(
                   L"SystemSettings_StorageSense_HiddenSystemComponentsAdvancedPageLink",
                   a3);
          v150 = v149;
          if ( v149 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x280,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
              (const char *)(unsigned int)v149,
              v161);
            return v150;
          }
        }
        else
        {
          v151 = SystemSettings::DataModel::PropValueHelper::CreateString(
                   L"SystemSettings_StorageSense_HiddenAppAdvancedPageLink",
                   a3);
          v152 = v151;
          if ( v151 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x284,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
              (const char *)(unsigned int)v151,
              v161);
            return v152;
          }
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18006A018, v146) )
      {
        v155 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                           (char *)this + 352,
                                           v153,
                                           v154);
        if ( SystemSettings::BatteryUsageHandlers::AppListEntry2::IsAppSystemComponent(v156, v155) )
        {
          v157 = SystemSettings::DataModel::PropValueHelper::CreateString(
                   L"SystemSettings_StorageSense_HiddenSystemComponentsAdvancedPageLink",
                   a3);
          v158 = v157;
          if ( v157 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x28B,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
              (const char *)(unsigned int)v157,
              v161);
            return v158;
          }
        }
        else
        {
          v159 = SystemSettings::DataModel::PropValueHelper::CreateString(
                   L"SystemSettings_StorageSense_HiddenAppAdvancedPageLink",
                   a3);
          v160 = v159;
          if ( v159 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x28F,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
              (const char *)(unsigned int)v159,
              v161);
            return v160;
          }
        }
        return 0;
      }
      result = -2147024809;
    }
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x29D,
             (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
             v9);
  }
  return result;
}

```

## disassembly

```asm
0x18004ce90  mov     [rsp+arg_18], rbx
0x18004ce95  push    rsi
0x18004ce96  push    rdi
0x18004ce97  push    r12
0x18004ce99  push    r14
0x18004ce9b  push    r15
0x18004ce9d  sub     rsp, 0B0h
0x18004cea4  mov     r14, r8
0x18004cea7  mov     rdi, rdx
0x18004ceaa  mov     rbx, rcx
0x18004cead  xor     r12d, r12d
0x18004ceb0  mov     [r8], r12
0x18004ceb3  lea     rdx, stru_1800652A0; HSTRING
0x18004ceba  mov     rcx, rdi; this
0x18004cebd  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004cec2  test    al, al
0x18004cec4  jz      short loc_18004CF08
0x18004cec6  mov     rax, [rbx]
0x18004cec9  mov     rdx, r14
0x18004cecc  mov     rcx, rbx
0x18004cecf  mov     rax, [rax+0E0h]
0x18004ced6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cedb  mov     ebx, eax
0x18004cedd  test    eax, eax
0x18004cedf  jns     loc_18004DD83
0x18004cee5  mov     rcx, [rsp+0D8h]; this
0x18004ceed  mov     r9d, eax; char *
0x18004cef0  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004cef7  mov     edx, 191h; void *
0x18004cefc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cf01  mov     eax, ebx
0x18004cf03  jmp     loc_18004DD92
0x18004cf08  lea     rdx, stru_180067F38; HSTRING
0x18004cf0f  mov     rcx, rdi; this
0x18004cf12  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004cf17  test    al, al
0x18004cf19  jz      short loc_18004CF5D
0x18004cf1b  mov     rax, [rbx]
0x18004cf1e  mov     rdx, r14
0x18004cf21  mov     rcx, rbx
0x18004cf24  mov     rax, [rax+0E8h]
0x18004cf2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf30  mov     ebx, eax
0x18004cf32  test    eax, eax
0x18004cf34  jns     loc_18004DD83
0x18004cf3a  mov     rcx, [rsp+0D8h]; this
0x18004cf42  mov     r9d, eax; char *
0x18004cf45  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004cf4c  mov     edx, 195h; void *
0x18004cf51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cf56  mov     eax, ebx
0x18004cf58  jmp     loc_18004DD92
0x18004cf5d  lea     rdx, stru_180069778; HSTRING
0x18004cf64  mov     rcx, rdi; this
0x18004cf67  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004cf6c  test    al, al
0x18004cf6e  jz      short loc_18004CFAD
0x18004cf70  mov     rdx, r14; struct IInspectable **
0x18004cf73  movsd   xmm0, qword ptr [rbx+120h]; double
0x18004cf7b  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x18004cf80  mov     ebx, eax
0x18004cf82  test    eax, eax
0x18004cf84  jns     loc_18004DD83
0x18004cf8a  mov     rcx, [rsp+0D8h]; this
0x18004cf92  mov     r9d, eax; char *
0x18004cf95  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004cf9c  mov     edx, 19Bh; void *
0x18004cfa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cfa6  mov     eax, ebx
0x18004cfa8  jmp     loc_18004DD92
0x18004cfad  lea     rdx, stru_180069760; HSTRING
0x18004cfb4  mov     rcx, rdi; this
0x18004cfb7  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004cfbc  test    al, al
0x18004cfbe  jz      short loc_18004CFFB
0x18004cfc0  mov     rdx, r14; struct IInspectable **
0x18004cfc3  mov     cl, [rbx+188h]; unsigned __int8
0x18004cfc9  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18004cfce  mov     ebx, eax
0x18004cfd0  test    eax, eax
0x18004cfd2  jns     loc_18004DD83
0x18004cfd8  mov     rcx, [rsp+0D8h]; this
0x18004cfe0  mov     r9d, eax; char *
0x18004cfe3  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004cfea  mov     edx, 19Fh; void *
0x18004cfef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cff4  mov     eax, ebx
0x18004cff6  jmp     loc_18004DD92
0x18004cffb  lea     rdx, stru_1800697A8; HSTRING
0x18004d002  mov     rcx, rdi; this
0x18004d005  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004d00a  test    al, al
0x18004d00c  jz      short loc_18004D04B
0x18004d00e  mov     rdx, r14; struct IInspectable **
0x18004d011  movsd   xmm0, qword ptr [rbx+120h]; double
0x18004d019  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x18004d01e  mov     ebx, eax
0x18004d020  test    eax, eax
0x18004d022  jns     loc_18004DD83
0x18004d028  mov     rcx, [rsp+0D8h]; this
0x18004d030  mov     r9d, eax; char *
0x18004d033  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004d03a  mov     edx, 1A3h; void *
0x18004d03f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d044  mov     eax, ebx
0x18004d046  jmp     loc_18004DD92
0x18004d04b  lea     rdx, stru_180069790; HSTRING
0x18004d052  mov     rcx, rdi; this
0x18004d055  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004d05a  test    al, al
0x18004d05c  jz      short loc_18004D0D5
0x18004d05e  lea     rcx, [rbx+0F8h]
0x18004d065  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d06a  xor     r9d, r9d
0x18004d06d  lea     r8, word_180065238
0x18004d074  mov     rdx, [rbx+108h]
0x18004d07b  mov     rcx, rax
0x18004d07e  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004d083  test    al, al
0x18004d085  jz      short loc_18004D091
0x18004d087  mov     eax, 80004005h
0x18004d08c  jmp     loc_18004DD92
0x18004d091  lea     rcx, [rbx+0F8h]
0x18004d098  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d09d  mov     rdx, r14; struct IInspectable **
0x18004d0a0  mov     rcx, rax; unsigned __int16 *
0x18004d0a3  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18004d0a8  mov     ebx, eax
0x18004d0aa  test    eax, eax
0x18004d0ac  jns     loc_18004DD83
0x18004d0b2  mov     rcx, [rsp+0D8h]; this
0x18004d0ba  mov     r9d, eax; char *
0x18004d0bd  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004d0c4  mov     edx, 1AEh; void *
0x18004d0c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d0ce  mov     eax, ebx
0x18004d0d0  jmp     loc_18004DD92
0x18004d0d5  lea     rdx, stru_180069800; HSTRING
0x18004d0dc  mov     rcx, rdi; this
0x18004d0df  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004d0e4  test    al, al
0x18004d0e6  jz      loc_18004D1E0
0x18004d0ec  lea     rcx, [rbx+0F8h]
0x18004d0f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d0f8  xor     r9d, r9d
0x18004d0fb  lea     r8, word_180065238
0x18004d102  mov     rdx, [rbx+108h]
0x18004d109  mov     rcx, rax
0x18004d10c  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004d111  test    al, al
0x18004d113  jz      short loc_18004D11F
0x18004d115  mov     eax, 80004005h
0x18004d11a  jmp     loc_18004DD92
0x18004d11f  mov     [rsp+0D8h+string], r12
0x18004d124  lea     rcx, [rsp+0D8h+string]
0x18004d129  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d12e  lea     rcx, [rbx+0F8h]
0x18004d135  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d13a  lea     r9, [rsp+0D8h+string]
0x18004d13f  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x18004d146  xor     edx, edx
0x18004d148  mov     rcx, rax
0x18004d14b  call    cs:__imp_CreateRandomAccessStreamOnFile
0x18004d151  mov     ebx, eax
0x18004d153  test    eax, eax
0x18004d155  jns     short loc_18004D184
0x18004d157  mov     rcx, [rsp+0D8h]; this
0x18004d15f  mov     r9d, eax; char *
0x18004d162  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004d169  mov     edx, 1B8h; void *
0x18004d16e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d173  lea     rcx, [rsp+0D8h+string]
0x18004d178  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d17d  mov     eax, ebx
0x18004d17f  jmp     loc_18004DD92
0x18004d184  mov     rcx, [rsp+0D8h+string]
0x18004d189  mov     rax, [rcx]
0x18004d18c  mov     r8, r14
0x18004d18f  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18004d196  mov     rax, [rax]
0x18004d199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d19e  mov     ebx, eax
0x18004d1a0  test    eax, eax
0x18004d1a2  jns     short loc_18004D1D1
0x18004d1a4  mov     rcx, [rsp+0D8h]; this
0x18004d1ac  mov     r9d, eax; char *
0x18004d1af  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004d1b6  mov     edx, 1BAh; void *
0x18004d1bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d1c0  lea     rcx, [rsp+0D8h+string]
0x18004d1c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d1ca  mov     eax, ebx
0x18004d1cc  jmp     loc_18004DD92
0x18004d1d1  lea     rcx, [rsp+0D8h+string]
0x18004d1d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d1db  jmp     loc_18004DD83
0x18004d1e0  lea     rdx, stru_1800697E0; HSTRING
0x18004d1e7  mov     rcx, rdi; this
0x18004d1ea  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004d1ef  test    al, al
0x18004d1f1  jz      short loc_18004D253
0x18004d1f3  movzx   ecx, byte ptr [rbx+119h]
0x18004d1fa  movzx   eax, byte ptr [rbx+118h]
0x18004d201  shl     eax, 8
0x18004d204  or      ecx, eax
0x18004d206  shl     ecx, 8
0x18004d209  movzx   eax, byte ptr [rbx+11Ah]
0x18004d210  or      ecx, eax
0x18004d212  shl     ecx, 8
0x18004d215  movzx   eax, byte ptr [rbx+11Bh]
0x18004d21c  or      ecx, eax; unsigned int
0x18004d21e  mov     rdx, r14; struct IInspectable **
0x18004d221  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x18004d226  mov     ebx, eax
0x18004d228  test    eax, eax
0x18004d22a  jns     loc_18004DD83
0x18004d230  mov     rcx, [rsp+0D8h]; this
0x18004d238  mov     r9d, eax; char *
0x18004d23b  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004d242  mov     edx, 1C0h; void *
0x18004d247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d24c  mov     eax, ebx
0x18004d24e  jmp     loc_18004DD92
0x18004d253  lea     rdx, stru_180069840; HSTRING
0x18004d25a  mov     rcx, rdi; this
0x18004d25d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004d262  test    al, al
0x18004d264  jz      short loc_18004D2D2
0x18004d266  lea     rdx, [rbx+0F8h]
0x18004d26d  mov     rcx, rdx
0x18004d270  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d275  xor     r9d, r9d
0x18004d278  lea     r8, word_180065238
0x18004d27f  mov     rdx, [rdx+10h]
0x18004d283  mov     rcx, rax
0x18004d286  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004d28b  test    al, al
0x18004d28d  jnz     short loc_18004D29A
0x18004d28f  cmp     [rbx+180h], r12d
0x18004d296  mov     cl, 1
0x18004d298  jz      short loc_18004D29D
0x18004d29a  mov     cl, r12b; unsigned __int8
0x18004d29d  mov     rdx, r14; struct IInspectable **
0x18004d2a0  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18004d2a5  mov     ebx, eax
0x18004d2a7  test    eax, eax
0x18004d2a9  jns     loc_18004DD83
0x18004d2af  mov     rcx, [rsp+0D8h]; this
0x18004d2b7  mov     r9d, eax; char *
0x18004d2ba  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004d2c1  mov     edx, 1C5h; void *
0x18004d2c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d2cb  mov     eax, ebx
0x18004d2cd  jmp     loc_18004DD92
0x18004d2d2  lea     rdx, stru_180069E50; HSTRING
0x18004d2d9  mov     rcx, rdi; this
0x18004d2dc  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004d2e1  test    al, al
0x18004d2e3  jz      loc_18004D5F4
0x18004d2e9  mov     ecx, 200h; unsigned __int64
0x18004d2ee  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004d2f3  mov     r15, rax
0x18004d2f6  mov     [rsp+0D8h+var_90], r12
0x18004d2fb  mov     [rsp+0D8h+var_60], r12
0x18004d300  mov     [rsp+0D8h+var_68], r12
0x18004d305  mov     [rsp+0D8h+string], r12
0x18004d30a  xorps   xmm0, xmm0
0x18004d30d  movdqu  xmmword ptr [rsp+0D8h+var_88], xmm0
0x18004d313  mov     [rsp+0D8h+var_78], r12
0x18004d318  lea     rdx, [rsp+0D8h+var_88]
0x18004d31d  mov     ecx, 2415h; uID
0x18004d322  call    ?GetResourceString@BatteryUsageHelper@DataModel@SystemSettings@@SAJIAEAV?$vector@GV?$allocator@G@std@@@std@@@Z; SystemSettings::DataModel::BatteryUsageHelper::GetResourceString(uint,std::vector<ushort> &)
0x18004d327  mov     edi, eax
0x18004d329  test    eax, eax
0x18004d32b  jns     short loc_18004D35B
0x18004d32d  mov     rcx, [rsp+0D8h]; this
0x18004d335  mov     r9d, eax; char *
0x18004d338  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004d33f  mov     edx, 1CEh; void *
0x18004d344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d349  nop
0x18004d34a  lea     rcx, [rsp+0D8h+var_88]
0x18004d34f  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004d354  mov     eax, edi
0x18004d356  jmp     loc_18004DD92
0x18004d35b  lea     r9, [rsp+0D8h+var_90]; HSTRING *
0x18004d360  mov     r8, [rsp+0D8h+var_88]; unsigned __int16 *
0x18004d365  movsd   xmm1, qword ptr [rbx+130h]; double
0x18004d36d  call    ?formatAppUsagePercentage@AppListEntry2@BatteryUsageHandlers@SystemSettings@@AEAAJNPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::BatteryUsageHandlers::AppListEntry2::formatAppUsagePercentage(double,ushort const *,HSTRING__ * *)
0x18004d372  mov     edi, eax
0x18004d374  test    eax, eax
0x18004d376  jns     short loc_18004D3A6
0x18004d378  mov     rcx, [rsp+0D8h]; this
0x18004d380  mov     r9d, eax; char *
0x18004d383  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004d38a  mov     edx, 1CFh; void *
0x18004d38f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d394  nop
0x18004d395  lea     rcx, [rsp+0D8h+var_88]
0x18004d39a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
  ... truncated ...
```
