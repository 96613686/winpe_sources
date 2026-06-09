# ModernDeployment::Autopilot::Core::DeviceLinkUtilities::ExportDeviceLinkInfoCsvAsync(HSTRING__ *,ModernDeployment::Autopilot::Core::DeviceLinkFormatFlags,Windows::Foundation::IAsyncOperation<HSTRING__ *> * *)

- ea: `0x180129590`
- end: `0x180129976`
- name: `?ExportDeviceLinkInfoCsvAsync@DeviceLinkUtilities@Core@Autopilot@ModernDeployment@@UEAAJPEAUHSTRING__@@W4DeviceLinkFormatFlags@234@PEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@Z`
- size: `998`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x180081294`
- `0x180081cac`
- `0x180084574`
- `0x18008a67c`
- `0x18008aea8`
- `0x18008d620`
- `0x18008e0c0`
- `0x18008e344`
- `0x1800dbea4`
- `0x1800dcc20`
- `0x1801287f0`
- `0x180128ba4`
- `0x180129590`
- `0x18017a534`
- `0x180200010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180129710`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180129710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180129653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180129653`

## string_xrefs

- `0x1801295de`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x18012960b`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x180129638`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x1801296b6`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x180129730`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x1801297e1`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x18012986c`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceLinkUtilities::ExportDeviceLinkInfoCsvAsync(
        unsigned __int16 *a1,
        HSTRING a2,
        int a3,
        __int64 a4)
{
  PCWSTR StringRawBuffer; // rax
  int Setting; // eax
  unsigned int v11; // ebx
  __int64 v12; // rbx
  __int64 v13; // rax
  unsigned int FolderHierarchy; // ebx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // ebx
  _QWORD *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rcx
  int v25[4]; // [rsp+20h] [rbp-98h] BYREF
  unsigned __int16 *v26; // [rsp+30h] [rbp-88h] BYREF
  int v27[2]; // [rsp+38h] [rbp-80h] BYREF
  _BYTE v28[32]; // [rsp+40h] [rbp-78h] BYREF
  _QWORD *v29; // [rsp+60h] [rbp-58h] BYREF
  char v30[32]; // [rsp+68h] [rbp-50h] BYREF
  int v31; // [rsp+88h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkutilities.cpp",
      (const char *)0x80004001LL,
      v25[0]);
    return 2147500033LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkutilities.cpp",
      (const char *)0x80070057LL,
      v25[0]);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkutilities.cpp",
      (const char *)0x80004003LL,
      v25[0]);
    return 2147500035LL;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  std::wstring::wstring(v28, StringRawBuffer);
  if ( (unsigned __int8)Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(v28) )
    goto LABEL_19;
  v26 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v26,
    0);
  Setting = EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUtils::AutoPilotGetSetting(
              (wchar_t *)L"ESP.AutomaticallyExportLogsToRemovableDrive",
              &v26);
  v11 = Setting;
  if ( Setting < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkutilities.cpp",
      (const char *)(unsigned int)Setting,
      v25[0]);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
    std::wstring::_Tidy_deallocate(v28);
    return v11;
  }
  std::wstring::wstring(&v29, v26);
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v29);
  if ( (unsigned int)_o__wcsicmp(v13, v12) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkutilities.cpp",
      (const char *)0x8103C010LL,
      v25[0]);
    std::wstring::_Tidy_deallocate(&v29);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
    std::wstring::_Tidy_deallocate(v28);
    return 2164506640LL;
  }
  FolderHierarchy = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchy(v28);
  if ( (FolderHierarchy & 0x80000000) == 0 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
      McTemplateU0z_EventWriteTransfer(v16, AutopilotExportLinkCreatedFolder, v15);
    }
    std::wstring::_Tidy_deallocate(&v29);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
