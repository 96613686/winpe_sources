# LockscreenBackupRestoreHandler::EnableSpotlight(void)

- ea: `0x1800bd330`
- end: `0x1800bd5be`
- name: `?EnableSpotlight@LockscreenBackupRestoreHandler@@AEAAXXZ`
- size: `654`
- prototype: `void __fastcall(LockscreenBackupRestoreHandler *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800be530`

## callees

- `0x1800161ec`
- `0x1800162a4`
- `0x18001666c`
- `0x18001cfa4`
- `0x18001da4c`
- `0x18002498c`
- `0x1800bb21c`
- `0x1800bbc54`
- `0x1800bd330`
- `0x1800bdc9c`
- `0x1800be928`
- `0x1800bee54`
- `0x1800bf3dc`

## import_xrefs

- `ADVAPI32!RegSetKeyValueW` at `0x1800bd407`
- `ADVAPI32!RegSetKeyValueW` at `0x1800bd4af`
- `ADVAPI32!RegSetKeyValueW` at `0x1800bd407`
- `ADVAPI32!RegSetKeyValueW` at `0x1800bd4af`
- `ADVAPI32!RegCreateKeyExW` at `0x1800bd3d1`
- `ADVAPI32!RegCreateKeyExW` at `0x1800bd479`
- `ADVAPI32!RegCreateKeyExW` at `0x1800bd3d1`
- `ADVAPI32!RegCreateKeyExW` at `0x1800bd479`

## pseudocode

```c
void __fastcall LockscreenBackupRestoreHandler::EnableSpotlight(LockscreenBackupRestoreHandler *this)
{
  int CurrentUserSidString; // eax
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  int dwOptions; // [rsp+20h] [rbp-19h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-19h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-19h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-19h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-19h]
  HKEY phkResult; // [rsp+50h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+1Fh] BYREF
  LPCWSTR v13; // [rsp+60h] [rbp+27h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp+2Fh] BYREF
  _BYTE v15[32]; // [rsp+70h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]
  int Data; // [rsp+A0h] [rbp+67h] BYREF
  int Data_4; // [rsp+A4h] [rbp+6Bh]
  int v19; // [rsp+A8h] [rbp+6Fh] BYREF
  LPWSTR StringSid; // [rsp+B0h] [rbp+77h] BYREF
  char v21; // [rsp+B8h] [rbp+7Fh] BYREF

  Data_4 = HIDWORD(this);
  Data = 1;
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  CurrentUserSidString = GetCurrentUserSidString(&StringSid);
  if ( CurrentUserSidString < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)(unsigned int)CurrentUserSidString,
      dwOptions);
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpSubKey,
    L"%s\\%s",
    StringSid,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager");
  hKey = 0;
  v2 = RegCreateKeyExW(HKEY_USERS, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v2 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x61,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)v2,
      dwOptionsa);
  v3 = RegSetKeyValueW(hKey, 0, L"RotatingLockScreenEnabled", 4u, &Data, 4u);
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x63,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)v3,
      dwOptionsb);
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v13,
    L"%s\\%s",
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Creative",
    StringSid);
  phkResult = 0;
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x6B,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)v4,
      dwOptionsc);
  v5 = RegSetKeyValueW(phkResult, 0, L"RotatingLockScreenEnabled", 4u, &Data, 4u);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x6D,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)v5,
      dwOptionsd);
  winrt::Windows::Services::TargetedContent::Internal::TargetedContentSubscriptionInternal::TargetedContentSubscriptionInternal((winrt::Windows::Services::TargetedContent::Internal::TargetedContentSubscriptionInternal *)&v21);
  v19 = 1;
  winrt::param::hstring::hstring((winrt::param::hstring *)v15, L"Locksreen");
  winrt::impl::consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal<winrt::Windows::Services::TargetedContent::Internal::ITargetedContentSubscriptionInternal>::SetSubscriptionConfiguration(
    &v21,
    v15,
    &v19);
  winrt::param::hstring::hstring((winrt::param::hstring *)v15, L"Locksreen");
  winrt::impl::consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal<winrt::Windows::Services::TargetedContent::Internal::ITargetedContentSubscriptionInternal>::ReactivateSubscription(
    &v21,
    v15);
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v21);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v13);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&StringSid);
}

```

## disassembly

