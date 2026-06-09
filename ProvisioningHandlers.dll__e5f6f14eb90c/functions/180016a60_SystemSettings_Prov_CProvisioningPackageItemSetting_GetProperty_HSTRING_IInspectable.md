# SystemSettings::Prov::CProvisioningPackageItemSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180016a60`
- end: `0x180017226`
- name: `?GetProperty@CProvisioningPackageItemSetting@Prov@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1990`
- prototype: `int(SystemSettings::Prov::CProvisioningPackageItemSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800067fc`
- `0x1800087ec`
- `0x180010944`
- `0x1800128c8`
- `0x18001291c`
- `0x180012af4`
- `0x180013018`
- `0x180013764`
- `0x180016a60`
- `0x18001a1d0`
- `0x18001e88c`
- `0x18001fb98`
- `0x18001fbb8`
- `0x18001fbfc`
- `0x180020d70`
- `0x1800230d8`
- `0x1800247cc`
- `0x1800247f4`
- `0x18002481c`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `msvcrt!swscanf_s` at `0x180016d0f`
- `msvcrt!swscanf_s` at `0x180016d0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016d66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016d66`

## string_xrefs

- `0x180016c01`: `Error during package installation`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall SystemSettings::Prov::CProvisioningPackageItemSetting::GetProperty(
        SystemSettings::Prov::CProvisioningPackageItemSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  __int64 PackageName; // rax
  int v8; // ebx
  __int64 v9; // rdx
  const unsigned __int16 *v11; // r8
  __int64 *PackageId; // rax
  __int64 v13; // rcx
  int InstalledPackageDetails; // eax
  __int64 v15; // rdx
  const char *v16; // r9
  int v17; // edx
  unsigned __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  const wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v25; // rax
  int v26; // eax
  unsigned int v27; // ebx
  __int64 v28; // rdx
  __int64 v29; // rdx
  unsigned __int16 **PackagePath; // rbx
  const unsigned __int16 *v31; // rcx
  int v32; // eax
  unsigned int v33; // ebx
  __int64 v34; // rdx
  const unsigned __int16 *v35; // r8
  unsigned __int8 v36; // di
  const unsigned __int16 *v37; // r8
  int v38; // eax
  unsigned int v39; // ebx
  int v40; // eax
  unsigned int v41; // ebx
  const unsigned __int16 *v42; // r8
  int v43; // eax
  unsigned int v44; // ebx
  int v45; // eax
  unsigned int v46; // ebx
  const unsigned __int16 *v47; // r8
  int Boolean; // eax
  unsigned int v49; // ebx
  int v50; // eax
  unsigned int v51; // ebx
  int v52; // eax
  unsigned int v53; // ebx
  __int64 v54; // [rsp+0h] [rbp-D8h] BYREF
  int v55[2]; // [rsp+20h] [rbp-B8h]
  int *v56; // [rsp+28h] [rbp-B0h]
  char *v57; // [rsp+30h] [rbp-A8h]
  int *v58; // [rsp+38h] [rbp-A0h]
  struct SystemSettings::Prov::CProvisioningPackageInfoDynamicDatabase *v59; // [rsp+40h] [rbp-98h] BYREF
  UINT32 length; // [rsp+48h] [rbp-90h] BYREF
  HSTRING v61; // [rsp+50h] [rbp-88h] BYREF
  HSTRING string; // [rsp+58h] [rbp-80h] BYREF
  int v63[4]; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int16 *v64[3]; // [rsp+70h] [rbp-68h] BYREF
  unsigned __int64 v65; // [rsp+88h] [rbp-50h]
  _OWORD v66[2]; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (const WCHAR *)&stru_180034FA0, (const unsigned __int16 *)a3) )
  {
    PackageName = ProvPackageInfo::GetPackageName(*((_QWORD *)this + 32), v66);
    if ( *(_QWORD *)(PackageName + 24) >= 8u )
      PackageName = *(_QWORD *)PackageName;
    v8 = SystemSettings::DataModel::PropValueHelper::CreateString((const unsigned __int16 *)PackageName, a3);
    LOBYTE(v9) = 1;
    std::wstring::_Tidy(v66, v9, 0);
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x361,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v8,
        v55[0]);
      return (unsigned int)v8;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (const WCHAR *)&stru_180034FB8, v6) )
  {
    v59 = 0;
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
    PackageId = (__int64 *)ProvPackageInfo::GetPackageId(*((_QWORD *)this + 32), v66);
    InstalledPackageDetails = CProvisioningSingleton::GetInstalledPackageDetails(v13, PackageId, &v59);
    if ( InstalledPackageDetails < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x366,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)InstalledPackageDetails,
        v55[0]);
    LOBYTE(v15) = 1;
    std::wstring::_Tidy(v66, v15, 0);
    if ( !v59 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x367,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        v16);
    *(_OWORD *)v63 = 0;
    string = 0;
    length = 0;
    v61 = 0;
    v65 = 7;
    v64[2] = 0;
    LOWORD(v64[0]) = 0;
    v17 = *((_DWORD *)this + 66);
    if ( v17 )
    {
      v18 = (unsigned int)(v17 - 1);
      if ( (_DWORD)v18 )
      {
        if ( (_DWORD)v18 == 1 )
        {
          v19 = SystemSettings::DataModel::PropValueHelper::CreateString(L"Error during package installation", a3);
          v20 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x381,
              (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
              (const char *)(unsigned int)v19,
              v55[0]);
            LOBYTE(v21) = 1;
            std::wstring::_Tidy(v64, v21, 0);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v61);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
            return v20;
          }
        }
      }
      else
      {
        v22 = *(_QWORD *)v59;
        string = 0;
        v23 = (*(__int64 (__fastcall **)(struct SystemSettings::Prov::CProvisioningPackageInfoDynamicDatabase *, HSTRING *))(v22 + 88))(
                v59,
                &string);
        if ( v23 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x373,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
            (const char *)(unsigned int)v23,
            v55[0]);
        StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
        if ( length )
        {
          *(_OWORD *)v63 = 0;
          v58 = &v63[3];
          v57 = (char *)&v63[2] + 2;
          v56 = &v63[2];
          *(_QWORD *)v55 = (char *)&v63[1] + 2;
          if ( swscanf_s(StringRawBuffer, L"%hu-%hu-%hu %hu:%hu:%hu", v63, (char *)v63 + 2) != 6 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x37A,
              (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
              (const char *)0xD,
              v55[0]);
          v61 = 0;
          v66[0] = *(_OWORD *)v63;
          SystemSettings::Prov::formatDateTimeToString(v66, &v61);
          v25 = WindowsGetStringRawBuffer(v61, 0);
          v26 = SystemSettings::DataModel::PropValueHelper::CreateString(v25, a3);
          v27 = v26;
          if ( v26 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x37D,
              (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
              (const char *)(unsigned int)v26,
              v55[0]);
            LOBYTE(v28) = 1;
            std::wstring::_Tidy(v64, v28, 0);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v61);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
            return v27;
          }
        }
      }
    }
    else
    {
      try
      {
        PackagePath = (unsigned __int16 **)ProvPackageInfo::GetPackagePath(*((_QWORD *)this + 32), v66);
        if ( v64 != PackagePath )
        {
          LOBYTE(v29) = 1;
          std::wstring::_Tidy(v64, v29, 0);
          std::wstring::_Assign_rv(v64, PackagePath);
        }
        LOBYTE(v29) = 1;
        std::wstring::_Tidy(v66, v29, 0);
        v31 = (const unsigned __int16 *)v64;
        if ( v65 >= 8 )
          v31 = v64[0];
        v32 = SystemSettings::DataModel::PropValueHelper::CreateString(v31, a3);
      }
      catch ( ... )
      {
        v18 = (unsigned __int64)&v54;
        goto LABEL_30;
      }
      v33 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x38A,
          (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
          (const char *)(unsigned int)v32,
          v55[0]);
        LOBYTE(v34) = 1;
        std::wstring::_Tidy(v64, v34, 0);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v61);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
        return v33;
      }
    }
