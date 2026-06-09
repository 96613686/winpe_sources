# CProvisioningSingleton::InitializeInstalledPackageList(void)

- ea: `0x1800235dc`
- end: `0x180023d3d`
- name: `?InitializeInstalledPackageList@CProvisioningSingleton@@QEAAJXZ`
- size: `1889`
- prototype: `__int64 __fastcall(CProvisioningSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014640`

## callees

- `0x1800020d0`
- `0x1800067fc`
- `0x1800087ec`
- `0x18000f534`
- `0x180010944`
- `0x180015d74`
- `0x180019c10`
- `0x18001ec4c`
- `0x180022424`
- `0x18002247c`
- `0x1800227b4`
- `0x1800235dc`
- `0x1800245ec`
- `0x180024618`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023607`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023607`

## string_xrefs

- `0x180023650`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x1800236a2`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x1800236f7`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x180023767`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x180023802`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x180023882`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x180023911`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x18002399c`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x180023a36`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x180023acc`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`
- `0x180023b71`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CProvisioningSingleton::InitializeInstalledPackageList(CProvisioningSingleton *this)
{
  const unsigned __int16 (*v1)[50]; // rdx
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, int *)); // rbx
  int v6; // eax
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, int *); // rdi
  int v9; // eax
  __int64 result; // rax
  int v11; // eax
  unsigned int v12; // ebx
  const char *v13; // r9
  unsigned int i; // esi
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 **); // rbx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // ebx
  int Lpcwstr; // eax
  unsigned int v23; // ebx
  __int64 v24; // rax
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rax
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // eax
  unsigned int v33; // ebx
  unsigned __int16 *v34; // rbx
  __int64 v35; // r14
  __int64 v36; // rdi
  __int64 v37; // rax
  unsigned __int16 *v38; // rax
  int v39[2]; // [rsp+20h] [rbp-128h] BYREF
  __int64 (__fastcall ***v40)(_QWORD, GUID *, int *); // [rsp+28h] [rbp-120h] BYREF
  __int64 *v41; // [rsp+30h] [rbp-118h] BYREF
  __int64 v42; // [rsp+38h] [rbp-110h] BYREF
  struct _RTL_CRITICAL_SECTION *v43; // [rsp+40h] [rbp-108h] BYREF
  __int64 v44; // [rsp+48h] [rbp-100h] BYREF
  unsigned int v45; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v46; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v47; // [rsp+60h] [rbp-E8h] BYREF
  unsigned __int16 *v48; // [rsp+68h] [rbp-E0h] BYREF
  unsigned __int16 *v49; // [rsp+70h] [rbp-D8h] BYREF
  unsigned __int16 *v50[3]; // [rsp+78h] [rbp-D0h] BYREF
  _QWORD v51[4]; // [rsp+90h] [rbp-B8h] BYREF
  _QWORD v52[4]; // [rsp+B0h] [rbp-98h] BYREF
  _QWORD v53[4]; // [rsp+D0h] [rbp-78h] BYREF
  HSTRING string; // [rsp+F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  EnterCriticalSection(&stru_18003EF28);
  v43 = &stru_18003EF28;
  Windows::Internal::StringReference::StringReference(&string, v1);
  v42 = 0;
  v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageCollection>>(
         string,
         &v42);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
      (const char *)(unsigned int)v2,
      v39[0]);
LABEL_8:
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
    return v3;
  }
  v40 = 0;
  v4 = v42;
  v5 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, int *)))(*(_QWORD *)v42 + 48LL);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
  v6 = v5(v4, &v40);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
      (const char *)(unsigned int)v6,
      v39[0]);