```asm
0x1800bd330  mov     [rsp-8+Data], rcx
0x1800bd335  push    rbp
0x1800bd336  lea     rbp, [rsp-57h]
0x1800bd33b  sub     rsp, 90h
0x1800bd342  mov     dword ptr [rbp+57h+Data], 1
0x1800bd349  mov     [rbp+57h+StringSid], 0
0x1800bd351  xor     edx, edx
0x1800bd353  lea     rcx, [rbp+57h+StringSid]
0x1800bd357  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800bd35c  lea     rcx, [rbp+57h+StringSid]; StringSid
0x1800bd360  call    ?GetCurrentUserSidString@@YAJPEAPEAG@Z; GetCurrentUserSidString(ushort * *)
0x1800bd365  mov     rcx, [rbp+5Fh]; this
0x1800bd369  test    eax, eax
0x1800bd36b  js      loc_1800BD56A
0x1800bd371  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800bd378  mov     r8, [rbp+57h+StringSid]
0x1800bd37c  lea     rdx, aSS; "%s\\%s"
0x1800bd383  lea     rcx, [rbp+57h+lpSubKey]
0x1800bd387  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x1800bd38c  nop
0x1800bd38d  mov     [rbp+57h+hKey], 0
0x1800bd395  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x1800bd39e  lea     rax, [rbp+57h+hKey]
0x1800bd3a2  mov     [rsp+90h+phkResult], rax; phkResult
0x1800bd3a7  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800bd3b0  mov     [rsp+90h+samDesired], 0F003Fh; samDesired
0x1800bd3b8  mov     [rsp+90h+dwOptions], 0; unsigned int
0x1800bd3c0  xor     r9d, r9d; lpClass
0x1800bd3c3  xor     r8d, r8d; Reserved
0x1800bd3c6  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800bd3ca  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800bd3d1  call    cs:__imp_RegCreateKeyExW
0x1800bd3d7  mov     rcx, [rbp+5Fh]; this
0x1800bd3db  test    eax, eax
0x1800bd3dd  jnz     loc_1800BD57F
0x1800bd3e3  mov     [rsp+90h+samDesired], 4; cbData
0x1800bd3eb  lea     rax, [rbp+57h+Data]
0x1800bd3ef  mov     qword ptr [rsp+90h+dwOptions], rax; unsigned int
0x1800bd3f4  mov     r9d, 4; dwType
0x1800bd3fa  lea     r8, aRotatinglocksc_0; "RotatingLockScreenEnabled"
0x1800bd401  xor     edx, edx; lpSubKey
0x1800bd403  mov     rcx, [rbp+57h+hKey]; hKey
0x1800bd407  call    cs:__imp_RegSetKeyValueW
0x1800bd40d  mov     rcx, [rbp+5Fh]; this
0x1800bd411  test    eax, eax
0x1800bd413  jnz     loc_1800BD594
0x1800bd419  mov     r9, [rbp+57h+StringSid]
0x1800bd41d  lea     r8, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800bd424  lea     rdx, aSS; "%s\\%s"
0x1800bd42b  lea     rcx, [rbp+57h+var_30]
0x1800bd42f  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x1800bd434  nop
0x1800bd435  mov     [rbp+57h+var_40], 0
0x1800bd43d  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x1800bd446  lea     rax, [rbp+57h+var_40]
0x1800bd44a  mov     [rsp+90h+phkResult], rax; phkResult
0x1800bd44f  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800bd458  mov     [rsp+90h+samDesired], 0F003Fh; samDesired
0x1800bd460  mov     [rsp+90h+dwOptions], 0; unsigned int
0x1800bd468  xor     r9d, r9d; lpClass
0x1800bd46b  xor     r8d, r8d; Reserved
0x1800bd46e  mov     rdx, [rbp+57h+var_30]; lpSubKey
0x1800bd472  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bd479  call    cs:__imp_RegCreateKeyExW
0x1800bd47f  mov     rcx, [rbp+5Fh]; this
0x1800bd483  test    eax, eax
0x1800bd485  jnz     loc_1800BD5A9
0x1800bd48b  mov     [rsp+90h+samDesired], 4; cbData
0x1800bd493  lea     rax, [rbp+57h+Data]
0x1800bd497  mov     qword ptr [rsp+90h+dwOptions], rax; unsigned int
0x1800bd49c  mov     r9d, 4; dwType
0x1800bd4a2  lea     r8, aRotatinglocksc_0; "RotatingLockScreenEnabled"
0x1800bd4a9  xor     edx, edx; lpSubKey
0x1800bd4ab  mov     rcx, [rbp+57h+var_40]; hKey
0x1800bd4af  call    cs:__imp_RegSetKeyValueW
0x1800bd4b5  mov     rcx, [rbp+5Fh]; this
0x1800bd4b9  test    eax, eax
0x1800bd4bb  jnz     loc_1800BD555
0x1800bd4c1  lea     rcx, [rbp+57h+arg_18]; this
0x1800bd4c5  call    ??0TargetedContentSubscriptionInternal@Internal@TargetedContent@Services@Windows@winrt@@QEAA@XZ; winrt::Windows::Services::TargetedContent::Internal::TargetedContentSubscriptionInternal::TargetedContentSubscriptionInternal(void)
0x1800bd4ca  nop
0x1800bd4cb  mov     [rbp+57h+arg_8], 1
0x1800bd4d2  lea     rdx, aLocksreen; "Locksreen"
0x1800bd4d9  lea     rcx, [rbp+57h+var_20]; this
0x1800bd4dd  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800bd4e2  lea     r8, [rbp+57h+arg_8]
0x1800bd4e6  lea     rdx, [rbp+57h+var_20]
0x1800bd4ea  lea     rcx, [rbp+57h+arg_18]
0x1800bd4ee  call    ?SetSubscriptionConfiguration@?$consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal@UITargetedContentSubscriptionInternal@Internal@TargetedContent@Services@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBW4TargetedContentConfigurationKinds@Internal@TargetedContent@Services@Windows@3@@Z; winrt::impl::consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal<winrt::Windows::Services::TargetedContent::Internal::ITargetedContentSubscriptionInternal>::SetSubscriptionConfiguration(winrt::param::hstring const &,winrt::Windows::Services::TargetedContent::Internal::TargetedContentConfigurationKinds const &)
0x1800bd4f3  lea     rdx, aLocksreen; "Locksreen"
0x1800bd4fa  lea     rcx, [rbp+57h+var_20]; this
0x1800bd4fe  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800bd503  lea     rdx, [rbp+57h+var_20]
0x1800bd507  lea     rcx, [rbp+57h+arg_18]
0x1800bd50b  call    ?ReactivateSubscription@?$consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal@UITargetedContentSubscriptionInternal@Internal@TargetedContent@Services@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal<winrt::Windows::Services::TargetedContent::Internal::ITargetedContentSubscriptionInternal>::ReactivateSubscription(winrt::param::hstring const &)
0x1800bd510  nop
0x1800bd511  lea     rcx, [rbp+57h+arg_18]; this
0x1800bd515  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800bd51a  nop
0x1800bd51b  lea     rcx, [rbp+57h+var_40]
0x1800bd51f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bd524  nop
0x1800bd525  lea     rcx, [rbp+57h+var_30]
0x1800bd529  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800bd52e  nop
0x1800bd52f  lea     rcx, [rbp+57h+hKey]
0x1800bd533  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bd538  nop
0x1800bd539  lea     rcx, [rbp+57h+lpSubKey]
0x1800bd53d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800bd542  nop
0x1800bd543  lea     rcx, [rbp+57h+StringSid]
0x1800bd547  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800bd54c  add     rsp, 90h
0x1800bd553  pop     rbp
0x1800bd554  retn
0x1800bd555  mov     r9d, eax; char *
0x1800bd558  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bd55f  mov     edx, 6Dh ; 'm'; void *
0x1800bd564  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800bd56a  mov     r9d, eax; char *
0x1800bd56d  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bd574  mov     edx, 5Ah ; 'Z'; void *
0x1800bd579  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bd57f  mov     r9d, eax; char *
0x1800bd582  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bd589  mov     edx, 61h ; 'a'; void *
0x1800bd58e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800bd594  mov     r9d, eax; char *
0x1800bd597  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bd59e  mov     edx, 63h ; 'c'; void *
0x1800bd5a3  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800bd5a9  mov     r9d, eax; char *
0x1800bd5ac  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bd5b3  mov     edx, 6Bh ; 'k'; void *
0x1800bd5b8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
