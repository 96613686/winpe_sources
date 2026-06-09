# NarratorAdminFlowHandler::UseSettingsBeforeSignIn(void)

- ea: `0x14006f850`
- end: `0x14006f95b`
- name: `?UseSettingsBeforeSignIn@NarratorAdminFlowHandler@@SAJXZ`
- size: `267`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140020120`
- `0x14006ee4c`

## callees

- `0x14000ed38`
- `0x14002a304`
- `0x14002c070`
- `0x14006d724`
- `0x14006d810`
- `0x14006f28c`
- `0x14006f850`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x14006f88e`
- `KERNEL32!RegOpenKeyExW` at `0x14006f88e`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x14006f909`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x14006f909`

## string_xrefs

- `0x14006f8a0`: `pcshell\shell\systemsettings\adminflows\accessibility\narratoradminflowhandler.cpp`
- `0x14006f8ec`: `pcshell\shell\systemsettings\adminflows\accessibility\narratoradminflowhandler.cpp`
- `0x14006f91b`: `pcshell\shell\systemsettings\adminflows\accessibility\narratoradminflowhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 NarratorAdminFlowHandler::UseSettingsBeforeSignIn(void)
{
  HKEY *v0; // rax
  unsigned int v1; // eax
  HKEY *v2; // rax
  unsigned int RegKey; // eax
  unsigned int v4; // eax
  const char *v5; // r9
  __int64 result; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v9; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKeyDest; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKeySrc; // [rsp+50h] [rbp+18h] BYREF

  wil::scope_exit__lambda_f809cc6f28d3fd46be719dd890eea2ee___(&v9);
  hKeySrc = 0;
  v0 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKeySrc);
  v1 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Narrator", 0, 0x20019u, v0);
  try
  {
    if ( v1 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x109,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\narratoradminflowhandler.cpp",
        (const char *)v1,
        phkResult);
    hKeyDest = 0;
    v2 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKeyDest);
    RegKey = anonymous_namespace_::OpenOrCreateRegKey(
               HKEY_USERS,
               L".DEFAULT\\Software\\Microsoft\\Narrator",
               0xF003Fu,
               v2);
    if ( RegKey )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x10C,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\narratoradminflowhandler.cpp",
        (const char *)RegKey,
        phkResult);
    v4 = RegCopyTreeW(hKeySrc, 0, hKeyDest);
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x10E,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\narratoradminflowhandler.cpp",
        (const char *)v4,
        phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeySrc);
    wil::details::lambda_call__lambda_f809cc6f28d3fd46be719dd890eea2ee___::_lambda_call__lambda_f809cc6f28d3fd46be719dd890eea2ee___(&v9);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x112,
                           (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\narratoradminflowhandler.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x14006f850  sub     rsp, 38h
0x14006f854  lea     rcx, [rsp+38h+arg_0]
0x14006f859  call    wil__scope_exit__lambda_f809cc6f28d3fd46be719dd890eea2ee___
0x14006f85e  nop
0x14006f85f  mov     [rsp+38h+hKeySrc], 0
0x14006f868  lea     rcx, [rsp+38h+hKeySrc]
0x14006f86d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x14006f872  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x14006f877  mov     r9d, 20019h; samDesired
0x14006f87d  xor     r8d, r8d; ulOptions
0x14006f880  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Narrator"
0x14006f887  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14006f88e  call    cs:__imp_RegOpenKeyExW
0x14006f894  mov     rcx, [rsp+38h]; this
0x14006f899  test    eax, eax
0x14006f89b  jz      short loc_14006F8B1
0x14006f89d  mov     r9d, eax; char *
0x14006f8a0  lea     r8, aPcshellShellSy_31; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006f8a7  mov     edx, 109h; void *
0x14006f8ac  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14006f8b1  mov     [rsp+38h+hKeyDest], 0
0x14006f8ba  lea     rcx, [rsp+38h+hKeyDest]
0x14006f8bf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x14006f8c4  mov     r9, rax; phkResult
0x14006f8c7  mov     r8d, 0F003Fh; samDesired
0x14006f8cd  lea     rdx, aDefaultSoftwar_0; ".DEFAULT\\Software\\Microsoft\\Narrator"
0x14006f8d4  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14006f8db  call    _anonymous_namespace___OpenOrCreateRegKey
0x14006f8e0  mov     rcx, [rsp+38h]; this
0x14006f8e5  test    eax, eax
0x14006f8e7  jz      short loc_14006F8FD
0x14006f8e9  mov     r9d, eax; char *
0x14006f8ec  lea     r8, aPcshellShellSy_31; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006f8f3  mov     edx, 10Ch; void *
0x14006f8f8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14006f8fd  mov     r8, [rsp+38h+hKeyDest]; hKeyDest
0x14006f902  xor     edx, edx; lpSubKey
0x14006f904  mov     rcx, [rsp+38h+hKeySrc]; hKeySrc
0x14006f909  call    cs:__imp_RegCopyTreeW
0x14006f90f  mov     rcx, [rsp+38h]; this
0x14006f914  test    eax, eax
0x14006f916  jz      short loc_14006F92D
0x14006f918  mov     r9d, eax; char *
0x14006f91b  lea     r8, aPcshellShellSy_31; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006f922  mov     edx, 10Eh; void *
0x14006f927  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14006f92d  lea     rcx, [rsp+38h+hKeyDest]
0x14006f932  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14006f937  nop
0x14006f938  lea     rcx, [rsp+38h+hKeySrc]
0x14006f93d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14006f942  nop
0x14006f943  lea     rcx, [rsp+38h+arg_0]
0x14006f948  call    wil__details__lambda_call__lambda_f809cc6f28d3fd46be719dd890eea2ee______lambda_call__lambda_f809cc6f28d3fd46be719dd890eea2ee___
0x14006f94d  xor     eax, eax
0x14006f94f  jmp     short loc_14006F955
0x14006f951  mov     eax, [rsp+38h+arg_0]
0x14006f955  add     rsp, 38h
0x14006f959  retn
```