LABEL_7:
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
    goto LABEL_8;
  }
  *(_QWORD *)v39 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
  v8 = **v40;
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
  v9 = v8(v7, &GUID_da650686_437b_5548_a75c_862ab4467cee, v39);
  v3 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
      (const char *)(unsigned int)v9,
      v39[0]);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
    goto LABEL_7;
  }
  try
  {
    v45 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v39 + 56LL))(*(_QWORD *)v39, &v45);
    v12 = v11;
    if ( v11 >= 0 )
    {
      std::vector<std::unique_ptr<ProvPackageInfo>>::clear(&xmmword_18003EFA0);
      for ( i = 0; i < v45; ++i )
      {
        v41 = 0;
        v15 = *(_QWORD *)v39;
        v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(**(_QWORD **)v39 + 48LL);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
        v17 = v16(v15, i, &v41);
        v18 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF8,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
            (const char *)(unsigned int)v17,
            v39[0]);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
          Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
          return v18;
        }
        v44 = 0;
        v19 = *v41;
        v44 = 0;
        v20 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 48))(v41, &v44);
        v21 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFB,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
            (const char *)(unsigned int)v20,
            v39[0]);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v44);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
          Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
          return v21;
        }
        v51[0] = v44;
        v48 = 0;
        Lpcwstr = Windows::Internal::StringReference::GetLpcwstr(
                    (Windows::Internal::StringReference *)v51,
                    (const unsigned __int16 **)&v48);
        v23 = Lpcwstr;
        if ( Lpcwstr < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFE,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
            (const char *)(unsigned int)Lpcwstr,
            v39[0]);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v44);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
          Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
          return v23;
        }
        v46 = 0;
        v24 = *v41;
        v46 = 0;
        v25 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v24 + 56))(v41, &v46);
        v26 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x101,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
            (const char *)(unsigned int)v25,
            v39[0]);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v46);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v44);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
          Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
          return v26;
        }
        v52[0] = v46;
        v50[0] = 0;
        v27 = Windows::Internal::StringReference::GetLpcwstr(
                (Windows::Internal::StringReference *)v52,
                (const unsigned __int16 **)v50);
        v28 = v27;
        if ( v27 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x104,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
            (const char *)(unsigned int)v27,
            v39[0]);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v46);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v44);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
          Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
          return v28;
        }
        v47 = 0;
        v29 = *v41;
        v47 = 0;
        v30 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v29 + 64))(v41, &v47);
        v31 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x107,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
            (const char *)(unsigned int)v30,
            v39[0]);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v47);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v46);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v44);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
          Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
          return v31;
        }
        v53[0] = v47;
        v49 = 0;
        v32 = Windows::Internal::StringReference::GetLpcwstr(
                (Windows::Internal::StringReference *)v53,
                (const unsigned __int16 **)&v49);
        v33 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10A,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
            (const char *)(unsigned int)v32,
            v39[0]);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v47);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v46);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v44);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
          Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
          return v33;
        }
        v34 = (unsigned __int16 *)operator new(0x60u);
        v50[1] = v34;
        if ( v34 )
        {
          v50[2] = (unsigned __int16 *)v53;
          v35 = std::wstring::wstring(v53, v49);
          v49 = (unsigned __int16 *)v52;
          v36 = std::wstring::wstring(v52, v50[0]);
          v37 = std::wstring::wstring(v51, v48);
          v38 = (unsigned __int16 *)ProvPackageInfo::ProvPackageInfo(v34, v37, v36, v35);
        }
        else
        {
          v38 = 0;
        }
        v48 = v38;
        std::vector<std::unique_ptr<ProvPackageInfo>>::emplace_back<std::unique_ptr<ProvPackageInfo>>(
          &xmmword_18003EFA0,
          &v48);
        std::unique_ptr<ProvPackageInfo>::_Delete(&v48);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v47);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v46);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v44);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v41);
      }
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
        (const char *)(unsigned int)v11,
        v39[0]);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
      result = v12;
    }
  }
  catch ( ... )
  {
    v45 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x110,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
            v13);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(v39);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v42);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v43);
    return v45;
  }
  return result;
}

