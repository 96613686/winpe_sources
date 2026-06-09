# ModernDeployment::Autopilot::Core::DeviceLinkEndpointResolver::CreateDiscoveryRequestSoapMessage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1801ce320`
- end: `0x1801ce9c3`
- name: `?CreateDiscoveryRequestSoapMessage@DeviceLinkEndpointResolver@Core@Autopilot@ModernDeployment@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV56@@Z`
- size: `1699`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801ce9cc`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067a54`
- `0x180067ffc`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x180089ff4`
- `0x18008c244`
- `0x18009542c`
- `0x1800a1fe4`
- `0x18019f59c`
- `0x18019f6b4`
- `0x1801b0134`
- `0x1801ce320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ce3e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ce469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ce3e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ce469`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1801ce3dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1801ce3dd`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1801ce539`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1801ce539`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1801ce45f`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1801ce45f`

## string_xrefs

- `0x1801ce394`: `CreateDiscoveryRequestSoapMessage`
- `0x1801ce372`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce40f`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce491`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce5a0`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce60f`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce685`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce6e2`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce742`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce79e`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce81a`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce8c4`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce95d`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801ce89d`: `<?xml version="1.0"?>\n<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing" xmlns:s="http://www.w3.org/2003/05/soap-envelope">\n  <s:Header>\n    <a:Action s:mustUnderstand="1">http://schemas.microsoft.com/windows/management/2012/01/enrollment/IDiscoveryService/Discover</a:Action>\n    <a:MessageID>urn:uuid:4e8ea50b-8202-40c3-b0d1-cc1cdced4e62</a:MessageID>\n    <a:ReplyTo>\n      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>\n    </a:ReplyTo>\n    <a:To s:mustUnder`
- `0x1801ce39b`: `DeviceLinkEndpointResolver`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceLinkEndpointResolver::CreateDiscoveryRequestSoapMessage(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  signed int v8; // eax
  unsigned int v9; // ebx
  signed int LastError; // eax
  unsigned int v11; // ebx
  _WORD *v12; // r10
  DWORD v13; // r8d
  int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // r14
  unsigned __int16 *v25; // rbx
  __int64 v26; // rax
  int v27; // eax
  unsigned int v28; // edi
  int pdwReturnedProductType; // [rsp+20h] [rbp-468h]
  int pdwReturnedProductTypea; // [rsp+20h] [rbp-468h]
  int pdwReturnedProductTypeb; // [rsp+20h] [rbp-468h]
  char v32[8]; // [rsp+40h] [rbp-448h] BYREF
  unsigned __int16 *v33; // [rsp+48h] [rbp-440h] BYREF
  DWORD v34; // [rsp+50h] [rbp-438h] BYREF
  int v35; // [rsp+54h] [rbp-434h] BYREF
  __int128 v36; // [rsp+58h] [rbp-430h] BYREF
  __m128i si128; // [rsp+68h] [rbp-420h]
  _BYTE v38[16]; // [rsp+78h] [rbp-410h] BYREF
  __int64 v39; // [rsp+88h] [rbp-400h]
  unsigned __int64 v40; // [rsp+98h] [rbp-3F0h] BYREF
  _BYTE v41[80]; // [rsp+A0h] [rbp-3E8h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+F0h] [rbp-398h] BYREF
  unsigned __int16 v43; // [rsp+204h] [rbp-284h]
  unsigned __int16 v44; // [rsp+206h] [rbp-282h]
  _BYTE v45[6]; // [rsp+23Ah] [rbp-24Eh] BYREF
  unsigned __int16 v46[264]; // [rsp+240h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    v35 = 0;
    Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(
      (Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41,
      L"DeviceLinkEndpointResolver",
      L"CreateDiscoveryRequestSoapMessage",
      &v35);
    v34 = 0;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( GetVersionExW(&VersionInformation) )
    {
      if ( GetProductInfo(VersionInformation.dwMajorVersion, VersionInformation.dwMinorVersion, v43, v44, &v34) )
      {
        v12 = v45;
        v13 = v34;
        do
        {
          *--v12 = v13 % 0xA + 48;
          v13 /= 0xAu;
        }
        while ( v13 );
        std::wstring::wstring(v38, v12, v45, v32);
        memset_0(v46, 0, 0x208u);
        v40 = 0;
        RtlGetDeviceFamilyInfoEnum(&v40, 0, 0);
        pdwReturnedProductTypeb = WORD2(v40);
        v14 = StringCchPrintfW(v46, 0x104u, L"%llu.%llu.%llu.%llu", HIWORD(v40));
        v16 = v14;
        v35 = v14;
        if ( v14 >= 0 )
        {
          v36 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v36) = 0;
          v17 = Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddPortToUrl(a3, v15, &v36);
          v18 = v17;
          v35 = v17;
          if ( v17 >= 0 )
          {
            v19 = -1;
            do
              ++v19;
            while ( v46[v19] );
            v20 = v19 + 1108;
            if ( v19 < 0xFFFFFFFFFFFFFBACuLL )
            {
              v21 = v20 + si128.m128i_i64[0];
              if ( v20 + si128.m128i_i64[0] >= v20 )
              {
                v22 = v21 + v39;
                if ( v21 + v39 >= v21 )
                {
                  v23 = v22 + *(_QWORD *)(a2 + 16);
                  if ( v23 >= v22 )
                  {
                    v24 = v23 + 1;
                    if ( v23 + 1 < v23 )
                    {
                      v35 = -2147024362;
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x80,
                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkend"
                                      "pointresolver.cpp",
                        (const char *)0x80070216LL,
                        pdwReturnedProductTypeb);
                      std::wstring::_Tidy_deallocate(&v36);
                      std::wstring::_Tidy_deallocate(v38);
                      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
                      return 2147942934LL;
                    }
                    else
                    {
                      v35 = 0;
                      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                        &v33,
                        0,
                        v23 + 1);
                      v25 = v33;
                      if ( v33 )
                      {
                        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
                        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
                        v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v36);
                        v27 = StringCchPrintfW(
                                v25,
                                v24,
                                L"<?xml version=\"1.0\"?>\n"
                                 "<s:Envelope xmlns:a=\"http://www.w3.org/2005/08/addressing\" xmlns:s=\"http://www.w3.or"
                                 "g/2003/05/soap-envelope\">\n"
                                 "  <s:Header>\n"
                                 "    <a:Action s:mustUnderstand=\"1\">http://schemas.microsoft.com/windows/management/20"
                                 "12/01/enrollment/IDiscoveryService/Discover</a:Action>\n"
                                 "    <a:MessageID>urn:uuid:4e8ea50b-8202-40c3-b0d1-cc1cdced4e62</a:MessageID>\n"
                                 "    <a:ReplyTo>\n"
                                 "      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>\n"
                                 "    </a:ReplyTo>\n"
                                 "    <a:To s:mustUnderstand=\"1\">%ws</a:To>\n"
                                 "  </s:Header>\n"
                                 "  <s:Body>\n"
                                 "    <Discover xmlns=\"http://schemas.microsoft.com/windows/management/2012/01/enrollmen"
                                 "t\">\n"
                                 "      <request xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\">\n"
                                 "        <RequestVersion>8.0</RequestVersion>\n"
                                 "        <DeviceType>CIMClient_Windows</DeviceType>\n"
                                 "        <ApplicationVersion>%ws</ApplicationVersion>\n"
                                 "        <OSEdition>%ws</OSEdition>\n"
                                 "        <TenantID>%ws</TenantID>\n"
                                 "        <AuthPolicies>\n"
                                 "          <AuthPolicy>OnPremise</AuthPolicy>\n"
                                 "          <AuthPolicy>Federated</AuthPolicy>\n"
                                 "        </AuthPolicies>\n"
                                 "      </request>\n"
                                 "    </Discover>\n"
                                 "  </s:Body>\n"
                                 "</s:Envelope>",
                                v26);
                        v28 = v27;
                        v35 = v27;
                        if ( v27 >= 0 )
                        {
                          std::wstring::assign(a4, v25);
                          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
                          std::wstring::_Tidy_deallocate(&v36);
                          std::wstring::_Tidy_deallocate(v38);
                          Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
                          return 0;
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x8D,
                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelin"
                                          "kendpointresolver.cpp",
                            (const char *)(unsigned int)v27,
                            (int)v46);
                          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
                          std::wstring::_Tidy_deallocate(&v36);
                          std::wstring::_Tidy_deallocate(v38);
                          Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
                          return v28;
                        }
                      }
                      else
                      {
                        v35 = -2147024882;
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x83,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinke"
                                        "ndpointresolver.cpp",
                          (const char *)0x8007000ELL,
                          pdwReturnedProductTypeb);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
                        std::wstring::_Tidy_deallocate(&v36);
                        std::wstring::_Tidy_deallocate(v38);
                        Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
                        return 2147942414LL;
                      }
                    }
                  }
                  else
                  {
                    v35 = -2147024362;
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x7F,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkendpointresolver.cpp",
                      (const char *)0x80070216LL,
                      pdwReturnedProductTypeb);
                    std::wstring::_Tidy_deallocate(&v36);
                    std::wstring::_Tidy_deallocate(v38);
                    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
                    return 2147942934LL;
                  }
                }
                else
                {
                  v35 = -2147024362;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x7E,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkendpointresolver.cpp",
                    (const char *)0x80070216LL,
                    pdwReturnedProductTypeb);
                  std::wstring::_Tidy_deallocate(&v36);
                  std::wstring::_Tidy_deallocate(v38);
                  Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
                  return 2147942934LL;
                }
              }
              else
              {
                v35 = -2147024362;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x7D,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkendpointresolver.cpp",
                  (const char *)0x80070216LL,
                  pdwReturnedProductTypeb);
                std::wstring::_Tidy_deallocate(&v36);
                std::wstring::_Tidy_deallocate(v38);
                Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
                return 2147942934LL;
              }
            }
            else
            {
              v35 = -2147024362;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x7C,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkendpointresolver.cpp",
                (const char *)0x80070216LL,
                pdwReturnedProductTypeb);
              std::wstring::_Tidy_deallocate(&v36);
              std::wstring::_Tidy_deallocate(v38);
              Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
              return 2147942934LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x78,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkendpointresolver.cpp",
              (const char *)(unsigned int)v17,
              pdwReturnedProductTypeb);
            std::wstring::_Tidy_deallocate(&v36);
            std::wstring::_Tidy_deallocate(v38);
            Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
            return v18;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x74,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkendpointresolver.cpp",
            (const char *)(unsigned int)v14,
            pdwReturnedProductTypeb);
          std::wstring::_Tidy_deallocate(v38);
          Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
          return v16;
        }
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        v35 = v11;
        if ( (v11 & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x63,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkendpointresolver.cpp",
            (const char *)v11,
            pdwReturnedProductTypea);
        Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
        return v11;
      }
    }
    else
    {
      v8 = GetLastError();
      v9 = v8;
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      v35 = v9;
      if ( (v9 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkendpointresolver.cpp",
          (const char *)v9,
          pdwReturnedProductType);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v41);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\devicelink\\devicelinkendpointresolver.cpp",
      (const char *)0x80004001LL,
      pdwReturnedProductType);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1801ce320  mov     [rsp+arg_0], rbx
