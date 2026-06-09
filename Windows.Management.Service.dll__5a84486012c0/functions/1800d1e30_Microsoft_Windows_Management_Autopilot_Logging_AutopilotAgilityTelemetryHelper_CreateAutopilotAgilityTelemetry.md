# Microsoft::Windows::Management::Autopilot::Logging::AutopilotAgilityTelemetryHelper::CreateAutopilotAgilityTelemetryFlagRegkey(void)

- ea: `0x1800d1e30`
- end: `0x1800d1f96`
- name: `?CreateAutopilotAgilityTelemetryFlagRegkey@AutopilotAgilityTelemetryHelper@Logging@Autopilot@Management@Windows@Microsoft@@SAJXZ`
- size: `358`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d365c`

## callees

- `0x180067a54`
- `0x18007ff90`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x1800d1e30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d1f4c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d1f4c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d1ef9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d1ef9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d1e8f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d1e8f`

## pseudocode

```c
LSTATUS Microsoft::Windows::Management::Autopilot::Logging::AutopilotAgilityTelemetryHelper::CreateAutopilotAgilityTelemetryFlagRegkey(
        void)
{
  bool v0; // al
  const WCHAR *v1; // rbx
  const WCHAR *v2; // rdx
  LSTATUS result; // eax
  unsigned int v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-38h]
  int pdwTypea; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD pcbData; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  pcbData = 0;
  v0 = ZTPIsStateSeparationEnabled();
  v1 = (const WCHAR *)&stru_180228C20;
  v2 = (const WCHAR *)&stru_180228C20;
  if ( !v0 )
    v2 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
  result = RegGetValueW(HKEY_LOCAL_MACHINE, v2, L"DisableAutopilotAgilityProductVersionTelemetry", 2u, 0, 0, &pcbData);
  if ( result )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    if ( !ZTPIsStateSeparationEnabled() )
      v1 = L"Software\\Microsoft\\Provisioning\\AutopilotSettings";
    v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v4 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x97,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotAgilityTelemetryHelpers.h",
             (const char *)v4,
             pdwType);
    }
    else
    {
      Data = 1;
      v6 = RegSetValueExW(hKey, L"DisableAutopilotAgilityProductVersionTelemetry", 0, 4u, (const BYTE *)&Data, 4u);
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v5 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9A,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotAgilityTelemetryHelpers.h",
          (const char *)(unsigned int)v5,
          pdwTypea);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800d1e30  mov     [rsp+arg_18], rbx
0x1800d1e35  push    r14
0x1800d1e37  sub     rsp, 50h
0x1800d1e3b  mov     [rsp+58h+arg_0], 0
0x1800d1e43  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800d1e48  test    al, al
0x1800d1e4a  lea     rbx, stru_180228C20
0x1800d1e51  lea     rax, [rsp+58h+arg_0]
0x1800d1e56  mov     rdx, rbx
0x1800d1e59  mov     [rsp+58h+pcbData], rax; pcbData
0x1800d1e5e  lea     r14, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800d1e65  mov     [rsp+58h+pvData], 0; pvData
0x1800d1e6e  lea     r8, aDisableautopil; "DisableAutopilotAgilityProductVersionTe"...
0x1800d1e75  cmovz   rdx, r14; lpSubKey
0x1800d1e79  mov     [rsp+58h+pdwType], 0; pdwType
0x1800d1e82  mov     r9d, 2; dwFlags
0x1800d1e88  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800d1e8f  call    cs:__imp_RegGetValueW
0x1800d1e95  test    eax, eax
0x1800d1e97  jz      loc_1800D1F8A
0x1800d1e9d  xor     edx, edx
0x1800d1e9f  mov     [rsp+58h+hKey], 0
0x1800d1ea8  lea     rcx, [rsp+58h+hKey]
0x1800d1ead  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d1eb2  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800d1eb7  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800d1ec0  test    al, al
0x1800d1ec2  lea     rax, [rsp+58h+hKey]
0x1800d1ec7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d1ece  cmovz   rbx, r14
0x1800d1ed2  mov     [rsp+58h+phkResult], rax; phkResult
0x1800d1ed7  mov     [rsp+58h+pcbData], 0; lpSecurityAttributes
0x1800d1ee0  mov     rdx, rbx; lpSubKey
0x1800d1ee3  mov     dword ptr [rsp+58h+pvData], 2; samDesired
0x1800d1eeb  xor     r9d, r9d; lpClass
0x1800d1eee  xor     r8d, r8d; Reserved
0x1800d1ef1  mov     dword ptr [rsp+58h+pdwType], 0; unsigned int
0x1800d1ef9  call    cs:__imp_RegCreateKeyExW
0x1800d1eff  test    eax, eax
0x1800d1f01  jz      short loc_1800D1F20
0x1800d1f03  mov     rcx, [rsp+58h]; this
0x1800d1f08  lea     r8, aOnecoreuapAdmi_143; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d1f0f  mov     r9d, eax; char *
0x1800d1f12  mov     edx, 97h; void *
0x1800d1f17  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d1f1c  mov     ebx, eax
0x1800d1f1e  jmp     short loc_1800D1F7E
0x1800d1f20  mov     rcx, [rsp+58h+hKey]; hKey
0x1800d1f25  lea     rax, [rsp+58h+Data]
0x1800d1f2a  mov     r9d, 4; dwType
0x1800d1f30  mov     [rsp+58h+Data], 1
0x1800d1f38  mov     dword ptr [rsp+58h+pvData], r9d; cbData
0x1800d1f3d  lea     rdx, aDisableautopil; "DisableAutopilotAgilityProductVersionTe"...
0x1800d1f44  xor     r8d, r8d; Reserved
0x1800d1f47  mov     [rsp+58h+pdwType], rax; int
0x1800d1f4c  call    cs:__imp_RegSetValueExW
0x1800d1f52  mov     ebx, eax
0x1800d1f54  test    eax, eax
0x1800d1f56  jle     short loc_1800D1F61
0x1800d1f58  movzx   ebx, ax
0x1800d1f5b  or      ebx, 80070000h
0x1800d1f61  test    ebx, ebx
0x1800d1f63  jns     short loc_1800D1F7E
0x1800d1f65  mov     rcx, [rsp+58h]; this
0x1800d1f6a  lea     r8, aOnecoreuapAdmi_143; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d1f71  mov     r9d, ebx; char *
0x1800d1f74  mov     edx, 9Ah; void *
0x1800d1f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1f7e  lea     rcx, [rsp+58h+hKey]
0x1800d1f83  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d1f88  mov     eax, ebx
0x1800d1f8a  mov     rbx, [rsp+58h+arg_18]
0x1800d1f8f  add     rsp, 50h
0x1800d1f93  pop     r14
0x1800d1f95  retn
```
