# RegistryManager::CreateRedirectionMap(void)

- ea: `0x1400065a8`
- end: `0x1400068ad`
- name: `?CreateRedirectionMap@RegistryManager@@CA?AV?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@XZ`
- size: `773`
- prototype: `void **__fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140001130`

## callees

- `0x140001ee0`
- `0x1400064b8`
- `0x1400065a8`

## string_xrefs

- `0x14000669a`: `WindowsUpdateUXRoot`
- `0x1400065fa`: `UpdateOrchestratorSharedRoot`
- `0x140006610`: `Software\Microsoft\WindowsUpdate\Orchestrator\USOShared`
- `0x14000661a`: `UpdateOrchestratorConfigurationRoot`
- `0x140006630`: `Software\Microsoft\WindowsUpdate\Orchestrator\Configurations`
- `0x14000663a`: `UpdateUxConfigurationRoot`
- `0x140006650`: `Software\Microsoft\Windows\CurrentVersion\UpdatePlatform\UX\Configurations`
- `0x14000665a`: `UpdateOrchestratorCurrentVersionRoot`
- `0x140006670`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Orchestrator`
- `0x14000667a`: `UpdateOrchestratorRoot`
- `0x140006690`: `Software\Microsoft\WindowsUpdate\Orchestrator`
- `0x1400066b0`: `Software\Microsoft\WindowsUpdate\UX`
- `0x1400066ba`: `WindowsUpdate`
- `0x1400066d0`: `Software\Microsoft\WindowsUpdate`
- `0x1400066f0`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x1400066fa`: `WindowsUpdatePolicies`
- `0x140006710`: `Software\Policies\Microsoft\Windows\WindowsUpdate`
- `0x14000671a`: `DeviceUpdate`
- `0x140006730`: `Software\Microsoft\Windows\CurrentVersion\DeviceUpdate`
- `0x140006770`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\DTU`
- `0x1400067fa`: `DynamicInstalledProducts`
- `0x140006810`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\DynamicInstalled`
- `0x14000683a`: `DeviceAccess`
- `0x140006850`: `SOFTWARE\Microsoft\Windows\CurrentVersion\DeviceAccess`
- `0x140006870`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Interface`

## pseudocode

```c
void **__fastcall RegistryManager::CreateRedirectionMap(const wchar_t *a1)
{
  _QWORD *v1; // rax
  __int64 v2; // rcx
  unsigned int v3; // r8d
  int v5; // [rsp+20h] [rbp-18h]
  _DWORD v6[14]; // [rsp+0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const wchar_t *v8; // [rsp+40h] [rbp+8h] BYREF
  void **v9; // [rsp+48h] [rbp+10h]

  v8 = a1;
  v9 = &RegistryManager::s_defaultRedirectionMap;
  RegistryManager::s_defaultRedirectionMap = 0;
  qword_14000D3F0 = 0;
  v1 = operator new(0x30u);
  *v1 = v1;
  v1[1] = v1;
  v1[2] = v1;
  *((_WORD *)v1 + 12) = 257;
  RegistryManager::s_defaultRedirectionMap = v1;
  v6[8] = 1;
  v8 = L"UpdateOrchestratorSharedRoot";
  try
  {
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](v2, (unsigned __int64 *)&v8) = L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\USOShared";
    v8 = L"UpdateOrchestratorConfigurationRoot";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\USOShared",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\Configurations";
    v8 = L"UpdateUxConfigurationRoot";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\Configurations",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\Windows\\CurrentVersion\\UpdatePlatform\\UX\\Configurations";
    v8 = L"UpdateOrchestratorCurrentVersionRoot";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\UpdatePlatform\\UX\\Configurations",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Orchestrator";
    v8 = L"UpdateOrchestratorRoot";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Orchestrator",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\WindowsUpdate\\Orchestrator";
    v8 = L"WindowsUpdateUXRoot";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\WindowsUpdate\\Orchestrator",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\WindowsUpdate\\UX";
    v8 = L"WindowsUpdate";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\WindowsUpdate\\UX",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\WindowsUpdate";
    v8 = L"WUCurrentVersion";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\WindowsUpdate",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate";
    v8 = L"WindowsUpdatePolicies";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate",
                 (unsigned __int64 *)&v8) = L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate";
    v8 = L"DeviceUpdate";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceUpdate";
    v8 = L"DtuSelfhost";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceUpdate",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\DTU";
    v8 = L"Dtu";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\DTU",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\DTU";
    v8 = L"SystemSetup";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\DTU",
                 (unsigned __int64 *)&v8) = L"System\\Setup";
    v8 = L"SystemVersions";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"System\\Setup",
                 (unsigned __int64 *)&v8) = L"System\\Versions";
    v8 = L"UIXProductFeatures";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"System\\Versions",
                 (unsigned __int64 *)&v8) = L"Software\\Microsoft\\UIX\\ProductFeatures";
    v8 = L"USO_Network";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"Software\\Microsoft\\UIX\\ProductFeatures",
                 (unsigned __int64 *)&v8) = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Settings\\Network";
    v8 = L"DynamicInstalledProducts";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Settings\\Network",
                 (unsigned __int64 *)&v8) = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Update\\TargetingInfo\\DynamicInstalled";
    v8 = L"ReserveManager";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Update\\TargetingInfo\\DynamicInstalled",
                 (unsigned __int64 *)&v8) = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager";
    v8 = L"DeviceAccess";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                 (unsigned __int64 *)&v8) = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess";
    v8 = L"CBSInterface";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess",
                 (unsigned __int64 *)&v8) = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface";
    v8 = L"Sih";
    *(_QWORD *)std::map<unsigned short const *,unsigned short const *>::operator[](
                 (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Interface",
                 (unsigned __int64 *)&v8) = L"SOFTWARE\\Microsoft\\sih";
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_Hr(retaddr, v6, v3, (const char *)0x8007000ELL, v5);
  }
  return &RegistryManager::s_defaultRedirectionMap;
}

