# OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary(OSIntegration::DEH::ICollectorPackageInformation const *)

- ea: `0x1801ba940`
- end: `0x1801bad30`
- name: `?CalculateBinaryCompatibilityPropertiesIfNecessary@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEAAJPEBUICollectorPackageInformation@34@@Z`
- size: `1008`
- prototype: `int(OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801cf4c8`

## callees

- `0x180084114`
- `0x1800990a4`
- `0x18009aff4`
- `0x1800b8300`
- `0x1801ba940`
- `0x1801c34b8`
- `0x1801c4364`
- `0x1801c570c`
- `0x1801c6fd0`
- `0x1801d4be4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ba999`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ba9fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801baa6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801baae1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801bab88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801babfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801bac56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801bac97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801bace8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ba999`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ba9fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801baa6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801baae1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801bab88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801babfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801bac56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801bac97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801bace8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801babaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bac1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801babaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bac1e`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x1801baa3c`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x1801bab1f`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x1801baa3c`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleArchitecture` at `0x1801bab1f`

## string_xrefs

- `0x1801ba9dd`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801baa9a`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x1801bab02`: `GetPackagedFileAbsolutePath(incomingPackage, _properties.DllPath.Value.GetRawBuffer(nullptr), _surrogateDllAbsolutePath)`
- `0x1801bab2b`: `CoGetModuleArchitecture(_surrogateDllAbsolutePath.get(), reinterpret_cast<DWORD*>(&_surrogateDllArchitecture))`
- `0x1801baa48`: `CoGetModuleArchitecture(_exeServerAbsolutePath.get(), reinterpret_cast<DWORD*>(&_executableArchitecture))`
- `0x1801baa89`: `ConstructCommandLine(_exeServerAbsolutePath.get(), _exeServerArguments.Value.GetRawBuffer(nullptr), _exeServerCommandLine)`
- `0x1801ba9d2`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary`
- `0x1801baaa5`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary`
- `0x1801baa1f`: `GetPackagedFileAbsolutePath(incomingPackage, _exeServerPath.Value.GetRawBuffer(nullptr), _exeServerAbsolutePath)`
- `0x1801ba9c1`: `GetSystemFileAbsolutePath(_executableArchitecture, _exeServerPath.Value.GetRawBuffer(nullptr), _exeServerAbsolutePath)`
- `0x1801bad06`: `GetPackagedFileAbsolutePath(incomingPackage, _properties.ElevationIcon.Value.GetRawBuffer(nullptr), _elevationIconAbsolutePath)`
- `0x1801bac74`: `GetPackagedFileAbsolutePath(incomingPackage, _properties.DefaultIcon.Value.GetRawBuffer(nullptr), _defaultIconAbsolutePath)`
- `0x1801bacb5`: `GetPackagedFileAbsolutePath(incomingPackage, _properties.ToolboxBitmap32.Value.GetRawBuffer(nullptr), _toolboxBitmap32AbsolutePath)`
- `0x1801babbf`: `GetPackagedFileAbsolutePath(incomingPackage, GetInprocServerDllForArchitecture(architecture).GetRawBuffer(nullptr), _inprocServerAbsolutePaths.*(architecture.PerArchitectureDllPath))`
- `0x1801bac33`: `GetPackagedFileAbsolutePath(incomingPackage, GetInprocHandlerDllForArchitecture(architecture).GetRawBuffer(nullptr), _inprocHandlerAbsolutePaths.*(architecture.PerArchitectureDllPath))`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary(
        HSTRING *this,
        const struct OSIntegration::DEH::ICollectorPackageInformation *a2)
{
  __int64 v4; // rcx
  const WCHAR *StringRawBuffer; // rax
  _QWORD *v6; // rbx
  int SystemFileAbsolutePath; // esi
  const char *v8; // rax
  __int64 v9; // rdx
  PCWSTR v11; // rax
  PCWSTR v12; // rax
  int PackagedFileAbsolutePath; // ebx
  const char *v14; // rax
  __int64 v15; // rdx
  PCWSTR v16; // rax
  __int64 *v17; // rsi
  __int64 *i; // rbp
  __int64 v19; // rbx
  HSTRING *InprocServerDllForArchitecture; // rax
  PCWSTR v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rbx
  PCWSTR v24; // rax
  PCWSTR v25; // rax
  PCWSTR v26; // rax
  PCWSTR v27; // rax
  char *v28; // [rsp+28h] [rbp-30h]
  int v29; // [rsp+30h] [rbp-28h]
  wil::details::in1diag5 *retaddr; // [rsp+58h] [rbp+0h]
  HSTRING string; // [rsp+70h] [rbp+18h] BYREF

  if ( OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::HasRegistryCompatibility((OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *)this) )
  {
    if ( *(_BYTE *)(v4 + 736) )
    {
      if ( *(_BYTE *)(v4 + 752) )
      {
        if ( !*(_DWORD *)(v4 + 756) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v4);
        StringRawBuffer = WindowsGetStringRawBuffer(this[93], 0);
        v6 = this + 107;
        SystemFileAbsolutePath = OSIntegration::DEH::Internal::GetSystemFileAbsolutePath(
                                   (char *)*((unsigned int *)this + 189),
                                   StringRawBuffer,
                                   (PWSTR *)this + 107);
        if ( SystemFileAbsolutePath < 0 )
        {
          v8 = "GetSystemFileAbsolutePath(_executableArchitecture, _exeServerPath.Value.GetRawBuffer(nullptr), _exeServerAbsolutePath)";
          v9 = 1696;
LABEL_8:
          LODWORD(v28) = SystemFileAbsolutePath;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)v9,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary",
            v8,
            v28,
            v29);
          return (unsigned int)SystemFileAbsolutePath;
        }
      }
      else
      {
        v11 = WindowsGetStringRawBuffer(*(HSTRING *)(v4 + 744), 0);
        v6 = this + 107;
        SystemFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(a2, v11, this + 107);
        if ( SystemFileAbsolutePath < 0 )
        {
          v8 = "GetPackagedFileAbsolutePath(incomingPackage, _exeServerPath.Value.GetRawBuffer(nullptr), _exeServerAbsolutePath)";
          v9 = 1701;
          goto LABEL_8;
        }
        if ( !*((_DWORD *)this + 189) )
        {
          SystemFileAbsolutePath = CoGetModuleArchitecture(*v6, (char *)this + 756);
          if ( SystemFileAbsolutePath < 0 )
          {
            v8 = "CoGetModuleArchitecture(_exeServerAbsolutePath.get(), reinterpret_cast<DWORD*>(&_executableArchitecture))";
            v9 = 1706;
            goto LABEL_8;
          }
        }
      }
      if ( *((_BYTE *)this + 768) )
      {
        v12 = WindowsGetStringRawBuffer(this[97], 0);
        PackagedFileAbsolutePath = OSIntegration::DEH::Internal::ConstructCommandLine(*v6, v12, this + 108);
        if ( PackagedFileAbsolutePath < 0 )
        {
          v14 = "ConstructCommandLine(_exeServerAbsolutePath.get(), _exeServerArguments.Value.GetRawBuffer(nullptr), _exe"
                "ServerCommandLine)";
          v15 = 1716;
LABEL_17:
          LODWORD(v28) = PackagedFileAbsolutePath;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CalculateBinaryCompatibilityPropertiesIfNecessary",
            v14,
            v28,
            v29);
          return (unsigned int)PackagedFileAbsolutePath;
        }
      }
    }
    if ( *((_BYTE *)this + 304) && (!*((_BYTE *)this + 400) || !*((_BYTE *)this + 401)) )
    {
      v16 = WindowsGetStringRawBuffer(this[39], 0);
      PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(a2, v16, this + 109);
      if ( PackagedFileAbsolutePath < 0 )
      {
        v14 = "GetPackagedFileAbsolutePath(incomingPackage, _properties.DllPath.Value.GetRawBuffer(nullptr), _surrogateDllAbsolutePath)";
        v15 = 1730;
        goto LABEL_17;
      }
      if ( !*((_DWORD *)this + 190) )
      {
        PackagedFileAbsolutePath = CoGetModuleArchitecture(this[109], this + 95);
        if ( PackagedFileAbsolutePath < 0 )
        {
          v14 = "CoGetModuleArchitecture(_surrogateDllAbsolutePath.get(), reinterpret_cast<DWORD*>(&_surrogateDllArchitecture))";
          v15 = 1735;
          goto LABEL_17;
        }
      }
    }
    v17 = qword_18022AC20;
    for ( i = qword_18022AC20; i != (__int64 *)off_18022ACC0; i += 5 )
    {
      if ( *((_BYTE *)this + *((int *)i + 6) + 64) && (!*((_BYTE *)this + 400) || !*((_BYTE *)this + 401)) )
      {
        v19 = *((int *)i + 9);
        InprocServerDllForArchitecture = (HSTRING *)OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(
                                                      this,
                                                      &string,
                                                      i);
        v21 = WindowsGetStringRawBuffer(*InprocServerDllForArchitecture, 0);
        PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(
                                     a2,
                                     v21,
                                     (char *)this + v19 + 880);
        WindowsDeleteString(string);
        string = 0;
        if ( PackagedFileAbsolutePath < 0 )
        {
          v14 = "GetPackagedFileAbsolutePath(incomingPackage, GetInprocServerDllForArchitecture(architecture).GetRawBuffe"
                "r(nullptr), _inprocServerAbsolutePaths.*(architecture.PerArchitectureDllPath))";
          v15 = 1751;
          goto LABEL_17;
        }
      }
    }
    while ( v17 != (__int64 *)off_18022ACC0 )
    {
      v22 = *((int *)v17 + 7);
      if ( *((_BYTE *)this + v22 + 64) )
      {
        v23 = *((int *)v17 + 9);
        OpaqueString::OpaqueString(&string, (const struct OpaqueString *)((char *)this + v22 + 72));
        v24 = WindowsGetStringRawBuffer(string, 0);
        PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(
                                     a2,
                                     v24,
                                     (char *)this + v23 + 912);
        WindowsDeleteString(string);
        string = 0;
        if ( PackagedFileAbsolutePath < 0 )
        {
          v14 = "GetPackagedFileAbsolutePath(incomingPackage, GetInprocHandlerDllForArchitecture(architecture).GetRawBuff"
                "er(nullptr), _inprocHandlerAbsolutePaths.*(architecture.PerArchitectureDllPath))";
          v15 = 1762;
          goto LABEL_17;
        }
      }
      v17 += 5;
    }
    if ( *((_BYTE *)this + 176) )
    {
      v25 = WindowsGetStringRawBuffer(this[23], 0);
      PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(a2, v25, this + 118);
      if ( PackagedFileAbsolutePath < 0 )
      {
        v14 = "GetPackagedFileAbsolutePath(incomingPackage, _properties.DefaultIcon.Value.GetRawBuffer(nullptr), _default"
              "IconAbsolutePath)";
        v15 = 1769;
        goto LABEL_17;
      }
    }
    if ( *((_BYTE *)this + 288) )
    {
      v26 = WindowsGetStringRawBuffer(this[37], 0);
      PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(a2, v26, this + 119);
      if ( PackagedFileAbsolutePath < 0 )
      {
        v14 = "GetPackagedFileAbsolutePath(incomingPackage, _properties.ToolboxBitmap32.Value.GetRawBuffer(nullptr), _too"
              "lboxBitmap32AbsolutePath)";
        v15 = 1775;
        goto LABEL_17;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      if ( *((_BYTE *)this + 592) )
      {
        v27 = WindowsGetStringRawBuffer(this[75], 0);
        PackagedFileAbsolutePath = OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(a2, v27, this + 120);
        if ( PackagedFileAbsolutePath < 0 )
        {
          v14 = "GetPackagedFileAbsolutePath(incomingPackage, _properties.ElevationIcon.Value.GetRawBuffer(nullptr), _ele"
                "vationIconAbsolutePath)";
          v15 = 1783;
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
0x1801ba940  mov     [rsp+arg_0], rbx
0x1801ba945  mov     [rsp+arg_8], rbp
0x1801ba94a  push    rsi
0x1801ba94b  push    rdi
0x1801ba94c  push    r12
0x1801ba94e  push    r14
0x1801ba950  push    r15; int
0x1801ba952  sub     rsp, 30h
0x1801ba956  mov     r14, rdx
0x1801ba959  mov     rdi, rcx
0x1801ba95c  xor     r15d, r15d
0x1801ba95f  call    ?HasRegistryCompatibility@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA_NXZ; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::HasRegistryCompatibility(void)
0x1801ba964  test    al, al
0x1801ba966  jz      loc_1801BAD17
0x1801ba96c  cmp     [rcx+2E0h], r15b
0x1801ba973  jz      loc_1801BAABD
0x1801ba979  cmp     [rcx+2F0h], r15b
0x1801ba980  jz      short loc_1801BA9F5
0x1801ba982  cmp     [rcx+2F4h], r15d
0x1801ba989  jnz     short loc_1801BA990
0x1801ba98b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1801ba990  mov     rcx, [rdi+2E8h]; string
0x1801ba997  xor     edx, edx; length
0x1801ba999  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ba99f  mov     ecx, [rdi+2F4h]
0x1801ba9a5  lea     rbx, [rdi+358h]
0x1801ba9ac  mov     r8, rbx
0x1801ba9af  mov     rdx, rax
0x1801ba9b2  call    ?GetSystemFileAbsolutePath@Internal@DEH@OSIntegration@@YAJIPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetSystemFileAbsolutePath(uint,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801ba9b7  mov     esi, eax
0x1801ba9b9  test    eax, eax
0x1801ba9bb  jns     loc_1801BAA59
0x1801ba9c1  lea     rax, aGetsystemfilea; "GetSystemFileAbsolutePath(_executableAr"...
0x1801ba9c8  mov     edx, 6A0h; void *
0x1801ba9cd  mov     rcx, [rsp+58h]; this
0x1801ba9d2  lea     r9, aOsintegrationD_302; "OSIntegration::DEH::Internal::ComClassR"...
0x1801ba9d9  mov     dword ptr [rsp+58h+var_30], esi; char *
0x1801ba9dd  lea     r8, aOnecoreAdminAp_96; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801ba9e4  mov     [rsp+58h+var_38], rax; char *
0x1801ba9e9  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801ba9ee  mov     eax, esi
0x1801ba9f0  jmp     loc_1801BAD19
0x1801ba9f5  mov     rcx, [rcx+2E8h]; string
0x1801ba9fc  xor     edx, edx; length
0x1801ba9fe  call    cs:__imp_WindowsGetStringRawBuffer
0x1801baa04  lea     rbx, [rdi+358h]
0x1801baa0b  mov     rcx, r14
0x1801baa0e  mov     r8, rbx
0x1801baa11  mov     rdx, rax
0x1801baa14  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801baa19  mov     esi, eax
0x1801baa1b  test    eax, eax
0x1801baa1d  jns     short loc_1801BAA2D
0x1801baa1f  lea     rax, aGetpackagedfil_1; "GetPackagedFileAbsolutePath(incomingPac"...
0x1801baa26  mov     edx, 6A5h
0x1801baa2b  jmp     short loc_1801BA9CD
0x1801baa2d  lea     rdx, [rdi+2F4h]
0x1801baa34  cmp     [rdx], r15d
0x1801baa37  jnz     short loc_1801BAA59
0x1801baa39  mov     rcx, [rbx]
0x1801baa3c  call    cs:__imp_CoGetModuleArchitecture
0x1801baa42  mov     esi, eax
0x1801baa44  test    eax, eax
0x1801baa46  jns     short loc_1801BAA59
0x1801baa48  lea     rax, aCogetmodulearc_2; "CoGetModuleArchitecture(_exeServerAbsol"...
0x1801baa4f  mov     edx, 6AAh
0x1801baa54  jmp     loc_1801BA9CD
0x1801baa59  cmp     [rdi+300h], r15b
0x1801baa60  jz      short loc_1801BAABD
0x1801baa62  mov     rcx, [rdi+308h]; string
0x1801baa69  xor     edx, edx; length
0x1801baa6b  call    cs:__imp_WindowsGetStringRawBuffer
0x1801baa71  mov     rcx, [rbx]
0x1801baa74  lea     r8, [rdi+360h]
0x1801baa7b  mov     rdx, rax
0x1801baa7e  call    ?ConstructCommandLine@Internal@DEH@OSIntegration@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::ConstructCommandLine(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801baa83  mov     ebx, eax
0x1801baa85  test    eax, eax
0x1801baa87  jns     short loc_1801BAABD
0x1801baa89  lea     rax, aConstructcomma; "ConstructCommandLine(_exeServerAbsolute"...
0x1801baa90  mov     edx, 6B4h; void *
0x1801baa95  mov     rcx, [rsp+58h]; this
0x1801baa9a  lea     r8, aOnecoreAdminAp_96; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1801baaa1  mov     dword ptr [rsp+58h+var_30], ebx; char *
0x1801baaa5  lea     r9, aOsintegrationD_302; "OSIntegration::DEH::Internal::ComClassR"...
0x1801baaac  mov     [rsp+58h+var_38], rax; char *
0x1801baab1  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1801baab6  mov     eax, ebx
0x1801baab8  jmp     loc_1801BAD19
0x1801baabd  cmp     [rdi+130h], r15b
0x1801baac4  jz      short loc_1801BAB3C
0x1801baac6  cmp     [rdi+190h], r15b
0x1801baacd  jz      short loc_1801BAAD8
0x1801baacf  cmp     [rdi+191h], r15b
0x1801baad6  jnz     short loc_1801BAB3C
0x1801baad8  mov     rcx, [rdi+138h]; string
0x1801baadf  xor     edx, edx; length
0x1801baae1  call    cs:__imp_WindowsGetStringRawBuffer
0x1801baae7  lea     rsi, [rdi+368h]
0x1801baaee  mov     rcx, r14
0x1801baaf1  mov     r8, rsi
0x1801baaf4  mov     rdx, rax
0x1801baaf7  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801baafc  mov     ebx, eax
0x1801baafe  test    eax, eax
0x1801bab00  jns     short loc_1801BAB10
0x1801bab02  lea     rax, aGetpackagedfil; "GetPackagedFileAbsolutePath(incomingPac"...
0x1801bab09  mov     edx, 6C2h
0x1801bab0e  jmp     short loc_1801BAA95
0x1801bab10  lea     rdx, [rdi+2F8h]
0x1801bab17  cmp     [rdx], r15d
0x1801bab1a  jnz     short loc_1801BAB3C
0x1801bab1c  mov     rcx, [rsi]
0x1801bab1f  call    cs:__imp_CoGetModuleArchitecture
0x1801bab25  mov     ebx, eax
0x1801bab27  test    eax, eax
0x1801bab29  jns     short loc_1801BAB3C
0x1801bab2b  lea     rax, aCogetmodulearc; "CoGetModuleArchitecture(_surrogateDllAb"...
0x1801bab32  mov     edx, 6C7h
0x1801bab37  jmp     loc_1801BAA95
0x1801bab3c  lea     rsi, qword_18022AC20
0x1801bab43  mov     rbp, rsi
0x1801bab46  lea     r12, off_18022ACC0; "MaxInstallOrder"
0x1801bab4d  cmp     rbp, r12
0x1801bab50  jz      short loc_1801BABD0
0x1801bab52  movsxd  rax, dword ptr [rbp+18h]
0x1801bab56  cmp     [rax+rdi+40h], r15b
0x1801bab5b  jz      short loc_1801BABB9
0x1801bab5d  cmp     [rdi+190h], r15b
0x1801bab64  jz      short loc_1801BAB6F
0x1801bab66  cmp     [rdi+191h], r15b
0x1801bab6d  jnz     short loc_1801BABB9
0x1801bab6f  movsxd  rbx, dword ptr [rbp+24h]
0x1801bab73  lea     rdx, [rsp+58h+string]
0x1801bab78  mov     r8, rbp
0x1801bab7b  mov     rcx, rdi
0x1801bab7e  call    ?GetInprocServerDllForArchitecture@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEBA?AVOpaqueString@@AEBUPerArchitectureInformation@234@@Z; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::GetInprocServerDllForArchitecture(OSIntegration::DEH::Internal::PerArchitectureInformation const &)
0x1801bab83  xor     edx, edx; length
0x1801bab85  mov     rcx, [rax]; string
0x1801bab88  call    cs:__imp_WindowsGetStringRawBuffer
0x1801bab8e  lea     r8, [rdi+370h]
0x1801bab95  mov     rcx, r14
0x1801bab98  add     r8, rbx
0x1801bab9b  mov     rdx, rax
0x1801bab9e  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801baba3  mov     rcx, [rsp+58h+string]; string
0x1801baba8  mov     ebx, eax
0x1801babaa  call    cs:__imp_WindowsDeleteString
0x1801babb0  mov     [rsp+58h+string], r15
0x1801babb5  test    ebx, ebx
0x1801babb7  js      short loc_1801BABBF
0x1801babb9  add     rbp, 28h ; '('
0x1801babbd  jmp     short loc_1801BAB4D
0x1801babbf  lea     rax, aGetpackagedfil_4; "GetPackagedFileAbsolutePath(incomingPac"...
0x1801babc6  mov     edx, 6D7h
0x1801babcb  jmp     loc_1801BAA95
0x1801babd0  cmp     rsi, r12
0x1801babd3  jz      short loc_1801BAC44
0x1801babd5  movsxd  rcx, dword ptr [rsi+1Ch]
0x1801babd9  cmp     [rcx+rdi+40h], r15b
0x1801babde  jz      short loc_1801BAC2D
0x1801babe0  movsxd  rbx, dword ptr [rsi+24h]
0x1801babe4  lea     rdx, [rdi+48h]
0x1801babe8  add     rdx, rcx; struct OpaqueString *
0x1801babeb  lea     rcx, [rsp+58h+string]; newString
0x1801babf0  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x1801babf5  mov     rcx, [rsp+58h+string]; string
0x1801babfa  xor     edx, edx; length
0x1801babfc  call    cs:__imp_WindowsGetStringRawBuffer
0x1801bac02  lea     r8, [rdi+390h]
0x1801bac09  mov     rcx, r14
0x1801bac0c  add     r8, rbx
0x1801bac0f  mov     rdx, rax
0x1801bac12  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801bac17  mov     rcx, [rsp+58h+string]; string
0x1801bac1c  mov     ebx, eax
0x1801bac1e  call    cs:__imp_WindowsDeleteString
0x1801bac24  mov     [rsp+58h+string], r15
0x1801bac29  test    ebx, ebx
0x1801bac2b  js      short loc_1801BAC33
0x1801bac2d  add     rsi, 28h ; '('
0x1801bac31  jmp     short loc_1801BABD0
0x1801bac33  lea     rax, aGetpackagedfil_0; "GetPackagedFileAbsolutePath(incomingPac"...
0x1801bac3a  mov     edx, 6E2h
0x1801bac3f  jmp     loc_1801BAA95
0x1801bac44  cmp     [rdi+0B0h], r15b
0x1801bac4b  jz      short loc_1801BAC85
0x1801bac4d  mov     rcx, [rdi+0B8h]; string
0x1801bac54  xor     edx, edx; length
0x1801bac56  call    cs:__imp_WindowsGetStringRawBuffer
0x1801bac5c  lea     r8, [rdi+3B0h]
0x1801bac63  mov     rcx, r14
0x1801bac66  mov     rdx, rax
0x1801bac69  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801bac6e  mov     ebx, eax
0x1801bac70  test    eax, eax
0x1801bac72  jns     short loc_1801BAC85
0x1801bac74  lea     rax, aGetpackagedfil_3; "GetPackagedFileAbsolutePath(incomingPac"...
0x1801bac7b  mov     edx, 6E9h
0x1801bac80  jmp     loc_1801BAA95
0x1801bac85  cmp     [rdi+120h], r15b
0x1801bac8c  jz      short loc_1801BACC6
0x1801bac8e  mov     rcx, [rdi+128h]; string
0x1801bac95  xor     edx, edx; length
0x1801bac97  call    cs:__imp_WindowsGetStringRawBuffer
0x1801bac9d  lea     r8, [rdi+3B8h]
0x1801baca4  mov     rcx, r14
0x1801baca7  mov     rdx, rax
0x1801bacaa  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801bacaf  mov     ebx, eax
0x1801bacb1  test    eax, eax
0x1801bacb3  jns     short loc_1801BACC6
0x1801bacb5  lea     rax, aGetpackagedfil_2; "GetPackagedFileAbsolutePath(incomingPac"...
0x1801bacbc  mov     edx, 6EFh
0x1801bacc1  jmp     loc_1801BAA95
0x1801bacc6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1801baccd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1801bacd2  test    al, al
0x1801bacd4  jz      short loc_1801BAD17
0x1801bacd6  cmp     [rdi+250h], r15b
0x1801bacdd  jz      short loc_1801BAD17
0x1801bacdf  mov     rcx, [rdi+258h]; string
0x1801bace6  xor     edx, edx; length
0x1801bace8  call    cs:__imp_WindowsGetStringRawBuffer
0x1801bacee  lea     r8, [rdi+3C0h]
0x1801bacf5  mov     rcx, r14
0x1801bacf8  mov     rdx, rax
0x1801bacfb  call    ?GetPackagedFileAbsolutePath@Internal@DEH@OSIntegration@@YAJPEBUICollectorPackageInformation@23@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; OSIntegration::DEH::Internal::GetPackagedFileAbsolutePath(OSIntegration::DEH::ICollectorPackageInformation const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1801bad00  mov     ebx, eax
0x1801bad02  test    eax, eax
0x1801bad04  jns     short loc_1801BAD17
0x1801bad06  lea     rax, aGetpackagedfil_5; "GetPackagedFileAbsolutePath(incomingPac"...
0x1801bad0d  mov     edx, 6F7h
0x1801bad12  jmp     loc_1801BAA95
0x1801bad17  xor     eax, eax
0x1801bad19  mov     rbx, [rsp+58h+arg_0]
0x1801bad1e  mov     rbp, [rsp+58h+arg_8]
0x1801bad23  add     rsp, 30h
0x1801bad27  pop     r15
0x1801bad29  pop     r14
0x1801bad2b  pop     r12
0x1801bad2d  pop     rdi
0x1801bad2e  pop     rsi
0x1801bad2f  retn
```
