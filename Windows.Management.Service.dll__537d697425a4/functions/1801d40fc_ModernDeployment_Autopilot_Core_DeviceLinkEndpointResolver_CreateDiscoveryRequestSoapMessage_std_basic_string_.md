# ModernDeployment::Autopilot::Core::DeviceLinkEndpointResolver::CreateDiscoveryRequestSoapMessage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1801d40fc`
- end: `0x1801d47bd`
- name: `?CreateDiscoveryRequestSoapMessage@DeviceLinkEndpointResolver@Core@Autopilot@ModernDeployment@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV56@@Z`
- size: `1729`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801d47c4`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067e54`
- `0x18006841c`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x18008aea8`
- `0x18008d290`
- `0x180096744`
- `0x1800a35f8`
- `0x1801a4a04`
- `0x1801a4b1c`
- `0x1801b5a60`
- `0x1801d40fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d41c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d4257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d41c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d4257`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1801d41b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1801d41b9`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1801d432d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1801d432d`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1801d4247`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1801d4247`

## string_xrefs

- `0x1801d4170`: `CreateDiscoveryRequestSoapMessage`
- `0x1801d414e`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d41f7`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d4285`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d439a`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d4409`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d447f`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d44dc`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d453c`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d4598`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d4614`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d46be`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d4757`: `onecoreuap\admin\moderndeployment\autopilot\service\devicelink\devicelinkendpointresolver.cpp`
- `0x1801d4697`: `<?xml version="1.0"?>\n<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing" xmlns:s="http://www.w3.org/2003/05/soap-envelope">\n  <s:Header>\n    <a:Action s:mustUnderstand="1">http://schemas.microsoft.com/windows/management/2012/01/enrollment/IDiscoveryService/Discover</a:Action>\n    <a:MessageID>urn:uuid:4e8ea50b-8202-40c3-b0d1-cc1cdced4e62</a:MessageID>\n    <a:ReplyTo>\n      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>\n    </a:ReplyTo>\n    <a:To s:mustUnder`
- `0x1801d4177`: `DeviceLinkEndpointResolver`

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
0x1801d40fc  mov     [rsp+arg_0], rbx
0x1801d4101  push    rsi
0x1801d4102  push    rdi
0x1801d4103  push    r12
0x1801d4105  push    r14
0x1801d4107  push    r15
0x1801d4109  sub     rsp, 460h
0x1801d4110  mov     rax, cs:__security_cookie
0x1801d4117  xor     rax, rsp
0x1801d411a  mov     [rsp+488h+var_38], rax
0x1801d4122  mov     r15, r9
0x1801d4125  mov     rsi, r8
0x1801d4128  mov     rdi, rdx
0x1801d412b  xor     r12d, r12d
0x1801d412e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801d4135  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801d413a  test    al, al
0x1801d413c  jnz     short loc_1801D4166
0x1801d413e  mov     rcx, [rsp+488h]; this
0x1801d4146  mov     ebx, 80004001h
0x1801d414b  mov     r9d, ebx; char *
0x1801d414e  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801d4155  lea     edx, [r12+52h]; void *
0x1801d415a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d415f  mov     eax, ebx
0x1801d4161  jmp     loc_1801D4794
0x1801d4166  mov     [rsp+488h+var_434], r12d
0x1801d416b  lea     r9, [rsp+488h+var_434]; int *
0x1801d4170  lea     r8, aCreatediscover; "CreateDiscoveryRequestSoapMessage"
0x1801d4177  lea     rdx, aDevicelinkendp; "DeviceLinkEndpointResolver"
0x1801d417e  lea     rcx, [rsp+488h+var_3E8]; this
0x1801d4186  call    ??0ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@PEBG0AEAJ@Z; Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(ushort const *,ushort const *,long &)
0x1801d418b  nop
0x1801d418c  mov     [rsp+488h+var_438], r12d
0x1801d4191  xor     edx, edx; Val
0x1801d4193  mov     r8d, 118h; Size
0x1801d4199  lea     rcx, [rsp+488h+VersionInformation.dwMajorVersion]; void *
0x1801d41a1  call    memset_0
0x1801d41a6  mov     [rsp+488h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1801d41b1  lea     rcx, [rsp+488h+VersionInformation]; lpVersionInformation
0x1801d41b9  call    cs:__imp_GetVersionExW
0x1801d41c0  nop     dword ptr [rax+rax+00h]
0x1801d41c5  test    eax, eax
0x1801d41c7  jnz     short loc_1801D421D
0x1801d41c9  call    cs:__imp_GetLastError
0x1801d41d0  nop     dword ptr [rax+rax+00h]
0x1801d41d5  mov     ebx, eax
0x1801d41d7  test    eax, eax
0x1801d41d9  jle     short loc_1801D41E4
0x1801d41db  movzx   ebx, ax
0x1801d41de  or      ebx, 80070000h
0x1801d41e4  mov     [rsp+488h+var_434], ebx
0x1801d41e8  test    ebx, ebx
0x1801d41ea  jns     short loc_1801D4209
0x1801d41ec  mov     rcx, [rsp+488h]; this
0x1801d41f4  mov     r9d, ebx; char *
0x1801d41f7  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801d41fe  mov     edx, 5Eh ; '^'; void *
0x1801d4203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d4208  nop
0x1801d4209  lea     rcx, [rsp+488h+var_3E8]; this
0x1801d4211  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801d4216  mov     eax, ebx
0x1801d4218  jmp     loc_1801D4794
0x1801d421d  movzx   r9d, [rsp+488h+var_282]; dwSpMinorVersion
0x1801d4226  movzx   r8d, [rsp+488h+var_284]; dwSpMajorVersion
0x1801d422f  lea     rax, [rsp+488h+var_438]
0x1801d4234  mov     [rsp+488h+pdwReturnedProductType], rax; int
0x1801d4239  mov     edx, [rsp+488h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x1801d4240  mov     ecx, [rsp+488h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x1801d4247  call    cs:__imp_GetProductInfo
0x1801d424e  nop     dword ptr [rax+rax+00h]
0x1801d4253  test    eax, eax
0x1801d4255  jnz     short loc_1801D42AB
0x1801d4257  call    cs:__imp_GetLastError
0x1801d425e  nop     dword ptr [rax+rax+00h]
0x1801d4263  mov     ebx, eax
0x1801d4265  test    eax, eax
0x1801d4267  jle     short loc_1801D4272
0x1801d4269  movzx   ebx, ax
0x1801d426c  or      ebx, 80070000h
0x1801d4272  mov     [rsp+488h+var_434], ebx
0x1801d4276  test    ebx, ebx
0x1801d4278  jns     short loc_1801D4297
0x1801d427a  mov     rcx, [rsp+488h]; this
0x1801d4282  mov     r9d, ebx; char *
0x1801d4285  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801d428c  mov     edx, 63h ; 'c'; void *
0x1801d4291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d4296  nop
0x1801d4297  lea     rcx, [rsp+488h+var_3E8]; this
0x1801d429f  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801d42a4  mov     eax, ebx
0x1801d42a6  jmp     loc_1801D4794
0x1801d42ab  lea     r10, [rsp+488h+var_24E]
0x1801d42b3  mov     r8d, [rsp+488h+var_438]
0x1801d42b8  sub     r10, 2
0x1801d42bc  mov     eax, 0CCCCCCCDh
0x1801d42c1  mul     r8d
0x1801d42c4  shr     edx, 3
0x1801d42c7  movzx   eax, dx
0x1801d42ca  shl     ax, 2
0x1801d42ce  lea     ecx, [rax+rdx]
0x1801d42d1  add     cx, cx
0x1801d42d4  sub     r8w, cx
0x1801d42d8  add     r8w, 30h ; '0'
0x1801d42dd  mov     [r10], r8w
0x1801d42e1  mov     r8d, edx
0x1801d42e4  test    edx, edx
0x1801d42e6  jnz     short loc_1801D42B8
0x1801d42e8  lea     r9, [rsp+488h+var_448]
0x1801d42ed  lea     r8, [rsp+488h+var_24E]
0x1801d42f5  mov     rdx, r10
0x1801d42f8  lea     rcx, [rsp+488h+var_410]
0x1801d42fd  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1801d4302  nop
0x1801d4303  xor     edx, edx; Val
0x1801d4305  mov     r8d, 208h; Size
0x1801d430b  lea     rcx, [rsp+488h+var_248]; void *
0x1801d4313  call    memset_0
0x1801d4318  mov     [rsp+488h+var_3F0], r12
0x1801d4320  xor     r8d, r8d
0x1801d4323  xor     edx, edx
0x1801d4325  lea     rcx, [rsp+488h+var_3F0]
0x1801d432d  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1801d4334  nop     dword ptr [rax+rax+00h]
0x1801d4339  mov     r9, [rsp+488h+var_3F0]
0x1801d4341  movzx   r8d, r9w
0x1801d4345  mov     rax, r9
0x1801d4348  shr     rax, 10h
0x1801d434c  movzx   edx, ax
0x1801d434f  mov     rax, r9
0x1801d4352  shr     rax, 20h
0x1801d4356  movzx   ecx, ax
0x1801d4359  shr     r9, 30h
0x1801d435d  mov     [rsp+488h+var_458], r8
0x1801d4362  mov     [rsp+488h+var_460], rdx
0x1801d4367  mov     [rsp+488h+pdwReturnedProductType], rcx; int
0x1801d436c  lea     r8, aLluLluLluLlu; "%llu.%llu.%llu.%llu"
0x1801d4373  mov     edx, 104h; unsigned __int64
0x1801d4378  lea     rcx, [rsp+488h+var_248]; unsigned __int16 *
0x1801d4380  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801d4385  mov     ebx, eax
0x1801d4387  mov     [rsp+488h+var_434], eax
0x1801d438b  test    eax, eax
0x1801d438d  jns     short loc_1801D43CB
0x1801d438f  mov     rcx, [rsp+488h]; this
0x1801d4397  mov     r9d, eax; char *
0x1801d439a  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801d43a1  mov     edx, 74h ; 't'; void *
0x1801d43a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d43ab  nop
0x1801d43ac  lea     rcx, [rsp+488h+var_410]
0x1801d43b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d43b6  nop
0x1801d43b7  lea     rcx, [rsp+488h+var_3E8]; this
0x1801d43bf  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801d43c4  mov     eax, ebx
0x1801d43c6  jmp     loc_1801D4794
0x1801d43cb  xorps   xmm0, xmm0
0x1801d43ce  movups  [rsp+488h+var_430], xmm0
0x1801d43d3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801d43db  movdqu  [rsp+488h+var_420], xmm1
0x1801d43e1  mov     word ptr [rsp+488h+var_430], r12w
0x1801d43e7  lea     r8, [rsp+488h+var_430]
0x1801d43ec  mov     rcx, rsi
0x1801d43ef  call    ?AddPortToUrl@HttpNetworkWrapper@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAV56@@Z; Microsoft::Windows::Autopilot::HttpNetworkWrapper::AddPortToUrl(std::wstring const &,ulong,std::wstring &)
0x1801d43f4  mov     ebx, eax
0x1801d43f6  mov     [rsp+488h+var_434], eax
0x1801d43fa  test    eax, eax
0x1801d43fc  jns     short loc_1801D4445
0x1801d43fe  mov     rcx, [rsp+488h]; this
0x1801d4406  mov     r9d, eax; char *
0x1801d4409  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801d4410  mov     edx, 78h ; 'x'; void *
0x1801d4415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d441a  nop
0x1801d441b  lea     rcx, [rsp+488h+var_430]
0x1801d4420  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d4425  nop
0x1801d4426  lea     rcx, [rsp+488h+var_410]
0x1801d442b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d4430  nop
0x1801d4431  lea     rcx, [rsp+488h+var_3E8]; this
0x1801d4439  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801d443e  mov     eax, ebx
0x1801d4440  jmp     loc_1801D4794
0x1801d4445  lea     rcx, [rsp+488h+var_248]
0x1801d444d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801d4451  inc     rax
0x1801d4454  cmp     [rcx+rax*2], r12w
0x1801d4459  jnz     short loc_1801D4451
0x1801d445b  lea     rdx, [rax+454h]
0x1801d4462  cmp     rdx, 454h
0x1801d4469  jnb     short loc_1801D44BB
0x1801d446b  mov     ebx, 80070216h
0x1801d4470  mov     [rsp+488h+var_434], ebx
0x1801d4474  mov     rcx, [rsp+488h]; this
0x1801d447c  mov     r9d, ebx; char *
0x1801d447f  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801d4486  mov     edx, 7Ch ; '|'; void *
0x1801d448b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d4490  nop
0x1801d4491  lea     rcx, [rsp+488h+var_430]
0x1801d4496  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d449b  nop
0x1801d449c  lea     rcx, [rsp+488h+var_410]
0x1801d44a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d44a6  nop
0x1801d44a7  lea     rcx, [rsp+488h+var_3E8]; this
0x1801d44af  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801d44b4  mov     eax, ebx
0x1801d44b6  jmp     loc_1801D4794
0x1801d44bb  mov     rcx, qword ptr [rsp+488h+var_420]
0x1801d44c0  add     rcx, rdx
0x1801d44c3  cmp     rcx, rdx
0x1801d44c6  jnb     short loc_1801D4518
0x1801d44c8  mov     ebx, 80070216h
0x1801d44cd  mov     [rsp+488h+var_434], ebx
0x1801d44d1  mov     rcx, [rsp+488h]; this
0x1801d44d9  mov     r9d, ebx; char *
0x1801d44dc  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801d44e3  mov     edx, 7Dh ; '}'; void *
0x1801d44e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d44ed  nop
0x1801d44ee  lea     rcx, [rsp+488h+var_430]
0x1801d44f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d44f8  nop
0x1801d44f9  lea     rcx, [rsp+488h+var_410]
0x1801d44fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d4503  nop
0x1801d4504  lea     rcx, [rsp+488h+var_3E8]; this
0x1801d450c  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801d4511  mov     eax, ebx
0x1801d4513  jmp     loc_1801D4794
0x1801d4518  mov     rdx, [rsp+488h+var_400]
0x1801d4520  add     rdx, rcx
0x1801d4523  cmp     rdx, rcx
0x1801d4526  jnb     short loc_1801D4578
0x1801d4528  mov     ebx, 80070216h
0x1801d452d  mov     [rsp+488h+var_434], ebx
0x1801d4531  mov     rcx, [rsp+488h]; this
0x1801d4539  mov     r9d, ebx; char *
0x1801d453c  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801d4543  mov     edx, 7Eh ; '~'; void *
0x1801d4548  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d454d  nop
0x1801d454e  lea     rcx, [rsp+488h+var_430]
0x1801d4553  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d4558  nop
0x1801d4559  lea     rcx, [rsp+488h+var_410]
0x1801d455e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d4563  nop
0x1801d4564  lea     rcx, [rsp+488h+var_3E8]; this
0x1801d456c  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801d4571  mov     eax, ebx
0x1801d4573  jmp     loc_1801D4794
0x1801d4578  mov     rcx, [rdi+10h]
0x1801d457c  add     rcx, rdx
0x1801d457f  cmp     rcx, rdx
0x1801d4582  jnb     short loc_1801D45D4
0x1801d4584  mov     ebx, 80070216h
0x1801d4589  mov     [rsp+488h+var_434], ebx
0x1801d458d  mov     rcx, [rsp+488h]; this
0x1801d4595  mov     r9d, ebx; char *
0x1801d4598  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801d459f  mov     edx, 7Fh; void *
0x1801d45a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d45a9  nop
0x1801d45aa  lea     rcx, [rsp+488h+var_430]
0x1801d45af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d45b4  nop
0x1801d45b5  lea     rcx, [rsp+488h+var_410]
0x1801d45ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801d45bf  nop
0x1801d45c0  lea     rcx, [rsp+488h+var_3E8]; this
0x1801d45c8  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x1801d45cd  mov     eax, ebx
0x1801d45cf  jmp     loc_1801D4794
0x1801d45d4  lea     r14, [rcx+1]
0x1801d45d8  cmp     r14, rcx
0x1801d45db  jb      loc_1801D4743
0x1801d45e1  mov     [rsp+488h+var_434], r12d
0x1801d45e6  mov     r8, r14
0x1801d45e9  xor     edx, edx
0x1801d45eb  lea     rcx, [rsp+488h+var_440]
0x1801d45f0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801d45f5  nop
0x1801d45f6  mov     rbx, [rsp+488h+var_440]
0x1801d45fb  test    rbx, rbx
0x1801d45fe  jnz     short loc_1801D465B
0x1801d4600  mov     ebx, 8007000Eh
0x1801d4605  mov     [rsp+488h+var_434], ebx
0x1801d4609  mov     rcx, [rsp+488h]; this
0x1801d4611  mov     r9d, ebx; char *
0x1801d4614  lea     r8, aOnecoreuapAdmi_146; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801d461b  mov     edx, 83h; void *
0x1801d4620  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d4625  nop
0x1801d4626  lea     rcx, [rsp+488h+var_440]
  ... truncated ...
```