LABEL_19:
    v26 = a1;
    if ( a1 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)a1 + 8LL))(a1);
    *(_QWORD *)v27 = 0;
    *(_QWORD *)v25 = v27;
    v19 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(v25);
    v20 = Microsoft::WRL::AsWeak<ModernDeployment::Autopilot::Core::IDeviceProvisioningStatusCallback>(a1, v19);
    v21 = v20;
    if ( v20 >= 0 )
    {
      v29 = *(_QWORD **)v27;
      *(_QWORD *)v27 = 0;
      std::wstring::wstring(v30, v28);
      v31 = a3;
      v21 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CHSTRINGResult_HSTRING_____Windows::Internal::ComTaskPoolHandler__ModernDeployment::Autopilot::Core::DeviceLinkUtilities::ExportDeviceLinkInfoCsvAsync_::_3_::_lambda_1___(
              v25,
              a4,
              v23,
              &v29,
              0x8000000003LL,
              0,
              v26);
      ModernDeployment::Autopilot::Core::DeviceLinkManager::RequestDiscoveryUrlAsync_::_3_::_lambda_1_::__lambda_1_(&v29);
      v24 = *(_QWORD **)v27;
      if ( *(_QWORD *)v27 )
      {
        *(_QWORD *)v27 = 0;
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v24 + 16LL))(v24, *v24);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkutilities.cpp",
        (const char *)(unsigned int)v20,
        v25[0]);
      v22 = *(_QWORD **)v27;
      if ( *(_QWORD *)v27 )
      {
        *(_QWORD *)v27 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    std::wstring::_Tidy_deallocate(v28);
    return v21;
  }
  if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
  {
    v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    McTemplateU0dz_EventWriteTransfer(v18, AutopilotExportLinkFailedToCreateFolder, FolderHierarchy, v17);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4C,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkutilities.cpp",
    (const char *)FolderHierarchy,
    v25[0]);
  std::wstring::_Tidy_deallocate(&v29);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
  std::wstring::_Tidy_deallocate(v28);
  return FolderHierarchy;
}