LABEL_30:
    LOBYTE(v18) = 1;
    std::wstring::_Tidy(v64, v18, 0);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v61);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (const WCHAR *)&stru_180035018, v11) )
  {
    v36 = 0;
    if ( *((_DWORD *)this + 66) == 3 || *((_DWORD *)this + 66) == 4 || (unsigned int)(*((_DWORD *)this + 66) - 5) <= 1 )
      v36 = 1;
    SystemSettings::DataModel::PropValueHelper::CreateBoolean(v36, a3);
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (const WCHAR *)&stru_180035040, v35) )
  {
    v59 = 0;
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
    v38 = SystemSettings::Prov::CProvisioningInstallSetting::CreateInstance(
            *((struct ProvPackageInfo **)this + 32),
            *((_BYTE *)this + 249),
            &v59);
    v39 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A5,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v38,
        v55[0]);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
      return v39;
    }
    v40 = (**(__int64 (__fastcall ***)(struct SystemSettings::Prov::CProvisioningPackageInfoDynamicDatabase *, GUID *, struct IInspectable **))v59)(
            v59,
            &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
            a3);
    v41 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A6,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v40,
        v55[0]);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
      return v41;
    }
LABEL_55:
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (const WCHAR *)&stru_180035068, v37) )
  {
    v59 = 0;
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
    v43 = SystemSettings::Prov::CProvisioningDeleteSetting::CreateInstance(
            *((struct ProvPackageInfo **)this + 32),
            *((_BYTE *)this + 250),
            &v59);
    v44 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3AB,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v43,
        v55[0]);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
      return v44;
    }
    v45 = (**(__int64 (__fastcall ***)(struct SystemSettings::Prov::CProvisioningPackageInfoDynamicDatabase *, GUID *, struct IInspectable **))v59)(
            v59,
            &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
            a3);
    v46 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3AC,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v45,
        v55[0]);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
      return v46;
    }
    goto LABEL_55;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (const WCHAR *)&stru_180035088, v42) )
  {
    Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 251), a3);
    v49 = Boolean;
    if ( Boolean < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B0,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)Boolean,
        v55[0]);
      return v49;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (const WCHAR *)&stru_1800350A0, v47) )
  {
    v59 = 0;
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
    v50 = SystemSettings::Prov::CProvisioningPackageInfoDynamicDatabase::CreateInstance(
            *((struct ProvPackageInfo **)this + 32),
            *((_BYTE *)this + 251),
            &v59);
    v51 = v50;
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B5,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v50,
        v55[0]);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
      return v51;
    }
    v52 = (**(__int64 (__fastcall ***)(struct SystemSettings::Prov::CProvisioningPackageInfoDynamicDatabase *, GUID *, struct IInspectable **))v59)(
            v59,
            &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
            a3);
    v53 = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B6,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v52,
        v55[0]);
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v59);
      return v53;
    }
    goto LABEL_55;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3BA,
    (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
    (const char *)0x8000FFFFLL,
    v55[0]);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180016a60  mov     [rsp+arg_18], rbx
