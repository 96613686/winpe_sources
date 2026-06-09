# IsolationEnvironmentPageHandler::SetEnabled(bool)

- ea: `0x140067c04`
- end: `0x140067cff`
- name: `?SetEnabled@IsolationEnvironmentPageHandler@@SAX_N@Z`
- size: `251`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x14000ed38`
- `0x14002c070`
- `0x140067a20`
- `0x140067c04`
- `0x140067d08`
- `0x140067fa4`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x140067c7e`
- `KERNEL32!RegOpenKeyExW` at `0x140067c7e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140067cb7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140067cb7`

## string_xrefs

- `0x140067c26`: `Failed to set MCP/CUA access`
- `0x140067cce`: `Failed to set IsoEnvBroker service value`
- `0x140067c70`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall IsolationEnvironmentPageHandler::SetEnabled(char a1)
{
  bool v1; // cl
  unsigned int v2; // eax
  HKEY *phkResult; // rax
  int v4; // eax
  bool v5; // sf
  const char *cbData; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  LOBYTE(Data) = a1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59214605>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59214605>::GetImpl'::`2'::impl) )
  {
    v2 = IsolationEnvironmentPageHandler::SetMcpCuaAccess(v1);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x1A,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\isolationenvironmentlib\\isolationenvironmentpagehandler.cpp",
      (const char *)v2,
      (int)"Failed to set MCP/CUA access",
      cbData);
  }
  Data = 0;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker", 0, 0xF003Fu, phkResult);
  v5 = v4 < 0;
  if ( v4 > 0 )
  {
    v4 = (unsigned __int16)v4 | 0x80070000;
    v5 = v4 < 0;
  }
  if ( !v5 )
  {
    v4 = RegSetKeyValueW(hKey, 0, L"Enabled", 4u, &Data, 4u);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
  }
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x33,
    (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\isolationenvironmentlib\\isolationenvironmentpagehandler.cpp",
    (const char *)(unsigned int)v4,
    (int)"Failed to set IsoEnvBroker service value",
    cbData);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x140067c04  mov     byte ptr [rsp+Data], cl
0x140067c08  sub     rsp, 38h
0x140067c0c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59214605@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59214605@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59214605> `wil::Feature<__WilFeatureTraits_Feature_ID59214605>::GetImpl(void)'::`2'::impl
0x140067c13  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59214605@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59214605>::__private_IsEnabled(void)
0x140067c18  test    al, al
0x140067c1a  jz      short loc_140067C47
0x140067c1c  call    ?SetMcpCuaAccess@IsolationEnvironmentPageHandler@@CAJ_N@Z; IsolationEnvironmentPageHandler::SetMcpCuaAccess(bool)
0x140067c21  mov     rcx, [rsp+38h]; this
0x140067c26  lea     rdx, aFailedToSetMcp; "Failed to set MCP/CUA access"
0x140067c2d  mov     [rsp+38h+phkResult], rdx; int
0x140067c32  mov     r9d, eax; char *
0x140067c35  lea     r8, aPcshellShellSy_4; "pcshell\\shell\\systemsettings\\adminfl"...
0x140067c3c  mov     edx, 1Ah; void *
0x140067c41  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x140067c46  nop
0x140067c47  mov     [rsp+38h+Data], 0
0x140067c4f  mov     [rsp+38h+hKey], 0
0x140067c58  lea     rcx, [rsp+38h+hKey]
0x140067c5d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140067c62  mov     [rsp+38h+phkResult], rax; phkResult
0x140067c67  mov     r9d, 0F003Fh; samDesired
0x140067c6d  xor     r8d, r8d; ulOptions
0x140067c70  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x140067c77  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140067c7e  call    cs:__imp_RegOpenKeyExW
0x140067c84  test    eax, eax
0x140067c86  jle     short loc_140067C92
0x140067c88  movzx   eax, ax
0x140067c8b  or      eax, 80070000h
0x140067c90  test    eax, eax
0x140067c92  js      short loc_140067CC9
0x140067c94  mov     r9d, 4; dwType
0x140067c9a  mov     [rsp+38h+cbData], r9d; char *
0x140067c9f  lea     rax, [rsp+38h+Data]
0x140067ca4  mov     [rsp+38h+phkResult], rax; lpData
0x140067ca9  lea     r8, Value; "Enabled"
0x140067cb0  xor     edx, edx; lpSubKey
0x140067cb2  mov     rcx, [rsp+38h+hKey]; hKey
0x140067cb7  call    cs:__imp_RegSetKeyValueW
0x140067cbd  test    eax, eax
0x140067cbf  jle     short loc_140067CC9
0x140067cc1  movzx   eax, ax
0x140067cc4  or      eax, 80070000h
0x140067cc9  mov     rcx, [rsp+38h]; this
0x140067cce  lea     rdx, aFailedToSetIso; "Failed to set IsoEnvBroker service valu"...
0x140067cd5  mov     [rsp+38h+phkResult], rdx; int
0x140067cda  mov     r9d, eax; char *
0x140067cdd  lea     r8, aPcshellShellSy_4; "pcshell\\shell\\systemsettings\\adminfl"...
0x140067ce4  mov     edx, 33h ; '3'; void *
0x140067ce9  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x140067cee  nop
0x140067cef  lea     rcx, [rsp+38h+hKey]
0x140067cf4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140067cf9  nop
0x140067cfa  add     rsp, 38h
0x140067cfe  retn
```
