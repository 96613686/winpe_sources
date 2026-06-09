# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::IsAppManagementSupported(SystemSettings::BatteryUsageHandlers::AppIdentity,bool *)

- ea: `0x180044eb0`
- end: `0x1800451e3`
- name: `?IsAppManagementSupported@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJUAppIdentity@23@PEA_N@Z`
- size: `819`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ded8`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18000a13c`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c78`
- `0x18002aab0`
- `0x18003b8e8`
- `0x18003bc74`
- `0x180044eb0`
- `0x1800457f0`
- `0x18004719c`
- `0x1800512e0`
- `0x18005203c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800450f2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800450f2`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800450dd`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800450dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044fef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044fef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045066`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::IsAppManagementSupported(
        __int64 a1,
        const struct SystemSettings::BatteryUsageHandlers::AppIdentity *a2,
        _BYTE *a3)
{
  __int64 result; // rax
  SystemSettings::BatteryUsageHandlers::AppIdentity *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  const char *v12; // r9
  __int64 *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // r8
  const WCHAR *v16; // rdi
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  unsigned int v20; // ebx
  PCWSTR StringRawBuffer; // rdx
  __int64 PackageFamilyNameFromPackageFullName; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  PCWSTR *i; // rbx
  SystemSettings::StorageSenseHandlers::CAppTileData *v26; // rbx
  int packageRelativeApplicationId; // [rsp+20h] [rbp-1F8h]
  HSTRING string; // [rsp+30h] [rbp-1E8h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+38h] [rbp-1E0h] BYREF
  __int64 v30; // [rsp+40h] [rbp-1D8h] BYREF
  UINT32 packageRelativeApplicationIdLength[2]; // [rsp+48h] [rbp-1D0h] BYREF
  SystemSettings::StorageSenseHandlers::CAppTileData *v32; // [rsp+50h] [rbp-1C8h] BYREF
  _BYTE v33[40]; // [rsp+58h] [rbp-1C0h] BYREF
  const struct SystemSettings::BatteryUsageHandlers::AppIdentity *v34; // [rsp+80h] [rbp-198h]
  _BYTE v35[32]; // [rsp+88h] [rbp-190h] BYREF
  _BYTE v36[40]; // [rsp+A8h] [rbp-170h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+D0h] [rbp-148h] BYREF
  WCHAR v38[72]; // [rsp+160h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v34 = a2;
  if ( *((_DWORD *)a2 + 8) > 1u )
  {
    *a3 = 0;
    std::wstring::_Tidy_deallocate(a2);
    return 0;
  }
  try
  {
    v30 = 0;
    string = 0;
    v6 = SystemSettings::BatteryUsageHandlers::AppIdentity::AppIdentity(
           (SystemSettings::BatteryUsageHandlers::AppIdentity *)v33,
           a2,
           (__int64)a3);
    v8 = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::LookupFriendlyName(v7, v35, v6);
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8, v9, v10);
    std::wstring::wstring((__int64)v36, v11);
    std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
      &qword_180079DC0,
      packageFamilyNameLength,
      v36);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v35);
    if ( *(_QWORD *)packageFamilyNameLength == qword_180079DC0 )
    {
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
      std::wstring::_Tidy_deallocate(a2);
      return 2147500037LL;
    }
    v13 = (__int64 *)(*(_QWORD *)packageFamilyNameLength + 64LL);
    Microsoft::WRL::ComPtr<IInspectable>::operator=<SystemSettings::BatteryUsageHandlers::IPackageInfo>(
      &v30,
      (__int64 *)(*(_QWORD *)packageFamilyNameLength + 64LL));
    if ( *((_DWORD *)a2 + 8) == 1 )
    {
      v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v14, v15);
      goto LABEL_10;
    }
    v17 = *v13;
    v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 72LL);
    WindowsDeleteString(string);
    string = 0;
    v19 = v18(v17, &string);
    v20 = v19;
    if ( v19 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      PackageFamilyNameFromPackageFullName = SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(
                                               v35,
                                               StringRawBuffer);
      v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                             PackageFamilyNameFromPackageFullName,
                             v23,
                             v24);
      std::wstring::_Tidy_deallocate(v35);
LABEL_10:
      for ( i = (PCWSTR *)&ShellBlockLists::AppsHiddenFromAppList;
            i != (PCWSTR *)&SystemSettings::BatteryUsageHandlers::DataDurationSelector::_sc_rgridpDurationValues;
            ++i )
      {
        packageFamilyNameLength[0] = 65;
        packageRelativeApplicationIdLength[0] = 66;
        if ( !ParseApplicationUserModelId(
                *i,
                packageFamilyNameLength,
                packageFamilyName,
                packageRelativeApplicationIdLength,
                v38)
          && !StrCmpIW(packageFamilyName, v16) )
        {
          *a3 = 0;
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          std::wstring::_Tidy_deallocate(a2);
          return 0;
        }
      }
      *(_QWORD *)packageRelativeApplicationIdLength = v30;
      packageFamilyNameLength[0] = 0;
      Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,IInspectable *>(
        &v32,
        packageFamilyNameLength,
        packageRelativeApplicationIdLength);
      v26 = v32;
      *a3 = SystemSettings::StorageSenseHandlers::CAppTileData::AreAdvancedOptionsSupported(v32);
      if ( v26 )
        (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::CAppTileData *))(*(_QWORD *)v26 + 16LL))(v26);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
      std::wstring::_Tidy_deallocate(a2);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x994,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v19,
      packageRelativeApplicationId);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    std::wstring::_Tidy_deallocate(a2);
    result = v20;
  }
  catch ( ... )
  {
    packageFamilyNameLength[0] = wil::details::in1diag3::Return_CaughtException(
                                   retaddr,
                                   (void *)0x9B9,
                                   (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
                                   v12);
    std::wstring::_Tidy_deallocate(v34);
    return packageFamilyNameLength[0];
  }
  return result;
}

```

