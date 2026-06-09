# OSIntegration::DEH::RegistryCompatibilityManager::OpenRootKey(ulong)

- ea: `0x180033ab0`
- end: `0x180033bf4`
- name: `?OpenRootKey@RegistryCompatibilityManager@DEH@OSIntegration@@AEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `324`
- prototype: `HKEY *__fastcall(__int64, HKEY *, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062568`
- `0x180063370`
- `0x180066ce0`
- `0x180109740`

## callees

- `0x180033ab0`
- `0x180033ca0`
- `0x180075e2c`
- `0x1800762cc`
- `0x18007cdc0`
- `0x180104cf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033bab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033bab`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180033b13`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180033b13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033b60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033b60`

## string_xrefs

- `0x180033b8c`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\registrycompatibilitymanager.cpp`
- `0x180033be2`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\registrycompatibilitymanager.cpp`
- `0x180033b79`: `RegOpenKeyEx(HKEY_LOCAL_MACHINE, L"", 0, samDesired | KEY_WOW64_64KEY, &handle)`
- `0x180033b85`: `OSIntegration::DEH::RegistryCompatibilityManager::OpenRootKey`
- `0x180033bdb`: `OSIntegration::DEH::RegistryCompatibilityManager::OpenRootKey`
- `0x180033bcf`: `RegOpenCurrentUser(samDesired | KEY_WOW64_64KEY, &handle)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY *__fastcall OSIntegration::DEH::RegistryCompatibilityManager::OpenRootKey(__int64 a1, HKEY *a2, int a3)
{
  HKEY v5; // rsi
  LSTATUS v6; // eax
  HKEY *phkResult; // rax
  LSTATUS v9; // eax
  char *v10; // [rsp+28h] [rbp-20h]
  wil::details::in1diag5 *retaddr; // [rsp+48h] [rbp+0h]
  char v12; // [rsp+50h] [rbp+8h] BYREF
  HKEY *v13; // [rsp+58h] [rbp+10h]

  v13 = a2;
  *a2 = 0;
  if ( *(_QWORD *)(a1 + 40) )
  {
    if ( !NtCurrentTeb()->IsImpersonating )
      MicrosoftTelemetryAssertTriggeredNoArgs(a1);
    v5 = *a2;
    if ( *a2 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
      RegCloseKey(v5);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
    }
    *a2 = 0;
    v6 = RegOpenCurrentUser(a3 | 0x100, a2);
    if ( v6 )
    {
      LODWORD(v10) = v6;
      wil::details::in1diag5::_Throw_Win32(
        retaddr,
        (void *)0x4B9,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\registrycompatibilitymanager.cpp",
        "OSIntegration::DEH::RegistryCompatibilityManager::OpenRootKey",
        "RegOpenCurrentUser(samDesired | KEY_WOW64_64KEY, &handle)",
        v10,
        1u);
    }
  }
  else
  {
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(a2);
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &Value, 0, a3 | 0x100, phkResult);
    if ( v9 )
    {
      LODWORD(v10) = v9;
      wil::details::in1diag5::_Throw_Win32(
        retaddr,
        (void *)0x4B1,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\registrycompatibilitymanager.cpp",
        "OSIntegration::DEH::RegistryCompatibilityManager::OpenRootKey",
        "RegOpenKeyEx(HKEY_LOCAL_MACHINE, L\"\", 0, samDesired | KEY_WOW64_64KEY, &handle)",
        v10,
        1u);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180033ab0  mov     rax, rsp
0x180033ab3  mov     [rax+18h], rbx
0x180033ab7  mov     [rax+20h], rsi
0x180033abb  mov     [rax+10h], rdx
0x180033abf  push    rdi
0x180033ac0  sub     rsp, 40h
0x180033ac4  mov     edi, r8d
0x180033ac7  mov     rbx, rdx
0x180033aca  mov     dword ptr [rax-18h], 0
0x180033ad1  mov     qword ptr [rdx], 0
0x180033ad8  mov     dword ptr [rax-18h], 1
0x180033adf  cmp     qword ptr [rcx+28h], 0
0x180033ae4  jz      short loc_180033B3B
0x180033ae6  mov     eax, gs:179Ch
0x180033aee  test    eax, eax
0x180033af0  jnz     short loc_180033AF7
0x180033af2  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "RtlIsImpersonating()")
0x180033af7  mov     rsi, [rbx]
0x180033afa  test    rsi, rsi
0x180033afd  jnz     loc_180033B9E
0x180033b03  mov     qword ptr [rbx], 0
0x180033b0a  bts     edi, 8
0x180033b0e  mov     rdx, rbx; phkResult
0x180033b11  mov     ecx, edi; samDesired
0x180033b13  call    cs:__imp_RegOpenCurrentUser
0x180033b1a  nop     dword ptr [rax+rax+00h]
0x180033b1f  test    eax, eax
0x180033b21  jnz     loc_180033BC6
0x180033b27  mov     rax, rbx
0x180033b2a  mov     rbx, [rsp+48h+arg_10]
0x180033b2f  mov     rsi, [rsp+48h+arg_18]
0x180033b34  add     rsp, 40h
0x180033b38  pop     rdi
0x180033b39  retn
0x180033b3b  mov     rcx, rbx
0x180033b3e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180033b43  bts     edi, 8
0x180033b47  mov     [rsp+48h+phkResult], rax; phkResult
0x180033b4c  mov     r9d, edi; samDesired
0x180033b4f  xor     r8d, r8d; ulOptions
0x180033b52  lea     rdx, Value; lpSubKey
0x180033b59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033b60  call    cs:__imp_RegOpenKeyExW
0x180033b67  nop     dword ptr [rax+rax+00h]
0x180033b6c  test    eax, eax
0x180033b6e  jz      short loc_180033B27
0x180033b70  mov     rcx, [rsp+48h]; this
0x180033b75  mov     dword ptr [rsp+48h+var_20], eax; char *
0x180033b79  lea     rax, aRegopenkeyexHk; "RegOpenKeyEx(HKEY_LOCAL_MACHINE, L\"\","...
0x180033b80  mov     [rsp+48h+phkResult], rax; char *
0x180033b85  lea     r9, aOsintegrationD_270; "OSIntegration::DEH::RegistryCompatibili"...
0x180033b8c  lea     r8, aOnecoreAdminAp_44; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180033b93  mov     edx, 4B1h; void *
0x180033b98  call    ?_Throw_Win32@in1diag5@details@wil@@YAXPEAXIPEBD11K@Z; wil::details::in1diag5::_Throw_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x180033b9e  lea     rcx, [rsp+48h+arg_0]; this
0x180033ba3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180033ba8  mov     rcx, rsi; hKey
0x180033bab  call    cs:__imp_RegCloseKey
0x180033bb2  nop     dword ptr [rax+rax+00h]
0x180033bb7  lea     rcx, [rsp+48h+arg_0]; this
0x180033bbc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180033bc1  jmp     loc_180033B03
0x180033bc6  mov     rcx, [rsp+48h]; this
0x180033bcb  mov     dword ptr [rsp+48h+var_20], eax; char *
0x180033bcf  lea     rax, aRegopencurrent; "RegOpenCurrentUser(samDesired | KEY_WOW"...
0x180033bd6  mov     [rsp+48h+phkResult], rax; char *
0x180033bdb  lea     r9, aOsintegrationD_270; "OSIntegration::DEH::RegistryCompatibili"...
0x180033be2  lea     r8, aOnecoreAdminAp_44; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180033be9  mov     edx, 4B9h; void *
0x180033bee  call    ?_Throw_Win32@in1diag5@details@wil@@YAXPEAXIPEBD11K@Z; wil::details::in1diag5::_Throw_Win32(void *,uint,char const *,char const *,char const *,ulong)
```
