# LockscreenBackupRestoreHandler::ApplyLockscreenFunFactsAndMore(bool)

- ea: `0x1800bc5ac`
- end: `0x1800bc86e`
- name: `?ApplyLockscreenFunFactsAndMore@LockscreenBackupRestoreHandler@@AEAAX_N@Z`
- size: `706`
- prototype: `void __fastcall(LockscreenBackupRestoreHandler *this, unsigned __int8)`
- caller_count: `1`
- callee_count: `14`
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
- `0x1800a0f70`
- `0x1800bb21c`
- `0x1800bbc54`
- `0x1800bc5ac`
- `0x1800bdc9c`
- `0x1800be928`
- `0x1800bee54`
- `0x1800bf3dc`

## import_xrefs

- `ADVAPI32!RegSetKeyValueW` at `0x1800bc6a8`
- `ADVAPI32!RegSetKeyValueW` at `0x1800bc749`
- `ADVAPI32!RegSetKeyValueW` at `0x1800bc6a8`
- `ADVAPI32!RegSetKeyValueW` at `0x1800bc749`
- `ADVAPI32!RegCreateKeyExW` at `0x1800bc673`
- `ADVAPI32!RegCreateKeyExW` at `0x1800bc71a`
- `ADVAPI32!RegCreateKeyExW` at `0x1800bc673`
- `ADVAPI32!RegCreateKeyExW` at `0x1800bc71a`

## pseudocode

```c
void __fastcall LockscreenBackupRestoreHandler::ApplyLockscreenFunFactsAndMore(
        LockscreenBackupRestoreHandler *this,
        unsigned __int8 a2)
{
  int v2; // ebx
  int v3; // eax
  int CurrentUserSidString; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  int dwOptions; // [rsp+20h] [rbp-29h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-29h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-29h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-29h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-29h]
  HKEY phkResult; // [rsp+50h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+Fh] BYREF
  LPCWSTR v16; // [rsp+60h] [rbp+17h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp+1Fh] BYREF
  _BYTE v18[48]; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  LockscreenBackupRestoreHandler *v20; // [rsp+B0h] [rbp+67h] BYREF
  int Data; // [rsp+B8h] [rbp+6Fh] BYREF
  LPWSTR StringSid; // [rsp+C0h] [rbp+77h] BYREF
  char v23; // [rsp+C8h] [rbp+7Fh] BYREF

  v20 = this;
  v2 = a2;
  v3 = SHRegSetDWORD(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager",
         L"RotatingLockScreenOverlayEnabled",
         a2);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)(unsigned int)v3,
      dwOptions);
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  CurrentUserSidString = GetCurrentUserSidString(&StringSid);
  if ( CurrentUserSidString < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)(unsigned int)CurrentUserSidString,
      dwOptions);
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpSubKey,
    L"%s\\%s",
    StringSid,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager");
  hKey = 0;
  v5 = RegCreateKeyExW(HKEY_USERS, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x84,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)v5,
      dwOptionsa);
  Data = v2;
  v6 = RegSetKeyValueW(hKey, 0, L"RotatingLockScreenOverlayEnabled", 4u, &Data, 4u);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x87,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)v6,
      dwOptionsb);
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v16,
    L"%s\\%s",
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Creative",
    StringSid);
  phkResult = 0;
  v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v16, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x8E,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)v7,
      dwOptionsc);
  v8 = RegSetKeyValueW(phkResult, 0, L"RotatingLockScreenOverlayEnabled", 4u, &Data, 4u);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x90,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
      (const char *)v8,
      dwOptionsd);
  winrt::Windows::Services::TargetedContent::Internal::TargetedContentSubscriptionInternal::TargetedContentSubscriptionInternal((winrt::Windows::Services::TargetedContent::Internal::TargetedContentSubscriptionInternal *)&v23);
  LODWORD(v20) = 1;
  winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"Locksreen");
  winrt::impl::consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal<winrt::Windows::Services::TargetedContent::Internal::ITargetedContentSubscriptionInternal>::SetSubscriptionConfiguration(
    &v23,
    v18,
    &v20);
  winrt::param::hstring::hstring((winrt::param::hstring *)v18, L"Locksreen");
  winrt::impl::consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal<winrt::Windows::Services::TargetedContent::Internal::ITargetedContentSubscriptionInternal>::ReactivateSubscription(
    &v23,
    v18);
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v23);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&StringSid);
}

```

## disassembly

