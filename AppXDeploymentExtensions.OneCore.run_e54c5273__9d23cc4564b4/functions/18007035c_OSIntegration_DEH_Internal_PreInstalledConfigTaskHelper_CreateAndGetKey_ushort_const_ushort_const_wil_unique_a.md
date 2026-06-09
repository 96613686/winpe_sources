# OSIntegration::DEH::Internal::PreInstalledConfigTaskHelper::CreateAndGetKey(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x18007035c`
- end: `0x180070527`
- name: `?CreateAndGetKey@PreInstalledConfigTaskHelper@Internal@DEH@OSIntegration@@CAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `459`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18013d4e0`

## callees

- `0x18007035c`
- `0x180070b78`
- `0x180087238`
- `0x180098bf4`
- `0x1800a2854`
- `0x18013d6b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800704c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800704cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800704de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800704c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800704cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800704de`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800703f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070450`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070493`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800703f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070450`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180070493`

## string_xrefs

- `0x180070427`: `Software\Microsoft\Windows NT\CurrentVersion\BackgroundModel\PreInstallTasks\RequireReschedule`
- `0x1800703a3`: `onecore\admin\appmodel\osim\src\deh\uex\preinstalledconfigtask\preinstalledconfigtaskhelper.cpp`
- `0x180070404`: `onecore\admin\appmodel\osim\src\deh\uex\preinstalledconfigtask\preinstalledconfigtaskhelper.cpp`
- `0x1800704a1`: `onecore\admin\appmodel\osim\src\deh\uex\preinstalledconfigtask\preinstalledconfigtaskhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::Internal::PreInstalledConfigTaskHelper::CreateAndGetKey(
        LPCWSTR lpSubKey,
        LPCWSTR a2,
        __int64 a3)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  __int64 v10; // rdx
  HKEY *v11; // rax
  HKEY *v12; // rax
  unsigned int v13; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-40h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-40h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-40h]
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HKEY v20; // [rsp+80h] [rbp+20h] BYREF
  HKEY v21; // [rsp+98h] [rbp+38h] BYREF

  hKey[0] = 0;
  v21 = 0;
  v20 = 0;
  if ( !lpSubKey )
  {
    v6 = 404;
LABEL_5:
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\preinstalledconfigtask\\preinstalledconfigtaskhelper.cpp",
      (const char *)0x80070057LL,
      dwOptions);
LABEL_19:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    return v7;
  }
  if ( !a2 )
  {
    v6 = 405;
    goto LABEL_5;
  }
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  Key = RegCreateKeyExW(HKEY_USERS, lpSubKey, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  if ( Key )
  {
    v10 = 415;
LABEL_8:
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\preinstalledconfigtask\\preinstalledconfigtaskhelper.cpp",
           (const char *)Key,
           dwOptionsa);
    goto LABEL_19;
  }
  v11 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v21);
  Key = RegCreateKeyExW(
          hKey[0],
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\BackgroundModel\\PreInstallTasks\\RequireReschedule",
          0,
          0,
          0,
          0xF003Fu,
          0,
          v11,
          0);
  if ( Key )
  {
    v10 = 425;
    goto LABEL_8;
  }
  v12 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v20);
  v13 = RegCreateKeyExW(v21, a2, 0, 0, 0, 0xF003Fu, 0, v12, 0);
  if ( !v13 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::swap(
      a3,
      &v20);
    v7 = 0;
    goto LABEL_19;
  }
  v7 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x1B3,
         (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\preinstalledconfigtask\\preinstalledconfigtaskhelper.cpp",
         (const char *)v13,
         dwOptionsb);
  if ( v20 )
    RegCloseKey(v20);
  if ( v21 )
    RegCloseKey(v21);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v7;
}

```

## disassembly

