# SetWallpaperTask::SetAccentColor(void)

- ea: `0x18002c668`
- end: `0x18002c782`
- name: `?SetAccentColor@SetWallpaperTask@@AEAAXXZ`
- size: `282`
- prototype: `void __fastcall(SetWallpaperTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18002c1d8`

## callees

- `0x18001094c`
- `0x18001e58c`
- `0x180022484`
- `0x180022aa8`
- `0x18002c668`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c746`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c746`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002c69a`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002c69a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002c6f1`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002c6f1`

## string_xrefs

- `0x18002c6ab`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`
- `0x18002c702`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`
- `0x18002c757`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SetWallpaperTask::SetAccentColor(SetWallpaperTask *this)
{
  unsigned int v1; // eax
  LSTATUS v2; // eax
  unsigned int v3; // eax
  unsigned int lpData; // [rsp+20h] [rbp-30h]
  unsigned int lpDataa; // [rsp+20h] [rbp-30h]
  HKEY *p_hKey; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  char v8; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  SetWallpaperTask *Data; // [rsp+60h] [rbp+10h] BYREF
  HKEY v11; // [rsp+68h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF

  Data = this;
  hKey = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v8 = 1;
  v1 = RegOpenCurrentUser(0xF003Fu, &phkResult);
  if ( v1 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5F,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
      (const char *)v1,
      lpData);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  v11 = 0;
  p_hKey = &v11;
  phkResult = 0;
  v8 = 1;
  v2 = RegCreateKeyW(hKey, L"Control Panel\\Desktop", &phkResult);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
      (const char *)(unsigned int)v2,
      lpData);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  LODWORD(Data) = 1;
  v3 = RegSetValueExW(v11, L"AutoColorization", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x63,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
      (const char *)v3,
      lpDataa);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18002c668  mov     [rsp-8+Data], rcx
0x18002c66d  push    rbp
0x18002c66e  mov     rbp, rsp
0x18002c671  sub     rsp, 50h
0x18002c675  mov     [rbp+hKey], 0
0x18002c67d  lea     rax, [rbp+hKey]
0x18002c681  mov     [rbp+var_20], rax
0x18002c685  mov     [rbp+phkResult], 0
0x18002c68d  mov     [rbp+var_10], 1
0x18002c691  lea     rdx, [rbp+phkResult]; phkResult
0x18002c695  mov     ecx, 0F003Fh; samDesired
0x18002c69a  call    cs:__imp_RegOpenCurrentUser
0x18002c6a0  mov     rcx, [rbp+8]; this
0x18002c6a4  test    eax, eax
0x18002c6a6  jz      short loc_18002C6BD
0x18002c6a8  mov     r9d, eax; char *
0x18002c6ab  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c6b2  mov     edx, 5Fh ; '_'; void *
0x18002c6b7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002c6bd  lea     rcx, [rbp+var_20]
0x18002c6c1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002c6c6  mov     [rbp+arg_8], 0
0x18002c6ce  lea     rax, [rbp+arg_8]
0x18002c6d2  mov     [rbp+var_20], rax
0x18002c6d6  mov     [rbp+phkResult], 0
0x18002c6de  mov     [rbp+var_10], 1
0x18002c6e2  lea     r8, [rbp+phkResult]; phkResult
0x18002c6e6  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x18002c6ed  mov     rcx, [rbp+hKey]; hKey
0x18002c6f1  call    cs:__imp_RegCreateKeyW
0x18002c6f7  mov     rcx, [rbp+8]; this
0x18002c6fb  test    eax, eax
0x18002c6fd  jns     short loc_18002C714
0x18002c6ff  mov     r9d, eax; char *
0x18002c702  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c709  mov     edx, 61h ; 'a'; void *
0x18002c70e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c714  lea     rcx, [rbp+var_20]
0x18002c718  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002c71d  mov     dword ptr [rbp+Data], 1
0x18002c724  mov     r9d, 4; dwType
0x18002c72a  mov     [rsp+50h+cbData], r9d; cbData
0x18002c72f  lea     rax, [rbp+Data]
0x18002c733  mov     [rsp+50h+lpData], rax; unsigned int
0x18002c738  xor     r8d, r8d; Reserved
0x18002c73b  lea     rdx, ValueName; "AutoColorization"
0x18002c742  mov     rcx, [rbp+arg_8]; hKey
0x18002c746  call    cs:__imp_RegSetValueExW
0x18002c74c  mov     rcx, [rbp+8]; this
0x18002c750  test    eax, eax
0x18002c752  jz      short loc_18002C769
0x18002c754  mov     r9d, eax; char *
0x18002c757  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c75e  mov     edx, 63h ; 'c'; void *
0x18002c763  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002c769  lea     rcx, [rbp+arg_8]
0x18002c76d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c772  nop
0x18002c773  lea     rcx, [rbp+hKey]
0x18002c777  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c77c  add     rsp, 50h
0x18002c780  pop     rbp
0x18002c781  retn
```