0x1801ce325  push    rsi
0x1801ce326  push    rdi
0x1801ce327  push    r12
0x1801ce329  push    r14
0x1801ce32b  push    r15
0x1801ce32d  sub     rsp, 460h
0x1801ce334  mov     rax, cs:__security_cookie
0x1801ce33b  xor     rax, rsp
0x1801ce33e  mov     [rsp+488h+var_38], rax
0x1801ce346  mov     r15, r9
0x1801ce349  mov     rsi, r8
0x1801ce34c  mov     rdi, rdx
0x1801ce34f  xor     r12d, r12d
0x1801ce352  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801ce359  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801ce35e  test    al, al
0x1801ce360  jnz     short loc_1801CE38A
0x1801ce362  mov     rcx, [rsp+488h]; this
0x1801ce36a  mov     ebx, 80004001h
0x1801ce36f  mov     r9d, ebx; char *
0x1801ce372  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ce379  lea     edx, [r12+52h]; void *
0x1801ce37e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ce383  mov     eax, ebx
0x1801ce385  jmp     loc_1801CE99A
0x1801ce38a  mov     [rsp+488h+var_434], r12d
0x1801ce38f  lea     r9, [rsp+488h+var_434]; int *
0x1801ce394  lea     r8, aCreatediscover; "CreateDiscoveryRequestSoapMessage"
0x1801ce39b  lea     rdx, aDevicelinkendp; "DeviceLinkEndpointResolver"
0x1801ce3a2  lea     rcx, [rsp+488h+var_3E8]; this
0x1801ce3aa  call    ??0ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@PEBG0AEAJ@Z; Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(ushort const *,ushort const *,long &)
0x1801ce3af  nop
0x1801ce3b0  mov     [rsp+488h+var_438], r12d
0x1801ce3b5  xor     edx, edx; Val
0x1801ce3b7  mov     r8d, 118h; Size
0x1801ce3bd  lea     rcx, [rsp+488h+VersionInformation.dwMajorVersion]; void *
0x1801ce3c5  call    memset_0
0x1801ce3ca  mov     [rsp+488h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1801ce3d5  lea     rcx, [rsp+488h+VersionInformation]; lpVersionInformation
0x1801ce3dd  call    cs:__imp_GetVersionExW
0x1801ce3e3  test    eax, eax
0x1801ce3e5  jnz     short loc_1801CE435
0x1801ce3e7  call    cs:__imp_GetLastError
0x1801ce3ed  mov     ebx, eax
0x1801ce3ef  test    eax, eax
0x1801ce3f1  jle     short loc_1801CE3FC
0x1801ce3f3  movzx   ebx, ax
0x1801ce3f6  or      ebx, 80070000h
0x1801ce3fc  mov     [rsp+488h+var_434], ebx
0x1801ce400  test    ebx, ebx
0x1801ce402  jns     short loc_1801CE421
0x1801ce404  mov     rcx, [rsp+488h]; this
0x1801ce40c  mov     r9d, ebx; char *
0x1801ce40f  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ce416  mov     edx, 5Eh ; '^'; void *
0x1801ce41b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ce420  nop
0x1801ce421  lea     rcx, [rsp+488h+var_3E8]; this
0x1801ce429  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801ce42e  mov     eax, ebx
0x1801ce430  jmp     loc_1801CE99A
0x1801ce435  movzx   r9d, [rsp+488h+var_282]; dwSpMinorVersion
0x1801ce43e  movzx   r8d, [rsp+488h+var_284]; dwSpMajorVersion
0x1801ce447  lea     rax, [rsp+488h+var_438]
0x1801ce44c  mov     [rsp+488h+pdwReturnedProductType], rax; int
0x1801ce451  mov     edx, [rsp+488h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x1801ce458  mov     ecx, [rsp+488h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x1801ce45f  call    cs:__imp_GetProductInfo
0x1801ce465  test    eax, eax
0x1801ce467  jnz     short loc_1801CE4B7
0x1801ce469  call    cs:__imp_GetLastError
0x1801ce46f  mov     ebx, eax
0x1801ce471  test    eax, eax
0x1801ce473  jle     short loc_1801CE47E
0x1801ce475  movzx   ebx, ax
0x1801ce478  or      ebx, 80070000h
0x1801ce47e  mov     [rsp+488h+var_434], ebx
0x1801ce482  test    ebx, ebx
0x1801ce484  jns     short loc_1801CE4A3
0x1801ce486  mov     rcx, [rsp+488h]; this
0x1801ce48e  mov     r9d, ebx; char *
0x1801ce491  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ce498  mov     edx, 63h ; 'c'; void *
0x1801ce49d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ce4a2  nop
0x1801ce4a3  lea     rcx, [rsp+488h+var_3E8]; this
0x1801ce4ab  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801ce4b0  mov     eax, ebx
0x1801ce4b2  jmp     loc_1801CE99A
0x1801ce4b7  lea     r10, [rsp+488h+var_24E]
0x1801ce4bf  mov     r8d, [rsp+488h+var_438]
0x1801ce4c4  sub     r10, 2
0x1801ce4c8  mov     eax, 0CCCCCCCDh
0x1801ce4cd  mul     r8d
0x1801ce4d0  shr     edx, 3
0x1801ce4d3  movzx   eax, dx
0x1801ce4d6  shl     ax, 2
0x1801ce4da  lea     ecx, [rax+rdx]
0x1801ce4dd  add     cx, cx
0x1801ce4e0  sub     r8w, cx
0x1801ce4e4  add     r8w, 30h ; '0'
0x1801ce4e9  mov     [r10], r8w
0x1801ce4ed  mov     r8d, edx
0x1801ce4f0  test    edx, edx
0x1801ce4f2  jnz     short loc_1801CE4C4
0x1801ce4f4  lea     r9, [rsp+488h+var_448]
0x1801ce4f9  lea     r8, [rsp+488h+var_24E]
0x1801ce501  mov     rdx, r10
0x1801ce504  lea     rcx, [rsp+488h+var_410]
0x1801ce509  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1801ce50e  nop
0x1801ce50f  xor     edx, edx; Val
0x1801ce511  mov     r8d, 208h; Size
0x1801ce517  lea     rcx, [rsp+488h+var_248]; void *
0x1801ce51f  call    memset_0
0x1801ce524  mov     [rsp+488h+var_3F0], r12
0x1801ce52c  xor     r8d, r8d
0x1801ce52f  xor     edx, edx
0x1801ce531  lea     rcx, [rsp+488h+var_3F0]
0x1801ce539  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1801ce53f  mov     r9, [rsp+488h+var_3F0]
0x1801ce547  movzx   r8d, r9w
0x1801ce54b  mov     rax, r9
0x1801ce54e  shr     rax, 10h
0x1801ce552  movzx   edx, ax
0x1801ce555  mov     rax, r9
0x1801ce558  shr     rax, 20h
0x1801ce55c  movzx   ecx, ax
0x1801ce55f  shr     r9, 30h
0x1801ce563  mov     [rsp+488h+var_458], r8
0x1801ce568  mov     [rsp+488h+var_460], rdx
0x1801ce56d  mov     [rsp+488h+pdwReturnedProductType], rcx; int
0x1801ce572  lea     r8, aLluLluLluLlu; "%llu.%llu.%llu.%llu"
0x1801ce579  mov     edx, 104h; unsigned __int64
0x1801ce57e  lea     rcx, [rsp+488h+var_248]; unsigned __int16 *
0x1801ce586  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801ce58b  mov     ebx, eax
0x1801ce58d  mov     [rsp+488h+var_434], eax
0x1801ce591  test    eax, eax
0x1801ce593  jns     short loc_1801CE5D1
0x1801ce595  mov     rcx, [rsp+488h]; this
0x1801ce59d  mov     r9d, eax; char *
0x1801ce5a0  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ce5a7  mov     edx, 74h ; 't'; void *
0x1801ce5ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ce5b1  nop
0x1801ce5b2  lea     rcx, [rsp+488h+var_410]
0x1801ce5b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce5bc  nop
0x1801ce5bd  lea     rcx, [rsp+488h+var_3E8]; this
0x1801ce5c5  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801ce5ca  mov     eax, ebx
0x1801ce5cc  jmp     loc_1801CE99A
0x1801ce5d1  xorps   xmm0, xmm0
0x1801ce5d4  movups  [rsp+488h+var_430], xmm0
0x1801ce5d9  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801ce5e1  movdqu  [rsp+488h+var_420], xmm1
0x1801ce5e7  mov     word ptr [rsp+488h+var_430], r12w
0x1801ce5ed  lea     r8, [rsp+488h+var_430]
0x1801ce5f2  mov     rcx, rsi
0x1801ce5f5  call    ?AddPortToUrl@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAV56@@Z; Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddPortToUrl(std::wstring const &,ulong,std::wstring &)
0x1801ce5fa  mov     ebx, eax
0x1801ce5fc  mov     [rsp+488h+var_434], eax
0x1801ce600  test    eax, eax
0x1801ce602  jns     short loc_1801CE64B
0x1801ce604  mov     rcx, [rsp+488h]; this
0x1801ce60c  mov     r9d, eax; char *
0x1801ce60f  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ce616  mov     edx, 78h ; 'x'; void *
0x1801ce61b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ce620  nop
0x1801ce621  lea     rcx, [rsp+488h+var_430]
0x1801ce626  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce62b  nop
0x1801ce62c  lea     rcx, [rsp+488h+var_410]
0x1801ce631  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce636  nop
0x1801ce637  lea     rcx, [rsp+488h+var_3E8]; this
0x1801ce63f  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801ce644  mov     eax, ebx
0x1801ce646  jmp     loc_1801CE99A
0x1801ce64b  lea     rcx, [rsp+488h+var_248]
0x1801ce653  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ce657  inc     rax
0x1801ce65a  cmp     [rcx+rax*2], r12w
0x1801ce65f  jnz     short loc_1801CE657
0x1801ce661  lea     rdx, [rax+454h]
0x1801ce668  cmp     rdx, 454h
0x1801ce66f  jnb     short loc_1801CE6C1
0x1801ce671  mov     ebx, 80070216h
0x1801ce676  mov     [rsp+488h+var_434], ebx
0x1801ce67a  mov     rcx, [rsp+488h]; this
0x1801ce682  mov     r9d, ebx; char *
0x1801ce685  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ce68c  mov     edx, 7Ch ; '|'; void *
0x1801ce691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ce696  nop
0x1801ce697  lea     rcx, [rsp+488h+var_430]
0x1801ce69c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce6a1  nop
0x1801ce6a2  lea     rcx, [rsp+488h+var_410]
0x1801ce6a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce6ac  nop
0x1801ce6ad  lea     rcx, [rsp+488h+var_3E8]; this
0x1801ce6b5  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801ce6ba  mov     eax, ebx
0x1801ce6bc  jmp     loc_1801CE99A
0x1801ce6c1  mov     rcx, qword ptr [rsp+488h+var_420]
0x1801ce6c6  add     rcx, rdx
0x1801ce6c9  cmp     rcx, rdx
0x1801ce6cc  jnb     short loc_1801CE71E
0x1801ce6ce  mov     ebx, 80070216h
0x1801ce6d3  mov     [rsp+488h+var_434], ebx
0x1801ce6d7  mov     rcx, [rsp+488h]; this
0x1801ce6df  mov     r9d, ebx; char *
0x1801ce6e2  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ce6e9  mov     edx, 7Dh ; '}'; void *
0x1801ce6ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ce6f3  nop
0x1801ce6f4  lea     rcx, [rsp+488h+var_430]
0x1801ce6f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce6fe  nop
0x1801ce6ff  lea     rcx, [rsp+488h+var_410]
0x1801ce704  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce709  nop
0x1801ce70a  lea     rcx, [rsp+488h+var_3E8]; this
0x1801ce712  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801ce717  mov     eax, ebx
0x1801ce719  jmp     loc_1801CE99A
0x1801ce71e  mov     rdx, [rsp+488h+var_400]
0x1801ce726  add     rdx, rcx
0x1801ce729  cmp     rdx, rcx
0x1801ce72c  jnb     short loc_1801CE77E
0x1801ce72e  mov     ebx, 80070216h
0x1801ce733  mov     [rsp+488h+var_434], ebx
0x1801ce737  mov     rcx, [rsp+488h]; this
0x1801ce73f  mov     r9d, ebx; char *
0x1801ce742  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ce749  mov     edx, 7Eh ; '~'; void *
0x1801ce74e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ce753  nop
0x1801ce754  lea     rcx, [rsp+488h+var_430]
0x1801ce759  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce75e  nop
0x1801ce75f  lea     rcx, [rsp+488h+var_410]
0x1801ce764  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce769  nop
0x1801ce76a  lea     rcx, [rsp+488h+var_3E8]; this
0x1801ce772  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801ce777  mov     eax, ebx
0x1801ce779  jmp     loc_1801CE99A
0x1801ce77e  mov     rcx, [rdi+10h]
0x1801ce782  add     rcx, rdx
0x1801ce785  cmp     rcx, rdx
0x1801ce788  jnb     short loc_1801CE7DA
0x1801ce78a  mov     ebx, 80070216h
0x1801ce78f  mov     [rsp+488h+var_434], ebx
0x1801ce793  mov     rcx, [rsp+488h]; this
0x1801ce79b  mov     r9d, ebx; char *
0x1801ce79e  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ce7a5  mov     edx, 7Fh; void *
0x1801ce7aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ce7af  nop
0x1801ce7b0  lea     rcx, [rsp+488h+var_430]
0x1801ce7b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce7ba  nop
0x1801ce7bb  lea     rcx, [rsp+488h+var_410]
0x1801ce7c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce7c5  nop
0x1801ce7c6  lea     rcx, [rsp+488h+var_3E8]; this
0x1801ce7ce  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801ce7d3  mov     eax, ebx
0x1801ce7d5  jmp     loc_1801CE99A
0x1801ce7da  lea     r14, [rcx+1]
0x1801ce7de  cmp     r14, rcx
0x1801ce7e1  jb      loc_1801CE949
0x1801ce7e7  mov     [rsp+488h+var_434], r12d
0x1801ce7ec  mov     r8, r14
0x1801ce7ef  xor     edx, edx
0x1801ce7f1  lea     rcx, [rsp+488h+var_440]
0x1801ce7f6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801ce7fb  nop
0x1801ce7fc  mov     rbx, [rsp+488h+var_440]
0x1801ce801  test    rbx, rbx
0x1801ce804  jnz     short loc_1801CE861
0x1801ce806  mov     ebx, 8007000Eh
0x1801ce80b  mov     [rsp+488h+var_434], ebx
0x1801ce80f  mov     rcx, [rsp+488h]; this
0x1801ce817  mov     r9d, ebx; char *
0x1801ce81a  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ce821  mov     edx, 83h; void *
0x1801ce826  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ce82b  nop
0x1801ce82c  lea     rcx, [rsp+488h+var_440]
0x1801ce831  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801ce836  nop
0x1801ce837  lea     rcx, [rsp+488h+var_430]
0x1801ce83c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ce841  nop
  ... truncated ...
```
