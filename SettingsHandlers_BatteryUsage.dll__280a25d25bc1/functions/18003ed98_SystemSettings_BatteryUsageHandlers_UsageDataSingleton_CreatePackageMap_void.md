# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::CreatePackageMap(void)

- ea: `0x18003ed98`
- end: `0x18003f115`
- name: `?CreatePackageMap@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@AEAAJXZ`
- size: `893`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::UsageDataSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045ca0`

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
- `0x18003ed98`
- `0x180043908`
- `0x180043ce0`
- `0x18004430c`
- `0x180052354`
- `0x1800523d8`
- `0x1800526ac`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f06c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f06c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003efce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003efce`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetKnownFolderItem` at `0x18003edf2`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetKnownFolderItem` at `0x18003edf2`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::CreatePackageMap(
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton *this)
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
      (void *)0x4FC,
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
      (void *)0x4FE,
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
      (void *)0x500,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v9,
      (int)&psfParent);
LABEL_8:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    goto LABEL_5;
  }
  std::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>>::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>>(v32);
  PackagedApps = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackagedApps(
                   (__int64)this,
                   (__int64 *)v32);
  v3 = PackagedApps;
  if ( PackagedApps < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x504,
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
    PackageFullNameFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(
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
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton::InsertPackage(this, v28);
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
        (void *)0x517,
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
    SystemSettings::BatteryUsageHandlers::UsageDataSingleton::InsertPackage(this, v25);
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
0x18003ed98  mov     [rsp-8+arg_8], rbx
0x18003ed9d  mov     [rsp-8+arg_10], rsi
0x18003eda2  push    rbp
0x18003eda3  push    rdi
0x18003eda4  push    r14
0x18003eda6  lea     rbp, [rsp-47h]
0x18003edab  sub     rsp, 0D0h
0x18003edb2  mov     rax, cs:__security_cookie
0x18003edb9  xor     rax, rsp
0x18003edbc  mov     [rbp+57h+var_18], rax
0x18003edc0  mov     rsi, rcx
0x18003edc3  xor     r14d, r14d
0x18003edc6  mov     [rbp+57h+var_80], r14
0x18003edca  lea     rcx, [rbp+57h+var_80]
0x18003edce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003edd3  lea     rax, [rbp+57h+var_80]
0x18003edd7  mov     qword ptr [rsp+0E0h+ppv], rax; int
0x18003eddc  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003ede3  xor     r8d, r8d; hToken
0x18003ede6  mov     edx, 4000h; flags
0x18003edeb  lea     rcx, FOLDERID_AppsFolder; rfid
0x18003edf2  call    cs:__imp_SHGetKnownFolderItem
0x18003edf8  mov     ebx, eax
0x18003edfa  test    eax, eax
0x18003edfc  jns     short loc_18003EE1B
0x18003edfe  mov     rcx, [rbp+5Fh]; this
0x18003ee02  mov     r9d, eax; char *
0x18003ee05  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003ee0c  mov     edx, 4FCh; void *
0x18003ee11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ee16  jmp     loc_18003F0E6
0x18003ee1b  mov     [rbp+57h+psfParent], r14
0x18003ee1f  mov     rdi, [rbp+57h+var_80]
0x18003ee23  mov     rax, [rdi]
0x18003ee26  mov     rbx, [rax+18h]
0x18003ee2a  lea     rcx, [rbp+57h+psfParent]
0x18003ee2e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ee33  lea     rax, [rbp+57h+psfParent]
0x18003ee37  mov     qword ptr [rsp+0E0h+ppv], rax; int
0x18003ee3c  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x18003ee43  lea     r8, BHID_SFObject
0x18003ee4a  xor     edx, edx
0x18003ee4c  mov     rcx, rdi
0x18003ee4f  mov     rax, rbx
0x18003ee52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee57  mov     ebx, eax
0x18003ee59  test    eax, eax
0x18003ee5b  jns     short loc_18003EE84
0x18003ee5d  mov     rcx, [rbp+5Fh]; this
0x18003ee61  mov     r9d, eax; char *
0x18003ee64  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003ee6b  mov     edx, 4FEh; void *
0x18003ee70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ee75  nop
0x18003ee76  lea     rcx, [rbp+57h+psfParent]
0x18003ee7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ee7f  jmp     loc_18003F0E6
0x18003ee84  mov     [rbp+57h+var_98], r14
0x18003ee88  mov     rdi, [rbp+57h+psfParent]
0x18003ee8c  mov     rax, [rdi]
0x18003ee8f  mov     rbx, [rax+20h]
0x18003ee93  lea     rcx, [rbp+57h+var_98]
0x18003ee97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ee9c  lea     r9, [rbp+57h+var_98]
0x18003eea0  xor     edx, edx
0x18003eea2  lea     r8d, [rdx+40h]
0x18003eea6  mov     rcx, rdi
0x18003eea9  mov     rax, rbx
0x18003eeac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eeb1  mov     ebx, eax
0x18003eeb3  test    eax, eax
0x18003eeb5  jns     short loc_18003EEDB
0x18003eeb7  mov     rcx, [rbp+5Fh]; this
0x18003eebb  mov     r9d, eax; char *
0x18003eebe  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003eec5  mov     edx, 500h; void *
0x18003eeca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eecf  nop
0x18003eed0  lea     rcx, [rbp+57h+var_98]
0x18003eed4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003eed9  jmp     short loc_18003EE76
0x18003eedb  lea     rcx, [rbp+57h+var_68]
0x18003eedf  call    ??0?$set@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@QEAA@XZ; std::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>>::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>>(void)
0x18003eee4  nop
0x18003eee5  lea     rdx, [rbp+57h+var_68]
0x18003eee9  mov     rcx, rsi
0x18003eeec  call    ?GetPackagedApps@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAV?$set@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackagedApps(std::set<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>> *)
0x18003eef1  mov     ebx, eax
0x18003eef3  test    eax, eax
0x18003eef5  jns     short loc_18003EF1B
0x18003eef7  mov     rcx, [rbp+5Fh]; this
0x18003eefb  mov     r9d, eax; char *
0x18003eefe  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003ef05  mov     edx, 504h; void *
0x18003ef0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ef0f  nop
0x18003ef10  lea     rcx, [rbp+57h+var_68]
0x18003ef14  call    ??1?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::~_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>(void)
0x18003ef19  jmp     short loc_18003EED0
0x18003ef1b  mov     rax, [rbp+57h+var_68]
0x18003ef1f  mov     rax, [rax]
0x18003ef22  mov     [rbp+57h+var_78], rax
0x18003ef26  cmp     [rax+19h], r14b
0x18003ef2a  jnz     loc_18003EFF3
0x18003ef30  lea     rdx, [rax+20h]
0x18003ef34  mov     [rbp+57h+var_A0], r14
0x18003ef38  mov     [rbp+57h+string], r14
0x18003ef3c  lea     rcx, [rbp+57h+var_58]
0x18003ef40  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003ef45  mov     r8, rax
0x18003ef48  lea     rdx, [rbp+57h+var_38]
0x18003ef4c  mov     rcx, rsi
0x18003ef4f  call    ?GetPackageFullNameFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(std::wstring)
0x18003ef54  mov     rcx, rax
0x18003ef57  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ef5c  mov     [rbp+57h+var_70], rax
0x18003ef60  lea     rdx, [rbp+57h+var_70]
0x18003ef64  lea     rcx, [rbp+57h+string]
0x18003ef68  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003ef6d  mov     ebx, eax
0x18003ef6f  shr     ebx, 1Fh
0x18003ef72  lea     rcx, [rbp+57h+var_38]
0x18003ef76  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ef7b  test    bl, bl
0x18003ef7d  jnz     short loc_18003EFCA
0x18003ef7f  lea     rcx, [rbp+57h+var_A0]
0x18003ef83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ef88  lea     rdx, [rbp+57h+var_A0]; struct SystemSettings::StorageSenseHandlers::CAppInfo **
0x18003ef8c  mov     rcx, [rbp+57h+string]; string
0x18003ef90  call    ?Create@CAppInfo@StorageSenseHandlers@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::Create(HSTRING__ *,SystemSettings::StorageSenseHandlers::CAppInfo * *)
0x18003ef95  test    eax, eax
0x18003ef97  js      short loc_18003EFCA
0x18003ef99  mov     [rbp+57h+var_88], r14
0x18003ef9d  lea     rcx, [rbp+57h+var_88]
0x18003efa1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003efa6  lea     rdx, [rbp+57h+var_88]; struct SystemSettings::BatteryUsageHandlers::IPackageInfo **
0x18003efaa  mov     rcx, [rbp+57h+var_A0]; struct SystemSettings::StorageSenseHandlers::CAppInfo *
0x18003efae  call    ?Create@CPackageInfo@StorageSenseHandlers@SystemSettings@@SAJPEAVCAppInfo@23@PEAPEAUIPackageInfo@BatteryUsageHandlers@3@@Z; SystemSettings::StorageSenseHandlers::CPackageInfo::Create(SystemSettings::StorageSenseHandlers::CAppInfo *,SystemSettings::BatteryUsageHandlers::IPackageInfo * *)
0x18003efb3  mov     rdx, [rbp+57h+var_88]; struct SystemSettings::BatteryUsageHandlers::IPackageInfo *
0x18003efb7  mov     rcx, rsi; this
0x18003efba  call    ?InsertPackage@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAUIPackageInfo@23@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::InsertPackage(SystemSettings::BatteryUsageHandlers::IPackageInfo *)
0x18003efbf  nop
0x18003efc0  lea     rcx, [rbp+57h+var_88]
0x18003efc4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003efc9  nop
0x18003efca  mov     rcx, [rbp+57h+string]; string
0x18003efce  call    cs:__imp_WindowsDeleteString
0x18003efd4  mov     [rbp+57h+string], r14
0x18003efd8  lea     rcx, [rbp+57h+var_A0]
0x18003efdc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003efe1  lea     rcx, [rbp+57h+var_78]
0x18003efe5  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<SystemSettings::BatteryUsageHandlers::AppIdentity>>,std::_Iterator_base0>::operator++(void)
0x18003efea  mov     rax, [rbp+57h+var_78]
0x18003efee  jmp     loc_18003EF26
0x18003eff3  mov     [rbp+57h+pv], r14
0x18003eff7  mov     rcx, [rbp+57h+var_98]
0x18003effb  mov     rax, [rcx]
0x18003effe  xor     r9d, r9d
0x18003f001  lea     r8, [rbp+57h+pv]
0x18003f005  lea     edx, [r9+1]
0x18003f009  mov     rax, [rax+18h]
0x18003f00d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f012  test    eax, eax
0x18003f014  jnz     loc_18003F0BC
0x18003f01a  mov     [rbp+57h+string], r14
0x18003f01e  lea     rcx, [rbp+57h+string]
0x18003f022  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f027  lea     r8, [rbp+57h+string]; struct SystemSettings::StorageSenseHandlers::CAppInfo **
0x18003f02b  mov     rdx, [rbp+57h+pv]; pidl
0x18003f02f  mov     rcx, [rbp+57h+psfParent]; psfParent
0x18003f033  call    ?Create@CAppInfo@StorageSenseHandlers@SystemSettings@@SAJPEAUIShellFolder@@PEFAU_ITEMIDLIST@@PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::Create(IShellFolder *,_ITEMIDLIST *,SystemSettings::StorageSenseHandlers::CAppInfo * *)
0x18003f038  mov     ebx, eax
0x18003f03a  test    eax, eax
0x18003f03c  js      short loc_18003F08B
0x18003f03e  mov     [rbp+57h+var_A0], r14
0x18003f042  lea     rcx, [rbp+57h+var_A0]
0x18003f046  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f04b  lea     rdx, [rbp+57h+var_A0]; struct SystemSettings::BatteryUsageHandlers::IPackageInfo **
0x18003f04f  mov     rcx, [rbp+57h+string]; struct SystemSettings::StorageSenseHandlers::CAppInfo *
0x18003f053  call    ?Create@CPackageInfo@StorageSenseHandlers@SystemSettings@@SAJPEAVCAppInfo@23@PEAPEAUIPackageInfo@BatteryUsageHandlers@3@@Z; SystemSettings::StorageSenseHandlers::CPackageInfo::Create(SystemSettings::StorageSenseHandlers::CAppInfo *,SystemSettings::BatteryUsageHandlers::IPackageInfo * *)
0x18003f058  mov     rdx, [rbp+57h+var_A0]; struct SystemSettings::BatteryUsageHandlers::IPackageInfo *
0x18003f05c  mov     rcx, rsi; this
0x18003f05f  call    ?InsertPackage@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAUIPackageInfo@23@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::InsertPackage(SystemSettings::BatteryUsageHandlers::IPackageInfo *)
0x18003f064  mov     rcx, [rbp+57h+pv]; pv
0x18003f068  mov     [rbp+57h+pv], r14
0x18003f06c  call    cs:__imp_CoTaskMemFree
0x18003f072  nop
0x18003f073  lea     rcx, [rbp+57h+var_A0]
0x18003f077  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f07c  nop
0x18003f07d  lea     rcx, [rbp+57h+string]
0x18003f081  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f086  jmp     loc_18003EFF7
0x18003f08b  mov     rcx, [rbp+5Fh]; this
0x18003f08f  mov     r9d, eax; char *
0x18003f092  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003f099  mov     edx, 517h; void *
0x18003f09e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f0a3  nop
0x18003f0a4  lea     rcx, [rbp+57h+string]
0x18003f0a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f0ad  nop
0x18003f0ae  lea     rcx, [rbp+57h+pv]
0x18003f0b2  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18003f0b7  jmp     loc_18003EF10
0x18003f0bc  lea     rcx, [rbp+57h+pv]
0x18003f0c0  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18003f0c5  nop
0x18003f0c6  lea     rcx, [rbp+57h+var_68]
0x18003f0ca  call    ??1?$_Tree@V?$_Tset_traits@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppIdentityCompare@23@V?$allocator@UAppIdentity@BatteryUsageHandlers@SystemSettings@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>::~_Tree<std::_Tset_traits<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppIdentityCompare,std::allocator<SystemSettings::BatteryUsageHandlers::AppIdentity>,0>>(void)
0x18003f0cf  nop
0x18003f0d0  lea     rcx, [rbp+57h+var_98]
0x18003f0d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f0d9  nop
0x18003f0da  lea     rcx, [rbp+57h+psfParent]
0x18003f0de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f0e3  mov     ebx, r14d
0x18003f0e6  lea     rcx, [rbp+57h+var_80]
0x18003f0ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f0ef  mov     eax, ebx
0x18003f0f1  mov     rcx, [rbp+57h+var_18]
0x18003f0f5  xor     rcx, rsp; StackCookie
0x18003f0f8  call    __security_check_cookie
0x18003f0fd  lea     r11, [rsp+0E0h+var_10]
0x18003f105  mov     rbx, [r11+28h]
0x18003f109  mov     rsi, [r11+30h]
0x18003f10d  mov     rsp, r11
0x18003f110  pop     r14
0x18003f112  pop     rdi
0x18003f113  pop     rbp
0x18003f114  retn
```
