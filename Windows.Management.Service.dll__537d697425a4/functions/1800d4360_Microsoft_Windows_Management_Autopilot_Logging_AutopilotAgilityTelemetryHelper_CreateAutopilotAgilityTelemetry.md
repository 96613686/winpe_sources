# Microsoft::Windows::Management::Autopilot::Logging::AutopilotAgilityTelemetryHelper::CreateAutopilotAgilityTelemetryFlagRegkey(void)

- ea: `0x1800d4360`
- end: `0x1800d44d9`
- name: `?CreateAutopilotAgilityTelemetryFlagRegkey@AutopilotAgilityTelemetryHelper@Logging@Autopilot@Management@Windows@Microsoft@@SAJXZ`
- size: `377`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d5c50`

## callees

- `0x180067e54`
- `0x180080984`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x1800d4360`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d4488`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d4488`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d442f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d442f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d43bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d43bf`

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
  v1 = (const WCHAR *)&stru_18022EC60;
  v2 = (const WCHAR *)&stru_18022EC60;
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
0x1800d4360  mov     [rsp+arg_18], rbx
0x1800d4365  push    r14
0x1800d4367  sub     rsp, 50h
0x1800d436b  mov     [rsp+58h+arg_0], 0
0x1800d4373  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800d4378  test    al, al
0x1800d437a  lea     rbx, stru_18022EC60
0x1800d4381  lea     rax, [rsp+58h+arg_0]
0x1800d4386  mov     rdx, rbx
0x1800d4389  mov     [rsp+58h+pcbData], rax; pcbData
0x1800d438e  lea     r14, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800d4395  mov     [rsp+58h+pvData], 0; pvData
0x1800d439e  lea     r8, aDisableautopil; "DisableAutopilotAgilityProductVersionTe"...
0x1800d43a5  cmovz   rdx, r14; lpSubKey
0x1800d43a9  mov     [rsp+58h+pdwType], 0; pdwType
0x1800d43b2  mov     r9d, 2; dwFlags
0x1800d43b8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800d43bf  call    cs:__imp_RegGetValueW
0x1800d43c6  nop     dword ptr [rax+rax+00h]
0x1800d43cb  test    eax, eax
0x1800d43cd  jz      loc_1800D44CC
0x1800d43d3  xor     edx, edx
0x1800d43d5  mov     [rsp+58h+hKey], 0
0x1800d43de  lea     rcx, [rsp+58h+hKey]
0x1800d43e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d43e8  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800d43ed  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800d43f6  test    al, al
0x1800d43f8  lea     rax, [rsp+58h+hKey]
0x1800d43fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d4404  cmovz   rbx, r14
0x1800d4408  mov     [rsp+58h+phkResult], rax; phkResult
0x1800d440d  mov     [rsp+58h+pcbData], 0; lpSecurityAttributes
0x1800d4416  mov     rdx, rbx; lpSubKey
0x1800d4419  mov     dword ptr [rsp+58h+pvData], 2; samDesired
0x1800d4421  xor     r9d, r9d; lpClass
0x1800d4424  xor     r8d, r8d; Reserved
0x1800d4427  mov     dword ptr [rsp+58h+pdwType], 0; unsigned int
0x1800d442f  call    cs:__imp_RegCreateKeyExW
0x1800d4436  nop     dword ptr [rax+rax+00h]
0x1800d443b  test    eax, eax
0x1800d443d  jz      short loc_1800D445C
0x1800d443f  mov     rcx, [rsp+58h]; this
0x1800d4444  lea     r8, aOnecoreuapAdmi_143; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d444b  mov     r9d, eax; char *
0x1800d444e  mov     edx, 97h; void *
0x1800d4453  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d4458  mov     ebx, eax
0x1800d445a  jmp     short loc_1800D44C0
0x1800d445c  mov     rcx, [rsp+58h+hKey]; hKey
0x1800d4461  lea     rax, [rsp+58h+Data]
0x1800d4466  mov     r9d, 4; dwType
0x1800d446c  mov     [rsp+58h+Data], 1
0x1800d4474  mov     dword ptr [rsp+58h+pvData], r9d; cbData
0x1800d4479  lea     rdx, aDisableautopil; "DisableAutopilotAgilityProductVersionTe"...
0x1800d4480  xor     r8d, r8d; Reserved
0x1800d4483  mov     [rsp+58h+pdwType], rax; int
0x1800d4488  call    cs:__imp_RegSetValueExW
0x1800d448f  nop     dword ptr [rax+rax+00h]
0x1800d4494  mov     ebx, eax
0x1800d4496  test    eax, eax
0x1800d4498  jle     short loc_1800D44A3
0x1800d449a  movzx   ebx, ax
0x1800d449d  or      ebx, 80070000h
0x1800d44a3  test    ebx, ebx
0x1800d44a5  jns     short loc_1800D44C0
0x1800d44a7  mov     rcx, [rsp+58h]; this
0x1800d44ac  lea     r8, aOnecoreuapAdmi_143; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d44b3  mov     r9d, ebx; char *
0x1800d44b6  mov     edx, 9Ah; void *
0x1800d44bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d44c0  lea     rcx, [rsp+58h+hKey]
0x1800d44c5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d44ca  mov     eax, ebx
0x1800d44cc  mov     rbx, [rsp+58h+arg_18]
0x1800d44d1  add     rsp, 50h
0x1800d44d5  pop     r14
0x1800d44d7  retn
```
