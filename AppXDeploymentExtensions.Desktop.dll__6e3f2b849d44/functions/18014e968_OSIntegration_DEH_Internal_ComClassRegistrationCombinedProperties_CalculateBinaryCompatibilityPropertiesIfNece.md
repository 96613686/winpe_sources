# OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary(OSIntegration::DEH::ICollectorPackageInformation const *)

- ea: `0x18014e968`
- end: `0x18014edae`
- name: `?CalculateBinaryCompatibilityPropertiesIfNecessary@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEAAJPEBUICollectorPackageInformation@34@@Z`
- size: `1094`
- prototype: `int(OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180164978`

## callees

- `0x1800502a4`
- `0x18006a320`
- `0x18006a4c8`
- `0x18007cdc0`
- `0x18014e968`
- `0x180158000`
- `0x180158f78`
- `0x18015a2f0`
- `0x18015bd50`
- `0x180169c98`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014e9c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ea2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014eaa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014eb25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ebd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ec47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ec9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ed08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ed5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014e9c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ea2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014eaa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014eb25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ebd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ec47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ec9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ed08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014ed5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ebfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ec6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ebfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014ec6f`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x18014ea70`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x18014eb6c`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x18014ea70`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x18014eb6c`

## string_xrefs

- `0x18014ea0b`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014eada`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014ea53`: `GetPackagedFileAbsolutePath(incomingPackage, _exeServerPath.Value.GetRawBuffer(nullptr), _exeServerAbsolutePath)`
- `0x18014ea00`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary`
- `0x18014eae5`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary`
- `0x18014eac9`: `ConstructCommandLine(_exeServerAbsolutePath.get(), _exeServerArguments.Value.GetRawBuffer(nullptr), _exeServerCommandLine)`
- `0x18014ea82`: `CoGetModuleArchitecture(_exeServerAbsolutePath.get(), reinterpret_cast<DWORD*>(&_executableArchitecture))`
- `0x18014eb7e`: `CoGetModuleArchitecture(_surrogateDllAbsolutePath.get(), reinterpret_cast<DWORD*>(&_surrogateDllArchitecture))`
- `0x18014eb4c`: `GetPackagedFileAbsolutePath(incomingPackage, _properties.DllPath.Value.GetRawBuffer(nullptr), _surrogateDllAbsolutePath)`
- `0x18014ece5`: `GetPackagedFileAbsolutePath(incomingPackage, GetInprocHandlerDllForArchitecture(architecture).GetRawBuffer(nullptr), _inprocHandlerAbsolutePaths.*(architecture.PerArchitectureDllPath))`
- `0x18014ecd4`: `GetPackagedFileAbsolutePath(incomingPackage, GetInprocServerDllForArchitecture(architecture).GetRawBuffer(nullptr), _inprocServerAbsolutePaths.*(architecture.PerArchitectureDllPath))`
- `0x18014ed2c`: `GetPackagedFileAbsolutePath(incomingPackage, _properties.ToolboxBitmap32.Value.GetRawBuffer(nullptr), _toolboxBitmap32AbsolutePath)`
- `0x18014ecc3`: `GetPackagedFileAbsolutePath(incomingPackage, _properties.DefaultIcon.Value.GetRawBuffer(nullptr), _defaultIconAbsolutePath)`
- `0x18014ed83`: `GetPackagedFileAbsolutePath(incomingPackage, _properties.ElevationIcon.Value.GetRawBuffer(nullptr), _elevationIconAbsolutePath)`
- `0x18014e9ef`: `GetSystemFileAbsolutePath(_executableArchitecture, _exeServerPath.Value.GetRawBuffer(nullptr), _exeServerAbsolutePath)`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary(
        OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *this,
        const struct OSIntegration::DEH::ICollectorPackageInformation *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  const WCHAR *StringRawBuffer; // rax
  _QWORD *v7; // rbx
  int SystemFileAbsolutePath; // esi
  const char *v9; // rax
  __int64 v10; // rdx
  const WCHAR *v12; // rax
  PCWSTR v13; // rax
  int PackagedFileAbsolutePath; // ebx
  const char *v15; // rax
  __int64 v16; // rdx
  const WCHAR *v17; // rax
  __int64 *v18; // rsi
  __int64 *v19; // rbp
  __int64 v20; // rbx
  HSTRING *InprocServerDllForArchitecture; // rax
  const WCHAR *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rbx
  const WCHAR *v25; // rax
  const WCHAR *v26; // rax
  const WCHAR *v27; // rax
  const WCHAR *v28; // rax
  char *v29; // [rsp+28h] [rbp-30h]
  int v30; // [rsp+30h] [rbp-28h]
  wil::details::in1diag5 *retaddr; // [rsp+58h] [rbp+0h]
  HSTRING string; // [rsp+70h] [rbp+18h] BYREF

  if ( OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::HasRegistryCompatibility(this) )
  {
    if ( *(_BYTE *)(v5 + 736) )
    {
      if ( *(_BYTE *)(v5 + 752) )
      {
        if ( !*(_DWORD *)(v5 + 756) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
        StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 93), 0);
        v7 = (_QWORD *)((char *)this + 856);
        SystemFileAbsolutePath = OSIntegration::DEH::Internal::GetSystemFileAbsolutePath(
                                   (char *)*((unsigned int *)this + 189),
                                   StringRawBuffer,
                                   (PWSTR *)this + 107);
        if ( SystemFileAbsolutePath < 0 )
        {
          v9 = "GetSystemFileAbsolutePath(_executableArchitecture, _exeServerPath.Value.GetRawBuffer(nullptr), _exeServerAbsolutePath)";
          v10 = 1696;
LABEL_8:
          LODWORD(v29) = SystemFileAbsolutePath;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)v10,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary",
            v9,
            v29,
            v30);
          return (unsigned int)SystemFileAbsolutePath;
        }
      }
      else
      {
        v12 = WindowsGetStringRawBuffer(*(HSTRING *)(v5 + 744), 0);
        v7 = (_QWORD *)((char *)this + 856);
        SystemFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(
                                   (__int64)a2,
                                   v12,
                                   (PWSTR *)this + 107);
        if ( SystemFileAbsolutePath < 0 )
        {
          v9 = "GetPackagedFileAbsolutePath(incomingPackage, _exeServerPath.Value.GetRawBuffer(nullptr), _exeServerAbsolutePath)";
          v10 = 1701;
          goto LABEL_8;
        }
        if ( !*((_DWORD *)this + 189) )
        {
          SystemFileAbsolutePath = CoGetModuleArchitecture(*v7, (char *)this + 756);
          if ( SystemFileAbsolutePath < 0 )
          {
            v9 = "CoGetModuleArchitecture(_exeServerAbsolutePath.get(), reinterpret_cast<DWORD*>(&_executableArchitecture))";
            v10 = 1706;
            goto LABEL_8;
          }
        }
      }
      if ( *((_BYTE *)this + 768) )
      {
        v13 = WindowsGetStringRawBuffer(*((HSTRING *)this + 97), 0);
        PackagedFileAbsolutePath = OSIntegration::DEH::Internal::ConstructCommandLine(*v7, v13, (char *)this + 864);
        if ( PackagedFileAbsolutePath < 0 )
        {
          v15 = "ConstructCommandLine(_exeServerAbsolutePath.get(), _exeServerArguments.Value.GetRawBuffer(nullptr), _exe"
                "ServerCommandLine)";
          v16 = 1716;
LABEL_17:
          LODWORD(v29) = PackagedFileAbsolutePath;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary",
            v15,
            v29,
            v30);
          return (unsigned int)PackagedFileAbsolutePath;
        }
      }
    }
    if ( *((_BYTE *)this + 304) && (!*((_BYTE *)this + 400) || !*((_BYTE *)this + 401)) )
    {
      v17 = WindowsGetStringRawBuffer(*((HSTRING *)this + 39), 0);
      PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(
                                   (__int64)a2,
                                   v17,
                                   (PWSTR *)this + 109);
      if ( PackagedFileAbsolutePath < 0 )
      {
        v15 = "GetPackagedFileAbsolutePath(incomingPackage, _properties.DllPath.Value.GetRawBuffer(nullptr), _surrogateDllAbsolutePath)";
        v16 = 1730;
        goto LABEL_17;
      }
      if ( !*((_DWORD *)this + 190) )
      {
        PackagedFileAbsolutePath = CoGetModuleArchitecture(*((_QWORD *)this + 109), (char *)this + 760);
        if ( PackagedFileAbsolutePath < 0 )
        {
          v15 = "CoGetModuleArchitecture(_surrogateDllAbsolutePath.get(), reinterpret_cast<DWORD*>(&_surrogateDllArchitecture))";
          v16 = 1735;
          goto LABEL_17;
        }
      }
    }
    v18 = qword_1801C00F0;
    v19 = qword_1801C00F0;
    do
    {
      if ( *((_BYTE *)this + *((int *)v19 + 6) + 64) && (!*((_BYTE *)this + 400) || !*((_BYTE *)this + 401)) )
      {
        v20 = *((int *)v19 + 9);
        InprocServerDllForArchitecture = (HSTRING *)OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
                                                      this,
                                                      &string,
                                                      v19);
        v22 = WindowsGetStringRawBuffer(*InprocServerDllForArchitecture, 0);
        PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(
                                     (__int64)a2,
                                     v22,
                                     (PWSTR *)((char *)this + v20 + 880));
        WindowsDeleteString(string);
        string = 0;
        if ( PackagedFileAbsolutePath < 0 )
        {
          v15 = "GetPackagedFileAbsolutePath(incomingPackage, GetInprocServerDllForArchitecture(architecture).GetRawBuffe"
                "r(nullptr), _inprocServerAbsolutePaths.*(architecture.PerArchitectureDllPath))";
          v16 = 1751;
          goto LABEL_17;
        }
      }
      v19 += 5;
    }
    while ( v19 != (__int64 *)L"\"$" );
    do
    {
      v23 = *((int *)v18 + 7);
      if ( *((_BYTE *)this + v23 + 64) )
      {
        v24 = *((int *)v18 + 9);
        OpaqueString::OpaqueString(
          &string,
          (OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *)((char *)this + v23 + 72));
        v25 = WindowsGetStringRawBuffer(string, 0);
        PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(
                                     (__int64)a2,
                                     v25,
                                     (PWSTR *)((char *)this + v24 + 912));
        WindowsDeleteString(string);
        string = 0;
        if ( PackagedFileAbsolutePath < 0 )
        {
          v15 = "GetPackagedFileAbsolutePath(incomingPackage, GetInprocHandlerDllForArchitecture(architecture).GetRawBuff"
                "er(nullptr), _inprocHandlerAbsolutePaths.*(architecture.PerArchitectureDllPath))";
          v16 = 1762;
          goto LABEL_17;
        }
      }
      v18 += 5;
    }
    while ( v18 != (__int64 *)L"\"$" );
    if ( *((_BYTE *)this + 176) )
    {
      v26 = WindowsGetStringRawBuffer(*((HSTRING *)this + 23), 0);
      PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(
                                   (__int64)a2,
                                   v26,
                                   (PWSTR *)this + 118);
      if ( PackagedFileAbsolutePath < 0 )
      {
        v15 = "GetPackagedFileAbsolutePath(incomingPackage, _properties.DefaultIcon.Value.GetRawBuffer(nullptr), _default"
              "IconAbsolutePath)";
        v16 = 1769;
        goto LABEL_17;
      }
    }
    if ( *((_BYTE *)this + 288) )
    {
      v27 = WindowsGetStringRawBuffer(*((HSTRING *)this + 37), 0);
      PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(
                                   (__int64)a2,
                                   v27,
                                   (PWSTR *)this + 119);
      if ( PackagedFileAbsolutePath < 0 )
      {
        v15 = "GetPackagedFileAbsolutePath(incomingPackage, _properties.ToolboxBitmap32.Value.GetRawBuffer(nullptr), _too"
              "lboxBitmap32AbsolutePath)";
        v16 = 1775;
        goto LABEL_17;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      if ( *((_BYTE *)this + 592) )
      {
        v28 = WindowsGetStringRawBuffer(*((HSTRING *)this + 75), 0);
        PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(
                                     (__int64)a2,
                                     v28,
                                     (PWSTR *)this + 120);
        if ( PackagedFileAbsolutePath < 0 )
        {
          v15 = "GetPackagedFileAbsolutePath(incomingPackage, _properties.ElevationIcon.Value.GetRawBuffer(nullptr), _ele"
                "vationIconAbsolutePath)";
          v16 = 1783;
          goto LABEL_17;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18014e968  mov     [rsp+arg_0], rbx
0x18014e96d  mov     [rsp+arg_8], rbp
0x18014e972  push    rsi
0x18014e973  push    rdi
0x18014e974  push    r12
0x18014e976  push    r14
0x18014e978  push    r15; int
0x18014e97a  sub     rsp, 30h
0x18014e97e  mov     r14, rdx
0x18014e981  mov     rdi, rcx
0x18014e984  xor     r15d, r15d
0x18014e987  call    ?HasRegistryCompatibility@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA_NXZ; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::HasRegistryCompatibility(void)
0x18014e98c  test    al, al
0x18014e98e  jz      loc_18014ED94
0x18014e994  cmp     [rcx+2E0h], r15b
0x18014e99b  jz      loc_18014EAFD
0x18014e9a1  cmp     [rcx+2F0h], r15b
0x18014e9a8  jz      short loc_18014EA23
0x18014e9aa  cmp     [rcx+2F4h], r15d
0x18014e9b1  jnz     short loc_18014E9B8
0x18014e9b3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "_executableArchitecture != IMAGE_FILE_MACHINE_UNKNOWN")
0x18014e9b8  mov     rcx, [rdi+2E8h]; string
0x18014e9bf  xor     edx, edx; length
0x18014e9c1  call    cs:__imp_WindowsGetStringRawBuffer
0x18014e9c8  nop     dword ptr [rax+rax+00h]
0x18014e9cd  mov     ecx, [rdi+2F4h]
0x18014e9d3  lea     rbx, [rdi+358h]
0x18014e9da  mov     r8, rbx
0x18014e9dd  mov     rdx, rax
0x18014e9e0  call    ?GetSystemFileAbsolutePath@Internal@DEH@OSIntegration@@YAJIPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetSystemFileAbsolutePath(uint,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18014e9e5  mov     esi, eax
0x18014e9e7  test    eax, eax
0x18014e9e9  jns     loc_18014EA93
0x18014e9ef  lea     rax, aGetsystemfilea; "GetSystemFileAbsolutePath(_executableAr"...
0x18014e9f6  mov     edx, 6A0h; void *
0x18014e9fb  mov     rcx, [rsp+58h]; this
0x18014ea00  lea     r9, aOsintegrationD_208; "OSIntegration::DEH::Internal::ComClassR"...
0x18014ea07  mov     dword ptr [rsp+58h+var_30], esi; char *
0x18014ea0b  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014ea12  mov     [rsp+58h+var_38], rax; char *
0x18014ea17  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014ea1c  mov     eax, esi
0x18014ea1e  jmp     loc_18014ED96
0x18014ea23  mov     rcx, [rcx+2E8h]; string
0x18014ea2a  xor     edx, edx; length
0x18014ea2c  call    cs:__imp_WindowsGetStringRawBuffer
0x18014ea33  nop     dword ptr [rax+rax+00h]
0x18014ea38  lea     rbx, [rdi+358h]
0x18014ea3f  mov     rcx, r14
0x18014ea42  mov     r8, rbx
0x18014ea45  mov     rdx, rax
0x18014ea48  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18014ea4d  mov     esi, eax
0x18014ea4f  test    eax, eax
0x18014ea51  jns     short loc_18014EA61
0x18014ea53  lea     rax, aGetpackagedfil_1; "GetPackagedFileAbsolutePath(incomingPac"...
0x18014ea5a  mov     edx, 6A5h
0x18014ea5f  jmp     short loc_18014E9FB
0x18014ea61  lea     rdx, [rdi+2F4h]
0x18014ea68  cmp     [rdx], r15d
0x18014ea6b  jnz     short loc_18014EA93
0x18014ea6d  mov     rcx, [rbx]
0x18014ea70  call    cs:__imp_CoGetModuleArchitecture
0x18014ea77  nop     dword ptr [rax+rax+00h]
0x18014ea7c  mov     esi, eax
0x18014ea7e  test    eax, eax
0x18014ea80  jns     short loc_18014EA93
0x18014ea82  lea     rax, aCogetmodulearc_0; "CoGetModuleArchitecture(_exeServerAbsol"...
0x18014ea89  mov     edx, 6AAh
0x18014ea8e  jmp     loc_18014E9FB
0x18014ea93  cmp     [rdi+300h], r15b
0x18014ea9a  jz      short loc_18014EAFD
0x18014ea9c  mov     rcx, [rdi+308h]; string
0x18014eaa3  xor     edx, edx; length
0x18014eaa5  call    cs:__imp_WindowsGetStringRawBuffer
0x18014eaac  nop     dword ptr [rax+rax+00h]
0x18014eab1  mov     rcx, [rbx]
0x18014eab4  lea     r8, [rdi+360h]
0x18014eabb  mov     rdx, rax
0x18014eabe  call    ?ConstructCommandLine@Internal@DEH@OSIntegration@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::ConstructCommandLine(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18014eac3  mov     ebx, eax
0x18014eac5  test    eax, eax
0x18014eac7  jns     short loc_18014EAFD
0x18014eac9  lea     rax, aConstructcomma; "ConstructCommandLine(_exeServerAbsolute"...
0x18014ead0  mov     edx, 6B4h; void *
0x18014ead5  mov     rcx, [rsp+58h]; this
0x18014eada  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014eae1  mov     dword ptr [rsp+58h+var_30], ebx; char *
0x18014eae5  lea     r9, aOsintegrationD_208; "OSIntegration::DEH::Internal::ComClassR"...
0x18014eaec  mov     [rsp+58h+var_38], rax; char *
0x18014eaf1  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014eaf6  mov     eax, ebx
0x18014eaf8  jmp     loc_18014ED96
0x18014eafd  cmp     [rdi+130h], r15b
0x18014eb04  jz      loc_18014EB8F
0x18014eb0a  cmp     [rdi+190h], r15b
0x18014eb11  jz      short loc_18014EB1C
0x18014eb13  cmp     [rdi+191h], r15b
0x18014eb1a  jnz     short loc_18014EB8F
0x18014eb1c  mov     rcx, [rdi+138h]; string
0x18014eb23  xor     edx, edx; length
0x18014eb25  call    cs:__imp_WindowsGetStringRawBuffer
0x18014eb2c  nop     dword ptr [rax+rax+00h]
0x18014eb31  lea     rsi, [rdi+368h]
0x18014eb38  mov     rcx, r14
0x18014eb3b  mov     r8, rsi
0x18014eb3e  mov     rdx, rax
0x18014eb41  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18014eb46  mov     ebx, eax
0x18014eb48  test    eax, eax
0x18014eb4a  jns     short loc_18014EB5D
0x18014eb4c  lea     rax, aGetpackagedfil; "GetPackagedFileAbsolutePath(incomingPac"...
0x18014eb53  mov     edx, 6C2h
0x18014eb58  jmp     loc_18014EAD5
0x18014eb5d  lea     rdx, [rdi+2F8h]
0x18014eb64  cmp     [rdx], r15d
0x18014eb67  jnz     short loc_18014EB8F
0x18014eb69  mov     rcx, [rsi]
0x18014eb6c  call    cs:__imp_CoGetModuleArchitecture
0x18014eb73  nop     dword ptr [rax+rax+00h]
0x18014eb78  mov     ebx, eax
0x18014eb7a  test    eax, eax
0x18014eb7c  jns     short loc_18014EB8F
0x18014eb7e  lea     rax, aCogetmodulearc; "CoGetModuleArchitecture(_surrogateDllAb"...
0x18014eb85  mov     edx, 6C7h
0x18014eb8a  jmp     loc_18014EAD5
0x18014eb8f  lea     rsi, qword_1801C00F0
0x18014eb96  mov     rbp, rsi
0x18014eb99  lea     r12, CmSymbolicLinkValueName; "\"$"
0x18014eba0  movsxd  rax, dword ptr [rbp+18h]
0x18014eba4  cmp     [rax+rdi+40h], r15b
0x18014eba9  jz      short loc_18014EC17
0x18014ebab  cmp     [rdi+190h], r15b
0x18014ebb2  jz      short loc_18014EBBD
0x18014ebb4  cmp     [rdi+191h], r15b
0x18014ebbb  jnz     short loc_18014EC17
0x18014ebbd  movsxd  rbx, dword ptr [rbp+24h]
0x18014ebc1  lea     rdx, [rsp+58h+string]
0x18014ebc6  mov     r8, rbp
0x18014ebc9  mov     rcx, rdi
0x18014ebcc  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x18014ebd1  xor     edx, edx; length
0x18014ebd3  mov     rcx, [rax]; string
0x18014ebd6  call    cs:__imp_WindowsGetStringRawBuffer
0x18014ebdd  nop     dword ptr [rax+rax+00h]
0x18014ebe2  lea     r8, [rdi+370h]
0x18014ebe9  mov     rcx, r14
0x18014ebec  add     r8, rbx
0x18014ebef  mov     rdx, rax
0x18014ebf2  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18014ebf7  mov     rcx, [rsp+58h+string]; string
0x18014ebfc  mov     ebx, eax
0x18014ebfe  call    cs:__imp_WindowsDeleteString
0x18014ec05  nop     dword ptr [rax+rax+00h]
0x18014ec0a  mov     [rsp+58h+string], r15
0x18014ec0f  test    ebx, ebx
0x18014ec11  js      loc_18014ECD4
0x18014ec17  add     rbp, 28h ; '('
0x18014ec1b  cmp     rbp, r12
0x18014ec1e  jnz     short loc_18014EBA0
0x18014ec20  movsxd  rcx, dword ptr [rsi+1Ch]
0x18014ec24  cmp     [rcx+rdi+40h], r15b
0x18014ec29  jz      short loc_18014EC84
0x18014ec2b  movsxd  rbx, dword ptr [rsi+24h]
0x18014ec2f  lea     rdx, [rdi+48h]
0x18014ec33  add     rdx, rcx; struct OpaqueString *
0x18014ec36  lea     rcx, [rsp+58h+string]; newString
0x18014ec3b  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x18014ec40  mov     rcx, [rsp+58h+string]; string
0x18014ec45  xor     edx, edx; length
0x18014ec47  call    cs:__imp_WindowsGetStringRawBuffer
0x18014ec4e  nop     dword ptr [rax+rax+00h]
0x18014ec53  lea     r8, [rdi+390h]
0x18014ec5a  mov     rcx, r14
0x18014ec5d  add     r8, rbx
0x18014ec60  mov     rdx, rax
0x18014ec63  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18014ec68  mov     rcx, [rsp+58h+string]; string
0x18014ec6d  mov     ebx, eax
0x18014ec6f  call    cs:__imp_WindowsDeleteString
0x18014ec76  nop     dword ptr [rax+rax+00h]
0x18014ec7b  mov     [rsp+58h+string], r15
0x18014ec80  test    ebx, ebx
0x18014ec82  js      short loc_18014ECE5
0x18014ec84  add     rsi, 28h ; '('
0x18014ec88  cmp     rsi, r12
0x18014ec8b  jnz     short loc_18014EC20
0x18014ec8d  cmp     [rdi+0B0h], r15b
0x18014ec94  jz      short loc_18014ECF6
0x18014ec96  mov     rcx, [rdi+0B8h]; string
0x18014ec9d  xor     edx, edx; length
0x18014ec9f  call    cs:__imp_WindowsGetStringRawBuffer
0x18014eca6  nop     dword ptr [rax+rax+00h]
0x18014ecab  lea     r8, [rdi+3B0h]
0x18014ecb2  mov     rcx, r14
0x18014ecb5  mov     rdx, rax
0x18014ecb8  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18014ecbd  mov     ebx, eax
0x18014ecbf  test    eax, eax
0x18014ecc1  jns     short loc_18014ECF6
0x18014ecc3  lea     rax, aGetpackagedfil_3; "GetPackagedFileAbsolutePath(incomingPac"...
0x18014ecca  mov     edx, 6E9h
0x18014eccf  jmp     loc_18014EAD5
0x18014ecd4  lea     rax, aGetpackagedfil_4; "GetPackagedFileAbsolutePath(incomingPac"...
0x18014ecdb  mov     edx, 6D7h
0x18014ece0  jmp     loc_18014EAD5
0x18014ece5  lea     rax, aGetpackagedfil_0; "GetPackagedFileAbsolutePath(incomingPac"...
0x18014ecec  mov     edx, 6E2h
0x18014ecf1  jmp     loc_18014EAD5
0x18014ecf6  cmp     [rdi+120h], r15b
0x18014ecfd  jz      short loc_18014ED3D
0x18014ecff  mov     rcx, [rdi+128h]; string
0x18014ed06  xor     edx, edx; length
0x18014ed08  call    cs:__imp_WindowsGetStringRawBuffer
0x18014ed0f  nop     dword ptr [rax+rax+00h]
0x18014ed14  lea     r8, [rdi+3B8h]
0x18014ed1b  mov     rcx, r14
0x18014ed1e  mov     rdx, rax
0x18014ed21  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18014ed26  mov     ebx, eax
0x18014ed28  test    eax, eax
0x18014ed2a  jns     short loc_18014ED3D
0x18014ed2c  lea     rax, aGetpackagedfil_2; "GetPackagedFileAbsolutePath(incomingPac"...
0x18014ed33  mov     edx, 6EFh
0x18014ed38  jmp     loc_18014EAD5
0x18014ed3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18014ed44  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18014ed49  test    al, al
0x18014ed4b  jz      short loc_18014ED94
0x18014ed4d  cmp     [rdi+250h], r15b
0x18014ed54  jz      short loc_18014ED94
0x18014ed56  mov     rcx, [rdi+258h]; string
0x18014ed5d  xor     edx, edx; length
0x18014ed5f  call    cs:__imp_WindowsGetStringRawBuffer
0x18014ed66  nop     dword ptr [rax+rax+00h]
0x18014ed6b  lea     r8, [rdi+3C0h]
0x18014ed72  mov     rcx, r14
0x18014ed75  mov     rdx, rax
0x18014ed78  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18014ed7d  mov     ebx, eax
0x18014ed7f  test    eax, eax
0x18014ed81  jns     short loc_18014ED94
0x18014ed83  lea     rax, aGetpackagedfil_5; "GetPackagedFileAbsolutePath(incomingPac"...
0x18014ed8a  mov     edx, 6F7h
0x18014ed8f  jmp     loc_18014EAD5
0x18014ed94  xor     eax, eax
0x18014ed96  mov     rbx, [rsp+58h+arg_0]
0x18014ed9b  mov     rbp, [rsp+58h+arg_8]
0x18014eda0  add     rsp, 30h
0x18014eda4  pop     r15
0x18014eda6  pop     r14
0x18014eda8  pop     r12
0x18014edaa  pop     rdi
0x18014edab  pop     rsi
0x18014edac  retn
```
