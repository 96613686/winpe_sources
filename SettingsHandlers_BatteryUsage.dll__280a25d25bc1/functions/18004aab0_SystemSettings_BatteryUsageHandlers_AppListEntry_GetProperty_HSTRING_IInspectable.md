# SystemSettings::BatteryUsageHandlers::AppListEntry::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x18004aab0`
- end: `0x18004b511`
- name: `?GetProperty@AppListEntry@BatteryUsageHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `2657`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::AppListEntry *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004cfc`
- `0x18000a13c`
- `0x18000e7f0`
- `0x18000fa78`
- `0x1800171c0`
- `0x1800177e0`
- `0x180017834`
- `0x18001e360`
- `0x180023c30`
- `0x18002aab0`
- `0x18003cedc`
- `0x1800430a4`
- `0x180043908`
- `0x18004a55c`
- `0x18004a5bc`
- `0x18004a814`
- `0x18004aab0`
- `0x18004b7b4`
- `0x18004b824`
- `0x18004b8fc`
- `0x18004b9f0`
- `0x18004c51c`
- `0x1800513a4`
- `0x18005a010`

## import_xrefs

- `SHCORE!CreateRandomAccessStreamOnFile` at `0x18004ad62`
- `SHCORE!CreateRandomAccessStreamOnFile` at `0x18004ad62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b1e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b1e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b1ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall SystemSettings::BatteryUsageHandlers::AppListEntry::GetProperty(
        SystemSettings::BatteryUsageHandlers::AppListEntry *this,
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
  int v46; // eax
  int v47; // ebx
  const unsigned __int16 *v48; // r8
  int v49; // eax
  int v50; // ebx
  const unsigned __int16 *v51; // r8
  int v52; // eax
  int v53; // ebx
  SystemSettings::BatteryUsageHandlers::AppListEntry *v54; // rcx
  const unsigned __int16 *v55; // r8
  SystemSettings::BatteryUsageHandlers::AppListEntry *v56; // rcx
  const unsigned __int16 *v57; // r8
  const unsigned __int16 *v58; // r8
  int v59; // eax
  int v60; // ebx
  const unsigned __int16 *v61; // r8
  const unsigned __int16 *CurrentPolicyDescriptionString; // rax
  int v63; // eax
  int v64; // ebx
  const unsigned __int16 *v65; // r8
  int v66; // eax
  int v67; // ebx
  const unsigned __int16 *v68; // r8
  unsigned __int8 IsAppManagementOptionsSupported; // al
  int v70; // eax
  int v71; // ebx
  const unsigned __int16 *v72; // r8
  __int64 v73; // r8
  SystemSettings::BatteryUsageHandlers::AppIdentity *v74; // rax
  __int64 v75; // rcx
  int PackageFamilyNameFromAppIdentity; // ebx
  const unsigned __int16 *v77; // r8
  int v78; // eax
  int v79; // ebx
  const unsigned __int16 *v80; // r8
  int v81; // eax
  int v82; // ebx
  const unsigned __int16 *v83; // r8
  unsigned __int8 IsSystemManaged; // al
  int v85; // eax
  int v86; // ebx
  const unsigned __int16 *v87; // r8
  unsigned __int8 IsBackgroundTasksPolicyManageable; // al
  int v89; // eax
  int v90; // ebx
  const unsigned __int16 *v91; // r8
  __int64 v92; // rax
  __int64 PackageFullNameFromFamilyName; // rax
  int TaskPolicy; // eax
  int v95; // ebx
  int v96; // eax
  int v97; // ebx
  const unsigned __int16 *v98; // r8
  unsigned __int8 IsBackgroundTasksControlUserConfigurable; // al
  int v100; // eax
  int v101; // ebx
  const unsigned __int16 *v102; // r8
  unsigned __int8 v103; // al
  int v104; // eax
  int v105; // ebx
  __int64 v106; // r8
  __int64 v107; // rax
  __int64 v108; // rcx
  char DoesFriendlyNameCollide; // al
  const unsigned __int16 *v110; // rcx
  int v111; // eax
  int v112; // ebx
  int v113[8]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v114[48]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HSTRING string; // [rsp+90h] [rbp+18h] BYREF

  *a3 = 0;
  IsHstringEqual = SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800652A0, (const unsigned __int16 *)a3);
  try
  {
    if ( IsHstringEqual )
    {
      v8 = (*(__int64 (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry *, struct IInspectable **))(*(_QWORD *)this + 224LL))(
             this,
             a3);
      v10 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x152,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)v8,
          v113[0]);
        return v10;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180067F38, v7) )
    {
      v13 = (*(__int64 (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry *, struct IInspectable **))(*(_QWORD *)this + 232LL))(
              this,
              a3);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x156,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)v13,
          v113[0]);
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
          (void *)0x15C,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)Double,
          v113[0]);
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
          (void *)0x160,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)Boolean,
          v113[0]);
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
          (void *)0x164,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)v22,
          v113[0]);
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
          (void *)0x16F,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)v30,
          v113[0]);
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
          (void *)0x179,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)v38,
          v113[0]);
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
          (void *)0x17B,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)v40,
          v113[0]);
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
                 | ((*((unsigned __int8 *)this + 281) | (*((unsigned __int8 *)this + 280) << 8)) << 8)) << 8),
                 a3);
      v44 = UInt32;
      if ( UInt32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)UInt32,
          v113[0]);
        return v44;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069840, v42) )
    {
      v46 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_DWORD *)this + 96) == 0, a3);
      v47 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x185,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)v46,
          v113[0]);
        return v47;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069820, v45) )
    {
      v49 = SystemSettings::DataModel::PropValueHelper::CreateDouble(*((double *)this + 37), a3);
      v50 = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18B,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)v49,
          v113[0]);
        return v50;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069880, v48) )
    {
      v52 = SystemSettings::DataModel::PropValueHelper::CreateDouble(*((double *)this + 38), a3);
      v53 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x191,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
          (const char *)(unsigned int)v52,
          v113[0]);
        return v53;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069860, v51) )
    {
      string = 0;
      result = SystemSettings::BatteryUsageHandlers::AppListEntry::formatAppUsageTime(
                 v54,
                 (double)*((int *)this + 78) / 3600000.0,
                 &string);
      if ( result < 0 )
        return result;
      result = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
      if ( result < 0 )
        return result;
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800698D0, v55) )
    {
      string = 0;
      result = SystemSettings::BatteryUsageHandlers::AppListEntry::formatAppUsageTime(
                 v56,
                 (double)*((int *)this + 79) / 3600000.0,
                 &string);
      if ( result >= 0 )
      {
        result = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
        if ( result >= 0 )
          return 0;
      }
    }
    else
    {
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800698A0, v57) )
      {
        v59 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(1u, a3);
        v60 = v59;
        if ( v59 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AB,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v59,
            v113[0]);
          return v60;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069920, v58) )
      {
        CurrentPolicyDescriptionString = SystemSettings::BatteryUsageHandlers::AppListEntry::GetCurrentPolicyDescriptionString(this);
        v63 = SystemSettings::DataModel::PropValueHelper::CreateString(CurrentPolicyDescriptionString, a3);
        v64 = v63;
        if ( v63 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B1,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v63,
            v113[0]);
          return v64;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800698F0, v61) )
      {
        v66 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(0, a3);
        v67 = v66;
        if ( v66 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B5,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v66,
            v113[0]);
          return v67;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069980, v65) )
      {
        IsAppManagementOptionsSupported = SystemSettings::BatteryUsageHandlers::AppListEntry::IsAppManagementOptionsSupported(this);
        v70 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsAppManagementOptionsSupported, a3);
        v71 = v70;
        if ( v70 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B9,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v70,
            v113[0]);
          return v71;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069950, v68) )
      {
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v74 = SystemSettings::BatteryUsageHandlers::AppIdentity::AppIdentity(
                (SystemSettings::BatteryUsageHandlers::AppIdentity *)v114,
                (SystemSettings::BatteryUsageHandlers::AppListEntry *)((char *)this + 352),
                v73);
        PackageFamilyNameFromAppIdentity = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFamilyNameFromAppIdentity(
                                             v75,
                                             v74,
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
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800699C8, v72) )
      {
        v78 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(1u, a3);
        v79 = v78;
        if ( v78 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1C6,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v78,
            v113[0]);
          return v79;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800699B0, v77) )
      {
        v81 = SystemSettings::DataModel::PropValueHelper::CreateDouble(1.0, a3);
        v82 = v81;
        if ( v81 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CA,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v81,
            v113[0]);
          return v82;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069A40, v80) )
      {
        IsSystemManaged = SystemSettings::BatteryUsageHandlers::AppListEntry::IsSystemManaged(this);
        v85 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsSystemManaged, a3);
        v86 = v85;
        if ( v85 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CE,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v85,
            v113[0]);
          return v86;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069A00, v83) )
      {
        IsBackgroundTasksPolicyManageable = SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksPolicyManageable(this);
        v89 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsBackgroundTasksPolicyManageable, a3);
        v90 = v89;
        if ( v89 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D4,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v89,
            v113[0]);
          return v90;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069AC8, v87) )
      {
        LODWORD(string) = 0;
        v92 = std::wstring::wstring((__int64)v113, (__int64)this + 352, (__int64)v91);
        PackageFullNameFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(
                                          &SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton,
                                          v114,
                                          v92);
        TaskPolicy = SystemSettings::BatteryUsageHandlers::GetTaskPolicy(PackageFullNameFromFamilyName, &string);
        v95 = TaskPolicy;
        if ( TaskPolicy < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1DB,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)TaskPolicy,
            v113[0]);
          return v95;
        }
        v96 = SystemSettings::DataModel::PropValueHelper::CreateBoolean((_DWORD)string == 3, a3);
        v97 = v96;
        if ( v96 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1DD,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v96,
            v113[0]);
          return v97;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069A70, v91) )
      {
        IsBackgroundTasksControlUserConfigurable = SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksControlUserConfigurable(this);
        v100 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(IsBackgroundTasksControlUserConfigurable, a3);
        v101 = v100;
        if ( v100 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1EA,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v100,
            v113[0]);
          return v101;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069B20, v98) )
      {
        v103 = SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksControlUserConfigurable(this);
        v104 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v103, a3);
        v105 = v104;
        if ( v104 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F0,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v104,
            v113[0]);
          return v105;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069AE8, v102) )
      {
        v107 = std::wstring::wstring((__int64)v114, (__int64)this + 320, v106);
        DoesFriendlyNameCollide = SystemSettings::BatteryUsageHandlers::FriendlyNameCollisionTracker::DoesFriendlyNameCollide(
                                    v108,
                                    v107);
        v110 = L"SystemSettings_BatterySaver_UsagePageFriendlyNameCollision";
        if ( !DoesFriendlyNameCollide )
          v110 = L"SystemSettings_BatterySaver_UsagePageNoFriendlyNameCollision";
        v111 = SystemSettings::DataModel::PropValueHelper::CreateString(v110, a3);
        v112 = v111;
        if ( v111 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1FA,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
            (const char *)(unsigned int)v111,
            v113[0]);
          return v112;
        }
        return 0;
      }
      result = -2147024809;
    }
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x203,
                        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
                        v9);
    return (int)string;
  }
  return result;
}

```