0x180016a65  push    rsi
0x180016a66  push    rdi
0x180016a67  push    r14
0x180016a69  sub     rsp, 0C0h
0x180016a70  mov     rax, cs:__security_cookie
0x180016a77  xor     rax, rsp
0x180016a7a  mov     [rsp+0D8h+var_28], rax
0x180016a82  mov     rsi, r8
0x180016a85  mov     rdi, rdx
0x180016a88  mov     rbx, rcx
0x180016a8b  xor     r14d, r14d
0x180016a8e  mov     [r8], r14
0x180016a91  lea     rdx, stru_180034FA0; HSTRING
0x180016a98  mov     rcx, rdi; this
0x180016a9b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180016aa0  test    al, al
0x180016aa2  jz      short loc_180016B0C
0x180016aa4  lea     rdx, [rsp+0D8h+var_48]
0x180016aac  mov     rcx, [rbx+100h]
0x180016ab3  call    ?GetPackageName@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackageName(void)
0x180016ab8  cmp     qword ptr [rax+18h], 8
0x180016abd  jb      short loc_180016AC2
0x180016abf  mov     rax, [rax]
0x180016ac2  mov     rdx, rsi; struct IInspectable **
0x180016ac5  mov     rcx, rax; unsigned __int16 *
0x180016ac8  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180016acd  mov     ebx, eax
0x180016acf  xor     r8d, r8d
0x180016ad2  mov     dl, 1
0x180016ad4  lea     rcx, [rsp+0D8h+var_48]
0x180016adc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016ae1  test    ebx, ebx
0x180016ae3  jns     loc_1800171D4
0x180016ae9  mov     rcx, [rsp+0D8h]; this
0x180016af1  mov     r9d, ebx; char *
0x180016af4  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180016afb  mov     edx, 361h; void *
0x180016b00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b05  mov     eax, ebx
0x180016b07  jmp     loc_180017201
0x180016b0c  lea     rdx, stru_180034FB8; HSTRING
0x180016b13  mov     rcx, rdi; this
0x180016b16  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180016b1b  test    al, al
0x180016b1d  jz      loc_180016EE0
0x180016b23  mov     [rsp+0D8h+var_98], r14
0x180016b28  lea     rcx, [rsp+0D8h+var_98]
0x180016b2d  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180016b32  lea     rdx, [rsp+0D8h+var_48]
0x180016b3a  mov     rcx, [rbx+100h]
0x180016b41  call    ?GetPackageId@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackageId(void)
0x180016b46  nop
0x180016b47  lea     r8, [rsp+0D8h+var_98]
0x180016b4c  mov     rdx, rax
0x180016b4f  call    ?GetInstalledPackageDetails@CProvisioningSingleton@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIPackage@Provisioning@Management@Windows@@@Z; CProvisioningSingleton::GetInstalledPackageDetails(std::wstring const &,Windows::Management::Provisioning::IPackage * *)
0x180016b54  mov     rcx, [rsp+0D8h]; this
0x180016b5c  test    eax, eax
0x180016b5e  jns     short loc_180016B75
0x180016b60  mov     r9d, eax; char *
0x180016b63  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180016b6a  mov     edx, 366h; void *
0x180016b6f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016b75  xor     r8d, r8d
0x180016b78  mov     dil, 1
0x180016b7b  mov     dl, dil
0x180016b7e  lea     rcx, [rsp+0D8h+var_48]
0x180016b86  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016b8b  mov     rax, [rsp+0D8h]
0x180016b93  mov     rcx, [rsp+0D8h+var_98]
0x180016b98  test    rcx, rcx
0x180016b9b  jnz     short loc_180016BB1
0x180016b9d  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180016ba4  mov     edx, 367h; void *
0x180016ba9  mov     rcx, rax; this
0x180016bac  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180016bb1  xorps   xmm0, xmm0
0x180016bb4  movups  xmmword ptr [rsp+0D8h+var_78], xmm0
0x180016bb9  mov     [rsp+0D8h+string], r14
0x180016bbe  mov     [rsp+0D8h+length], r14d
0x180016bc3  mov     [rsp+0D8h+var_88], r14
0x180016bc8  mov     [rsp+0D8h+var_50], 7
0x180016bd4  mov     [rsp+0D8h+var_58], r14
0x180016bdc  mov     word ptr [rsp+0D8h+var_68], r14w
0x180016be2  mov     edx, [rbx+108h]
0x180016be8  test    edx, edx
0x180016bea  jz      loc_180016DDC
0x180016bf0  sub     edx, 1
0x180016bf3  jz      short loc_180016C6C
0x180016bf5  cmp     edx, 1
0x180016bf8  jnz     loc_180016EAA
0x180016bfe  mov     rdx, rsi; struct IInspectable **
0x180016c01  lea     rcx, aErrorDuringPac; "Error during package installation"
0x180016c08  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180016c0d  mov     ebx, eax
0x180016c0f  test    eax, eax
0x180016c11  jns     loc_180016EAA
0x180016c17  mov     rcx, [rsp+0D8h]; this
0x180016c1f  mov     r9d, eax; char *
0x180016c22  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180016c29  mov     edx, 381h; void *
0x180016c2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c33  nop
0x180016c34  xor     r8d, r8d
0x180016c37  mov     dl, dil
0x180016c3a  lea     rcx, [rsp+0D8h+var_68]
0x180016c3f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016c44  nop
0x180016c45  lea     rcx, [rsp+0D8h+var_88]
0x180016c4a  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016c4f  nop
0x180016c50  lea     rcx, [rsp+0D8h+string]
0x180016c55  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016c5a  nop
0x180016c5b  lea     rcx, [rsp+0D8h+var_98]
0x180016c60  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180016c65  mov     eax, ebx
0x180016c67  jmp     loc_180017201
0x180016c6c  mov     rax, [rcx]
0x180016c6f  mov     [rsp+0D8h+string], r14
0x180016c74  lea     rdx, [rsp+0D8h+string]
0x180016c79  mov     rax, [rax+58h]
0x180016c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c82  mov     rcx, [rsp+0D8h]; this
0x180016c8a  test    eax, eax
0x180016c8c  jns     short loc_180016CA2
0x180016c8e  mov     r9d, eax; char *
0x180016c91  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180016c98  mov     edx, 373h; void *
0x180016c9d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016ca2  lea     rdx, [rsp+0D8h+length]; length
0x180016ca7  mov     rcx, [rsp+0D8h+string]; string
0x180016cac  call    cs:__imp_WindowsGetStringRawBuffer
0x180016cb3  nop     dword ptr [rax+rax+00h]
0x180016cb8  cmp     [rsp+0D8h+length], r14d
0x180016cbd  jz      loc_180016EAA
0x180016cc3  xorps   xmm0, xmm0
0x180016cc6  movups  xmmword ptr [rsp+0D8h+var_78], xmm0
0x180016ccb  mov     rbx, [rsp+0D8h]
0x180016cd3  lea     rcx, [rsp+0D8h+var_78+0Ch]
0x180016cd8  mov     [rsp+0D8h+var_A0], rcx
0x180016cdd  lea     rcx, [rsp+0D8h+var_78+0Ah]
0x180016ce2  mov     [rsp+0D8h+var_A8], rcx
0x180016ce7  lea     rcx, [rsp+0D8h+var_78+8]
0x180016cec  mov     [rsp+0D8h+var_B0], rcx
0x180016cf1  lea     rcx, [rsp+0D8h+var_78+6]
0x180016cf6  mov     qword ptr [rsp+0D8h+var_B8], rcx; int
0x180016cfb  lea     r9, [rsp+0D8h+var_78+2]
0x180016d00  lea     r8, [rsp+0D8h+var_78]
0x180016d05  lea     rdx, aHuHuHuHuHuHu; "%hu-%hu-%hu %hu:%hu:%hu"
0x180016d0c  mov     rcx, rax; Buffer
0x180016d0f  call    cs:__imp_swscanf_s
0x180016d16  nop     dword ptr [rax+rax+00h]
0x180016d1b  cmp     eax, 6
0x180016d1e  jz      short loc_180016D3A
0x180016d20  mov     r9d, 0Dh; char *
0x180016d26  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180016d2d  mov     edx, 37Ah; void *
0x180016d32  mov     rcx, rbx; this
0x180016d35  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016d3a  mov     [rsp+0D8h+var_88], r14
0x180016d3f  movaps  xmm0, xmmword ptr [rsp+0D8h+var_78]
0x180016d44  movdqa  [rsp+0D8h+var_48], xmm0
0x180016d4d  lea     rdx, [rsp+0D8h+var_88]
0x180016d52  lea     rcx, [rsp+0D8h+var_48]
0x180016d5a  call    SystemSettings__Prov__formatDateTimeToString
0x180016d5f  xor     edx, edx; length
0x180016d61  mov     rcx, [rsp+0D8h+var_88]; string
0x180016d66  call    cs:__imp_WindowsGetStringRawBuffer
0x180016d6d  nop     dword ptr [rax+rax+00h]
0x180016d72  mov     rcx, rax; unsigned __int16 *
0x180016d75  mov     rdx, rsi; struct IInspectable **
0x180016d78  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180016d7d  mov     ebx, eax
0x180016d7f  test    eax, eax
0x180016d81  jns     loc_180016EAA
0x180016d87  mov     rcx, [rsp+0D8h]; this
0x180016d8f  mov     r9d, eax; char *
0x180016d92  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180016d99  mov     edx, 37Dh; void *
0x180016d9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016da3  nop
0x180016da4  xor     r8d, r8d
0x180016da7  mov     dl, dil
0x180016daa  lea     rcx, [rsp+0D8h+var_68]
0x180016daf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016db4  nop
0x180016db5  lea     rcx, [rsp+0D8h+var_88]
0x180016dba  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016dbf  nop
0x180016dc0  lea     rcx, [rsp+0D8h+string]
0x180016dc5  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016dca  nop
0x180016dcb  lea     rcx, [rsp+0D8h+var_98]
0x180016dd0  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180016dd5  mov     eax, ebx
0x180016dd7  jmp     loc_180017201
0x180016ddc  lea     rdx, [rsp+0D8h+var_48]
0x180016de4  mov     rcx, [rbx+100h]
0x180016deb  call    ?GetPackagePath@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackagePath(void)
0x180016df0  mov     rbx, rax
0x180016df3  lea     rax, [rsp+0D8h+var_68]
0x180016df8  cmp     rax, rbx
0x180016dfb  jz      short loc_180016E1B
0x180016dfd  xor     r8d, r8d
0x180016e00  mov     dl, dil
0x180016e03  lea     rcx, [rsp+0D8h+var_68]
0x180016e08  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016e0d  mov     rdx, rbx
0x180016e10  lea     rcx, [rsp+0D8h+var_68]
0x180016e15  call    ?_Assign_rv@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX$$QEAV12@@Z; std::wstring::_Assign_rv(std::wstring &&)
0x180016e1a  nop
0x180016e1b  xor     r8d, r8d
0x180016e1e  mov     dl, dil
0x180016e21  lea     rcx, [rsp+0D8h+var_48]
0x180016e29  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016e2e  lea     rcx, [rsp+0D8h+var_68]
0x180016e33  cmp     [rsp+0D8h+var_50], 8
0x180016e3c  cmovnb  rcx, [rsp+0D8h+var_68]; unsigned __int16 *
0x180016e42  mov     rdx, rsi; struct IInspectable **
0x180016e45  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180016e4a  mov     ebx, eax
0x180016e4c  test    eax, eax
0x180016e4e  jns     short loc_180016EA5
0x180016e50  mov     rcx, [rsp+0D8h]; this
0x180016e58  mov     r9d, eax; char *
0x180016e5b  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180016e62  mov     edx, 38Ah; void *
0x180016e67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016e6c  nop
0x180016e6d  xor     r8d, r8d
0x180016e70  mov     dl, dil
0x180016e73  lea     rcx, [rsp+0D8h+var_68]
0x180016e78  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016e7d  nop
0x180016e7e  lea     rcx, [rsp+0D8h+var_88]
0x180016e83  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016e88  nop
0x180016e89  lea     rcx, [rsp+0D8h+string]
0x180016e8e  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016e93  nop
0x180016e94  lea     rcx, [rsp+0D8h+var_98]
0x180016e99  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180016e9e  mov     eax, ebx
0x180016ea0  jmp     loc_180017201
0x180016ea5  jmp     short loc_180016EAA
0x180016ea7  mov     dil, 1
0x180016eaa  xor     r8d, r8d
0x180016ead  mov     dl, dil
0x180016eb0  lea     rcx, [rsp+0D8h+var_68]
0x180016eb5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016eba  nop
0x180016ebb  lea     rcx, [rsp+0D8h+var_88]
0x180016ec0  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016ec5  nop
0x180016ec6  lea     rcx, [rsp+0D8h+string]
0x180016ecb  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016ed0  nop
0x180016ed1  lea     rcx, [rsp+0D8h+var_98]
0x180016ed6  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180016edb  jmp     loc_1800171D4
0x180016ee0  lea     rdx, stru_180035018; HSTRING
0x180016ee7  mov     rcx, rdi; this
0x180016eea  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180016eef  test    al, al
0x180016ef1  jz      short loc_180016F23
0x180016ef3  mov     dil, r14b
0x180016ef6  mov     ecx, [rbx+108h]
0x180016efc  sub     ecx, 3
0x180016eff  jz      short loc_180016F10
0x180016f01  sub     ecx, 1
0x180016f04  jz      short loc_180016F10
0x180016f06  sub     ecx, 1
0x180016f09  jz      short loc_180016F10
0x180016f0b  cmp     ecx, 1
0x180016f0e  jnz     short loc_180016F13
0x180016f10  mov     dil, 1
0x180016f13  mov     rdx, rsi; struct IInspectable **
0x180016f16  mov     cl, dil; unsigned __int8
0x180016f19  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x180016f1e  jmp     loc_1800171D4
0x180016f23  lea     rdx, stru_180035040; HSTRING
0x180016f2a  mov     rcx, rdi; this
0x180016f2d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180016f32  test    al, al
0x180016f34  jz      loc_180016FF1
0x180016f3a  mov     [rsp+0D8h+var_98], r14
0x180016f3f  lea     rcx, [rsp+0D8h+var_98]
0x180016f44  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180016f49  lea     r8, [rsp+0D8h+var_98]; struct SystemSettings::Prov::CProvisioningInstallSetting **
0x180016f4e  mov     dl, [rbx+0F9h]; unsigned __int8
0x180016f54  mov     rcx, [rbx+100h]; struct ProvPackageInfo *
0x180016f5b  call    ?CreateInstance@CProvisioningInstallSetting@Prov@SystemSettings@@SAJPEAVProvPackageInfo@@EPEAPEAV123@@Z; SystemSettings::Prov::CProvisioningInstallSetting::CreateInstance(ProvPackageInfo *,uchar,SystemSettings::Prov::CProvisioningInstallSetting * *)
0x180016f60  mov     ebx, eax
0x180016f62  test    eax, eax
0x180016f64  jns     short loc_180016F94
0x180016f66  mov     rcx, [rsp+0D8h]; this
0x180016f6e  mov     r9d, eax; char *
0x180016f71  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180016f78  mov     edx, 3A5h; void *
  ... truncated ...
```
