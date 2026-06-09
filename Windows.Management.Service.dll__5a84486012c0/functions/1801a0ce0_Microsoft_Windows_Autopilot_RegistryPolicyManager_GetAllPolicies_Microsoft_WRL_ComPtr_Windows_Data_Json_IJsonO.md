# Microsoft::Windows::Autopilot::RegistryPolicyManager::GetAllPolicies(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x1801a0ce0`
- end: `0x1801a10db`
- name: `?GetAllPolicies@RegistryPolicyManager@Autopilot@Windows@Microsoft@@UEBAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `1019`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067a54`
- `0x18006c628`
- `0x18007755c`
- `0x18007ff90`
- `0x18008019c`
- `0x180084208`
- `0x1800853a0`
- `0x1800873a4`
- `0x180089614`
- `0x180089b58`
- `0x18008b9c4`
- `0x18008c630`
- `0x18008e438`
- `0x18008e584`
- `0x1801a0ce0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801a0eb6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801a0eb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a0e18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a0e18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a0f2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a0f95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a0fe6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a0f2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a0f95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a0fe6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801a0d6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801a0d6a`

## string_xrefs

- `0x1801a0d1c`: `Windows.Data.Json.JsonObject`
- `0x1801a0d4a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1801a0db9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1801a0e4c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1801a1032`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1801a1054`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1801a1073`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::RegistryPolicyManager::GetAllPolicies(
        __int64 a1,
        struct Windows::Data::Json::IJsonObject **a2)
{
  int v3; // eax
  signed int v4; // ebx
  int v5; // eax
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rax
  bool v8; // al
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  __int64 v11; // rdx
  unsigned __int64 v12; // r9
  DWORD i; // esi
  LSTATUS v14; // eax
  LSTATUS v15; // edi
  unsigned int v16; // eax
  int v17; // eax
  unsigned int ValueW; // eax
  void *v19; // rax
  const unsigned __int16 *v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v28; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int pvData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchValueName; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[32]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ValueName; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[526]; // [rsp+B2h] [rbp-4Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v3 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v34, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    std::wstring::wstring(v36);
    v5 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(&SystemTime, v36);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
      v5 = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a2, L"AutopilotCreationDate", v7);
      v4 = v5;
      if ( v5 >= 0 )
      {
        hKey = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
        v8 = ZTPIsStateSeparationEnabled();
        v9 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicy";
        if ( !v8 )
          v9 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicy";
        v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hKey);
        v4 = v10;
        if ( (unsigned int)(v10 - 2) <= 1 )
        {
LABEL_42:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          v4 = 0;
        }
        else
        {
          if ( v10 > 0 )
            v4 = (unsigned __int16)v10 | 0x80070000;
          if ( v4 >= 0 )
          {
            memset_0(v38, 0, 0x206u);
            for ( i = 0; ; ++i )
            {
              cchValueName = 260;
              ValueName = 0;
              Type = 0;
              v14 = RegEnumValueW(hKey, i, &ValueName, &cchValueName, 0, &Type, 0, 0);
              v15 = v14;
              if ( v14 == 259 )
                goto LABEL_42;
              v4 = v14 > 0 ? (unsigned __int16)v14 | 0x80070000 : v14;
              if ( v4 < 0 )
                break;
              if ( Type == 1 )
              {
                std::wstring::wstring(&hstringHeader);
                v28 = 0;
                ValueW = RegGetValueW(hKey, 0, &ValueName, 2u, 0, 0, &v28);
                if ( ValueW )
                {
                  v22 = 165;
                  goto LABEL_39;
                }
                std::wstring::resize(&hstringHeader, (unsigned __int64)v28 >> 1, 0);
                v19 = (void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
                ValueW = RegGetValueW(hKey, 0, &ValueName, 2u, 0, v19, &v28);
                if ( ValueW )
                {
                  v22 = 167;
LABEL_39:
                  v4 = wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)v22,
                         (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
                         (const char *)ValueW,
                         phkResultb);
                  goto LABEL_40;
                }
                v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
                v21 = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a2, &ValueName, v20);
                v4 = v21;
                if ( v21 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xA9,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
                    (const char *)(unsigned int)v21,
                    phkResultb);
LABEL_40:
                  std::wstring::_Tidy_deallocate(&hstringHeader);
                  goto LABEL_17;
                }
                std::wstring::_Tidy_deallocate(&hstringHeader);
              }
              else if ( Type == 4 )
              {
                pvData = 0;
                pcbData = 4;
                v16 = RegGetValueW(hKey, 0, &ValueName, 0x10u, 0, &pvData, &pcbData);
                if ( v16 )
                {
                  v4 = wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)0xB1,
                         (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
                         (const char *)v16,
                         phkResulta);
                  goto LABEL_17;
                }
                v17 = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a2, &ValueName, pvData);
                v4 = v17;
                if ( v17 < 0 )
                {
                  v12 = (unsigned int)v17;
                  v11 = 179;
                  goto LABEL_16;
                }
              }
              if ( v15 )
                goto LABEL_42;
            }
            v11 = 157;
          }
          else
          {
            v11 = 130;
          }
          v12 = (unsigned int)v4;