```

## disassembly

```asm
0x1400065a8  mov     [rsp+arg_0], rcx
0x1400065ad  push    rbx
0x1400065ae  sub     rsp, 30h
0x1400065b2  xor     eax, eax
0x1400065b4  mov     [rsp+38h+var_18], eax
0x1400065b8  lea     rbx, ?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x1400065bf  mov     [rsp+38h+arg_8], rbx
0x1400065c4  mov     cs:?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A, rax; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x1400065cb  mov     cs:qword_14000D3F0, rax
0x1400065d2  lea     ecx, [rax+30h]; Size
0x1400065d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400065da  mov     [rax], rax
0x1400065dd  mov     [rax+8], rax
0x1400065e1  mov     [rax+10h], rax
0x1400065e5  mov     word ptr [rax+18h], 101h
0x1400065eb  mov     cs:?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A, rax; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x1400065f2  mov     [rsp+38h+var_18], 1
0x1400065fa  lea     rax, aUpdateorchestr_2; "UpdateOrchestratorSharedRoot"
0x140006601  mov     [rsp+38h+arg_0], rax
0x140006606  lea     rdx, [rsp+38h+arg_0]
0x14000660b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006610  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x140006617  mov     [rax], rcx
0x14000661a  lea     rax, aUpdateorchestr; "UpdateOrchestratorConfigurationRoot"
0x140006621  mov     [rsp+38h+arg_0], rax
0x140006626  lea     rdx, [rsp+38h+arg_0]
0x14000662b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006630  lea     rcx, aSoftwareMicros_12; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x140006637  mov     [rax], rcx
0x14000663a  lea     rax, aUpdateuxconfig; "UpdateUxConfigurationRoot"
0x140006641  mov     [rsp+38h+arg_0], rax
0x140006646  lea     rdx, [rsp+38h+arg_0]
0x14000664b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006650  lea     rcx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140006657  mov     [rax], rcx
0x14000665a  lea     rax, aUpdateorchestr_1; "UpdateOrchestratorCurrentVersionRoot"
0x140006661  mov     [rsp+38h+arg_0], rax
0x140006666  lea     rdx, [rsp+38h+arg_0]
0x14000666b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006670  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140006677  mov     [rax], rcx
0x14000667a  lea     rax, aUpdateorchestr_0; "UpdateOrchestratorRoot"
0x140006681  mov     [rsp+38h+arg_0], rax
0x140006686  lea     rdx, [rsp+38h+arg_0]
0x14000668b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006690  lea     rcx, aSoftwareMicros_6; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x140006697  mov     [rax], rcx
0x14000669a  lea     rax, aWindowsupdateu; "WindowsUpdateUXRoot"
0x1400066a1  mov     [rsp+38h+arg_0], rax
0x1400066a6  lea     rdx, [rsp+38h+arg_0]
0x1400066ab  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x1400066b0  lea     rcx, aSoftwareMicros_14; "Software\\Microsoft\\WindowsUpdate\\UX"
0x1400066b7  mov     [rax], rcx
0x1400066ba  lea     rax, aWindowsupdate; "WindowsUpdate"
0x1400066c1  mov     [rsp+38h+arg_0], rax
0x1400066c6  lea     rdx, [rsp+38h+arg_0]
0x1400066cb  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x1400066d0  lea     rcx, aSoftwareMicros_9; "Software\\Microsoft\\WindowsUpdate"
0x1400066d7  mov     [rax], rcx
0x1400066da  lea     rax, aWucurrentversi; "WUCurrentVersion"
0x1400066e1  mov     [rsp+38h+arg_0], rax
0x1400066e6  lea     rdx, [rsp+38h+arg_0]
0x1400066eb  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x1400066f0  lea     rcx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400066f7  mov     [rax], rcx
0x1400066fa  lea     rax, aWindowsupdatep; "WindowsUpdatePolicies"
0x140006701  mov     [rsp+38h+arg_0], rax
0x140006706  lea     rdx, [rsp+38h+arg_0]
0x14000670b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006710  lea     rcx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x140006717  mov     [rax], rcx
0x14000671a  lea     rax, aDeviceupdate; "DeviceUpdate"
0x140006721  mov     [rsp+38h+arg_0], rax
0x140006726  lea     rdx, [rsp+38h+arg_0]
0x14000672b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006730  lea     rcx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140006737  mov     [rax], rcx
0x14000673a  lea     rax, aDtuselfhost; "DtuSelfhost"
0x140006741  mov     [rsp+38h+arg_0], rax
0x140006746  lea     rdx, [rsp+38h+arg_0]
0x14000674b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006750  lea     rcx, aSoftwareMicros_11; "Software\\Microsoft\\DTU"
0x140006757  mov     [rax], rcx
0x14000675a  lea     rax, aDtu; "Dtu"
0x140006761  mov     [rsp+38h+arg_0], rax
0x140006766  lea     rdx, [rsp+38h+arg_0]
0x14000676b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006770  lea     rcx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140006777  mov     [rax], rcx
0x14000677a  lea     rax, aSystemsetup; "SystemSetup"
0x140006781  mov     [rsp+38h+arg_0], rax
0x140006786  lea     rdx, [rsp+38h+arg_0]
0x14000678b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006790  lea     rcx, aSystemSetup; "System\\Setup"
0x140006797  mov     [rax], rcx
0x14000679a  lea     rax, aSystemversions; "SystemVersions"
0x1400067a1  mov     [rsp+38h+arg_0], rax
0x1400067a6  lea     rdx, [rsp+38h+arg_0]
0x1400067ab  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x1400067b0  lea     rcx, aSystemVersions; "System\\Versions"
0x1400067b7  mov     [rax], rcx
0x1400067ba  lea     rax, aUixproductfeat; "UIXProductFeatures"
0x1400067c1  mov     [rsp+38h+arg_0], rax
0x1400067c6  lea     rdx, [rsp+38h+arg_0]
0x1400067cb  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x1400067d0  lea     rcx, aSoftwareMicros_5; "Software\\Microsoft\\UIX\\ProductFeatur"...
0x1400067d7  mov     [rax], rcx
0x1400067da  lea     rax, aUsoNetwork; "USO_Network"
0x1400067e1  mov     [rsp+38h+arg_0], rax
0x1400067e6  lea     rdx, [rsp+38h+arg_0]
0x1400067eb  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x1400067f0  lea     rcx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400067f7  mov     [rax], rcx
0x1400067fa  lea     rax, aDynamicinstall; "DynamicInstalledProducts"
0x140006801  mov     [rsp+38h+arg_0], rax
0x140006806  lea     rdx, [rsp+38h+arg_0]
0x14000680b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006810  lea     rcx, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140006817  mov     [rax], rcx
0x14000681a  lea     rax, aReservemanager; "ReserveManager"
0x140006821  mov     [rsp+38h+arg_0], rax
0x140006826  lea     rdx, [rsp+38h+arg_0]
0x14000682b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006830  lea     rcx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140006837  mov     [rax], rcx
0x14000683a  lea     rax, aDeviceaccess; "DeviceAccess"
0x140006841  mov     [rsp+38h+arg_0], rax
0x140006846  lea     rdx, [rsp+38h+arg_0]
0x14000684b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006850  lea     rcx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140006857  mov     [rax], rcx
0x14000685a  lea     rax, aCbsinterface; "CBSInterface"
0x140006861  mov     [rsp+38h+arg_0], rax
0x140006866  lea     rdx, [rsp+38h+arg_0]
0x14000686b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006870  lea     rcx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140006877  mov     [rax], rcx
0x14000687a  lea     rax, aSih; "Sih"
0x140006881  mov     [rsp+38h+arg_0], rax
0x140006886  lea     rdx, [rsp+38h+arg_0]
0x14000688b  call    ??A?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAAAEAPEBGAEBQEBG@Z; std::map<ushort const *,ushort const *>::operator[](ushort const * const &)
0x140006890  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\sih"
0x140006897  mov     [rax], rcx
0x14000689a  jmp     short loc_1400068A3
0x14000689c  lea     rbx, ?s_defaultRedirectionMap@RegistryManager@@0V?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@A; std::map<ushort const *,ushort const *> RegistryManager::s_defaultRedirectionMap
0x1400068a3  mov     rax, rbx
0x1400068a6  add     rsp, 30h
0x1400068aa  pop     rbx
0x1400068ab  retn
```
