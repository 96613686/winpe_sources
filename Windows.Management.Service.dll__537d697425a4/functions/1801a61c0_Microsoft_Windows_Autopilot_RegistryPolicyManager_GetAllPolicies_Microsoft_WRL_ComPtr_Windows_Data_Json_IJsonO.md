# Microsoft::Windows::Autopilot::RegistryPolicyManager::GetAllPolicies(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x1801a61c0`
- end: `0x1801a65e0`
- name: `?GetAllPolicies@RegistryPolicyManager@Autopilot@Windows@Microsoft@@UEBAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `1056`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067e54`
- `0x18006cb28`
- `0x180077de0`
- `0x180080984`
- `0x180080bac`
- `0x180084d80`
- `0x180086044`
- `0x180088144`
- `0x18008a454`
- `0x18008a9c4`
- `0x18008c9a8`
- `0x18008d6d8`
- `0x18008f570`
- `0x18008f6c0`
- `0x1801a61c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801a63a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1801a63a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a62fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a62fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a641d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a648d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a64e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a641d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a648d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801a64e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801a624a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801a624a`

## string_xrefs

- `0x1801a61fc`: `Windows.Data.Json.JsonObject`
- `0x1801a622a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1801a629f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1801a6338`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1801a6536`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1801a6558`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`
- `0x1801a6577`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`

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
0x1801a61c0  push    rbp
0x1801a61c2  push    rbx
0x1801a61c3  push    rsi
0x1801a61c4  push    rdi
0x1801a61c5  push    r14
0x1801a61c7  push    r15
0x1801a61c9  lea     rbp, [rsp-1D8h]
0x1801a61d1  sub     rsp, 2D8h
0x1801a61d8  mov     rax, cs:__security_cookie
0x1801a61df  xor     rax, rsp
0x1801a61e2  mov     [rbp+200h+var_40], rax
0x1801a61e9  mov     r14, rdx
0x1801a61ec  xor     r15d, r15d
0x1801a61ef  mov     [rsp+300h+var_288], r15
0x1801a61f4  lea     r9d, [r15+1Ch]; unsigned int
0x1801a61f8  lea     r8d, [r15+1Dh]; unsigned int
0x1801a61fc  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1801a6203  lea     rcx, [rsp+300h+hstringHeader]; hstringHeader
0x1801a6208  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801a620d  mov     rdx, r14
0x1801a6210  mov     rcx, [rsp+300h+var_288]
0x1801a6215  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1801a621a  mov     ebx, eax
0x1801a621c  test    eax, eax
0x1801a621e  jns     short loc_1801A623F
0x1801a6220  mov     rcx, [rbp+208h]; this
0x1801a6227  mov     r9d, eax; char *
0x1801a622a  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a6231  lea     edx, [r15+6Ch]; void *
0x1801a6235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a623a  jmp     loc_1801A65BE
0x1801a623f  xorps   xmm0, xmm0
0x1801a6242  movups  xmmword ptr [rbp+200h+SystemTime.wYear], xmm0
0x1801a6246  lea     rcx, [rbp+200h+SystemTime]; lpSystemTime
0x1801a624a  call    cs:__imp_GetSystemTime
0x1801a6251  nop     dword ptr [rax+rax+00h]
0x1801a6256  lea     rcx, [rbp+200h+var_270]
0x1801a625a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801a625f  lea     rdx, [rbp+200h+var_270]
0x1801a6263  lea     rcx, [rbp+200h+SystemTime]
0x1801a6267  call    ?SystemTimeToISO8601String@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEBU_SYSTEMTIME@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::SystemTimeToISO8601String(_SYSTEMTIME const &,std::wstring &)
0x1801a626c  mov     ebx, eax
0x1801a626e  test    eax, eax
0x1801a6270  jns     short loc_1801A6279
0x1801a6272  mov     edx, 72h ; 'r'
0x1801a6277  jmp     short loc_1801A629F
0x1801a6279  lea     rcx, [rbp+200h+var_270]
0x1801a627d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a6282  mov     r8, rax; unsigned __int16 *
0x1801a6285  lea     rdx, aAutopilotcreat; "AutopilotCreationDate"
0x1801a628c  mov     rcx, [r14]; struct Windows::Data::Json::IJsonObject *
0x1801a628f  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1801a6294  mov     ebx, eax
0x1801a6296  test    eax, eax
0x1801a6298  jns     short loc_1801A62BA
0x1801a629a  mov     edx, 73h ; 's'; void *
0x1801a629f  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a62a6  mov     r9d, eax; char *
0x1801a62a9  mov     rcx, [rbp+208h]; this
0x1801a62b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a62b5  jmp     loc_1801A65B5
0x1801a62ba  mov     [rsp+300h+hKey], r15
0x1801a62bf  xor     edx, edx
0x1801a62c1  lea     rcx, [rsp+300h+hKey]
0x1801a62c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801a62cb  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1801a62d0  lea     rcx, aSoftwareMicros_16; "Software\\Microsoft\\Provisioning\\Auto"...
0x1801a62d7  lea     rdx, SubKey; "OSData\\Software\\Microsoft\\Provisioni"...
0x1801a62de  test    al, al
0x1801a62e0  cmovz   rdx, rcx; lpSubKey
0x1801a62e4  lea     rax, [rsp+300h+hKey]
0x1801a62e9  mov     [rsp+300h+phkResult], rax; int
0x1801a62ee  mov     r9d, 20019h; samDesired
0x1801a62f4  xor     r8d, r8d; ulOptions
0x1801a62f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a62fe  call    cs:__imp_RegOpenKeyExW
0x1801a6305  nop     dword ptr [rax+rax+00h]
0x1801a630a  mov     ebx, eax
0x1801a630c  lea     ecx, [rax-2]
0x1801a630f  cmp     ecx, 1
0x1801a6312  jbe     loc_1801A65A8
0x1801a6318  test    eax, eax
0x1801a631a  jle     short loc_1801A6325
0x1801a631c  movzx   ebx, ax
0x1801a631f  or      ebx, 80070000h
0x1801a6325  test    ebx, ebx
0x1801a6327  jns     short loc_1801A6353
0x1801a6329  mov     edx, 82h; void *
0x1801a632e  mov     r9d, ebx; char *
0x1801a6331  mov     rcx, [rbp+208h]; this
0x1801a6338  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a633f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a6344  lea     rcx, [rsp+300h+hKey]
0x1801a6349  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801a634e  jmp     loc_1801A65B5
0x1801a6353  xor     edx, edx; Val
0x1801a6355  mov     r8d, 206h; Size
0x1801a635b  lea     rcx, [rbp+200h+var_24E]; void *
0x1801a635f  call    memset_0
0x1801a6364  mov     esi, r15d
0x1801a6367  mov     [rsp+300h+cchValueName], 104h
0x1801a636f  mov     [rbp+200h+ValueName], r15w
0x1801a6374  mov     [rsp+300h+Type], r15d
0x1801a6379  mov     [rsp+300h+lpcbData], r15; lpcbData
0x1801a637e  mov     [rsp+300h+lpData], r15; lpData
0x1801a6383  lea     rax, [rsp+300h+Type]
0x1801a6388  mov     [rsp+300h+lpType], rax; lpType
0x1801a638d  mov     [rsp+300h+phkResult], r15; lpReserved
0x1801a6392  lea     r9, [rsp+300h+cchValueName]; lpcchValueName
0x1801a6397  lea     r8, [rbp+200h+ValueName]; lpValueName
0x1801a639b  mov     edx, esi; dwIndex
0x1801a639d  mov     rcx, [rsp+300h+hKey]; hKey
0x1801a63a2  call    cs:__imp_RegEnumValueW
0x1801a63a9  nop     dword ptr [rax+rax+00h]
0x1801a63ae  mov     edi, eax
0x1801a63b0  cmp     eax, 103h
0x1801a63b5  jz      loc_1801A65A8
0x1801a63bb  test    eax, eax
0x1801a63bd  jg      short loc_1801A63C3
0x1801a63bf  mov     ebx, eax
0x1801a63c1  jmp     short loc_1801A63CC
0x1801a63c3  movzx   ebx, di
0x1801a63c6  or      ebx, 80070000h
0x1801a63cc  test    ebx, ebx
0x1801a63ce  js      loc_1801A659E
0x1801a63d4  mov     eax, [rsp+300h+Type]
0x1801a63d8  sub     eax, 1
0x1801a63db  jz      short loc_1801A6459
0x1801a63dd  cmp     eax, 3
0x1801a63e0  jnz     loc_1801A651D
0x1801a63e6  mov     [rsp+300h+pvData], r15d
0x1801a63eb  mov     [rsp+300h+pcbData], 4
0x1801a63f3  lea     rax, [rsp+300h+pcbData]
0x1801a63f8  mov     [rsp+300h+lpData], rax; pcbData
0x1801a63fd  lea     rax, [rsp+300h+pvData]
0x1801a6402  mov     [rsp+300h+lpType], rax; pvData
0x1801a6407  mov     [rsp+300h+phkResult], r15; unsigned int
0x1801a640c  mov     r9d, 10h; dwFlags
0x1801a6412  lea     r8, [rbp+200h+ValueName]; lpValue
0x1801a6416  xor     edx, edx; lpSubKey
0x1801a6418  mov     rcx, [rsp+300h+hKey]; hkey
0x1801a641d  call    cs:__imp_RegGetValueW
0x1801a6424  nop     dword ptr [rax+rax+00h]
0x1801a6429  test    eax, eax
0x1801a642b  jnz     loc_1801A652C
0x1801a6431  mov     r8d, [rsp+300h+pvData]; unsigned int
0x1801a6436  lea     rdx, [rbp+200h+ValueName]; unsigned __int16 *
0x1801a643a  mov     rcx, [r14]; struct Windows::Data::Json::IJsonObject *
0x1801a643d  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x1801a6442  mov     ebx, eax
0x1801a6444  test    eax, eax
0x1801a6446  jns     loc_1801A651D
0x1801a644c  mov     r9d, eax
0x1801a644f  mov     edx, 0B3h
0x1801a6454  jmp     loc_1801A6331
0x1801a6459  lea     rcx, [rsp+300h+hstringHeader]
0x1801a645e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801a6463  mov     [rsp+300h+var_2B8], r15d
0x1801a6468  lea     rax, [rsp+300h+var_2B8]
0x1801a646d  mov     [rsp+300h+lpData], rax; pcbData
0x1801a6472  mov     [rsp+300h+lpType], r15; pvData
0x1801a6477  mov     [rsp+300h+phkResult], r15; unsigned int
0x1801a647c  mov     r9d, 2; dwFlags
0x1801a6482  lea     r8, [rbp+200h+ValueName]; lpValue
0x1801a6486  xor     edx, edx; lpSubKey
0x1801a6488  mov     rcx, [rsp+300h+hKey]; hkey
0x1801a648d  call    cs:__imp_RegGetValueW
0x1801a6494  nop     dword ptr [rax+rax+00h]
0x1801a6499  test    eax, eax
0x1801a649b  jnz     loc_1801A6572
0x1801a64a1  xor     r8d, r8d
0x1801a64a4  mov     edx, [rsp+300h+var_2B8]
0x1801a64a8  shr     rdx, 1
0x1801a64ab  lea     rcx, [rsp+300h+hstringHeader]
0x1801a64b0  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1801a64b5  lea     rcx, [rsp+300h+hstringHeader]
0x1801a64ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a64bf  lea     rcx, [rsp+300h+var_2B8]
0x1801a64c4  mov     [rsp+300h+lpData], rcx; pcbData
0x1801a64c9  mov     [rsp+300h+lpType], rax; pvData
0x1801a64ce  mov     [rsp+300h+phkResult], r15; int
0x1801a64d3  mov     r9d, 2; dwFlags
0x1801a64d9  lea     r8, [rbp+200h+ValueName]; lpValue
0x1801a64dd  xor     edx, edx; lpSubKey
0x1801a64df  mov     rcx, [rsp+300h+hKey]; hkey
0x1801a64e4  call    cs:__imp_RegGetValueW
0x1801a64eb  nop     dword ptr [rax+rax+00h]
0x1801a64f0  test    eax, eax
0x1801a64f2  jnz     short loc_1801A656B
0x1801a64f4  lea     rcx, [rsp+300h+hstringHeader]
0x1801a64f9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801a64fe  mov     r8, rax; unsigned __int16 *
0x1801a6501  lea     rdx, [rbp+200h+ValueName]; unsigned __int16 *
0x1801a6505  mov     rcx, [r14]; struct Windows::Data::Json::IJsonObject *
0x1801a6508  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x1801a650d  mov     ebx, eax
0x1801a650f  test    eax, eax
0x1801a6511  js      short loc_1801A654E
0x1801a6513  lea     rcx, [rsp+300h+hstringHeader]
0x1801a6518  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a651d  test    edi, edi
0x1801a651f  jnz     loc_1801A65A8
0x1801a6525  inc     esi
0x1801a6527  jmp     loc_1801A6367
0x1801a652c  mov     rcx, [rbp+208h]; this
0x1801a6533  mov     r9d, eax; char *
0x1801a6536  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a653d  mov     edx, 0B1h; void *
0x1801a6542  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801a6547  mov     ebx, eax
0x1801a6549  jmp     loc_1801A6344
0x1801a654e  mov     rcx, [rbp+208h]; this
0x1801a6555  mov     r9d, eax; char *
0x1801a6558  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a655f  mov     edx, 0A9h; void *
0x1801a6564  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a6569  jmp     short loc_1801A658F
0x1801a656b  mov     edx, 0A7h
0x1801a6570  jmp     short loc_1801A6577
0x1801a6572  mov     edx, 0A5h; void *
0x1801a6577  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a657e  mov     r9d, eax; char *
0x1801a6581  mov     rcx, [rbp+208h]; this
0x1801a6588  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801a658d  mov     ebx, eax
0x1801a658f  lea     rcx, [rsp+300h+hstringHeader]
0x1801a6594  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a6599  jmp     loc_1801A6344
0x1801a659e  mov     edx, 9Dh
0x1801a65a3  jmp     loc_1801A632E
0x1801a65a8  lea     rcx, [rsp+300h+hKey]
0x1801a65ad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801a65b2  mov     ebx, r15d
0x1801a65b5  lea     rcx, [rbp+200h+var_270]
0x1801a65b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a65be  mov     eax, ebx
0x1801a65c0  mov     rcx, [rbp+200h+var_40]
0x1801a65c7  xor     rcx, rsp; StackCookie
0x1801a65ca  call    __security_check_cookie
0x1801a65cf  add     rsp, 2D8h
0x1801a65d6  pop     r15
0x1801a65d8  pop     r14
0x1801a65da  pop     rdi
0x1801a65db  pop     rsi
0x1801a65dc  pop     rbx
0x1801a65dd  pop     rbp
0x1801a65de  retn
```