## disassembly

```asm
0x180044eb0  mov     [rsp+arg_0], rbx
0x180044eb5  mov     [rsp+arg_18], rdi
0x180044eba  push    r12
0x180044ebc  push    r14
0x180044ebe  push    r15
0x180044ec0  sub     rsp, 200h
0x180044ec7  mov     rax, cs:__security_cookie
0x180044ece  xor     rax, rsp
0x180044ed1  mov     [rsp+218h+var_28], rax
0x180044ed9  mov     r15, r8
0x180044edc  mov     r14, rdx
0x180044edf  mov     [rsp+218h+var_198], rdx
0x180044ee7  cmp     dword ptr [rdx+20h], 1
0x180044eeb  jbe     short loc_180044F00
0x180044eed  mov     byte ptr [r8], 0
0x180044ef1  mov     rcx, r14
0x180044ef4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044ef9  xor     eax, eax
0x180044efb  jmp     loc_1800451B9
0x180044f00  mov     [rsp+218h+var_1D8], 0
0x180044f09  mov     [rsp+218h+string], 0
0x180044f12  lea     rcx, [rsp+218h+var_1C0]; this
0x180044f17  call    ??0AppIdentity@BatteryUsageHandlers@SystemSettings@@QEAA@AEBU012@@Z; SystemSettings::BatteryUsageHandlers::AppIdentity::AppIdentity(SystemSettings::BatteryUsageHandlers::AppIdentity const &)
0x180044f1c  mov     r8, rax
0x180044f1f  lea     rdx, [rsp+218h+var_190]
0x180044f27  call    ?LookupFriendlyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppIdentity@23@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::LookupFriendlyName(SystemSettings::BatteryUsageHandlers::AppIdentity)
0x180044f2c  nop
0x180044f2d  mov     rcx, rax
0x180044f30  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044f35  mov     rdx, rax
0x180044f38  lea     rcx, [rsp+218h+var_170]
0x180044f40  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180044f45  lea     r8, [rsp+218h+var_170]
0x180044f4d  lea     rdx, [rsp+218h+packageFamilyNameLength]
0x180044f52  lea     rcx, qword_180079DC0
0x180044f59  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180044f5e  lea     rcx, [rsp+218h+var_170]
0x180044f66  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044f6b  nop
0x180044f6c  lea     rcx, [rsp+218h+var_190]
0x180044f74  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044f79  mov     rax, qword ptr [rsp+218h+packageFamilyNameLength]
0x180044f7e  cmp     rax, cs:qword_180079DC0
0x180044f85  jnz     short loc_180044FB8
0x180044f87  mov     rcx, [rsp+218h+string]; string
0x180044f8c  call    cs:__imp_WindowsDeleteString
0x180044f92  mov     [rsp+218h+string], 0
0x180044f9b  lea     rcx, [rsp+218h+var_1D8]
0x180044fa0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044fa5  nop
0x180044fa6  mov     rcx, r14
0x180044fa9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044fae  mov     eax, 80004005h
0x180044fb3  jmp     loc_1800451B9
0x180044fb8  lea     rdi, [rax+40h]
0x180044fbc  mov     rdx, rdi
0x180044fbf  lea     rcx, [rsp+218h+var_1D8]
0x180044fc4  call    ??$?4UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEAAAEAV012@AEBV?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::operator=<SystemSettings::BatteryUsageHandlers::IPackageInfo>(Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo> const &)
0x180044fc9  cmp     dword ptr [r14+20h], 1
0x180044fce  jnz     short loc_180044FE0
0x180044fd0  mov     rcx, r14
0x180044fd3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044fd8  mov     rdi, rax
0x180044fdb  jmp     loc_180045094
0x180044fe0  mov     rdi, [rdi]
0x180044fe3  mov     rax, [rdi]
0x180044fe6  mov     rbx, [rax+48h]
0x180044fea  mov     rcx, [rsp+218h+string]; string
0x180044fef  call    cs:__imp_WindowsDeleteString
0x180044ff5  mov     [rsp+218h+string], 0
0x180044ffe  lea     rdx, [rsp+218h+string]
0x180045003  mov     rcx, rdi
0x180045006  mov     rax, rbx
0x180045009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004500e  mov     ebx, eax
0x180045010  test    eax, eax
0x180045012  jns     short loc_18004505F
0x180045014  mov     rcx, [rsp+218h]; this
0x18004501c  mov     r9d, eax; char *
0x18004501f  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180045026  mov     edx, 994h; void *
0x18004502b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045030  nop
0x180045031  mov     rcx, [rsp+218h+string]; string
0x180045036  call    cs:__imp_WindowsDeleteString
0x18004503c  mov     [rsp+218h+string], 0
0x180045045  lea     rcx, [rsp+218h+var_1D8]
0x18004504a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004504f  nop
0x180045050  mov     rcx, r14
0x180045053  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045058  mov     eax, ebx
0x18004505a  jmp     loc_1800451B9
0x18004505f  xor     edx, edx; length
0x180045061  mov     rcx, [rsp+218h+string]; string
0x180045066  call    cs:__imp_WindowsGetStringRawBuffer
0x18004506c  mov     rdx, rax
0x18004506f  lea     rcx, [rsp+218h+var_190]
0x180045077  call    ?GetPackageFamilyNameFromPackageFullName@BatteryUsageHandlers@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(ushort const *)
0x18004507c  mov     rcx, rax
0x18004507f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045084  mov     rdi, rax
0x180045087  lea     rcx, [rsp+218h+var_190]
0x18004508f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045094  lea     rbx, ?AppsHiddenFromAppList@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::AppsHiddenFromAppList
0x18004509b  lea     r12, ?_sc_rgridpDurationValues@DataDurationSelector@BatteryUsageHandlers@SystemSettings@@0QBUDURATION_VALUE_PAIR@123@B; SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR const near * const SystemSettings::BatteryUsageHandlers::DataDurationSelector::_sc_rgridpDurationValues
0x1800450a2  lea     rdx, [rsp+218h+packageFamilyNameLength]; packageFamilyNameLength
0x1800450a7  cmp     rbx, r12
0x1800450aa  jz      loc_180045136
0x1800450b0  mov     [rsp+218h+packageFamilyNameLength], 41h ; 'A'
0x1800450b8  mov     [rsp+218h+packageRelativeApplicationIdLength], 42h ; 'B'
0x1800450c0  lea     rax, [rsp+218h+var_B8]
0x1800450c8  mov     qword ptr [rsp+218h+packageRelativeApplicationId], rax; packageRelativeApplicationId
0x1800450cd  lea     r9, [rsp+218h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x1800450d2  lea     r8, [rsp+218h+packageFamilyName]; packageFamilyName
0x1800450da  mov     rcx, [rbx]; applicationUserModelId
0x1800450dd  call    cs:__imp_ParseApplicationUserModelId
0x1800450e3  test    eax, eax
0x1800450e5  jnz     short loc_18004512D
0x1800450e7  mov     rdx, rdi; psz2
0x1800450ea  lea     rcx, [rsp+218h+packageFamilyName]; psz1
0x1800450f2  call    cs:__imp_StrCmpIW
0x1800450f8  test    eax, eax
0x1800450fa  jnz     short loc_18004512D
0x1800450fc  mov     [r15], al
0x1800450ff  mov     rcx, [rsp+218h+string]; string
0x180045104  call    cs:__imp_WindowsDeleteString
0x18004510a  mov     [rsp+218h+string], 0
0x180045113  lea     rcx, [rsp+218h+var_1D8]
0x180045118  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004511d  nop
0x18004511e  mov     rcx, r14
0x180045121  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045126  xor     eax, eax
0x180045128  jmp     loc_1800451B9
0x18004512d  add     rbx, 8
0x180045131  jmp     loc_1800450A2
0x180045136  mov     rax, [rsp+218h+var_1D8]
0x18004513b  mov     qword ptr [rsp+218h+packageRelativeApplicationIdLength], rax
0x180045140  mov     [rsp+218h+packageFamilyNameLength], 0
0x180045148  lea     r8, [rsp+218h+packageRelativeApplicationIdLength]
0x18004514d  lea     rcx, [rsp+218h+var_1C8]
0x180045152  call    ??$Make@VCAppTileData@StorageSenseHandlers@SystemSettings@@W4AppListType@23@PEAUIInspectable@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4AppListType@StorageSenseHandlers@SystemSettings@@$$QEAPEAUIInspectable@@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,SystemSettings::StorageSenseHandlers::AppListType,IInspectable *>(SystemSettings::StorageSenseHandlers::AppListType &&,IInspectable * &&)
0x180045157  nop
0x180045158  mov     rbx, [rsp+218h+var_1C8]
0x18004515d  mov     rcx, rbx; this
0x180045160  call    ?AreAdvancedOptionsSupported@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAA_NXZ; SystemSettings::StorageSenseHandlers::CAppTileData::AreAdvancedOptionsSupported(void)
0x180045165  mov     [r15], al
0x180045168  test    rbx, rbx
0x18004516b  jz      short loc_18004517D
0x18004516d  mov     rax, [rbx]
0x180045170  mov     rcx, rbx
0x180045173  mov     rax, [rax+10h]
0x180045177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004517c  nop
0x18004517d  mov     rcx, [rsp+218h+string]; string
0x180045182  call    cs:__imp_WindowsDeleteString
0x180045188  mov     [rsp+218h+string], 0
0x180045191  lea     rcx, [rsp+218h+var_1D8]
0x180045196  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004519b  nop
0x18004519c  mov     rcx, r14
0x18004519f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800451a4  xor     eax, eax
0x1800451a6  jmp     short loc_1800451B9
0x1800451a8  mov     rcx, [rsp+218h+var_198]
0x1800451b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800451b5  mov     eax, [rsp+218h+packageFamilyNameLength]
0x1800451b9  mov     rcx, [rsp+218h+var_28]
0x1800451c1  xor     rcx, rsp; StackCookie
0x1800451c4  call    __security_check_cookie
0x1800451c9  lea     r11, [rsp+218h+var_18]
0x1800451d1  mov     rbx, [r11+20h]
0x1800451d5  mov     rdi, [r11+38h]
0x1800451d9  mov     rsp, r11
0x1800451dc  pop     r15
0x1800451de  pop     r14
0x1800451e0  pop     r12
0x1800451e2  retn
```
