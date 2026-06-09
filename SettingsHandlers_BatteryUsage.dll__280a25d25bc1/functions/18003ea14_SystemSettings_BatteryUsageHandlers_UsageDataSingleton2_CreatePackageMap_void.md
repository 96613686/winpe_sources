# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::CreatePackageMap(void)

- ea: `0x18003ea14`
- end: `0x18003ed91`
- name: `?CreatePackageMap@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@AEAAJXZ`
- size: `893`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045c30`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18000a13c`
- `0x180013be0`
- `0x1800157f0`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c30`
- `0x180025cf4`
- `0x18002a9ac`
- `0x18002b994`
- `0x18003ea14`
- `0x180043770`
- `0x180043aa0`
- `0x180043f80`
- `0x180052354`
- `0x1800523d8`
- `0x1800526ac`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ece8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ece8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ec4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ec4a`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetKnownFolderItem` at `0x18003ea6e`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetKnownFolderItem` at `0x18003ea6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::CreatePackageMap(
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  void *v4; // rdi
  __int64 (__fastcall *v5)(void *, _QWORD, const GUID *, GUID *); // rbx
  int v6; // eax
  IShellFolder *v7; // rdi
  HRESULT (__stdcall *EnumObjects)(IShellFolder *, HWND, SHCONTF, IEnumIDList **); // rbx
  int v9; // eax
  int PackagedApps; // eax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 PackageFullNameFromFamilyName; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  char v17; // r8
  unsigned int v18; // ebx
  int v19; // eax
  void *v20; // rcx
  int ppv; // [rsp+20h] [rbp-69h]
  HSTRING string; // [rsp+30h] [rbp-59h] BYREF
  IShellFolder *psfParent; // [rsp+38h] [rbp-51h] BYREF
  struct SystemSettings::StorageSenseHandlers::CAppInfo *v25; // [rsp+40h] [rbp-49h] BYREF
  __int64 v26; // [rsp+48h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-39h] BYREF
  struct SystemSettings::BatteryUsageHandlers::IPackageInfo *v28; // [rsp+58h] [rbp-31h] BYREF
  void *v29; // [rsp+60h] [rbp-29h] BYREF
  __int64 v30; // [rsp+68h] [rbp-21h] BYREF
  __int64 v31; // [rsp+70h] [rbp-19h] BYREF
  void *v32[2]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v33[32]; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v34[32]; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v29 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v2 = SHGetKnownFolderItem(
         &FOLDERID_AppsFolder,
         KF_FLAG_DONT_VERIFY,
         0,
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         &v29);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB9,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v2,
      ppv);
    goto LABEL_24;
  }
  psfParent = 0;
  v4 = v29;
  v5 = *(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)v29 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&psfParent);
  v6 = v5(v4, 0, &BHID_SFObject, &GUID_000214e6_0000_0000_c000_000000000046);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xABB,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v6,
      (int)&psfParent);
LABEL_5:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&psfParent);
    goto LABEL_24;
  }
  v26 = 0;
  v7 = psfParent;
  EnumObjects = psfParent->lpVtbl->EnumObjects;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v9 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, __int64, __int64 *))EnumObjects)(v7, 0, 64, &v26);
  v3 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xABD,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v9,
      (int)&psfParent);
LABEL_8:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    goto LABEL_5;
  }
  std::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>>::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>>(v32);
  PackagedApps = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackagedApps(
                   (__int64)this,
                   (__int64 *)v32);
  v3 = PackagedApps;
  if ( PackagedApps < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC1,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)PackagedApps,
      (int)&psfParent);
LABEL_11:
    std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::~_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>(v32);
    goto LABEL_8;
  }
  v12 = *(_QWORD *)v32[0];
  v30 = *(_QWORD *)v32[0];
  while ( !*(_BYTE *)(v12 + 25) )
  {
    v25 = 0;
    string = 0;
    v13 = std::wstring::wstring((__int64)v33, v12 + 32, v11);
    PackageFullNameFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(
                                      this,
                                      v34,
                                      v13);
    v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(PackageFullNameFromFamilyName, v15, v16);
    v18 = (unsigned int)Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
                          (Microsoft::WRL::Wrappers::HString *)&string,
                          &v31,
                          v17) >> 31;
    std::wstring::_Tidy_deallocate(v34);
    if ( !(_BYTE)v18 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      if ( (int)SystemSettings::StorageSenseHandlers::CAppInfo::Create(string, &v25) >= 0 )
      {
        v28 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
        SystemSettings::StorageSenseHandlers::CPackageInfo::Create(v25, &v28);
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::InsertPackage(this, v28);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      }
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<SystemSettings::BatteryUsageHandlers::AppIdentity>>,std::_Iterator_base0>::operator++(&v30);
    v12 = v30;
  }
  pv = 0;
  while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v26 + 24LL))(v26, 1, &pv) )
  {
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
    v19 = SystemSettings::StorageSenseHandlers::CAppInfo::Create(
            psfParent,
            (LPCITEMIDLIST)pv,
            (struct SystemSettings::StorageSenseHandlers::CAppInfo **)&string);
    v3 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAD4,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v19,
        (int)&psfParent);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pv);
      goto LABEL_11;
    }
    v25 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    SystemSettings::StorageSenseHandlers::CPackageInfo::Create(
      (struct SystemSettings::StorageSenseHandlers::CAppInfo *)string,
      &v25);
    SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::InsertPackage(this, v25);
    v20 = pv;
    pv = 0;
    CoTaskMemFree(v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&string);
  }
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pv);
  std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::~_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>(v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&psfParent);
  v3 = 0;
LABEL_24:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  return v3;
}

```

