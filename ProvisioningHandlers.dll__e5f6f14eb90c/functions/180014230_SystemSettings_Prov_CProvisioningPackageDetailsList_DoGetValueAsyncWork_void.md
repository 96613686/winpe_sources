# SystemSettings::Prov::CProvisioningPackageDetailsList::DoGetValueAsyncWork(void)

- ea: `0x180014230`
- end: `0x180014635`
- name: `?DoGetValueAsyncWork@CProvisioningPackageDetailsList@Prov@SystemSettings@@UEAAXXZ`
- size: `1029`
- prototype: `void __fastcall(SystemSettings::Prov::CProvisioningPackageDetailsList *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800067fc`
- `0x180010944`
- `0x180012740`
- `0x180014230`
- `0x180015d74`
- `0x18001a7a4`
- `0x18001d940`
- `0x18001fb98`
- `0x18001fbb8`
- `0x18001fbfc`
- `0x180020d70`
- `0x1800230d8`
- `0x1800247cc`
- `0x1800247f4`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `msvcrt!swscanf_s` at `0x180014472`
- `msvcrt!swscanf_s` at `0x180014472`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001440f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800144ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001440f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800144ce`

## string_xrefs

- `0x1800144dd`: `SystemSettingsProvisioningDetailsInstallDateLabel`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall SystemSettings::Prov::CProvisioningPackageDetailsList::DoGetValueAsyncWork(
        SystemSettings::Prov::CProvisioningPackageDetailsList *this)
{
  SystemSettings::Prov::CProvisioningPackageDetailsList *v1; // rbx
  __int64 *PackageId; // rax
  __int64 v3; // rcx
  int InstalledPackageDetails; // eax
  __int64 v5; // rdx
  const char *v6; // r9
  __int64 PackageName; // rax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int Lpcwstr; // eax
  int v21; // eax
  const char *v22; // r9
  char *v23; // [rsp+20h] [rbp-98h]
  __int64 *v24; // [rsp+40h] [rbp-78h] BYREF
  HSTRING v25; // [rsp+48h] [rbp-70h] BYREF
  UINT32 length; // [rsp+50h] [rbp-68h] BYREF
  HSTRING v27; // [rsp+58h] [rbp-60h] BYREF
  HSTRING string; // [rsp+60h] [rbp-58h] BYREF
  SystemSettings::Prov::CProvisioningPackageDetailsList *v29; // [rsp+68h] [rbp-50h]
  int v30[4]; // [rsp+70h] [rbp-48h] BYREF
  _OWORD v31[2]; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v1 = this;
  v29 = this;
  Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(*((_QWORD *)this + 26));
  v24 = 0;
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v24);
  try
  {
    PackageId = (__int64 *)ProvPackageInfo::GetPackageId(*((_QWORD *)v1 + 33), v31);
    InstalledPackageDetails = CProvisioningSingleton::GetInstalledPackageDetails(v3, PackageId, &v24);
    if ( InstalledPackageDetails < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)InstalledPackageDetails,
        (int)v23);
    LOBYTE(v5) = 1;
    std::wstring::_Tidy(v31, v5, 0);
    if ( !v24 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        v6);
    PackageName = ProvPackageInfo::GetPackageName(*((_QWORD *)v1 + 33), v31);
    if ( *(_QWORD *)(PackageName + 24) >= 8u )
      PackageName = *(_QWORD *)PackageName;
    v8 = SystemSettings::Prov::CProvisioningPackageDetailsList::ShowPackageMetadata(
           v1,
           L"SystemSettingsProvisioningDetailsNameLabel",
           (const unsigned __int16 *)PackageName);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v8,
        (int)v23);
    LOBYTE(v9) = 1;
    std::wstring::_Tidy(v31, v9, 0);
    v10 = ProvPackageInfo::GetPackageId(*((_QWORD *)v1 + 33), v31);
    if ( *(_QWORD *)(v10 + 24) >= 8u )
      v10 = *(_QWORD *)v10;
    v11 = SystemSettings::Prov::CProvisioningPackageDetailsList::ShowPackageMetadata(
            v1,
            L"SystemSettingsProvisioningDetailsPackageIDLabel",
            (const unsigned __int16 *)v10);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v11,
        (int)v23);
    LOBYTE(v12) = 1;
    std::wstring::_Tidy(v31, v12, 0);
    string = 0;
    v13 = *v24;
    string = 0;
    v14 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v13 + 88))(v24, &string);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v14,
        (int)v23);
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    if ( length )
    {
      *(_OWORD *)v30 = 0;
      v23 = (char *)&v30[1] + 2;
      if ( swscanf_s(StringRawBuffer, L"%hu-%hu-%hu %hu:%hu:%hu", v30, (char *)v30 + 2) != 6 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x16F,
          (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
          (const char *)0xD,
          (int)&v30[1] + 2);
      v25 = 0;
      v31[0] = *(_OWORD *)v30;
      SystemSettings::Prov::formatDateTimeToString(v31, &v25);
      v16 = WindowsGetStringRawBuffer(v25, 0);
      v17 = SystemSettings::Prov::CProvisioningPackageDetailsList::ShowPackageMetadata(
              v1,
              L"SystemSettingsProvisioningDetailsInstallDateLabel",
              v16);
      if ( v17 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x174,
          (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
          (const char *)(unsigned int)v17,
          (int)&v30[1] + 2);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v25);
    }
    v27 = 0;
    v18 = *v24;
    v27 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v18 + 80))(v24, &v27);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x17A,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v19,
        (int)v23);
    *(_QWORD *)&v31[0] = v27;
    v25 = 0;
    Lpcwstr = Windows::Internal::StringReference::GetLpcwstr(
                (Windows::Internal::StringReference *)v31,
                (const unsigned __int16 **)&v25);
    if ( Lpcwstr < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)Lpcwstr,
        (int)v23);
    v21 = SystemSettings::Prov::CProvisioningPackageDetailsList::ShowPackageMetadata(
            v1,
            L"SystemSettingsProvisioningDetailsVersionLabel",
            (const unsigned __int16 *)v25);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x17E,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v21,
        (int)v23);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v27);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v24);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      v22);
    v1 = v29;
  }
  SystemSettings::DataModel::CSettingBase::OnValueChanged(v1, (const unsigned __int16 *)&stru_180035948);
}

```

