# SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveUISettingsToNtUserFile(HKEY__ *)

- ea: `0x14004435c`
- end: `0x1400445e9`
- name: `?IntlSaveUISettingsToNtUserFile@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEAUHKEY__@@@Z`
- size: `653`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1400437e4`

## callees

- `0x140004e68`
- `0x140005f30`
- `0x14000ed38`
- `0x14002996c`
- `0x14002c070`
- `0x140043d64`
- `0x140043ea4`
- `0x140044000`
- `0x14004435c`
- `0x140044b1c`

## import_xrefs

- `KERNEL32!RegCreateKeyExW` at `0x140044503`
- `KERNEL32!RegCreateKeyExW` at `0x140044503`
- `KERNEL32!RegSetValueExW` at `0x1400444a3`
- `KERNEL32!RegSetValueExW` at `0x140044573`
- `KERNEL32!RegSetValueExW` at `0x1400444a3`
- `KERNEL32!RegSetValueExW` at `0x140044573`

## string_xrefs

- `0x1400444df`: `LanguageConfiguration`
- `0x1400443e4`: `pcshell\shell\systemsettings\adminflows\languagemanager\lib\copycurrentusersettings.cpp`
- `0x14004444a`: `pcshell\shell\systemsettings\adminflows\languagemanager\lib\copycurrentusersettings.cpp`
- `0x140044595`: `pcshell\shell\systemsettings\adminflows\languagemanager\lib\copycurrentusersettings.cpp`

## pseudocode

```c
void __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlSaveUISettingsToNtUserFile(HKEY hKey)
{
  __int64 v2; // rdi
  const unsigned __int16 *v3; // rcx
  int v4; // r8d
  HKEY v5; // rbx
  __int64 v6; // rcx
  WCHAR *v7; // rax
  unsigned __int16 *v8; // rax
  __int64 v9; // r9
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rax
  int v14; // eax
  bool v15; // sf
  HKEY *phkResult; // rax
  int v17; // eax
  int v18; // r9d
  bool v19; // sf
  __int64 v20; // rdx
  unsigned __int64 cbData; // rdx
  const unsigned __int16 *v22; // rcx
  bool v23; // sf
  int lpData; // [rsp+20h] [rbp-E0h]
  int lpDataa; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v26[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-A8h] BYREF
  HKEY NtUserHive; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Data[352]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v31[352]; // [rsp+330h] [rbp+230h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+618h] [rbp+518h]

  v2 = 700;
  v26[0] = 0;
  memset_0(Data, 0, 0x2BCu);
  memset_0(v31, 0, 0x2BCu);
  dwDisposition = 0;
  NtUserHive = SystemSettings::DataModel::CopyCurrentUserSettings::IntlLoadNtUserHive(
                 v3,
                 L"Control Panel\\Desktop",
                 v26);
  v5 = NtUserHive;
  if ( NtUserHive )
  {
    v6 = 700;
    v7 = Data;
    do
    {
      *(_BYTE *)v7 = 0;
      v7 = (WCHAR *)((char *)v7 + 1);
      --v6;
    }
    while ( v6 );
    v8 = v31;
    do
    {
      *(_BYTE *)v8 = 0;
      v8 = (unsigned __int16 *)((char *)v8 + 1);
      --v2;
    }
    while ( v2 );
    if ( !(unsigned int)SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILanguage(hKey, Data, v4) )
    {
      v9 = 2147500037LL;
      v10 = 343;
LABEL_9:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\copycurrentusersettings.cpp",
        (const char *)v9,
        lpData);
      SystemSettings::DataModel::CopyCurrentUserSettings::IntlUnloadNtUserHive(v11, v26);
      goto LABEL_29;
    }
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( Data[v13] );
    v14 = RegSetValueExW(v5, L"PreferredUILanguages", 0, 7u, (const BYTE *)Data, 2 * v13 + 2);
    v15 = v14 < 0;
    if ( v14 > 0 )
    {
      v14 = (unsigned __int16)v14 | 0x80070000;
      v15 = v14 < 0;
    }
    if ( v15 )
    {
      v9 = (unsigned int)v14;
      v10 = 355;
      goto LABEL_9;
    }
    hKeya = 0;
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKeya);
    v17 = RegCreateKeyExW(v5, L"LanguageConfiguration", 0, 0, 0, 0x20006u, 0, phkResult, &dwDisposition);
    v19 = v17 < 0;
    if ( v17 > 0 )
    {
      v17 = (unsigned __int16)v17 | 0x80070000;
      v19 = v17 < 0;
    }
    if ( v19 )
    {
      v20 = 371;
    }
    else
    {
      cbData = SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILangConfig(hKey, Data, v31, v18);
      do
        ++v12;
      while ( v31[v12] );
      v22 = (const unsigned __int16 *)(2 * v12);
      if ( cbData <= 2 * v12 )
        goto LABEL_28;
      v17 = RegSetValueExW(hKeya, Data, 0, 7u, (const BYTE *)v31, cbData);
      v23 = v17 < 0;
      if ( v17 > 0 )
      {
        v17 = (unsigned __int16)v17 | 0x80070000;
        v23 = v17 < 0;
      }
      if ( !v23 )
        goto LABEL_28;
      v20 = 387;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\copycurrentusersettings.cpp",
      (const char *)(unsigned int)v17,
      lpDataa);