## disassembly

```asm
0x18003ea14  mov     [rsp-8+arg_8], rbx
0x18003ea19  mov     [rsp-8+arg_10], rsi
0x18003ea1e  push    rbp
0x18003ea1f  push    rdi
0x18003ea20  push    r14
0x18003ea22  lea     rbp, [rsp-47h]
0x18003ea27  sub     rsp, 0D0h
0x18003ea2e  mov     rax, cs:__security_cookie
0x18003ea35  xor     rax, rsp
0x18003ea38  mov     [rbp+57h+var_18], rax
0x18003ea3c  mov     rsi, rcx
0x18003ea3f  xor     r14d, r14d
0x18003ea42  mov     [rbp+57h+var_80], r14
0x18003ea46  lea     rcx, [rbp+57h+var_80]
0x18003ea4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ea4f  lea     rax, [rbp+57h+var_80]
0x18003ea53  mov     qword ptr [rsp+0E0h+ppv], rax; int
0x18003ea58  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003ea5f  xor     r8d, r8d; hToken
0x18003ea62  mov     edx, 4000h; flags
0x18003ea67  lea     rcx, FOLDERID_AppsFolder; rfid
0x18003ea6e  call    cs:__imp_SHGetKnownFolderItem
0x18003ea74  mov     ebx, eax
0x18003ea76  test    eax, eax
0x18003ea78  jns     short loc_18003EA97
0x18003ea7a  mov     rcx, [rbp+5Fh]; this
0x18003ea7e  mov     r9d, eax; char *
0x18003ea81  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003ea88  mov     edx, 0AB9h; void *
0x18003ea8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ea92  jmp     loc_18003ED62
0x18003ea97  mov     [rbp+57h+psfParent], r14
0x18003ea9b  mov     rdi, [rbp+57h+var_80]
0x18003ea9f  mov     rax, [rdi]
0x18003eaa2  mov     rbx, [rax+18h]
0x18003eaa6  lea     rcx, [rbp+57h+psfParent]
0x18003eaaa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003eaaf  lea     rax, [rbp+57h+psfParent]
0x18003eab3  mov     qword ptr [rsp+0E0h+ppv], rax; int
0x18003eab8  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x18003eabf  lea     r8, BHID_SFObject
0x18003eac6  xor     edx, edx
0x18003eac8  mov     rcx, rdi
0x18003eacb  mov     rax, rbx
0x18003eace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ead3  mov     ebx, eax
0x18003ead5  test    eax, eax
0x18003ead7  jns     short loc_18003EB00
0x18003ead9  mov     rcx, [rbp+5Fh]; this
0x18003eadd  mov     r9d, eax; char *
0x18003eae0  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003eae7  mov     edx, 0ABBh; void *
0x18003eaec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eaf1  nop
0x18003eaf2  lea     rcx, [rbp+57h+psfParent]
0x18003eaf6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003eafb  jmp     loc_18003ED62
0x18003eb00  mov     [rbp+57h+var_98], r14
0x18003eb04  mov     rdi, [rbp+57h+psfParent]
0x18003eb08  mov     rax, [rdi]
0x18003eb0b  mov     rbx, [rax+20h]
0x18003eb0f  lea     rcx, [rbp+57h+var_98]
0x18003eb13  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003eb18  lea     r9, [rbp+57h+var_98]
0x18003eb1c  xor     edx, edx
0x18003eb1e  lea     r8d, [rdx+40h]
0x18003eb22  mov     rcx, rdi
0x18003eb25  mov     rax, rbx
0x18003eb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb2d  mov     ebx, eax
0x18003eb2f  test    eax, eax
0x18003eb31  jns     short loc_18003EB57
0x18003eb33  mov     rcx, [rbp+5Fh]; this
0x18003eb37  mov     r9d, eax; char *
0x18003eb3a  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003eb41  mov     edx, 0ABDh; void *
0x18003eb46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eb4b  nop
0x18003eb4c  lea     rcx, [rbp+57h+var_98]
0x18003eb50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003eb55  jmp     short loc_18003EAF2
0x18003eb57  lea     rcx, [rbp+57h+var_68]
0x18003eb5b  call    ??0?$set@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@QEAA@XZ; std::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>>::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>>(void)
0x18003eb60  nop
0x18003eb61  lea     rdx, [rbp+57h+var_68]
0x18003eb65  mov     rcx, rsi
0x18003eb68  call    ?GetPackagedApps@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJPEAV?$set@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackagedApps(std::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>> *)
0x18003eb6d  mov     ebx, eax
0x18003eb6f  test    eax, eax
0x18003eb71  jns     short loc_18003EB97
0x18003eb73  mov     rcx, [rbp+5Fh]; this
0x18003eb77  mov     r9d, eax; char *
0x18003eb7a  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003eb81  mov     edx, 0AC1h; void *
0x18003eb86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eb8b  nop
0x18003eb8c  lea     rcx, [rbp+57h+var_68]
0x18003eb90  call    ??1?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::~_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>(void)
0x18003eb95  jmp     short loc_18003EB4C
0x18003eb97  mov     rax, [rbp+57h+var_68]
0x18003eb9b  mov     rax, [rax]
0x18003eb9e  mov     [rbp+57h+var_78], rax
0x18003eba2  cmp     [rax+19h], r14b
0x18003eba6  jnz     loc_18003EC6F
0x18003ebac  lea     rdx, [rax+20h]
0x18003ebb0  mov     [rbp+57h+var_A0], r14
0x18003ebb4  mov     [rbp+57h+string], r14
0x18003ebb8  lea     rcx, [rbp+57h+var_58]
0x18003ebbc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003ebc1  mov     r8, rax
0x18003ebc4  lea     rdx, [rbp+57h+var_38]
0x18003ebc8  mov     rcx, rsi
0x18003ebcb  call    ?GetPackageFullNameFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(std::wstring)
0x18003ebd0  mov     rcx, rax
0x18003ebd3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ebd8  mov     [rbp+57h+var_70], rax
0x18003ebdc  lea     rdx, [rbp+57h+var_70]
0x18003ebe0  lea     rcx, [rbp+57h+string]
0x18003ebe4  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003ebe9  mov     ebx, eax
0x18003ebeb  shr     ebx, 1Fh
0x18003ebee  lea     rcx, [rbp+57h+var_38]
0x18003ebf2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ebf7  test    bl, bl
0x18003ebf9  jnz     short loc_18003EC46
0x18003ebfb  lea     rcx, [rbp+57h+var_A0]
0x18003ebff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ec04  lea     rdx, [rbp+57h+var_A0]; struct SystemSettings::StorageSenseHandlers::CAppInfo **
0x18003ec08  mov     rcx, [rbp+57h+string]; string
0x18003ec0c  call    ?Create@CAppInfo@StorageSenseHandlers@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::Create(HSTRING__ *,SystemSettings::StorageSenseHandlers::CAppInfo * *)
0x18003ec11  test    eax, eax
0x18003ec13  js      short loc_18003EC46
0x18003ec15  mov     [rbp+57h+var_88], r14
0x18003ec19  lea     rcx, [rbp+57h+var_88]
0x18003ec1d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ec22  lea     rdx, [rbp+57h+var_88]; struct SystemSettings::BatteryUsageHandlers::IPackageInfo **
0x18003ec26  mov     rcx, [rbp+57h+var_A0]; struct SystemSettings::StorageSenseHandlers::CAppInfo *
0x18003ec2a  call    ?Create@CPackageInfo@StorageSenseHandlers@SystemSettings@@SAJPEAVCAppInfo@23@PEAPEAUIPackageInfo@BatteryUsageHandlers@3@@Z; SystemSettings::StorageSenseHandlers::CPackageInfo::Create(SystemSettings::StorageSenseHandlers::CAppInfo *,SystemSettings::BatteryUsageHandlers::IPackageInfo * *)
0x18003ec2f  mov     rdx, [rbp+57h+var_88]; struct SystemSettings::BatteryUsageHandlers::IPackageInfo *
0x18003ec33  mov     rcx, rsi; this
0x18003ec36  call    ?InsertPackage@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@AEAAJPEAUIPackageInfo@23@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::InsertPackage(SystemSettings::BatteryUsageHandlers::IPackageInfo *)
0x18003ec3b  nop
0x18003ec3c  lea     rcx, [rbp+57h+var_88]
0x18003ec40  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ec45  nop
0x18003ec46  mov     rcx, [rbp+57h+string]; string
0x18003ec4a  call    cs:__imp_WindowsDeleteString
0x18003ec50  mov     [rbp+57h+string], r14
0x18003ec54  lea     rcx, [rbp+57h+var_A0]
0x18003ec58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ec5d  lea     rcx, [rbp+57h+var_78]
0x18003ec61  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<SystemSettings::BatteryUsageHandlers::AppIdentity>>,std::_Iterator_base0>::operator++(void)
0x18003ec66  mov     rax, [rbp+57h+var_78]
0x18003ec6a  jmp     loc_18003EBA2
0x18003ec6f  mov     [rbp+57h+pv], r14
0x18003ec73  mov     rcx, [rbp+57h+var_98]
0x18003ec77  mov     rax, [rcx]
0x18003ec7a  xor     r9d, r9d
0x18003ec7d  lea     r8, [rbp+57h+pv]
0x18003ec81  lea     edx, [r9+1]
0x18003ec85  mov     rax, [rax+18h]
0x18003ec89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec8e  test    eax, eax
0x18003ec90  jnz     loc_18003ED38
0x18003ec96  mov     [rbp+57h+string], r14
0x18003ec9a  lea     rcx, [rbp+57h+string]
0x18003ec9e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003eca3  lea     r8, [rbp+57h+string]; struct SystemSettings::StorageSenseHandlers::CAppInfo **
0x18003eca7  mov     rdx, [rbp+57h+pv]; pidl
0x18003ecab  mov     rcx, [rbp+57h+psfParent]; psfParent
0x18003ecaf  call    ?Create@CAppInfo@StorageSenseHandlers@SystemSettings@@SAJPEAUIShellFolder@@PEFAU_ITEMIDLIST@@PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::Create(IShellFolder *,_ITEMIDLIST *,SystemSettings::StorageSenseHandlers::CAppInfo * *)
0x18003ecb4  mov     ebx, eax
0x18003ecb6  test    eax, eax
0x18003ecb8  js      short loc_18003ED07
0x18003ecba  mov     [rbp+57h+var_A0], r14
0x18003ecbe  lea     rcx, [rbp+57h+var_A0]
0x18003ecc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ecc7  lea     rdx, [rbp+57h+var_A0]; struct SystemSettings::BatteryUsageHandlers::IPackageInfo **
0x18003eccb  mov     rcx, [rbp+57h+string]; struct SystemSettings::StorageSenseHandlers::CAppInfo *
0x18003eccf  call    ?Create@CPackageInfo@StorageSenseHandlers@SystemSettings@@SAJPEAVCAppInfo@23@PEAPEAUIPackageInfo@BatteryUsageHandlers@3@@Z; SystemSettings::StorageSenseHandlers::CPackageInfo::Create(SystemSettings::StorageSenseHandlers::CAppInfo *,SystemSettings::BatteryUsageHandlers::IPackageInfo * *)
0x18003ecd4  mov     rdx, [rbp+57h+var_A0]; struct SystemSettings::BatteryUsageHandlers::IPackageInfo *
0x18003ecd8  mov     rcx, rsi; this
0x18003ecdb  call    ?InsertPackage@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@AEAAJPEAUIPackageInfo@23@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::InsertPackage(SystemSettings::BatteryUsageHandlers::IPackageInfo *)
0x18003ece0  mov     rcx, [rbp+57h+pv]; pv
0x18003ece4  mov     [rbp+57h+pv], r14
0x18003ece8  call    cs:__imp_CoTaskMemFree
0x18003ecee  nop
0x18003ecef  lea     rcx, [rbp+57h+var_A0]
0x18003ecf3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ecf8  nop
0x18003ecf9  lea     rcx, [rbp+57h+string]
0x18003ecfd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ed02  jmp     loc_18003EC73
0x18003ed07  mov     rcx, [rbp+5Fh]; this
0x18003ed0b  mov     r9d, eax; char *
0x18003ed0e  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003ed15  mov     edx, 0AD4h; void *
0x18003ed1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ed1f  nop
0x18003ed20  lea     rcx, [rbp+57h+string]
0x18003ed24  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ed29  nop
0x18003ed2a  lea     rcx, [rbp+57h+pv]
0x18003ed2e  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18003ed33  jmp     loc_18003EB8C
0x18003ed38  lea     rcx, [rbp+57h+pv]
0x18003ed3c  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18003ed41  nop
0x18003ed42  lea     rcx, [rbp+57h+var_68]
0x18003ed46  call    ??1?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::~_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>(void)
0x18003ed4b  nop
0x18003ed4c  lea     rcx, [rbp+57h+var_98]
0x18003ed50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ed55  nop
0x18003ed56  lea     rcx, [rbp+57h+psfParent]
0x18003ed5a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ed5f  mov     ebx, r14d
0x18003ed62  lea     rcx, [rbp+57h+var_80]
0x18003ed66  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ed6b  mov     eax, ebx
0x18003ed6d  mov     rcx, [rbp+57h+var_18]
0x18003ed71  xor     rcx, rsp; StackCookie
0x18003ed74  call    __security_check_cookie
0x18003ed79  lea     r11, [rsp+0E0h+var_10]
0x18003ed81  mov     rbx, [r11+28h]
0x18003ed85  mov     rsi, [r11+30h]
0x18003ed89  mov     rsp, r11
0x18003ed8c  pop     r14
0x18003ed8e  pop     rdi
0x18003ed8f  pop     rbp
0x18003ed90  retn
```
