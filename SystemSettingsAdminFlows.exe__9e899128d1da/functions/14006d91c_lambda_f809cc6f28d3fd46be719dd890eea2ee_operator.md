# _lambda_f809cc6f28d3fd46be719dd890eea2ee_::operator()

- ea: `0x14006d91c`
- end: `0x14006d99d`
- name: `_lambda_f809cc6f28d3fd46be719dd890eea2ee_::operator()`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006d810`

## callees

- `0x14000ed38`
- `0x14002a304`
- `0x14002c070`
- `0x14006d91c`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x14006d954`
- `KERNEL32!RegOpenKeyExW` at `0x14006d954`
- `KERNEL32!RegDeleteValueW` at `0x14006d96a`
- `KERNEL32!RegDeleteValueW` at `0x14006d96a`

## string_xrefs

- `0x14006d98b`: `pcshell\shell\systemsettings\adminflows\accessibility\narratoradminflowhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS lambda_f809cc6f28d3fd46be719dd890eea2ee_::operator()()
{
  HKEY *v0; // rax
  unsigned int v1; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( !RegOpenKeyExW(HKEY_USERS, L".DEFAULT\\Software\\Microsoft\\Narrator\\NoRoam", 0, 0xF003Fu, v0) )
  {
    v1 = RegDeleteValueW(hKey, L"RunningState");
    if ( v1 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x104,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\narratoradminflowhandler.cpp",
        (const char *)v1,
        phkResult);
  }
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x14006d91c  mov     [rsp+hKey], rcx
0x14006d921  sub     rsp, 38h
0x14006d925  mov     [rsp+38h+hKey], 0
0x14006d92e  lea     rcx, [rsp+38h+hKey]
0x14006d933  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x14006d938  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x14006d93d  mov     r9d, 0F003Fh; samDesired
0x14006d943  xor     r8d, r8d; ulOptions
0x14006d946  lea     rdx, aDefaultSoftwar; ".DEFAULT\\Software\\Microsoft\\Narrator"...
0x14006d94d  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14006d954  call    cs:__imp_RegOpenKeyExW
0x14006d95a  test    eax, eax
0x14006d95c  jnz     short loc_14006D979
0x14006d95e  lea     rdx, aRunningstate; "RunningState"
0x14006d965  mov     rcx, [rsp+38h+hKey]; hKey
0x14006d96a  call    cs:__imp_RegDeleteValueW
0x14006d970  mov     rcx, [rsp+38h]; this
0x14006d975  test    eax, eax
0x14006d977  jnz     short loc_14006D988
0x14006d979  lea     rcx, [rsp+38h+hKey]
0x14006d97e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14006d983  add     rsp, 38h
0x14006d987  retn
0x14006d988  mov     r9d, eax; char *
0x14006d98b  lea     r8, aPcshellShellSy_31; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006d992  mov     edx, 104h; void *
0x14006d997  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