```

## disassembly

```asm
0x180129590  mov     [rsp+arg_0], rbx
0x180129595  push    rsi
0x180129596  push    rdi
0x180129597  push    r14
0x180129599  sub     rsp, 0A0h
0x1801295a0  mov     rax, cs:__security_cookie
0x1801295a7  xor     rax, rsp
0x1801295aa  mov     [rsp+0B8h+var_28], rax
0x1801295b2  mov     rsi, r9
0x1801295b5  mov     r14d, r8d
0x1801295b8  mov     rbx, rdx
0x1801295bb  mov     rdi, rcx
0x1801295be  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801295c5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801295ca  test    al, al
0x1801295cc  jnz     short loc_1801295F6
0x1801295ce  mov     rcx, [rsp+0B8h]; this
0x1801295d6  mov     ebx, 80004001h
0x1801295db  mov     r9d, ebx; char *
0x1801295de  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801295e5  mov     edx, 2Bh ; '+'; void *
0x1801295ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801295ef  mov     eax, ebx
0x1801295f1  jmp     loc_180129951
0x1801295f6  test    rbx, rbx
0x1801295f9  jnz     short loc_180129623
0x1801295fb  mov     rcx, [rsp+0B8h]; this
0x180129603  mov     ebx, 80070057h
0x180129608  mov     r9d, ebx; char *
0x18012960b  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x180129612  mov     edx, 2Dh ; '-'; void *
0x180129617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012961c  mov     eax, ebx
0x18012961e  jmp     loc_180129951
0x180129623  test    rsi, rsi
0x180129626  jnz     short loc_18012964E
0x180129628  mov     rcx, [rsp+0B8h]; this
0x180129630  mov     ebx, 80004003h
0x180129635  mov     r9d, ebx; char *
0x180129638  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x18012963f  lea     edx, [rsi+2Eh]; void *
0x180129642  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180129647  mov     eax, ebx
0x180129649  jmp     loc_180129951
0x18012964e  xor     edx, edx; length
0x180129650  mov     rcx, rbx; string
0x180129653  call    cs:__imp_WindowsGetStringRawBuffer
0x18012965a  nop     dword ptr [rax+rax+00h]
0x18012965f  mov     rdx, rax
0x180129662  lea     rcx, [rsp+0B8h+var_78]
0x180129667  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18012966c  nop
0x18012966d  lea     rcx, [rsp+0B8h+var_78]
0x180129672  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x180129677  test    al, al
0x180129679  jnz     loc_180129819
0x18012967f  mov     [rsp+0B8h+var_88], 0
0x180129688  xor     edx, edx
0x18012968a  lea     rcx, [rsp+0B8h+var_88]
0x18012968f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180129694  lea     rdx, [rsp+0B8h+var_88]; unsigned __int16 **
0x180129699  lea     rcx, aEspAutomatical; "ESP.AutomaticallyExportLogsToRemovableD"...
0x1801296a0  call    ?AutoPilotGetSetting@AutopilotUtils@AutoPilot@Service@EnterpriseDeviceManagement@@SAJPEBGPEAPEAG@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUtils::AutoPilotGetSetting(ushort const *,ushort * *)
0x1801296a5  mov     ebx, eax
0x1801296a7  test    eax, eax
0x1801296a9  jns     short loc_1801296E4
0x1801296ab  mov     rcx, [rsp+0B8h]; this
0x1801296b3  mov     r9d, eax; char *
0x1801296b6  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801296bd  mov     edx, 3Dh ; '='; void *
0x1801296c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801296c7  nop
0x1801296c8  lea     rcx, [rsp+0B8h+var_88]
0x1801296cd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801296d2  nop
0x1801296d3  lea     rcx, [rsp+0B8h+var_78]
0x1801296d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801296dd  mov     eax, ebx
0x1801296df  jmp     loc_180129951
0x1801296e4  mov     rdx, [rsp+0B8h+var_88]
0x1801296e9  lea     rcx, [rsp+0B8h+var_58]
0x1801296ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801296f3  lea     rcx, [rsp+0B8h+var_78]
0x1801296f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801296fd  mov     rbx, rax
0x180129700  lea     rcx, [rsp+0B8h+var_58]
0x180129705  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012970a  mov     rcx, rax
0x18012970d  mov     rdx, rbx
0x180129710  call    cs:__imp__o__wcsicmp
0x180129717  nop     dword ptr [rax+rax+00h]
0x18012971c  test    eax, eax
0x18012971e  jz      short loc_180129768
0x180129720  mov     rcx, [rsp+0B8h]; this
0x180129728  mov     ebx, 8103C010h
0x18012972d  mov     r9d, ebx; char *
0x180129730  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x180129737  mov     edx, 42h ; 'B'; void *
0x18012973c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180129741  lea     rcx, [rsp+0B8h+var_58]
0x180129746  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012974b  nop
0x18012974c  lea     rcx, [rsp+0B8h+var_88]
0x180129751  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180129756  nop
0x180129757  lea     rcx, [rsp+0B8h+var_78]
0x18012975c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180129761  mov     eax, ebx
0x180129763  jmp     loc_180129951
0x180129768  lea     rcx, [rsp+0B8h+var_78]
0x18012976d  call    ?CreateFolderHierarchy@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchy(std::wstring const &)
0x180129772  mov     ebx, eax
0x180129774  test    eax, eax
0x180129776  js      short loc_1801297B1
0x180129778  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18012977f  jz      short loc_18012979A
0x180129781  lea     rcx, [rsp+0B8h+var_78]
0x180129786  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18012978b  mov     r8, rax
0x18012978e  lea     rdx, AutopilotExportLinkCreatedFolder
0x180129795  call    McTemplateU0z_EventWriteTransfer
0x18012979a  lea     rcx, [rsp+0B8h+var_58]
0x18012979f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801297a4  nop
0x1801297a5  lea     rcx, [rsp+0B8h+var_88]
0x1801297aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801297af  jmp     short loc_180129819
0x1801297b1  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x1801297b8  jz      short loc_1801297D6
0x1801297ba  lea     rcx, [rsp+0B8h+var_78]
0x1801297bf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801297c4  mov     r9, rax
0x1801297c7  mov     r8d, ebx
0x1801297ca  lea     rdx, AutopilotExportLinkFailedToCreateFolder
0x1801297d1  call    McTemplateU0dz_EventWriteTransfer
0x1801297d6  mov     rcx, [rsp+0B8h]; this
0x1801297de  mov     r9d, ebx; char *
0x1801297e1  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801297e8  mov     edx, 4Ch ; 'L'; void *
0x1801297ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801297f2  lea     rcx, [rsp+0B8h+var_58]
0x1801297f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801297fc  nop
0x1801297fd  lea     rcx, [rsp+0B8h+var_88]
0x180129802  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180129807  nop
0x180129808  lea     rcx, [rsp+0B8h+var_78]
0x18012980d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180129812  mov     eax, ebx
0x180129814  jmp     loc_180129951
0x180129819  mov     [rsp+0B8h+var_88], rdi
0x18012981e  test    rdi, rdi
0x180129821  jz      short loc_180129833
0x180129823  mov     rax, [rdi]
0x180129826  mov     rcx, rdi
0x180129829  mov     rax, [rax+8]
0x18012982d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129832  nop
0x180129833  mov     qword ptr [rsp+0B8h+var_80], 0
0x18012983c  lea     rax, [rsp+0B8h+var_80]
0x180129841  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180129846  lea     rcx, [rsp+0B8h+var_98]
0x18012984b  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180129850  mov     rdx, rax
0x180129853  mov     rcx, rdi
0x180129856  call    ??$AsWeak@UIDeviceProvisioningStatusCallback@Core@Autopilot@ModernDeployment@@@WRL@Microsoft@@YAJPEAUIDeviceProvisioningStatusCallback@Core@Autopilot@ModernDeployment@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<ModernDeployment::Autopilot::Core::IDeviceProvisioningStatusCallback>(ModernDeployment::Autopilot::Core::IDeviceProvisioningStatusCallback *,Microsoft::WRL::WeakRef *)
0x18012985b  mov     ebx, eax
0x18012985d  test    eax, eax
0x18012985f  jns     short loc_1801298BA
0x180129861  mov     rcx, [rsp+0B8h]; this
0x180129869  mov     r9d, eax; char *
0x18012986c  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x180129873  mov     edx, 52h ; 'R'; void *
0x180129878  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012987d  nop
0x18012987e  mov     rcx, qword ptr [rsp+0B8h+var_80]
0x180129883  test    rcx, rcx
0x180129886  jz      short loc_18012989E
0x180129888  mov     qword ptr [rsp+0B8h+var_80], 0
0x180129891  mov     rax, [rcx]
0x180129894  mov     rax, [rax+10h]
0x180129898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012989d  nop
0x18012989e  lea     rcx, [rsp+0B8h+var_88]
0x1801298a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801298a8  nop
0x1801298a9  lea     rcx, [rsp+0B8h+var_78]
0x1801298ae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801298b3  mov     eax, ebx
0x1801298b5  jmp     loc_180129951
0x1801298ba  mov     rax, qword ptr [rsp+0B8h+var_80]
0x1801298bf  mov     [rsp+0B8h+var_58], rax
0x1801298c4  mov     qword ptr [rsp+0B8h+var_80], 0
0x1801298cd  lea     rdx, [rsp+0B8h+var_78]
0x1801298d2  lea     rcx, [rsp+0B8h+var_50]
0x1801298d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801298dc  mov     [rsp+0B8h+var_30], r14d
0x1801298e4  mov     [rsp+0B8h+var_98], 3
0x1801298ec  mov     qword ptr [rsp+0B8h+var_98+4], 80h
0x1801298f5  lea     r9, [rsp+0B8h+var_58]
0x1801298fa  mov     rdx, rsi
0x1801298fd  lea     rcx, [rsp+0B8h+var_98]
0x180129902  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CHSTRINGResult_HSTRING_____Windows__Internal__ComTaskPoolHandler__ModernDeployment__Autopilot__Core__DeviceLinkUtilities__ExportDeviceLinkInfoCsvAsync____3____lambda_1___
0x180129907  mov     ebx, eax
0x180129909  lea     rcx, [rsp+0B8h+var_58]
0x18012990e  call    _ModernDeployment__Autopilot__Core__DeviceLinkManager__RequestDiscoveryUrlAsync____3____lambda_1_____lambda_1_
0x180129913  nop
0x180129914  mov     rcx, qword ptr [rsp+0B8h+var_80]
0x180129919  test    rcx, rcx
0x18012991c  jz      short loc_180129934
0x18012991e  mov     qword ptr [rsp+0B8h+var_80], 0
0x180129927  mov     rdx, [rcx]
0x18012992a  mov     rax, [rdx+10h]
0x18012992e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129933  nop
0x180129934  lea     rcx, [rsp+0B8h+var_88]
0x180129939  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012993e  nop
0x18012993f  lea     rcx, [rsp+0B8h+var_78]
0x180129944  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180129949  mov     eax, ebx
0x18012994b  jmp     short loc_180129951
0x18012994d  mov     eax, dword ptr [rsp+0B8h+var_88]
0x180129951  mov     rcx, [rsp+0B8h+var_28]
0x180129959  xor     rcx, rsp; StackCookie
0x18012995c  call    __security_check_cookie
0x180129961  mov     rbx, [rsp+0B8h+arg_0]
0x180129969  add     rsp, 0A0h
0x180129970  pop     r14
0x180129972  pop     rdi
0x180129973  pop     rsi
0x180129974  retn
```
