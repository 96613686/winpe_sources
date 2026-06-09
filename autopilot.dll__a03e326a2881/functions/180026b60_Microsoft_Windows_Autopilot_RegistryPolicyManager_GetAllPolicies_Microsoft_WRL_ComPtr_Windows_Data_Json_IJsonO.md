# Microsoft::Windows::Autopilot::RegistryPolicyManager::GetAllPolicies(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x180026b60`
- end: `0x180027025`
- name: `?GetAllPolicies@RegistryPolicyManager@Autopilot@Windows@Microsoft@@UEBAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `1221`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x18000ec40`
- `0x1800105f4`
- `0x1800166dc`
- `0x1800174f0`
- `0x1800175f4`
- `0x180018120`
- `0x18001e7b4`
- `0x18001ea04`
- `0x180020ec0`
- `0x180026b60`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026e08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026e86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026eff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026e08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026e86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026eff`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180026d93`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180026d93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026cea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026cea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026d38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026fcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026fed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026d38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026fcc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026fed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026ba9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026ba9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180026c12`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180026c12`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180026ca4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180026ca4`

## string_xrefs

- `0x180026ba2`: `Windows.Data.Json.JsonObject`
- `0x180026bef`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x180026c73`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x180026d1e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x180026f50`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x180026f72`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x180026f91`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Autopilot::RegistryPolicyManager::GetAllPolicies(
        __int64 a1,
        struct Windows::Data::Json::IJsonObject **a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  HSTRING v6; // rbx
  struct Windows::Data::Json::IJsonObject *v7; // rcx
  int v8; // eax
  signed int v9; // ebx
  int v11; // eax
  __int64 v12; // rdx
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  char v16; // al
  const WCHAR *v17; // rdx
  LSTATUS v18; // eax
  __int64 v19; // rdx
  unsigned __int64 v20; // r9
  DWORD i; // r14d
  LSTATUS v22; // eax
  LSTATUS v23; // esi
  unsigned int v24; // eax
  int v25; // eax
  unsigned int ValueW; // eax
  unsigned __int64 v27; // rdx
  _WORD *p_hstringHeader; // rcx
  void *Reserved1; // rax
  const unsigned __int16 *v30; // r8
  int v31; // eax
  __int64 v32; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v37; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int pvData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchValueName; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v44[2]; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v48[526]; // [rsp+B2h] [rbp-4Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x180027024LL);
  }
  v6 = string;
  v7 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v6, a2);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
      (const char *)(unsigned int)v8,
      phkResult);
    return (unsigned int)v9;
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  *(_OWORD *)v44 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v44[0]) = 0;
  v11 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(&SystemTime, v44);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = 114;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
      (const char *)(unsigned int)v11,
      phkResult);
LABEL_64:
    std::wstring::_Tidy_deallocate(v44);
    return (unsigned int)v9;
  }
  v13 = (const unsigned __int16 *)v44;
  if ( si128.m128i_i64[1] > 7uLL )
    v13 = v44[0];
  v11 = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a2, L"AutopilotCreationDate", v13);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = 115;
    goto LABEL_13;
  }
  hKey = 0;
  if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    v16 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
  }
  else
  {
    v16 = (unsigned __int8)RtlIsStateSeparationEnabled(v15, v14) != 0;
    `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v16;
    `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
  }
  v17 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  if ( !v16 )
    v17 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v17, 0, 0x20019u, &hKey);
  v9 = v18;
  if ( (unsigned int)(v18 - 2) > 1 )
  {
    if ( v18 > 0 )
      v9 = (unsigned __int16)v18 | 0x80070000;
    if ( v9 >= 0 )
    {
      memset_0(v48, 0, 0x206u);
      for ( i = 0; ; ++i )
      {
        cchValueName = 260;
        ValueName = 0;
        Type = 0;
        v22 = RegEnumValueW(hKey, i, &ValueName, &cchValueName, 0, &Type, 0, 0);
        v23 = v22;
        if ( v22 == 259 )
          break;
        if ( v22 > 0 )
          v9 = (unsigned __int16)v22 | 0x80070000;
        else
          v9 = v22;
        if ( v9 < 0 )
        {
          v19 = 157;
          goto LABEL_24;
        }
        if ( Type == 1 )
        {
          memset(&hstringHeader, 0, sizeof(hstringHeader));
          string = (HSTRING)7;
          LOWORD(hstringHeader.Reserved.Reserved1) = 0;
          v37 = 0;
          ValueW = RegGetValueW(hKey, 0, &ValueName, 2u, 0, 0, &v37);
          if ( ValueW )
          {
            v32 = 165;
LABEL_58:
            v9 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)v32,
                   (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
                   (const char *)ValueW,
                   phkResultb);
LABEL_59:
            std::wstring::_Tidy_deallocate(&hstringHeader);
            goto LABEL_26;
          }
          v27 = (unsigned __int64)v37 >> 1;
          p_hstringHeader = &hstringHeader;
          if ( v27 > *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] )
          {
            std::wstring::append(&hstringHeader);
          }
          else
          {
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = (unsigned __int64)v37 >> 1;
            if ( (unsigned __int64)string > 7 )
              p_hstringHeader = hstringHeader.Reserved.Reserved1;
            p_hstringHeader[v27] = 0;
          }
          Reserved1 = &hstringHeader;
          if ( (unsigned __int64)string > 7 )
            Reserved1 = hstringHeader.Reserved.Reserved1;
          ValueW = RegGetValueW(hKey, 0, &ValueName, 2u, 0, Reserved1, &v37);
          if ( ValueW )
          {
            v32 = 167;
            goto LABEL_58;
          }
          v30 = (const unsigned __int16 *)&hstringHeader;
          if ( (unsigned __int64)string > 7 )
            v30 = (const unsigned __int16 *)hstringHeader.Reserved.Reserved1;
          v31 = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a2, &ValueName, v30);
          v9 = v31;
          if ( v31 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA9,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
              (const char *)(unsigned int)v31,
              phkResultb);
            goto LABEL_59;
          }
          std::wstring::_Tidy_deallocate(&hstringHeader);
        }
        else if ( Type == 4 )
        {
          pvData = 0;
          pcbData = 4;
          v24 = RegGetValueW(hKey, 0, &ValueName, 0x10u, 0, &pvData, &pcbData);
          if ( v24 )
          {
            v9 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0xB1,
                   (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
                   (const char *)v24,
                   phkResulta);
            goto LABEL_26;
          }
          v25 = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a2, &ValueName, pvData);
          v9 = v25;
          if ( v25 < 0 )
          {
            v20 = (unsigned int)v25;
            v19 = 179;
            goto LABEL_25;
          }
        }
        if ( v23 )
          goto LABEL_65;
      }
      if ( hKey )
        RegCloseKey(hKey);
      v9 = 0;
    }
    else
    {
      v19 = 130;
LABEL_24:
      v20 = (unsigned int)v9;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
        (const char *)v20,
        phkResulta);
LABEL_26:
      if ( hKey )
        RegCloseKey(hKey);
    }
    goto LABEL_64;
  }
LABEL_65:
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::_Tidy_deallocate(v44);
  return 0;
}

```