## disassembly

```asm
0x180014230  mov     [rsp+arg_8], rbx
0x180014235  push    rdi
0x180014236  sub     rsp, 0B0h
0x18001423d  mov     rax, cs:__security_cookie
0x180014244  xor     rax, rsp
0x180014247  mov     [rsp+0B8h+var_18], rax
0x18001424f  mov     rbx, rcx
0x180014252  mov     [rsp+0B8h+var_50], rcx
0x180014257  mov     rcx, [rcx+0D0h]
0x18001425e  call    ?Clear@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJXZ; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(void)
0x180014263  nop
0x180014264  mov     [rsp+0B8h+var_78], 0
0x18001426d  lea     rcx, [rsp+0B8h+var_78]
0x180014272  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180014277  lea     rdx, [rsp+0B8h+var_38]
0x18001427f  mov     rcx, [rbx+108h]
0x180014286  call    ?GetPackageId@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackageId(void)
0x18001428b  nop
0x18001428c  lea     r8, [rsp+0B8h+var_78]
0x180014291  mov     rdx, rax
0x180014294  call    ?GetInstalledPackageDetails@CProvisioningSingleton@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIPackage@Provisioning@Management@Windows@@@Z; CProvisioningSingleton::GetInstalledPackageDetails(std::wstring const &,Windows::Management::Provisioning::IPackage * *)
0x180014299  mov     rcx, [rsp+0B8h]; this
0x1800142a1  test    eax, eax
0x1800142a3  jns     short loc_1800142BA
0x1800142a5  mov     r9d, eax; char *
0x1800142a8  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800142af  mov     edx, 15Bh; void *
0x1800142b4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800142ba  xor     r8d, r8d
0x1800142bd  mov     dl, 1
0x1800142bf  lea     rcx, [rsp+0B8h+var_38]
0x1800142c7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800142cc  mov     rcx, [rsp+0B8h]; this
0x1800142d4  cmp     [rsp+0B8h+var_78], 0
0x1800142da  jnz     short loc_1800142ED
0x1800142dc  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800142e3  mov     edx, 15Ch; void *
0x1800142e8  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800142ed  lea     rdx, [rsp+0B8h+var_38]
0x1800142f5  mov     rcx, [rbx+108h]
0x1800142fc  call    ?GetPackageName@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackageName(void)
0x180014301  nop
0x180014302  cmp     qword ptr [rax+18h], 8
0x180014307  jb      short loc_18001430C
0x180014309  mov     rax, [rax]
0x18001430c  mov     r8, rax; unsigned __int16 *
0x18001430f  lea     rdx, aSystemsettings; "SystemSettingsProvisioningDetailsNameLa"...
0x180014316  mov     rcx, rbx; this
0x180014319  call    ?ShowPackageMetadata@CProvisioningPackageDetailsList@Prov@SystemSettings@@AEAAJPEBG0@Z; SystemSettings::Prov::CProvisioningPackageDetailsList::ShowPackageMetadata(ushort const *,ushort const *)
0x18001431e  mov     rcx, [rsp+0B8h]; this
0x180014326  test    eax, eax
0x180014328  jns     short loc_18001433F
0x18001432a  mov     r9d, eax; char *
0x18001432d  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180014334  mov     edx, 15Fh; void *
0x180014339  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001433f  xor     r8d, r8d
0x180014342  mov     dl, 1
0x180014344  lea     rcx, [rsp+0B8h+var_38]
0x18001434c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180014351  lea     rdx, [rsp+0B8h+var_38]
0x180014359  mov     rcx, [rbx+108h]
0x180014360  call    ?GetPackageId@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackageId(void)
0x180014365  nop
0x180014366  cmp     qword ptr [rax+18h], 8
0x18001436b  jb      short loc_180014370
0x18001436d  mov     rax, [rax]
0x180014370  mov     r8, rax; unsigned __int16 *
0x180014373  lea     rdx, aSystemsettings_34; "SystemSettingsProvisioningDetailsPackag"...
0x18001437a  mov     rcx, rbx; this
0x18001437d  call    ?ShowPackageMetadata@CProvisioningPackageDetailsList@Prov@SystemSettings@@AEAAJPEBG0@Z; SystemSettings::Prov::CProvisioningPackageDetailsList::ShowPackageMetadata(ushort const *,ushort const *)
0x180014382  mov     rcx, [rsp+0B8h]; this
0x18001438a  test    eax, eax
0x18001438c  jns     short loc_1800143A3
0x18001438e  mov     r9d, eax; char *
0x180014391  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180014398  mov     edx, 162h; void *
0x18001439d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800143a3  xor     r8d, r8d
0x1800143a6  mov     dl, 1
0x1800143a8  lea     rcx, [rsp+0B8h+var_38]
0x1800143b0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800143b5  mov     [rsp+0B8h+string], 0
0x1800143be  mov     rcx, [rsp+0B8h+var_78]
0x1800143c3  mov     rax, [rcx]
0x1800143c6  mov     [rsp+0B8h+string], 0
0x1800143cf  lea     rdx, [rsp+0B8h+string]
0x1800143d4  mov     rax, [rax+58h]
0x1800143d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143dd  mov     rcx, [rsp+0B8h]; this
0x1800143e5  test    eax, eax
0x1800143e7  jns     short loc_1800143FD
0x1800143e9  mov     r9d, eax; char *
0x1800143ec  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800143f3  mov     edx, 166h; void *
0x1800143f8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800143fd  mov     [rsp+0B8h+length], 0
0x180014405  lea     rdx, [rsp+0B8h+length]; length
0x18001440a  mov     rcx, [rsp+0B8h+string]; string
0x18001440f  call    cs:__imp_WindowsGetStringRawBuffer
0x180014416  nop     dword ptr [rax+rax+00h]
0x18001441b  cmp     [rsp+0B8h+length], 0
0x180014420  jz      loc_180014517
0x180014426  xorps   xmm0, xmm0
0x180014429  movups  xmmword ptr [rsp+0B8h+var_48], xmm0
0x18001442e  mov     rdi, [rsp+0B8h]
0x180014436  lea     rcx, [rsp+0B8h+var_48+0Ch]
0x18001443b  mov     [rsp+0B8h+var_80], rcx
0x180014440  lea     rcx, [rsp+0B8h+var_48+0Ah]
0x180014445  mov     [rsp+0B8h+var_88], rcx
0x18001444a  lea     rcx, [rsp+0B8h+var_48+8]
0x18001444f  mov     [rsp+0B8h+var_90], rcx
0x180014454  lea     rcx, [rsp+0B8h+var_48+6]
0x180014459  mov     qword ptr [rsp+0B8h+var_98], rcx; int
0x18001445e  lea     r9, [rsp+0B8h+var_48+2]
0x180014463  lea     r8, [rsp+0B8h+var_48]
0x180014468  lea     rdx, aHuHuHuHuHuHu; "%hu-%hu-%hu %hu:%hu:%hu"
0x18001446f  mov     rcx, rax; Buffer
0x180014472  call    cs:__imp_swscanf_s
0x180014479  nop     dword ptr [rax+rax+00h]
0x18001447e  cmp     eax, 6
0x180014481  jz      short loc_18001449E
0x180014483  mov     r9d, 0Dh; char *
0x180014489  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180014490  mov     edx, 16Fh; void *
0x180014495  mov     rcx, rdi; this
0x180014498  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001449e  mov     [rsp+0B8h+var_70], 0
0x1800144a7  movaps  xmm0, xmmword ptr [rsp+0B8h+var_48]
0x1800144ac  movdqa  [rsp+0B8h+var_38], xmm0
0x1800144b5  lea     rdx, [rsp+0B8h+var_70]
0x1800144ba  lea     rcx, [rsp+0B8h+var_38]
0x1800144c2  call    SystemSettings__Prov__formatDateTimeToString
0x1800144c7  xor     edx, edx; length
0x1800144c9  mov     rcx, [rsp+0B8h+var_70]; string
0x1800144ce  call    cs:__imp_WindowsGetStringRawBuffer
0x1800144d5  nop     dword ptr [rax+rax+00h]
0x1800144da  mov     r8, rax; unsigned __int16 *
0x1800144dd  lea     rdx, aSystemsettings_1; "SystemSettingsProvisioningDetailsInstal"...
0x1800144e4  mov     rcx, rbx; this
0x1800144e7  call    ?ShowPackageMetadata@CProvisioningPackageDetailsList@Prov@SystemSettings@@AEAAJPEBG0@Z; SystemSettings::Prov::CProvisioningPackageDetailsList::ShowPackageMetadata(ushort const *,ushort const *)
0x1800144ec  mov     rcx, [rsp+0B8h]; this
0x1800144f4  test    eax, eax
0x1800144f6  jns     short loc_18001450D
0x1800144f8  mov     r9d, eax; char *
0x1800144fb  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180014502  mov     edx, 174h; void *
0x180014507  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001450d  lea     rcx, [rsp+0B8h+var_70]
0x180014512  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180014517  mov     [rsp+0B8h+var_60], 0
0x180014520  mov     rcx, [rsp+0B8h+var_78]
0x180014525  mov     rax, [rcx]
0x180014528  mov     [rsp+0B8h+var_60], 0
0x180014531  lea     rdx, [rsp+0B8h+var_60]
0x180014536  mov     rax, [rax+50h]
0x18001453a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001453f  mov     rcx, [rsp+0B8h]; this
0x180014547  test    eax, eax
0x180014549  jns     short loc_18001455F
0x18001454b  mov     r9d, eax; char *
0x18001454e  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180014555  mov     edx, 17Ah; void *
0x18001455a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001455f  mov     rax, [rsp+0B8h+var_60]
0x180014564  mov     qword ptr [rsp+0B8h+var_38], rax
0x18001456c  mov     [rsp+0B8h+var_70], 0
0x180014575  lea     rdx, [rsp+0B8h+var_70]; unsigned __int16 **
0x18001457a  lea     rcx, [rsp+0B8h+var_38]; this
0x180014582  call    ?GetLpcwstr@StringReference@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::StringReference::GetLpcwstr(ushort const * *)
0x180014587  mov     rcx, [rsp+0B8h]; this
0x18001458f  test    eax, eax
0x180014591  jns     short loc_1800145A7
0x180014593  mov     r9d, eax; char *
0x180014596  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x18001459d  mov     edx, 17Dh; void *
0x1800145a2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800145a7  mov     r8, [rsp+0B8h+var_70]; unsigned __int16 *
0x1800145ac  lea     rdx, aSystemsettings_42; "SystemSettingsProvisioningDetailsVersio"...
0x1800145b3  mov     rcx, rbx; this
0x1800145b6  call    ?ShowPackageMetadata@CProvisioningPackageDetailsList@Prov@SystemSettings@@AEAAJPEBG0@Z; SystemSettings::Prov::CProvisioningPackageDetailsList::ShowPackageMetadata(ushort const *,ushort const *)
0x1800145bb  mov     rcx, [rsp+0B8h]; this
0x1800145c3  test    eax, eax
0x1800145c5  jns     short loc_1800145DC
0x1800145c7  mov     r9d, eax; char *
0x1800145ca  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800145d1  mov     edx, 17Eh; void *
0x1800145d6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800145dc  lea     rcx, [rsp+0B8h+var_60]
0x1800145e1  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800145e6  nop
0x1800145e7  lea     rcx, [rsp+0B8h+string]
0x1800145ec  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800145f1  nop
0x1800145f2  lea     rcx, [rsp+0B8h+var_78]
0x1800145f7  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800145fc  nop
0x1800145fd  jmp     short loc_180014604
0x1800145ff  mov     rbx, [rsp+0B8h+var_50]
0x180014604  lea     rdx, stru_180035948; unsigned __int16 *
0x18001460b  mov     rcx, rbx; this
0x18001460e  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180014613  mov     rcx, [rsp+0B8h+var_18]
0x18001461b  xor     rcx, rsp; StackCookie
0x18001461e  call    __security_check_cookie
0x180014623  mov     rbx, [rsp+0B8h+arg_8]
0x18001462b  add     rsp, 0B0h
0x180014632  pop     rdi
0x180014633  retn
```