## disassembly

```asm
0x18004aab0  mov     [rsp+arg_0], rbx
0x18004aab5  mov     [rsp+arg_8], rsi
0x18004aaba  push    rdi
0x18004aabb  sub     rsp, 70h
0x18004aabf  mov     rdi, r8
0x18004aac2  mov     rbx, rdx
0x18004aac5  mov     rsi, rcx
0x18004aac8  mov     qword ptr [r8], 0
0x18004aacf  lea     rdx, stru_1800652A0; HSTRING
0x18004aad6  mov     rcx, rbx; this
0x18004aad9  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004aade  test    al, al
0x18004aae0  jz      short loc_18004AB21
0x18004aae2  mov     rax, [rsi]
0x18004aae5  mov     rdx, rdi
0x18004aae8  mov     rcx, rsi
0x18004aaeb  mov     rax, [rax+0E0h]
0x18004aaf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aaf7  mov     ebx, eax
0x18004aaf9  test    eax, eax
0x18004aafb  jns     loc_18004B4EC
0x18004ab01  mov     rcx, [rsp+78h]; this
0x18004ab06  mov     r9d, eax; char *
0x18004ab09  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004ab10  mov     edx, 152h; void *
0x18004ab15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ab1a  mov     eax, ebx
0x18004ab1c  jmp     loc_18004B4FE
0x18004ab21  lea     rdx, stru_180067F38; HSTRING
0x18004ab28  mov     rcx, rbx; this
0x18004ab2b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004ab30  test    al, al
0x18004ab32  jz      short loc_18004AB73
0x18004ab34  mov     rax, [rsi]
0x18004ab37  mov     rdx, rdi
0x18004ab3a  mov     rcx, rsi
0x18004ab3d  mov     rax, [rax+0E8h]
0x18004ab44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab49  mov     ebx, eax
0x18004ab4b  test    eax, eax
0x18004ab4d  jns     loc_18004B4EC
0x18004ab53  mov     rcx, [rsp+78h]; this
0x18004ab58  mov     r9d, eax; char *
0x18004ab5b  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004ab62  mov     edx, 156h; void *
0x18004ab67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ab6c  mov     eax, ebx
0x18004ab6e  jmp     loc_18004B4FE
0x18004ab73  lea     rdx, stru_180069778; HSTRING
0x18004ab7a  mov     rcx, rbx; this
0x18004ab7d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004ab82  test    al, al
0x18004ab84  jz      short loc_18004ABC0
0x18004ab86  mov     rdx, rdi; struct IInspectable **
0x18004ab89  movsd   xmm0, qword ptr [rsi+120h]; double
0x18004ab91  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x18004ab96  mov     ebx, eax
0x18004ab98  test    eax, eax
0x18004ab9a  jns     loc_18004B4EC
0x18004aba0  mov     rcx, [rsp+78h]; this
0x18004aba5  mov     r9d, eax; char *
0x18004aba8  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004abaf  mov     edx, 15Ch; void *
0x18004abb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004abb9  mov     eax, ebx
0x18004abbb  jmp     loc_18004B4FE
0x18004abc0  lea     rdx, stru_180069760; HSTRING
0x18004abc7  mov     rcx, rbx; this
0x18004abca  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004abcf  test    al, al
0x18004abd1  jz      short loc_18004AC0B
0x18004abd3  mov     rdx, rdi; struct IInspectable **
0x18004abd6  mov     cl, [rsi+188h]; unsigned __int8
0x18004abdc  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18004abe1  mov     ebx, eax
0x18004abe3  test    eax, eax
0x18004abe5  jns     loc_18004B4EC
0x18004abeb  mov     rcx, [rsp+78h]; this
0x18004abf0  mov     r9d, eax; char *
0x18004abf3  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004abfa  mov     edx, 160h; void *
0x18004abff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ac04  mov     eax, ebx
0x18004ac06  jmp     loc_18004B4FE
0x18004ac0b  lea     rdx, stru_1800697A8; HSTRING
0x18004ac12  mov     rcx, rbx; this
0x18004ac15  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004ac1a  test    al, al
0x18004ac1c  jz      short loc_18004AC58
0x18004ac1e  mov     rdx, rdi; struct IInspectable **
0x18004ac21  movsd   xmm0, qword ptr [rsi+120h]; double
0x18004ac29  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x18004ac2e  mov     ebx, eax
0x18004ac30  test    eax, eax
0x18004ac32  jns     loc_18004B4EC
0x18004ac38  mov     rcx, [rsp+78h]; this
0x18004ac3d  mov     r9d, eax; char *
0x18004ac40  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004ac47  mov     edx, 164h; void *
0x18004ac4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ac51  mov     eax, ebx
0x18004ac53  jmp     loc_18004B4FE
0x18004ac58  lea     rdx, stru_180069790; HSTRING
0x18004ac5f  mov     rcx, rbx; this
0x18004ac62  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004ac67  test    al, al
0x18004ac69  jz      short loc_18004ACDF
0x18004ac6b  lea     rcx, [rsi+0F8h]
0x18004ac72  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ac77  xor     r9d, r9d
0x18004ac7a  lea     r8, word_180065238
0x18004ac81  mov     rdx, [rsi+108h]
0x18004ac88  mov     rcx, rax
0x18004ac8b  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004ac90  test    al, al
0x18004ac92  jz      short loc_18004AC9E
0x18004ac94  mov     eax, 80004005h
0x18004ac99  jmp     loc_18004B4FE
0x18004ac9e  lea     rcx, [rsi+0F8h]
0x18004aca5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004acaa  mov     rdx, rdi; struct IInspectable **
0x18004acad  mov     rcx, rax; unsigned __int16 *
0x18004acb0  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18004acb5  mov     ebx, eax
0x18004acb7  test    eax, eax
0x18004acb9  jns     loc_18004B4EC
0x18004acbf  mov     rcx, [rsp+78h]; this
0x18004acc4  mov     r9d, eax; char *
0x18004acc7  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004acce  mov     edx, 16Fh; void *
0x18004acd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004acd8  mov     eax, ebx
0x18004acda  jmp     loc_18004B4FE
0x18004acdf  lea     rdx, stru_180069800; HSTRING
0x18004ace6  mov     rcx, rbx; this
0x18004ace9  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004acee  test    al, al
0x18004acf0  jz      loc_18004ADFD
0x18004acf6  lea     rcx, [rsi+0F8h]
0x18004acfd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ad02  xor     r9d, r9d
0x18004ad05  lea     r8, word_180065238
0x18004ad0c  mov     rdx, [rsi+108h]
0x18004ad13  mov     rcx, rax
0x18004ad16  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004ad1b  test    al, al
0x18004ad1d  jz      short loc_18004AD29
0x18004ad1f  mov     eax, 80004005h
0x18004ad24  jmp     loc_18004B4FE
0x18004ad29  mov     [rsp+78h+string], 0
0x18004ad35  lea     rcx, [rsp+78h+string]
0x18004ad3d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ad42  lea     rcx, [rsi+0F8h]
0x18004ad49  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ad4e  lea     r9, [rsp+78h+string]
0x18004ad56  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x18004ad5d  xor     edx, edx
0x18004ad5f  mov     rcx, rax
0x18004ad62  call    cs:__imp_CreateRandomAccessStreamOnFile
0x18004ad68  mov     ebx, eax
0x18004ad6a  test    eax, eax
0x18004ad6c  jns     short loc_18004AD9B
0x18004ad6e  mov     rcx, [rsp+78h]; this
0x18004ad73  mov     r9d, eax; char *
0x18004ad76  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004ad7d  mov     edx, 179h; void *
0x18004ad82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ad87  lea     rcx, [rsp+78h+string]
0x18004ad8f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ad94  mov     eax, ebx
0x18004ad96  jmp     loc_18004B4FE
0x18004ad9b  mov     rcx, [rsp+78h+string]
0x18004ada3  mov     rax, [rcx]
0x18004ada6  mov     r8, rdi
0x18004ada9  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18004adb0  mov     rax, [rax]
0x18004adb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004adb8  mov     ebx, eax
0x18004adba  test    eax, eax
0x18004adbc  jns     short loc_18004ADEB
0x18004adbe  mov     rcx, [rsp+78h]; this
0x18004adc3  mov     r9d, eax; char *
0x18004adc6  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004adcd  mov     edx, 17Bh; void *
0x18004add2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004add7  lea     rcx, [rsp+78h+string]
0x18004addf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ade4  mov     eax, ebx
0x18004ade6  jmp     loc_18004B4FE
0x18004adeb  lea     rcx, [rsp+78h+string]
0x18004adf3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004adf8  jmp     loc_18004B4EC
0x18004adfd  lea     rdx, stru_1800697E0; HSTRING
0x18004ae04  mov     rcx, rbx; this
0x18004ae07  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004ae0c  test    al, al
0x18004ae0e  jz      short loc_18004AE6D
0x18004ae10  movzx   ecx, byte ptr [rsi+118h]
0x18004ae17  shl     ecx, 8
0x18004ae1a  movzx   eax, byte ptr [rsi+119h]
0x18004ae21  or      ecx, eax
0x18004ae23  shl     ecx, 8
0x18004ae26  movzx   eax, byte ptr [rsi+11Ah]
0x18004ae2d  or      ecx, eax
0x18004ae2f  shl     ecx, 8
0x18004ae32  movzx   eax, byte ptr [rsi+11Bh]
0x18004ae39  or      ecx, eax; unsigned int
0x18004ae3b  mov     rdx, rdi; struct IInspectable **
0x18004ae3e  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x18004ae43  mov     ebx, eax
0x18004ae45  test    eax, eax
0x18004ae47  jns     loc_18004B4EC
0x18004ae4d  mov     rcx, [rsp+78h]; this
0x18004ae52  mov     r9d, eax; char *
0x18004ae55  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004ae5c  mov     edx, 181h; void *
0x18004ae61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ae66  mov     eax, ebx
0x18004ae68  jmp     loc_18004B4FE
0x18004ae6d  lea     rdx, stru_180069840; HSTRING
0x18004ae74  mov     rcx, rbx; this
0x18004ae77  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004ae7c  test    al, al
0x18004ae7e  jz      short loc_18004AEBC
0x18004ae80  cmp     dword ptr [rsi+180h], 0
0x18004ae87  setz    cl; unsigned __int8
0x18004ae8a  mov     rdx, rdi; struct IInspectable **
0x18004ae8d  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18004ae92  mov     ebx, eax
0x18004ae94  test    eax, eax
0x18004ae96  jns     loc_18004B4EC
0x18004ae9c  mov     rcx, [rsp+78h]; this
0x18004aea1  mov     r9d, eax; char *
0x18004aea4  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004aeab  mov     edx, 185h; void *
0x18004aeb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aeb5  mov     eax, ebx
0x18004aeb7  jmp     loc_18004B4FE
0x18004aebc  lea     rdx, stru_180069820; HSTRING
0x18004aec3  mov     rcx, rbx; this
0x18004aec6  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004aecb  test    al, al
0x18004aecd  jz      short loc_18004AF09
0x18004aecf  mov     rdx, rdi; struct IInspectable **
0x18004aed2  movsd   xmm0, qword ptr [rsi+128h]; double
0x18004aeda  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x18004aedf  mov     ebx, eax
0x18004aee1  test    eax, eax
0x18004aee3  jns     loc_18004B4EC
0x18004aee9  mov     rcx, [rsp+78h]; this
0x18004aeee  mov     r9d, eax; char *
0x18004aef1  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004aef8  mov     edx, 18Bh; void *
0x18004aefd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004af02  mov     eax, ebx
0x18004af04  jmp     loc_18004B4FE
0x18004af09  lea     rdx, stru_180069880; HSTRING
0x18004af10  mov     rcx, rbx; this
0x18004af13  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004af18  test    al, al
0x18004af1a  jz      short loc_18004AF56
0x18004af1c  mov     rdx, rdi; struct IInspectable **
0x18004af1f  movsd   xmm0, qword ptr [rsi+130h]; double
0x18004af27  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x18004af2c  mov     ebx, eax
0x18004af2e  test    eax, eax
0x18004af30  jns     loc_18004B4EC
0x18004af36  mov     rcx, [rsp+78h]; this
0x18004af3b  mov     r9d, eax; char *
0x18004af3e  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004af45  mov     edx, 191h; void *
0x18004af4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004af4f  mov     eax, ebx
0x18004af51  jmp     loc_18004B4FE
0x18004af56  lea     rdx, stru_180069860; HSTRING
0x18004af5d  mov     rcx, rbx; this
0x18004af60  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004af65  test    al, al
0x18004af67  jz      short loc_18004AFBD
0x18004af69  mov     [rsp+78h+string], 0
0x18004af75  mov     eax, [rsi+138h]
0x18004af7b  xorps   xmm1, xmm1
0x18004af7e  cvtsi2sd xmm1, rax
0x18004af83  divsd   xmm1, cs:__real@414b774000000000; double
0x18004af8b  lea     r8, [rsp+78h+string]; HSTRING *
0x18004af93  call    ?formatAppUsageTime@AppListEntry@BatteryUsageHandlers@SystemSettings@@AEAAJNPEAPEAUHSTRING__@@@Z; SystemSettings::BatteryUsageHandlers::AppListEntry::formatAppUsageTime(double,HSTRING__ * *)
0x18004af98  test    eax, eax
0x18004af9a  js      loc_18004B4FE
0x18004afa0  mov     rdx, rdi; struct IInspectable **
0x18004afa3  mov     rcx, [rsp+78h+string]; HSTRING
0x18004afab  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18004afb0  test    eax, eax
0x18004afb2  jns     loc_18004B4EC
0x18004afb8  jmp     loc_18004B4FE
0x18004afbd  lea     rdx, stru_1800698D0; HSTRING
0x18004afc4  mov     rcx, rbx; this
0x18004afc7  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004afcc  test    al, al
0x18004afce  jz      short loc_18004B024
0x18004afd0  mov     [rsp+78h+string], 0
  ... truncated ...
```
