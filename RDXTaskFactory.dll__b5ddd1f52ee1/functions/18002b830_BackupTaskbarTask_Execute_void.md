# BackupTaskbarTask::Execute(void)

- ea: `0x18002b830`
- end: `0x18002b99a`
- name: `?Execute@BackupTaskbarTask@@EEAAXXZ`
- size: `362`
- prototype: `void __fastcall(BackupTaskbarTask *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008bbc`
- `0x18001094c`
- `0x18001e58c`
- `0x180022484`
- `0x180022aa8`
- `0x18002b7d4`
- `0x18002b830`
- `0x18002e5b8`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b94b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b94b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b8f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002b8f0`

## string_xrefs

- `0x18002b8e2`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\ServiceReadWrite\PinnedToTaskbarDefaultApplist`
- `0x18002b87a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backuptaskbartask.cpp`
- `0x18002b901`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backuptaskbartask.cpp`
- `0x18002b988`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\backuptaskbartask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall BackupTaskbarTask::Execute(BackupTaskbarTask *this)
{
  _QWORD *UserAgent; // rax
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // eax
  __int64 v6; // rbx
  unsigned int i; // eax
  unsigned int v8; // eax
  int dwOptions; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-50h]
  _BYTE v12[8]; // [rsp+50h] [rbp-20h] BYREF
  HKEY *p_hKey; // [rsp+58h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-10h] BYREF
  char v15; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  unsigned int v17; // [rsp+88h] [rbp+18h] BYREF
  LPVOID *v18; // [rsp+90h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+28h] BYREF

  v17 = 0;
  v18 = 0;
  UserAgent = (_QWORD *)RetailDemoUtil::GetUserAgent(v12, 0);
  v2 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, LPVOID **))(*(_QWORD *)*UserAgent + 96LL))(
         *UserAgent,
         &v17,
         &v18);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backuptaskbartask.cpp",
      (const char *)(unsigned int)v2,
      dwOptions);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v12, v3, v4);
  hKey = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v15 = 1;
  v5 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\ServiceReadWrite\\PinnedToTaskbarDefaultApplist",
         0,
         0,
         0,
         2u,
         0,
         &phkResult,
         0);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x20,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backuptaskbartask.cpp",
      (const char *)v5,
      dwOptionsa);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  v6 = 0;
  for ( i = v17; (unsigned int)v6 < v17; i = v17 )
  {
    v8 = RegSetValueExW(hKey, (LPCWSTR)v18[v6], 0, 1u, 0, 0);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x23,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\backuptaskbartask.cpp",
        (const char *)v8,
        dwOptionsb);
    v6 = (unsigned int)(v6 + 1);
  }
  SHCoFreeArray<unsigned short>(v18, i);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18002b830  mov     [rsp-8+arg_0], rbx
0x18002b835  push    rbp
0x18002b836  mov     rbp, rsp
0x18002b839  sub     rsp, 70h
0x18002b83d  mov     [rbp+arg_8], 0
0x18002b844  mov     [rbp+arg_10], 0
0x18002b84c  xor     edx, edx
0x18002b84e  lea     rcx, [rbp+var_20]
0x18002b852  call    ?GetUserAgent@RetailDemoUtil@@YA?AV?$ComPtr@UIRetailDemoUserAgent@@@WRL@Microsoft@@PEAUIServiceProvider@@@Z; RetailDemoUtil::GetUserAgent(IServiceProvider *)
0x18002b857  nop
0x18002b858  mov     rcx, [rax]
0x18002b85b  mov     rax, [rcx]
0x18002b85e  lea     r8, [rbp+arg_10]
0x18002b862  lea     rdx, [rbp+arg_8]
0x18002b866  mov     rax, [rax+60h]
0x18002b86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b86f  mov     rcx, [rbp+8]; this
0x18002b873  test    eax, eax
0x18002b875  jns     short loc_18002B88C
0x18002b877  mov     r9d, eax; char *
0x18002b87a  lea     r8, aPcshellShellRe; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b881  mov     edx, 1Ch; void *
0x18002b886  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b88c  lea     rcx, [rbp+var_20]
0x18002b890  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b895  mov     [rbp+hKey], 0
0x18002b89d  lea     rax, [rbp+hKey]
0x18002b8a1  mov     [rbp+var_18], rax
0x18002b8a5  mov     [rbp+var_10], 0
0x18002b8ad  mov     [rbp+var_8], 1
0x18002b8b1  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18002b8ba  lea     rax, [rbp+var_10]
0x18002b8be  mov     [rsp+70h+phkResult], rax; phkResult
0x18002b8c3  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002b8cc  mov     [rsp+70h+samDesired], 2; samDesired
0x18002b8d4  mov     [rsp+70h+dwOptions], 0; unsigned int
0x18002b8dc  xor     r9d, r9d; lpClass
0x18002b8df  xor     r8d, r8d; Reserved
0x18002b8e2  lea     rdx, ?c_retailDemoKeyPinnedToTaskbarDefaultApplist@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002b8e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b8f0  call    cs:__imp_RegCreateKeyExW
0x18002b8f6  mov     rcx, [rbp+8]; this
0x18002b8fa  test    eax, eax
0x18002b8fc  jz      short loc_18002B913
0x18002b8fe  mov     r9d, eax; char *
0x18002b901  lea     r8, aPcshellShellRe; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b908  mov     edx, 20h ; ' '; void *
0x18002b90d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002b913  lea     rcx, [rbp+var_18]
0x18002b917  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002b91c  xor     ebx, ebx
0x18002b91e  mov     eax, [rbp+arg_8]
0x18002b921  test    eax, eax
0x18002b923  jz      short loc_18002B962
0x18002b925  mov     [rsp+70h+samDesired], 0; cbData
0x18002b92d  mov     qword ptr [rsp+70h+dwOptions], 0; unsigned int
0x18002b936  mov     r9d, 1; dwType
0x18002b93c  xor     r8d, r8d; Reserved
0x18002b93f  mov     rdx, [rbp+arg_10]
0x18002b943  mov     rdx, [rdx+rbx*8]; lpValueName
0x18002b947  mov     rcx, [rbp+hKey]; hKey
0x18002b94b  call    cs:__imp_RegSetValueExW
0x18002b951  mov     rcx, [rbp+8]; this
0x18002b955  test    eax, eax
0x18002b957  jnz     short loc_18002B985
0x18002b959  inc     ebx
0x18002b95b  mov     eax, [rbp+arg_8]
0x18002b95e  cmp     ebx, eax
0x18002b960  jb      short loc_18002B925
0x18002b962  mov     edx, eax
0x18002b964  mov     rcx, [rbp+arg_10]
0x18002b968  call    ??$SHCoFreeArray@G@@YAXPEAPEAG_K@Z; SHCoFreeArray<ushort>(ushort * *,unsigned __int64)
0x18002b96d  nop
0x18002b96e  lea     rcx, [rbp+hKey]
0x18002b972  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b977  mov     rbx, [rsp+70h+arg_0]
0x18002b97f  add     rsp, 70h
0x18002b983  pop     rbp
0x18002b984  retn
0x18002b985  mov     r9d, eax; char *
0x18002b988  lea     r8, aPcshellShellRe; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b98f  mov     edx, 23h ; '#'; void *
0x18002b994  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