LABEL_28:
    SystemSettings::DataModel::CopyCurrentUserSettings::IntlUnloadNtUserHive(v22, v26);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
    goto LABEL_29;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x14F,
    (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\copycurrentusersettings.cpp",
    (const char *)0x80004005LL,
    lpData);
LABEL_29:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&NtUserHive);
}

```

## disassembly

```asm
0x14004435c  mov     [rsp-8+arg_8], rbx
0x140044361  mov     [rsp-8+arg_10], rsi
0x140044366  push    rbp
0x140044367  push    rdi
0x140044368  push    r14
0x14004436a  lea     rbp, [rsp-500h]
0x140044372  sub     rsp, 600h
0x140044379  mov     rax, cs:__security_cookie
0x140044380  xor     rax, rsp
0x140044383  mov     [rbp+510h+var_20], rax
0x14004438a  mov     rsi, rcx
0x14004438d  mov     edi, 2BCh
0x140044392  xor     r14d, r14d
0x140044395  lea     rcx, [rsp+610h+Data]; void *
0x14004439a  mov     r8d, edi; Size
0x14004439d  mov     [rsp+610h+var_5C0], r14b
0x1400443a2  xor     edx, edx; Val
0x1400443a4  call    memset_0
0x1400443a9  mov     r8d, edi; Size
0x1400443ac  lea     rcx, [rbp+510h+var_2E0]; void *
0x1400443b3  xor     edx, edx; Val
0x1400443b5  call    memset_0
0x1400443ba  lea     r8, [rsp+610h+var_5C0]; unsigned __int8 *
0x1400443bf  mov     [rsp+610h+dwDisposition], r14d
0x1400443c4  lea     rdx, aControlPanelDe_1; "Control Panel\\Desktop"
0x1400443cb  call    ?IntlLoadNtUserHive@CopyCurrentUserSettings@DataModel@SystemSettings@@CAPEAUHKEY__@@PEBG0PEAE@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlLoadNtUserHive(ushort const *,ushort const *,uchar *)
0x1400443d0  mov     [rsp+610h+var_5B0], rax
0x1400443d5  mov     rbx, rax
0x1400443d8  test    rax, rax
0x1400443db  jnz     short loc_140044400
0x1400443dd  mov     rcx, [rbp+518h]; this
0x1400443e4  lea     r8, aPcshellShellSy_33; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400443eb  mov     r9d, 80004005h; char *
0x1400443f1  mov     edx, 14Fh; void *
0x1400443f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400443fb  jmp     loc_1400445B8
0x140044400  mov     rcx, rdi
0x140044403  lea     rax, [rsp+610h+Data]
0x140044408  mov     [rax], r14b
0x14004440b  inc     rax
0x14004440e  sub     rcx, 1
0x140044412  jnz     short loc_140044408
0x140044414  lea     rax, [rbp+510h+var_2E0]
0x14004441b  mov     [rax], r14b
0x14004441e  inc     rax
0x140044421  sub     rdi, 1
0x140044425  jnz     short loc_14004441B
0x140044427  lea     rdx, [rsp+610h+Data]; unsigned __int16 *
0x14004442c  mov     rcx, rsi; hKey
0x14004442f  call    ?IntlGetUserUILanguage@CopyCurrentUserSettings@DataModel@SystemSettings@@CAHPEAUHKEY__@@PEAGH@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILanguage(HKEY__ *,ushort *,int)
0x140044434  test    eax, eax
0x140044436  jnz     short loc_140044465
0x140044438  mov     r9d, 80004005h; char *
0x14004443e  mov     edx, 157h; void *
0x140044443  mov     rcx, [rbp+518h]; this
0x14004444a  lea     r8, aPcshellShellSy_33; "pcshell\\shell\\systemsettings\\adminfl"...
0x140044451  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140044456  lea     rdx, [rsp+610h+var_5C0]; unsigned __int8 *
0x14004445b  call    ?IntlUnloadNtUserHive@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEBGPEAE@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlUnloadNtUserHive(ushort const *,uchar *)
0x140044460  jmp     loc_1400445B8
0x140044465  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140044469  lea     rcx, [rsp+610h+Data]
0x14004446e  mov     rax, rdi
0x140044471  inc     rax
0x140044474  cmp     [rcx+rax*2], r14w
0x140044479  jnz     short loc_140044471
0x14004447b  lea     eax, ds:2[rax*2]
0x140044482  mov     r9d, 7; dwType
0x140044488  mov     [rsp+610h+cbData], eax; cbData
0x14004448c  lea     rdx, aPreferreduilan; "PreferredUILanguages"
0x140044493  lea     rax, [rsp+610h+Data]
0x140044498  xor     r8d, r8d; Reserved
0x14004449b  mov     rcx, rbx; hKey
0x14004449e  mov     [rsp+610h+lpData], rax; lpData
0x1400444a3  call    cs:__imp_RegSetValueExW
0x1400444a9  test    eax, eax
0x1400444ab  jle     short loc_1400444B7
0x1400444ad  movzx   eax, ax
0x1400444b0  or      eax, 80070000h
0x1400444b5  test    eax, eax
0x1400444b7  jns     short loc_1400444C3
0x1400444b9  mov     r9d, eax
0x1400444bc  mov     edx, 163h
0x1400444c1  jmp     short loc_140044443
0x1400444c3  lea     rcx, [rsp+610h+hKey]
0x1400444c8  mov     [rsp+610h+hKey], r14
0x1400444cd  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400444d2  lea     rcx, [rsp+610h+dwDisposition]
0x1400444d7  xor     r9d, r9d; lpClass
0x1400444da  mov     [rsp+610h+lpdwDisposition], rcx; lpdwDisposition
0x1400444df  lea     rdx, aLanguageconfig; "LanguageConfiguration"
0x1400444e6  mov     [rsp+610h+phkResult], rax; phkResult
0x1400444eb  xor     r8d, r8d; Reserved
0x1400444ee  mov     [rsp+610h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1400444f3  mov     rcx, rbx; hKey
0x1400444f6  mov     [rsp+610h+cbData], 20006h; samDesired
0x1400444fe  mov     dword ptr [rsp+610h+lpData], r14d; dwOptions
0x140044503  call    cs:__imp_RegCreateKeyExW
0x140044509  test    eax, eax
0x14004450b  jle     short loc_140044517
0x14004450d  movzx   eax, ax
0x140044510  or      eax, 80070000h
0x140044515  test    eax, eax
0x140044517  jns     short loc_140044520
0x140044519  mov     edx, 173h
0x14004451e  jmp     short loc_14004458E
0x140044520  lea     r8, [rbp+510h+var_2E0]; Destination
0x140044527  mov     rcx, rsi; hKey
0x14004452a  lea     rdx, [rsp+610h+Data]; lpValueName
0x14004452f  call    ?IntlGetUserUILangConfig@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEAUHKEY__@@PEAG1H@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILangConfig(HKEY__ *,ushort *,ushort *,int)
0x140044534  mov     edx, eax
0x140044536  lea     rax, [rbp+510h+var_2E0]
0x14004453d  inc     rdi
0x140044540  cmp     [rax+rdi*2], r14w
0x140044545  jnz     short loc_14004453D
0x140044547  lea     rcx, [rdi+rdi]
0x14004454b  cmp     rdx, rcx
0x14004454e  jbe     short loc_1400445A4
0x140044550  mov     rcx, [rsp+610h+hKey]; hKey
0x140044555  lea     rax, [rbp+510h+var_2E0]
0x14004455c  mov     [rsp+610h+cbData], edx; cbData
0x140044560  mov     r9d, 7; dwType
0x140044566  lea     rdx, [rsp+610h+Data]; lpValueName
0x14004456b  mov     [rsp+610h+lpData], rax; int
0x140044570  xor     r8d, r8d; Reserved
0x140044573  call    cs:__imp_RegSetValueExW
0x140044579  test    eax, eax
0x14004457b  jle     short loc_140044587
0x14004457d  movzx   eax, ax
0x140044580  or      eax, 80070000h
0x140044585  test    eax, eax
0x140044587  jns     short loc_1400445A4
0x140044589  mov     edx, 183h; void *
0x14004458e  mov     rcx, [rbp+518h]; this
0x140044595  lea     r8, aPcshellShellSy_33; "pcshell\\shell\\systemsettings\\adminfl"...
0x14004459c  mov     r9d, eax; char *
0x14004459f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400445a4  lea     rdx, [rsp+610h+var_5C0]; unsigned __int8 *
0x1400445a9  call    ?IntlUnloadNtUserHive@CopyCurrentUserSettings@DataModel@SystemSettings@@CAXPEBGPEAE@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlUnloadNtUserHive(ushort const *,uchar *)
0x1400445ae  lea     rcx, [rsp+610h+hKey]
0x1400445b3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400445b8  lea     rcx, [rsp+610h+var_5B0]
0x1400445bd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400445c2  mov     rcx, [rbp+510h+var_20]
0x1400445c9  xor     rcx, rsp; StackCookie
0x1400445cc  call    __security_check_cookie
0x1400445d1  lea     r11, [rsp+610h+var_10]
0x1400445d9  mov     rbx, [r11+28h]
0x1400445dd  mov     rsi, [r11+30h]
0x1400445e1  mov     rsp, r11
0x1400445e4  pop     r14
0x1400445e6  pop     rdi
0x1400445e7  pop     rbp
0x1400445e8  retn
```
