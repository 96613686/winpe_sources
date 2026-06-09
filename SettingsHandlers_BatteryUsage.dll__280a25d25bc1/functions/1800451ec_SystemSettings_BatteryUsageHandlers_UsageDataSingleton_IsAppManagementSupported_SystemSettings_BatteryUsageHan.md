# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::IsAppManagementSupported(SystemSettings::BatteryUsageHandlers::AppIdentity,bool *)

- ea: `0x1800451ec`
- end: `0x18004551f`
- name: `?IsAppManagementSupported@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJUAppIdentity@23@PEA_N@Z`
- size: `819`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b7b4`

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
- `0x1800451ec`
- `0x180045954`
- `0x18004719c`
- `0x1800512e0`
- `0x18005203c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18004542e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18004542e`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180045419`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180045419`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800452c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004532b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045372`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800454be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800452c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004532b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045372`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800454be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800453a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800453a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::IsAppManagementSupported(
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
    v8 = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::LookupFriendlyName(v7, v35, v6);
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8, v9, v10);
    std::wstring::wstring((__int64)v36, v11);
    std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
      &qword_180079B90,
      packageFamilyNameLength,
      v36);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v35);
    if ( *(_QWORD *)packageFamilyNameLength == qword_180079B90 )
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
      (void *)0x3D6,
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
                                   (void *)0x3FB,
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
0x1800451ec  mov     [rsp+arg_0], rbx
0x1800451f1  mov     [rsp+arg_18], rdi
0x1800451f6  push    r12
0x1800451f8  push    r14
0x1800451fa  push    r15
0x1800451fc  sub     rsp, 200h
0x180045203  mov     rax, cs:__security_cookie
0x18004520a  xor     rax, rsp
0x18004520d  mov     [rsp+218h+var_28], rax
0x180045215  mov     r15, r8
0x180045218  mov     r14, rdx
0x18004521b  mov     [rsp+218h+var_198], rdx
0x180045223  cmp     dword ptr [rdx+20h], 1
0x180045227  jbe     short loc_18004523C
0x180045229  mov     byte ptr [r8], 0
0x18004522d  mov     rcx, r14
0x180045230  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045235  xor     eax, eax
0x180045237  jmp     loc_1800454F5
0x18004523c  mov     [rsp+218h+var_1D8], 0
0x180045245  mov     [rsp+218h+string], 0
0x18004524e  lea     rcx, [rsp+218h+var_1C0]; this
0x180045253  call    ??0AppIdentity@BatteryUsageHandlers@SystemSettings@@QEAA@AEBU012@@Z; SystemSettings::BatteryUsageHandlers::AppIdentity::AppIdentity(SystemSettings::BatteryUsageHandlers::AppIdentity const &)
0x180045258  mov     r8, rax
0x18004525b  lea     rdx, [rsp+218h+var_190]
0x180045263  call    ?LookupFriendlyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppIdentity@23@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::LookupFriendlyName(SystemSettings::BatteryUsageHandlers::AppIdentity)
0x180045268  nop
0x180045269  mov     rcx, rax
0x18004526c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045271  mov     rdx, rax
0x180045274  lea     rcx, [rsp+218h+var_170]
0x18004527c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180045281  lea     r8, [rsp+218h+var_170]
0x180045289  lea     rdx, [rsp+218h+packageFamilyNameLength]
0x18004528e  lea     rcx, qword_180079B90
0x180045295  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18004529a  lea     rcx, [rsp+218h+var_170]
0x1800452a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800452a7  nop
0x1800452a8  lea     rcx, [rsp+218h+var_190]
0x1800452b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800452b5  mov     rax, qword ptr [rsp+218h+packageFamilyNameLength]
0x1800452ba  cmp     rax, cs:qword_180079B90
0x1800452c1  jnz     short loc_1800452F4
0x1800452c3  mov     rcx, [rsp+218h+string]; string
0x1800452c8  call    cs:__imp_WindowsDeleteString
0x1800452ce  mov     [rsp+218h+string], 0
0x1800452d7  lea     rcx, [rsp+218h+var_1D8]
0x1800452dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800452e1  nop
0x1800452e2  mov     rcx, r14
0x1800452e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800452ea  mov     eax, 80004005h
0x1800452ef  jmp     loc_1800454F5
0x1800452f4  lea     rdi, [rax+40h]
0x1800452f8  mov     rdx, rdi
0x1800452fb  lea     rcx, [rsp+218h+var_1D8]
0x180045300  call    ??$?4UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEAAAEAV012@AEBV?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::operator=<SystemSettings::BatteryUsageHandlers::IPackageInfo>(Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo> const &)
0x180045305  cmp     dword ptr [r14+20h], 1
0x18004530a  jnz     short loc_18004531C
0x18004530c  mov     rcx, r14
0x18004530f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045314  mov     rdi, rax
0x180045317  jmp     loc_1800453D0
0x18004531c  mov     rdi, [rdi]
0x18004531f  mov     rax, [rdi]
0x180045322  mov     rbx, [rax+48h]
0x180045326  mov     rcx, [rsp+218h+string]; string
0x18004532b  call    cs:__imp_WindowsDeleteString
0x180045331  mov     [rsp+218h+string], 0
0x18004533a  lea     rdx, [rsp+218h+string]
0x18004533f  mov     rcx, rdi
0x180045342  mov     rax, rbx
0x180045345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004534a  mov     ebx, eax
0x18004534c  test    eax, eax
0x18004534e  jns     short loc_18004539B
0x180045350  mov     rcx, [rsp+218h]; this
0x180045358  mov     r9d, eax; char *
0x18004535b  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180045362  mov     edx, 3D6h; void *
0x180045367  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004536c  nop
0x18004536d  mov     rcx, [rsp+218h+string]; string
0x180045372  call    cs:__imp_WindowsDeleteString
0x180045378  mov     [rsp+218h+string], 0
0x180045381  lea     rcx, [rsp+218h+var_1D8]
0x180045386  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004538b  nop
0x18004538c  mov     rcx, r14
0x18004538f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045394  mov     eax, ebx
0x180045396  jmp     loc_1800454F5
0x18004539b  xor     edx, edx; length
0x18004539d  mov     rcx, [rsp+218h+string]; string
0x1800453a2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800453a8  mov     rdx, rax
0x1800453ab  lea     rcx, [rsp+218h+var_190]
0x1800453b3  call    ?GetPackageFamilyNameFromPackageFullName@BatteryUsageHandlers@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(ushort const *)
0x1800453b8  mov     rcx, rax
0x1800453bb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800453c0  mov     rdi, rax
0x1800453c3  lea     rcx, [rsp+218h+var_190]
0x1800453cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800453d0  lea     rbx, ?AppsHiddenFromAppList@ShellBlockLists@@3QBQEBGB; ushort const * const near * const ShellBlockLists::AppsHiddenFromAppList
0x1800453d7  lea     r12, ?_sc_rgridpDurationValues@DataDurationSelector@BatteryUsageHandlers@SystemSettings@@0QBUDURATION_VALUE_PAIR@123@B; SystemSettings::BatteryUsageHandlers::DataDurationSelector::DURATION_VALUE_PAIR const near * const SystemSettings::BatteryUsageHandlers::DataDurationSelector::_sc_rgridpDurationValues
0x1800453de  lea     rdx, [rsp+218h+packageFamilyNameLength]; packageFamilyNameLength
0x1800453e3  cmp     rbx, r12
0x1800453e6  jz      loc_180045472
0x1800453ec  mov     [rsp+218h+packageFamilyNameLength], 41h ; 'A'
0x1800453f4  mov     [rsp+218h+packageRelativeApplicationIdLength], 42h ; 'B'
0x1800453fc  lea     rax, [rsp+218h+var_B8]
0x180045404  mov     qword ptr [rsp+218h+packageRelativeApplicationId], rax; packageRelativeApplicationId
0x180045409  lea     r9, [rsp+218h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18004540e  lea     r8, [rsp+218h+packageFamilyName]; packageFamilyName
0x180045416  mov     rcx, [rbx]; applicationUserModelId
0x180045419  call    cs:__imp_ParseApplicationUserModelId
0x18004541f  test    eax, eax
0x180045421  jnz     short loc_180045469
0x180045423  mov     rdx, rdi; psz2
0x180045426  lea     rcx, [rsp+218h+packageFamilyName]; psz1
0x18004542e  call    cs:__imp_StrCmpIW
0x180045434  test    eax, eax
0x180045436  jnz     short loc_180045469
0x180045438  mov     [r15], al
0x18004543b  mov     rcx, [rsp+218h+string]; string
0x180045440  call    cs:__imp_WindowsDeleteString
0x180045446  mov     [rsp+218h+string], 0
0x18004544f  lea     rcx, [rsp+218h+var_1D8]
0x180045454  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045459  nop
0x18004545a  mov     rcx, r14
0x18004545d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045462  xor     eax, eax
0x180045464  jmp     loc_1800454F5
0x180045469  add     rbx, 8
0x18004546d  jmp     loc_1800453DE
0x180045472  mov     rax, [rsp+218h+var_1D8]
0x180045477  mov     qword ptr [rsp+218h+packageRelativeApplicationIdLength], rax
0x18004547c  mov     [rsp+218h+packageFamilyNameLength], 0
0x180045484  lea     r8, [rsp+218h+packageRelativeApplicationIdLength]
0x180045489  lea     rcx, [rsp+218h+var_1C8]
0x18004548e  call    ??$Make@VCAppTileData@StorageSenseHandlers@SystemSettings@@W4AppListType@23@PEAUIInspectable@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4AppListType@StorageSenseHandlers@SystemSettings@@$$QEAPEAUIInspectable@@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,SystemSettings::StorageSenseHandlers::AppListType,IInspectable *>(SystemSettings::StorageSenseHandlers::AppListType &&,IInspectable * &&)
0x180045493  nop
0x180045494  mov     rbx, [rsp+218h+var_1C8]
0x180045499  mov     rcx, rbx; this
0x18004549c  call    ?AreAdvancedOptionsSupported@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAA_NXZ; SystemSettings::StorageSenseHandlers::CAppTileData::AreAdvancedOptionsSupported(void)
0x1800454a1  mov     [r15], al
0x1800454a4  test    rbx, rbx
0x1800454a7  jz      short loc_1800454B9
0x1800454a9  mov     rax, [rbx]
0x1800454ac  mov     rcx, rbx
0x1800454af  mov     rax, [rax+10h]
0x1800454b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454b8  nop
0x1800454b9  mov     rcx, [rsp+218h+string]; string
0x1800454be  call    cs:__imp_WindowsDeleteString
0x1800454c4  mov     [rsp+218h+string], 0
0x1800454cd  lea     rcx, [rsp+218h+var_1D8]
0x1800454d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800454d7  nop
0x1800454d8  mov     rcx, r14
0x1800454db  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800454e0  xor     eax, eax
0x1800454e2  jmp     short loc_1800454F5
0x1800454e4  mov     rcx, [rsp+218h+var_198]
0x1800454ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800454f1  mov     eax, [rsp+218h+packageFamilyNameLength]
0x1800454f5  mov     rcx, [rsp+218h+var_28]
0x1800454fd  xor     rcx, rsp; StackCookie
0x180045500  call    __security_check_cookie
0x180045505  lea     r11, [rsp+218h+var_18]
0x18004550d  mov     rbx, [r11+20h]
0x180045511  mov     rdi, [r11+38h]
0x180045515  mov     rsp, r11
0x180045518  pop     r15
0x18004551a  pop     r14
0x18004551c  pop     r12
0x18004551e  retn
```