```asm
0x18007035c  mov     [rsp-18h+arg_8], rbx
0x180070361  mov     [rsp-18h+arg_10], rsi
0x180070366  push    rbp
0x180070367  push    rdi
0x180070368  push    r14
0x18007036a  mov     rbp, rsp
0x18007036d  sub     rsp, 60h
0x180070371  xor     r14d, r14d
0x180070374  mov     rsi, r8
0x180070377  mov     [rbp+hKey], r14
0x18007037b  mov     rbx, rdx
0x18007037e  mov     [rbp+arg_18], r14
0x180070382  mov     rdi, rcx
0x180070385  mov     [rbp+arg_0], r14
0x180070389  test    rcx, rcx
0x18007038c  jnz     short loc_180070395
0x18007038e  mov     edx, 194h
0x180070393  jmp     short loc_18007039F
0x180070395  test    rbx, rbx
0x180070398  jnz     short loc_1800703BC
0x18007039a  mov     edx, 195h; void *
0x18007039f  mov     rcx, [rbp+18h]; this
0x1800703a3  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800703aa  mov     ebx, 80070057h
0x1800703af  mov     r9d, ebx; char *
0x1800703b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800703b7  jmp     loc_1800704F5
0x1800703bc  lea     rcx, [rbp+hKey]
0x1800703c0  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800703c5  mov     [rsp+60h+lpdwDisposition], r14; lpdwDisposition
0x1800703ca  xor     r9d, r9d; lpClass
0x1800703cd  mov     [rsp+60h+phkResult], rax; phkResult
0x1800703d2  xor     r8d, r8d; Reserved
0x1800703d5  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800703da  mov     rdx, rdi; lpSubKey
0x1800703dd  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x1800703e5  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800703ec  mov     [rsp+60h+dwOptions], r14d; unsigned int
0x1800703f1  call    cs:__imp_RegCreateKeyExW
0x1800703f7  test    eax, eax
0x1800703f9  jz      short loc_18007041A
0x1800703fb  mov     edx, 19Fh; void *
0x180070400  mov     rcx, [rbp+18h]; this
0x180070404  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18007040b  mov     r9d, eax; char *
0x18007040e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180070413  mov     ebx, eax
0x180070415  jmp     loc_1800704F5
0x18007041a  lea     rcx, [rbp+arg_18]
0x18007041e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180070423  mov     rcx, [rbp+hKey]; hKey
0x180070427  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18007042e  mov     [rsp+60h+lpdwDisposition], r14; lpdwDisposition
0x180070433  xor     r9d, r9d; lpClass
0x180070436  mov     [rsp+60h+phkResult], rax; phkResult
0x18007043b  xor     r8d, r8d; Reserved
0x18007043e  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180070443  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18007044b  mov     [rsp+60h+dwOptions], r14d; dwOptions
0x180070450  call    cs:__imp_RegCreateKeyExW
0x180070456  test    eax, eax
0x180070458  jz      short loc_180070461
0x18007045a  mov     edx, 1A9h
0x18007045f  jmp     short loc_180070400
0x180070461  lea     rcx, [rbp+arg_0]
0x180070465  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18007046a  mov     rcx, [rbp+arg_18]; hKey
0x18007046e  xor     r9d, r9d; lpClass
0x180070471  mov     [rsp+60h+lpdwDisposition], r14; lpdwDisposition
0x180070476  xor     r8d, r8d; Reserved
0x180070479  mov     [rsp+60h+phkResult], rax; phkResult
0x18007047e  mov     rdx, rbx; lpSubKey
0x180070481  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180070486  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18007048e  mov     [rsp+60h+dwOptions], r14d; unsigned int
0x180070493  call    cs:__imp_RegCreateKeyExW
0x180070499  test    eax, eax
0x18007049b  jz      short loc_1800704E6
0x18007049d  mov     rcx, [rbp+18h]; this
0x1800704a1  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800704a8  mov     r9d, eax; char *
0x1800704ab  mov     edx, 1B3h; void *
0x1800704b0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800704b5  mov     rcx, [rbp+arg_0]; hKey
0x1800704b9  mov     ebx, eax
0x1800704bb  test    rcx, rcx
0x1800704be  jz      short loc_1800704C6
0x1800704c0  call    cs:__imp_RegCloseKey
0x1800704c6  mov     rcx, [rbp+arg_18]; hKey
0x1800704ca  test    rcx, rcx
0x1800704cd  jz      short loc_1800704D5
0x1800704cf  call    cs:__imp_RegCloseKey
0x1800704d5  mov     rcx, [rbp+hKey]; hKey
0x1800704d9  test    rcx, rcx
0x1800704dc  jz      short loc_180070510
0x1800704de  call    cs:__imp_RegCloseKey
0x1800704e4  jmp     short loc_180070510
0x1800704e6  lea     rdx, [rbp+arg_0]
0x1800704ea  mov     rcx, rsi
0x1800704ed  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x1800704f2  mov     ebx, r14d
0x1800704f5  lea     rcx, [rbp+arg_0]
0x1800704f9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800704fe  lea     rcx, [rbp+arg_18]
0x180070502  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180070507  lea     rcx, [rbp+hKey]
0x18007050b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180070510  lea     r11, [rsp+60h+var_s0]
0x180070515  mov     eax, ebx
0x180070517  mov     rbx, [r11+28h]
0x18007051b  mov     rsi, [r11+30h]
0x18007051f  mov     rsp, r11
0x180070522  pop     r14
0x180070524  pop     rdi
0x180070525  pop     rbp
0x180070526  retn
```
