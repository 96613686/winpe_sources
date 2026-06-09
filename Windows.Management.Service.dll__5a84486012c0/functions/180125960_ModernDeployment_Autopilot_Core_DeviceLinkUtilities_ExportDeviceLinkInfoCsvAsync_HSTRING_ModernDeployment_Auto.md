# ModernDeployment::Autopilot::Core::DeviceLinkUtilities::ExportDeviceLinkInfoCsvAsync(HSTRING__ *,ModernDeployment::Autopilot::Core::DeviceLinkFormatFlags,Windows::Foundation::IAsyncOperation<HSTRING__ *> * *)

- ea: `0x180125960`
- end: `0x180125d3a`
- name: `?ExportDeviceLinkInfoCsvAsync@DeviceLinkUtilities@Core@Autopilot@ModernDeployment@@UEAAJPEAUHSTRING__@@W4DeviceLinkFormatFlags@234@PEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@Z`
- size: `986`
- prototype: `__int64 __fastcall(unsigned __int16 *, HSTRING, int, __int64)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x18008084c`
- `0x18008122c`
- `0x1800839bc`
- `0x18008982c`
- `0x180089ff4`
- `0x18008c588`
- `0x18008cfd4`
- `0x18008d270`
- `0x1800d9718`
- `0x1800da468`
- `0x180124bd0`
- `0x180124f70`
- `0x180125960`
- `0x180175f4c`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180125ada`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180125ada`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180125a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180125a23`

## string_xrefs

- `0x1801259ae`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x1801259db`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x180125a08`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x180125a80`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x180125af4`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x180125ba5`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`
- `0x180125c30`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x180125960  mov     [rsp+arg_0], rbx
0x180125965  push    rsi
0x180125966  push    rdi
0x180125967  push    r14
0x180125969  sub     rsp, 0A0h
0x180125970  mov     rax, cs:__security_cookie
0x180125977  xor     rax, rsp
0x18012597a  mov     [rsp+0B8h+var_28], rax
0x180125982  mov     rsi, r9
0x180125985  mov     r14d, r8d
0x180125988  mov     rbx, rdx
0x18012598b  mov     rdi, rcx
0x18012598e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180125995  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18012599a  test    al, al
0x18012599c  jnz     short loc_1801259C6
0x18012599e  mov     rcx, [rsp+0B8h]; this
0x1801259a6  mov     ebx, 80004001h
0x1801259ab  mov     r9d, ebx; char *
0x1801259ae  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801259b5  mov     edx, 2Bh ; '+'; void *
0x1801259ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801259bf  mov     eax, ebx
0x1801259c1  jmp     loc_180125D15
0x1801259c6  test    rbx, rbx
0x1801259c9  jnz     short loc_1801259F3
0x1801259cb  mov     rcx, [rsp+0B8h]; this
0x1801259d3  mov     ebx, 80070057h
0x1801259d8  mov     r9d, ebx; char *
0x1801259db  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801259e2  mov     edx, 2Dh ; '-'; void *
0x1801259e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801259ec  mov     eax, ebx
0x1801259ee  jmp     loc_180125D15
0x1801259f3  test    rsi, rsi
0x1801259f6  jnz     short loc_180125A1E
0x1801259f8  mov     rcx, [rsp+0B8h]; this
0x180125a00  mov     ebx, 80004003h
0x180125a05  mov     r9d, ebx; char *
0x180125a08  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x180125a0f  lea     edx, [rsi+2Eh]; void *
0x180125a12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125a17  mov     eax, ebx
0x180125a19  jmp     loc_180125D15
0x180125a1e  xor     edx, edx; length
0x180125a20  mov     rcx, rbx; string
0x180125a23  call    cs:__imp_WindowsGetStringRawBuffer
0x180125a29  mov     rdx, rax
0x180125a2c  lea     rcx, [rsp+0B8h+var_78]
0x180125a31  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180125a36  nop
0x180125a37  lea     rcx, [rsp+0B8h+var_78]
0x180125a3c  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x180125a41  test    al, al
0x180125a43  jnz     loc_180125BDD
0x180125a49  mov     [rsp+0B8h+var_88], 0
0x180125a52  xor     edx, edx
0x180125a54  lea     rcx, [rsp+0B8h+var_88]
0x180125a59  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180125a5e  lea     rdx, [rsp+0B8h+var_88]; unsigned __int16 **
0x180125a63  lea     rcx, aEspAutomatical; "ESP.AutomaticallyExportLogsToRemovableD"...
0x180125a6a  call    ?AutoPilotGetSetting@AutopilotUtils@AutoPilot@Service@EnterpriseDeviceManagement@@SAJPEBGPEAPEAG@Z; EnterpriseDeviceManagement::Service::AutoPilot::AutopilotUtils::AutoPilotGetSetting(ushort const *,ushort * *)
0x180125a6f  mov     ebx, eax
0x180125a71  test    eax, eax
0x180125a73  jns     short loc_180125AAE
0x180125a75  mov     rcx, [rsp+0B8h]; this
0x180125a7d  mov     r9d, eax; char *
0x180125a80  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x180125a87  mov     edx, 3Dh ; '='; void *
0x180125a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125a91  nop
0x180125a92  lea     rcx, [rsp+0B8h+var_88]
0x180125a97  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180125a9c  nop
0x180125a9d  lea     rcx, [rsp+0B8h+var_78]
0x180125aa2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180125aa7  mov     eax, ebx
0x180125aa9  jmp     loc_180125D15
0x180125aae  mov     rdx, [rsp+0B8h+var_88]
0x180125ab3  lea     rcx, [rsp+0B8h+var_58]
0x180125ab8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180125abd  lea     rcx, [rsp+0B8h+var_78]
0x180125ac2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180125ac7  mov     rbx, rax
0x180125aca  lea     rcx, [rsp+0B8h+var_58]
0x180125acf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180125ad4  mov     rcx, rax
0x180125ad7  mov     rdx, rbx
0x180125ada  call    cs:__imp__o__wcsicmp
0x180125ae0  test    eax, eax
0x180125ae2  jz      short loc_180125B2C
0x180125ae4  mov     rcx, [rsp+0B8h]; this
0x180125aec  mov     ebx, 8103C010h
0x180125af1  mov     r9d, ebx; char *
0x180125af4  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x180125afb  mov     edx, 42h ; 'B'; void *
0x180125b00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125b05  lea     rcx, [rsp+0B8h+var_58]
0x180125b0a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180125b0f  nop
0x180125b10  lea     rcx, [rsp+0B8h+var_88]
0x180125b15  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180125b1a  nop
0x180125b1b  lea     rcx, [rsp+0B8h+var_78]
0x180125b20  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180125b25  mov     eax, ebx
0x180125b27  jmp     loc_180125D15
0x180125b2c  lea     rcx, [rsp+0B8h+var_78]
0x180125b31  call    ?CreateFolderHierarchy@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchy(std::wstring const &)
0x180125b36  mov     ebx, eax
0x180125b38  test    eax, eax
0x180125b3a  js      short loc_180125B75
0x180125b3c  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180125b43  jz      short loc_180125B5E
0x180125b45  lea     rcx, [rsp+0B8h+var_78]
0x180125b4a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180125b4f  mov     r8, rax
0x180125b52  lea     rdx, AutopilotExportLinkCreatedFolder
0x180125b59  call    McTemplateU0z_EventWriteTransfer
0x180125b5e  lea     rcx, [rsp+0B8h+var_58]
0x180125b63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180125b68  nop
0x180125b69  lea     rcx, [rsp+0B8h+var_88]
0x180125b6e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180125b73  jmp     short loc_180125BDD
0x180125b75  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180125b7c  jz      short loc_180125B9A
0x180125b7e  lea     rcx, [rsp+0B8h+var_78]
0x180125b83  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180125b88  mov     r9, rax
0x180125b8b  mov     r8d, ebx
0x180125b8e  lea     rdx, AutopilotExportLinkFailedToCreateFolder
0x180125b95  call    McTemplateU0dz_EventWriteTransfer
0x180125b9a  mov     rcx, [rsp+0B8h]; this
0x180125ba2  mov     r9d, ebx; char *
0x180125ba5  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x180125bac  mov     edx, 4Ch ; 'L'; void *
0x180125bb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125bb6  lea     rcx, [rsp+0B8h+var_58]
0x180125bbb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180125bc0  nop
0x180125bc1  lea     rcx, [rsp+0B8h+var_88]
0x180125bc6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180125bcb  nop
0x180125bcc  lea     rcx, [rsp+0B8h+var_78]
0x180125bd1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180125bd6  mov     eax, ebx
0x180125bd8  jmp     loc_180125D15
0x180125bdd  mov     [rsp+0B8h+var_88], rdi
0x180125be2  test    rdi, rdi
0x180125be5  jz      short loc_180125BF7
0x180125be7  mov     rax, [rdi]
0x180125bea  mov     rcx, rdi
0x180125bed  mov     rax, [rax+8]
0x180125bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125bf6  nop
0x180125bf7  mov     qword ptr [rsp+0B8h+var_80], 0
0x180125c00  lea     rax, [rsp+0B8h+var_80]
0x180125c05  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180125c0a  lea     rcx, [rsp+0B8h+var_98]
0x180125c0f  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180125c14  mov     rdx, rax
0x180125c17  mov     rcx, rdi
0x180125c1a  call    ??$AsWeak@UIDeviceProvisioningStatusCallback@Core@Autopilot@ModernDeployment@@@WRL@Microsoft@@YAJPEAUIDeviceProvisioningStatusCallback@Core@Autopilot@ModernDeployment@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<ModernDeployment::Autopilot::Core::IDeviceProvisioningStatusCallback>(ModernDeployment::Autopilot::Core::IDeviceProvisioningStatusCallback *,Microsoft::WRL::WeakRef *)
0x180125c1f  mov     ebx, eax
0x180125c21  test    eax, eax
0x180125c23  jns     short loc_180125C7E
0x180125c25  mov     rcx, [rsp+0B8h]; this
0x180125c2d  mov     r9d, eax; char *
0x180125c30  lea     r8, aOnecoreuapAdmi_139; "onecoreuap\\admin\\moderndeployment\\au"...
0x180125c37  mov     edx, 52h ; 'R'; void *
0x180125c3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180125c41  nop
0x180125c42  mov     rcx, qword ptr [rsp+0B8h+var_80]
0x180125c47  test    rcx, rcx
0x180125c4a  jz      short loc_180125C62
0x180125c4c  mov     qword ptr [rsp+0B8h+var_80], 0
0x180125c55  mov     rax, [rcx]
0x180125c58  mov     rax, [rax+10h]
0x180125c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125c61  nop
0x180125c62  lea     rcx, [rsp+0B8h+var_88]
0x180125c67  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180125c6c  nop
0x180125c6d  lea     rcx, [rsp+0B8h+var_78]
0x180125c72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180125c77  mov     eax, ebx
0x180125c79  jmp     loc_180125D15
0x180125c7e  mov     rax, qword ptr [rsp+0B8h+var_80]
0x180125c83  mov     [rsp+0B8h+var_58], rax
0x180125c88  mov     qword ptr [rsp+0B8h+var_80], 0
0x180125c91  lea     rdx, [rsp+0B8h+var_78]
0x180125c96  lea     rcx, [rsp+0B8h+var_50]
0x180125c9b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180125ca0  mov     [rsp+0B8h+var_30], r14d
0x180125ca8  mov     [rsp+0B8h+var_98], 3
0x180125cb0  mov     qword ptr [rsp+0B8h+var_98+4], 80h
0x180125cb9  lea     r9, [rsp+0B8h+var_58]
0x180125cbe  mov     rdx, rsi
0x180125cc1  lea     rcx, [rsp+0B8h+var_98]
0x180125cc6  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CHSTRINGResult_HSTRING_____Windows__Internal__ComTaskPoolHandler__ModernDeployment__Autopilot__Core__DeviceLinkUtilities__ExportDeviceLinkInfoCsvAsync____3____lambda_1___
0x180125ccb  mov     ebx, eax
0x180125ccd  lea     rcx, [rsp+0B8h+var_58]
0x180125cd2  call    _ModernDeployment__Autopilot__Core__DeviceLinkManager__RequestDiscoveryUrlAsync____3____lambda_1_____lambda_1_
0x180125cd7  nop
0x180125cd8  mov     rcx, qword ptr [rsp+0B8h+var_80]
0x180125cdd  test    rcx, rcx
0x180125ce0  jz      short loc_180125CF8
0x180125ce2  mov     qword ptr [rsp+0B8h+var_80], 0
0x180125ceb  mov     rdx, [rcx]
0x180125cee  mov     rax, [rdx+10h]
0x180125cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180125cf7  nop
0x180125cf8  lea     rcx, [rsp+0B8h+var_88]
0x180125cfd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180125d02  nop
0x180125d03  lea     rcx, [rsp+0B8h+var_78]
0x180125d08  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180125d0d  mov     eax, ebx
0x180125d0f  jmp     short loc_180125D15
0x180125d11  mov     eax, dword ptr [rsp+0B8h+var_88]
0x180125d15  mov     rcx, [rsp+0B8h+var_28]
0x180125d1d  xor     rcx, rsp; StackCookie
0x180125d20  call    __security_check_cookie
0x180125d25  mov     rbx, [rsp+0B8h+arg_0]
0x180125d2d  add     rsp, 0A0h
0x180125d34  pop     r14
0x180125d36  pop     rdi
0x180125d37  pop     rsi
0x180125d38  retn
```