## disassembly

```asm
0x180026b60  push    rbp
0x180026b62  push    rbx
0x180026b63  push    rsi
0x180026b64  push    rdi
0x180026b65  push    r14
0x180026b67  push    r15
0x180026b69  lea     rbp, [rsp-1D8h]
0x180026b71  sub     rsp, 2D8h
0x180026b78  mov     rax, cs:__security_cookie
0x180026b7f  xor     rax, rsp
0x180026b82  mov     [rbp+200h+var_40], rax
0x180026b89  mov     rdi, rdx
0x180026b8c  xor     r15d, r15d
0x180026b8f  mov     [rsp+300h+string], r15
0x180026b94  lea     r9, [rsp+300h+string]; string
0x180026b99  lea     r8, [rsp+300h+hstringHeader]; hstringHeader
0x180026b9e  lea     edx, [r15+1Ch]; length
0x180026ba2  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180026ba9  call    cs:__imp_WindowsCreateStringReference
0x180026baf  test    eax, eax
0x180026bb1  js      loc_18002701D
0x180026bb7  mov     rbx, [rsp+300h+string]
0x180026bbc  mov     rcx, [rdi]
0x180026bbf  test    rcx, rcx
0x180026bc2  jz      short loc_180026BD4
0x180026bc4  mov     [rdi], r15
0x180026bc7  mov     rax, [rcx]
0x180026bca  mov     rax, [rax+10h]
0x180026bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bd3  nop
0x180026bd4  mov     rdx, rdi
0x180026bd7  mov     rcx, rbx
0x180026bda  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180026bdf  mov     ebx, eax
0x180026be1  test    eax, eax
0x180026be3  jns     short loc_180026C07
0x180026be5  mov     rcx, [rbp+208h]; this
0x180026bec  mov     r9d, eax; char *
0x180026bef  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026bf6  mov     edx, 6Ch ; 'l'; void *
0x180026bfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026c00  mov     eax, ebx
0x180026c02  jmp     loc_180026FFE
0x180026c07  xorps   xmm0, xmm0
0x180026c0a  movups  xmmword ptr [rbp+200h+SystemTime.wYear], xmm0
0x180026c0e  lea     rcx, [rbp+200h+SystemTime]; lpSystemTime
0x180026c12  call    cs:__imp_GetSystemTime
0x180026c18  xorps   xmm0, xmm0
0x180026c1b  movups  xmmword ptr [rbp+200h+var_280], xmm0
0x180026c1f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180026c27  movdqu  [rbp+200h+var_270], xmm1
0x180026c2c  mov     word ptr [rbp+200h+var_280], r15w
0x180026c31  lea     rdx, [rbp+200h+var_280]
0x180026c35  lea     rcx, [rbp+200h+SystemTime]
0x180026c39  call    ?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::wstring &)
0x180026c3e  mov     ebx, eax
0x180026c40  test    eax, eax
0x180026c42  jns     short loc_180026C4B
0x180026c44  mov     edx, 72h ; 'r'
0x180026c49  jmp     short loc_180026C73
0x180026c4b  lea     r8, [rbp+200h+var_280]
0x180026c4f  cmp     qword ptr [rbp+200h+var_270+8], 7
0x180026c54  cmova   r8, [rbp+200h+var_280]; unsigned __int16 *
0x180026c59  lea     rdx, aAutopilotcreat; "AutopilotCreationDate"
0x180026c60  mov     rcx, [rdi]; struct Windows::Data::Json::IJsonObject *
0x180026c63  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180026c68  mov     ebx, eax
0x180026c6a  test    eax, eax
0x180026c6c  jns     short loc_180026C8E
0x180026c6e  mov     edx, 73h ; 's'; void *
0x180026c73  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026c7a  mov     r9d, eax; char *
0x180026c7d  mov     rcx, [rbp+208h]; this
0x180026c84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026c89  jmp     loc_180026FD5
0x180026c8e  mov     [rsp+300h+hKey], r15
0x180026c93  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r15b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180026c9a  jz      short loc_180026CA4
0x180026c9c  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180026ca2  jmp     short loc_180026CBC
0x180026ca4  call    cs:__imp_RtlIsStateSeparationEnabled
0x180026caa  test    al, al
0x180026cac  setnz   al
0x180026caf  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180026cb5  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180026cbc  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x180026cc3  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x180026cca  test    al, al
0x180026ccc  cmovz   rdx, rcx; lpSubKey
0x180026cd0  lea     rax, [rsp+300h+hKey]
0x180026cd5  mov     [rsp+300h+phkResult], rax; int
0x180026cda  mov     r9d, 20019h; samDesired
0x180026ce0  xor     r8d, r8d; ulOptions
0x180026ce3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026cea  call    cs:__imp_RegOpenKeyExW
0x180026cf0  mov     ebx, eax
0x180026cf2  lea     ecx, [rax-2]
0x180026cf5  cmp     ecx, 1
0x180026cf8  jbe     loc_180026FE3
0x180026cfe  test    eax, eax
0x180026d00  jle     short loc_180026D0B
0x180026d02  movzx   ebx, ax
0x180026d05  or      ebx, 80070000h
0x180026d0b  test    ebx, ebx
0x180026d0d  jns     short loc_180026D43
0x180026d0f  mov     edx, 82h; void *
0x180026d14  mov     r9d, ebx; char *
0x180026d17  mov     rcx, [rbp+208h]; this
0x180026d1e  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d2a  mov     rcx, [rsp+300h+hKey]; hKey
0x180026d2f  test    rcx, rcx
0x180026d32  jz      loc_180026FD5
0x180026d38  call    cs:__imp_RegCloseKey
0x180026d3e  jmp     loc_180026FD5
0x180026d43  xor     edx, edx; Val
0x180026d45  mov     r8d, 206h; Size
0x180026d4b  lea     rcx, [rbp+200h+var_24E]; void *
0x180026d4f  call    memset_0
0x180026d54  mov     r14d, r15d
0x180026d57  mov     [rsp+300h+cchValueName], 104h
0x180026d5f  mov     [rbp+200h+ValueName], r15w
0x180026d64  mov     [rsp+300h+Type], r15d
0x180026d69  mov     [rsp+300h+lpcbData], r15; lpcbData
0x180026d6e  mov     [rsp+300h+lpData], r15; lpData
0x180026d73  lea     rax, [rsp+300h+Type]
0x180026d78  mov     [rsp+300h+lpType], rax; lpType
0x180026d7d  mov     [rsp+300h+phkResult], r15; lpReserved
0x180026d82  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x180026d87  lea     r8, [rbp+200h+ValueName]; lpValueName
0x180026d8b  mov     edx, r14d; dwIndex
0x180026d8e  mov     rcx, [rsp+300h+hKey]; hKey
0x180026d93  call    cs:__imp_RegEnumValueW
0x180026d99  mov     esi, eax
0x180026d9b  cmp     eax, 103h
0x180026da0  jz      loc_180026FC2
0x180026da6  test    eax, eax
0x180026da8  jg      short loc_180026DAE
0x180026daa  mov     ebx, eax
0x180026dac  jmp     short loc_180026DB7
0x180026dae  movzx   ebx, si
0x180026db1  or      ebx, 80070000h
0x180026db7  test    ebx, ebx
0x180026db9  js      loc_180026FB8
0x180026dbf  mov     eax, [rsp+300h+Type]
0x180026dc3  sub     eax, 1
0x180026dc6  jz      short loc_180026E3E
0x180026dc8  cmp     eax, 3
0x180026dcb  jnz     loc_180026F36
0x180026dd1  mov     [rsp+300h+pvData], r15d
0x180026dd6  mov     [rsp+300h+pcbData], 4
0x180026dde  lea     rax, [rsp+300h+pcbData]
0x180026de3  mov     [rsp+300h+lpData], rax; pcbData
0x180026de8  lea     rax, [rsp+300h+pvData]
0x180026ded  mov     [rsp+300h+lpType], rax; pvData
0x180026df2  mov     [rsp+300h+phkResult], r15; unsigned int
0x180026df7  mov     r9d, 10h; dwFlags
0x180026dfd  lea     r8, [rbp+200h+ValueName]; lpValue
0x180026e01  xor     edx, edx; lpSubKey
0x180026e03  mov     rcx, [rsp+300h+hKey]; hkey
0x180026e08  call    cs:__imp_RegGetValueW
0x180026e0e  test    eax, eax
0x180026e10  jnz     loc_180026F46
0x180026e16  mov     r8d, [rsp+300h+pvData]; unsigned int
0x180026e1b  lea     rdx, [rbp+200h+ValueName]; unsigned __int16 *
0x180026e1f  mov     rcx, [rdi]; struct Windows::Data::Json::IJsonObject *
0x180026e22  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x180026e27  mov     ebx, eax
0x180026e29  test    eax, eax
0x180026e2b  jns     loc_180026F36
0x180026e31  mov     r9d, eax
0x180026e34  mov     edx, 0B3h
0x180026e39  jmp     loc_180026D17
0x180026e3e  xorps   xmm0, xmm0
0x180026e41  movups  xmmword ptr [rsp+300h+hstringHeader.Reserved], xmm0
0x180026e46  mov     qword ptr [rsp+300h+hstringHeader.Reserved+10h], r15
0x180026e4b  mov     [rsp+300h+string], 7
0x180026e54  mov     word ptr [rsp+300h+hstringHeader.Reserved], r15w
0x180026e5a  mov     [rsp+300h+var_2B8], r15d
0x180026e5f  lea     rax, [rsp+300h+var_2B8]
0x180026e64  mov     [rsp+300h+lpData], rax; pcbData
0x180026e69  mov     [rsp+300h+lpType], r15; pvData
0x180026e6e  mov     [rsp+300h+phkResult], r15; unsigned int
0x180026e73  mov     ebx, 2
0x180026e78  mov     r9d, ebx; dwFlags
0x180026e7b  lea     r8, [rbp+200h+ValueName]; lpValue
0x180026e7f  xor     edx, edx; lpSubKey
0x180026e81  mov     rcx, [rsp+300h+hKey]; hkey
0x180026e86  call    cs:__imp_RegGetValueW
0x180026e8c  test    eax, eax
0x180026e8e  jnz     loc_180026F8C
0x180026e94  mov     edx, [rsp+300h+var_2B8]
0x180026e98  shr     rdx, 1
0x180026e9b  lea     rcx, [rsp+300h+hstringHeader]; Src
0x180026ea0  cmp     rdx, qword ptr [rsp+300h+hstringHeader.Reserved+10h]
0x180026ea5  ja      short loc_180026EBF
0x180026ea7  mov     qword ptr [rsp+300h+hstringHeader.Reserved+10h], rdx
0x180026eac  cmp     [rsp+300h+string], 7
0x180026eb2  cmova   rcx, qword ptr [rsp+300h+hstringHeader.Reserved]
0x180026eb8  mov     [rcx+rdx*2], r15w
0x180026ebd  jmp     short loc_180026ECC
0x180026ebf  xor     r8d, r8d
0x180026ec2  sub     rdx, qword ptr [rsp+300h+hstringHeader.Reserved+10h]
0x180026ec7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x180026ecc  lea     rax, [rsp+300h+hstringHeader]
0x180026ed1  cmp     [rsp+300h+string], 7
0x180026ed7  cmova   rax, qword ptr [rsp+300h+hstringHeader.Reserved]
0x180026edd  lea     rcx, [rsp+300h+var_2B8]
0x180026ee2  mov     [rsp+300h+lpData], rcx; pcbData
0x180026ee7  mov     [rsp+300h+lpType], rax; pvData
0x180026eec  mov     [rsp+300h+phkResult], r15; int
0x180026ef1  mov     r9d, ebx; dwFlags
0x180026ef4  lea     r8, [rbp+200h+ValueName]; lpValue
0x180026ef8  xor     edx, edx; lpSubKey
0x180026efa  mov     rcx, [rsp+300h+hKey]; hkey
0x180026eff  call    cs:__imp_RegGetValueW
0x180026f05  test    eax, eax
0x180026f07  jnz     short loc_180026F85
0x180026f09  lea     r8, [rsp+300h+hstringHeader]
0x180026f0e  cmp     [rsp+300h+string], 7
0x180026f14  cmova   r8, qword ptr [rsp+300h+hstringHeader.Reserved]; unsigned __int16 *
0x180026f1a  lea     rdx, [rbp+200h+ValueName]; unsigned __int16 *
0x180026f1e  mov     rcx, [rdi]; struct Windows::Data::Json::IJsonObject *
0x180026f21  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180026f26  mov     ebx, eax
0x180026f28  test    eax, eax
0x180026f2a  js      short loc_180026F68
0x180026f2c  lea     rcx, [rsp+300h+hstringHeader]
0x180026f31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026f36  test    esi, esi
0x180026f38  jnz     loc_180026FE3
0x180026f3e  inc     r14d
0x180026f41  jmp     loc_180026D57
0x180026f46  mov     rcx, [rbp+208h]; this
0x180026f4d  mov     r9d, eax; char *
0x180026f50  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026f57  mov     edx, 0B1h; void *
0x180026f5c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026f61  mov     ebx, eax
0x180026f63  jmp     loc_180026D2A
0x180026f68  mov     rcx, [rbp+208h]; this
0x180026f6f  mov     r9d, eax; char *
0x180026f72  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026f79  mov     edx, 0A9h; void *
0x180026f7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f83  jmp     short loc_180026FA9
0x180026f85  mov     edx, 0A7h
0x180026f8a  jmp     short loc_180026F91
0x180026f8c  mov     edx, 0A5h; void *
0x180026f91  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026f98  mov     r9d, eax; char *
0x180026f9b  mov     rcx, [rbp+208h]; this
0x180026fa2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026fa7  mov     ebx, eax
0x180026fa9  lea     rcx, [rsp+300h+hstringHeader]
0x180026fae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026fb3  jmp     loc_180026D2A
0x180026fb8  mov     edx, 9Dh
0x180026fbd  jmp     loc_180026D14
0x180026fc2  mov     rcx, [rsp+300h+hKey]; hKey
0x180026fc7  test    rcx, rcx
0x180026fca  jz      short loc_180026FD2
0x180026fcc  call    cs:__imp_RegCloseKey
0x180026fd2  mov     ebx, r15d
0x180026fd5  lea     rcx, [rbp+200h+var_280]
0x180026fd9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026fde  jmp     loc_180026C00
0x180026fe3  mov     rcx, [rsp+300h+hKey]; hKey
0x180026fe8  test    rcx, rcx
0x180026feb  jz      short loc_180026FF3
0x180026fed  call    cs:__imp_RegCloseKey
0x180026ff3  lea     rcx, [rbp+200h+var_280]
0x180026ff7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026ffc  xor     eax, eax
0x180026ffe  mov     rcx, [rbp+200h+var_40]
0x180027005  xor     rcx, rsp; StackCookie
0x180027008  call    __security_check_cookie
0x18002700d  add     rsp, 2D8h
0x180027014  pop     r15
0x180027016  pop     r14
0x180027018  pop     rdi
0x180027019  pop     rsi
0x18002701a  pop     rbx
0x18002701b  pop     rbp
0x18002701c  retn
0x18002701d  mov     ecx, eax; this
0x18002701f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