```

## disassembly

```asm
0x1800235dc  push    rbx
0x1800235de  push    rsi
0x1800235df  push    rdi
0x1800235e0  push    r14
0x1800235e2  push    r15
0x1800235e4  sub     rsp, 120h
0x1800235eb  mov     rax, cs:__security_cookie
0x1800235f2  xor     rax, rsp
0x1800235f5  mov     [rsp+148h+var_38], rax
0x1800235fd  lea     rbx, stru_18003EF28
0x180023604  mov     rcx, rbx; lpCriticalSection
0x180023607  call    cs:__imp_EnterCriticalSection
0x18002360e  nop     dword ptr [rax+rax+00h]
0x180023613  mov     [rsp+148h+var_108], rbx
0x180023618  lea     rcx, [rsp+148h+string]; string
0x180023620  call    ??$?0$0DC@@StringReference@Internal@Windows@@QEAA@AEAY0DC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[50])
0x180023625  xor     r15d, r15d
0x180023628  mov     [rsp+148h+var_110], r15
0x18002362d  lea     rdx, [rsp+148h+var_110]
0x180023632  mov     rcx, [rsp+148h+string]
0x18002363a  call    ??$ActivateInstance@V?$ComPtr@UIPackageCollection@Provisioning@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageCollection@Provisioning@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageCollection>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageCollection>>)
0x18002363f  mov     ebx, eax
0x180023641  test    eax, eax
0x180023643  jns     short loc_180023666
0x180023645  mov     rcx, [rsp+148h]; this
0x18002364d  mov     r9d, eax; char *
0x180023650  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023657  mov     edx, 0EAh; void *
0x18002365c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023661  jmp     loc_18002371F
0x180023666  mov     [rsp+148h+var_120], r15
0x18002366b  mov     rdi, [rsp+148h+var_110]
0x180023670  mov     rax, [rdi]
0x180023673  mov     rbx, [rax+30h]
0x180023677  lea     rcx, [rsp+148h+var_120]
0x18002367c  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023681  lea     rdx, [rsp+148h+var_120]
0x180023686  mov     rcx, rdi
0x180023689  mov     rax, rbx
0x18002368c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023691  mov     ebx, eax
0x180023693  test    eax, eax
0x180023695  jns     short loc_1800236B5
0x180023697  mov     rcx, [rsp+148h]; this
0x18002369f  mov     r9d, eax; char *
0x1800236a2  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800236a9  mov     edx, 0ECh; void *
0x1800236ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800236b3  jmp     short loc_180023714
0x1800236b5  mov     qword ptr [rsp+148h+var_128], r15; int
0x1800236ba  mov     rbx, [rsp+148h+var_120]
0x1800236bf  mov     rax, [rbx]
0x1800236c2  mov     rdi, [rax]
0x1800236c5  lea     rcx, [rsp+148h+var_128]
0x1800236ca  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800236cf  lea     r8, [rsp+148h+var_128]
0x1800236d4  lea     rdx, _GUID_da650686_437b_5548_a75c_862ab4467cee
0x1800236db  mov     rcx, rbx
0x1800236de  mov     rax, rdi
0x1800236e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236e6  mov     ebx, eax
0x1800236e8  test    eax, eax
0x1800236ea  jns     short loc_18002373B
0x1800236ec  mov     rcx, [rsp+148h]; this
0x1800236f4  mov     r9d, eax; char *
0x1800236f7  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800236fe  mov     edx, 0EEh; void *
0x180023703  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023708  nop
0x180023709  lea     rcx, [rsp+148h+var_128]
0x18002370e  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023713  nop
0x180023714  lea     rcx, [rsp+148h+var_120]
0x180023719  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18002371e  nop
0x18002371f  lea     rcx, [rsp+148h+var_110]
0x180023724  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023729  nop
0x18002372a  lea     rcx, [rsp+148h+var_108]; this
0x18002372f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023734  mov     eax, ebx
0x180023736  jmp     loc_180023D1D
0x18002373b  mov     [rsp+148h+var_F8], r15d
0x180023740  mov     rcx, qword ptr [rsp+148h+var_128]
0x180023745  mov     rax, [rcx]
0x180023748  lea     rdx, [rsp+148h+var_F8]
0x18002374d  mov     rax, [rax+38h]
0x180023751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023756  mov     ebx, eax
0x180023758  test    eax, eax
0x18002375a  jns     short loc_1800237AB
0x18002375c  mov     rcx, [rsp+148h]; this
0x180023764  mov     r9d, eax; char *
0x180023767  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x18002376e  mov     edx, 0F3h; void *
0x180023773  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023778  nop
0x180023779  lea     rcx, [rsp+148h+var_128]
0x18002377e  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023783  nop
0x180023784  lea     rcx, [rsp+148h+var_120]
0x180023789  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18002378e  nop
0x18002378f  lea     rcx, [rsp+148h+var_110]
0x180023794  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023799  nop
0x18002379a  lea     rcx, [rsp+148h+var_108]; this
0x18002379f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800237a4  mov     eax, ebx
0x1800237a6  jmp     loc_180023D1D
0x1800237ab  lea     rcx, xmmword_18003EFA0
0x1800237b2  call    ?clear@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@QEAAXXZ; std::vector<std::unique_ptr<ProvPackageInfo>>::clear(void)
0x1800237b7  mov     esi, r15d
0x1800237ba  cmp     esi, [rsp+148h+var_F8]
0x1800237be  jnb     loc_180023CBF
0x1800237c4  mov     [rsp+148h+var_118], r15
0x1800237c9  mov     rdi, qword ptr [rsp+148h+var_128]
0x1800237ce  mov     rax, [rdi]
0x1800237d1  mov     rbx, [rax+30h]
0x1800237d5  lea     rcx, [rsp+148h+var_118]
0x1800237da  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800237df  lea     r8, [rsp+148h+var_118]
0x1800237e4  mov     edx, esi
0x1800237e6  mov     rcx, rdi
0x1800237e9  mov     rax, rbx
0x1800237ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237f1  mov     ebx, eax
0x1800237f3  test    eax, eax
0x1800237f5  jns     short loc_180023851
0x1800237f7  mov     rcx, [rsp+148h]; this
0x1800237ff  mov     r9d, eax; char *
0x180023802  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023809  mov     edx, 0F8h; void *
0x18002380e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023813  nop
0x180023814  lea     rcx, [rsp+148h+var_118]
0x180023819  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18002381e  nop
0x18002381f  lea     rcx, [rsp+148h+var_128]
0x180023824  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023829  nop
0x18002382a  lea     rcx, [rsp+148h+var_120]
0x18002382f  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023834  nop
0x180023835  lea     rcx, [rsp+148h+var_110]
0x18002383a  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18002383f  nop
0x180023840  lea     rcx, [rsp+148h+var_108]; this
0x180023845  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18002384a  mov     eax, ebx
0x18002384c  jmp     loc_180023D1D
0x180023851  mov     [rsp+148h+var_100], r15
0x180023856  mov     rcx, [rsp+148h+var_118]
0x18002385b  mov     rax, [rcx]
0x18002385e  mov     [rsp+148h+var_100], r15
0x180023863  lea     rdx, [rsp+148h+var_100]
0x180023868  mov     rax, [rax+30h]
0x18002386c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023871  mov     ebx, eax
0x180023873  test    eax, eax
0x180023875  jns     short loc_1800238DC
0x180023877  mov     rcx, [rsp+148h]; this
0x18002387f  mov     r9d, eax; char *
0x180023882  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023889  mov     edx, 0FBh; void *
0x18002388e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023893  nop
0x180023894  lea     rcx, [rsp+148h+var_100]
0x180023899  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18002389e  nop
0x18002389f  lea     rcx, [rsp+148h+var_118]
0x1800238a4  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800238a9  nop
0x1800238aa  lea     rcx, [rsp+148h+var_128]
0x1800238af  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800238b4  nop
0x1800238b5  lea     rcx, [rsp+148h+var_120]
0x1800238ba  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800238bf  nop
0x1800238c0  lea     rcx, [rsp+148h+var_110]
0x1800238c5  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800238ca  nop
0x1800238cb  lea     rcx, [rsp+148h+var_108]; this
0x1800238d0  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800238d5  mov     eax, ebx
0x1800238d7  jmp     loc_180023D1D
0x1800238dc  mov     rax, [rsp+148h+var_100]
0x1800238e1  mov     [rsp+148h+var_B8], rax
0x1800238e9  mov     [rsp+148h+var_E0], r15
0x1800238ee  lea     rdx, [rsp+148h+var_E0]; unsigned __int16 **
0x1800238f3  lea     rcx, [rsp+148h+var_B8]; this
0x1800238fb  call    ?GetLpcwstr@StringReference@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::StringReference::GetLpcwstr(ushort const * *)
0x180023900  mov     ebx, eax
0x180023902  test    eax, eax
0x180023904  jns     short loc_18002396B
0x180023906  mov     rcx, [rsp+148h]; this
0x18002390e  mov     r9d, eax; char *
0x180023911  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023918  mov     edx, 0FEh; void *
0x18002391d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023922  nop
0x180023923  lea     rcx, [rsp+148h+var_100]
0x180023928  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18002392d  nop
0x18002392e  lea     rcx, [rsp+148h+var_118]
0x180023933  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023938  nop
0x180023939  lea     rcx, [rsp+148h+var_128]
0x18002393e  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023943  nop
0x180023944  lea     rcx, [rsp+148h+var_120]
0x180023949  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18002394e  nop
0x18002394f  lea     rcx, [rsp+148h+var_110]
0x180023954  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023959  nop
0x18002395a  lea     rcx, [rsp+148h+var_108]; this
0x18002395f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023964  mov     eax, ebx
0x180023966  jmp     loc_180023D1D
0x18002396b  mov     [rsp+148h+var_F0], r15
0x180023970  mov     rcx, [rsp+148h+var_118]
0x180023975  mov     rax, [rcx]
0x180023978  mov     [rsp+148h+var_F0], r15
0x18002397d  lea     rdx, [rsp+148h+var_F0]
0x180023982  mov     rax, [rax+38h]
0x180023986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002398b  mov     ebx, eax
0x18002398d  test    eax, eax
0x18002398f  jns     short loc_180023A01
0x180023991  mov     rcx, [rsp+148h]; this
0x180023999  mov     r9d, eax; char *
0x18002399c  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800239a3  mov     edx, 101h; void *
0x1800239a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239ad  nop
0x1800239ae  lea     rcx, [rsp+148h+var_F0]
0x1800239b3  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800239b8  nop
0x1800239b9  lea     rcx, [rsp+148h+var_100]
0x1800239be  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800239c3  nop
0x1800239c4  lea     rcx, [rsp+148h+var_118]
0x1800239c9  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800239ce  nop
0x1800239cf  lea     rcx, [rsp+148h+var_128]
0x1800239d4  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800239d9  nop
0x1800239da  lea     rcx, [rsp+148h+var_120]
0x1800239df  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800239e4  nop
0x1800239e5  lea     rcx, [rsp+148h+var_110]
0x1800239ea  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800239ef  nop
0x1800239f0  lea     rcx, [rsp+148h+var_108]; this
0x1800239f5  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800239fa  mov     eax, ebx
0x1800239fc  jmp     loc_180023D1D
0x180023a01  mov     rax, [rsp+148h+var_F0]
0x180023a06  mov     [rsp+148h+var_98], rax
0x180023a0e  mov     [rsp+148h+var_D0], r15
0x180023a13  lea     rdx, [rsp+148h+var_D0]; unsigned __int16 **
0x180023a18  lea     rcx, [rsp+148h+var_98]; this
0x180023a20  call    ?GetLpcwstr@StringReference@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::StringReference::GetLpcwstr(ushort const * *)
0x180023a25  mov     ebx, eax
0x180023a27  test    eax, eax
0x180023a29  jns     short loc_180023A9B
0x180023a2b  mov     rcx, [rsp+148h]; this
0x180023a33  mov     r9d, eax; char *
0x180023a36  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023a3d  mov     edx, 104h; void *
0x180023a42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023a47  nop
0x180023a48  lea     rcx, [rsp+148h+var_F0]
0x180023a4d  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180023a52  nop
0x180023a53  lea     rcx, [rsp+148h+var_100]
0x180023a58  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180023a5d  nop
0x180023a5e  lea     rcx, [rsp+148h+var_118]
0x180023a63  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023a68  nop
0x180023a69  lea     rcx, [rsp+148h+var_128]
0x180023a6e  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023a73  nop
0x180023a74  lea     rcx, [rsp+148h+var_120]
0x180023a79  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023a7e  nop
0x180023a7f  lea     rcx, [rsp+148h+var_110]
0x180023a84  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180023a89  nop
0x180023a8a  lea     rcx, [rsp+148h+var_108]; this
0x180023a8f  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023a94  mov     eax, ebx
0x180023a96  jmp     loc_180023D1D
0x180023a9b  mov     [rsp+148h+var_E8], r15
0x180023aa0  mov     rcx, [rsp+148h+var_118]
0x180023aa5  mov     rax, [rcx]
0x180023aa8  mov     [rsp+148h+var_E8], r15
0x180023aad  lea     rdx, [rsp+148h+var_E8]
  ... truncated ...
```