```asm
0x1800bc5ac  mov     [rsp-8+arg_0], rcx
0x1800bc5b1  push    rbp
0x1800bc5b2  push    rbx
0x1800bc5b3  lea     rbp, [rsp-4Fh]
0x1800bc5b8  sub     rsp, 98h
0x1800bc5bf  movzx   ebx, dl
0x1800bc5c2  mov     r9d, ebx; unsigned int
0x1800bc5c5  lea     r8, ValueName; "RotatingLockScreenOverlayEnabled"
0x1800bc5cc  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800bc5d3  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800bc5da  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800bc5df  mov     rcx, [rbp+5Fh]; this
0x1800bc5e3  test    eax, eax
0x1800bc5e5  js      loc_1800BC805
0x1800bc5eb  mov     [rbp+57h+StringSid], 0
0x1800bc5f3  xor     edx, edx
0x1800bc5f5  lea     rcx, [rbp+57h+StringSid]
0x1800bc5f9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800bc5fe  lea     rcx, [rbp+57h+StringSid]; StringSid
0x1800bc602  call    ?GetCurrentUserSidString@@YAJPEAPEAG@Z; GetCurrentUserSidString(ushort * *)
0x1800bc607  mov     rcx, [rbp+5Fh]; this
0x1800bc60b  test    eax, eax
0x1800bc60d  js      loc_1800BC81A
0x1800bc613  lea     r9, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800bc61a  mov     r8, [rbp+57h+StringSid]
0x1800bc61e  lea     rdx, aSS; "%s\\%s"
0x1800bc625  lea     rcx, [rbp+57h+lpSubKey]
0x1800bc629  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x1800bc62e  nop
0x1800bc62f  mov     [rbp+57h+hKey], 0
0x1800bc637  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x1800bc640  lea     rax, [rbp+57h+hKey]
0x1800bc644  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800bc649  mov     [rsp+0A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800bc652  mov     [rsp+0A0h+samDesired], 0F003Fh; samDesired
0x1800bc65a  mov     [rsp+0A0h+dwOptions], 0; unsigned int
0x1800bc662  xor     r9d, r9d; lpClass
0x1800bc665  xor     r8d, r8d; Reserved
0x1800bc668  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800bc66c  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800bc673  call    cs:__imp_RegCreateKeyExW
0x1800bc679  mov     rcx, [rbp+5Fh]; this
0x1800bc67d  test    eax, eax
0x1800bc67f  jnz     loc_1800BC82F
0x1800bc685  mov     [rbp+57h+Data], ebx
0x1800bc688  lea     ebx, [rax+4]
0x1800bc68b  mov     [rsp+0A0h+samDesired], ebx; cbData
0x1800bc68f  lea     rax, [rbp+57h+Data]
0x1800bc693  mov     qword ptr [rsp+0A0h+dwOptions], rax; unsigned int
0x1800bc698  mov     r9d, ebx; dwType
0x1800bc69b  lea     r8, ValueName; "RotatingLockScreenOverlayEnabled"
0x1800bc6a2  xor     edx, edx; lpSubKey
0x1800bc6a4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800bc6a8  call    cs:__imp_RegSetKeyValueW
0x1800bc6ae  mov     rcx, [rbp+5Fh]; this
0x1800bc6b2  test    eax, eax
0x1800bc6b4  jnz     loc_1800BC844
0x1800bc6ba  mov     r9, [rbp+57h+StringSid]
0x1800bc6be  lea     r8, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800bc6c5  lea     rdx, aSS; "%s\\%s"
0x1800bc6cc  lea     rcx, [rbp+57h+var_40]
0x1800bc6d0  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x1800bc6d5  nop
0x1800bc6d6  mov     [rbp+57h+var_50], 0
0x1800bc6de  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x1800bc6e7  lea     rax, [rbp+57h+var_50]
0x1800bc6eb  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800bc6f0  mov     [rsp+0A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800bc6f9  mov     [rsp+0A0h+samDesired], 0F003Fh; samDesired
0x1800bc701  mov     [rsp+0A0h+dwOptions], 0; unsigned int
0x1800bc709  xor     r9d, r9d; lpClass
0x1800bc70c  xor     r8d, r8d; Reserved
0x1800bc70f  mov     rdx, [rbp+57h+var_40]; lpSubKey
0x1800bc713  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bc71a  call    cs:__imp_RegCreateKeyExW
0x1800bc720  mov     rcx, [rbp+5Fh]; this
0x1800bc724  test    eax, eax
0x1800bc726  jnz     loc_1800BC859
0x1800bc72c  mov     [rsp+0A0h+samDesired], ebx; cbData
0x1800bc730  lea     rax, [rbp+57h+Data]
0x1800bc734  mov     qword ptr [rsp+0A0h+dwOptions], rax; unsigned int
0x1800bc739  mov     r9d, ebx; dwType
0x1800bc73c  lea     r8, ValueName; "RotatingLockScreenOverlayEnabled"
0x1800bc743  xor     edx, edx; lpSubKey
0x1800bc745  mov     rcx, [rbp+57h+var_50]; hKey
0x1800bc749  call    cs:__imp_RegSetKeyValueW
0x1800bc74f  mov     rcx, [rbp+5Fh]; this
0x1800bc753  test    eax, eax
0x1800bc755  jnz     loc_1800BC7F0
0x1800bc75b  lea     rcx, [rbp+57h+arg_18]; this
0x1800bc75f  call    ??0TargetedContentSubscriptionInternal@Internal@TargetedContent@Services@Windows@winrt@@QEAA@XZ; winrt::Windows::Services::TargetedContent::Internal::TargetedContentSubscriptionInternal::TargetedContentSubscriptionInternal(void)
0x1800bc764  nop
0x1800bc765  mov     dword ptr [rbp+57h+arg_0], 1
0x1800bc76c  lea     rdx, aLocksreen; "Locksreen"
0x1800bc773  lea     rcx, [rbp+57h+var_30]; this
0x1800bc777  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800bc77c  lea     r8, [rbp+57h+arg_0]
0x1800bc780  lea     rdx, [rbp+57h+var_30]
0x1800bc784  lea     rcx, [rbp+57h+arg_18]
0x1800bc788  call    ?SetSubscriptionConfiguration@?$consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal@UITargetedContentSubscriptionInternal@Internal@TargetedContent@Services@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBW4TargetedContentConfigurationKinds@Internal@TargetedContent@Services@Windows@3@@Z; winrt::impl::consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal<winrt::Windows::Services::TargetedContent::Internal::ITargetedContentSubscriptionInternal>::SetSubscriptionConfiguration(winrt::param::hstring const &,winrt::Windows::Services::TargetedContent::Internal::TargetedContentConfigurationKinds const &)
0x1800bc78d  lea     rdx, aLocksreen; "Locksreen"
0x1800bc794  lea     rcx, [rbp+57h+var_30]; this
0x1800bc798  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800bc79d  lea     rdx, [rbp+57h+var_30]
0x1800bc7a1  lea     rcx, [rbp+57h+arg_18]
0x1800bc7a5  call    ?ReactivateSubscription@?$consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal@UITargetedContentSubscriptionInternal@Internal@TargetedContent@Services@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Services_TargetedContent_Internal_ITargetedContentSubscriptionInternal<winrt::Windows::Services::TargetedContent::Internal::ITargetedContentSubscriptionInternal>::ReactivateSubscription(winrt::param::hstring const &)
0x1800bc7aa  nop
0x1800bc7ab  lea     rcx, [rbp+57h+arg_18]; this
0x1800bc7af  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800bc7b4  nop
0x1800bc7b5  lea     rcx, [rbp+57h+var_50]
0x1800bc7b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bc7be  nop
0x1800bc7bf  lea     rcx, [rbp+57h+var_40]
0x1800bc7c3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800bc7c8  nop
0x1800bc7c9  lea     rcx, [rbp+57h+hKey]
0x1800bc7cd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800bc7d2  nop
0x1800bc7d3  lea     rcx, [rbp+57h+lpSubKey]
0x1800bc7d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800bc7dc  nop
0x1800bc7dd  lea     rcx, [rbp+57h+StringSid]
0x1800bc7e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800bc7e6  add     rsp, 98h
0x1800bc7ed  pop     rbx
0x1800bc7ee  pop     rbp
0x1800bc7ef  retn
0x1800bc7f0  mov     r9d, eax; char *
0x1800bc7f3  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bc7fa  mov     edx, 90h; void *
0x1800bc7ff  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800bc805  mov     r9d, eax; char *
0x1800bc808  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bc80f  mov     edx, 7Ah ; 'z'; void *
0x1800bc814  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bc81a  mov     r9d, eax; char *
0x1800bc81d  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bc824  mov     edx, 7Dh ; '}'; void *
0x1800bc829  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800bc82f  mov     r9d, eax; char *
0x1800bc832  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bc839  mov     edx, 84h; void *
0x1800bc83e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800bc844  mov     r9d, eax; char *
0x1800bc847  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bc84e  mov     edx, 87h; void *
0x1800bc853  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800bc859  mov     r9d, eax; char *
0x1800bc85c  lea     r8, aPcshellShellCl_27; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800bc863  mov     edx, 8Eh; void *
0x1800bc868  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