LABEL_16:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v11,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
            (const char *)v12,
            phkResulta);
LABEL_17:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        }
        goto LABEL_43;
      }
      v6 = 115;
    }
    else
    {
      v6 = 114;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
LABEL_43:
    std::wstring::_Tidy_deallocate(v36);
    return (unsigned int)v4;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6C,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
    (const char *)(unsigned int)v3,
    phkResult);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801a0ce0  push    rbp
0x1801a0ce2  push    rbx
0x1801a0ce3  push    rsi
0x1801a0ce4  push    rdi
0x1801a0ce5  push    r14
0x1801a0ce7  push    r15
0x1801a0ce9  lea     rbp, [rsp-1D8h]
0x1801a0cf1  sub     rsp, 2D8h
0x1801a0cf8  mov     rax, cs:__security_cookie
0x1801a0cff  xor     rax, rsp
0x1801a0d02  mov     [rbp+200h+var_40], rax
0x1801a0d09  mov     r14, rdx
0x1801a0d0c  xor     r15d, r15d
0x1801a0d0f  mov     [rsp+300h+var_288], r15
0x1801a0d14  lea     r9d, [r15+1Ch]; unsigned int
0x1801a0d18  lea     r8d, [r15+1Dh]; unsigned int
0x1801a0d1c  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1801a0d23  lea     rcx, [rsp+300h+hstringHeader]; hstringHeader
0x1801a0d28  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801a0d2d  mov     rdx, r14
0x1801a0d30  mov     rcx, [rsp+300h+var_288]
0x1801a0d35  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1801a0d3a  mov     ebx, eax
0x1801a0d3c  test    eax, eax
0x1801a0d3e  jns     short loc_1801A0D5F
0x1801a0d40  mov     rcx, [rbp+208h]; this
0x1801a0d47  mov     r9d, eax; char *
0x1801a0d4a  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a0d51  lea     edx, [r15+6Ch]; void *
0x1801a0d55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a0d5a  jmp     loc_1801A10BA
0x1801a0d5f  xorps   xmm0, xmm0
0x1801a0d62  movups  xmmword ptr [rbp+200h+SystemTime.wYear], xmm0
0x1801a0d66  lea     rcx, [rbp+200h+SystemTime]; lpSystemTime
0x1801a0d6a  call    cs:__imp_GetSystemTime
0x1801a0d70  lea     rcx, [rbp+200h+var_270]
0x1801a0d74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801a0d79  lea     rdx, [rbp+200h+var_270]
0x1801a0d7d  lea     rcx, [rbp+200h+SystemTime]
0x1801a0d81  call    ?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::wstring &)
0x1801a0d86  mov     ebx, eax
0x1801a0d88  test    eax, eax
0x1801a0d8a  jns     short loc_1801A0D93
0x1801a0d8c  mov     edx, 72h ; 'r'
0x1801a0d91  jmp     short loc_1801A0DB9
0x1801a0d93  lea     rcx, [rbp+200h+var_270]
0x1801a0d97  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0d9c  mov     r8, rax; unsigned __int16 *
0x1801a0d9f  lea     rdx, aAutopilotcreat; "AutopilotCreationDate"
0x1801a0da6  mov     rcx, [r14]; struct Windows::Data::Json::IJsonObject *
0x1801a0da9  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1801a0dae  mov     ebx, eax
0x1801a0db0  test    eax, eax
0x1801a0db2  jns     short loc_1801A0DD4
0x1801a0db4  mov     edx, 73h ; 's'; void *
0x1801a0db9  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a0dc0  mov     r9d, eax; char *
0x1801a0dc3  mov     rcx, [rbp+208h]; this
0x1801a0dca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a0dcf  jmp     loc_1801A10B1
0x1801a0dd4  mov     [rsp+300h+hKey], r15
0x1801a0dd9  xor     edx, edx
0x1801a0ddb  lea     rcx, [rsp+300h+hKey]
0x1801a0de0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801a0de5  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1801a0dea  lea     rcx, aSoftwareMicros_16; "Software\\Microsoft\\Provisioning\\Auto"...
0x1801a0df1  lea     rdx, SubKey; "OSData\\Software\\Microsoft\\Provisioni"...
0x1801a0df8  test    al, al
0x1801a0dfa  cmovz   rdx, rcx; lpSubKey
0x1801a0dfe  lea     rax, [rsp+300h+hKey]
0x1801a0e03  mov     [rsp+300h+phkResult], rax; int
0x1801a0e08  mov     r9d, 20019h; samDesired
0x1801a0e0e  xor     r8d, r8d; ulOptions
0x1801a0e11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a0e18  call    cs:__imp_RegOpenKeyExW
0x1801a0e1e  mov     ebx, eax
0x1801a0e20  lea     ecx, [rax-2]
0x1801a0e23  cmp     ecx, 1
0x1801a0e26  jbe     loc_1801A10A4
0x1801a0e2c  test    eax, eax
0x1801a0e2e  jle     short loc_1801A0E39
0x1801a0e30  movzx   ebx, ax
0x1801a0e33  or      ebx, 80070000h
0x1801a0e39  test    ebx, ebx
0x1801a0e3b  jns     short loc_1801A0E67
0x1801a0e3d  mov     edx, 82h; void *
0x1801a0e42  mov     r9d, ebx; char *
0x1801a0e45  mov     rcx, [rbp+208h]; this
0x1801a0e4c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a0e53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a0e58  lea     rcx, [rsp+300h+hKey]
0x1801a0e5d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801a0e62  jmp     loc_1801A10B1
0x1801a0e67  xor     edx, edx; Val
0x1801a0e69  mov     r8d, 206h; Size
0x1801a0e6f  lea     rcx, [rbp+200h+var_24E]; void *
0x1801a0e73  call    memset_0
0x1801a0e78  mov     esi, r15d
0x1801a0e7b  mov     [rsp+300h+cchValueName], 104h
0x1801a0e83  mov     [rbp+200h+ValueName], r15w
0x1801a0e88  mov     [rsp+300h+Type], r15d
0x1801a0e8d  mov     [rsp+300h+lpcbData], r15; lpcbData
0x1801a0e92  mov     [rsp+300h+lpData], r15; lpData
0x1801a0e97  lea     rax, [rsp+300h+Type]
0x1801a0e9c  mov     [rsp+300h+lpType], rax; lpType
0x1801a0ea1  mov     [rsp+300h+phkResult], r15; lpReserved
0x1801a0ea6  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x1801a0eab  lea     r8, [rbp+200h+ValueName]; lpValueName
0x1801a0eaf  mov     edx, esi; dwIndex
0x1801a0eb1  mov     rcx, [rsp+300h+hKey]; hKey
0x1801a0eb6  call    cs:__imp_RegEnumValueW
0x1801a0ebc  mov     edi, eax
0x1801a0ebe  cmp     eax, 103h
0x1801a0ec3  jz      loc_1801A10A4
0x1801a0ec9  test    eax, eax
0x1801a0ecb  jg      short loc_1801A0ED1
0x1801a0ecd  mov     ebx, eax
0x1801a0ecf  jmp     short loc_1801A0EDA
0x1801a0ed1  movzx   ebx, di
0x1801a0ed4  or      ebx, 80070000h
0x1801a0eda  test    ebx, ebx
0x1801a0edc  js      loc_1801A109A
0x1801a0ee2  mov     eax, [rsp+300h+Type]
0x1801a0ee6  sub     eax, 1
0x1801a0ee9  jz      short loc_1801A0F61
0x1801a0eeb  cmp     eax, 3
0x1801a0eee  jnz     loc_1801A1019
0x1801a0ef4  mov     [rsp+300h+pvData], r15d
0x1801a0ef9  mov     [rsp+300h+pcbData], 4
0x1801a0f01  lea     rax, [rsp+300h+pcbData]
0x1801a0f06  mov     [rsp+300h+lpData], rax; pcbData
0x1801a0f0b  lea     rax, [rsp+300h+pvData]
0x1801a0f10  mov     [rsp+300h+lpType], rax; pvData
0x1801a0f15  mov     [rsp+300h+phkResult], r15; unsigned int
0x1801a0f1a  mov     r9d, 10h; dwFlags
0x1801a0f20  lea     r8, [rbp+200h+ValueName]; lpValue
0x1801a0f24  xor     edx, edx; lpSubKey
0x1801a0f26  mov     rcx, [rsp+300h+hKey]; hkey
0x1801a0f2b  call    cs:__imp_RegGetValueW
0x1801a0f31  test    eax, eax
0x1801a0f33  jnz     loc_1801A1028
0x1801a0f39  mov     r8d, [rsp+300h+pvData]; unsigned int
0x1801a0f3e  lea     rdx, [rbp+200h+ValueName]; unsigned __int16 *
0x1801a0f42  mov     rcx, [r14]; struct Windows::Data::Json::IJsonObject *
0x1801a0f45  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1801a0f4a  mov     ebx, eax
0x1801a0f4c  test    eax, eax
0x1801a0f4e  jns     loc_1801A1019
0x1801a0f54  mov     r9d, eax
0x1801a0f57  mov     edx, 0B3h
0x1801a0f5c  jmp     loc_1801A0E45
0x1801a0f61  lea     rcx, [rsp+300h+hstringHeader]
0x1801a0f66  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801a0f6b  mov     [rsp+300h+var_2B8], r15d
0x1801a0f70  lea     rax, [rsp+300h+var_2B8]
0x1801a0f75  mov     [rsp+300h+lpData], rax; pcbData
0x1801a0f7a  mov     [rsp+300h+lpType], r15; pvData
0x1801a0f7f  mov     [rsp+300h+phkResult], r15; unsigned int
0x1801a0f84  mov     r9d, 2; dwFlags
0x1801a0f8a  lea     r8, [rbp+200h+ValueName]; lpValue
0x1801a0f8e  xor     edx, edx; lpSubKey
0x1801a0f90  mov     rcx, [rsp+300h+hKey]; hkey
0x1801a0f95  call    cs:__imp_RegGetValueW
0x1801a0f9b  test    eax, eax
0x1801a0f9d  jnz     loc_1801A106E
0x1801a0fa3  xor     r8d, r8d
0x1801a0fa6  mov     edx, [rsp+300h+var_2B8]
0x1801a0faa  shr     rdx, 1
0x1801a0fad  lea     rcx, [rsp+300h+hstringHeader]
0x1801a0fb2  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1801a0fb7  lea     rcx, [rsp+300h+hstringHeader]
0x1801a0fbc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0fc1  lea     rcx, [rsp+300h+var_2B8]
0x1801a0fc6  mov     [rsp+300h+lpData], rcx; pcbData
0x1801a0fcb  mov     [rsp+300h+lpType], rax; pvData
0x1801a0fd0  mov     [rsp+300h+phkResult], r15; int
0x1801a0fd5  mov     r9d, 2; dwFlags
0x1801a0fdb  lea     r8, [rbp+200h+ValueName]; lpValue
0x1801a0fdf  xor     edx, edx; lpSubKey
0x1801a0fe1  mov     rcx, [rsp+300h+hKey]; hkey
0x1801a0fe6  call    cs:__imp_RegGetValueW
0x1801a0fec  test    eax, eax
0x1801a0fee  jnz     short loc_1801A1067
0x1801a0ff0  lea     rcx, [rsp+300h+hstringHeader]
0x1801a0ff5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a0ffa  mov     r8, rax; unsigned __int16 *
0x1801a0ffd  lea     rdx, [rbp+200h+ValueName]; unsigned __int16 *
0x1801a1001  mov     rcx, [r14]; struct Windows::Data::Json::IJsonObject *
0x1801a1004  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1801a1009  mov     ebx, eax
0x1801a100b  test    eax, eax
0x1801a100d  js      short loc_1801A104A
0x1801a100f  lea     rcx, [rsp+300h+hstringHeader]
0x1801a1014  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a1019  test    edi, edi
0x1801a101b  jnz     loc_1801A10A4
0x1801a1021  inc     esi
0x1801a1023  jmp     loc_1801A0E7B
0x1801a1028  mov     rcx, [rbp+208h]; this
0x1801a102f  mov     r9d, eax; char *
0x1801a1032  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a1039  mov     edx, 0B1h; void *
0x1801a103e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801a1043  mov     ebx, eax
0x1801a1045  jmp     loc_1801A0E58
0x1801a104a  mov     rcx, [rbp+208h]; this
0x1801a1051  mov     r9d, eax; char *
0x1801a1054  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a105b  mov     edx, 0A9h; void *
0x1801a1060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a1065  jmp     short loc_1801A108B
0x1801a1067  mov     edx, 0A7h
0x1801a106c  jmp     short loc_1801A1073
0x1801a106e  mov     edx, 0A5h; void *
0x1801a1073  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a107a  mov     r9d, eax; char *
0x1801a107d  mov     rcx, [rbp+208h]; this
0x1801a1084  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801a1089  mov     ebx, eax
0x1801a108b  lea     rcx, [rsp+300h+hstringHeader]
0x1801a1090  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a1095  jmp     loc_1801A0E58
0x1801a109a  mov     edx, 9Dh
0x1801a109f  jmp     loc_1801A0E42
0x1801a10a4  lea     rcx, [rsp+300h+hKey]
0x1801a10a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801a10ae  mov     ebx, r15d
0x1801a10b1  lea     rcx, [rbp+200h+var_270]
0x1801a10b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a10ba  mov     eax, ebx
0x1801a10bc  mov     rcx, [rbp+200h+var_40]
0x1801a10c3  xor     rcx, rsp; StackCookie
0x1801a10c6  call    __security_check_cookie
0x1801a10cb  add     rsp, 2D8h
0x1801a10d2  pop     r15
0x1801a10d4  pop     r14
0x1801a10d6  pop     rdi
0x1801a10d7  pop     rsi
0x1801a10d8  pop     rbx
0x1801a10d9  pop     rbp
0x1801a10da  retn
```
