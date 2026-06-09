# Microsoft::Windows::Autopilot::RegistryPolicyManager::GetAllPolicies(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x180027b00`
- end: `0x180028008`
- name: `?GetAllPolicies@RegistryPolicyManager@Autopilot@Windows@Microsoft@@UEBAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `1288`
- prototype: `__int64 __fastcall(__int64, struct Windows::Data::Json::IJsonObject **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x18000ed44`
- `0x180010764`
- `0x180016b80`
- `0x180017a20`
- `0x180017b2c`
- `0x180018678`
- `0x18001f030`
- `0x18001f28c`
- `0x1800218f0`
- `0x180027b00`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027dcc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027e50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027ecf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027dcc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027e50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027ecf`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027d51`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027d51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027c9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027c9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027cf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027fa2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027fc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027cf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027fa2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027fc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027b49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027b49`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180027bb8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180027bb8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027c50`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027c50`

## string_xrefs

- `0x180027b42`: `Windows.Data.Json.JsonObject`
- `0x180027b95`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x180027c1f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x180027cd6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x180027f26`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x180027f48`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x180027f67`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
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
    JUMPOUT(0x180028007LL);
  }
  v6 = string;
  v7 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v8 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)v6, a2);
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
    std::wstring::_Tidy_deallocate((char **)v44);
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
            std::wstring::_Tidy_deallocate((char **)&hstringHeader);
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
          std::wstring::_Tidy_deallocate((char **)&hstringHeader);
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
          v25 = Microsoft::Windows::Autopilot::JsonHelpers::Append(*a2, &ValueName);
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
  std::wstring::_Tidy_deallocate((char **)v44);
  return 0;
}

```

## disassembly

```asm
0x180027b00  push    rbp
0x180027b02  push    rbx
0x180027b03  push    rsi
0x180027b04  push    rdi
0x180027b05  push    r14
0x180027b07  push    r15
0x180027b09  lea     rbp, [rsp-1D8h]
0x180027b11  sub     rsp, 2D8h
0x180027b18  mov     rax, cs:__security_cookie
0x180027b1f  xor     rax, rsp
0x180027b22  mov     [rbp+200h+var_40], rax
0x180027b29  mov     rdi, rdx
0x180027b2c  xor     r15d, r15d
0x180027b2f  mov     [rsp+300h+string], r15
0x180027b34  lea     r9, [rsp+300h+string]; string
0x180027b39  lea     r8, [rsp+300h+hstringHeader]; hstringHeader
0x180027b3e  lea     edx, [r15+1Ch]; length
0x180027b42  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180027b49  call    cs:__imp_WindowsCreateStringReference
0x180027b50  nop     dword ptr [rax+rax+00h]
0x180027b55  test    eax, eax
0x180027b57  js      loc_180028000
0x180027b5d  mov     rbx, [rsp+300h+string]
0x180027b62  mov     rcx, [rdi]
0x180027b65  test    rcx, rcx
0x180027b68  jz      short loc_180027B7A
0x180027b6a  mov     [rdi], r15
0x180027b6d  mov     rax, [rcx]
0x180027b70  mov     rax, [rax+10h]
0x180027b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b79  nop
0x180027b7a  mov     rdx, rdi
0x180027b7d  mov     rcx, rbx
0x180027b80  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180027b85  mov     ebx, eax
0x180027b87  test    eax, eax
0x180027b89  jns     short loc_180027BAD
0x180027b8b  mov     rcx, [rbp+208h]; this
0x180027b92  mov     r9d, eax; char *
0x180027b95  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027b9c  mov     edx, 6Ch ; 'l'; void *
0x180027ba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ba6  mov     eax, ebx
0x180027ba8  jmp     loc_180027FE0
0x180027bad  xorps   xmm0, xmm0
0x180027bb0  movups  xmmword ptr [rbp+200h+SystemTime.wYear], xmm0
0x180027bb4  lea     rcx, [rbp+200h+SystemTime]; lpSystemTime
0x180027bb8  call    cs:__imp_GetSystemTime
0x180027bbf  nop     dword ptr [rax+rax+00h]
0x180027bc4  xorps   xmm0, xmm0
0x180027bc7  movups  xmmword ptr [rbp+200h+var_280], xmm0
0x180027bcb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180027bd3  movdqu  [rbp+200h+var_270], xmm1
0x180027bd8  mov     word ptr [rbp+200h+var_280], r15w
0x180027bdd  lea     rdx, [rbp+200h+var_280]
0x180027be1  lea     rcx, [rbp+200h+SystemTime]
0x180027be5  call    ?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::wstring &)
0x180027bea  mov     ebx, eax
0x180027bec  test    eax, eax
0x180027bee  jns     short loc_180027BF7
0x180027bf0  mov     edx, 72h ; 'r'
0x180027bf5  jmp     short loc_180027C1F
0x180027bf7  lea     r8, [rbp+200h+var_280]
0x180027bfb  cmp     qword ptr [rbp+200h+var_270+8], 7
0x180027c00  cmova   r8, [rbp+200h+var_280]; unsigned __int16 *
0x180027c05  lea     rdx, aAutopilotcreat; "AutopilotCreationDate"
0x180027c0c  mov     rcx, [rdi]; struct Windows::Data::Json::IJsonObject *
0x180027c0f  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180027c14  mov     ebx, eax
0x180027c16  test    eax, eax
0x180027c18  jns     short loc_180027C3A
0x180027c1a  mov     edx, 73h ; 's'; void *
0x180027c1f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027c26  mov     r9d, eax; char *
0x180027c29  mov     rcx, [rbp+208h]; this
0x180027c30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c35  jmp     loc_180027FB1
0x180027c3a  mov     [rsp+300h+hKey], r15
0x180027c3f  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r15b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180027c46  jz      short loc_180027C50
0x180027c48  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180027c4e  jmp     short loc_180027C6E
0x180027c50  call    cs:__imp_RtlIsStateSeparationEnabled
0x180027c57  nop     dword ptr [rax+rax+00h]
0x180027c5c  test    al, al
0x180027c5e  setnz   al
0x180027c61  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180027c67  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180027c6e  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x180027c75  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x180027c7c  test    al, al
0x180027c7e  cmovz   rdx, rcx; lpSubKey
0x180027c82  lea     rax, [rsp+300h+hKey]
0x180027c87  mov     [rsp+300h+phkResult], rax; int
0x180027c8c  mov     r9d, 20019h; samDesired
0x180027c92  xor     r8d, r8d; ulOptions
0x180027c95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027c9c  call    cs:__imp_RegOpenKeyExW
0x180027ca3  nop     dword ptr [rax+rax+00h]
0x180027ca8  mov     ebx, eax
0x180027caa  lea     ecx, [rax-2]
0x180027cad  cmp     ecx, 1
0x180027cb0  jbe     loc_180027FBF
0x180027cb6  test    eax, eax
0x180027cb8  jle     short loc_180027CC3
0x180027cba  movzx   ebx, ax
0x180027cbd  or      ebx, 80070000h
0x180027cc3  test    ebx, ebx
0x180027cc5  jns     short loc_180027D01
0x180027cc7  mov     edx, 82h; void *
0x180027ccc  mov     r9d, ebx; char *
0x180027ccf  mov     rcx, [rbp+208h]; this
0x180027cd6  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027cdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ce2  mov     rcx, [rsp+300h+hKey]; hKey
0x180027ce7  test    rcx, rcx
0x180027cea  jz      loc_180027FB1
0x180027cf0  call    cs:__imp_RegCloseKey
0x180027cf7  nop     dword ptr [rax+rax+00h]
0x180027cfc  jmp     loc_180027FB1
0x180027d01  xor     edx, edx; Val
0x180027d03  mov     r8d, 206h; Size
0x180027d09  lea     rcx, [rbp+200h+var_24E]; void *
0x180027d0d  call    memset_0
0x180027d12  mov     r14d, r15d
0x180027d15  mov     [rsp+300h+cchValueName], 104h
0x180027d1d  mov     [rbp+200h+ValueName], r15w
0x180027d22  mov     [rsp+300h+Type], r15d
0x180027d27  mov     [rsp+300h+lpcbData], r15; lpcbData
0x180027d2c  mov     [rsp+300h+lpData], r15; lpData
0x180027d31  lea     rax, [rsp+300h+Type]
0x180027d36  mov     [rsp+300h+lpType], rax; lpType
0x180027d3b  mov     [rsp+300h+phkResult], r15; lpReserved
0x180027d40  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x180027d45  lea     r8, [rbp+200h+ValueName]; lpValueName
0x180027d49  mov     edx, r14d; dwIndex
0x180027d4c  mov     rcx, [rsp+300h+hKey]; hKey
0x180027d51  call    cs:__imp_RegEnumValueW
0x180027d58  nop     dword ptr [rax+rax+00h]
0x180027d5d  mov     esi, eax
0x180027d5f  cmp     eax, 103h
0x180027d64  jz      loc_180027F98
0x180027d6a  test    eax, eax
0x180027d6c  jg      short loc_180027D72
0x180027d6e  mov     ebx, eax
0x180027d70  jmp     short loc_180027D7B
0x180027d72  movzx   ebx, si
0x180027d75  or      ebx, 80070000h
0x180027d7b  test    ebx, ebx
0x180027d7d  js      loc_180027F8E
0x180027d83  mov     eax, [rsp+300h+Type]
0x180027d87  sub     eax, 1
0x180027d8a  jz      short loc_180027E08
0x180027d8c  cmp     eax, 3
0x180027d8f  jnz     loc_180027F0C
0x180027d95  mov     [rsp+300h+pvData], r15d
0x180027d9a  mov     [rsp+300h+pcbData], 4
0x180027da2  lea     rax, [rsp+300h+pcbData]
0x180027da7  mov     [rsp+300h+lpData], rax; pcbData
0x180027dac  lea     rax, [rsp+300h+pvData]
0x180027db1  mov     [rsp+300h+lpType], rax; pvData
0x180027db6  mov     [rsp+300h+phkResult], r15; unsigned int
0x180027dbb  mov     r9d, 10h; dwFlags
0x180027dc1  lea     r8, [rbp+200h+ValueName]; lpValue
0x180027dc5  xor     edx, edx; lpSubKey
0x180027dc7  mov     rcx, [rsp+300h+hKey]; hkey
0x180027dcc  call    cs:__imp_RegGetValueW
0x180027dd3  nop     dword ptr [rax+rax+00h]
0x180027dd8  test    eax, eax
0x180027dda  jnz     loc_180027F1C
0x180027de0  mov     r8d, [rsp+300h+pvData]; unsigned int
0x180027de5  lea     rdx, [rbp+200h+ValueName]; unsigned __int16 *
0x180027de9  mov     rcx, [rdi]; struct Windows::Data::Json::IJsonObject *
0x180027dec  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x180027df1  mov     ebx, eax
0x180027df3  test    eax, eax
0x180027df5  jns     loc_180027F0C
0x180027dfb  mov     r9d, eax
0x180027dfe  mov     edx, 0B3h
0x180027e03  jmp     loc_180027CCF
0x180027e08  xorps   xmm0, xmm0
0x180027e0b  movups  xmmword ptr [rsp+300h+hstringHeader.Reserved], xmm0
0x180027e10  mov     qword ptr [rsp+300h+hstringHeader.Reserved+10h], r15
0x180027e15  mov     [rsp+300h+string], 7
0x180027e1e  mov     word ptr [rsp+300h+hstringHeader.Reserved], r15w
0x180027e24  mov     [rsp+300h+var_2B8], r15d
0x180027e29  lea     rax, [rsp+300h+var_2B8]
0x180027e2e  mov     [rsp+300h+lpData], rax; pcbData
0x180027e33  mov     [rsp+300h+lpType], r15; pvData
0x180027e38  mov     [rsp+300h+phkResult], r15; unsigned int
0x180027e3d  mov     ebx, 2
0x180027e42  mov     r9d, ebx; dwFlags
0x180027e45  lea     r8, [rbp+200h+ValueName]; lpValue
0x180027e49  xor     edx, edx; lpSubKey
0x180027e4b  mov     rcx, [rsp+300h+hKey]; hkey
0x180027e50  call    cs:__imp_RegGetValueW
0x180027e57  nop     dword ptr [rax+rax+00h]
0x180027e5c  test    eax, eax
0x180027e5e  jnz     loc_180027F62
0x180027e64  mov     edx, [rsp+300h+var_2B8]
0x180027e68  shr     rdx, 1
0x180027e6b  lea     rcx, [rsp+300h+hstringHeader]; Src
0x180027e70  cmp     rdx, qword ptr [rsp+300h+hstringHeader.Reserved+10h]
0x180027e75  ja      short loc_180027E8F
0x180027e77  mov     qword ptr [rsp+300h+hstringHeader.Reserved+10h], rdx
0x180027e7c  cmp     [rsp+300h+string], 7
0x180027e82  cmova   rcx, qword ptr [rsp+300h+hstringHeader.Reserved]
0x180027e88  mov     [rcx+rdx*2], r15w
0x180027e8d  jmp     short loc_180027E9C
0x180027e8f  xor     r8d, r8d
0x180027e92  sub     rdx, qword ptr [rsp+300h+hstringHeader.Reserved+10h]
0x180027e97  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x180027e9c  lea     rax, [rsp+300h+hstringHeader]
0x180027ea1  cmp     [rsp+300h+string], 7
0x180027ea7  cmova   rax, qword ptr [rsp+300h+hstringHeader.Reserved]
0x180027ead  lea     rcx, [rsp+300h+var_2B8]
0x180027eb2  mov     [rsp+300h+lpData], rcx; pcbData
0x180027eb7  mov     [rsp+300h+lpType], rax; pvData
0x180027ebc  mov     [rsp+300h+phkResult], r15; int
0x180027ec1  mov     r9d, ebx; dwFlags
0x180027ec4  lea     r8, [rbp+200h+ValueName]; lpValue
0x180027ec8  xor     edx, edx; lpSubKey
0x180027eca  mov     rcx, [rsp+300h+hKey]; hkey
0x180027ecf  call    cs:__imp_RegGetValueW
0x180027ed6  nop     dword ptr [rax+rax+00h]
0x180027edb  test    eax, eax
0x180027edd  jnz     short loc_180027F5B
0x180027edf  lea     r8, [rsp+300h+hstringHeader]
0x180027ee4  cmp     [rsp+300h+string], 7
0x180027eea  cmova   r8, qword ptr [rsp+300h+hstringHeader.Reserved]; unsigned __int16 *
0x180027ef0  lea     rdx, [rbp+200h+ValueName]; unsigned __int16 *
0x180027ef4  mov     rcx, [rdi]; struct Windows::Data::Json::IJsonObject *
0x180027ef7  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180027efc  mov     ebx, eax
0x180027efe  test    eax, eax
0x180027f00  js      short loc_180027F3E
0x180027f02  lea     rcx, [rsp+300h+hstringHeader]
0x180027f07  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027f0c  test    esi, esi
0x180027f0e  jnz     loc_180027FBF
0x180027f14  inc     r14d
0x180027f17  jmp     loc_180027D15
0x180027f1c  mov     rcx, [rbp+208h]; this
0x180027f23  mov     r9d, eax; char *
0x180027f26  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027f2d  mov     edx, 0B1h; void *
0x180027f32  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180027f37  mov     ebx, eax
0x180027f39  jmp     loc_180027CE2
0x180027f3e  mov     rcx, [rbp+208h]; this
0x180027f45  mov     r9d, eax; char *
0x180027f48  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027f4f  mov     edx, 0A9h; void *
0x180027f54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027f59  jmp     short loc_180027F7F
0x180027f5b  mov     edx, 0A7h
0x180027f60  jmp     short loc_180027F67
0x180027f62  mov     edx, 0A5h; void *
0x180027f67  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027f6e  mov     r9d, eax; char *
0x180027f71  mov     rcx, [rbp+208h]; this
0x180027f78  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180027f7d  mov     ebx, eax
0x180027f7f  lea     rcx, [rsp+300h+hstringHeader]
0x180027f84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027f89  jmp     loc_180027CE2
0x180027f8e  mov     edx, 9Dh
0x180027f93  jmp     loc_180027CCC
0x180027f98  mov     rcx, [rsp+300h+hKey]; hKey
0x180027f9d  test    rcx, rcx
0x180027fa0  jz      short loc_180027FAE
0x180027fa2  call    cs:__imp_RegCloseKey
0x180027fa9  nop     dword ptr [rax+rax+00h]
0x180027fae  mov     ebx, r15d
0x180027fb1  lea     rcx, [rbp+200h+var_280]
0x180027fb5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027fba  jmp     loc_180027BA6
0x180027fbf  mov     rcx, [rsp+300h+hKey]; hKey
0x180027fc4  test    rcx, rcx
0x180027fc7  jz      short loc_180027FD5
0x180027fc9  call    cs:__imp_RegCloseKey
0x180027fd0  nop     dword ptr [rax+rax+00h]
0x180027fd5  lea     rcx, [rbp+200h+var_280]
0x180027fd9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027fde  xor     eax, eax
0x180027fe0  mov     rcx, [rbp+200h+var_40]
0x180027fe7  xor     rcx, rsp; StackCookie
0x180027fea  call    __security_check_cookie
0x180027fef  add     rsp, 2D8h
0x180027ff6  pop     r15
0x180027ff8  pop     r14
0x180027ffa  pop     rdi
0x180027ffb  pop     rsi
0x180027ffc  pop     rbx
0x180027ffd  pop     rbp
0x180027ffe  retn
0x180028000  mov     ecx, eax; this
0x180028002  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
